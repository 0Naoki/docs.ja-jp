---
title: <behaviors> ワークフローの
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 3c6017b6-0c4f-4192-bd67-9515f5d1ec82
ms.openlocfilehash: b7c5cf93a82ac88c25f9c478ad52cf41eb6f6d65
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59129208"
---
# <a name="behaviors-of-workflow"></a><span data-ttu-id="39f9f-102">\<動作 > のワークフロー</span><span class="sxs-lookup"><span data-stu-id="39f9f-102">\<behaviors> of workflow</span></span>
<span data-ttu-id="39f9f-103">この要素が含まれています、 **serviceBehaviors**コレクション。</span><span class="sxs-lookup"><span data-stu-id="39f9f-103">This element contains the **serviceBehaviors** collection.</span></span>  <span data-ttu-id="39f9f-104">コレクション内の各要素は、ワークフロー サービスによって使用されるそれぞれの動作要素を定義します。</span><span class="sxs-lookup"><span data-stu-id="39f9f-104">Each element in the collection defines behavior elements consumed by workflow services.</span></span> <span data-ttu-id="39f9f-105">各動作要素が、一意で識別される**名前**属性。</span><span class="sxs-lookup"><span data-stu-id="39f9f-105">Each behavior element is identified by its unique **name** attribute.</span></span>  
  
 <span data-ttu-id="39f9f-106">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="39f9f-106">\<system.ServiceModel></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39f9f-107">構文</span><span class="sxs-lookup"><span data-stu-id="39f9f-107">Syntax</span></span>  
  
```xml  
<behaviors>  
  <serviceBehaviors>  
  </serviceBehaviors>  
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="39f9f-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="39f9f-108">Attributes and Elements</span></span>  
 <span data-ttu-id="39f9f-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="39f9f-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="39f9f-110">属性</span><span class="sxs-lookup"><span data-stu-id="39f9f-110">Attributes</span></span>  
 <span data-ttu-id="39f9f-111">なし</span><span class="sxs-lookup"><span data-stu-id="39f9f-111">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="39f9f-112">子要素</span><span class="sxs-lookup"><span data-stu-id="39f9f-112">Child Elements</span></span>  
  
|<span data-ttu-id="39f9f-113">要素</span><span class="sxs-lookup"><span data-stu-id="39f9f-113">Element</span></span>|<span data-ttu-id="39f9f-114">説明</span><span class="sxs-lookup"><span data-stu-id="39f9f-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="39f9f-115">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="39f9f-115">\<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/servicebehaviors-of-workflow.md)|<span data-ttu-id="39f9f-116">この構成セクションは、特定のワークフロー サービスに対して定義されたすべての動作を表します。</span><span class="sxs-lookup"><span data-stu-id="39f9f-116">This configuration section represents all the behaviors defined for a specific workflow service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="39f9f-117">親要素</span><span class="sxs-lookup"><span data-stu-id="39f9f-117">Parent Elements</span></span>  
  
|<span data-ttu-id="39f9f-118">要素</span><span class="sxs-lookup"><span data-stu-id="39f9f-118">Element</span></span>|<span data-ttu-id="39f9f-119">説明</span><span class="sxs-lookup"><span data-stu-id="39f9f-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="39f9f-120">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="39f9f-120">\<system.serviceModel></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)|<span data-ttu-id="39f9f-121">すべてのワークフロー構成要素のルート要素。</span><span class="sxs-lookup"><span data-stu-id="39f9f-121">The root element of all workflow configuration elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="39f9f-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="39f9f-122">See also</span></span>

- <xref:System.ServiceModel.Configuration.BehaviorsSection>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElementCollection>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElement>
- [<span data-ttu-id="39f9f-123">動作を使用したランタイムの構成と拡張</span><span class="sxs-lookup"><span data-stu-id="39f9f-123">Configuring and Extending the Runtime with Behaviors</span></span>](../../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)
