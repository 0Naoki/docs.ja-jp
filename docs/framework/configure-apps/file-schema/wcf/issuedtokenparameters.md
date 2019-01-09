---
title: '&lt;issuedTokenParameters&gt;'
ms.date: 03/30/2017
ms.assetid: 120b3f37-7331-4816-b712-d6aab39655a4
ms.openlocfilehash: 2060f98e94cec9e656420ac073204a82bc592b92
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/09/2019
ms.locfileid: "54149242"
---
# <a name="ltissuedtokenparametersgt"></a><span data-ttu-id="befb3-102">&lt;issuedTokenParameters&gt;</span><span class="sxs-lookup"><span data-stu-id="befb3-102">&lt;issuedTokenParameters&gt;</span></span>
<span data-ttu-id="befb3-103">フェデレーション セキュリティのシナリオで発行されるセキュリティ トークンのパラメーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="befb3-103">Specifies the parameters for a security token issued in a Federated security scenario.</span></span>  
  
 <span data-ttu-id="befb3-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="befb3-104">\<system.serviceModel></span></span>  
<span data-ttu-id="befb3-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="befb3-105">\<bindings></span></span>  
<span data-ttu-id="befb3-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="befb3-106">\<customBinding></span></span>  
<span data-ttu-id="befb3-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="befb3-107">\<binding></span></span>  
<span data-ttu-id="befb3-108">\<セキュリティ ></span><span class="sxs-lookup"><span data-stu-id="befb3-108">\<security></span></span>  
<span data-ttu-id="befb3-109">\<issuedTokenParameters ></span><span class="sxs-lookup"><span data-stu-id="befb3-109">\<issuedTokenParameters></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="befb3-110">構文</span><span class="sxs-lookup"><span data-stu-id="befb3-110">Syntax</span></span>  
  
```xml  
<issuedTokenParameters defaultMessageSecurityVersion="System.ServiceModel.MessageSecurityVersion"
                       inclusionMode="AlwaysToInitiator/AlwaysToRecipient/Never/Once"
                       keySize="Integer"
                       keyType="AsymmetricKey/BearerKey/SymmetricKey"
                       tokenType="String">
  <additionalRequestParameters />
  <claimTypeRequirements>
    <add claimType="URI"
         isOptional="Boolean" />
  </claimTypeRequirements>
  <issuer address="String"
          binding="" />
  <issuerMetadata address="String" />
</issuedTokenParameters>
```  
  
## <a name="type"></a><span data-ttu-id="befb3-111">型</span><span class="sxs-lookup"><span data-stu-id="befb3-111">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="befb3-112">属性および要素</span><span class="sxs-lookup"><span data-stu-id="befb3-112">Attributes and Elements</span></span>  
 <span data-ttu-id="befb3-113">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="befb3-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="befb3-114">属性</span><span class="sxs-lookup"><span data-stu-id="befb3-114">Attributes</span></span>  
  
