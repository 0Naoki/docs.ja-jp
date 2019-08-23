---
title: <transport> の <webHttpBinding>
ms.date: 03/30/2017
ms.assetid: f150fb19-7de1-44af-81f4-86cad881cd05
ms.openlocfilehash: f78add5397644dc40bfd22f10bd84aa5c5eb29e6
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69923212"
---
# <a name="transport-of-webhttpbinding"></a><span data-ttu-id="aa3c5-102">\<webHttpBinding の\<トランスポート > ></span><span class="sxs-lookup"><span data-stu-id="aa3c5-102">\<transport> of \<webHttpBinding></span></span>
<span data-ttu-id="aa3c5-103">HTTP 要求を受信するように構成されたサービス エンドポイントのトランスポート レベルのセキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="aa3c5-103">Defines the transport-level security settings for a service endpoint configured to receive HTTP requests.</span></span>  
  
 <span data-ttu-id="aa3c5-104">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="aa3c5-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="aa3c5-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="aa3c5-105">\<bindings></span></span>  
<span data-ttu-id="aa3c5-106">\<webHttpBinding></span><span class="sxs-lookup"><span data-stu-id="aa3c5-106">\<webHttpBinding></span></span>  
<span data-ttu-id="aa3c5-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="aa3c5-107">\<binding></span></span>  
<span data-ttu-id="aa3c5-108">\<セキュリティ ></span><span class="sxs-lookup"><span data-stu-id="aa3c5-108">\<security></span></span>  
<span data-ttu-id="aa3c5-109">\<transport></span><span class="sxs-lookup"><span data-stu-id="aa3c5-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa3c5-110">構文</span><span class="sxs-lookup"><span data-stu-id="aa3c5-110">Syntax</span></span>  
  
```xml  
<webHttpBinding>
  <binding>
    <security mode="None|Transport|Message|TransportWithMessageCredential|TransportCredentialOnly">
      <transport clientCredentialType="None|Basic|Digest|Ntlm|Windows"
                 proxyCredentialType="None|Basic|Digest|Ntlm|Windows"
                 realm="string">
        <extendedProtectionPolicy policyEnforcement="Never|WhenSupported|Always"
                                  protectionScenario="TransportSelected|TrustedProxy">
          <customServiceNames>
          </customServiceNames>
        </extendedProtectionPolicy>
      </transport>
    </security>
  </binding>
</webHttpBinding>
```  
  
## <a name="type"></a><span data-ttu-id="aa3c5-111">型</span><span class="sxs-lookup"><span data-stu-id="aa3c5-111">Type</span></span>  
 <xref:System.ServiceModel.HttpTransportSecurity>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="aa3c5-112">属性および要素</span><span class="sxs-lookup"><span data-stu-id="aa3c5-112">Attributes and Elements</span></span>  
 <span data-ttu-id="aa3c5-113">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="aa3c5-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="aa3c5-114">属性</span><span class="sxs-lookup"><span data-stu-id="aa3c5-114">Attributes</span></span>  
  
