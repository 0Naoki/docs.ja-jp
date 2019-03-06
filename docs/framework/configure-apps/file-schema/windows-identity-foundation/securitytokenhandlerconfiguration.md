---
title: <securityTokenHandlerConfiguration>
ms.date: 03/30/2017
ms.assetid: 28724cc6-020c-4a06-9a1f-d7594f315019
author: BrucePerlerMS
ms.openlocfilehash: 29e18cdda9e18addef4f0f32fd30e9abf6af78fc
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57360408"
---
# <a name="securitytokenhandlerconfiguration"></a><span data-ttu-id="f6973-101">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="f6973-101">\<securityTokenHandlerConfiguration></span></span>
<span data-ttu-id="f6973-102">トークン ハンドラーのコレクションの構成を提供します。</span><span class="sxs-lookup"><span data-stu-id="f6973-102">Provides configuration for the collection of token handlers.</span></span>  
  
 <span data-ttu-id="f6973-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="f6973-103">\<system.identityModel></span></span>  
<span data-ttu-id="f6973-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="f6973-104">\<identityConfiguration></span></span>  
<span data-ttu-id="f6973-105">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="f6973-105">\<securityTokenHandlers></span></span>  
<span data-ttu-id="f6973-106">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="f6973-106">\<securityTokenHandlerConfiguration></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6973-107">構文</span><span class="sxs-lookup"><span data-stu-id="f6973-107">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration saveBootstrapContext=xs:boolean  
          maximumClockSkew=TimeSpan>  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f6973-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="f6973-108">Attributes and Elements</span></span>  
 <span data-ttu-id="f6973-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="f6973-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f6973-110">属性</span><span class="sxs-lookup"><span data-stu-id="f6973-110">Attributes</span></span>  
  
