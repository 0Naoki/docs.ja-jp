---
title: '&lt;claimTypeRequirements&gt; の &lt;add&gt;'
ms.date: 03/30/2017
ms.assetid: c68e83c9-39e8-4264-b1ce-b6a9eb5b98aa
ms.openlocfilehash: 5d4f0cd71ab9bf69921704300018207c9f7af107
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/09/2019
ms.locfileid: "54145212"
---
# <a name="ltaddgt-of-ltclaimtyperequirementsgt"></a><span data-ttu-id="c0a10-102">&lt;claimTypeRequirements&gt; の &lt;add&gt;</span><span class="sxs-lookup"><span data-stu-id="c0a10-102">&lt;add&gt; of &lt;claimTypeRequirements&gt;</span></span>
<span data-ttu-id="c0a10-103">フェデレーション資格情報に表示されると予想される必須のクレームおよび省略可能なクレームの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="c0a10-103">Specifies the types of required and optional claims expected to appear in the federated credential.</span></span> <span data-ttu-id="c0a10-104">たとえば、サービスは、クレームの種類の特定のセットを処理する必要がある受信資格情報について要件を記述します。</span><span class="sxs-lookup"><span data-stu-id="c0a10-104">For example, services state the requirements on incoming credentials, which must possess a certain set of claim types.</span></span>  
  
 <span data-ttu-id="c0a10-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="c0a10-105">\<system.serviceModel></span></span>  
<span data-ttu-id="c0a10-106">\<bindings></span><span class="sxs-lookup"><span data-stu-id="c0a10-106">\<bindings></span></span>  
<span data-ttu-id="c0a10-107">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="c0a10-107">\<customBinding></span></span>  
<span data-ttu-id="c0a10-108">\<binding></span><span class="sxs-lookup"><span data-stu-id="c0a10-108">\<binding></span></span>  
<span data-ttu-id="c0a10-109">\<セキュリティ ></span><span class="sxs-lookup"><span data-stu-id="c0a10-109">\<security></span></span>  
<span data-ttu-id="c0a10-110">\<issuedTokenParameters ></span><span class="sxs-lookup"><span data-stu-id="c0a10-110">\<issuedTokenParameters></span></span>  
<span data-ttu-id="c0a10-111">\<claimTypeRequirements ></span><span class="sxs-lookup"><span data-stu-id="c0a10-111">\<claimTypeRequirements></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0a10-112">構文</span><span class="sxs-lookup"><span data-stu-id="c0a10-112">Syntax</span></span>  
  
