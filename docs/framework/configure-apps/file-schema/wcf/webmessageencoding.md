---
title: <webMessageEncoding>
ms.date: 03/30/2017
ms.assetid: 892ca485-e21a-4a44-8e40-633161ef6796
ms.openlocfilehash: e13f23d6894083c8b507bdb73bea897c4845300f
ms.sourcegitcommit: 01ea420eaa4bf76d5fc47673294c8881379b3369
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2019
ms.locfileid: "55759645"
---
# <a name="webmessageencoding"></a><span data-ttu-id="ab759-101">\<webMessageEncoding></span><span class="sxs-lookup"><span data-stu-id="ab759-101">\<webMessageEncoding></span></span>
<span data-ttu-id="ab759-102">Windows Communication Foundation (WCF) での使用時に、プレーンテキストの XML、JavaScript Object Notation (JSON) メッセージ エンコード、および "無変換の" バイナリ コンテンツの読み取りおよび書き込みを有効にします。</span><span class="sxs-lookup"><span data-stu-id="ab759-102">Enables plain-text XML, JavaScript Object Notation (JSON) message encodings and "raw" binary content to be read and written when used in a Windows Communication Foundation (WCF) binding.</span></span>  
  
 <span data-ttu-id="ab759-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="ab759-103">\<system.serviceModel></span></span>  
<span data-ttu-id="ab759-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="ab759-104">\<bindings></span></span>  
<span data-ttu-id="ab759-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="ab759-105">\<customBinding></span></span>  
<span data-ttu-id="ab759-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="ab759-106">\<binding></span></span>  
<span data-ttu-id="ab759-107">\<webMessageEncoding></span><span class="sxs-lookup"><span data-stu-id="ab759-107">\<webMessageEncoding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab759-108">構文</span><span class="sxs-lookup"><span data-stu-id="ab759-108">Syntax</span></span>  
  
