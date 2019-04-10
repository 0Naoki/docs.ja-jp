---
title: <serviceDiscovery>
ms.date: 03/30/2017
ms.assetid: a3c68a4a-fc95-43c5-aacb-785936c0cf39
ms.openlocfilehash: 54a9833f56927568af711a103bd3831b767711e4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59209997"
---
# <a name="servicediscovery"></a><span data-ttu-id="cdc95-101">\<serviceDiscovery ></span><span class="sxs-lookup"><span data-stu-id="cdc95-101">\<serviceDiscovery></span></span>
<span data-ttu-id="cdc95-102">サービス エンドポイントの探索可能性を指定します。</span><span class="sxs-lookup"><span data-stu-id="cdc95-102">Specifies the discoverability of service endpoints.</span></span>  
  
 <span data-ttu-id="cdc95-103">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="cdc95-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="cdc95-104">\<<behaviors></span><span class="sxs-lookup"><span data-stu-id="cdc95-104">\<behaviors></span></span>  
<span data-ttu-id="cdc95-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="cdc95-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="cdc95-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="cdc95-106">\<behavior></span></span>  
<span data-ttu-id="cdc95-107">\<serviceDiscovery ></span><span class="sxs-lookup"><span data-stu-id="cdc95-107">\<serviceDiscovery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cdc95-108">構文</span><span class="sxs-lookup"><span data-stu-id="cdc95-108">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <serviceDiscovery>
        <announcementEndpoints>
          <endpoint name="String"
                    kind="Type" />
        </announcementEndpoints>
        <discoveryEndpoints>
          <endpoint name="String"
                    kind="Type" />
        </discoveryEndpoints>
      </serviceDiscovery>
    </behavior>
  </serviceBehaviors>
</behaviors>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cdc95-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="cdc95-109">Attributes and Elements</span></span>  
 <span data-ttu-id="cdc95-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="cdc95-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cdc95-111">属性</span><span class="sxs-lookup"><span data-stu-id="cdc95-111">Attributes</span></span>  
 <span data-ttu-id="cdc95-112">なし。</span><span class="sxs-lookup"><span data-stu-id="cdc95-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="cdc95-113">子要素</span><span class="sxs-lookup"><span data-stu-id="cdc95-113">Child Elements</span></span>  
  
|<span data-ttu-id="cdc95-114">要素</span><span class="sxs-lookup"><span data-stu-id="cdc95-114">Element</span></span>|<span data-ttu-id="cdc95-115">説明</span><span class="sxs-lookup"><span data-stu-id="cdc95-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cdc95-116">\<announcementEndpoint></span><span class="sxs-lookup"><span data-stu-id="cdc95-116">\<announcementEndpoint></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/announcementendpoint.md)|<span data-ttu-id="cdc95-117">アナウンス エンドポイントのコレクション。</span><span class="sxs-lookup"><span data-stu-id="cdc95-117">A collection of announcement endpoints.</span></span> <span data-ttu-id="cdc95-118">このセクションを使用して、アナウンス メッセージの送信に使用するエンドポイントを指定します。</span><span class="sxs-lookup"><span data-stu-id="cdc95-118">Use this section to specify the endpoints to use for sending announcement messages.</span></span>|  
|[<span data-ttu-id="cdc95-119">\<discoveryEndpoint></span><span class="sxs-lookup"><span data-stu-id="cdc95-119">\<discoveryEndpoint></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/discoveryendpoint.md)|<span data-ttu-id="cdc95-120">探索エンドポイントのコレクション。</span><span class="sxs-lookup"><span data-stu-id="cdc95-120">A collection of discovery endpoints.</span></span> <span data-ttu-id="cdc95-121">このセクションを使用して、探索メッセージをリッスンするエンドポイントを指定します。</span><span class="sxs-lookup"><span data-stu-id="cdc95-121">Use this section to specify the endpoints on which to listen for the discovery messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="cdc95-122">親要素</span><span class="sxs-lookup"><span data-stu-id="cdc95-122">Parent Elements</span></span>  
  