|<span data-ttu-id="f6973-111">属性</span><span class="sxs-lookup"><span data-stu-id="f6973-111">Attribute</span></span>|<span data-ttu-id="f6973-112">説明</span><span class="sxs-lookup"><span data-stu-id="f6973-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f6973-113">saveBootstrapContext</span><span class="sxs-lookup"><span data-stu-id="f6973-113">saveBootstrapContext</span></span>|<span data-ttu-id="f6973-114">セッション トークンにブートス トラップ トークンを含める必要があるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="f6973-114">Specifies whether bootstrap tokens should be included in the session token.</span></span> <span data-ttu-id="f6973-115">設定して、値がトークン ハンドラー コレクションに設定することも可能性があります、`saveBootstrapContext`属性を[ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)要素。</span><span class="sxs-lookup"><span data-stu-id="f6973-115">The value may also be set on a token handler collection by setting the `saveBootstrapContext` attribute on the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element.</span></span> <span data-ttu-id="f6973-116">トークン ハンドラー コレクションに設定値は、サービスの設定値をオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="f6973-116">A value set on the token handler collection overrides the value set on the service.</span></span>|  
|<span data-ttu-id="f6973-117">maximumClockSkew</span><span class="sxs-lookup"><span data-stu-id="f6973-117">maximumClockSkew</span></span>|<span data-ttu-id="f6973-118">A<xref:System.TimeSpan>許可されている最大のクロック スキューを指定します。</span><span class="sxs-lookup"><span data-stu-id="f6973-118">A <xref:System.TimeSpan> that specifies the maximum allowed clock skew.</span></span> <span data-ttu-id="f6973-119">サインイン セッションの有効期限の検証などの時間を区別する操作を実行するときは、最大の許可されている時刻のずれを制御します。</span><span class="sxs-lookup"><span data-stu-id="f6973-119">Controls the maximum allowed clock skew when performing time-sensitive operations, such as validating the expiration time of a sign-in session.</span></span> <span data-ttu-id="f6973-120">既定値は 5 分間、"00: 継続"。</span><span class="sxs-lookup"><span data-stu-id="f6973-120">The default is 5 minutes, "00:05:00".</span></span> <span data-ttu-id="f6973-121">指定する方法の詳細についての<xref:System.TimeSpan>値を参照してください[Timespan 値](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md)します。</span><span class="sxs-lookup"><span data-stu-id="f6973-121">For more information about how to specify <xref:System.TimeSpan> values, see [Timespan Values](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span></span> <span data-ttu-id="f6973-122">設定して、最大クロック スキューがサービス レベルで設定することも可能性があります、`maximumClockSkew`属性を[ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)要素。</span><span class="sxs-lookup"><span data-stu-id="f6973-122">The maximum clock skew may also be set at the service level by setting the `maximumClockSkew` attribute on the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element.</span></span> <span data-ttu-id="f6973-123">トークン ハンドラー コレクションに設定値は、サービスの設定値をオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="f6973-123">A value set on the token handler collection overrides the value set on the service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f6973-124">子要素</span><span class="sxs-lookup"><span data-stu-id="f6973-124">Child Elements</span></span>  
  
|<span data-ttu-id="f6973-125">要素</span><span class="sxs-lookup"><span data-stu-id="f6973-125">Element</span></span>|<span data-ttu-id="f6973-126">説明</span><span class="sxs-lookup"><span data-stu-id="f6973-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f6973-127">\<audienceUris></span><span class="sxs-lookup"><span data-stu-id="f6973-127">\<audienceUris></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/audienceuris.md)|<span data-ttu-id="f6973-128">この証明書利用者の許容可能な識別子 Uri のセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="f6973-128">Specifies the set of URIs that are acceptable identifiers of this relying party.</span></span> <span data-ttu-id="f6973-129">任意。</span><span class="sxs-lookup"><span data-stu-id="f6973-129">Optional.</span></span>|  
|[<span data-ttu-id="f6973-130">\<caches></span><span class="sxs-lookup"><span data-stu-id="f6973-130">\<caches></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/caches.md)|<span data-ttu-id="f6973-131">セッション トークンやトークン リプレイ検出のために使用されるキャッシュを登録します。</span><span class="sxs-lookup"><span data-stu-id="f6973-131">Registers the caches used for session tokens and token replay detection.</span></span> <span data-ttu-id="f6973-132">サービス レベルまたはセキュリティ トークン ハンドラー コレクションに指定できます。</span><span class="sxs-lookup"><span data-stu-id="f6973-132">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="f6973-133">任意。</span><span class="sxs-lookup"><span data-stu-id="f6973-133">Optional.</span></span>|  
|[<span data-ttu-id="f6973-134">\<certificateValidation></span><span class="sxs-lookup"><span data-stu-id="f6973-134">\<certificateValidation></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md)|<span data-ttu-id="f6973-135">トークン ハンドラーを使用して証明書の検証の設定を制御します。</span><span class="sxs-lookup"><span data-stu-id="f6973-135">Controls the settings that token handlers use to validate certificates.</span></span> <span data-ttu-id="f6973-136">サービス レベルまたはセキュリティ トークン ハンドラー コレクションに指定できます。</span><span class="sxs-lookup"><span data-stu-id="f6973-136">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="f6973-137">特定のハンドラーが、独自の検証ツールで構成されている場合、これらの設定が上書きされます。</span><span class="sxs-lookup"><span data-stu-id="f6973-137">These settings are overridden if a specific handler is configured with its own validator.</span></span> <span data-ttu-id="f6973-138">任意。</span><span class="sxs-lookup"><span data-stu-id="f6973-138">Optional.</span></span>|  
|[<span data-ttu-id="f6973-139">\<issuerNameRegistry></span><span class="sxs-lookup"><span data-stu-id="f6973-139">\<issuerNameRegistry></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/issuernameregistry.md)|<span data-ttu-id="f6973-140">トークン ハンドラー コレクションのハンドラーによって使用される発行者名レジストリを構成します。</span><span class="sxs-lookup"><span data-stu-id="f6973-140">Configures the issuer name registry that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="f6973-141">任意。</span><span class="sxs-lookup"><span data-stu-id="f6973-141">Optional.</span></span>|  
|[<span data-ttu-id="f6973-142">\<issuerTokenResolver></span><span class="sxs-lookup"><span data-stu-id="f6973-142">\<issuerTokenResolver></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/issuertokenresolver.md)|<span data-ttu-id="f6973-143">トークン ハンドラー コレクションのハンドラーによって使用される発行者トークン リゾルバーを登録します。</span><span class="sxs-lookup"><span data-stu-id="f6973-143">Registers the issuer token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="f6973-144">発行者トークン リゾルバーを使用して、受信トークンおよびメッセージの署名トークンを解決します。</span><span class="sxs-lookup"><span data-stu-id="f6973-144">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span> <span data-ttu-id="f6973-145">任意。</span><span class="sxs-lookup"><span data-stu-id="f6973-145">Optional.</span></span>|  
|[<span data-ttu-id="f6973-146">\<serviceTokenResolver></span><span class="sxs-lookup"><span data-stu-id="f6973-146">\<serviceTokenResolver></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/servicetokenresolver.md)|<span data-ttu-id="f6973-147">トークン ハンドラー コレクションのハンドラーによって使用されるサービス トークン リゾルバーを登録します。</span><span class="sxs-lookup"><span data-stu-id="f6973-147">Registers the service token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="f6973-148">サービス トークン リゾルバーを使用して、受信トークンおよびメッセージの暗号化トークンを解決します。</span><span class="sxs-lookup"><span data-stu-id="f6973-148">The service token resolver is used to resolve the encryption token on incoming tokens and messages.</span></span> <span data-ttu-id="f6973-149">任意。</span><span class="sxs-lookup"><span data-stu-id="f6973-149">Optional.</span></span>|  
|[<span data-ttu-id="f6973-150">\<tokenReplayDetection></span><span class="sxs-lookup"><span data-stu-id="f6973-150">\<tokenReplayDetection></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md)|<span data-ttu-id="f6973-151">トークン リプレイ検出が有効にし、トークンの有効期限を指定します。</span><span class="sxs-lookup"><span data-stu-id="f6973-151">Enables token replay detection and specifies the expiration time for tokens.</span></span> <span data-ttu-id="f6973-152">サービス レベルまたはセキュリティ トークン ハンドラー コレクションに指定できます。</span><span class="sxs-lookup"><span data-stu-id="f6973-152">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="f6973-153">任意。</span><span class="sxs-lookup"><span data-stu-id="f6973-153">Optional.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f6973-154">親要素</span><span class="sxs-lookup"><span data-stu-id="f6973-154">Parent Elements</span></span>  
  
