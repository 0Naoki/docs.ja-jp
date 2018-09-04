---
title: '&lt;textMessageEncoding&gt;'
ms.date: 03/30/2017
ms.assetid: e6d834d0-356e-45eb-b530-bbefbb9ec3f0
ms.openlocfilehash: e684c21c0b1360a9b270214ebe7b3ad00b42657f
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "43554501"
---
# <a name="lttextmessageencodinggt"></a><span data-ttu-id="969a5-102">&lt;textMessageEncoding&gt;</span><span class="sxs-lookup"><span data-stu-id="969a5-102">&lt;textMessageEncoding&gt;</span></span>
<span data-ttu-id="969a5-103">テキストベースの XML メッセージに使用される文字エンコーディングおよびメッセージ バージョン管理を指定します。</span><span class="sxs-lookup"><span data-stu-id="969a5-103">Specifies the character encoding and message versioning used for text-based XML messages.</span></span>  
  
 <span data-ttu-id="969a5-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="969a5-104">\<system.serviceModel></span></span>  
<span data-ttu-id="969a5-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="969a5-105">\<bindings></span></span>  
<span data-ttu-id="969a5-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="969a5-106">\<customBinding></span></span>  
<span data-ttu-id="969a5-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="969a5-107">\<binding></span></span>  
<span data-ttu-id="969a5-108">\<textMessageEncoding></span><span class="sxs-lookup"><span data-stu-id="969a5-108">\<textMessageEncoding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="969a5-109">構文</span><span class="sxs-lookup"><span data-stu-id="969a5-109">Syntax</span></span>  
  
