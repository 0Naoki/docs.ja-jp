---
title: '&lt;identity&gt;'
ms.date: 03/30/2017
ms.assetid: c1d2ae56-e231-4a07-9c3f-9f13381dc0d8
ms.openlocfilehash: 03e73f64090e0851b06ee67fe70c157b6145966c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54677358"
---
# <a name="ltidentitygt"></a><span data-ttu-id="2ca4b-102">&lt;identity&gt;</span><span class="sxs-lookup"><span data-stu-id="2ca4b-102">&lt;identity&gt;</span></span>
<span data-ttu-id="2ca4b-103">ID 要素を使用すると、クライアント開発者は予想されるサービスの ID をデザイン時に指定できます。</span><span class="sxs-lookup"><span data-stu-id="2ca4b-103">The identity element allows a client developer to specify at design time the expected identity of the service.</span></span> <span data-ttu-id="2ca4b-104">クライアントとサービス間のハンドシェイク プロセスで Windows Communication Foundation (WCF) インフラストラクチャが予期されるサービスと一致する、この要素の値の id を保証して、そのため、認証されたことができます。</span><span class="sxs-lookup"><span data-stu-id="2ca4b-104">In the handshake process between the client and service, the Windows Communication Foundation (WCF) infrastructure will ensure that the identity of the expected service matches the values of this element, and thus can be authenticated.</span></span> <span data-ttu-id="2ca4b-105">詳細については、次を参照してください。[サービス Id と認証](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)します。</span><span class="sxs-lookup"><span data-stu-id="2ca4b-105">For more information, see [Service Identity and Authentication](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
 <span data-ttu-id="2ca4b-106">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="2ca4b-106">\<system.ServiceModel></span></span>  
<span data-ttu-id="2ca4b-107">\<client></span><span class="sxs-lookup"><span data-stu-id="2ca4b-107">\<client></span></span>  
<span data-ttu-id="2ca4b-108">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="2ca4b-108">\<endpoint></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ca4b-109">構文</span><span class="sxs-lookup"><span data-stu-id="2ca4b-109">Syntax</span></span>  
  
```xml  
<identity>
  <certificate encodedValue="String" />
  <certificateReference findValue="String"
                        isChainIncluded="Boolean"
                        storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
                        storeLocation="LocalMachine/CurrentUser"
                        X509FindType="Enumeration" />
  <dns value="String" />
  <rsa value="String" />
  <servicePrincipalName value="String" />
  <usePrincipalName value="String" />
</identity>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2ca4b-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="2ca4b-110">Attributes and Elements</span></span>  
 <span data-ttu-id="2ca4b-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="2ca4b-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2ca4b-112">属性</span><span class="sxs-lookup"><span data-stu-id="2ca4b-112">Attributes</span></span>  
 <span data-ttu-id="2ca4b-113">なし。</span><span class="sxs-lookup"><span data-stu-id="2ca4b-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="2ca4b-114">子要素</span><span class="sxs-lookup"><span data-stu-id="2ca4b-114">Child Elements</span></span>  
  
|<span data-ttu-id="2ca4b-115">要素</span><span class="sxs-lookup"><span data-stu-id="2ca4b-115">Element</span></span>|<span data-ttu-id="2ca4b-116">説明</span><span class="sxs-lookup"><span data-stu-id="2ca4b-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2ca4b-117">certificate</span><span class="sxs-lookup"><span data-stu-id="2ca4b-117">certificate</span></span>|<span data-ttu-id="2ca4b-118">X.509 証明書の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="2ca4b-118">Specifies settings of an X.509 certificate.</span></span> <span data-ttu-id="2ca4b-119">この要素は <xref:System.ServiceModel.Configuration.CertificateElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="2ca4b-119">This element is of type <xref:System.ServiceModel.Configuration.CertificateElement>.</span></span> <span data-ttu-id="2ca4b-120">この要素には、この証明書でエンコードされる値を指定する文字列の `encodedValue` 属性が含まれています。</span><span class="sxs-lookup"><span data-stu-id="2ca4b-120">It contains an attribute `encodedValue` that is a string, which specifies the value encoded by this certificate.</span></span>|  
|<span data-ttu-id="2ca4b-121">certificateReference</span><span class="sxs-lookup"><span data-stu-id="2ca4b-121">certificateReference</span></span>|<span data-ttu-id="2ca4b-122">X.509 証明書検証の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="2ca4b-122">Specifies settings for X.509 certificate validation.</span></span> <span data-ttu-id="2ca4b-123">この要素は <xref:System.ServiceModel.Configuration.CertificateReferenceElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="2ca4b-123">This element is of type <xref:System.ServiceModel.Configuration.CertificateReferenceElement>.</span></span>|  
|<span data-ttu-id="2ca4b-124">dns</span><span class="sxs-lookup"><span data-stu-id="2ca4b-124">dns</span></span>|<span data-ttu-id="2ca4b-125">サービスの認証に使用される X.509 証明書の DNS を指定します。</span><span class="sxs-lookup"><span data-stu-id="2ca4b-125">Specifies the DNS of an X.509 certificate used to authenticate a service.</span></span> <span data-ttu-id="2ca4b-126">この要素には、実際の ID を含む文字列の `value` 属性が含まれています。</span><span class="sxs-lookup"><span data-stu-id="2ca4b-126">This element contains an attribute `value` that is a string, and contains the actual identity.</span></span>|  
|<span data-ttu-id="2ca4b-127">rsa</span><span class="sxs-lookup"><span data-stu-id="2ca4b-127">rsa</span></span>|<span data-ttu-id="2ca4b-128">クライアントに対するサービスの認証に使用される X.509 証明書の RSA フィールドの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="2ca4b-128">Specifies the value of the RSA field of an X.509 certificate used to authenticate a service to a client.</span></span> <span data-ttu-id="2ca4b-129">この要素には、実際の ID を含む文字列の `value` 属性が含まれています</span><span class="sxs-lookup"><span data-stu-id="2ca4b-129">This element contains an attribute `value` that is a string, and contains the actual identity</span></span>|  
|<span data-ttu-id="2ca4b-130">servicePrincipalName</span><span class="sxs-lookup"><span data-stu-id="2ca4b-130">servicePrincipalName</span></span>|<span data-ttu-id="2ca4b-131">サーバー プリンシパル名 (SPN) ID を指定します。これは、サービスのインスタンスを一意に識別するために、クライアントにより使用されるプリンシパル名です。</span><span class="sxs-lookup"><span data-stu-id="2ca4b-131">Specifies a server principal name (SPN) identity, which is the principal name used by a client to uniquely identify an instance of a service.</span></span> <span data-ttu-id="2ca4b-132">この要素には、実際のプリンシパル名が文字列で含まれている `value` 属性が含まれています。</span><span class="sxs-lookup"><span data-stu-id="2ca4b-132">This element contains an attribute `value` that is a string, and contains the actual principal name.</span></span> <span data-ttu-id="2ca4b-133">この要素は <xref:System.ServiceModel.Configuration.ServicePrincipalNameElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="2ca4b-133">This element is of type <xref:System.ServiceModel.Configuration.ServicePrincipalNameElement>.</span></span>|  
|<span data-ttu-id="2ca4b-134">userPrincipalName</span><span class="sxs-lookup"><span data-stu-id="2ca4b-134">userPrincipalName</span></span>|<span data-ttu-id="2ca4b-135">ユーザー プリンシパル名 (UPN) ID を指定します。これは、ネットワーク上のユーザーのログオン名の種類です。</span><span class="sxs-lookup"><span data-stu-id="2ca4b-135">Specifies a user principal name (UPN) identity, which is the logon name type of a user on a network.</span></span> <span data-ttu-id="2ca4b-136">ユーザー プリンシパル名から成る後に、Active Directory で使用されるユーザー オブジェクト名、アット マーク (\@) およびドメインを親通常は、次に、ドメイン ネーム システム。</span><span class="sxs-lookup"><span data-stu-id="2ca4b-136">The user principal name consists of the user object name used in Active Directory, followed by the at symbol (\@) and then, typically, the Domain Name System parent domain.</span></span> <span data-ttu-id="2ca4b-137">たとえば、Fabrikam.com ドメイン ツリーの Jeff のユーザー プリンシパル名がある[ jeff@fabrikam.com](mailto:jeffsmith@fabrikam.com)します。</span><span class="sxs-lookup"><span data-stu-id="2ca4b-137">For example, Jeff in the Fabrikam.com domain tree might have the user principal name [jeff@fabrikam.com](mailto:jeffsmith@fabrikam.com).</span></span>  <span data-ttu-id="2ca4b-138">この要素には、実際のプリンシパル名が文字列で含まれている `value` 属性が含まれています。</span><span class="sxs-lookup"><span data-stu-id="2ca4b-138">This element contains an attribute `value` that is a string, and contains the actual principal name.</span></span> <span data-ttu-id="2ca4b-139">この要素は <xref:System.ServiceModel.Configuration.UserPrincipalNameElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="2ca4b-139">This element is of type <xref:System.ServiceModel.Configuration.UserPrincipalNameElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2ca4b-140">親要素</span><span class="sxs-lookup"><span data-stu-id="2ca4b-140">Parent Elements</span></span>  
  
|<span data-ttu-id="2ca4b-141">要素</span><span class="sxs-lookup"><span data-stu-id="2ca4b-141">Element</span></span>|<span data-ttu-id="2ca4b-142">説明</span><span class="sxs-lookup"><span data-stu-id="2ca4b-142">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2ca4b-143">\<custom></span><span class="sxs-lookup"><span data-stu-id="2ca4b-143">\<custom></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custom.md)|<span data-ttu-id="2ca4b-144">netPeerTcpBinding のカスタム ピア リゾルバーを指定します。</span><span class="sxs-lookup"><span data-stu-id="2ca4b-144">Specifies a custom peer resolver for a netPeerTcpBinding.</span></span>|  
|[<span data-ttu-id="2ca4b-145">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="2ca4b-145">\<endpoint></span></span>](https://msdn.microsoft.com/library/13aa23b7-2f08-4add-8dbf-a99f8127c017)|<span data-ttu-id="2ca4b-146">さまざまなタイプのエンドポイントを設定します。</span><span class="sxs-lookup"><span data-stu-id="2ca4b-146">Configures different types of endpoints.</span></span>|  
|[<span data-ttu-id="2ca4b-147">\<issuer></span><span class="sxs-lookup"><span data-stu-id="2ca4b-147">\<issuer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuer.md)|<span data-ttu-id="2ca4b-148">フェデレーション サービスのセキュリティ トークン サービス (STS) を指定します。</span><span class="sxs-lookup"><span data-stu-id="2ca4b-148">Specifies the Security Token Service (STS) for the federated service.</span></span>|  
|[<span data-ttu-id="2ca4b-149">\<issuerMetadata></span><span class="sxs-lookup"><span data-stu-id="2ca4b-149">\<issuerMetadata></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuermetadata.md)|<span data-ttu-id="2ca4b-150">フェデレーション サービスのセキュリティ トークン サービス (STS) のメタデータ エンドポイントを指定します。</span><span class="sxs-lookup"><span data-stu-id="2ca4b-150">Specifies the metadata endpoint for the Security Token Service (STS) of a federated service.</span></span>|  
|[<span data-ttu-id="2ca4b-151">\<issuedTokenParameters></span><span class="sxs-lookup"><span data-stu-id="2ca4b-151">\<issuedTokenParameters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenparameters.md)|<span data-ttu-id="2ca4b-152">カスタム バインドで発行済みトークンのパラメーターを定義します。</span><span class="sxs-lookup"><span data-stu-id="2ca4b-152">Defines parameters for an issued token in a custom binding.</span></span>|  
|[<span data-ttu-id="2ca4b-153">\<localIssuer></span><span class="sxs-lookup"><span data-stu-id="2ca4b-153">\<localIssuer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/localissuer.md)|<span data-ttu-id="2ca4b-154">ローカル セキュリティ トークン サービス (STS) を指定します。</span><span class="sxs-lookup"><span data-stu-id="2ca4b-154">Specifies a local Security Token Service (STS).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2ca4b-155">関連項目</span><span class="sxs-lookup"><span data-stu-id="2ca4b-155">See also</span></span>
- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- [<span data-ttu-id="2ca4b-156">サービス ID と認証</span><span class="sxs-lookup"><span data-stu-id="2ca4b-156">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="2ca4b-157">エンドポイント:アドレス、バインディング、およびコントラクト</span><span class="sxs-lookup"><span data-stu-id="2ca4b-157">Endpoints: Addresses, Bindings, and Contracts</span></span>](../../../../../docs/framework/wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)
