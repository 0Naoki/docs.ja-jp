---
title: -リンク (Visual Basic)
ms.date: 03/10/2018
helpviewer_keywords:
- l compiler option [Visual Basic]
- EmbedInteropTypes
- embed interop types [COM Interop]
- -link compiler option [Visual Basic]
- /link compiler option [Visual Basic]
- link compiler option [Visual Basic]
- -l compiler option [Visual Basic]
- /l compiler option [Visual Basic]
ms.assetid: 1885f24a-86f5-486c-a064-9fb7e455ccec
ms.openlocfilehash: b13d8266d0702d831a0f5ebb3a9586864fe22ccb
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2019
ms.locfileid: "65586533"
---
# <a name="-link-visual-basic"></a><span data-ttu-id="afbda-102">-リンク (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="afbda-102">-link (Visual Basic)</span></span>
<span data-ttu-id="afbda-103">指定したアセンブリ内の COM 型情報を、現在のコンパイル対象のプロジェクトで使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="afbda-103">Causes the compiler to make COM type information in the specified assemblies available to the project that you are currently compiling.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="afbda-104">構文</span><span class="sxs-lookup"><span data-stu-id="afbda-104">Syntax</span></span>  
  
```  
-link:fileList  
' -or-  
-l:fileList  
```  
  
## <a name="arguments"></a><span data-ttu-id="afbda-105">引数</span><span class="sxs-lookup"><span data-stu-id="afbda-105">Arguments</span></span>  
  
