---
title: '&lt;trustedIssuers&gt;'
ms.date: 03/30/2017
ms.assetid: d818c917-07b4-40db-9801-8676561859fd
author: BrucePerlerMS
ms.openlocfilehash: 1459027ae22344d5b1abc917c490b8e98fa0f2c3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54634000"
---
# <a name="lttrustedissuersgt"></a><span data-ttu-id="f5a20-102">&lt;trustedIssuers&gt;</span><span class="sxs-lookup"><span data-stu-id="f5a20-102">&lt;trustedIssuers&gt;</span></span>
<span data-ttu-id="f5a20-103">構成ベースの発行者名レジストリによって使用される信頼された発行者証明書の一覧を構成します (<xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>)。</span><span class="sxs-lookup"><span data-stu-id="f5a20-103">Configures the list of trusted issuer certificates used by the configuration-based issuer name registry (<xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>).</span></span>  
  
 <span data-ttu-id="f5a20-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="f5a20-104">\<system.identityModel></span></span>  
<span data-ttu-id="f5a20-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="f5a20-105">\<identityConfiguration></span></span>  
<span data-ttu-id="f5a20-106">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="f5a20-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="f5a20-107">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="f5a20-107">\<securityTokenHandlerConfiguration></span></span>  
<span data-ttu-id="f5a20-108">\<issuerNameRegistry></span><span class="sxs-lookup"><span data-stu-id="f5a20-108">\<issuerNameRegistry></span></span>  
<span data-ttu-id="f5a20-109">\<trustedIssuers></span><span class="sxs-lookup"><span data-stu-id="f5a20-109">\<trustedIssuers></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5a20-110">構文</span><span class="sxs-lookup"><span data-stu-id="f5a20-110">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration>  
        <issuerNameRegistry>  
          <trustedIssuers>  
            <add thumbprint=xs:string name=xs:string>  
            <clear>  
            <remove thumbprint=xs:string>  
          </trustedIssuers>  
        </issuerNameRegistry>  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f5a20-111">属性および要素</span><span class="sxs-lookup"><span data-stu-id="f5a20-111">Attributes and Elements</span></span>  
 <span data-ttu-id="f5a20-112">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="f5a20-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f5a20-113">属性</span><span class="sxs-lookup"><span data-stu-id="f5a20-113">Attributes</span></span>  
 <span data-ttu-id="f5a20-114">なし</span><span class="sxs-lookup"><span data-stu-id="f5a20-114">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="f5a20-115">子要素</span><span class="sxs-lookup"><span data-stu-id="f5a20-115">Child Elements</span></span>  
  
|<span data-ttu-id="f5a20-116">要素</span><span class="sxs-lookup"><span data-stu-id="f5a20-116">Element</span></span>|<span data-ttu-id="f5a20-117">説明</span><span class="sxs-lookup"><span data-stu-id="f5a20-117">Description</span></span>|  
|-------------|-----------------|  
|`<add thumbprint=xs:string name=xs:string>`|<span data-ttu-id="f5a20-118">証明書を信頼された発行者のコレクションに追加します。</span><span class="sxs-lookup"><span data-stu-id="f5a20-118">Adds a certificate to the collection of trusted issuers.</span></span> <span data-ttu-id="f5a20-119">証明書を指定した、`thumbprint`属性。</span><span class="sxs-lookup"><span data-stu-id="f5a20-119">The certificate is specified with the `thumbprint` attribute.</span></span> <span data-ttu-id="f5a20-120">この属性は必須であり、証明書のサムプリントの ASN.1 エンコードされたフォームを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="f5a20-120">This attribute is required and should contain the ASN.1 encoded form of the certificate thumbprint.</span></span> <span data-ttu-id="f5a20-121">`name`属性は省略可能と証明書のフレンドリ名を指定するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="f5a20-121">The `name` attribute is optional and can be used to specify a friendly name for the certificate.</span></span>|  
|`<clear>`|<span data-ttu-id="f5a20-122">信頼された発行者のコレクションからすべての証明書をクリアします。</span><span class="sxs-lookup"><span data-stu-id="f5a20-122">Clears all certificates from the collection of trusted issuers.</span></span>|  
|`<remove thumbprint=xs:string>`|<span data-ttu-id="f5a20-123">証明書を信頼された発行者のコレクションから削除します。</span><span class="sxs-lookup"><span data-stu-id="f5a20-123">Removes a certificate from the collection of trusted issuers.</span></span> <span data-ttu-id="f5a20-124">証明書を指定した、`thumbprint`属性。</span><span class="sxs-lookup"><span data-stu-id="f5a20-124">The certificate is specified with the `thumbprint` attribute.</span></span> <span data-ttu-id="f5a20-125">この属性は必須です。</span><span class="sxs-lookup"><span data-stu-id="f5a20-125">This attribute is required.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f5a20-126">親要素</span><span class="sxs-lookup"><span data-stu-id="f5a20-126">Parent Elements</span></span>  
  
