---
title: <customTrackingQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4e9e732d-911d-45a3-a569-4b5e9cd1ffbe
ms.openlocfilehash: 663dda571990a86dc71ea927c4e97241e0ed3fc1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59120082"
---
# <a name="customtrackingqueries"></a><span data-ttu-id="ad6d5-101">\<customTrackingQueries></span><span class="sxs-lookup"><span data-stu-id="ad6d5-101">\<customTrackingQueries></span></span>
<span data-ttu-id="ad6d5-102">コード アクティビティで定義するイベントを追跡するために使用する、クエリのコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="ad6d5-102">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="ad6d5-103">追跡参加要素がカスタム追跡レコードを定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="ad6d5-103">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="ad6d5-104">追跡プロファイルのクエリの詳細については、次を参照してください[追跡プロファイル。](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="ad6d5-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="ad6d5-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="ad6d5-105">\<system.serviceModel></span></span>  
<span data-ttu-id="ad6d5-106">\<追跡 ></span><span class="sxs-lookup"><span data-stu-id="ad6d5-106">\<tracking></span></span>  
<span data-ttu-id="ad6d5-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="ad6d5-107">\<trackingProfile></span></span>  
<span data-ttu-id="ad6d5-108">\<ワークフロー ></span><span class="sxs-lookup"><span data-stu-id="ad6d5-108">\<workflow></span></span>  
<span data-ttu-id="ad6d5-109">\<customTrackingQueries></span><span class="sxs-lookup"><span data-stu-id="ad6d5-109">\<customTrackingQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad6d5-110">構文</span><span class="sxs-lookup"><span data-stu-id="ad6d5-110">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <customTrackingQueries>
        <customTrackingQuery activityName="String" 
                             name="String" />
      </customTrackingQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ad6d5-111">属性および要素</span><span class="sxs-lookup"><span data-stu-id="ad6d5-111">Attributes and Elements</span></span>  
 <span data-ttu-id="ad6d5-112">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="ad6d5-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ad6d5-113">属性</span><span class="sxs-lookup"><span data-stu-id="ad6d5-113">Attributes</span></span>  
 <span data-ttu-id="ad6d5-114">なし。</span><span class="sxs-lookup"><span data-stu-id="ad6d5-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="ad6d5-115">子要素</span><span class="sxs-lookup"><span data-stu-id="ad6d5-115">Child Elements</span></span>  
  
|<span data-ttu-id="ad6d5-116">要素</span><span class="sxs-lookup"><span data-stu-id="ad6d5-116">Element</span></span>|<span data-ttu-id="ad6d5-117">説明</span><span class="sxs-lookup"><span data-stu-id="ad6d5-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ad6d5-118">\<customTrackingQuery></span><span class="sxs-lookup"><span data-stu-id="ad6d5-118">\<customTrackingQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/customtrackingquery.md)|<span data-ttu-id="ad6d5-119">コード アクティビティで定義するイベントを追跡するために使用するクエリ。</span><span class="sxs-lookup"><span data-stu-id="ad6d5-119">A query that is used to track events that you define in your code activities.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ad6d5-120">親要素</span><span class="sxs-lookup"><span data-stu-id="ad6d5-120">Parent Elements</span></span>  
  
|<span data-ttu-id="ad6d5-121">要素</span><span class="sxs-lookup"><span data-stu-id="ad6d5-121">Element</span></span>|<span data-ttu-id="ad6d5-122">説明</span><span class="sxs-lookup"><span data-stu-id="ad6d5-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ad6d5-123">\<workflow></span><span class="sxs-lookup"><span data-stu-id="ad6d5-123">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="ad6d5-124">識別される特定のワークフローのすべてのクエリを格納する構成要素、 **activityDefinitionId**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="ad6d5-124">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ad6d5-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="ad6d5-125">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="ad6d5-126">ワークフローの追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="ad6d5-126">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="ad6d5-127">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="ad6d5-127">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