|<span data-ttu-id="aa3c5-115">属性</span><span class="sxs-lookup"><span data-stu-id="aa3c5-115">Attribute</span></span>|<span data-ttu-id="aa3c5-116">説明</span><span class="sxs-lookup"><span data-stu-id="aa3c5-116">Description</span></span>|  
|---------------|-----------------|  
|`clientCredentialType`|<span data-ttu-id="aa3c5-117">サービスに対するクライアントの認証に使用される資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="aa3c5-117">Specifies the credential used to authenticate the client to the service.</span></span> <span data-ttu-id="aa3c5-118">この属性は <xref:System.ServiceModel.HttpClientCredentialType> 型です。</span><span class="sxs-lookup"><span data-stu-id="aa3c5-118">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|  
|`proxyCredentialType`|<span data-ttu-id="aa3c5-119">ドメイン プロキシに対するクライアントの認証に使用される資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="aa3c5-119">Specifies the credential used to authenticate the client to a domain proxy.</span></span> <span data-ttu-id="aa3c5-120">この属性は <xref:System.ServiceModel.HttpProxyCredentialType> 型です。</span><span class="sxs-lookup"><span data-stu-id="aa3c5-120">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|  
|`realm`|<span data-ttu-id="aa3c5-121">ダイジェストまたは基本認証の認証レルムを指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="aa3c5-121">A string that specifies the authentication realm for digest or basic authentication.</span></span> <span data-ttu-id="aa3c5-122">既定値は空の文字列です。</span><span class="sxs-lookup"><span data-stu-id="aa3c5-122">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="aa3c5-123">認証レルムでは、少なくとも、認証を実行するホストの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="aa3c5-123">An authentication realm specifies at least the name of the host that performs the authentication.</span></span> <span data-ttu-id="aa3c5-124">アクセス権のあるユーザーのコレクションも指定できます。</span><span class="sxs-lookup"><span data-stu-id="aa3c5-124">It can also specify a collection of users that has access.</span></span> <span data-ttu-id="aa3c5-125">ユーザーは、認証レルムを照会して、複数のユーザー名およびパスワードの候補のうち、どれを使用できるかを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="aa3c5-125">A user can query the authentication realm to ascertain which one of the several possible usernames and passwords can be used.</span></span>|  
|`policyEnforcement`|<span data-ttu-id="aa3c5-126">この列挙体は、<xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> を適用するタイミングを指定します。</span><span class="sxs-lookup"><span data-stu-id="aa3c5-126">This enumeration specifies when the <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> should be enforced.</span></span><br /><br /> <span data-ttu-id="aa3c5-127">1. Never – ポリシーが適用されることはありません (拡張保護は無効になります)。</span><span class="sxs-lookup"><span data-stu-id="aa3c5-127">1.  Never – The policy is never enforced (Extended Protection is disabled).</span></span><br /><span data-ttu-id="aa3c5-128">2. WhenSupported – ポリシーが適用されるのは、クライアントが拡張保護をサポートしている場合のみです。</span><span class="sxs-lookup"><span data-stu-id="aa3c5-128">2.  WhenSupported – The policy is enforced only if the client supports Extended Protection.</span></span><br /><span data-ttu-id="aa3c5-129">3.Always – ポリシーは常に適用されます。</span><span class="sxs-lookup"><span data-stu-id="aa3c5-129">3.  Always – The policy is always enforced.</span></span> <span data-ttu-id="aa3c5-130">拡張保護をサポートしていないクライアントは認証に失敗します。</span><span class="sxs-lookup"><span data-stu-id="aa3c5-130">Clients which don’t support Extended Protection will fail to authenticate.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="aa3c5-131">clientCredentialType 属性</span><span class="sxs-lookup"><span data-stu-id="aa3c5-131">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="aa3c5-132">値</span><span class="sxs-lookup"><span data-stu-id="aa3c5-132">Value</span></span>|<span data-ttu-id="aa3c5-133">説明</span><span class="sxs-lookup"><span data-stu-id="aa3c5-133">Description</span></span>|  
|-----------|-----------------|  
|`None`|<span data-ttu-id="aa3c5-134">セキュリティを無効にします。</span><span class="sxs-lookup"><span data-stu-id="aa3c5-134">Security is disabled.</span></span>|  
|`Basic`|<span data-ttu-id="aa3c5-135">基本認証を使用します。</span><span class="sxs-lookup"><span data-stu-id="aa3c5-135">Uses basic authentication.</span></span>|  
|`Certificate`|<span data-ttu-id="aa3c5-136">X.509 証明書を使用して、クライアントを認証します。</span><span class="sxs-lookup"><span data-stu-id="aa3c5-136">Uses X.509 certificates to authenticate the client.</span></span>|  
|`Digest`|<span data-ttu-id="aa3c5-137">ダイジェスト認証を使用します。</span><span class="sxs-lookup"><span data-stu-id="aa3c5-137">Uses digest authentication.</span></span>|  
|`Ntlm`|<span data-ttu-id="aa3c5-138">Windows ドメインのフォールバックとして NTLM 認証を使用します。</span><span class="sxs-lookup"><span data-stu-id="aa3c5-138">Uses NTLM authentication as a fallback with a Windows domain.</span></span>|  
|`Windows`|<span data-ttu-id="aa3c5-139">統合 Windows 認証を使用します。</span><span class="sxs-lookup"><span data-stu-id="aa3c5-139">Uses integrated Windows authentication.</span></span>|  
  
## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="aa3c5-140">proxyCredentialType 属性</span><span class="sxs-lookup"><span data-stu-id="aa3c5-140">proxyCredentialType Attribute</span></span>  
  
|<span data-ttu-id="aa3c5-141">値</span><span class="sxs-lookup"><span data-stu-id="aa3c5-141">Value</span></span>|<span data-ttu-id="aa3c5-142">説明</span><span class="sxs-lookup"><span data-stu-id="aa3c5-142">Description</span></span>|  
|-----------|-----------------|  
|`None`|<span data-ttu-id="aa3c5-143">セキュリティを無効にします。</span><span class="sxs-lookup"><span data-stu-id="aa3c5-143">Security is disabled.</span></span>|  
|`Basic`|<span data-ttu-id="aa3c5-144">基本認証を使用します。</span><span class="sxs-lookup"><span data-stu-id="aa3c5-144">Uses basic authentication.</span></span>|  
|`Digest`|<span data-ttu-id="aa3c5-145">ダイジェスト認証を使用します。</span><span class="sxs-lookup"><span data-stu-id="aa3c5-145">Uses digest authentication.</span></span>|  
|`Ntlm`|<span data-ttu-id="aa3c5-146">Windows ドメインのフォールバックとして NTLM を使用します。</span><span class="sxs-lookup"><span data-stu-id="aa3c5-146">Uses NTLM as a fallback with a Windows domain.</span></span>|  
|`Windows`|<span data-ttu-id="aa3c5-147">統合 Windows 認証を使用します。</span><span class="sxs-lookup"><span data-stu-id="aa3c5-147">Uses integrated Windows authentication.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="aa3c5-148">子要素</span><span class="sxs-lookup"><span data-stu-id="aa3c5-148">Child Elements</span></span>  
 <span data-ttu-id="aa3c5-149">なし。</span><span class="sxs-lookup"><span data-stu-id="aa3c5-149">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="aa3c5-150">親要素</span><span class="sxs-lookup"><span data-stu-id="aa3c5-150">Parent Elements</span></span>  
  
|<span data-ttu-id="aa3c5-151">要素</span><span class="sxs-lookup"><span data-stu-id="aa3c5-151">Element</span></span>|<span data-ttu-id="aa3c5-152">説明</span><span class="sxs-lookup"><span data-stu-id="aa3c5-152">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="aa3c5-153">\<security></span><span class="sxs-lookup"><span data-stu-id="aa3c5-153">\<security></span></span>](security-of-webhttpbinding.md)|<span data-ttu-id="aa3c5-154">WsHttpBinding > 要素の[ \<](wshttpbinding.md)セキュリティ機能を表します。</span><span class="sxs-lookup"><span data-stu-id="aa3c5-154">Represents the security capabilities of the [\<wsHttpBinding>](wshttpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="aa3c5-155">関連項目</span><span class="sxs-lookup"><span data-stu-id="aa3c5-155">See also</span></span>

- <xref:System.ServiceModel.HttpTransportSecurity>
- <xref:System.ServiceModel.Configuration.WebHttpSecurityElement.Transport%2A>
- <xref:System.ServiceModel.WebHttpSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>
- [<span data-ttu-id="aa3c5-156">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="aa3c5-156">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="aa3c5-157">バインディング</span><span class="sxs-lookup"><span data-stu-id="aa3c5-157">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="aa3c5-158">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="aa3c5-158">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="aa3c5-159">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="aa3c5-159">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="aa3c5-160">\<binding></span><span class="sxs-lookup"><span data-stu-id="aa3c5-160">\<binding></span></span>](../../../misc/binding.md)
- [<span data-ttu-id="aa3c5-161">WCF Web HTTP プログラミング モデル</span><span class="sxs-lookup"><span data-stu-id="aa3c5-161">WCF Web HTTP Programming Model</span></span>](../../../wcf/feature-details/wcf-web-http-programming-model.md)