|<span data-ttu-id="afbda-106">用語</span><span class="sxs-lookup"><span data-stu-id="afbda-106">Term</span></span>|<span data-ttu-id="afbda-107">定義</span><span class="sxs-lookup"><span data-stu-id="afbda-107">Definition</span></span>|  
|---|---|  
|`fileList`|<span data-ttu-id="afbda-108">必須。</span><span class="sxs-lookup"><span data-stu-id="afbda-108">Required.</span></span> <span data-ttu-id="afbda-109">アセンブリ ファイル名のコンマ区切りリスト。</span><span class="sxs-lookup"><span data-stu-id="afbda-109">Comma-delimited list of assembly file names.</span></span> <span data-ttu-id="afbda-110">ファイル名に空白が含まれている場合は、名前を二重引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="afbda-110">If the file name contains a space, enclose the name in quotation marks.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="afbda-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="afbda-111">Remarks</span></span>  
 <span data-ttu-id="afbda-112">`-link` オプションを使用すると、埋め込み型情報を含むアプリケーションを配置できます。</span><span class="sxs-lookup"><span data-stu-id="afbda-112">The `-link` option enables you to deploy an application that has embedded type information.</span></span> <span data-ttu-id="afbda-113">その後、このアプリケーションは、埋め込み型情報を実装する、ランタイム アセンブリ内の型を使用できます。その際、ランタイム アセンブリへの参照は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="afbda-113">The application can then use types in a runtime assembly that implement the embedded type information without requiring a reference to the runtime assembly.</span></span> <span data-ttu-id="afbda-114">ランタイム アセンブリのさまざまなバージョンが公開されている場合、埋め込み型情報を含むアプリケーションは、再コンパイルする必要なく、各種バージョンで動作できます。</span><span class="sxs-lookup"><span data-stu-id="afbda-114">If various versions of the runtime assembly are published, the application that contains the embedded type information can work with the various versions without having to be recompiled.</span></span> <span data-ttu-id="afbda-115">例については、「[チュートリアル:マネージド アセンブリからの型の埋め込み](../../../visual-basic/programming-guide/concepts/assemblies-gac/walkthrough-embedding-types-from-managed-assemblies-in-vs.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="afbda-115">For an example, see [Walkthrough: Embedding Types from Managed Assemblies](../../../visual-basic/programming-guide/concepts/assemblies-gac/walkthrough-embedding-types-from-managed-assemblies-in-vs.md).</span></span>  
  
 <span data-ttu-id="afbda-116">`-link` オプションの使用は、COM 相互運用を使用している場合に特に便利です。</span><span class="sxs-lookup"><span data-stu-id="afbda-116">Using the `-link` option is especially useful when you are working with COM interop.</span></span> <span data-ttu-id="afbda-117">COM 型を埋め込むことができるため、アプリケーションは、ターゲット コンピューター上にプライマリ相互運用機能アセンブリ (PIA) を必要としなくなります。</span><span class="sxs-lookup"><span data-stu-id="afbda-117">You can embed COM types so that your application no longer requires a primary interop assembly (PIA) on the target computer.</span></span> <span data-ttu-id="afbda-118">`-link` オプションを使用すると、コンパイラによって、COM 型情報は、参照先の相互運用アセンブリから結果としてコンパイルされるコードに埋め込まれます。</span><span class="sxs-lookup"><span data-stu-id="afbda-118">The `-link` option instructs the compiler to embed the COM type information from the referenced interop assembly into the resulting compiled code.</span></span> <span data-ttu-id="afbda-119">COM 型は、CLSID (GUID) 値によって識別されます。</span><span class="sxs-lookup"><span data-stu-id="afbda-119">The COM type is identified by the CLSID (GUID) value.</span></span> <span data-ttu-id="afbda-120">その結果、同じ CLSID 値の同じ COM 型がインストールされているターゲット コンピューターでアプリケーションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="afbda-120">As a result, your application can run on a target computer that has installed the same COM types with the same CLSID values.</span></span> <span data-ttu-id="afbda-121">Microsoft Office を自動化するアプリケーションが良い例です。</span><span class="sxs-lookup"><span data-stu-id="afbda-121">Applications that automate Microsoft Office are a good example.</span></span> <span data-ttu-id="afbda-122">Office のようなアプリケーションは、通常、さまざまなバージョン間で同じ CLSID 値を保持するため、.NET Framework 4 以降がターゲット コンピューターにインストールされていて、参照先の COM 型に含まれているメソッド、プロパティ、またはイベントがアプリケーションで使用される限りは、そのアプリケーションで参照先の COM 型を使用できます。</span><span class="sxs-lookup"><span data-stu-id="afbda-122">Because applications like Office usually keep the same CLSID value across different versions, your application can use the referenced COM types as long as .NET Framework 4 or later is installed on the target computer and your application uses methods, properties, or events that are included in the referenced COM types.</span></span>  
  
 <span data-ttu-id="afbda-123">`-link` オプションで埋め込まれるのは、インターフェイス、構造体、デリゲートのみです。</span><span class="sxs-lookup"><span data-stu-id="afbda-123">The `-link` option embeds only interfaces, structures, and delegates.</span></span> <span data-ttu-id="afbda-124">COM クラスの埋め込みはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="afbda-124">Embedding COM classes is not supported.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="afbda-125">コードで埋め込み COM 型のインスタンスを作成する際は、適切なインターフェイスを使用してインスタンスを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="afbda-125">When you create an instance of an embedded COM type in your code, you must create the instance by using the appropriate interface.</span></span> <span data-ttu-id="afbda-126">コクラスを使用して埋め込み COM 型のインスタンスを作成しようとすると、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="afbda-126">Attempting to create an instance of an embedded COM type by using the CoClass causes an error.</span></span>  
  
 <span data-ttu-id="afbda-127">Visual Studio で `-link` オプションを設定するには、アセンブリ参照を追加し、`Embed Interop Types` プロパティを **true** に設定します。</span><span class="sxs-lookup"><span data-stu-id="afbda-127">To set the `-link` option in Visual Studio, add an assembly reference and set the `Embed Interop Types` property to **true**.</span></span> <span data-ttu-id="afbda-128">`Embed Interop Types` プロパティの既定値は **false** です。</span><span class="sxs-lookup"><span data-stu-id="afbda-128">The default for the `Embed Interop Types` property is **false**.</span></span>  
  
 <span data-ttu-id="afbda-129">別の COM アセンブリ (アセンブリ B) を参照する COM アセンブリ (アセンブリ A) にリンクする場合、次のいずれかが当てはまるときは、アセンブリ B にもリンクする必要があります。</span><span class="sxs-lookup"><span data-stu-id="afbda-129">If you link to a COM assembly (Assembly A) which itself references another COM assembly (Assembly B), you also have to link to Assembly B if either of the following is true:</span></span>  
  
- <span data-ttu-id="afbda-130">アセンブリ A の型がアセンブリ B の型から継承されているか、アセンブリ B のインターフェイスを実装する。</span><span class="sxs-lookup"><span data-stu-id="afbda-130">A type from Assembly A inherits from a type or implements an interface from Assembly B.</span></span>  
  
- <span data-ttu-id="afbda-131">アセンブリ B の戻り値の型またはパラメーターの型を使用するフィールド、プロパティ、イベント、またはメソッドが呼び出される。</span><span class="sxs-lookup"><span data-stu-id="afbda-131">A field, property, event, or method that has a return type or parameter type from Assembly B is invoked.</span></span>  
  
 <span data-ttu-id="afbda-132">使用[-libpath](../../../visual-basic/reference/command-line-compiler/libpath.md)を 1 つ以上のアセンブリ参照があるディレクトリを指定します。</span><span class="sxs-lookup"><span data-stu-id="afbda-132">Use [-libpath](../../../visual-basic/reference/command-line-compiler/libpath.md) to specify the directory in which one or more of your assembly references is located.</span></span>  
  
 <span data-ttu-id="afbda-133">ように、 [/reference](../../../visual-basic/reference/command-line-compiler/reference.md)コンパイラ オプション、`-link`コンパイラ オプションは頻繁に使用される .NET Framework アセンブリを参照する、Vbc.rsp 応答ファイルを使用します。</span><span class="sxs-lookup"><span data-stu-id="afbda-133">Like the [/reference](../../../visual-basic/reference/command-line-compiler/reference.md) compiler option, the `-link` compiler option uses the Vbc.rsp response file, which references frequently used .NET Framework assemblies.</span></span> <span data-ttu-id="afbda-134">使用して、 [-noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md)コンパイラ オプション、コンパイラが Vbc.rsp ファイルを使用したくない場合。</span><span class="sxs-lookup"><span data-stu-id="afbda-134">Use the [-noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md) compiler option if you do not want the compiler to use the Vbc.rsp file.</span></span>  
  
 <span data-ttu-id="afbda-135">`-link` の省略形は `-l` です。</span><span class="sxs-lookup"><span data-stu-id="afbda-135">The short form of `-link` is `-l`.</span></span>  
  
## <a name="generics-and-embedded-types"></a><span data-ttu-id="afbda-136">ジェネリック型と埋め込み型</span><span class="sxs-lookup"><span data-stu-id="afbda-136">Generics and Embedded Types</span></span>  
 <span data-ttu-id="afbda-137">以降のセクションでは、相互運用機能型を埋め込むアプリケーションでジェネリック型を使用する際の制限事項について説明します。</span><span class="sxs-lookup"><span data-stu-id="afbda-137">The following sections describe the limitations on using generic types in applications that embed interop types.</span></span>  
  
### <a name="generic-interfaces"></a><span data-ttu-id="afbda-138">ジェネリック インターフェイス</span><span class="sxs-lookup"><span data-stu-id="afbda-138">Generic Interfaces</span></span>  
 <span data-ttu-id="afbda-139">相互運用アセンブリから埋め込まれるジェネリック インターフェイスを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="afbda-139">Generic interfaces that are embedded from an interop assembly cannot be used.</span></span> <span data-ttu-id="afbda-140">これを次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="afbda-140">This is shown in the following example.</span></span>  
  
 [!code-vb[VbLinkCompiler#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vblinkcompiler/vb/module1.vb#1)]  
  
### <a name="types-that-have-generic-parameters"></a><span data-ttu-id="afbda-141">ジェネリック パラメーターを含む型</span><span class="sxs-lookup"><span data-stu-id="afbda-141">Types That Have Generic Parameters</span></span>  
 <span data-ttu-id="afbda-142">型が相互運用アセンブリから埋め込まれているジェネリック パラメーターを含む型は、外部アセンブリからの型である場合に使用できません。</span><span class="sxs-lookup"><span data-stu-id="afbda-142">Types that have a generic parameter whose type is embedded from an interop assembly cannot be used if that type is from an external assembly.</span></span> <span data-ttu-id="afbda-143">この制限はインターフェイスには当てはまりません。</span><span class="sxs-lookup"><span data-stu-id="afbda-143">This restriction does not apply to interfaces.</span></span> <span data-ttu-id="afbda-144">たとえば、<xref:Microsoft.Office.Interop.Excel> アセンブリで定義されている <xref:Microsoft.Office.Interop.Excel.Range> インターフェイスについて考えます。</span><span class="sxs-lookup"><span data-stu-id="afbda-144">For example, consider the <xref:Microsoft.Office.Interop.Excel.Range> interface that is defined in the <xref:Microsoft.Office.Interop.Excel> assembly.</span></span> <span data-ttu-id="afbda-145">ライブラリによって <xref:Microsoft.Office.Interop.Excel> アセンブリから相互運用型が埋め込まれ、型が <xref:Microsoft.Office.Interop.Excel.Range> インターフェイスであるパラメーターを含むジェネリック型を返すメソッドが公開される場合、次のコード例に示すように、そのメソッドはジェネリック インターフェイスを返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="afbda-145">If a library embeds interop types from the <xref:Microsoft.Office.Interop.Excel> assembly and exposes a method that returns a generic type that has a parameter whose type is the <xref:Microsoft.Office.Interop.Excel.Range> interface, that method must return a generic interface, as shown in the following code example.</span></span>  
  
 [!code-vb[VbLinkCompiler#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vblinkcompiler/vb/utility.vb#2)]  
[!code-vb[VbLinkCompiler#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vblinkcompiler/vb/utility.vb#3)]  
[!code-vb[VbLinkCompiler#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vblinkcompiler/vb/utility.vb#4)]  
  
 <span data-ttu-id="afbda-146">次の例では、クライアント コードで、<xref:System.Collections.IList> ジェネリック インターフェイスを返すメソッドをエラーなしで呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="afbda-146">In the following example, client code can call the method that returns the <xref:System.Collections.IList> generic interface without error.</span></span>  
  
 [!code-vb[VbLinkCompiler#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vblinkcompiler/vb/module1.vb#5)]  
  
## <a name="example"></a><span data-ttu-id="afbda-147">例</span><span class="sxs-lookup"><span data-stu-id="afbda-147">Example</span></span>  
 <span data-ttu-id="afbda-148">次のコマンドラインは、ソース ファイルをコンパイル`OfficeApp.vb`からの参照アセンブリと`COMData1.dll`と`COMData2.dll`を生成する`OfficeApp.exe`します。</span><span class="sxs-lookup"><span data-stu-id="afbda-148">The following command line compiles source file `OfficeApp.vb` and reference assemblies from `COMData1.dll` and `COMData2.dll` to produce `OfficeApp.exe`.</span></span>  
  
```console  
vbc -link:COMData1.dll,COMData2.dll /out:OfficeApp.exe OfficeApp.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="afbda-149">関連項目</span><span class="sxs-lookup"><span data-stu-id="afbda-149">See also</span></span>

- [<span data-ttu-id="afbda-150">Visual Basic のコマンド ライン コンパイラ</span><span class="sxs-lookup"><span data-stu-id="afbda-150">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="afbda-151">チュートリアル: マネージド アセンブリからの型の埋め込み</span><span class="sxs-lookup"><span data-stu-id="afbda-151">Walkthrough: Embedding Types from Managed Assemblies</span></span>](../../../visual-basic/programming-guide/concepts/assemblies-gac/walkthrough-embedding-types-from-managed-assemblies-in-vs.md)
- [<span data-ttu-id="afbda-152">-参照 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="afbda-152">-reference (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/reference.md)
- [<span data-ttu-id="afbda-153">-noconfig</span><span class="sxs-lookup"><span data-stu-id="afbda-153">-noconfig</span></span>](../../../visual-basic/reference/command-line-compiler/noconfig.md)
- [<span data-ttu-id="afbda-154">-libpath</span><span class="sxs-lookup"><span data-stu-id="afbda-154">-libpath</span></span>](../../../visual-basic/reference/command-line-compiler/libpath.md)
- [<span data-ttu-id="afbda-155">コンパイル コマンド ラインのサンプル</span><span class="sxs-lookup"><span data-stu-id="afbda-155">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="afbda-156">COM 相互運用の概要</span><span class="sxs-lookup"><span data-stu-id="afbda-156">Introduction to COM Interop</span></span>](../../../visual-basic/programming-guide/com-interop/introduction-to-com-interop.md)
