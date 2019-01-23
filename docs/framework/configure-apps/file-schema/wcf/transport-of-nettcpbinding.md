---
title: '&lt;netTcpBinding&gt; の &lt;transport&gt;'
ms.date: 03/30/2017
ms.assetid: 49462e0a-66e1-463f-b3e1-c83a441673c6
ms.openlocfilehash: 7372b94bde8325ec00116ee7022739f1b17a1ac9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54555493"
---
# <a name="lttransportgt-of-ltnettcpbindinggt"></a><span data-ttu-id="cb57f-102">&lt;netTcpBinding&gt; の &lt;transport&gt;</span><span class="sxs-lookup"><span data-stu-id="cb57f-102">&lt;transport&gt; of &lt;netTcpBinding&gt;</span></span>
<span data-ttu-id="cb57f-103">構成されているエンドポイントのメッセージ レベルのセキュリティ要件の種類を定義、 [ \<netTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md)します。</span><span class="sxs-lookup"><span data-stu-id="cb57f-103">Defines the type of message-level security requirements for an endpoint configured with the [\<netTcpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md).</span></span>  
  
 <span data-ttu-id="cb57f-104">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="cb57f-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="cb57f-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="cb57f-105">\<bindings></span></span>  
<span data-ttu-id="cb57f-106">\<netTcpBinding ></span><span class="sxs-lookup"><span data-stu-id="cb57f-106">\<netTcpBinding></span></span>  
<span data-ttu-id="cb57f-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="cb57f-107">\<binding></span></span>  
<span data-ttu-id="cb57f-108">\<セキュリティ ></span><span class="sxs-lookup"><span data-stu-id="cb57f-108">\<security></span></span>  
<span data-ttu-id="cb57f-109">\<transport></span><span class="sxs-lookup"><span data-stu-id="cb57f-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb57f-110">構文</span><span class="sxs-lookup"><span data-stu-id="cb57f-110">Syntax</span></span>  
  
