---
title: '&lt;wsHttpBinding&gt; の &lt;security&gt;'
ms.date: 03/30/2017
ms.assetid: 8658b162-2ddf-4162-a869-aa517a42288a
ms.openlocfilehash: dd3ff1b1b00be376abc5f8d3c44cb0aabc49a230
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54688819"
---
# <a name="ltsecuritygt-of-ltwshttpbindinggt"></a><span data-ttu-id="36394-102">&lt;wsHttpBinding&gt; の &lt;security&gt;</span><span class="sxs-lookup"><span data-stu-id="36394-102">&lt;security&gt; of &lt;wsHttpBinding&gt;</span></span>
<span data-ttu-id="36394-103">セキュリティ機能を表す、 [ \<wsHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)します。</span><span class="sxs-lookup"><span data-stu-id="36394-103">Represents the security capabilities of the [\<wsHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md).</span></span>  
  
 <span data-ttu-id="36394-104">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="36394-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="36394-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="36394-105">\<bindings></span></span>  
<span data-ttu-id="36394-106">\<wsHttpBinding></span><span class="sxs-lookup"><span data-stu-id="36394-106">\<wsHttpBinding></span></span>  
<span data-ttu-id="36394-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="36394-107">\<binding></span></span>  
<span data-ttu-id="36394-108">\<セキュリティ ></span><span class="sxs-lookup"><span data-stu-id="36394-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36394-109">構文</span><span class="sxs-lookup"><span data-stu-id="36394-109">Syntax</span></span>  
  
