---
title: <add> (行中)  <allowedAudienceUris>
ms.date: 03/30/2017
ms.assetid: 4e7b7637-e0ea-4a91-988f-6b6ef28d9fc3
ms.openlocfilehash: a3ad50462cfa268a1826b62603110be3c5ba33db
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59148279"
---
# <a name="add-of-allowedaudienceuris"></a><span data-ttu-id="0358e-102">\<add> of \<allowedAudienceUris></span><span class="sxs-lookup"><span data-stu-id="0358e-102">\<add> of \<allowedAudienceUris></span></span>
<span data-ttu-id="0358e-103"><xref:System.IdentityModel.Tokens.SamlSecurityToken> インスタンスにより有効と見なされるように、<xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> セキュリティ トークンのターゲットとなる URI を追加します。</span><span class="sxs-lookup"><span data-stu-id="0358e-103">Adds a target Uri for which the <xref:System.IdentityModel.Tokens.SamlSecurityToken> security token can be targeted for in order to be considered valid by a <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> instance.</span></span>  
  
 <span data-ttu-id="0358e-104">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="0358e-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="0358e-105">\<<behaviors></span><span class="sxs-lookup"><span data-stu-id="0358e-105">\<behaviors></span></span>  
<span data-ttu-id="0358e-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="0358e-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="0358e-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="0358e-107">\<behavior></span></span>  
<span data-ttu-id="0358e-108">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="0358e-108">\<serviceCredentials></span></span>  
<span data-ttu-id="0358e-109">\<issuedTokenAuthentication></span><span class="sxs-lookup"><span data-stu-id="0358e-109">\<issuedTokenAuthentication></span></span>  
<span data-ttu-id="0358e-110">\<allowedAudienceUris></span><span class="sxs-lookup"><span data-stu-id="0358e-110">\<allowedAudienceUris></span></span>  
<span data-ttu-id="0358e-111">\<追加 > 要素の\<allowedAudienceUris ></span><span class="sxs-lookup"><span data-stu-id="0358e-111">\<add> element for \<allowedAudienceUris></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0358e-112">構文</span><span class="sxs-lookup"><span data-stu-id="0358e-112">Syntax</span></span>  
  