```xml  
<textMessageEncoding maxReadPoolSize="Integer"  
   maxWritePoolSize="Integer"  
   messageVersion="Soap11Addressing10/Soap12Addressing10"  
      writeEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="969a5-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="969a5-110">Attributes and Elements</span></span>  
 <span data-ttu-id="969a5-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="969a5-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="969a5-112">属性</span><span class="sxs-lookup"><span data-stu-id="969a5-112">Attributes</span></span>  
  
|<span data-ttu-id="969a5-113">属性</span><span class="sxs-lookup"><span data-stu-id="969a5-113">Attribute</span></span>|<span data-ttu-id="969a5-114">説明</span><span class="sxs-lookup"><span data-stu-id="969a5-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="969a5-115">maxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="969a5-115">maxReadPoolSize</span></span>|<span data-ttu-id="969a5-116">新しいリーダーを割り当てずに同時に読み取り可能なメッセージの数を指定する整数です。</span><span class="sxs-lookup"><span data-stu-id="969a5-116">An integer that specifies how many messages can be read simultaneously without allocating new readers.</span></span> <span data-ttu-id="969a5-117">プール サイズを大きくすると、システムでは、比較的大きい作業セットで、アクティビティの急増に対する許容度が高まります。</span><span class="sxs-lookup"><span data-stu-id="969a5-117">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="969a5-118">既定値は 64 です。</span><span class="sxs-lookup"><span data-stu-id="969a5-118">The default is 64.</span></span>|  
|<span data-ttu-id="969a5-119">maxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="969a5-119">maxWritePoolSize</span></span>|<span data-ttu-id="969a5-120">新しいライターを割り当てずに同時に送信可能なメッセージの数を指定する整数です。</span><span class="sxs-lookup"><span data-stu-id="969a5-120">An integer that specifies how many messages can be sent simultaneously without allocating new writers.</span></span> <span data-ttu-id="969a5-121">プール サイズを大きくすると、システムでは、比較的大きい作業セットで、アクティビティの急増に対する許容度が高まります。</span><span class="sxs-lookup"><span data-stu-id="969a5-121">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="969a5-122">既定値は 16 です。</span><span class="sxs-lookup"><span data-stu-id="969a5-122">The default is 16.</span></span>|  
|<span data-ttu-id="969a5-123">messageVersion</span><span class="sxs-lookup"><span data-stu-id="969a5-123">messageVersion</span></span>|<span data-ttu-id="969a5-124">バインディングを使用して送信されたメッセージの SOAP バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="969a5-124">Specifies the SOAP version of the messages sent using the binding.</span></span> <span data-ttu-id="969a5-125">有効な値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="969a5-125">Valid values are</span></span><br /><br /> <span data-ttu-id="969a5-126">-Soap11Addressing10</span><span class="sxs-lookup"><span data-stu-id="969a5-126">-   Soap11Addressing10</span></span><br /><span data-ttu-id="969a5-127">-Soap12addressing10 です。</span><span class="sxs-lookup"><span data-stu-id="969a5-127">-   Soap12Addressing10</span></span><br /><br /> <span data-ttu-id="969a5-128">既定値は Soap12Addressing10 です。</span><span class="sxs-lookup"><span data-stu-id="969a5-128">The default is Soap12Addressing10.</span></span> <span data-ttu-id="969a5-129">この属性は <xref:System.ServiceModel.Channels.MessageVersion> 型です。</span><span class="sxs-lookup"><span data-stu-id="969a5-129">This attribute is of type <xref:System.ServiceModel.Channels.MessageVersion>.</span></span>|  
|<span data-ttu-id="969a5-130">writeEncoding</span><span class="sxs-lookup"><span data-stu-id="969a5-130">writeEncoding</span></span>|<span data-ttu-id="969a5-131">バインドでメッセージの発行に使用される文字セット エンコーディングを指定します。</span><span class="sxs-lookup"><span data-stu-id="969a5-131">Specifies the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="969a5-132">有効な値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="969a5-132">Valid values are</span></span><br /><br /> <span data-ttu-id="969a5-133">-UnicodeFffeTextEncoding: Unicode BigEndian エンコーディング</span><span class="sxs-lookup"><span data-stu-id="969a5-133">-   UnicodeFffeTextEncoding: Unicode BigEndian encoding</span></span><br /><span data-ttu-id="969a5-134">-Utf16TextEncoding: Unicode エンコーディング</span><span class="sxs-lookup"><span data-stu-id="969a5-134">-   Utf16TextEncoding: Unicode encoding</span></span><br /><span data-ttu-id="969a5-135">-Utf8TextEncoding: 8 ビットのエンコーディング</span><span class="sxs-lookup"><span data-stu-id="969a5-135">-   Utf8TextEncoding: 8-bit encoding</span></span><br /><br /> <span data-ttu-id="969a5-136">既定値は Utf8TextEncoding です。</span><span class="sxs-lookup"><span data-stu-id="969a5-136">The default is Utf8TextEncoding.</span></span> <span data-ttu-id="969a5-137">この属性は <xref:System.Text.Encoding> 型です。</span><span class="sxs-lookup"><span data-stu-id="969a5-137">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="969a5-138">子要素</span><span class="sxs-lookup"><span data-stu-id="969a5-138">Child Elements</span></span>  
  
|<span data-ttu-id="969a5-139">要素</span><span class="sxs-lookup"><span data-stu-id="969a5-139">Element</span></span>|<span data-ttu-id="969a5-140">説明</span><span class="sxs-lookup"><span data-stu-id="969a5-140">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="969a5-141">\<readerQuotas></span><span class="sxs-lookup"><span data-stu-id="969a5-141">\<readerQuotas></span></span>](https://msdn.microsoft.com/library/3e5e42ff-cef8-478f-bf14-034449239bfd)|<span data-ttu-id="969a5-142">このバインドを使用して設定されるエンドポイントにより処理可能な、SOAP メッセージの複雑さに対する制約を定義します。</span><span class="sxs-lookup"><span data-stu-id="969a5-142">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="969a5-143">この要素は <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="969a5-143">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="969a5-144">親要素</span><span class="sxs-lookup"><span data-stu-id="969a5-144">Parent Elements</span></span>  
  
|<span data-ttu-id="969a5-145">要素</span><span class="sxs-lookup"><span data-stu-id="969a5-145">Element</span></span>|<span data-ttu-id="969a5-146">説明</span><span class="sxs-lookup"><span data-stu-id="969a5-146">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="969a5-147">\<binding></span><span class="sxs-lookup"><span data-stu-id="969a5-147">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="969a5-148">カスタム バインドのすべてのバインド機能を定義します。</span><span class="sxs-lookup"><span data-stu-id="969a5-148">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="969a5-149">Remarks</span><span class="sxs-lookup"><span data-stu-id="969a5-149">Remarks</span></span>  
 <span data-ttu-id="969a5-150">エンコーディングは、メッセージをバイト シーケンスに変換するプロセスです。</span><span class="sxs-lookup"><span data-stu-id="969a5-150">Encoding is the process of transforming a message into a sequence of bytes.</span></span> <span data-ttu-id="969a5-151">デコードは、その逆のプロセスです。</span><span class="sxs-lookup"><span data-stu-id="969a5-151">Decoding is the reverse process.</span></span> <span data-ttu-id="969a5-152">WCF (Windows Communication Foundation) には、SOAP メッセージのエンコードとして、テキスト、バイナリ、および MTOM (Message Transmission Optimization Mechanism) の 3 種類があります。</span><span class="sxs-lookup"><span data-stu-id="969a5-152">Windows Communication Foundation (WCF) includes three types of encoding for SOAP messages: Text, Binary and Message Transmission Optimization Mechanism (MTOM).</span></span>  
  
 <span data-ttu-id="969a5-153">`textMessageEncoding` 要素で表されるテキスト エンコーディングでは相互運用性が最も高くなりますが、XML メッセージのエンコーダーとしての効率は最も低くなります。</span><span class="sxs-lookup"><span data-stu-id="969a5-153">The text encoding represented by the `textMessageEncoding` element is the most interoperable, but the least efficient encoder for XML messages.</span></span>  <span data-ttu-id="969a5-154">テキスト エンコーダーは、ネットワーク上でテキストベースのメッセージを作成します。</span><span class="sxs-lookup"><span data-stu-id="969a5-154">The text encoder creates text-based messages on the wire.</span></span> <span data-ttu-id="969a5-155">このエンコーダーにより生成されるメッセージは、WS-\* ベースの相互運用に適しています。</span><span class="sxs-lookup"><span data-stu-id="969a5-155">Messages produced by this encoder are suitable for WS-\* based interop.</span></span> <span data-ttu-id="969a5-156">Web サービスまたは Web サービス クライアントは、一般に、テキスト形式の XML を認識できます。</span><span class="sxs-lookup"><span data-stu-id="969a5-156">Web service or Web service client can generally understand textual XML.</span></span> <span data-ttu-id="969a5-157">しかし、大きいブロックのバイナリ データをテキストとして転送するのは、XML メッセージをエンコードする上では、最も非効率的な方法です。</span><span class="sxs-lookup"><span data-stu-id="969a5-157">However, transmitting large blocks of binary data as text is the least efficient method for encoding XML messages.</span></span>  
  
## <a name="example"></a><span data-ttu-id="969a5-158">例</span><span class="sxs-lookup"><span data-stu-id="969a5-158">Example</span></span>  
  
```xml  
<textMessageEncoding maxReadPoolSize="211"  
    maxWritePoolSize="2132"  
    messageVersion="Soap12Addressing10"  
    textEncoding="utf-8" />  
```  
  
## <a name="see-also"></a><span data-ttu-id="969a5-159">関連項目</span><span class="sxs-lookup"><span data-stu-id="969a5-159">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.TextMessageEncodingElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>  
 <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>  
 [<span data-ttu-id="969a5-160">メッセージ エンコーダーを選択する</span><span class="sxs-lookup"><span data-stu-id="969a5-160">Choosing a Message Encoder</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)  
 [<span data-ttu-id="969a5-161">メッセージ エンコーディング</span><span class="sxs-lookup"><span data-stu-id="969a5-161">Message Encoding</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-encoding.md)  
 [<span data-ttu-id="969a5-162">バインディング</span><span class="sxs-lookup"><span data-stu-id="969a5-162">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="969a5-163">バインディングの拡張</span><span class="sxs-lookup"><span data-stu-id="969a5-163">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="969a5-164">カスタム バインディング</span><span class="sxs-lookup"><span data-stu-id="969a5-164">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="969a5-165">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="969a5-165">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
