---
title: シリアル化 (C#)
ms.date: 04/26/2018
ms.openlocfilehash: 638fdbd31912ffeb284d734e1f8ce2ecd879b540
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61680110"
---
# <a name="serialization-c"></a><span data-ttu-id="e009a-102">シリアル化 (C#)</span><span class="sxs-lookup"><span data-stu-id="e009a-102">Serialization (C#)</span></span>

<span data-ttu-id="e009a-103">シリアル化は、オブジェクトを格納するか、メモリ、データベース、またはファイルに転送するためにバイト ストリームに変換するプロセスです。</span><span class="sxs-lookup"><span data-stu-id="e009a-103">Serialization is the process of converting an object into a stream of bytes to store the object or transmit it to memory, a database, or a file.</span></span> <span data-ttu-id="e009a-104">その主な目的は、必要なときに再作成できるように、オブジェクトの状態を保存しておくことです。</span><span class="sxs-lookup"><span data-stu-id="e009a-104">Its main purpose is to save the state of an object in order to be able to recreate it when needed.</span></span> <span data-ttu-id="e009a-105">逆のプロセスは、逆シリアル化と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="e009a-105">The reverse process is called deserialization.</span></span>

## <a name="how-serialization-works"></a><span data-ttu-id="e009a-106">シリアル化のしくみ</span><span class="sxs-lookup"><span data-stu-id="e009a-106">How serialization works</span></span>

<span data-ttu-id="e009a-107">この図は、シリアル化の全体的なプロセスを示しています:</span><span class="sxs-lookup"><span data-stu-id="e009a-107">This illustration shows the overall process of serialization:</span></span>

![シリアル化グラフィック](./media/index/serialization-process.gif)

<span data-ttu-id="e009a-109">オブジェクトは、データだけでなく、バージョン、カルチャ、アセンブリ名などのオブジェクトの型に関する情報も伝達するストリームにシリアル化されます。</span><span class="sxs-lookup"><span data-stu-id="e009a-109">The object is serialized to a stream, which carries not just the data, but information about the object's type, such as its version, culture, and assembly name.</span></span> <span data-ttu-id="e009a-110">そのストリームから、オブジェクトをデータベース、ファイル、またはメモリに格納できます。</span><span class="sxs-lookup"><span data-stu-id="e009a-110">From that stream, it can be stored in a database, a file, or memory.</span></span>

### <a name="uses-for-serialization"></a><span data-ttu-id="e009a-111">シリアル化の使用方法</span><span class="sxs-lookup"><span data-stu-id="e009a-111">Uses for serialization</span></span>

<span data-ttu-id="e009a-112">開発者は、シリアル化を使用して、オブジェクトの状態を保存し、必要に応じて、オブジェクトのストレージとデータ交換を指定することで、オブジェクトを再作成することができます。</span><span class="sxs-lookup"><span data-stu-id="e009a-112">Serialization allows the developer to save the state of an object and recreate it as needed, providing storage of objects as well as data exchange.</span></span> <span data-ttu-id="e009a-113">シリアル化を通じて、開発者は、Web サービスによるリモート アプリケーションへのオブジェクトの送信、ドメイン間のオブジェクトの受け渡し、XML 文字列としてのオブジェクトのファイアウォールの通過、アプリケーション間でのセキュリティまたはユーザー固有情報の維持などの操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="e009a-113">Through serialization, a developer can perform actions like sending the object to a remote application by means of a Web Service, passing an object from one domain to another, passing an object through a firewall as an XML string, or maintaining security or user-specific information across applications.</span></span>

### <a name="making-an-object-serializable"></a><span data-ttu-id="e009a-114">オブジェクトをシリアル化可能にする</span><span class="sxs-lookup"><span data-stu-id="e009a-114">Making an object serializable</span></span>

<span data-ttu-id="e009a-115">オブジェクトをシリアル化するには、シリアル化するオブジェクト、シリアル化したオブジェクトを格納するストリーム、および <xref:System.Runtime.Serialization.Formatter> が必要です。</span><span class="sxs-lookup"><span data-stu-id="e009a-115">To serialize an object, you need the object to be serialized, a stream to contain the serialized object, and a <xref:System.Runtime.Serialization.Formatter>.</span></span> <span data-ttu-id="e009a-116"><xref:System.Runtime.Serialization> には、オブジェクトのシリアル化と逆シリアル化に必要なクラスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="e009a-116"><xref:System.Runtime.Serialization> contains the classes necessary for serializing and deserializing objects.</span></span>

<span data-ttu-id="e009a-117">この型のインスタンスをシリアル化できることを示すには、<xref:System.SerializableAttribute> 属性を適用します。</span><span class="sxs-lookup"><span data-stu-id="e009a-117">Apply the <xref:System.SerializableAttribute> attribute to a type to indicate that instances of this type can be serialized.</span></span> <span data-ttu-id="e009a-118">型に <xref:System.SerializableAttribute> 属性が適用されていない状態でシリアル化しようとすると、例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="e009a-118">An  exception is thrown if you attempt to serialize but the type doesn't have the <xref:System.SerializableAttribute> attribute.</span></span>

<span data-ttu-id="e009a-119">クラス内のフィールドをシリアル化しない場合は、<xref:System.NonSerializedAttribute> 属性を適用します。</span><span class="sxs-lookup"><span data-stu-id="e009a-119">If you don't want a field within your class to be serializable, apply the <xref:System.NonSerializedAttribute> attribute.</span></span> <span data-ttu-id="e009a-120">シリアル化できる型のフィールドに、特定の環境に固有のポインター、ハンドル、その他のデータ構造が含まれているときに、そのフィールドを別の環境で意味があるように再構成できない場合は、シリアル化不可にすることができます。</span><span class="sxs-lookup"><span data-stu-id="e009a-120">If a field of a serializable type contains a pointer, a handle, or some other data structure that is specific to a particular environment, and the field cannot be meaningfully reconstituted in a different environment, then you may want to make it nonserializable.</span></span>

<span data-ttu-id="e009a-121">シリアル化されたクラスに、<xref:System.SerializableAttribute> とマークされている他のクラスのオブジェクトへの参照が含まれている場合は、これらのオブジェクトもシリアル化されます。</span><span class="sxs-lookup"><span data-stu-id="e009a-121">If a serialized class contains references to objects of other classes that are marked <xref:System.SerializableAttribute>, those objects will also be serialized.</span></span>

## <a name="binary-and-xml-serialization"></a><span data-ttu-id="e009a-122">バイナリ シリアル化と XML シリアル化</span><span class="sxs-lookup"><span data-stu-id="e009a-122">Binary and XML serialization</span></span>

<span data-ttu-id="e009a-123">バイナリまたは XML シリアル化を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="e009a-123">You can use binary or XML serialization.</span></span> <span data-ttu-id="e009a-124">バイナリ シリアル化では、読み取り専用メンバーも含め、すべてのメンバーがシリアル化され、パフォーマンスが向上します。</span><span class="sxs-lookup"><span data-stu-id="e009a-124">In binary serialization, all members, even members that are read-only, are serialized, and performance is enhanced.</span></span> <span data-ttu-id="e009a-125">XML シリアル化では、コードの読みやすさだけではなく、オブジェクトの共有と相互運用を行うための柔軟性が増加します。</span><span class="sxs-lookup"><span data-stu-id="e009a-125">XML serialization provides more readable code, and greater flexibility of object sharing and usage for interoperability purposes.</span></span>

### <a name="binary-serialization"></a><span data-ttu-id="e009a-126">バイナリ シリアル化</span><span class="sxs-lookup"><span data-stu-id="e009a-126">Binary serialization</span></span>

<span data-ttu-id="e009a-127">バイナリ シリアル化では、バイナリ エンコードを使用して、ストレージやソケット ベースのネットワーク ストリームなどのためのコンパクトなシリアル化を生成します。</span><span class="sxs-lookup"><span data-stu-id="e009a-127">Binary serialization uses binary encoding to produce compact serialization for uses such as storage or socket-based network streams.</span></span>

### <a name="xml-serialization"></a><span data-ttu-id="e009a-128">XML シリアル化</span><span class="sxs-lookup"><span data-stu-id="e009a-128">XML serialization</span></span>

<span data-ttu-id="e009a-129">XML シリアル化では、オブジェクトのパブリック フィールドやパブリック プロパティ、またはメソッドのパラメーターや戻り値を、特定の XML スキーマ定義言語 (XSD) ドキュメントに準拠する XML ストリームにシリアル化します。</span><span class="sxs-lookup"><span data-stu-id="e009a-129">XML serialization serializes the public fields and properties of an object, or the parameters and return values of methods, into an XML stream that conforms to a specific XML Schema definition language (XSD) document.</span></span> <span data-ttu-id="e009a-130">XML シリアル化では、XML に変換されるパブリック プロパティとパブリック フィールドによって厳密に型指定されたクラスが生成されます。</span><span class="sxs-lookup"><span data-stu-id="e009a-130">XML serialization results in strongly typed classes with public properties and fields that are converted to XML.</span></span> <span data-ttu-id="e009a-131"><xref:System.Xml.Serialization> には、XML のシリアル化と逆シリアル化に必要なクラスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="e009a-131"><xref:System.Xml.Serialization> contains the classes necessary for serializing and deserializing XML.</span></span>

<span data-ttu-id="e009a-132">属性をクラスおよびクラス メンバーに適用すると、<xref:System.Xml.Serialization.XmlSerializer> がそのクラスのインスタンスをシリアル化または逆シリアル化する方法を制御できます。</span><span class="sxs-lookup"><span data-stu-id="e009a-132">You apply attributes to classes and class members to control the way the <xref:System.Xml.Serialization.XmlSerializer> serializes or deserializes an instance of the class.</span></span>

## <a name="basic-and-custom-serialization"></a><span data-ttu-id="e009a-133">基本的なシリアル化とカスタムのシリアル化</span><span class="sxs-lookup"><span data-stu-id="e009a-133">Basic and custom serialization</span></span>

<span data-ttu-id="e009a-134">シリアル化は、2 つの方法で実行できます (基本およびカスタム)。</span><span class="sxs-lookup"><span data-stu-id="e009a-134">Serialization can be performed in two ways, basic and custom.</span></span> <span data-ttu-id="e009a-135">基本的なシリアル化では、.NET Framework を使用して、オブジェクトが自動的にシリアル化されます。</span><span class="sxs-lookup"><span data-stu-id="e009a-135">Basic serialization uses the .NET Framework to automatically serialize the object.</span></span>

### <a name="basic-serialization"></a><span data-ttu-id="e009a-136">基本的なシリアル化</span><span class="sxs-lookup"><span data-stu-id="e009a-136">Basic serialization</span></span>

<span data-ttu-id="e009a-137">基本的なシリアル化の唯一の要件は、オブジェクトに <xref:System.SerializableAttribute> 属性が適用されていることです。</span><span class="sxs-lookup"><span data-stu-id="e009a-137">The only requirement in basic serialization is that the object has the <xref:System.SerializableAttribute> attribute applied.</span></span> <span data-ttu-id="e009a-138"><xref:System.NonSerializedAttribute> を使用して、特定のフィールドがシリアル化されないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="e009a-138">The <xref:System.NonSerializedAttribute> can be used to keep specific fields from being serialized.</span></span>

<span data-ttu-id="e009a-139">基本的なシリアル化を使用する場合、オブジェクトのバージョン管理によって問題が発生する場合があります。</span><span class="sxs-lookup"><span data-stu-id="e009a-139">When you use basic serialization, the versioning of objects may create problems.</span></span> <span data-ttu-id="e009a-140">バージョン管理の問題が重要な場合は、カスタムのシリアル化を使用します。</span><span class="sxs-lookup"><span data-stu-id="e009a-140">You would use custom serialization when versioning issues are important.</span></span> <span data-ttu-id="e009a-141">基本的なシリアル化は、シリアル化を実行する最も簡単な方法ですが、プロセスを細かく制御することはできません。</span><span class="sxs-lookup"><span data-stu-id="e009a-141">Basic serialization is the easiest way to perform serialization, but it does not provide much control over the process.</span></span>

### <a name="custom-serialization"></a><span data-ttu-id="e009a-142">カスタムのシリアル化</span><span class="sxs-lookup"><span data-stu-id="e009a-142">Custom serialization</span></span>

<span data-ttu-id="e009a-143">カスタムのシリアル化では、シリアル化するオブジェクトとシリアル化の方法を正確を指定できます。</span><span class="sxs-lookup"><span data-stu-id="e009a-143">In custom serialization, you can specify exactly which objects will be serialized and how it will be done.</span></span> <span data-ttu-id="e009a-144">クラスを <xref:System.SerializableAttribute> でマークし、<xref:System.Runtime.Serialization.ISerializable> インターフェイスを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e009a-144">The class must be marked <xref:System.SerializableAttribute> and implement the <xref:System.Runtime.Serialization.ISerializable> interface.</span></span>

<span data-ttu-id="e009a-145">カスタムの方法でオブジェクトを逆シリアル化する場合は、カスタム コンストラクターを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e009a-145">If you want your object to be deserialized in a custom manner as well, you must use a custom constructor.</span></span>

## <a name="designer-serialization"></a><span data-ttu-id="e009a-146">デザイナーのシリアル化</span><span class="sxs-lookup"><span data-stu-id="e009a-146">Designer serialization</span></span>

<span data-ttu-id="e009a-147">デザイナーのシリアル化はシリアル化の特殊な形式であり、開発ツールに関連付けられているオブジェクトの永続性の種類を含みます。</span><span class="sxs-lookup"><span data-stu-id="e009a-147">Designer serialization is a special form of serialization that involves the kind of object persistence associated with development tools.</span></span> <span data-ttu-id="e009a-148">デザイナーのシリアル化は、後でオブジェクト グラフを復元できるように、オブジェクト グラフをソース ファイルに変換するプロセスです。</span><span class="sxs-lookup"><span data-stu-id="e009a-148">Designer serialization is the process of converting an object graph into a source file that can later be used to recover the object graph.</span></span> <span data-ttu-id="e009a-149">ソース ファイルには、コードとマークアップを含めることができますが、SQL テーブル情報を含めることもできます。</span><span class="sxs-lookup"><span data-stu-id="e009a-149">A source file can contain code, markup, or even SQL table information.</span></span>

## <span data-ttu-id="e009a-150"><a name="BKMK_RelatedTopics">関連トピックと例</a></span><span class="sxs-lookup"><span data-stu-id="e009a-150"><a name="BKMK_RelatedTopics"></a> Related Topics and Examples</span></span>  
[<span data-ttu-id="e009a-151">チュートリアル: オブジェクトの永続化 (Visual Studio (C#))</span><span class="sxs-lookup"><span data-stu-id="e009a-151">Walkthrough: Persisting an Object in Visual Studio (C#)</span></span>](walkthrough-persisting-an-object-in-visual-studio.md)  
<span data-ttu-id="e009a-152">シリアル化によってインスタンス間でオブジェクトのデータを永続化して値を保存しておき、次にそのオブジェクトをインスタンス化するときにその値を取得する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="e009a-152">Demonstrates how serialization can be used to persist an object's data between instances, allowing you to store values and retrieve them the next time the object is instantiated.</span></span>

[<span data-ttu-id="e009a-153">方法: XML ファイルからオブジェクト データを読み込む (C#)</span><span class="sxs-lookup"><span data-stu-id="e009a-153">How to: Read Object Data from an XML File (C#)</span></span>](how-to-read-object-data-from-an-xml-file.md)  
 <span data-ttu-id="e009a-154"><xref:System.Xml.Serialization.XmlSerializer> クラスを使用して、XML ファイルに以前に書き込まれたオブジェクト データを読み込む方法を示します。</span><span class="sxs-lookup"><span data-stu-id="e009a-154">Shows how to read object data that was previously written to an XML file using the <xref:System.Xml.Serialization.XmlSerializer> class.</span></span>

[<span data-ttu-id="e009a-155">方法: XML ファイルにオブジェクト データを書き込む (C#)</span><span class="sxs-lookup"><span data-stu-id="e009a-155">How to: Write Object Data to an XML File (C#)</span></span>](how-to-write-object-data-to-an-xml-file.md)  
<span data-ttu-id="e009a-156"><xref:System.Xml.Serialization.XmlSerializer> クラスを使用して、クラスから XML ファイルにオブジェクトを書き込む方法を示します。</span><span class="sxs-lookup"><span data-stu-id="e009a-156">Shows how to write the object from a class to an XML file using the <xref:System.Xml.Serialization.XmlSerializer> class.</span></span>