```xml  
<allowedAudienceUris>
  <add allowedAudienceUri="String" />
</allowedAudienceUris>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0358e-113">属性および要素</span><span class="sxs-lookup"><span data-stu-id="0358e-113">Attributes and Elements</span></span>  
 <span data-ttu-id="0358e-114">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="0358e-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0358e-115">属性</span><span class="sxs-lookup"><span data-stu-id="0358e-115">Attributes</span></span>  
  
|<span data-ttu-id="0358e-116">属性</span><span class="sxs-lookup"><span data-stu-id="0358e-116">Attribute</span></span>|<span data-ttu-id="0358e-117">説明</span><span class="sxs-lookup"><span data-stu-id="0358e-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0358e-118">allowedAudienceUri</span><span class="sxs-lookup"><span data-stu-id="0358e-118">allowedAudienceUri</span></span>|<span data-ttu-id="0358e-119"><xref:System.IdentityModel.Tokens.SamlSecurityToken> インスタンスにより有効と見なされるように、<xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> セキュリティ トークンのターゲットとなる URI を含む文字列です。</span><span class="sxs-lookup"><span data-stu-id="0358e-119">A string that contains a target Uri for which the <xref:System.IdentityModel.Tokens.SamlSecurityToken> security token can be targeted for in order to be considered valid by a <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> instance.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0358e-120">子要素</span><span class="sxs-lookup"><span data-stu-id="0358e-120">Child Elements</span></span>  
 <span data-ttu-id="0358e-121">なし。</span><span class="sxs-lookup"><span data-stu-id="0358e-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0358e-122">親要素</span><span class="sxs-lookup"><span data-stu-id="0358e-122">Parent Elements</span></span>  
  
|<span data-ttu-id="0358e-123">要素</span><span class="sxs-lookup"><span data-stu-id="0358e-123">Element</span></span>|<span data-ttu-id="0358e-124">説明</span><span class="sxs-lookup"><span data-stu-id="0358e-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0358e-125">\<allowedAudienceUris></span><span class="sxs-lookup"><span data-stu-id="0358e-125">\<allowedAudienceUris></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/allowedaudienceuris.md)|<span data-ttu-id="0358e-126"><xref:System.IdentityModel.Tokens.SamlSecurityToken> インスタンスにより有効と見なされるように、<xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> セキュリティ トークンのターゲットとなる URI のコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="0358e-126">Represents a collection of target URIs for which the <xref:System.IdentityModel.Tokens.SamlSecurityToken> security token can be targeted for in order to be considered valid by a <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> instance.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0358e-127">Remarks</span><span class="sxs-lookup"><span data-stu-id="0358e-127">Remarks</span></span>  
 <span data-ttu-id="0358e-128">このコレクションは、<xref:System.IdentityModel.Tokens.SamlSecurityToken> セキュリティ トークンを発行するセキュリティ トークン サービス (STS) を利用するフェデレーション アプリケーションで使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0358e-128">You should use this collection in a federated application that utilizes a security token service (STS) that issues <xref:System.IdentityModel.Tokens.SamlSecurityToken> security tokens.</span></span> <span data-ttu-id="0358e-129">STS がセキュリティ トークンを発行する場合、このセキュリティ トークンに <xref:System.IdentityModel.Tokens.SamlAudienceRestrictionCondition> を追加して、セキュリティ トークンの提供先となる Web サービスの URI を指定できます。</span><span class="sxs-lookup"><span data-stu-id="0358e-129">When the STS issues the security token, it can specify the URI of the Web services for which the security token is intended by adding a <xref:System.IdentityModel.Tokens.SamlAudienceRestrictionCondition> to the security token.</span></span> <span data-ttu-id="0358e-130">これにより、受け取り側 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> Web サービスは、次のようにしてこのチェックが行われるように指定することで、発行されたセキュリティ トークンがこの Web サービスを対象としていることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="0358e-130">That allows the <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> for the recipient Web service to verify that the issued security token is intended for this Web service by specifying that this check should happen by doing the following:</span></span>  
  
-   <span data-ttu-id="0358e-131">`audienceUriMode` の `<issuedTokenAuthentication>` 属性を <xref:System.IdentityModel.Selectors.AudienceUriMode.Always> または <xref:System.IdentityModel.Selectors.AudienceUriMode.BearerKeyOnly> に設定します。</span><span class="sxs-lookup"><span data-stu-id="0358e-131">Set the `audienceUriMode` attribute of `<issuedTokenAuthentication>` to <xref:System.IdentityModel.Selectors.AudienceUriMode.Always> or <xref:System.IdentityModel.Selectors.AudienceUriMode.BearerKeyOnly>.</span></span>  
  
-   <span data-ttu-id="0358e-132">このコレクションに URI を追加して、有効な URI のセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="0358e-132">Specify the set of valid URIs, by adding the URIs to this collection.</span></span>  
  
 <span data-ttu-id="0358e-133">詳細については、「 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0358e-133">For more information, see <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>.</span></span>  
  
 <span data-ttu-id="0358e-134">この構成要素の使用に関する詳細については、次を参照してください。[方法。フェデレーション サービスで資格情報を構成](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)します。</span><span class="sxs-lookup"><span data-stu-id="0358e-134">For more information on using this configuration element, see [How to: Configure Credentials on a Federation Service](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0358e-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="0358e-135">See also</span></span>

- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement.AllowedAudienceUris%2A>
- <xref:System.ServiceModel.Configuration.AllowedAudienceUriElementCollection>
- <xref:System.ServiceModel.Configuration.AllowedAudienceUriElement>
- <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.AllowedAudienceUris%2A>
- [<span data-ttu-id="0358e-136">\<allowedAudienceUris></span><span class="sxs-lookup"><span data-stu-id="0358e-136">\<allowedAudienceUris></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/allowedaudienceuris.md)
- [<span data-ttu-id="0358e-137">\<issuedTokenAuthentication></span><span class="sxs-lookup"><span data-stu-id="0358e-137">\<issuedTokenAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md)
- [<span data-ttu-id="0358e-138">セキュリティ動作</span><span class="sxs-lookup"><span data-stu-id="0358e-138">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="0358e-139">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="0358e-139">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="0358e-140">方法: フェデレーション サービスで資格情報を設定する</span><span class="sxs-lookup"><span data-stu-id="0358e-140">How to: Configure Credentials on a Federation Service</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)