```xml  
<netTcpBinding>
  <binding>
    <security mode="None|Transport|Message|TransportWithMessageCredential">
      <transport clientCredentialType="None|Windows|Certificate"
                 protectionLevel="None|Sign|EncryptAndSign"
                 sslProtocols="Tls|Tls11|Tls12">
        <extendedProtectionPolicy policyEnforcement="Never|WhenSupported|Always"
                                  protectionScenario="TransportSelected|TrustedProxy">
          <customServiceNames>
          </customServiceNames>
        </extendedProtectionPolicy>
      </transport>
    </security>
  </binding>
</netTcpBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cb57f-111">属性および要素</span><span class="sxs-lookup"><span data-stu-id="cb57f-111">Attributes and Elements</span></span>  
 <span data-ttu-id="cb57f-112">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="cb57f-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cb57f-113">属性</span><span class="sxs-lookup"><span data-stu-id="cb57f-113">Attributes</span></span>  
  
|<span data-ttu-id="cb57f-114">属性</span><span class="sxs-lookup"><span data-stu-id="cb57f-114">Attribute</span></span>|<span data-ttu-id="cb57f-115">説明</span><span class="sxs-lookup"><span data-stu-id="cb57f-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="cb57f-116">clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="cb57f-116">clientCredentialType</span></span>|<span data-ttu-id="cb57f-117">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="cb57f-117">Optional.</span></span> <span data-ttu-id="cb57f-118">トランスポート セキュリティを使用してクライアント認証を実行するときに使用される資格情報の種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="cb57f-118">Specifies the type of credential to be used when performing client authentication using Transport security.</span></span><br /><br /> <span data-ttu-id="cb57f-119">-既定値は`Windows`します。</span><span class="sxs-lookup"><span data-stu-id="cb57f-119">-   The default value is `Windows`.</span></span><br /><span data-ttu-id="cb57f-120">-この属性が型<xref:System.ServiceModel.TcpClientCredentialType>します。</span><span class="sxs-lookup"><span data-stu-id="cb57f-120">-   This attribute is of type <xref:System.ServiceModel.TcpClientCredentialType>.</span></span>|  
|<span data-ttu-id="cb57f-121">protectionLevel</span><span class="sxs-lookup"><span data-stu-id="cb57f-121">protectionLevel</span></span>|<span data-ttu-id="cb57f-122">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="cb57f-122">Optional.</span></span> <span data-ttu-id="cb57f-123">TCP トランスポートのレベルでセキュリティを定義します。</span><span class="sxs-lookup"><span data-stu-id="cb57f-123">Defines security at the level of the TCP transport.</span></span> <span data-ttu-id="cb57f-124">メッセージに署名すると、転送中のメッセージが第三者によって改ざんされるリスクを軽減します。</span><span class="sxs-lookup"><span data-stu-id="cb57f-124">Signing messages mitigates the risk of a third party tampering with the message while it is being transferred.</span></span> <span data-ttu-id="cb57f-125">暗号化により、転送中にデータレベルのプライバシーが提供されます。</span><span class="sxs-lookup"><span data-stu-id="cb57f-125">Encryption provides data-level privacy during transport.</span></span><br /><br /> <span data-ttu-id="cb57f-126">既定値は `EncryptAndSign` です。</span><span class="sxs-lookup"><span data-stu-id="cb57f-126">The default value is `EncryptAndSign`.</span></span>|  
|<span data-ttu-id="cb57f-127">sslProtocols</span><span class="sxs-lookup"><span data-stu-id="cb57f-127">sslProtocols</span></span>|<span data-ttu-id="cb57f-128">どの SslProtocols がサポートされているのかを指定する SslProtocols 列挙型フラグの値。</span><span class="sxs-lookup"><span data-stu-id="cb57f-128">A SslProtocols enum flag value that specifies which SslProtocols are supported.</span></span> <span data-ttu-id="cb57f-129">既定値は Tls&#124;Tls11&#124;tls12 です。</span><span class="sxs-lookup"><span data-stu-id="cb57f-129">The default is Tls&#124;Tls11&#124;Tls12.</span></span>|  
|<span data-ttu-id="cb57f-130">policyEnforcement</span><span class="sxs-lookup"><span data-stu-id="cb57f-130">policyEnforcement</span></span>|<span data-ttu-id="cb57f-131">この列挙体は、<xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> を適用するタイミングを指定します。</span><span class="sxs-lookup"><span data-stu-id="cb57f-131">This enumeration specifies when the <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> should be enforced.</span></span><br /><br /> <span data-ttu-id="cb57f-132">1.Never – ポリシーが適用されることはありません (拡張保護は無効になります)。</span><span class="sxs-lookup"><span data-stu-id="cb57f-132">1.  Never – The policy is never enforced (Extended Protection is disabled).</span></span><br /><span data-ttu-id="cb57f-133">2.WhenSupported – ポリシーが適用されるのは、クライアントが拡張保護をサポートしている場合のみです。</span><span class="sxs-lookup"><span data-stu-id="cb57f-133">2.  WhenSupported – The policy is enforced only if the client supports Extended Protection.</span></span><br /><span data-ttu-id="cb57f-134">3.Always – ポリシーは常に適用されます。</span><span class="sxs-lookup"><span data-stu-id="cb57f-134">3.  Always – The policy is always enforced.</span></span> <span data-ttu-id="cb57f-135">拡張保護をサポートしていないクライアントは認証に失敗します。</span><span class="sxs-lookup"><span data-stu-id="cb57f-135">Clients which don’t support Extended Protection will fail to authenticate.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="cb57f-136">clientCredentialType 属性</span><span class="sxs-lookup"><span data-stu-id="cb57f-136">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="cb57f-137">値</span><span class="sxs-lookup"><span data-stu-id="cb57f-137">Value</span></span>|<span data-ttu-id="cb57f-138">説明</span><span class="sxs-lookup"><span data-stu-id="cb57f-138">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="cb57f-139">なし</span><span class="sxs-lookup"><span data-stu-id="cb57f-139">None</span></span>|<span data-ttu-id="cb57f-140">クライアントは匿名です。</span><span class="sxs-lookup"><span data-stu-id="cb57f-140">The client is anonymous.</span></span> <span data-ttu-id="cb57f-141">これには、サービスの証明書が必要です。</span><span class="sxs-lookup"><span data-stu-id="cb57f-141">This requires a certificate for the service.</span></span>|  
|<span data-ttu-id="cb57f-142">Windows</span><span class="sxs-lookup"><span data-stu-id="cb57f-142">Windows</span></span>|<span data-ttu-id="cb57f-143">SP ネゴシエーション (Kerberos ネゴシエーション) を使用して、クライアントの Windows 認証を指定します。</span><span class="sxs-lookup"><span data-stu-id="cb57f-143">Specifies Windows authentication of the client using SP Negotiation (Kerberos negotiation).</span></span>|  
|<span data-ttu-id="cb57f-144">証明書</span><span class="sxs-lookup"><span data-stu-id="cb57f-144">Certificate</span></span>|<span data-ttu-id="cb57f-145">クライアントは、証明書を使用して認証されます。</span><span class="sxs-lookup"><span data-stu-id="cb57f-145">The client is authenticated using a certificate.</span></span> <span data-ttu-id="cb57f-146">これは SSL ネゴシエーションを使用し、サービスの証明書が必要です。</span><span class="sxs-lookup"><span data-stu-id="cb57f-146">This uses SSL Negotiation and requires a certificate for the service.</span></span>|  
  
## <a name="protectionlevel-attribute"></a><span data-ttu-id="cb57f-147">protectionLevel 属性</span><span class="sxs-lookup"><span data-stu-id="cb57f-147">protectionLevel Attribute</span></span>  
  
|<span data-ttu-id="cb57f-148">値</span><span class="sxs-lookup"><span data-stu-id="cb57f-148">Value</span></span>|<span data-ttu-id="cb57f-149">説明</span><span class="sxs-lookup"><span data-stu-id="cb57f-149">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="cb57f-150">なし</span><span class="sxs-lookup"><span data-stu-id="cb57f-150">None</span></span>|<span data-ttu-id="cb57f-151">保護されません。</span><span class="sxs-lookup"><span data-stu-id="cb57f-151">No protection.</span></span>|  
|<span data-ttu-id="cb57f-152">Sign</span><span class="sxs-lookup"><span data-stu-id="cb57f-152">Sign</span></span>|<span data-ttu-id="cb57f-153">メッセージは署名されます。</span><span class="sxs-lookup"><span data-stu-id="cb57f-153">Messages are signed.</span></span>|  
|<span data-ttu-id="cb57f-154">EncryptAndSign</span><span class="sxs-lookup"><span data-stu-id="cb57f-154">EncryptAndSign</span></span>|<span data-ttu-id="cb57f-155">メッセージの数が、暗号化および署名されます。</span><span class="sxs-lookup"><span data-stu-id="cb57f-155">-   Messages are encrypted and signed.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cb57f-156">子要素</span><span class="sxs-lookup"><span data-stu-id="cb57f-156">Child Elements</span></span>  
 <span data-ttu-id="cb57f-157">なし</span><span class="sxs-lookup"><span data-stu-id="cb57f-157">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="cb57f-158">親要素</span><span class="sxs-lookup"><span data-stu-id="cb57f-158">Parent Elements</span></span>  
  
|<span data-ttu-id="cb57f-159">要素</span><span class="sxs-lookup"><span data-stu-id="cb57f-159">Element</span></span>|<span data-ttu-id="cb57f-160">説明</span><span class="sxs-lookup"><span data-stu-id="cb57f-160">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cb57f-161">\<security></span><span class="sxs-lookup"><span data-stu-id="cb57f-161">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-nettcpbinding.md)|<span data-ttu-id="cb57f-162">セキュリティ機能を指定します、 [ \<netTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md)します。</span><span class="sxs-lookup"><span data-stu-id="cb57f-162">Specifies the security capabilities of the [\<netTcpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cb57f-163">Remarks</span><span class="sxs-lookup"><span data-stu-id="cb57f-163">Remarks</span></span>  
 <span data-ttu-id="cb57f-164">トランスポート セキュリティは、SOAP メッセージの整合性と機密性の保護、および相互認証に使用します。</span><span class="sxs-lookup"><span data-stu-id="cb57f-164">Use Transport security for integrity and confidentiality of the SOAP message and for mutual authentication.</span></span> <span data-ttu-id="cb57f-165">このセキュリティ モードがバインディング上で選択された場合、チャネル スタックはセキュリティ トランスポートを使用して構成され、SOAP メッセージは Windows (ネゴシエート) や TCP 上の SSL などのトランスポート セキュリティを使用して保護されます。</span><span class="sxs-lookup"><span data-stu-id="cb57f-165">If this security mode is selected on a binding, the channel stack is configured using a secure transport and the SOAP messages are secured using transport security such as Windows (Negotiate) or SSL over TCP.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb57f-166">関連項目</span><span class="sxs-lookup"><span data-stu-id="cb57f-166">See also</span></span>
- <xref:System.ServiceModel.TcpTransportSecurity>
- <xref:System.ServiceModel.Configuration.NetTcpSecurityElement.Transport%2A>
- <xref:System.ServiceModel.NetTcpSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.NetTcpSecurityElement>
- [<span data-ttu-id="cb57f-167">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="cb57f-167">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="cb57f-168">バインディング</span><span class="sxs-lookup"><span data-stu-id="cb57f-168">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="cb57f-169">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="cb57f-169">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="cb57f-170">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="cb57f-170">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="cb57f-171">\<binding></span><span class="sxs-lookup"><span data-stu-id="cb57f-171">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
