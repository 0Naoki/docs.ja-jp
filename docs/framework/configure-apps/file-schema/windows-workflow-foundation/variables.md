---
title: <variables>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: da0fd144-dda9-4613-b650-fe6325076513
ms.openlocfilehash: 3ff568c267331538fb9be0e6cb40eebbca44d882
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/30/2019
ms.locfileid: "55276550"
---
# <a name="variables"></a><span data-ttu-id="bbaec-101">\<variables></span><span class="sxs-lookup"><span data-stu-id="bbaec-101">\<variables></span></span>
<span data-ttu-id="bbaec-102">このアクティビティ クエリに関連付けられている変数のコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="bbaec-102">Represents a collection of variables associated with this activity query.</span></span>  
  
 <span data-ttu-id="bbaec-103">追跡プロファイルのクエリの詳細については、次を参照してください。[追跡プロファイル](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)します。</span><span class="sxs-lookup"><span data-stu-id="bbaec-103">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="bbaec-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="bbaec-104">\<system.serviceModel></span></span>  
<span data-ttu-id="bbaec-105">\<追跡 ></span><span class="sxs-lookup"><span data-stu-id="bbaec-105">\<tracking></span></span>  
<span data-ttu-id="bbaec-106">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="bbaec-106">\<trackingProfile></span></span>  
<span data-ttu-id="bbaec-107">\<ワークフロー ></span><span class="sxs-lookup"><span data-stu-id="bbaec-107">\<workflow></span></span>  
<span data-ttu-id="bbaec-108">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="bbaec-108">\<activityStateQueries></span></span>  
<span data-ttu-id="bbaec-109">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="bbaec-109">\<activityStateQuery></span></span>  
<span data-ttu-id="bbaec-110">\<variables></span><span class="sxs-lookup"><span data-stu-id="bbaec-110">\<variables></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bbaec-111">構文</span><span class="sxs-lookup"><span data-stu-id="bbaec-111">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityStateQueries>
        <activityStateQuery activityName="String" />
        <variables>
          <variable name="String" />
        </variables>
      </activityStateQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bbaec-112">属性および要素</span><span class="sxs-lookup"><span data-stu-id="bbaec-112">Attributes and Elements</span></span>  
 <span data-ttu-id="bbaec-113">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="bbaec-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bbaec-114">属性</span><span class="sxs-lookup"><span data-stu-id="bbaec-114">Attributes</span></span>  
 <span data-ttu-id="bbaec-115">なし。</span><span class="sxs-lookup"><span data-stu-id="bbaec-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="bbaec-116">子要素</span><span class="sxs-lookup"><span data-stu-id="bbaec-116">Child Elements</span></span>  
  
|<span data-ttu-id="bbaec-117">要素</span><span class="sxs-lookup"><span data-stu-id="bbaec-117">Element</span></span>|<span data-ttu-id="bbaec-118">説明</span><span class="sxs-lookup"><span data-stu-id="bbaec-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bbaec-119">\<variable></span><span class="sxs-lookup"><span data-stu-id="bbaec-119">\<variable></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/variable.md)|<span data-ttu-id="bbaec-120">アクティビティ状態クエリに関連付けられている変数。</span><span class="sxs-lookup"><span data-stu-id="bbaec-120">A variable associated with an activity state query.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="bbaec-121">親要素</span><span class="sxs-lookup"><span data-stu-id="bbaec-121">Parent Elements</span></span>  
  
|<span data-ttu-id="bbaec-122">要素</span><span class="sxs-lookup"><span data-stu-id="bbaec-122">Element</span></span>|<span data-ttu-id="bbaec-123">説明</span><span class="sxs-lookup"><span data-stu-id="bbaec-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bbaec-124">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="bbaec-124">\<activityStateQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md)|<span data-ttu-id="bbaec-125">親アクティビティが子アクティビティを取り消すための要求を追跡するのに使用する構成要素を表します。</span><span class="sxs-lookup"><span data-stu-id="bbaec-125">Represents a configuration element that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="bbaec-126">追跡参加要素がキャンセル要求レコード オブジェクトを定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="bbaec-126">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bbaec-127">Remarks</span><span class="sxs-lookup"><span data-stu-id="bbaec-127">Remarks</span></span>  
 <span data-ttu-id="bbaec-128">ActivityStateQuery の固有の機能の 1 つは、ワークフローの実行を追跡するときにデータを抽出する機能です。</span><span class="sxs-lookup"><span data-stu-id="bbaec-128">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="bbaec-129">これにより、実行後に追跡レコードにアクセスするときにコンテキストが追加されます。</span><span class="sxs-lookup"><span data-stu-id="bbaec-129">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="bbaec-130">使用することができます、 [\<引数 >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md)、 [\<状態 >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)と[\<状態 >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)任意の変数または引数を抽出する要素ワークフロー内の任意のアクティビティから</span><span class="sxs-lookup"><span data-stu-id="bbaec-130">You can use the [\<arguments>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) and [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="bbaec-131">次の例は、アクティビティの `Closed` 追跡レコードが生成されたときに変数と引数を抽出するアクティビティ状態クエリを示しています。</span><span class="sxs-lookup"><span data-stu-id="bbaec-131">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="bbaec-132">ActivityStateRecord でのみ抽出できるし、追跡のため購読中の変数と引数を使用してプロファイル[ \<activityStateQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md)します。</span><span class="sxs-lookup"><span data-stu-id="bbaec-132">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span></span>  
  
```xml  
<activityStateQuery activityName="SendEmailActivity">  
  <states>  
    <state name="Closed"/>  
  </states>  
  <variables>  
    <variable name="FromAddress"/>  
  </variables>  
  <arguments>  
    <argument name="Result"/>  
  </arguments>  
</activityStateQuery>  
```  
  
## <a name="see-also"></a><span data-ttu-id="bbaec-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="bbaec-133">See also</span></span>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.VariableElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="bbaec-134">ワークフローの追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="bbaec-134">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="bbaec-135">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="bbaec-135">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
