---
title: <issuerMetadata>
ms.date: 03/30/2017
ms.assetid: e7eae2c0-cc17-4281-af59-e4eb8d54f92a
ms.openlocfilehash: 0dffad6a17720dd0506acbcd60efe4aafe24ed28
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59090109"
---
# <a name="issuermetadata"></a><span data-ttu-id="f61f2-101">\<issuerMetadata ></span><span class="sxs-lookup"><span data-stu-id="f61f2-101">\<issuerMetadata></span></span>
<span data-ttu-id="f61f2-102">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="f61f2-102">\<system.serviceModel></span></span>  
<span data-ttu-id="f61f2-103">\<bindings></span><span class="sxs-lookup"><span data-stu-id="f61f2-103">\<bindings></span></span>  
<span data-ttu-id="f61f2-104">\<wsFederationHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="f61f2-104">\<wsFederationHttpBinding></span></span>  
<span data-ttu-id="f61f2-105">\<binding></span><span class="sxs-lookup"><span data-stu-id="f61f2-105">\<binding></span></span>  
<span data-ttu-id="f61f2-106">\<セキュリティ ></span><span class="sxs-lookup"><span data-stu-id="f61f2-106">\<security></span></span>  
<span data-ttu-id="f61f2-107">\<message></span><span class="sxs-lookup"><span data-stu-id="f61f2-107">\<message></span></span>  
<span data-ttu-id="f61f2-108">\<issuerMetadata ></span><span class="sxs-lookup"><span data-stu-id="f61f2-108">\<issuerMetadata></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f61f2-109">構文</span><span class="sxs-lookup"><span data-stu-id="f61f2-109">Syntax</span></span>  
  
```xml  
<issuerMetadata address="String">
  <headers>
    <add name="String"
         namespace="String" />
  </headers>
  <identity>
    <certificate encodedValue="String" />
    <certificateReference findValue="String"
                          isChainIncluded="Boolean"
                          storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
                          storeLocation="LocalMachine/CurrentUser"
                          x509FindType="System.Security.Cryptography.X509certificates.X509findtype" />
    <dns value="String" />
    <rsa value="String" />
    <servicePrincipalName value="String" />
    <usePrincipalName value="String" />
  </identity>
</issuerMetadata>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f61f2-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="f61f2-110">Attributes and Elements</span></span>  
 <span data-ttu-id="f61f2-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="f61f2-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f61f2-112">属性</span><span class="sxs-lookup"><span data-stu-id="f61f2-112">Attributes</span></span>  
  
|<span data-ttu-id="f61f2-113">属性</span><span class="sxs-lookup"><span data-stu-id="f61f2-113">Attribute</span></span>|<span data-ttu-id="f61f2-114">説明</span><span class="sxs-lookup"><span data-stu-id="f61f2-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f61f2-115">アドレス</span><span class="sxs-lookup"><span data-stu-id="f61f2-115">address</span></span>|<span data-ttu-id="f61f2-116">必須の `string` 属性です。</span><span class="sxs-lookup"><span data-stu-id="f61f2-116">Required `string` attribute.</span></span><br /><br /> <span data-ttu-id="f61f2-117">エンドポイントのアドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="f61f2-117">Specifies the address of the endpoint.</span></span> <span data-ttu-id="f61f2-118">アドレスは、絶対 URI にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f61f2-118">The address must be an absolute URI.</span></span> <span data-ttu-id="f61f2-119">既定値は空の文字列です。</span><span class="sxs-lookup"><span data-stu-id="f61f2-119">The default value is an empty string.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f61f2-120">子要素</span><span class="sxs-lookup"><span data-stu-id="f61f2-120">Child Elements</span></span>  
  
|<span data-ttu-id="f61f2-121">要素</span><span class="sxs-lookup"><span data-stu-id="f61f2-121">Element</span></span>|<span data-ttu-id="f61f2-122">説明</span><span class="sxs-lookup"><span data-stu-id="f61f2-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f61f2-123">\<headers></span><span class="sxs-lookup"><span data-stu-id="f61f2-123">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|<span data-ttu-id="f61f2-124">アドレス ヘッダーのコレクション。</span><span class="sxs-lookup"><span data-stu-id="f61f2-124">A collection of address headers.</span></span>|  
|[<span data-ttu-id="f61f2-125">\<identity></span><span class="sxs-lookup"><span data-stu-id="f61f2-125">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="f61f2-126">メッセージを交換する他のエンドポイントによるエンドポイントの認証を可能にする ID です。</span><span class="sxs-lookup"><span data-stu-id="f61f2-126">An identity that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f61f2-127">親要素</span><span class="sxs-lookup"><span data-stu-id="f61f2-127">Parent Elements</span></span>  
  
|<span data-ttu-id="f61f2-128">要素</span><span class="sxs-lookup"><span data-stu-id="f61f2-128">Element</span></span>|<span data-ttu-id="f61f2-129">説明</span><span class="sxs-lookup"><span data-stu-id="f61f2-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f61f2-130">\<message></span><span class="sxs-lookup"><span data-stu-id="f61f2-130">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-wsfederationhttpbinding.md)|<span data-ttu-id="f61f2-131">メッセージ レベル セキュリティの設定を定義、 [ \<wsFederationHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md)要素。</span><span class="sxs-lookup"><span data-stu-id="f61f2-131">Defines the settings for the message-level security for the [\<wsFederationHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f61f2-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="f61f2-132">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.IssuerMetadataAddress%2A>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.IssuerMetadata%2A>
- [<span data-ttu-id="f61f2-133">サービス ID と認証</span><span class="sxs-lookup"><span data-stu-id="f61f2-133">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="f61f2-134">フェデレーションと発行済みトークン</span><span class="sxs-lookup"><span data-stu-id="f61f2-134">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="f61f2-135">カスタム バインドを使用したセキュリティ機能</span><span class="sxs-lookup"><span data-stu-id="f61f2-135">Security Capabilities with Custom Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="f61f2-136">フェデレーションと発行済みトークン</span><span class="sxs-lookup"><span data-stu-id="f61f2-136">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
