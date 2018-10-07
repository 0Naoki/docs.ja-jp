---
title: '&lt;basicHttpBinding&gt; の &lt;security&gt;'
ms.date: 03/30/2017
ms.assetid: 6432708d-5465-4bd9-bfc2-466742db99cb
author: BrucePerlerMS
ms.openlocfilehash: 5f7386fc2368ee8c27a95202cef81d8a5c736d5e
ms.sourcegitcommit: 586dbdcaef9767642436b1e4efbe88fb15473d6f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2018
ms.locfileid: "48835947"
---
# <a name="ltsecuritygt-of-ltbasichttpbindinggt"></a><span data-ttu-id="36d4d-102">&lt;basicHttpBinding&gt; の &lt;security&gt;</span><span class="sxs-lookup"><span data-stu-id="36d4d-102">&lt;security&gt; of &lt;basicHttpBinding&gt;</span></span>
<span data-ttu-id="36d4d-103">セキュリティ機能を定義、 [ \<basicHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md)します。</span><span class="sxs-lookup"><span data-stu-id="36d4d-103">Defines the security capabilities of the [\<basicHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md).</span></span>  
  
 <span data-ttu-id="36d4d-104">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="36d4d-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="36d4d-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="36d4d-105">\<bindings></span></span>  
<span data-ttu-id="36d4d-106">\<basicHttpBinding></span><span class="sxs-lookup"><span data-stu-id="36d4d-106">\<basicHttpBinding></span></span>  
<span data-ttu-id="36d4d-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="36d4d-107">\<binding></span></span>  
<span data-ttu-id="36d4d-108">\<セキュリティ ></span><span class="sxs-lookup"><span data-stu-id="36d4d-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36d4d-109">構文</span><span class="sxs-lookup"><span data-stu-id="36d4d-109">Syntax</span></span>  
  