```xml  
<webMessageEncoding maxReadPoolSize="Integer"
                    maxWritePoolSize="Integer"
                    writeEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ab759-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="ab759-109">Attributes and Elements</span></span>  
 <span data-ttu-id="ab759-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="ab759-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ab759-111">属性</span><span class="sxs-lookup"><span data-stu-id="ab759-111">Attributes</span></span>  
  
|<span data-ttu-id="ab759-112">属性</span><span class="sxs-lookup"><span data-stu-id="ab759-112">Attribute</span></span>|<span data-ttu-id="ab759-113">説明</span><span class="sxs-lookup"><span data-stu-id="ab759-113">Description</span></span>|  
|---------------|-----------------|  
|`maxReadPoolSize`|<span data-ttu-id="ab759-114">新しいリーダーを割り当てずに同時に読み取ることができるメッセージの数。</span><span class="sxs-lookup"><span data-stu-id="ab759-114">The amount of messages that can be read simultaneously without allocating new readers.</span></span> <span data-ttu-id="ab759-115">プール サイズを大きくすると、システムでは、比較的大きい作業セットで、アクティビティの急増に対する許容度が高まります。</span><span class="sxs-lookup"><span data-stu-id="ab759-115">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="ab759-116">既定値は、内部エンコーダー (Text、JSON、および raw (生)) ごとに 64 リーダーです。</span><span class="sxs-lookup"><span data-stu-id="ab759-116">The default is 64 readers for each of the inner encoders (text, JSON, and "raw").</span></span><br /><br /> <span data-ttu-id="ab759-117">この数を増やすとメモリの消費量が増えますが、受信メッセージ数の急激な増加にエンコーダーが対処できるようになります。これは、作成済みのリーダーをプールから使用でき、新しいリーダーを作成する必要がないためです。</span><span class="sxs-lookup"><span data-stu-id="ab759-117">Increasing this number increases memory consumption, but prepares the encoder to deal with sudden bursts of incoming messages because it is able to use readers from the pool that are already created instead of creating new ones.</span></span>|  
|`maxWritePoolSize`|<span data-ttu-id="ab759-118">新しいライターを割り当てずに同時に送信できるメッセージの数。</span><span class="sxs-lookup"><span data-stu-id="ab759-118">The amount of messages that can be sent simultaneously without allocating new writers.</span></span> <span data-ttu-id="ab759-119">プール サイズを大きくすると、システムでは、比較的大きい作業セットで、アクティビティの急増に対する許容度が高まります。</span><span class="sxs-lookup"><span data-stu-id="ab759-119">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="ab759-120">既定値は、内部エンコーダー (Text、JSON、および raw (生)) ごとに 64 リーダーです。</span><span class="sxs-lookup"><span data-stu-id="ab759-120">The default is 16 writers for each of the inner encoders (text, JSON, and "raw").</span></span><br /><br /> <span data-ttu-id="ab759-121">この数を増やすとメモリの消費が増えますが、送信メッセージ数の急激な増加にエンコーダーが対処できるようになります。これは、作成済みのライターをプールから使用でき、新しいライターを作成する必要がないためです。</span><span class="sxs-lookup"><span data-stu-id="ab759-121">Increasing this number increases memory consumption, but prepares the encoder to deal with sudden bursts of outgoing messages because it is able to use writers from the pool that are already created instead of creating new ones.</span></span>|  
|`writeEncoding`|<span data-ttu-id="ab759-122">バインドでメッセージの発行に使用される文字セット エンコーディングを指定します。</span><span class="sxs-lookup"><span data-stu-id="ab759-122">Specifies the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="ab759-123">次の値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="ab759-123">Valid values are:</span></span><br /><br /> <span data-ttu-id="ab759-124">-   UnicodeFffeTextEncoding:Unicode ビッグ エンディアン エンコーディング。</span><span class="sxs-lookup"><span data-stu-id="ab759-124">-   UnicodeFffeTextEncoding: Unicode Big Endian encoding.</span></span><br /><span data-ttu-id="ab759-125">-   Utf16TextEncoding:Unicode エンコーディング。</span><span class="sxs-lookup"><span data-stu-id="ab759-125">-   Utf16TextEncoding: Unicode encoding.</span></span><br /><span data-ttu-id="ab759-126">-   Utf8TextEncoding:8 ビット エンコーディング。</span><span class="sxs-lookup"><span data-stu-id="ab759-126">-   Utf8TextEncoding: 8-bit encoding.</span></span><br /><br /> <span data-ttu-id="ab759-127">既定値は Utf8TextEncoding です。</span><span class="sxs-lookup"><span data-stu-id="ab759-127">The default is Utf8TextEncoding.</span></span> <span data-ttu-id="ab759-128">この属性は <xref:System.Text.Encoding> 型です。</span><span class="sxs-lookup"><span data-stu-id="ab759-128">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ab759-129">子要素</span><span class="sxs-lookup"><span data-stu-id="ab759-129">Child Elements</span></span>  
  
|<span data-ttu-id="ab759-130">要素</span><span class="sxs-lookup"><span data-stu-id="ab759-130">Element</span></span>|<span data-ttu-id="ab759-131">説明</span><span class="sxs-lookup"><span data-stu-id="ab759-131">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ab759-132">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="ab759-132">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span></span>|<span data-ttu-id="ab759-133">このバインドを使用して設定されるエンドポイントにより処理可能な、SOAP メッセージの複雑さに対する制約を定義します。</span><span class="sxs-lookup"><span data-stu-id="ab759-133">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="ab759-134">この要素は <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="ab759-134">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ab759-135">親要素</span><span class="sxs-lookup"><span data-stu-id="ab759-135">Parent Elements</span></span>  
  
|<span data-ttu-id="ab759-136">要素</span><span class="sxs-lookup"><span data-stu-id="ab759-136">Element</span></span>|<span data-ttu-id="ab759-137">説明</span><span class="sxs-lookup"><span data-stu-id="ab759-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ab759-138">\<binding></span><span class="sxs-lookup"><span data-stu-id="ab759-138">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="ab759-139">カスタム バインドのすべてのバインド機能を定義します。</span><span class="sxs-lookup"><span data-stu-id="ab759-139">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ab759-140">Remarks</span><span class="sxs-lookup"><span data-stu-id="ab759-140">Remarks</span></span>  
 <span data-ttu-id="ab759-141">エンコーディングは、メッセージをバイト シーケンスに変換するプロセスです。</span><span class="sxs-lookup"><span data-stu-id="ab759-141">Encoding is the process of transforming a message into a sequence of bytes.</span></span> <span data-ttu-id="ab759-142">デコードは、その逆のプロセスです。</span><span class="sxs-lookup"><span data-stu-id="ab759-142">Decoding is the reverse process.</span></span> <span data-ttu-id="ab759-143">これらのプロセスでは、文字エンコーディングの指定が必要です。</span><span class="sxs-lookup"><span data-stu-id="ab759-143">These processes require the specification of a character encoding.</span></span>  
  
 <span data-ttu-id="ab759-144">`webMessageEncoding` 要素は、プレーンテキストの XML と JSON エンコーディング、および "生" のバイナリ データの処理を、一連の内部エンコーダーに代行させることで機能します。</span><span class="sxs-lookup"><span data-stu-id="ab759-144">The `webMessageEncoding` element works by delegating to a series of inner encoders to handle the plain-text XML and JSON encodings, and "raw" binary data.</span></span> <span data-ttu-id="ab759-145">この委任は、複合メッセージ エンコーダーによって実行されます。</span><span class="sxs-lookup"><span data-stu-id="ab759-145">This delegation is done by a composite message encoder.</span></span>  
  
 <span data-ttu-id="ab759-146">このバインディング要素と複合エンコーダーは、`webHttpBinding` 要素によって使用される SOAP メッセージを使用しないシナリオでのエンコーディングを制御するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="ab759-146">This binding element and its composite encoder are used to control the encoding in scenarios that do not use SOAP messaging used by the `webHttpBinding` element.</span></span> <span data-ttu-id="ab759-147">これらのシナリオには、POX ("Plain Old XML")、REST (Representational State Transfer)、RSS (Really Simple Syndication) と Atom 配信、および AJAX (Asynchronous JavaScript and XML) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="ab759-147">These scenarios include "Plain Old XML" (POX), Representational State Transfer (REST), Really Simple Syndication (RSS) and Atom syndication, and Asynchronous JavaScript and XML (AJAX).</span></span> <span data-ttu-id="ab759-148">複合メッセージ エンコーダーは SOAP または WS-Addressing をサポートしません。</span><span class="sxs-lookup"><span data-stu-id="ab759-148">The composite message encoder does not support SOAP or WS-Addressing.</span></span>  
  
 <span data-ttu-id="ab759-149">`writeEncoding` 属性を使用すると、バインディング要素に書き込みの文字エンコーディングを構成できます。</span><span class="sxs-lookup"><span data-stu-id="ab759-149">The binding element can be configured with a write character encoding by using the `writeEncoding` attribute.</span></span> <span data-ttu-id="ab759-150">指定された <xref:System.Text.Encoding> 値は、JSON およびテキスト形式の XML の場合の書き込みの動作を指定します。</span><span class="sxs-lookup"><span data-stu-id="ab759-150">The supplied <xref:System.Text.Encoding> value specifies the behavior on write for the JSON and Textual XML cases.</span></span> <span data-ttu-id="ab759-151">読み取りについては、任意の有効なメッセージ エンコーディングとテキスト エンコーディングが認識されます。</span><span class="sxs-lookup"><span data-stu-id="ab759-151">On read, any valid message encoding and text encoding is understood.</span></span>  
  
 <span data-ttu-id="ab759-152">`maxReadPoolSize` と `maxWritePoolSize` を使用して、割り当てられるリーダーとライターの最大数をそれぞれ設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="ab759-152">`maxReadPoolSize` and `maxWritePoolSize` can also be used to set the maximum number of readers and writers to be allocated respectively.</span></span> <span data-ttu-id="ab759-153">既定では、64 のリーダーと 16 のライターが割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="ab759-153">By default 64 readers and 16 writers are allocated.</span></span>  
  
 <span data-ttu-id="ab759-154">既定の複雑さの制約を使用してを設定しても、 [ \<readerQuotas >](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))サービス拒否 (DOS) のクラスから保護するための要素がメッセージの複雑さを使用してエンドポイント処理を停滞させるを試行するを攻撃リソース。</span><span class="sxs-lookup"><span data-stu-id="ab759-154">Default complexity constraints are also set using the [\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100)) element to protect against a class of denial of service (DOS) attacks that attempt to use message complexity to tie up endpoint processing resources.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ab759-155">例</span><span class="sxs-lookup"><span data-stu-id="ab759-155">Example</span></span>  
  
```xml  
<webMessageEncoding maxReadPoolSize="256"
                    maxWritePoolSize="128"
                    messageVersion="None"
                    textEncoding="utf-8" />
```  
  
## <a name="see-also"></a><span data-ttu-id="ab759-156">関連項目</span><span class="sxs-lookup"><span data-stu-id="ab759-156">See also</span></span>
- <xref:System.ServiceModel.Configuration.WebMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.WebMessageEncodingBindingElement>
- [<span data-ttu-id="ab759-157">メッセージ エンコーディング</span><span class="sxs-lookup"><span data-stu-id="ab759-157">Message Encoding</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-encoding.md)
- [<span data-ttu-id="ab759-158">メッセージ エンコーダーを選択する</span><span class="sxs-lookup"><span data-stu-id="ab759-158">Choosing a Message Encoder</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)
- [<span data-ttu-id="ab759-159">バインディング</span><span class="sxs-lookup"><span data-stu-id="ab759-159">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="ab759-160">バインディングの拡張</span><span class="sxs-lookup"><span data-stu-id="ab759-160">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="ab759-161">カスタム バインディング</span><span class="sxs-lookup"><span data-stu-id="ab759-161">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="ab759-162">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="ab759-162">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
