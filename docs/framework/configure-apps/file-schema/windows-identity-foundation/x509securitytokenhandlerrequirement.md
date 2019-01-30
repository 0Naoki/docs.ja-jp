---
title: <x509SecurityTokenHandlerRequirement>
ms.date: 03/30/2017
ms.assetid: aca22c2c-5ae7-42af-9bbd-15c2524692ce
author: BrucePerlerMS
ms.openlocfilehash: 6e8267f170dbb26381564be7b66df5f617156885
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/30/2019
ms.locfileid: "55271944"
---
# <a name="x509securitytokenhandlerrequirement"></a><span data-ttu-id="a7db1-101">\<x509SecurityTokenHandlerRequirement ></span><span class="sxs-lookup"><span data-stu-id="a7db1-101">\<x509SecurityTokenHandlerRequirement></span></span>
<span data-ttu-id="a7db1-102">オプションの構成を提供します、<xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>クラスまたは派生クラス。</span><span class="sxs-lookup"><span data-stu-id="a7db1-102">Provides optional configuration for the <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> class or derived classes.</span></span>  
  
 <span data-ttu-id="a7db1-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="a7db1-103">\<system.identityModel></span></span>  
<span data-ttu-id="a7db1-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="a7db1-104">\<identityConfiguration></span></span>  
<span data-ttu-id="a7db1-105">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="a7db1-105">\<securityTokenHandlers></span></span>  
<span data-ttu-id="a7db1-106">\<add></span><span class="sxs-lookup"><span data-stu-id="a7db1-106">\<add></span></span>  
<span data-ttu-id="a7db1-107">\<x509SecurityTokenHandlerRequirement ></span><span class="sxs-lookup"><span data-stu-id="a7db1-107">\<x509SecurityTokenHandlerRequirement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7db1-108">構文</span><span class="sxs-lookup"><span data-stu-id="a7db1-108">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add type="System.IdentityModel.Tokens.X509SecurityTokenHandler, System.IdentityModel">  
        <x509SecurityTokenHandlerRequirement>  
          mapToWindows=xs:boolean  
          certificateValidationMode="None||ChainTrust||PeerTrust||PeerOrChainTrust||Custom"  
          certificateValidator="Namespace.Class, Assembly"  
          revocationMode="NoCheck||Offline||Online"  
          trustedStoreLocation="CurrentUser||LocalMachine"  
        </x509SecurityTokenHandlerRequirement>  
      </add>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a7db1-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="a7db1-109">Attributes and Elements</span></span>  
 <span data-ttu-id="a7db1-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="a7db1-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a7db1-111">属性</span><span class="sxs-lookup"><span data-stu-id="a7db1-111">Attributes</span></span>  
  
|<span data-ttu-id="a7db1-112">属性</span><span class="sxs-lookup"><span data-stu-id="a7db1-112">Attribute</span></span>|<span data-ttu-id="a7db1-113">説明</span><span class="sxs-lookup"><span data-stu-id="a7db1-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a7db1-114">certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="a7db1-114">certificateValidationMode</span></span>|<span data-ttu-id="a7db1-115"><xref:System.ServiceModel.Security.X509CertificateValidationMode> X.509 証明書を使用する検証モードを指定する値。</span><span class="sxs-lookup"><span data-stu-id="a7db1-115">An <xref:System.ServiceModel.Security.X509CertificateValidationMode> value that specifies the validation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="a7db1-116">既定値は、"PeerOrChainTrust"です。</span><span class="sxs-lookup"><span data-stu-id="a7db1-116">The default value is "PeerOrChainTrust".</span></span>|  
|<span data-ttu-id="a7db1-117">mapToWindows</span><span class="sxs-lookup"><span data-stu-id="a7db1-117">mapToWindows</span></span>|<span data-ttu-id="a7db1-118">トークン ハンドラーが、入力方向の UPN 要求を使用して、検証トークンを Windows アカウントにマップする必要があるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="a7db1-118">Specifies whether the token handler should map the validating token to a Windows account by using the incoming UPN claim.</span></span> <span data-ttu-id="a7db1-119">既定では"false です"。</span><span class="sxs-lookup"><span data-stu-id="a7db1-119">The default is "false".</span></span>|  
|<span data-ttu-id="a7db1-120">revocationMode</span><span class="sxs-lookup"><span data-stu-id="a7db1-120">revocationMode</span></span>|<span data-ttu-id="a7db1-121"><xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> X.509 証明書を使用する失効モードを指定する値。</span><span class="sxs-lookup"><span data-stu-id="a7db1-121">An <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> value that specifies the revocation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="a7db1-122">既定値は、"Online"です。</span><span class="sxs-lookup"><span data-stu-id="a7db1-122">The default value is "Online".</span></span>|  
|<span data-ttu-id="a7db1-123">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="a7db1-123">trustedStoreLocation</span></span>|<span data-ttu-id="a7db1-124">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> X.509 証明書ストアを指定する値。</span><span class="sxs-lookup"><span data-stu-id="a7db1-124">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the X.509 certificate store.</span></span> <span data-ttu-id="a7db1-125">既定値は、"LocalMachine"です。</span><span class="sxs-lookup"><span data-stu-id="a7db1-125">The default value is "LocalMachine".</span></span>|  
|<span data-ttu-id="a7db1-126">certificateValidator</span><span class="sxs-lookup"><span data-stu-id="a7db1-126">certificateValidator</span></span>|<span data-ttu-id="a7db1-127">派生したカスタム型<xref:System.IdentityModel.Selectors.X509CertificateValidator>します。</span><span class="sxs-lookup"><span data-stu-id="a7db1-127">A custom type that derives from <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span> <span data-ttu-id="a7db1-128">場合、`certificateValidationMode`属性が"Custom"は、この型のインスタンスが発行者証明書の検証に使用します。</span><span class="sxs-lookup"><span data-stu-id="a7db1-128">If the `certificateValidationMode` attribute is "Custom", an instance of this type is used for issuer certificate validation.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a7db1-129">子要素</span><span class="sxs-lookup"><span data-stu-id="a7db1-129">Child Elements</span></span>  
 <span data-ttu-id="a7db1-130">なし</span><span class="sxs-lookup"><span data-stu-id="a7db1-130">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a7db1-131">親要素</span><span class="sxs-lookup"><span data-stu-id="a7db1-131">Parent Elements</span></span>  
  
|<span data-ttu-id="a7db1-132">要素</span><span class="sxs-lookup"><span data-stu-id="a7db1-132">Element</span></span>|<span data-ttu-id="a7db1-133">説明</span><span class="sxs-lookup"><span data-stu-id="a7db1-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a7db1-134">\<add></span><span class="sxs-lookup"><span data-stu-id="a7db1-134">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/add.md)|<span data-ttu-id="a7db1-135">トークン ハンドラー コレクションには、指定したセキュリティ トークン ハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="a7db1-135">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="a7db1-136">例</span><span class="sxs-lookup"><span data-stu-id="a7db1-136">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.X509SecurityTokenHandler, System.IdentityModel">  
    <x509SecurityTokenHandlerRequirement mapToWindows="true"   
                                         certificateValidationMode="PeerOrChainTrust"   
                                         revocationMode="Online"   
                                         trustedStoreLocation="LocalMachine" />  
</add>  
```