```xml  
<security mode="Message/None/Transport/TransportWithCredential">  
   <transport  
      clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"  
      proxyCredentialType="Basic/Digest/None/Ntlm/Windows"  
      realm="string" />  
   <message  
      algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
            clientCredentialType="Certificate/IssuedToken/None/UserName/Windows" />  
</security>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="36d4d-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="36d4d-110">Attributes and Elements</span></span>  
 <span data-ttu-id="36d4d-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="36d4d-111">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="36d4d-112">属性</span><span class="sxs-lookup"><span data-stu-id="36d4d-112">Attributes</span></span>  
  
|<span data-ttu-id="36d4d-113">属性</span><span class="sxs-lookup"><span data-stu-id="36d4d-113">Attribute</span></span>|<span data-ttu-id="36d4d-114">説明</span><span class="sxs-lookup"><span data-stu-id="36d4d-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="36d4d-115">モード</span><span class="sxs-lookup"><span data-stu-id="36d4d-115">mode</span></span>|<span data-ttu-id="36d4d-116">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="36d4d-116">Optional.</span></span> <span data-ttu-id="36d4d-117">使用されるセキュリティの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="36d4d-117">Specifies the type of security that is used.</span></span> <span data-ttu-id="36d4d-118">既定値は、`None` です。</span><span class="sxs-lookup"><span data-stu-id="36d4d-118">The default is `None`.</span></span> <span data-ttu-id="36d4d-119">この属性は <xref:System.ServiceModel.BasicHttpSecurityMode> 型です。</span><span class="sxs-lookup"><span data-stu-id="36d4d-119">This attribute is of type <xref:System.ServiceModel.BasicHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="36d4d-120">mode 属性</span><span class="sxs-lookup"><span data-stu-id="36d4d-120">mode Attribute</span></span>  
  
|<span data-ttu-id="36d4d-121">値</span><span class="sxs-lookup"><span data-stu-id="36d4d-121">Value</span></span>|<span data-ttu-id="36d4d-122">説明</span><span class="sxs-lookup"><span data-stu-id="36d4d-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="36d4d-123">なし</span><span class="sxs-lookup"><span data-stu-id="36d4d-123">None</span></span>|<span data-ttu-id="36d4d-124">メッセージの数は、転送中にセキュリティ保護されません。</span><span class="sxs-lookup"><span data-stu-id="36d4d-124">-   Messages are not secured during transfer.</span></span>|  
|<span data-ttu-id="36d4d-125">Transport</span><span class="sxs-lookup"><span data-stu-id="36d4d-125">Transport</span></span>|<span data-ttu-id="36d4d-126">セキュリティは、HTTPS トランスポートを使用して提供されます。</span><span class="sxs-lookup"><span data-stu-id="36d4d-126">Security is provided using HTTPS transport.</span></span> <span data-ttu-id="36d4d-127">SOAP メッセージは、HTTPS を使用したセキュリティで保護されます。</span><span class="sxs-lookup"><span data-stu-id="36d4d-127">The SOAP messages are secured using HTTPS.</span></span> <span data-ttu-id="36d4d-128">サービスは、サービスの X.509 証明書を使用してクライアントに認証されます。</span><span class="sxs-lookup"><span data-stu-id="36d4d-128">The service is authenticated to the client using the service's X.509 certificate.</span></span> <span data-ttu-id="36d4d-129">クライアントは、提供される ClientCredentialType を使用して認証されます。</span><span class="sxs-lookup"><span data-stu-id="36d4d-129">The client is authenticated using the ClientCredentialType supplied.</span></span> <span data-ttu-id="36d4d-130">参照してください、 [\<トランスポート >](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-basichttpbinding.md)します。</span><span class="sxs-lookup"><span data-stu-id="36d4d-130">See the [\<transport>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-basichttpbinding.md).</span></span>|  
|<span data-ttu-id="36d4d-131">メッセージ</span><span class="sxs-lookup"><span data-stu-id="36d4d-131">Message</span></span>|<span data-ttu-id="36d4d-132">セキュリティは、SOAP メッセージ セキュリティを使用して確保されます。</span><span class="sxs-lookup"><span data-stu-id="36d4d-132">Security is provided using SOAP message security.</span></span> <span data-ttu-id="36d4d-133">既定では、本文は暗号化および署名されます。</span><span class="sxs-lookup"><span data-stu-id="36d4d-133">By default, the body is encrypted and signed.</span></span> <span data-ttu-id="36d4d-134">このバインディングの場合、サーバー証明書をクライアントの帯域外で提供するように要求されます。</span><span class="sxs-lookup"><span data-stu-id="36d4d-134">For this binding, the system requires that the server certificate be provided to the client out of band.</span></span> <span data-ttu-id="36d4d-135">このバインディングの唯一の有効な `ClientCredentialType` は、`Certificate` です。</span><span class="sxs-lookup"><span data-stu-id="36d4d-135">The only valid `ClientCredentialType` for this binding is `Certificate`.</span></span>|  
|<span data-ttu-id="36d4d-136">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="36d4d-136">TransportWithMessageCredential</span></span>|<span data-ttu-id="36d4d-137">整合性、機密性、およびサーバー認証は、トランスポート セキュリティによって提供されます。</span><span class="sxs-lookup"><span data-stu-id="36d4d-137">Integrity, confidentiality and server authentication are provided by transport security.</span></span> <span data-ttu-id="36d4d-138">クライアント認証は、SOAP メッセージ セキュリティで提供されます。</span><span class="sxs-lookup"><span data-stu-id="36d4d-138">Client authentication is provided by means of SOAP message security.</span></span> <span data-ttu-id="36d4d-139">このモードは、ユーザーがユーザー名およびパスワードを使用して認証し、メッセージ転送をセキュリティで保護するために既存の HTTP が配置されている場合に関連します。</span><span class="sxs-lookup"><span data-stu-id="36d4d-139">This mode is relevant when the user is authenticating using username/password and there is an existing HTTP deployment for securing message transfer.</span></span>|  
|<span data-ttu-id="36d4d-140">TransportCredentialOnly</span><span class="sxs-lookup"><span data-stu-id="36d4d-140">TransportCredentialOnly</span></span>|<span data-ttu-id="36d4d-141">このモードは、メッセージの整合性と機密性を提供しません。</span><span class="sxs-lookup"><span data-stu-id="36d4d-141">This mode does not provide message integrity and confidentiality.</span></span> <span data-ttu-id="36d4d-142">http ベースのクライアント認証を提供します。</span><span class="sxs-lookup"><span data-stu-id="36d4d-142">It provides http-based client authentication.</span></span> <span data-ttu-id="36d4d-143">このモードを使用するときは、十分に注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="36d4d-143">This mode should be used with caution.</span></span> <span data-ttu-id="36d4d-144">これは、トランスポート セキュリティ (IPSec) などの他の方法で提供されるされ、クライアント認証だけが、WCF インフラストラクチャによって提供される環境で使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="36d4d-144">It should be used in environments where the transport security is being provided by other means (such as IPSec) and only client authentication is provided by the WCF infrastructure.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="36d4d-145">子要素</span><span class="sxs-lookup"><span data-stu-id="36d4d-145">Child Elements</span></span>  
  
|<span data-ttu-id="36d4d-146">要素</span><span class="sxs-lookup"><span data-stu-id="36d4d-146">Element</span></span>|<span data-ttu-id="36d4d-147">説明</span><span class="sxs-lookup"><span data-stu-id="36d4d-147">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="36d4d-148">\<transport></span><span class="sxs-lookup"><span data-stu-id="36d4d-148">\<transport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-basichttpbinding.md)|<span data-ttu-id="36d4d-149">基本 HTTP サービスのトランスポート セキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="36d4d-149">Defines the transport security settings for a basic HTTP service.</span></span> <span data-ttu-id="36d4d-150">この要素は、<xref:System.ServiceModel.HttpTransportSecurity> に対応しています。</span><span class="sxs-lookup"><span data-stu-id="36d4d-150">This element corresponds to <xref:System.ServiceModel.HttpTransportSecurity>.</span></span>|  
|[<span data-ttu-id="36d4d-151">\<message></span><span class="sxs-lookup"><span data-stu-id="36d4d-151">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-of-basichttpbinding.md)|<span data-ttu-id="36d4d-152">基本 HTTP サービスのメッセージ セキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="36d4d-152">Defines the message security settings for a basic HTTP service.</span></span> <span data-ttu-id="36d4d-153">この要素は、<xref:System.ServiceModel.BasicHttpMessageSecurity> に対応しています。</span><span class="sxs-lookup"><span data-stu-id="36d4d-153">This element corresponds to <xref:System.ServiceModel.BasicHttpMessageSecurity>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="36d4d-154">親要素</span><span class="sxs-lookup"><span data-stu-id="36d4d-154">Parent Elements</span></span>  
  
|<span data-ttu-id="36d4d-155">要素</span><span class="sxs-lookup"><span data-stu-id="36d4d-155">Element</span></span>|<span data-ttu-id="36d4d-156">説明</span><span class="sxs-lookup"><span data-stu-id="36d4d-156">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="36d4d-157">バインド</span><span class="sxs-lookup"><span data-stu-id="36d4d-157">binding</span></span>|<span data-ttu-id="36d4d-158">バインド要素、 [ \<basicHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md)します。</span><span class="sxs-lookup"><span data-stu-id="36d4d-158">The binding element of the [\<basicHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="36d4d-159">Remarks</span><span class="sxs-lookup"><span data-stu-id="36d4d-159">Remarks</span></span>  
 <span data-ttu-id="36d4d-160">既定では、SOAP メッセージはセキュリティで保護されず、クライアントは認証されません。</span><span class="sxs-lookup"><span data-stu-id="36d4d-160">By default, the SOAP message is not secured and the client is not authenticated.</span></span> <span data-ttu-id="36d4d-161">この要素を使用すると、`basicHttpBinding` 要素に追加のセキュリティ設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="36d4d-161">This element enables you to configure additional security settings for the `basicHttpBinding` element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36d4d-162">関連項目</span><span class="sxs-lookup"><span data-stu-id="36d4d-162">See Also</span></span>  
 <xref:System.ServiceModel.BasicHttpBinding.Security%2A>  
 <xref:System.ServiceModel.Configuration.BasicHttpBindingElement.Security%2A>  
 <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement>  
 <xref:System.ServiceModel.BasicHttpSecurity>  
 [<span data-ttu-id="36d4d-163">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="36d4d-163">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="36d4d-164">資格情報の種類の選択</span><span class="sxs-lookup"><span data-stu-id="36d4d-164">Selecting a Credential Type</span></span>](../../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)  
 [<span data-ttu-id="36d4d-165">バインディング</span><span class="sxs-lookup"><span data-stu-id="36d4d-165">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="36d4d-166">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="36d4d-166">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="36d4d-167">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="36d4d-167">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)  
 [<span data-ttu-id="36d4d-168">\<binding></span><span class="sxs-lookup"><span data-stu-id="36d4d-168">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