|<span data-ttu-id="cdc95-123">要素</span><span class="sxs-lookup"><span data-stu-id="cdc95-123">Element</span></span>|<span data-ttu-id="cdc95-124">説明</span><span class="sxs-lookup"><span data-stu-id="cdc95-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cdc95-125">\<behavior></span><span class="sxs-lookup"><span data-stu-id="cdc95-125">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="cdc95-126">動作の要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="cdc95-126">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cdc95-127">Remarks</span><span class="sxs-lookup"><span data-stu-id="cdc95-127">Remarks</span></span>  
 <span data-ttu-id="cdc95-128">サービスの動作構成に追加すると、この構成要素により、サービスの探索可能性はすべてのエンドポイントで有効になります。</span><span class="sxs-lookup"><span data-stu-id="cdc95-128">When added to the service’s behavior configuration, this configuration element makes all of the endpoints of that service discoverable.</span></span> <span data-ttu-id="cdc95-129">使用してこのようなエンドポイントの探索機能をさらに構成できる、 [ \<discoveryEndpoint >](../../../../../docs/framework/configure-apps/file-schema/wcf/discoveryendpoint.md)または[ \<announcementEndpoint >](../../../../../docs/framework/configure-apps/file-schema/wcf/announcementendpoint.md)子要素。</span><span class="sxs-lookup"><span data-stu-id="cdc95-129">You can further configure the discovery features of such endpoints by using the [\<discoveryEndpoint>](../../../../../docs/framework/configure-apps/file-schema/wcf/discoveryendpoint.md) or [\<announcementEndpoint>](../../../../../docs/framework/configure-apps/file-schema/wcf/announcementendpoint.md) child elements.</span></span> <span data-ttu-id="cdc95-130">使用して、 [ \<announcementEndpoint >](../../../../../docs/framework/configure-apps/file-schema/wcf/announcementendpoint.md)サービス アナウンス (こんにちは/オンラインおよびオフライン/Bye) の送信に使用するエンドポイント構成を指定して、アナウンスを構成するセクション。</span><span class="sxs-lookup"><span data-stu-id="cdc95-130">Use the [\<announcementEndpoint>](../../../../../docs/framework/configure-apps/file-schema/wcf/announcementendpoint.md) section to configure the announcements by specifying the endpoint configuration to be use to send service announcements (online/Hello and offline/Bye).</span></span> <span data-ttu-id="cdc95-131">使用して、 [ \<discoveryEndpoint >](../../../../../docs/framework/configure-apps/file-schema/wcf/discoveryendpoint.md)セクションを手動で探索メッセージをリッスンするエンドポイントを指定します。</span><span class="sxs-lookup"><span data-stu-id="cdc95-131">Use the [\<discoveryEndpoint>](../../../../../docs/framework/configure-apps/file-schema/wcf/discoveryendpoint.md) section to manually specify the endpoint on which to listen for the discovery messages.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cdc95-132">例</span><span class="sxs-lookup"><span data-stu-id="cdc95-132">Example</span></span>  
 <span data-ttu-id="cdc95-133">次の構成例では、CalculatorService を探索可能に指定しています。また、オプションで、使用するアナウンス エンドポイントを指定しています。</span><span class="sxs-lookup"><span data-stu-id="cdc95-133">The following configuration example specifies that the CalculatorService to be discoverable, and optionally specifies the announcement endpoint to be used.</span></span>  
  
```xml  
<services>
  <service name="CalculatorService"
           behaviorConfiguration="CalculatorServiceBehavior">
    ...
  </service>
</services>
<behaviors>
  <serviceBehaviors>
    <behavior name="CalculatorServiceBehavior">
      <serviceDiscovery>
        <announcementEndpoints>
          <endpoint name="udpEndpoint"
                    kind="udpAnnouncementEndpoint" />
        </announcementEndpoints>
      </serviceDiscovery>
    </behavior>
  </serviceBehaviors>
</behaviors>
```  
  
## <a name="see-also"></a><span data-ttu-id="cdc95-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="cdc95-134">See also</span></span>

- <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior>