```xml  
<claimTypeRequirements>
  <add claimType="URI"
       isOptional="Boolean" />
</claimTypeRequirements>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c0a10-113">属性および要素</span><span class="sxs-lookup"><span data-stu-id="c0a10-113">Attributes and Elements</span></span>  
 <span data-ttu-id="c0a10-114">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="c0a10-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c0a10-115">属性</span><span class="sxs-lookup"><span data-stu-id="c0a10-115">Attributes</span></span>  
  
|<span data-ttu-id="c0a10-116">属性</span><span class="sxs-lookup"><span data-stu-id="c0a10-116">Attribute</span></span>|<span data-ttu-id="c0a10-117">説明</span><span class="sxs-lookup"><span data-stu-id="c0a10-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c0a10-118">claimType</span><span class="sxs-lookup"><span data-stu-id="c0a10-118">claimType</span></span>|<span data-ttu-id="c0a10-119">クレームの種類を定義する URI。</span><span class="sxs-lookup"><span data-stu-id="c0a10-119">A URI that defines the type of a claim.</span></span> <span data-ttu-id="c0a10-120">たとえば、Web サイトから製品を購入するために、ユーザーは、十分な与信限度額を備えた有効なクレジット カードを示す必要があります。</span><span class="sxs-lookup"><span data-stu-id="c0a10-120">For example, to purchase a product from a Web site, the user must present a valid credit card with sufficient credit limit.</span></span> <span data-ttu-id="c0a10-121">クレームの種類として、クレジット カードの URI があります。</span><span class="sxs-lookup"><span data-stu-id="c0a10-121">The claim type would be the credit card URI.</span></span>|  
|<span data-ttu-id="c0a10-122">isOptional</span><span class="sxs-lookup"><span data-stu-id="c0a10-122">isOptional</span></span>|<span data-ttu-id="c0a10-123">これが省略可能なクレームかどうかを指定するブール値。</span><span class="sxs-lookup"><span data-stu-id="c0a10-123">A Boolean value that specifies if this is for an optional claim.</span></span> <span data-ttu-id="c0a10-124">これが必須のクレームの場合は、この属性を `false` に設定します。</span><span class="sxs-lookup"><span data-stu-id="c0a10-124">Set this attribute to `false` if this is a required claim.</span></span><br /><br /> <span data-ttu-id="c0a10-125">サービスが必須でない情報を求めるときにこの属性を使用できます。</span><span class="sxs-lookup"><span data-stu-id="c0a10-125">You can use this attribute when the service asks for some information but does not require it.</span></span> <span data-ttu-id="c0a10-126">たとえば、ユーザーに氏名と住所の入力を要求し、電話番号は省略可能にする場合などです。</span><span class="sxs-lookup"><span data-stu-id="c0a10-126">For example, if you require the user to enter his/her first name, last name and address, but decide that phone number is optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c0a10-127">子要素</span><span class="sxs-lookup"><span data-stu-id="c0a10-127">Child Elements</span></span>  
 <span data-ttu-id="c0a10-128">なし。</span><span class="sxs-lookup"><span data-stu-id="c0a10-128">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c0a10-129">親要素</span><span class="sxs-lookup"><span data-stu-id="c0a10-129">Parent Elements</span></span>  
  
|<span data-ttu-id="c0a10-130">要素</span><span class="sxs-lookup"><span data-stu-id="c0a10-130">Element</span></span>|<span data-ttu-id="c0a10-131">説明</span><span class="sxs-lookup"><span data-stu-id="c0a10-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c0a10-132">\<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="c0a10-132">\<claimTypeRequirements></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/claimtyperequirements-element.md)|<span data-ttu-id="c0a10-133">必須のクレームの種類のコレクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="c0a10-133">Specifies a collection of required claim types.</span></span><br /><br /> <span data-ttu-id="c0a10-134">フェデレーション シナリオでは、サービスが受信資格情報についての要件を記述します。</span><span class="sxs-lookup"><span data-stu-id="c0a10-134">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="c0a10-135">たとえば、受信資格情報は、特定のクレーム タイプのセットを処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c0a10-135">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="c0a10-136">このコレクションの要素はそれぞれ、フェデレーション資格情報に表示されると予想される必須の要求および省略可能な要求の種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="c0a10-136">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c0a10-137">Remarks</span><span class="sxs-lookup"><span data-stu-id="c0a10-137">Remarks</span></span>  
 <span data-ttu-id="c0a10-138">フェデレーション シナリオでは、サービスが受信資格情報についての要件を記述します。</span><span class="sxs-lookup"><span data-stu-id="c0a10-138">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="c0a10-139">たとえば、受信資格情報は、特定のクレーム タイプのセットを処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c0a10-139">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="c0a10-140">この要件はセキュリティ ポリシー内に明記されます。</span><span class="sxs-lookup"><span data-stu-id="c0a10-140">This requirement is manifested in a security policy.</span></span> <span data-ttu-id="c0a10-141">クライアントがフェデレーション サービスの資格情報 (CardSpace など) を要求する場合、クライアントは要件をトークン要求 (RequestSecurityToken) に設定します。これにより、フェデレーション サービスは、要件どおりの資格情報を発行できます。</span><span class="sxs-lookup"><span data-stu-id="c0a10-141">When a client requests credentials from a federated service (for example, CardSpace), it puts the requirements into a token request (RequestSecurityToken) so that the federated service can issue the credentials that satisfy the requirements accordingly.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c0a10-142">例</span><span class="sxs-lookup"><span data-stu-id="c0a10-142">Example</span></span>  
 <span data-ttu-id="c0a10-143">次の構成では、2 つのクレームの種類の要件をセキュリティ バインディングに追加しています。</span><span class="sxs-lookup"><span data-stu-id="c0a10-143">The following configuration adds two claim type requirements to a security binding.</span></span>  
  
```xml  
<bindings>
  <wsFederationHttpBinding>
    <binding name="myFederatedBinding">
      <security mode="Message">
        <message issuedTokenType="urn:oasis:names:tc:SAML:1.0:assertion">
          <claimTypeRequirements>
            <add claimType="http://schemas.microsoft.com/ws/2005/05/identity/claims/EmailAddress" />
            <add claimType="http://schemas.microsoft.com/ws/2005/05/identity/claims/UserName"
                 optional="true" />
          </claimTypeRequirements>
        </message>
      </security>
    </binding>
  </wsFederationHttpBinding>
</bindings>
```  
  
## <a name="see-also"></a><span data-ttu-id="c0a10-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="c0a10-144">See Also</span></span>  
 <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>  
 <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters.ClaimTypeRequirements%2A>  
 <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement.ClaimTypeRequirements%2A>  
 <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>  
 <xref:System.ServiceModel.Configuration.ClaimTypeElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="c0a10-145">\<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="c0a10-145">\<claimTypeRequirements></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/claimtyperequirements-element.md)  
 [<span data-ttu-id="c0a10-146">バインディング</span><span class="sxs-lookup"><span data-stu-id="c0a10-146">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="c0a10-147">バインディングの拡張</span><span class="sxs-lookup"><span data-stu-id="c0a10-147">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="c0a10-148">カスタム バインディング</span><span class="sxs-lookup"><span data-stu-id="c0a10-148">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="c0a10-149">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="c0a10-149">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)  
 [<span data-ttu-id="c0a10-150">方法: SecurityBindingElement を使用してカスタム バインディングを作成します。</span><span class="sxs-lookup"><span data-stu-id="c0a10-150">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)  
 [<span data-ttu-id="c0a10-151">カスタム バインド セキュリティ</span><span class="sxs-lookup"><span data-stu-id="c0a10-151">Custom Binding Security</span></span>](../../../../../docs/framework/wcf/samples/custom-binding-security.md)