|<span data-ttu-id="f5a20-127">要素</span><span class="sxs-lookup"><span data-stu-id="f5a20-127">Element</span></span>|<span data-ttu-id="f5a20-128">説明</span><span class="sxs-lookup"><span data-stu-id="f5a20-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f5a20-129">\<issuerNameRegistry></span><span class="sxs-lookup"><span data-stu-id="f5a20-129">\<issuerNameRegistry></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/issuernameregistry.md)|<span data-ttu-id="f5a20-130">発行者名レジストリを構成します。</span><span class="sxs-lookup"><span data-stu-id="f5a20-130">Configures the issuer name registry.</span></span> <span data-ttu-id="f5a20-131">**重要:** `type`の属性、`<issuerNameRegistry>`要素を参照する必要があります、<xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>クラス、`<trustedIssuers>`を有効にする要素。</span><span class="sxs-lookup"><span data-stu-id="f5a20-131">**Important:**  The `type` attribute of the `<issuerNameRegistry>` element must reference the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class for the `<trustedIssuers>` element to be valid.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f5a20-132">Remarks</span><span class="sxs-lookup"><span data-stu-id="f5a20-132">Remarks</span></span>  
 <span data-ttu-id="f5a20-133">Windows Identity Foundation (WIF) の単一の実装を提供する、<xref:System.IdentityModel.Tokens.IssuerNameRegistry>すぐに使えるクラス、<xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>クラス。</span><span class="sxs-lookup"><span data-stu-id="f5a20-133">Windows Identity Foundation (WIF) provides a single implementation of the <xref:System.IdentityModel.Tokens.IssuerNameRegistry> class out of the box, the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class.</span></span> <span data-ttu-id="f5a20-134">構成の発行者名レジストリは、構成から読み込まれる信頼された発行者の一覧を保持します。</span><span class="sxs-lookup"><span data-stu-id="f5a20-134">The configuration issuer name registry maintains a list of trusted issuers that is loaded from configuration.</span></span> <span data-ttu-id="f5a20-135">一覧は、各発行者名を発行者によって生成されたトークンの署名を検証するために必要な X.509 証明書に関連付けます。</span><span class="sxs-lookup"><span data-stu-id="f5a20-135">The list associates each issuer name with the X.509 certificate that is needed to verify the signature of tokens produced by the issuer.</span></span> <span data-ttu-id="f5a20-136">信頼された発行者の証明書の一覧が指定されて、`<trustedIssuers>`要素。</span><span class="sxs-lookup"><span data-stu-id="f5a20-136">The list of trusted issuer certificates is specified under the `<trustedIssuers>` element.</span></span> <span data-ttu-id="f5a20-137">リスト内の各要素は、その発行者によって生成されたトークンの署名を検証するために必要な X.509 証明書をニーモニックの発行者名を関連付けます。</span><span class="sxs-lookup"><span data-stu-id="f5a20-137">Each element in the list associates a mnemonic issuer name with the X.509 certificate that is needed to verify the signature of tokens produced by that issuer.</span></span> <span data-ttu-id="f5a20-138">信頼された証明書が証明書の拇印の形式でエンコードされた ASN.1 を使用して、指定され、を使用して、コレクションに追加されます`<add>`要素。</span><span class="sxs-lookup"><span data-stu-id="f5a20-138">Trusted certificates are specified using the ASN.1 encoded form of the certificate thumbprint and are added the collection by using `<add>` element.</span></span> <span data-ttu-id="f5a20-139">オフにしたり、発行者 (証明書) を使用して一覧から削除、`<clear>`と`<remove>`要素。</span><span class="sxs-lookup"><span data-stu-id="f5a20-139">You can clear or remove issuers (certificates) from the list by using the `<clear>` and `<remove>` elements.</span></span>  
  
 <span data-ttu-id="f5a20-140">`type`の属性、`<issuerNameRegistry>`要素を参照する必要があります、<xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>クラス、`<trustedIssuers>`を有効にする要素。</span><span class="sxs-lookup"><span data-stu-id="f5a20-140">The `type` attribute of the `<issuerNameRegistry>` element must reference the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class for the `<trustedIssuers>` element to be valid.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f5a20-141">例</span><span class="sxs-lookup"><span data-stu-id="f5a20-141">Example</span></span>  
 <span data-ttu-id="f5a20-142">次の XML では、名前のレジストリをベースの構成の発行者を指定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f5a20-142">The following XML shows how to specify the configuration based issuer name registry.</span></span>  
  
```xml  
<issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
  <trustedIssuers>  
    <add thumbprint="9B74CB2F32 … B1DC01EF40D0" name="LocalSTS" />  
  </trustedIssuers>  
</issuerNameRegistry>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f5a20-143">関連項目</span><span class="sxs-lookup"><span data-stu-id="f5a20-143">See also</span></span>
- <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>
- <xref:System.IdentityModel.Tokens.IssuerNameRegistry>
