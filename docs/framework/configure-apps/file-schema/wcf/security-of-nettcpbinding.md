---
title: '&lt;netTcpBinding&gt; の &lt;security&gt;'
ms.date: 03/30/2017
ms.assetid: 286cd191-4fd5-4c4e-a223-9c71cf7fdead
author: BrucePerlerMS
ms.openlocfilehash: 045fb60f6ae0fb54dce7fd9bc8c634caee5fddcd
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/26/2018
ms.locfileid: "47205327"
---
# <a name="ltsecuritygt-of-ltnettcpbindinggt"></a><span data-ttu-id="474b9-102">&lt;netTcpBinding&gt; の &lt;security&gt;</span><span class="sxs-lookup"><span data-stu-id="474b9-102">&lt;security&gt; of &lt;netTcpBinding&gt;</span></span>
<span data-ttu-id="474b9-103">バインディングのセキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="474b9-103">Defines the security settings for a binding.</span></span>  
  
 <span data-ttu-id="474b9-104">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="474b9-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="474b9-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="474b9-105">\<bindings></span></span>  
<span data-ttu-id="474b9-106">\<netTcpBinding ></span><span class="sxs-lookup"><span data-stu-id="474b9-106">\<netTcpBinding></span></span>  
<span data-ttu-id="474b9-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="474b9-107">\<binding></span></span>  
<span data-ttu-id="474b9-108">\<セキュリティ ></span><span class="sxs-lookup"><span data-stu-id="474b9-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="474b9-109">構文</span><span class="sxs-lookup"><span data-stu-id="474b9-109">Syntax</span></span>  
  
