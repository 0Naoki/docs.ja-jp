---
title: '&lt;behaviors&gt;'
ms.date: 03/30/2017
ms.assetid: 0e5da4e6-1aa5-466c-924e-f10efee57f0b
ms.openlocfilehash: a6786efb289ee66da3f0635e1a86e23f9b7302d9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54528434"
---
# <a name="ltbehaviorsgt"></a><span data-ttu-id="47708-102">&lt;behaviors&gt;</span><span class="sxs-lookup"><span data-stu-id="47708-102">&lt;behaviors&gt;</span></span>
<span data-ttu-id="47708-103">この要素は、`endpointBehaviors` と`serviceBehaviors` という 2 つの子コレクションを定義します。</span><span class="sxs-lookup"><span data-stu-id="47708-103">This element defines two child collections named `endpointBehaviors` and `serviceBehaviors`.</span></span>  <span data-ttu-id="47708-104">各コレクションは、エンドポイントとサービスによって使用されるそれぞれの動作要素を定義します。</span><span class="sxs-lookup"><span data-stu-id="47708-104">Each collection defines behavior elements consumed by endpoints and services respectively.</span></span> <span data-ttu-id="47708-105">各動作要素は、その一意の `name` 属性で識別されます。</span><span class="sxs-lookup"><span data-stu-id="47708-105">Each behavior element is identified by its unique `name` attribute.</span></span> <span data-ttu-id="47708-106">[!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] 以降では、バインディングおよび動作に名前を付ける必要はありません。</span><span class="sxs-lookup"><span data-stu-id="47708-106">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="47708-107">既定の構成と無名のバインディングおよび動作の詳細については、「[簡略化された構成](../../../../../docs/framework/wcf/simplified-configuration.md)」と「[WCF サービスの構成を簡略化](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="47708-107">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
 <span data-ttu-id="47708-108">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="47708-108">\<system.ServiceModel></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47708-109">構文</span><span class="sxs-lookup"><span data-stu-id="47708-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
  </serviceBehaviors>
  <endpointBehaviors>
  </endpointBehaviors>
</behaviors>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="47708-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="47708-110">Attributes and Elements</span></span>  
 <span data-ttu-id="47708-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="47708-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="47708-112">属性</span><span class="sxs-lookup"><span data-stu-id="47708-112">Attributes</span></span>  
 <span data-ttu-id="47708-113">なし</span><span class="sxs-lookup"><span data-stu-id="47708-113">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="47708-114">子要素</span><span class="sxs-lookup"><span data-stu-id="47708-114">Child Elements</span></span>  
  
|<span data-ttu-id="47708-115">要素</span><span class="sxs-lookup"><span data-stu-id="47708-115">Element</span></span>|<span data-ttu-id="47708-116">説明</span><span class="sxs-lookup"><span data-stu-id="47708-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="47708-117">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="47708-117">\<endpointBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpointbehaviors.md)|<span data-ttu-id="47708-118">この構成セクションは、特定のエンドポイントに対して定義されたすべての動作を表します。</span><span class="sxs-lookup"><span data-stu-id="47708-118">This configuration section represents all the behaviors defined for a specific endpoint.</span></span>|  
|[<span data-ttu-id="47708-119">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="47708-119">\<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md)|<span data-ttu-id="47708-120">この構成セクションは、特定のサービスに対して定義されたすべての動作を表します。</span><span class="sxs-lookup"><span data-stu-id="47708-120">This configuration section represents all the behaviors defined for a specific service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="47708-121">親要素</span><span class="sxs-lookup"><span data-stu-id="47708-121">Parent Elements</span></span>  
  
|<span data-ttu-id="47708-122">要素</span><span class="sxs-lookup"><span data-stu-id="47708-122">Element</span></span>|<span data-ttu-id="47708-123">説明</span><span class="sxs-lookup"><span data-stu-id="47708-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="47708-124">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="47708-124">\<system.serviceModel></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)|<span data-ttu-id="47708-125">すべての Windows Communication Foundation (WCF) 構成要素のルート要素です。</span><span class="sxs-lookup"><span data-stu-id="47708-125">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="47708-126">Remarks</span><span class="sxs-lookup"><span data-stu-id="47708-126">Remarks</span></span>  
 <span data-ttu-id="47708-127">`<remove>` 要素を使用して、コレクションから特定の動作を削除できます。</span><span class="sxs-lookup"><span data-stu-id="47708-127">You can use the `<remove>` element to remove a particular behavior from the collection.</span></span> <span data-ttu-id="47708-128">これを行うには、`name` 要素の `<remove>` 属性に、削除する動作の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="47708-128">To do so, simply supply the name of the behavior to remove in the `name` attribute of the `<remove>` element.</span></span>  <span data-ttu-id="47708-129">また、`<clear>` 要素を使用してコレクションの内容をすべて消去し、動作コレクションの初期値を確実に空にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="47708-129">You can also use the `<clear>` element to insure that a behavior collection starts empty by clearing out all the content of the collection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47708-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="47708-130">See also</span></span>
- <xref:System.ServiceModel.Configuration.BehaviorsSection>
- <xref:System.ServiceModel.Configuration.EndpointBehaviorElementCollection>
- <xref:System.ServiceModel.Configuration.EndpointBehaviorElement>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElementCollection>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElement>
- [<span data-ttu-id="47708-131">動作を使用したランタイムの構成と拡張</span><span class="sxs-lookup"><span data-stu-id="47708-131">Configuring and Extending the Runtime with Behaviors</span></span>](../../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)
- [<span data-ttu-id="47708-132">クライアントの動作の構成</span><span class="sxs-lookup"><span data-stu-id="47708-132">Configuring Client Behaviors</span></span>](../../../../../docs/framework/wcf/configuring-client-behaviors.md)
- [<span data-ttu-id="47708-133">クライアントのランタイム動作の指定</span><span class="sxs-lookup"><span data-stu-id="47708-133">Specifying Client Run-Time Behavior</span></span>](../../../../../docs/framework/wcf/specifying-client-run-time-behavior.md)
- [<span data-ttu-id="47708-134">サービスのランタイム動作の指定</span><span class="sxs-lookup"><span data-stu-id="47708-134">Specifying Service Run-Time Behavior</span></span>](../../../../../docs/framework/wcf/specifying-service-run-time-behavior.md)
- [<span data-ttu-id="47708-135">セキュリティ動作</span><span class="sxs-lookup"><span data-stu-id="47708-135">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
