---
title: <netHttpsBinding>
ms.date: 03/30/2017
ms.assetid: ff122116-6042-4792-9f21-275b4f97a105
ms.openlocfilehash: 82d1d68a8d6c4954b47509db2adaf88f88ae625d
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/30/2019
ms.locfileid: "55275783"
---
# <a name="nethttpsbinding"></a><span data-ttu-id="b7d9b-101">\<netHttpsBinding ></span><span class="sxs-lookup"><span data-stu-id="b7d9b-101">\<netHttpsBinding></span></span>
<span data-ttu-id="b7d9b-102">Windows Communication Foundation (WCF) サービスが構成および HTTPS 経由で通信できるエンドポイントを公開に使用できるバインディングを表します。</span><span class="sxs-lookup"><span data-stu-id="b7d9b-102">Represents a binding that a Windows Communication Foundation (WCF) service can use to configure and expose endpoints that are able to communicate over HTTPS.</span></span> <span data-ttu-id="b7d9b-103">双方向コントラクトで使用すると、Web ソケットが使用されます。それ以外の場合は、HTTPS が使用されます。</span><span class="sxs-lookup"><span data-stu-id="b7d9b-103">When used with a duplex contract, Web Sockets will be used, otherwise HTTPS will be used.</span></span>  
  
 <span data-ttu-id="b7d9b-104">ルート要素</span><span class="sxs-lookup"><span data-stu-id="b7d9b-104">Root Element</span></span>  
<span data-ttu-id="b7d9b-105">次の要素</span><span class="sxs-lookup"><span data-stu-id="b7d9b-105">Next Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7d9b-106">構文</span><span class="sxs-lookup"><span data-stu-id="b7d9b-106">Syntax</span></span>  
  
```xml  
<netHttpsBinding>
  <binding allowCookies="Boolean"
           bypassProxyOnLocal="Boolean"
           closeTimeout="TimeSpan"
           hostNameComparisonMode="StrongWildCard/Exact/WeakWildcard"
           maxBufferPoolSize="Integer"
           maxBufferSize="Integer"
           maxReceivedMessageSize="Integer"
           messageEncoding="Binary/Text/Mtom"
           name="string"
           openTimeout="TimeSpan"
           proxyAddress="URI"
           receiveTimeout="TimeSpan"
           sendTimeout="TimeSpan"
           textEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding"
           transferMode="Buffered/Streamed/StreamedRequest/StreamedResponse"
           useDefaultWebProxy="Boolean">
    <security mode="None/Transport/Message/TransportWithMessageCredential/TransportCredentialOnly">
      <transport clientCredentialType="None/Basic/Digest/Ntlm/Windows/Certificate"
                 proxyCredentialType="None/Basic/Digest/Ntlm/Windows"
                 realm="string" />
      <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
               clientCredentialType="UserName/Certificate" />
    </security>
    <readerQuotas maxArrayLength="Integer"
                  maxBytesPerRead="Integer"
                  maxDepth="Integer"
                  maxNameTableCharCount="Integer"
                  maxStringContentLength="Integer" />
  </binding>
</netHttpsBinding>
```  
  
## <a name="type"></a><span data-ttu-id="b7d9b-107">型</span><span class="sxs-lookup"><span data-stu-id="b7d9b-107">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b7d9b-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="b7d9b-108">Attributes and Elements</span></span>  
 <span data-ttu-id="b7d9b-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="b7d9b-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b7d9b-110">属性</span><span class="sxs-lookup"><span data-stu-id="b7d9b-110">Attributes</span></span>  
  