|<span data-ttu-id="befb3-115">属性</span><span class="sxs-lookup"><span data-stu-id="befb3-115">Attribute</span></span>|<span data-ttu-id="befb3-116">説明</span><span class="sxs-lookup"><span data-stu-id="befb3-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="befb3-117">defaultMessageSecurityVersion</span><span class="sxs-lookup"><span data-stu-id="befb3-117">defaultMessageSecurityVersion</span></span>|<span data-ttu-id="befb3-118">バインドでサポートする必要があるセキュリティ仕様 (WS-Security、WS-Trust、WS-Secure Conversation、および WS-Security Policy) のバージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="befb3-118">Specifies the versions of the security specifications, (WS-Security, WS-Trust, WS-Secure Conversation and WS-Security Policy) that must be supported by the binding.</span></span> <span data-ttu-id="befb3-119">この値は、<xref:System.ServiceModel.MessageSecurityVersion> 型です。</span><span class="sxs-lookup"><span data-stu-id="befb3-119">This value is of type <xref:System.ServiceModel.MessageSecurityVersion>.</span></span>|  
|<span data-ttu-id="befb3-120">inclusionMode</span><span class="sxs-lookup"><span data-stu-id="befb3-120">inclusionMode</span></span>|<span data-ttu-id="befb3-121">トークン包含要件を指定します。</span><span class="sxs-lookup"><span data-stu-id="befb3-121">Specifies the token inclusion requirements.</span></span> <span data-ttu-id="befb3-122">この属性は <xref:System.ServiceModel.Security.Tokens.SecurityTokenInclusionMode> 型です。</span><span class="sxs-lookup"><span data-stu-id="befb3-122">This attribute is of type <xref:System.ServiceModel.Security.Tokens.SecurityTokenInclusionMode>.</span></span>|  
|<span data-ttu-id="befb3-123">keySize</span><span class="sxs-lookup"><span data-stu-id="befb3-123">keySize</span></span>|<span data-ttu-id="befb3-124">トークン キー サイズを指定する整数。</span><span class="sxs-lookup"><span data-stu-id="befb3-124">An integer that specifies the token key size.</span></span> <span data-ttu-id="befb3-125">既定値は 256 です。</span><span class="sxs-lookup"><span data-stu-id="befb3-125">The default value is 256.</span></span>|  
|<span data-ttu-id="befb3-126">keyType</span><span class="sxs-lookup"><span data-stu-id="befb3-126">keyType</span></span>|<span data-ttu-id="befb3-127">キーの型を指定する <xref:System.IdentityModel.Tokens.SecurityKeyType> の有効な値。</span><span class="sxs-lookup"><span data-stu-id="befb3-127">A valid value of <xref:System.IdentityModel.Tokens.SecurityKeyType> that specifies the key type.</span></span> <span data-ttu-id="befb3-128">既定値は、`SymmetricKey` です。</span><span class="sxs-lookup"><span data-stu-id="befb3-128">The default is `SymmetricKey`.</span></span>|  
|<span data-ttu-id="befb3-129">tokenType</span><span class="sxs-lookup"><span data-stu-id="befb3-129">tokenType</span></span>|<span data-ttu-id="befb3-130">トークンの種類を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="befb3-130">A string that specifies the token type.</span></span> <span data-ttu-id="befb3-131">既定値は "http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAML" です。</span><span class="sxs-lookup"><span data-stu-id="befb3-131">The default is "http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAML".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="befb3-132">子要素</span><span class="sxs-lookup"><span data-stu-id="befb3-132">Child Elements</span></span>  
  
|<span data-ttu-id="befb3-133">要素</span><span class="sxs-lookup"><span data-stu-id="befb3-133">Element</span></span>|<span data-ttu-id="befb3-134">説明</span><span class="sxs-lookup"><span data-stu-id="befb3-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="befb3-135">\<additionalRequestParameters ></span><span class="sxs-lookup"><span data-stu-id="befb3-135">\<additionalRequestParameters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/additionalrequestparameters-element.md)|<span data-ttu-id="befb3-136">追加の要求パラメーターを指定する構成要素のコレクション。</span><span class="sxs-lookup"><span data-stu-id="befb3-136">A collection of configuration elements that specify additional request parameters.</span></span>|  
|[<span data-ttu-id="befb3-137">\<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="befb3-137">\<claimTypeRequirements></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/claimtyperequirements-element.md)|<span data-ttu-id="befb3-138">必須のクレームの種類のコレクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="befb3-138">Specifies a collection of required claim types.</span></span><br /><br /> <span data-ttu-id="befb3-139">フェデレーション シナリオでは、サービスが受信資格情報についての要件を記述します。</span><span class="sxs-lookup"><span data-stu-id="befb3-139">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="befb3-140">たとえば、受信資格情報は、特定のクレーム タイプのセットを処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="befb3-140">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="befb3-141">このコレクションの要素はそれぞれ、フェデレーション資格情報に表示されると予想される必須の要求および省略可能な要求の種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="befb3-141">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
|[<span data-ttu-id="befb3-142">\<issuer></span><span class="sxs-lookup"><span data-stu-id="befb3-142">\<issuer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuer-of-issuedtokenparameters.md)|<span data-ttu-id="befb3-143">現在のトークンを発行するエンドポイントを指定する構成要素。</span><span class="sxs-lookup"><span data-stu-id="befb3-143">A configuration element that specifies the endpoint that issues the current token.</span></span>|  
|[<span data-ttu-id="befb3-144">\<issuerMetadata></span><span class="sxs-lookup"><span data-stu-id="befb3-144">\<issuerMetadata></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuermetadata-of-issuedtokenparameters.md)|<span data-ttu-id="befb3-145">トークン発行者のメタデータのエンドポイント アドレスを指定する構成要素。</span><span class="sxs-lookup"><span data-stu-id="befb3-145">A configuration element that specifies the endpoint address of the token issuer's metadata.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="befb3-146">親要素</span><span class="sxs-lookup"><span data-stu-id="befb3-146">Parent Elements</span></span>  
  
