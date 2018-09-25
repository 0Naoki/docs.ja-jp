---
title: '&lt;certificateValidator&gt;'
ms.date: 03/30/2017
ms.assetid: 86161897-c20f-4ad8-9d7f-050c247251bf
author: BrucePerlerMS
ms.openlocfilehash: 65b8aa6fa4422579ce0d1c5e33d3418ea051612a
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/25/2018
ms.locfileid: "47077656"
---
# <a name="ltcertificatevalidatorgt"></a><span data-ttu-id="4ebd6-102">&lt;certificateValidator&gt;</span><span class="sxs-lookup"><span data-stu-id="4ebd6-102">&lt;certificateValidator&gt;</span></span>
<span data-ttu-id="4ebd6-103">証明書の検証のカスタム型を指定します。</span><span class="sxs-lookup"><span data-stu-id="4ebd6-103">Specifies a custom type for certificate validation.</span></span> <span data-ttu-id="4ebd6-104">場合にのみ、この型が使用される、`certificateValidationMode`の属性、 [ \<certificateValidation >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md)要素が"Custom"に設定します。</span><span class="sxs-lookup"><span data-stu-id="4ebd6-104">This type is used only if the `certificateValidationMode` attribute of the [\<certificateValidation>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md) element is set to "Custom".</span></span>  
  
 <span data-ttu-id="4ebd6-105">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="4ebd6-105">\<system.identityModel></span></span>  
<span data-ttu-id="4ebd6-106">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="4ebd6-106">\<identityConfiguration></span></span>  
<span data-ttu-id="4ebd6-107">\<certificateValidation ></span><span class="sxs-lookup"><span data-stu-id="4ebd6-107">\<certificateValidation></span></span>  
<span data-ttu-id="4ebd6-108">\<certificateValidator ></span><span class="sxs-lookup"><span data-stu-id="4ebd6-108">\<certificateValidator></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ebd6-109">構文</span><span class="sxs-lookup"><span data-stu-id="4ebd6-109">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <certificateValidation>  
      <certificateValidator type=xs:string>  
      </certificateValidator>  
    </certificateValidation>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4ebd6-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="4ebd6-110">Attributes and Elements</span></span>  
 <span data-ttu-id="4ebd6-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="4ebd6-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4ebd6-112">属性</span><span class="sxs-lookup"><span data-stu-id="4ebd6-112">Attributes</span></span>  
  
|<span data-ttu-id="4ebd6-113">属性</span><span class="sxs-lookup"><span data-stu-id="4ebd6-113">Attribute</span></span>|<span data-ttu-id="4ebd6-114">説明</span><span class="sxs-lookup"><span data-stu-id="4ebd6-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4ebd6-115">型</span><span class="sxs-lookup"><span data-stu-id="4ebd6-115">type</span></span>|<span data-ttu-id="4ebd6-116">派生したカスタム型を指定します、<xref:System.IdentityModel.Selectors.X509CertificateValidator>クラス。</span><span class="sxs-lookup"><span data-stu-id="4ebd6-116">Specifies a custom type that derives from the <xref:System.IdentityModel.Selectors.X509CertificateValidator> class.</span></span> <span data-ttu-id="4ebd6-117">設定、`certificateValidationMode`の属性、 [ \<certificateValidation >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md)要素がこの型を使用するには、"Custom"にします。</span><span class="sxs-lookup"><span data-stu-id="4ebd6-117">Set the `certificateValidationMode` attribute of the [\<certificateValidation>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md) element to "Custom" to use this type.</span></span> <span data-ttu-id="4ebd6-118">詳細を指定する方法については、`type`属性は、「[カスタム型の参照](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md)します。</span><span class="sxs-lookup"><span data-stu-id="4ebd6-118">For more information about how to specify the `type` attribute, see [Custom Type References](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span></span> <span data-ttu-id="4ebd6-119">任意。</span><span class="sxs-lookup"><span data-stu-id="4ebd6-119">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4ebd6-120">子要素</span><span class="sxs-lookup"><span data-stu-id="4ebd6-120">Child Elements</span></span>  
 <span data-ttu-id="4ebd6-121">なし</span><span class="sxs-lookup"><span data-stu-id="4ebd6-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4ebd6-122">親要素</span><span class="sxs-lookup"><span data-stu-id="4ebd6-122">Parent Elements</span></span>  
  
|<span data-ttu-id="4ebd6-123">要素</span><span class="sxs-lookup"><span data-stu-id="4ebd6-123">Element</span></span>|<span data-ttu-id="4ebd6-124">説明</span><span class="sxs-lookup"><span data-stu-id="4ebd6-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4ebd6-125">\<certificateValidation ></span><span class="sxs-lookup"><span data-stu-id="4ebd6-125">\<certificateValidation></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md)|<span data-ttu-id="4ebd6-126">トークン ハンドラーを使用して証明書の検証の設定を制御します。</span><span class="sxs-lookup"><span data-stu-id="4ebd6-126">Controls the settings that token handlers use to validate certificates.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="4ebd6-127">例</span><span class="sxs-lookup"><span data-stu-id="4ebd6-127">Example</span></span>  
  
```xml  
<certificateValidation certificateValidationMode="Custom"  
                       revocationMode="Online"  
                       trustedStoreLocation="LocalMachine">  
    <certificateValidator type="MyNamespace.CustomValidator, MyAssembly" />    
</certificateValidation>        
```