```xml  
<security mode="Message/None/Transport/TransportWithMessageCredential">
  <transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
             proxyCredentialType="Basic/Digest/None/Ntlm/Windows"
             realm="String"
             defaultClientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
             defaultProxyCredentialType="Basic/Digest/None/Ntlm/Windows"
             defaultRealm="String" />
  <message clientCredentialType="Certificate/IssuedToken/None/UserName/Windows"
           algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
           establishSecurityContext="Boolean"
           negotiateServiceCredential="Boolean" />
</security>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="36394-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="36394-110">Attributes and Elements</span></span>  
 <span data-ttu-id="36394-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="36394-111">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="36394-112">属性</span><span class="sxs-lookup"><span data-stu-id="36394-112">Attributes</span></span>  
  
|<span data-ttu-id="36394-113">属性</span><span class="sxs-lookup"><span data-stu-id="36394-113">Attribute</span></span>|<span data-ttu-id="36394-114">説明</span><span class="sxs-lookup"><span data-stu-id="36394-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="36394-115">モード</span><span class="sxs-lookup"><span data-stu-id="36394-115">mode</span></span>|<span data-ttu-id="36394-116">-省略可能。</span><span class="sxs-lookup"><span data-stu-id="36394-116">-   Optional.</span></span> <span data-ttu-id="36394-117">適用するセキュリティの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="36394-117">Specifies the type of security that is applied.</span></span> <span data-ttu-id="36394-118">既定値は `Message` です。</span><span class="sxs-lookup"><span data-stu-id="36394-118">The default is `Message`.</span></span><br /><span data-ttu-id="36394-119">-この属性が型<xref:System.ServiceModel.SecurityMode>します。</span><span class="sxs-lookup"><span data-stu-id="36394-119">-   This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="36394-120">Mode 属性</span><span class="sxs-lookup"><span data-stu-id="36394-120">Mode Attribute</span></span>  
  
|<span data-ttu-id="36394-121">値</span><span class="sxs-lookup"><span data-stu-id="36394-121">Value</span></span>|<span data-ttu-id="36394-122">説明</span><span class="sxs-lookup"><span data-stu-id="36394-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="36394-123">なし</span><span class="sxs-lookup"><span data-stu-id="36394-123">None</span></span>|<span data-ttu-id="36394-124">セキュリティを無効にします。</span><span class="sxs-lookup"><span data-stu-id="36394-124">Security is disabled.</span></span>|  
|<span data-ttu-id="36394-125">Transport</span><span class="sxs-lookup"><span data-stu-id="36394-125">Transport</span></span>|<span data-ttu-id="36394-126">セキュリティは、HTTPS を使用して確保されます。</span><span class="sxs-lookup"><span data-stu-id="36394-126">Security is provided using HTTPS.</span></span> <span data-ttu-id="36394-127">サービスは、SSL 証明書を使用して構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="36394-127">The service needs to be configured with SSL certificates.</span></span> <span data-ttu-id="36394-128">メッセージは、HTTPS を使用して完全にセキュリティで保護され、サービスの SSL 証明書を使用するクライアントによって認証されます。</span><span class="sxs-lookup"><span data-stu-id="36394-128">The message is entirely secured using HTTPS and is authenticated by the client using the service’s SSL certificate.</span></span> <span data-ttu-id="36394-129">クライアント認証は、`ClientCredentials` 属性を使用して制御されます。</span><span class="sxs-lookup"><span data-stu-id="36394-129">The client authentication is controlled through the `ClientCredentials` attribute.</span></span> <span data-ttu-id="36394-130">[\<トランスポート >](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-wshttpbinding.md)します。</span><span class="sxs-lookup"><span data-stu-id="36394-130">of the [\<transport>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-wshttpbinding.md).</span></span>|  
|<span data-ttu-id="36394-131">メッセージ</span><span class="sxs-lookup"><span data-stu-id="36394-131">Message</span></span>|<span data-ttu-id="36394-132">セキュリティは、SOAP メッセージ セキュリティを使用して確保されます。</span><span class="sxs-lookup"><span data-stu-id="36394-132">Security is provided using SOAP message security.</span></span> <span data-ttu-id="36394-133">既定では、SOAP 本文は暗号化および署名されます。</span><span class="sxs-lookup"><span data-stu-id="36394-133">By default, the SOAP body is Encrypted and Signed.</span></span> <span data-ttu-id="36394-134">このモードは、サービス資格情報をクライアントの帯域外で使用可能にするかどうか、使用するアルゴリズム スイート、Security.Message プロパティを使用してメッセージ本文に適用する保護レベルなど、さまざまな機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="36394-134">This mode offers a variety of features, such as whether the service credentials are available at the client out of band, the algorithm suite to use, and what level of protection to apply to the message body through the Security.Message property.</span></span> <span data-ttu-id="36394-135">クライアント認証はセッションごとに 1 回実行され、認証の結果はセッションの存続中にキャッシュされます。</span><span class="sxs-lookup"><span data-stu-id="36394-135">Client authentication is performed once per session and the results of authentication are cached for the duration of the session.</span></span>|  
|<span data-ttu-id="36394-136">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="36394-136">TransportWithMessageCredential</span></span>|<span data-ttu-id="36394-137">このモードでは、HTTPS は、整合性、機密性、およびサーバー認証を提供し、SOAP メッセージ セキュリティはクライアント認証を提供します。</span><span class="sxs-lookup"><span data-stu-id="36394-137">In this mode, HTTPS provides integrity, confidentiality, and server authentication, and SOAP message security provides client authentication.</span></span> <span data-ttu-id="36394-138">既定では、クライアント認証はセッションごとに 1 回実行され、認証の結果はセッションの存続中にキャッシュされます。</span><span class="sxs-lookup"><span data-stu-id="36394-138">By default, client authentication is performed once per session and the results of authentication are cached for the duration of the session.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="36394-139">子要素</span><span class="sxs-lookup"><span data-stu-id="36394-139">Child Elements</span></span>  
  
|<span data-ttu-id="36394-140">要素</span><span class="sxs-lookup"><span data-stu-id="36394-140">Element</span></span>|<span data-ttu-id="36394-141">説明</span><span class="sxs-lookup"><span data-stu-id="36394-141">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="36394-142">\<transport></span><span class="sxs-lookup"><span data-stu-id="36394-142">\<transport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-wshttpbinding.md)|<span data-ttu-id="36394-143">トランスポートのセキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="36394-143">Defines the transport security settings.</span></span> <span data-ttu-id="36394-144">この要素は、<xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> 型に対応しています。</span><span class="sxs-lookup"><span data-stu-id="36394-144">This element corresponds to the <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> type.</span></span>|  
|[<span data-ttu-id="36394-145">\<message></span><span class="sxs-lookup"><span data-stu-id="36394-145">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wshttpbinding.md)|<span data-ttu-id="36394-146">メッセージのセキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="36394-146">Defines the security settings for the message.</span></span> <span data-ttu-id="36394-147">この要素は、<xref:System.ServiceModel.Configuration.MessageSecurityOverHttpElement> 型に対応しています。</span><span class="sxs-lookup"><span data-stu-id="36394-147">This element corresponds to the <xref:System.ServiceModel.Configuration.MessageSecurityOverHttpElement> type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="36394-148">親要素</span><span class="sxs-lookup"><span data-stu-id="36394-148">Parent Elements</span></span>  
  
|<span data-ttu-id="36394-149">要素</span><span class="sxs-lookup"><span data-stu-id="36394-149">Element</span></span>|<span data-ttu-id="36394-150">説明</span><span class="sxs-lookup"><span data-stu-id="36394-150">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="36394-151">\<wsHttpBinding></span><span class="sxs-lookup"><span data-stu-id="36394-151">\<wsHttpBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)|<span data-ttu-id="36394-152">HTTP トランスポート アプリケーションのセキュリティで保護されたバインド。</span><span class="sxs-lookup"><span data-stu-id="36394-152">A secure binding for HTTP transport applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="36394-153">Remarks</span><span class="sxs-lookup"><span data-stu-id="36394-153">Remarks</span></span>  
 <span data-ttu-id="36394-154">WSHttpBinding クラスは、WS-\* 仕様を実装するサービスと相互運用するようにデザインされています。</span><span class="sxs-lookup"><span data-stu-id="36394-154">The WSHttpBinding class is designed for interoperation with services that implement WS-\* specifications.</span></span> <span data-ttu-id="36394-155">このバインディングのトランスポート セキュリティは、SSL (Secure Sockets Layer) over HTTP または HTTPS です。</span><span class="sxs-lookup"><span data-stu-id="36394-155">The transport security for this binding is Secure Sockets Layer (SSL) over HTTP, or HTTPS.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36394-156">関連項目</span><span class="sxs-lookup"><span data-stu-id="36394-156">See also</span></span>
- <xref:System.ServiceModel.WSHttpSecurity>
- <xref:System.ServiceModel.WSHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.WSHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>
- [<span data-ttu-id="36394-157">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="36394-157">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="36394-158">バインディング</span><span class="sxs-lookup"><span data-stu-id="36394-158">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="36394-159">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="36394-159">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="36394-160">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="36394-160">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="36394-161">\<binding></span><span class="sxs-lookup"><span data-stu-id="36394-161">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