```xml  
<security mode="Message/None/Transport/TransportWithCredential">  
   <transport  
      clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"  
           protectionLevel="None/Sign/EncryptAndSign" />  
   <message  
      algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
      clientCredentialType="Certificate/IssuedToken/None/UserName/Windows" />  
</security>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="474b9-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="474b9-110">Attributes and Elements</span></span>  
 <span data-ttu-id="474b9-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="474b9-111">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="474b9-112">属性</span><span class="sxs-lookup"><span data-stu-id="474b9-112">Attributes</span></span>  
  
|<span data-ttu-id="474b9-113">属性</span><span class="sxs-lookup"><span data-stu-id="474b9-113">Attribute</span></span>|<span data-ttu-id="474b9-114">説明</span><span class="sxs-lookup"><span data-stu-id="474b9-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="474b9-115">モード</span><span class="sxs-lookup"><span data-stu-id="474b9-115">mode</span></span>|<span data-ttu-id="474b9-116">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="474b9-116">Optional.</span></span> <span data-ttu-id="474b9-117">適用するセキュリティの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="474b9-117">Specifies the type of security that is applied.</span></span> <span data-ttu-id="474b9-118">有効な値を次に示します。</span><span class="sxs-lookup"><span data-stu-id="474b9-118">Valid values are shown below.</span></span> <span data-ttu-id="474b9-119">既定値は `Transport` です。</span><span class="sxs-lookup"><span data-stu-id="474b9-119">The default value is `Transport`.</span></span><br /><br /> <span data-ttu-id="474b9-120">この属性は <xref:System.ServiceModel.SecurityMode> 型です。</span><span class="sxs-lookup"><span data-stu-id="474b9-120">This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="474b9-121">mode 属性</span><span class="sxs-lookup"><span data-stu-id="474b9-121">mode Attribute</span></span>  
  
|<span data-ttu-id="474b9-122">値</span><span class="sxs-lookup"><span data-stu-id="474b9-122">Value</span></span>|<span data-ttu-id="474b9-123">説明</span><span class="sxs-lookup"><span data-stu-id="474b9-123">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="474b9-124">なし</span><span class="sxs-lookup"><span data-stu-id="474b9-124">None</span></span>|<span data-ttu-id="474b9-125">セキュリティを無効にします。</span><span class="sxs-lookup"><span data-stu-id="474b9-125">Security is disabled.</span></span>|  
|<span data-ttu-id="474b9-126">Transport</span><span class="sxs-lookup"><span data-stu-id="474b9-126">Transport</span></span>|<span data-ttu-id="474b9-127">トランスポート セキュリティは、TCP 経由の TLS または SPNaego を使用して提供されます。</span><span class="sxs-lookup"><span data-stu-id="474b9-127">Transport security is provided using TLS over TCP or SPNego.</span></span> <span data-ttu-id="474b9-128">サービスは、SSL 証明書を使用して設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="474b9-128">The service may need to be configured with SSL certificates.</span></span> <span data-ttu-id="474b9-129">このモードでの保護レベルを制御できます。</span><span class="sxs-lookup"><span data-stu-id="474b9-129">It is possible to control the protection level with this mode.</span></span>|  
|<span data-ttu-id="474b9-130">メッセージ</span><span class="sxs-lookup"><span data-stu-id="474b9-130">Message</span></span>|<span data-ttu-id="474b9-131">セキュリティは、SOAP メッセージ セキュリティを使用して確保されます。</span><span class="sxs-lookup"><span data-stu-id="474b9-131">Security is provided using SOAP message security.</span></span> <span data-ttu-id="474b9-132">既定では、SOAP 本文は暗号化および署名されます。</span><span class="sxs-lookup"><span data-stu-id="474b9-132">By default, the SOAP body is encrypted and signed.</span></span> <span data-ttu-id="474b9-133">このモードは、サービス資格情報をクライアントの帯域外で使用可能にするかどうか、使用するアルゴリズム スイート、メッセージ本文に適用する保護レベルなど、さまざまな機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="474b9-133">This mode offers a variety of features, such as whether the service credentials are available at the client out of band, the algorithm suite to use, and what level of protection to apply to the message body.</span></span> <span data-ttu-id="474b9-134">クライアント認証はセッションごとに 1 回実行され、認証の結果はセッションの存続中にキャッシュされます。</span><span class="sxs-lookup"><span data-stu-id="474b9-134">Client authentication is performed once per session and the results of authentication are cached for the duration of the session.</span></span>|  
|<span data-ttu-id="474b9-135">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="474b9-135">TransportWithMessageCredential</span></span>|<span data-ttu-id="474b9-136">トランスポート セキュリティは、メッセージ セキュリティと組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="474b9-136">Transport security is coupled with message security.</span></span> <span data-ttu-id="474b9-137">トランスポート セキュリティは、TCP 経由の TLS または SPNego によって提供され、整合性、機密性、およびサーバー認証が保証されます。</span><span class="sxs-lookup"><span data-stu-id="474b9-137">Transport security is provided by TLS over TCP, or SPNego, and ensures integrity, confidentiality, and server authentication.</span></span> <span data-ttu-id="474b9-138">SOAP メッセージ セキュリティは、クライアント認証を提供します。</span><span class="sxs-lookup"><span data-stu-id="474b9-138">SOAP message security provides client authentication.</span></span> <span data-ttu-id="474b9-139">既定では、クライアント認証はセッションごとに 1 回実行され、認証の結果はセッションの存続中にキャッシュされます。</span><span class="sxs-lookup"><span data-stu-id="474b9-139">By default, client authentication is performed once per session and the results of authentication are cached for the duration of the session.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="474b9-140">子要素</span><span class="sxs-lookup"><span data-stu-id="474b9-140">Child Elements</span></span>  
  
|<span data-ttu-id="474b9-141">要素</span><span class="sxs-lookup"><span data-stu-id="474b9-141">Element</span></span>|<span data-ttu-id="474b9-142">説明</span><span class="sxs-lookup"><span data-stu-id="474b9-142">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="474b9-143">\<transport></span><span class="sxs-lookup"><span data-stu-id="474b9-143">\<transport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-nettcpbinding.md)|<span data-ttu-id="474b9-144">トランスポートのセキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="474b9-144">Defines the security settings for the transport.</span></span> <span data-ttu-id="474b9-145">この要素は <xref:System.ServiceModel.Configuration.TcpTransportSecurityElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="474b9-145">This element is of type <xref:System.ServiceModel.Configuration.TcpTransportSecurityElement>.</span></span>|  
|[<span data-ttu-id="474b9-146">\<message></span><span class="sxs-lookup"><span data-stu-id="474b9-146">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-nettcpbinding.md)|<span data-ttu-id="474b9-147">メッセージのセキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="474b9-147">Defines the security settings for the message.</span></span> <span data-ttu-id="474b9-148">この要素は <xref:System.ServiceModel.Configuration.MessageSecurityOverTcpElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="474b9-148">This element is of type <xref:System.ServiceModel.Configuration.MessageSecurityOverTcpElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="474b9-149">親要素</span><span class="sxs-lookup"><span data-stu-id="474b9-149">Parent Elements</span></span>  
  
|<span data-ttu-id="474b9-150">要素</span><span class="sxs-lookup"><span data-stu-id="474b9-150">Element</span></span>|<span data-ttu-id="474b9-151">説明</span><span class="sxs-lookup"><span data-stu-id="474b9-151">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="474b9-152">バインド</span><span class="sxs-lookup"><span data-stu-id="474b9-152">binding</span></span>|<span data-ttu-id="474b9-153">バインド要素、 [ \<netTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md)します。</span><span class="sxs-lookup"><span data-stu-id="474b9-153">The binding element of the [\<netTcpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="474b9-154">Remarks</span><span class="sxs-lookup"><span data-stu-id="474b9-154">Remarks</span></span>  
 <span data-ttu-id="474b9-155">標準バインディングにはそれぞれ、転送セキュリティ要件を制御するためのパラメーターが用意されています。</span><span class="sxs-lookup"><span data-stu-id="474b9-155">Each of the standard bindings provides parameters for controlling the transfer security requirements.</span></span> <span data-ttu-id="474b9-156">通常、これらのパラメーターには、使用されるセキュリティ レベル (メッセージ レベルまたはトランスポート レベル) を指定したセキュリティ モードと、クライアント資格情報の種類が含まれています。</span><span class="sxs-lookup"><span data-stu-id="474b9-156">These parameters typically include the security mode that specified whether message-level or transport-level security is used and the choice of client credential type.</span></span> <span data-ttu-id="474b9-157">これらのパラメーターが提示するオプションの選択に基づいて、適切なセキュリティが設定されたチャネル スタックが構築されます。</span><span class="sxs-lookup"><span data-stu-id="474b9-157">Based on the choice of options these parameters present, a channel stack is constructed with appropriate security.</span></span>  
  
 <span data-ttu-id="474b9-158">WCF (Windows Communication Foundation) に用意されているシステム標準のバインディグは、最も一般的なシナリオ要件の一部を満たすように設計されたセットです。</span><span class="sxs-lookup"><span data-stu-id="474b9-158">The system-provided bindings supplied by Windows Communication Foundation (WCF) are a set designed to meet some of the most common scenario requirements.</span></span> <span data-ttu-id="474b9-159">これらのバイディングでは、特定のシナリオを対象とするセキュリティ要件を指定できます。</span><span class="sxs-lookup"><span data-stu-id="474b9-159">Each of these bindings allows the specification of security requirements for some specific targeted scenarios.</span></span>  
  
 <span data-ttu-id="474b9-160">この構成要素によって、`netTcpBinding` のセキュリティ仕様が提供されます。</span><span class="sxs-lookup"><span data-stu-id="474b9-160">This configuration element provides the security specifications for `netTcpBinding`.</span></span> <span data-ttu-id="474b9-161">これは、コンピューター間通信に適した、安全で信頼できる最適化されたバインディングです。</span><span class="sxs-lookup"><span data-stu-id="474b9-161">This is a secure, reliable, optimized binding suitable for cross-machine communication.</span></span> <span data-ttu-id="474b9-162">既定では、このバインディングは、メッセージを配信するための TCP、メッセージの保護と認証を行うための Windows セキュリティ、信頼性を高めるための WS-ReliableMessaging、およびバイナリ メッセージのエンコーディングをサポートするランタイム通信スタックを生成します。</span><span class="sxs-lookup"><span data-stu-id="474b9-162">By default it generates a runtime communication stack supporting TCP for message delivery and Windows Security for message security and authentication, WS-ReliableMessaging for reliability, and binary message encoding.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="474b9-163">関連項目</span><span class="sxs-lookup"><span data-stu-id="474b9-163">See Also</span></span>  
 <xref:System.ServiceModel.NetTcpSecurity>  
 <xref:System.ServiceModel.NetTcpBinding.Security%2A>  
 <xref:System.ServiceModel.Configuration.NetTcpBindingElement.Security%2A>  
 <xref:System.ServiceModel.Configuration.NetTcpSecurityElement>  
 [<span data-ttu-id="474b9-164">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="474b9-164">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="474b9-165">バインディング</span><span class="sxs-lookup"><span data-stu-id="474b9-165">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="474b9-166">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="474b9-166">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="474b9-167">バインドを使用して、Windows Communication Foundation サービスとクライアントを構成するには</span><span class="sxs-lookup"><span data-stu-id="474b9-167">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](https://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="474b9-168">\<binding></span><span class="sxs-lookup"><span data-stu-id="474b9-168">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
