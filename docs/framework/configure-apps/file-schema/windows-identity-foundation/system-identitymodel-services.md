---
title: <system.identityModel.services>
ms.date: 03/30/2017
ms.assetid: fa1624dd-2d74-4ae3-942e-498cee261ac5
author: BrucePerlerMS
ms.openlocfilehash: 9728f3caee4dba367e4fc4a3e68213b1055cc3d1
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/30/2019
ms.locfileid: "55273976"
---
# <a name="systemidentitymodelservices"></a><span data-ttu-id="a5484-102">\<system.identityModel.services></span><span class="sxs-lookup"><span data-stu-id="a5484-102">\<system.identityModel.services></span></span>
<span data-ttu-id="a5484-103">Ws-federation プロトコルを使用して認証用の構成セクション。</span><span class="sxs-lookup"><span data-stu-id="a5484-103">Configuration section for authentication using the WS-Federation protocol.</span></span>  
  
 <span data-ttu-id="a5484-104">\<system.identityModel.services></span><span class="sxs-lookup"><span data-stu-id="a5484-104">\<system.identityModel.services></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5484-105">構文</span><span class="sxs-lookup"><span data-stu-id="a5484-105">Syntax</span></span>  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration name=xs:string identityConfigurationName=xs:string>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a5484-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="a5484-106">Attributes and Elements</span></span>  
 <span data-ttu-id="a5484-107">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="a5484-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a5484-108">属性</span><span class="sxs-lookup"><span data-stu-id="a5484-108">Attributes</span></span>  
 <span data-ttu-id="a5484-109">なし</span><span class="sxs-lookup"><span data-stu-id="a5484-109">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a5484-110">子要素</span><span class="sxs-lookup"><span data-stu-id="a5484-110">Child Elements</span></span>  
  
|<span data-ttu-id="a5484-111">要素</span><span class="sxs-lookup"><span data-stu-id="a5484-111">Element</span></span>|<span data-ttu-id="a5484-112">説明</span><span class="sxs-lookup"><span data-stu-id="a5484-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a5484-113">\<federationConfiguration></span><span class="sxs-lookup"><span data-stu-id="a5484-113">\<federationConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md)|<span data-ttu-id="a5484-114">構成設定が含まれています、 <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) と<xref:System.IdentityModel.Services.SessionAuthenticationModule>(SAM) HTTP モジュールです。</span><span class="sxs-lookup"><span data-stu-id="a5484-114">Contains the settings that configure the <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) and the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) HTTP modules.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a5484-115">親要素</span><span class="sxs-lookup"><span data-stu-id="a5484-115">Parent Elements</span></span>  
 <span data-ttu-id="a5484-116">なし</span><span class="sxs-lookup"><span data-stu-id="a5484-116">None</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a5484-117">Remarks</span><span class="sxs-lookup"><span data-stu-id="a5484-117">Remarks</span></span>  
 <span data-ttu-id="a5484-118">追加、 `<system.identityModel.services>` SAM と WSFAM の設定を提供するアプリケーションの構成ファイルにセクション。</span><span class="sxs-lookup"><span data-stu-id="a5484-118">Add a `<system.identityModel.services>` section to your application’s configuration file to provide settings for the SAM and WSFAM.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="a5484-119">使用する場合、<xref:System.IdentityModel.Services.ClaimsPrincipalPermission>または<xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute>、コードでは、クレーム承認マネージャーでのクレームに基づくアクセス制御を提供するクラス (<xref:System.Security.Claims.ClaimsAuthorizationManager>) を通じて承認決定を行うために使用するポリシーが構成されていると、 `<identityConfiguration>`暗黙的または明示的に参照される要素を`<federationConfiguration>`このセクションの要素。</span><span class="sxs-lookup"><span data-stu-id="a5484-119">When using the <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> or the <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> class to provide claims-based access control in your code, the claims authorization manager (<xref:System.Security.Claims.ClaimsAuthorizationManager>) and policy that is used to make authorization decisions are configured through an `<identityConfiguration>` element that is implicitly or explicitly referenced from a `<federationConfiguration>` element in this section.</span></span> <span data-ttu-id="a5484-120">詳細については、次を参照してください。、**解説**下、 [ \<federationConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md)要素。</span><span class="sxs-lookup"><span data-stu-id="a5484-120">For more information, see the **Remarks** under the [\<federationConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md) element.</span></span>  
  
 <span data-ttu-id="a5484-121">`<system.identityModel.services>`セクションがによって表される、<xref:System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection>クラス。</span><span class="sxs-lookup"><span data-stu-id="a5484-121">The `<system.identityModel.services>` section is represented by the <xref:System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection> class.</span></span> <span data-ttu-id="a5484-122">子のコレクション`<federationConfiguration>`のセクションの構成要素として表されます、<xref:System.IdentityModel.Services.Configuration.FederationConfigurationElementCollection>クラス。</span><span class="sxs-lookup"><span data-stu-id="a5484-122">The collection of child `<federationConfiguration>` elements configured in the section is represented by the <xref:System.IdentityModel.Services.Configuration.FederationConfigurationElementCollection> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a5484-123">例</span><span class="sxs-lookup"><span data-stu-id="a5484-123">Example</span></span>  
 <span data-ttu-id="a5484-124">次の XML を追加する方法を示しています、`<system.identityModel.services>`構成ファイルにセクション。</span><span class="sxs-lookup"><span data-stu-id="a5484-124">The following XML shows how to add a `<system.identityModel.services>` section to a configuration file.</span></span> <span data-ttu-id="a5484-125">両方のセクションの宣言を追加する必要があります最初、`<system.identityModel.services>`セクションおよび`<system.identityModel>`セクション。</span><span class="sxs-lookup"><span data-stu-id="a5484-125">You must first add section declarations for both the `<system.identityModel.services>` section and the `<system.identityModel>` sections.</span></span> <span data-ttu-id="a5484-126">(追加すると、`<system.identityModel.services>`セクションの宣言も追加する必要があります、`<system.identityModel>`ことに、既定値を確認するセクション`<identityConfiguration>`セクションは、必要な場合、ランタイムによって作成できます)。フェデレーション認証設定を構成できますセクション宣言を追加した後、`<system.identityModel.services>`要素。</span><span class="sxs-lookup"><span data-stu-id="a5484-126">(When you add a `<system.identityModel.services>` section, you should also add a declaration for the `<system.identityModel>` section to ensure that a default `<identityConfiguration>` section can be created by the runtime if necessary.) After the section declarations have been added, you can configure federated authentication settings under the `<system.identityModel.services>` element.</span></span>  
  
```xml  
<configuration>  
  <configSections>  
    <section name="system.identityModel" type="System.IdentityModel.Configuration.SystemIdentityModelSection, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089" />  
    <section name="system.identityModel.services" type="System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089" />  
  </configSections>  
  
  <!-- Additional elements (not shown) -->  
  
  <system.identityModel.services>  
    <federationConfiguration>  
      <wsFederation passiveRedirectEnabled="true"   
        issuer="http://localhost:15839/wsFederationSTS/Issue"   
        realm="http://localhost:50969/" reply="http://localhost:50969/"   
        requireHttps="false"   
        signOutReply="http://localhost:50969/SignedOutPage.html"   
        signOutQueryString="Param1=value2&Param2=value2"   
        persistentCookiesOnPassiveRedirects="true" />  
      <cookieHandler requireSsl="false" />  
    </federationConfiguration>  
  </system.identityModel.services>  
  
</configuration>  
```