|<span data-ttu-id="b7d9b-111">属性</span><span class="sxs-lookup"><span data-stu-id="b7d9b-111">Attribute</span></span>|<span data-ttu-id="b7d9b-112">説明</span><span class="sxs-lookup"><span data-stu-id="b7d9b-112">Description</span></span>|  
|---------------|-----------------|  
|`allowCookies`|<span data-ttu-id="b7d9b-113">クライアントがクッキーを受け入れて、それらを今後の要求に反映させるかどうかを指定するブール値です。</span><span class="sxs-lookup"><span data-stu-id="b7d9b-113">A Boolean value that indicates whether the client accepts cookies and propagates them on future requests.</span></span> <span data-ttu-id="b7d9b-114">既定値は、`false` です。</span><span class="sxs-lookup"><span data-stu-id="b7d9b-114">The default is `false`.</span></span><br /><br /> <span data-ttu-id="b7d9b-115">クッキーを使用する ASMX Web サービスと対話する場合にこのプロパティを使用できます。</span><span class="sxs-lookup"><span data-stu-id="b7d9b-115">You can use this property when you interact with ASMX Web services that use cookies.</span></span> <span data-ttu-id="b7d9b-116">この方法で、サーバーから返されるクッキーを、それ以降のサービスに対するすべてのクライアント要求に自動的にコピーできます。</span><span class="sxs-lookup"><span data-stu-id="b7d9b-116">In this way, you can be sure that the cookies returned from the server are automatically copied to all future client requests for that service.</span></span>|  
|`bypassProxyOnLocal`|<span data-ttu-id="b7d9b-117">ローカル アドレスでプロキシ サーバーをバイパスするかどうかを示すブール値。</span><span class="sxs-lookup"><span data-stu-id="b7d9b-117">A Boolean value that indicates whether to bypass the proxy server for local addresses.</span></span> <span data-ttu-id="b7d9b-118">既定値は、`false` です。</span><span class="sxs-lookup"><span data-stu-id="b7d9b-118">The default is `false`.</span></span><br /><br /> <span data-ttu-id="b7d9b-119">インターネット リソースは、ローカル アドレスを持つ場合ローカルです。</span><span class="sxs-lookup"><span data-stu-id="b7d9b-119">An Internet resource is local if it has a local address.</span></span> <span data-ttu-id="b7d9b-120">によって識別される、構文的に、Uri と同様にピリオド (.) の欠如が同じコンピューター、ローカル LAN またはイントラネット上にあり、ローカル アドレスは "http://webserver/" と "http://localhost/" です。</span><span class="sxs-lookup"><span data-stu-id="b7d9b-120">A local address is one that is on same computer, the local LAN or intranet and is identified, syntactically, by the lack of a period (.) as in the URIs "http://webserver/" and "http://localhost/".</span></span><br /><br /> <span data-ttu-id="b7d9b-121">この属性の設定は、BasicHttpBinding で構成されたエンドポイントがローカル リソースへのアクセス時にプロキシ サーバーを使用するかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="b7d9b-121">Setting this attribute determines whether endpoints configured with the BasicHttpBinding use the proxy server when accessing local resources.</span></span> <span data-ttu-id="b7d9b-122">この属性が `true` の場合、ローカル インターネット リソースへの要求はプロキシ サーバーを使用しません。</span><span class="sxs-lookup"><span data-stu-id="b7d9b-122">If this attribute is `true`, requests to local Internet resources do not use the proxy server.</span></span> <span data-ttu-id="b7d9b-123">この属性を `true` に設定した場合で、同じコンピューター上のサービスと対話するクライアントがプロキシを経由するときは、(localhost ではなく) ホスト名を使用します。</span><span class="sxs-lookup"><span data-stu-id="b7d9b-123">Use the host name (rather than localhost) if you want clients to go through a proxy when talking to services on the same machine when this attribute is set to `true`.</span></span><br /><br /> <span data-ttu-id="b7d9b-124">この属性が `false` の場合、すべてのインターネット要求はプロキシ サーバー経由で行われます。</span><span class="sxs-lookup"><span data-stu-id="b7d9b-124">When this attribute is `false`, all Internet requests are made through the proxy server.</span></span>|  
|`closeTimeout`|<span data-ttu-id="b7d9b-125">クローズ操作が完了するまでの期間を指定する <xref:System.TimeSpan> 値。</span><span class="sxs-lookup"><span data-stu-id="b7d9b-125">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="b7d9b-126">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="b7d9b-126">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="b7d9b-127">既定値は 00:01:00 です。</span><span class="sxs-lookup"><span data-stu-id="b7d9b-127">The default is 00:01:00.</span></span>|  
|`hostnameComparisonMode`|<span data-ttu-id="b7d9b-128">URI の解析に使用する HTTP ホスト名比較モードを指定します。</span><span class="sxs-lookup"><span data-stu-id="b7d9b-128">Specifies the HTTP hostname comparison mode used to parse URIs.</span></span> <span data-ttu-id="b7d9b-129">この属性は `HostnameComparisonMode` 型で、URI が一致したときにサービスへのアクセスにホスト名を使用するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="b7d9b-129">This attribute is of type `HostnameComparisonMode`, which indicates whether the hostname is used to reach the service when matching on the URI.</span></span> <span data-ttu-id="b7d9b-130">既定値は `StrongWildcard` で、一致しているホスト名を無視します。</span><span class="sxs-lookup"><span data-stu-id="b7d9b-130">The default value is `StrongWildcard`, which ignores the hostname in the match.</span></span>|  
|`maxBufferPoolSize`|<span data-ttu-id="b7d9b-131">チャネルからメッセージを受け取るメッセージ バッファーのマネージャーが使用するために割り当てられる、最大メモリ量を指定する整数値。</span><span class="sxs-lookup"><span data-stu-id="b7d9b-131">An integer value that specifies the maximum amount of memory that is allocated for use by the manager of the message buffers that receive messages from the channel.</span></span> <span data-ttu-id="b7d9b-132">既定値は 524288 (0x80000) バイトです。</span><span class="sxs-lookup"><span data-stu-id="b7d9b-132">The default value is 524288 (0x80000) bytes.</span></span><br /><br /> <span data-ttu-id="b7d9b-133">バッファー マネージャーは、バッファー プールを使用することで、バッファーの使用コストを最小化します。</span><span class="sxs-lookup"><span data-stu-id="b7d9b-133">The Buffer Manager minimizes the cost of using buffers by using a buffer pool.</span></span> <span data-ttu-id="b7d9b-134">バッファーは、チャネルから出てくるメッセージをサービスが処理するときに必要です。</span><span class="sxs-lookup"><span data-stu-id="b7d9b-134">Buffers are required to process messages by the service when they come out of the channel.</span></span> <span data-ttu-id="b7d9b-135">メッセージの読み込み処理に十分なメモリがバッファー プールにない場合、バッファー マネージャーは、CLR ヒープから追加のメモリを割り当てる必要があります。これにより、ガベージ コレクションのオーバーヘッドが増加します。</span><span class="sxs-lookup"><span data-stu-id="b7d9b-135">If there is not sufficient memory in the buffer pool to process the message load, the Buffer Manager must allocate additional memory from the CLR heap, which increases the garbage collection overhead.</span></span> <span data-ttu-id="b7d9b-136">CLR ガベージ ヒープから多大な割り当てが行われることは、バッファー プール サイズが小さすぎること、およびこの属性で指定される制限を緩めて割り当てを増やすとパフォーマンスが向上する可能性があることを示します。</span><span class="sxs-lookup"><span data-stu-id="b7d9b-136">Extensive allocation from the CLR garbage heap is an indication that the buffer pool size is too small and that performance can be improved with a larger allocation by increasing the limit specified by this attribute.</span></span>|  
|`maxBufferSize`|<span data-ttu-id="b7d9b-137">このバインディングで構成されるエンドポイントのメッセージが処理されるときのメッセージを格納するバッファーの最大サイズを指定する整数値 (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="b7d9b-137">An integer value that specifies the maximum size, in bytes, of a buffer that stores messages while they are processed for an endpoint configured with this binding.</span></span> <span data-ttu-id="b7d9b-138">既定値は 65,536 バイトです。</span><span class="sxs-lookup"><span data-stu-id="b7d9b-138">The default value is 65,536 bytes.</span></span>|  
|`maxReceivedMessageSize`|<span data-ttu-id="b7d9b-139">このバインディングで構成されるチャネルが受信可能なメッセージの最大メッセージ サイズ (ヘッダーを含む) をバイト単位で定義する正の整数。</span><span class="sxs-lookup"><span data-stu-id="b7d9b-139">A positive integer that defines the maximum message size, in bytes, including headers, for a message that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="b7d9b-140">受信側のメッセージが大きすぎると、送信側は SOAP エラーを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="b7d9b-140">The sender receives a SOAP fault if the message is too large for the receiver.</span></span> <span data-ttu-id="b7d9b-141">メッセージは受信者によって破棄され、トレース ログにこのイベントのエントリが作成されます。</span><span class="sxs-lookup"><span data-stu-id="b7d9b-141">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="b7d9b-142">既定値は 65,536 バイトです。</span><span class="sxs-lookup"><span data-stu-id="b7d9b-142">The default is 65,536 bytes.</span></span>|  
|`messageEncoding`|<span data-ttu-id="b7d9b-143">SOAP メッセージのエンコードに使用されるエンコーダーを定義します。</span><span class="sxs-lookup"><span data-stu-id="b7d9b-143">Defines the encoder used to encode the SOAP message.</span></span> <span data-ttu-id="b7d9b-144">以下の値が有効です。</span><span class="sxs-lookup"><span data-stu-id="b7d9b-144">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="b7d9b-145">テキスト:テキスト メッセージ エンコーダーを使用します。</span><span class="sxs-lookup"><span data-stu-id="b7d9b-145">-   Text: Use a text message encoder.</span></span><br /><span data-ttu-id="b7d9b-146">Mtom:Message Transmission 組織 Mechanism 1.0 (MTOM) エンコーダーを使用します。</span><span class="sxs-lookup"><span data-stu-id="b7d9b-146">-   Mtom: Use a Message Transmission Organization Mechanism 1.0 (MTOM) encoder.</span></span><br /><br /> <span data-ttu-id="b7d9b-147">既定値は Text です。</span><span class="sxs-lookup"><span data-stu-id="b7d9b-147">The default is Text.</span></span> <span data-ttu-id="b7d9b-148">この属性は <xref:System.ServiceModel.WSMessageEncoding> 型です。</span><span class="sxs-lookup"><span data-stu-id="b7d9b-148">This attribute is of type <xref:System.ServiceModel.WSMessageEncoding>.</span></span>|  
|`name`|<span data-ttu-id="b7d9b-149">バインディングの構成名を格納する文字列です。</span><span class="sxs-lookup"><span data-stu-id="b7d9b-149">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="b7d9b-150">この値は、バインディングの ID として使用されるため、一意にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b7d9b-150">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="b7d9b-151">各バインドには、サービスのメタデータでこれをまとめて一意に識別する `name` および `namespace` 属性が含まれています。</span><span class="sxs-lookup"><span data-stu-id="b7d9b-151">Each binding has a `name` and `namespace` attribute that together uniquely identify it in the metadata of the service.</span></span> <span data-ttu-id="b7d9b-152">また、この名前は、同じ種類のバインディング間で一意です。</span><span class="sxs-lookup"><span data-stu-id="b7d9b-152">In addition, this name is unique among bindings of the same type.</span></span> <span data-ttu-id="b7d9b-153">[!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] 以降では、バインディングおよび動作に名前を付ける必要はありません。</span><span class="sxs-lookup"><span data-stu-id="b7d9b-153">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="b7d9b-154">既定の構成と無名のバインディングおよび動作の詳細については、「[簡略化された構成](../../../../../docs/framework/wcf/simplified-configuration.md)」と「[WCF サービスの構成を簡略化](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b7d9b-154">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`namespace`|<span data-ttu-id="b7d9b-155">バインディングの XML 名前空間を指定します。</span><span class="sxs-lookup"><span data-stu-id="b7d9b-155">Specifies the XML namespace of the binding.</span></span> <span data-ttu-id="b7d9b-156">既定値は "http://tempuri.org/Bindings" です。</span><span class="sxs-lookup"><span data-stu-id="b7d9b-156">The default value is "http://tempuri.org/Bindings".</span></span> <span data-ttu-id="b7d9b-157">各バインドには、サービスのメタデータでこれをまとめて一意に識別する `name` および `namespace` 属性が含まれています。</span><span class="sxs-lookup"><span data-stu-id="b7d9b-157">Each binding has a `name` and `namespace` attribute that together uniquely identify it in the metadata of the service.</span></span>|  
|`openTimeout`|<span data-ttu-id="b7d9b-158">実行中の操作が完了するまでの時間間隔を指定する <xref:System.TimeSpan> 値です。</span><span class="sxs-lookup"><span data-stu-id="b7d9b-158">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="b7d9b-159">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="b7d9b-159">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="b7d9b-160">既定値は 00:01:00 です。</span><span class="sxs-lookup"><span data-stu-id="b7d9b-160">The default is 00:01:00.</span></span>|  
|`proxyAddress`|<span data-ttu-id="b7d9b-161">HTTP プロキシのアドレスを格納する URI。</span><span class="sxs-lookup"><span data-stu-id="b7d9b-161">A URI that contains the address of the HTTP proxy.</span></span> <span data-ttu-id="b7d9b-162">`useSystemWebProxy` が `true` に設定されている場合、この設定は `null` である必要があります。</span><span class="sxs-lookup"><span data-stu-id="b7d9b-162">If `useSystemWebProxy` is set to `true`, this setting must be `null`.</span></span> <span data-ttu-id="b7d9b-163">既定値は、`null` です。</span><span class="sxs-lookup"><span data-stu-id="b7d9b-163">The default is `null`.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="b7d9b-164">受信操作が完了するまでの時間間隔を指定する <xref:System.TimeSpan> 値です。</span><span class="sxs-lookup"><span data-stu-id="b7d9b-164">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="b7d9b-165">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="b7d9b-165">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="b7d9b-166">既定値は 00:10:00 です。</span><span class="sxs-lookup"><span data-stu-id="b7d9b-166">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="b7d9b-167">送信操作が完了するまでの時間間隔を指定する <xref:System.TimeSpan> 値です。</span><span class="sxs-lookup"><span data-stu-id="b7d9b-167">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="b7d9b-168">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="b7d9b-168">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="b7d9b-169">既定値は 00:01:00 です。</span><span class="sxs-lookup"><span data-stu-id="b7d9b-169">The default is 00:01:00.</span></span>|  
|`textEncoding`|<span data-ttu-id="b7d9b-170">バインディングでメッセージの発行に使用される文字セット エンコーディングを設定します。</span><span class="sxs-lookup"><span data-stu-id="b7d9b-170">Sets the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="b7d9b-171">以下の値が有効です。</span><span class="sxs-lookup"><span data-stu-id="b7d9b-171">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="b7d9b-172">-BigEndianUnicode:Unicode BigEndian エンコーディングします。</span><span class="sxs-lookup"><span data-stu-id="b7d9b-172">-   BigEndianUnicode: Unicode BigEndian encoding.</span></span><br /><span data-ttu-id="b7d9b-173">Unicode:16 ビット エンコーディング。</span><span class="sxs-lookup"><span data-stu-id="b7d9b-173">-   Unicode: 16-bit encoding.</span></span><br /><span data-ttu-id="b7d9b-174">UTF8:8 ビット エンコード</span><span class="sxs-lookup"><span data-stu-id="b7d9b-174">-   UTF8: 8-bit encoding</span></span><br /><br /> <span data-ttu-id="b7d9b-175">既定値は UTF8 です。</span><span class="sxs-lookup"><span data-stu-id="b7d9b-175">The default is UTF8.</span></span> <span data-ttu-id="b7d9b-176">この属性は <xref:System.Text.Encoding> 型です。</span><span class="sxs-lookup"><span data-stu-id="b7d9b-176">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
|`transferMode`|<span data-ttu-id="b7d9b-177">要求または応答に対してメッセージがバッファーされるか、ストリーム配信されるかを指定する有効な <xref:System.ServiceModel.TransferMode> 値。</span><span class="sxs-lookup"><span data-stu-id="b7d9b-177">A valid <xref:System.ServiceModel.TransferMode> value that specifies whether messages are buffered or streamed on a request or response.</span></span>|  
|`useDefaultWebProxy`|<span data-ttu-id="b7d9b-178">使用できる場合にシステムの自動設定 HTTP プロキシを使用するかどうかを指定するブール値。</span><span class="sxs-lookup"><span data-stu-id="b7d9b-178">A Boolean value that specifies whether the auto-configured HTTP proxy of the system should be used, if available.</span></span> <span data-ttu-id="b7d9b-179">既定値は `true` です。</span><span class="sxs-lookup"><span data-stu-id="b7d9b-179">The default is `true`.</span></span>|  
|||  
  
### <a name="child-elements"></a><span data-ttu-id="b7d9b-180">子要素</span><span class="sxs-lookup"><span data-stu-id="b7d9b-180">Child Elements</span></span>  
  
|<span data-ttu-id="b7d9b-181">要素</span><span class="sxs-lookup"><span data-stu-id="b7d9b-181">Element</span></span>|<span data-ttu-id="b7d9b-182">説明</span><span class="sxs-lookup"><span data-stu-id="b7d9b-182">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b7d9b-183">\<security></span><span class="sxs-lookup"><span data-stu-id="b7d9b-183">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-nethttpbinding.md)|<span data-ttu-id="b7d9b-184">バインディングのセキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="b7d9b-184">Defines the security settings for the binding.</span></span> <span data-ttu-id="b7d9b-185">この要素は <xref:System.ServiceModel.Configuration.BasicHttpsSecurityElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="b7d9b-185">This element is of type <xref:System.ServiceModel.Configuration.BasicHttpsSecurityElement>.</span></span> |  
|[<span data-ttu-id="b7d9b-186">\<readerQuotas></span><span class="sxs-lookup"><span data-stu-id="b7d9b-186">\<readerQuotas></span></span>](https://msdn.microsoft.com/library/3e5e42ff-cef8-478f-bf14-034449239bfd)|<span data-ttu-id="b7d9b-187">このバインドを使用して設定されるエンドポイントにより処理可能な、SOAP メッセージの複雑さに対する制約を定義します。</span><span class="sxs-lookup"><span data-stu-id="b7d9b-187">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="b7d9b-188">この要素は <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="b7d9b-188">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b7d9b-189">親要素</span><span class="sxs-lookup"><span data-stu-id="b7d9b-189">Parent Elements</span></span>  
  
|<span data-ttu-id="b7d9b-190">要素</span><span class="sxs-lookup"><span data-stu-id="b7d9b-190">Element</span></span>|<span data-ttu-id="b7d9b-191">説明</span><span class="sxs-lookup"><span data-stu-id="b7d9b-191">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b7d9b-192">\<bindings></span><span class="sxs-lookup"><span data-stu-id="b7d9b-192">\<bindings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|<span data-ttu-id="b7d9b-193">この要素には、標準バインディングおよびカスタム バインドのコレクションが保持されます。</span><span class="sxs-lookup"><span data-stu-id="b7d9b-193">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b7d9b-194">Remarks</span><span class="sxs-lookup"><span data-stu-id="b7d9b-194">Remarks</span></span>  
 <span data-ttu-id="b7d9b-195">NetHttpsBinding では、メッセージを送信するために、HTTPS をトランスポートとして使用します。</span><span class="sxs-lookup"><span data-stu-id="b7d9b-195">The NetHttpsBinding uses HTTPS as the transport for sending messages.</span></span> <span data-ttu-id="b7d9b-196">双方向コントラクトで使用すると、Web ソケットが使用されます。</span><span class="sxs-lookup"><span data-stu-id="b7d9b-196">When used with a duplex contract, Web Sockets will be used.</span></span>  <span data-ttu-id="b7d9b-197">要求/応答コントラクト NetHttpsBinding と使用する場合、バイナリ エンコーダーとの BasicHttpsBinding のように動作します。</span><span class="sxs-lookup"><span data-stu-id="b7d9b-197">When used with a request-reply contract NetHttpsBinding will behave like a BasicHttpsBinding with a binary encoder.</span></span>  
  
 <span data-ttu-id="b7d9b-198">セキュリティが既定でオフにしの mode 属性を設定する追加することが、 [\<セキュリティ >](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-basichttpbinding.md)以外の値を子要素`None`します。</span><span class="sxs-lookup"><span data-stu-id="b7d9b-198">Security is turned off by default, but can be added setting the mode attribute of the [\<security>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-basichttpbinding.md) child element to a value other than `None`.</span></span> <span data-ttu-id="b7d9b-199">サービスは、"Text" メッセージ エンコードおよび UTF-8 テキスト エンコードを既定で使用します。</span><span class="sxs-lookup"><span data-stu-id="b7d9b-199">It uses a "Text" message encoding and UTF-8 text encoding by default.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b7d9b-200">例</span><span class="sxs-lookup"><span data-stu-id="b7d9b-200">Example</span></span>  
 <span data-ttu-id="b7d9b-201">第 1 世代と第 2 世代の Web サービスで HTTPS 通信と最大限の相互運用性を実現する、<xref:System.ServiceModel.NetHttpBinding> の使用例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="b7d9b-201">The following example demonstrates the use of <xref:System.ServiceModel.NetHttpBinding> that provides HTTPS communication and maximum interoperability with first- and second-generation Web services.</span></span> <span data-ttu-id="b7d9b-202">バインディングは、クライアントとサービスの構成ファイルに指定されます。</span><span class="sxs-lookup"><span data-stu-id="b7d9b-202">The binding is specified in the configuration files for the client and service.</span></span> <span data-ttu-id="b7d9b-203">バインディングの種類は、`binding` 要素の `<endpoint>` 属性を使用して指定します。</span><span class="sxs-lookup"><span data-stu-id="b7d9b-203">The binding type is specified using the `binding` attribute of the `<endpoint>` element.</span></span> <span data-ttu-id="b7d9b-204">基本的なバインディングを構成してその設定の一部を変更する場合は、バインディング構成を定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b7d9b-204">If you want to configure the basic binding and change some of its settings, it is necessary to define a binding configuration.</span></span> <span data-ttu-id="b7d9b-205">エンドポイントは、`bindingConfiguration` 要素の `<endpoint>` 属性を使用して、名前でバインド構成を参照する必要があります。次のサービスの構成コードを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b7d9b-205">The endpoint must reference the binding configuration by name by using the `bindingConfiguration` attribute of the `<endpoint>` element, as shown in the following configuration code for the service.</span></span>  
  
```xml  
<system.serviceModel>
  <services>
    <service type="Microsoft.ServiceModel.Samples.CalculatorService"
             behaviorConfiguration="CalculatorServiceBehavior">
      <endpoint address=""
                binding="netHttpsBinding"
                bindingConfiguration="Binding1"
                contract="Microsoft.ServiceModel.Samples.ICalculator" />
    </service>
  </services>
  <bindings>
    <netHttpsBinding>
      <binding name="Binding1"
               hostNameComparisonMode="StrongWildcard"
               receiveTimeout="00:10:00"
               sendTimeout="00:10:00"
               openTimeout="00:10:00"
               closeTimeout="00:10:00"
               maxReceivedMessageSize="65536"
               maxBufferSize="65536"
               maxBufferPoolSize="524288"
               transferMode="Buffered"
               messageEncoding="Binary"
               textEncoding="utf-8"
               bypassProxyOnLocal="false"
               useDefaultWebProxy="true">
        <security mode="None" />
      </binding>
    </netHttpsBinding>
  </bindings>
</system.serviceModel>
```  
  
## <a name="example"></a><span data-ttu-id="b7d9b-206">例</span><span class="sxs-lookup"><span data-stu-id="b7d9b-206">Example</span></span>  
 <span data-ttu-id="b7d9b-207">[!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] 以降では、バインディングおよび動作に名前を付ける必要はありません。</span><span class="sxs-lookup"><span data-stu-id="b7d9b-207">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="b7d9b-208">エンドポイント アドレスとバインディングの名前から、bindingConfiguration を削除することで、前の例では、の機能を実現できます。</span><span class="sxs-lookup"><span data-stu-id="b7d9b-208">The functionality from the previous example can be accomplished by removing the bindingConfiguration from the endpoint address and the name from the binding.</span></span>  
  
```xml  
<system.serviceModel>
  <services>
    <service type="Microsoft.ServiceModel.Samples.CalculatorService"
             behaviorConfiguration="CalculatorServiceBehavior">
      <endpoint address=""
                binding="netHttpsBinding"
                contract="Microsoft.ServiceModel.Samples.ICalculator" />
    </service>
  </services>
  <bindings>
    <netHttpsBinding>
      <binding hostNameComparisonMode="StrongWildcard"
               receiveTimeout="00:10:00"
               sendTimeout="00:10:00"
               openTimeout="00:10:00"
               closeTimeout="00:10:00"
               maxReceivedMessageSize="65536"
               maxBufferSize="65536"
               maxBufferPoolSize="524288"
               transferMode="Buffered"
               messageEncoding="Binary"
               textEncoding="utf-8"
               bypassProxyOnLocal="false"
               useDefaultWebProxy="true">
        <security mode="None" />
      </binding>
    </netHttpsBinding>
  </bindings>
</system.serviceModel>
```  
  
 <span data-ttu-id="b7d9b-209">既定の構成と無名のバインディングおよび動作の詳細については、「[簡略化された構成](../../../../../docs/framework/wcf/simplified-configuration.md)」と「[WCF サービスの構成を簡略化](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b7d9b-209">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7d9b-210">関連項目</span><span class="sxs-lookup"><span data-stu-id="b7d9b-210">See also</span></span>
- <xref:System.ServiceModel.Channels.Binding>
- <xref:System.ServiceModel.Channels.BindingElement>
- <xref:System.ServiceModel.BasicHttpBinding>
- <xref:System.ServiceModel.Configuration.BasicHttpBindingElement>
- [<span data-ttu-id="b7d9b-211">バインディング</span><span class="sxs-lookup"><span data-stu-id="b7d9b-211">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="b7d9b-212">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="b7d9b-212">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="b7d9b-213">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="b7d9b-213">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="b7d9b-214">\<binding></span><span class="sxs-lookup"><span data-stu-id="b7d9b-214">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