|<span data-ttu-id="befb3-147">要素</span><span class="sxs-lookup"><span data-stu-id="befb3-147">Element</span></span>|<span data-ttu-id="befb3-148">説明</span><span class="sxs-lookup"><span data-stu-id="befb3-148">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="befb3-149">\<secureConversationBootstrap ></span><span class="sxs-lookup"><span data-stu-id="befb3-149">\<secureConversationBootstrap></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md)|<span data-ttu-id="befb3-150">セキュリティで保護されたメッセージ交換サービスの開始に使用される既定値を指定します。</span><span class="sxs-lookup"><span data-stu-id="befb3-150">Specifies the default values used for initiating a secure conversation service.</span></span>|  
|[<span data-ttu-id="befb3-151">\<security></span><span class="sxs-lookup"><span data-stu-id="befb3-151">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)|<span data-ttu-id="befb3-152">カスタム バインドのセキュリティ オプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="befb3-152">Specifies the security options for a custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="befb3-153">関連項目</span><span class="sxs-lookup"><span data-stu-id="befb3-153">See Also</span></span>  
 <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters>  
 <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement>  
 <xref:System.ServiceModel.Configuration.SecurityElementBase.IssuedTokenParameters%2A>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="befb3-154">バインディング</span><span class="sxs-lookup"><span data-stu-id="befb3-154">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="befb3-155">バインディングの拡張</span><span class="sxs-lookup"><span data-stu-id="befb3-155">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="befb3-156">カスタム バインディング</span><span class="sxs-lookup"><span data-stu-id="befb3-156">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="befb3-157">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="befb3-157">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)  
 [<span data-ttu-id="befb3-158">方法: SecurityBindingElement を使用してカスタム バインディングを作成します。</span><span class="sxs-lookup"><span data-stu-id="befb3-158">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)  
 [<span data-ttu-id="befb3-159">カスタム バインド セキュリティ</span><span class="sxs-lookup"><span data-stu-id="befb3-159">Custom Binding Security</span></span>](../../../../../docs/framework/wcf/samples/custom-binding-security.md)  
 [<span data-ttu-id="befb3-160">サービス ID と認証</span><span class="sxs-lookup"><span data-stu-id="befb3-160">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="befb3-161">フェデレーションと発行済みトークン</span><span class="sxs-lookup"><span data-stu-id="befb3-161">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="befb3-162">カスタム バインドを使用したセキュリティ機能</span><span class="sxs-lookup"><span data-stu-id="befb3-162">Security Capabilities with Custom Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)  
 [<span data-ttu-id="befb3-163">フェデレーションと発行済みトークン</span><span class="sxs-lookup"><span data-stu-id="befb3-163">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
