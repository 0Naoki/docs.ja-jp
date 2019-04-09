---
title: <add> (行中)  <transportConfigurationType>
ms.date: 03/30/2017
ms.assetid: 03d79db9-571d-4534-acef-d05e5467b257
ms.openlocfilehash: c71a58b13e89bedb5eed24d784c82fb1525f7625
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59126725"
---
# <a name="add-of-transportconfigurationtype"></a><span data-ttu-id="93cc0-102">\<add> of \<transportConfigurationType></span><span class="sxs-lookup"><span data-stu-id="93cc0-102">\<add> of \<transportConfigurationType></span></span>
<span data-ttu-id="93cc0-103">この要素は、特定のトランスポートの種類を識別するキーと値のペアです。</span><span class="sxs-lookup"><span data-stu-id="93cc0-103">This element is a key/value pair, which identifies the type of a particular transport.</span></span>  
  
 <span data-ttu-id="93cc0-104">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="93cc0-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="93cc0-105">\<serviceHostingEnvironment ></span><span class="sxs-lookup"><span data-stu-id="93cc0-105">\<ServiceHostingEnvironment></span></span>  
<span data-ttu-id="93cc0-106">\<transportConfigurationTypes></span><span class="sxs-lookup"><span data-stu-id="93cc0-106">\<transportConfigurationTypes></span></span>  
<span data-ttu-id="93cc0-107">\<add></span><span class="sxs-lookup"><span data-stu-id="93cc0-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="93cc0-108">構文</span><span class="sxs-lookup"><span data-stu-id="93cc0-108">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>
  <transportConfigurationTypes>
    <add name="String"
         transportConfigurationType="String" />
  </transportConfigurationTypes>
</serviceHostingEnvironment>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="93cc0-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="93cc0-109">Attributes and Elements</span></span>  
 <span data-ttu-id="93cc0-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="93cc0-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="93cc0-111">属性</span><span class="sxs-lookup"><span data-stu-id="93cc0-111">Attributes</span></span>  
  
|<span data-ttu-id="93cc0-112">属性</span><span class="sxs-lookup"><span data-stu-id="93cc0-112">Attribute</span></span>|<span data-ttu-id="93cc0-113">説明</span><span class="sxs-lookup"><span data-stu-id="93cc0-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="93cc0-114">name</span><span class="sxs-lookup"><span data-stu-id="93cc0-114">name</span></span>|<span data-ttu-id="93cc0-115">必須の文字列属性です。</span><span class="sxs-lookup"><span data-stu-id="93cc0-115">Required String attribute.</span></span><br /><br /> <span data-ttu-id="93cc0-116">トランスポートの種類を一意に識別するユーザー定義キーを含みます。</span><span class="sxs-lookup"><span data-stu-id="93cc0-116">Contains a user-defined key that uniquely identifies the transport type.</span></span>|  
|<span data-ttu-id="93cc0-117">transportConfigurationType</span><span class="sxs-lookup"><span data-stu-id="93cc0-117">transportConfigurationType</span></span>|<span data-ttu-id="93cc0-118">特定のトランスポートを実装する種類を含む文字列。</span><span class="sxs-lookup"><span data-stu-id="93cc0-118">A string that contains the type that implements the specific transport.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="93cc0-119">子要素</span><span class="sxs-lookup"><span data-stu-id="93cc0-119">Child Elements</span></span>  
 <span data-ttu-id="93cc0-120">なし</span><span class="sxs-lookup"><span data-stu-id="93cc0-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="93cc0-121">親要素</span><span class="sxs-lookup"><span data-stu-id="93cc0-121">Parent Elements</span></span>  
  
|<span data-ttu-id="93cc0-122">要素</span><span class="sxs-lookup"><span data-stu-id="93cc0-122">Element</span></span>|<span data-ttu-id="93cc0-123">説明</span><span class="sxs-lookup"><span data-stu-id="93cc0-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="93cc0-124">\<transportConfigurationTypes></span><span class="sxs-lookup"><span data-stu-id="93cc0-124">\<transportConfigurationTypes></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transportconfigurationtypes.md)|<span data-ttu-id="93cc0-125">特定のトランスポートを実装する型のコレクション。</span><span class="sxs-lookup"><span data-stu-id="93cc0-125">A collection of types that implement the specific transport.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="93cc0-126">例</span><span class="sxs-lookup"><span data-stu-id="93cc0-126">Example</span></span>  
  
```xml  
<serviceHostingEnvironment>
  <transportConfigurationTypes>
    <add name="net.udp"
         transportConfigurationType="Microsoft.ServiceModel.Samples.Hosting.HostedUdpTransportConfiguration, UdpActivation, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6fa904d2da1848d6" />
  </transportConfigurationTypes>
</serviceHostingEnvironment>
```  
  
## <a name="see-also"></a><span data-ttu-id="93cc0-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="93cc0-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.TransportConfigurationTypeElement>
- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
- [<span data-ttu-id="93cc0-128">ホスト</span><span class="sxs-lookup"><span data-stu-id="93cc0-128">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
