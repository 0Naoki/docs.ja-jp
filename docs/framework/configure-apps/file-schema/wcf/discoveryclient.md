---
title: <discoveryClient>
ms.date: 03/30/2017
ms.assetid: a78f74c3-1152-4149-ab29-3f12d316caeb
ms.openlocfilehash: 512a91bf25180606213eb9eb3b4f7c6a0cb4cbbf
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57366232"
---
# <a name="discoveryclient"></a><span data-ttu-id="d3bea-101">\<discoveryClient></span><span class="sxs-lookup"><span data-stu-id="d3bea-101">\<discoveryClient></span></span>
<span data-ttu-id="d3bea-102">クライアント アプリケーションが実行時に探索可能なサービスを自動的に検索し、そのアドレスを見つけることができるカスタム バインドを作成するための構成要素。</span><span class="sxs-lookup"><span data-stu-id="d3bea-102">A configuration element for creating a custom binding that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>  
  
<span data-ttu-id="d3bea-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="d3bea-103">\<system.serviceModel></span></span>  
<span data-ttu-id="d3bea-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="d3bea-104">\<bindings></span></span>  
<span data-ttu-id="d3bea-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="d3bea-105">\<customBinding></span></span>  
<span data-ttu-id="d3bea-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="d3bea-106">\<binding></span></span>  
<span data-ttu-id="d3bea-107">\<discoveryClient></span><span class="sxs-lookup"><span data-stu-id="d3bea-107">\<discoveryClient></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d3bea-108">構文</span><span class="sxs-lookup"><span data-stu-id="d3bea-108">Syntax</span></span>  
  
```xml  
<discoveryClient discoveryEndpoint="String">
  <findCriteria duration="TimeSpan"
                maxResults="Integer"
                scopeMatchBy="Uri">
    <contractTypeNames>
      <add name="String"
           namespace="String" />
    </contractTypeNames>
    <extensions />
    <scopes>
      <add scope="URI"/>
    </scopes>
  </findCriteria>
</discoveryClient>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d3bea-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="d3bea-109">Attributes and Elements</span></span>  
 <span data-ttu-id="d3bea-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="d3bea-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d3bea-111">属性</span><span class="sxs-lookup"><span data-stu-id="d3bea-111">Attributes</span></span>  
  
|<span data-ttu-id="d3bea-112">属性</span><span class="sxs-lookup"><span data-stu-id="d3bea-112">Attribute</span></span>|<span data-ttu-id="d3bea-113">説明</span><span class="sxs-lookup"><span data-stu-id="d3bea-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d3bea-114">discoveryEndpoint</span><span class="sxs-lookup"><span data-stu-id="d3bea-114">discoveryEndpoint</span></span>|<span data-ttu-id="d3bea-115">クライアント アプリケーションが実行時に探索可能なサービスを自動的に検索し、そのアドレスを見つけることができる探索エンドポイントの名前を含む文字列。</span><span class="sxs-lookup"><span data-stu-id="d3bea-115">A string that contains the name of the Discovery Endpoint that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d3bea-116">子要素</span><span class="sxs-lookup"><span data-stu-id="d3bea-116">Child Elements</span></span>  
  
|<span data-ttu-id="d3bea-117">要素</span><span class="sxs-lookup"><span data-stu-id="d3bea-117">Element</span></span>|<span data-ttu-id="d3bea-118">説明</span><span class="sxs-lookup"><span data-stu-id="d3bea-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d3bea-119">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="d3bea-119">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="d3bea-120">探索サービスの検索にクライアント アプリケーションによって使用される基準を提供する構成要素。</span><span class="sxs-lookup"><span data-stu-id="d3bea-120">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="d3bea-121">条件は、(探しているサービスの種類を指定して) 検索条件にグループ化することができ、検索 (検索持続期間)、終了条件。</span><span class="sxs-lookup"><span data-stu-id="d3bea-121">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d3bea-122">親要素</span><span class="sxs-lookup"><span data-stu-id="d3bea-122">Parent Elements</span></span>  
  
|<span data-ttu-id="d3bea-123">要素</span><span class="sxs-lookup"><span data-stu-id="d3bea-123">Element</span></span>|<span data-ttu-id="d3bea-124">説明</span><span class="sxs-lookup"><span data-stu-id="d3bea-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d3bea-125">\<binding></span><span class="sxs-lookup"><span data-stu-id="d3bea-125">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="d3bea-126">カスタム バインドのすべてのバインド機能を定義します。</span><span class="sxs-lookup"><span data-stu-id="d3bea-126">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d3bea-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="d3bea-127">See also</span></span>
- <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>
- <xref:System.ServiceModel.Discovery.Configuration.DiscoveryClientElement>