|<span data-ttu-id="f6973-155">要素</span><span class="sxs-lookup"><span data-stu-id="f6973-155">Element</span></span>|<span data-ttu-id="f6973-156">説明</span><span class="sxs-lookup"><span data-stu-id="f6973-156">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f6973-157">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="f6973-157">\<securityTokenHandlers></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlers.md)|<span data-ttu-id="f6973-158">エンドポイントに登録されているセキュリティ トークン ハンドラーのコレクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="f6973-158">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f6973-159">Remarks</span><span class="sxs-lookup"><span data-stu-id="f6973-159">Remarks</span></span>  
 <span data-ttu-id="f6973-160">このセクションのプロパティ値を提供する、<xref:System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="f6973-160">This section provides property values for a <xref:System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration> object.</span></span> <span data-ttu-id="f6973-161">このセクションで構成した設定は、サービスで構成されているものをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="f6973-161">Settings configured in this section override those configured on the service.</span></span> <span data-ttu-id="f6973-162">これらの設定の一部は、ハンドラーがセキュリティ トークン ハンドラー コレクションに追加されたときに指定されている設定によってさらに、オーバーライドことができます。</span><span class="sxs-lookup"><span data-stu-id="f6973-162">Some of these settings can, in turn, be overridden by settings that are specified when a handler is added to the security token handler collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f6973-163">例</span><span class="sxs-lookup"><span data-stu-id="f6973-163">Example</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>   
      <securityTokenHandlerConfiguration>  
  
        <audienceUris>  
          <clear/>  
          <add value="http://www.example.com/myapp/" />  
        </audienceUris>  
  
        <issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel">  
          <trustedIssuers>  
            <add thumbprint="97249e1a … 4c9158de" name="contoso.com" />  
          </trustedIssuers>  
        </issuerNameRegistry>  
  
        <issuerTokenResolver type="MyNamespace.CustomTokenResolver, MyAssembly" />  
  
        <serviceTokenResolver type="MyNamespace.CustomTokenResolver, MyAssembly" />  
  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```
