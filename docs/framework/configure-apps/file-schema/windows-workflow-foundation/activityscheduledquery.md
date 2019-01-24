---
title: '&lt;activityScheduledQuery&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: a8bcd6d4-b389-4daf-86bf-1ade85fec114
ms.openlocfilehash: 0e69c32a7c292fda90828396c402c95e4899600a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54687441"
---
# <a name="ltactivityscheduledquerygt"></a><span data-ttu-id="76f0b-102">&lt;activityScheduledQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="76f0b-102">&lt;activityScheduledQuery&gt;</span></span>
<span data-ttu-id="76f0b-103">親アクティビティによる実行がスケジュールされているアクティビティを追跡するために使用する、クエリのコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="76f0b-103">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="76f0b-104">アクティビティがスケジュールされたレコードを追跡参加要素が定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="76f0b-104">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
 <span data-ttu-id="76f0b-105">追跡プロファイルのクエリの詳細については、次を参照してください[追跡プロファイル。](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="76f0b-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="76f0b-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="76f0b-106">\<system.serviceModel></span></span>  
<span data-ttu-id="76f0b-107">\<追跡 ></span><span class="sxs-lookup"><span data-stu-id="76f0b-107">\<tracking></span></span>  
<span data-ttu-id="76f0b-108">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="76f0b-108">\<trackingProfile></span></span>  
<span data-ttu-id="76f0b-109">\<ワークフロー ></span><span class="sxs-lookup"><span data-stu-id="76f0b-109">\<workflow></span></span>  
<span data-ttu-id="76f0b-110">\<activityScheduledQueries></span><span class="sxs-lookup"><span data-stu-id="76f0b-110">\<activityScheduledQueries></span></span>  
<span data-ttu-id="76f0b-111">\<activityScheduledQuery></span><span class="sxs-lookup"><span data-stu-id="76f0b-111">\<activityScheduledQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76f0b-112">構文</span><span class="sxs-lookup"><span data-stu-id="76f0b-112">Syntax</span></span>  
  
```xml 
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityScheduledQueries>
        <activityScheduledQuery activityName="String" 
                                childActivityName="String"/>
      </activityScheduledQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="76f0b-113">属性および要素</span><span class="sxs-lookup"><span data-stu-id="76f0b-113">Attributes and Elements</span></span>  
 <span data-ttu-id="76f0b-114">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="76f0b-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="76f0b-115">属性</span><span class="sxs-lookup"><span data-stu-id="76f0b-115">Attributes</span></span>  
  
|<span data-ttu-id="76f0b-116">属性</span><span class="sxs-lookup"><span data-stu-id="76f0b-116">Attribute</span></span>|<span data-ttu-id="76f0b-117">説明</span><span class="sxs-lookup"><span data-stu-id="76f0b-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="76f0b-118">activityName</span><span class="sxs-lookup"><span data-stu-id="76f0b-118">activityName</span></span>|<span data-ttu-id="76f0b-119">キャンセルを要求しているアクティビティの名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="76f0b-119">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|<span data-ttu-id="76f0b-120">childActivityName</span><span class="sxs-lookup"><span data-stu-id="76f0b-120">childActivityName</span></span>|<span data-ttu-id="76f0b-121">キャンセルが要求された子アクティビティの名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="76f0b-121">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="76f0b-122">子要素</span><span class="sxs-lookup"><span data-stu-id="76f0b-122">Child Elements</span></span>  
 <span data-ttu-id="76f0b-123">なし。</span><span class="sxs-lookup"><span data-stu-id="76f0b-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="76f0b-124">親要素</span><span class="sxs-lookup"><span data-stu-id="76f0b-124">Parent Elements</span></span>  
  
|<span data-ttu-id="76f0b-125">要素</span><span class="sxs-lookup"><span data-stu-id="76f0b-125">Element</span></span>|<span data-ttu-id="76f0b-126">説明</span><span class="sxs-lookup"><span data-stu-id="76f0b-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="76f0b-127">\<activityScheduledQuery></span><span class="sxs-lookup"><span data-stu-id="76f0b-127">\<activityScheduledQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activityscheduledquery.md)|<span data-ttu-id="76f0b-128">親アクティビティによる実行がスケジュールされているアクティビティを追跡するために使用するクエリ。</span><span class="sxs-lookup"><span data-stu-id="76f0b-128">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="76f0b-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="76f0b-129">See also</span></span>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityScheduledQuery?displayProperty=nameWithType>
- [<span data-ttu-id="76f0b-130">ワークフローの追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="76f0b-130">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="76f0b-131">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="76f0b-131">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
