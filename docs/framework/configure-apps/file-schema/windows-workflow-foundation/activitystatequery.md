---
title: '&lt;activityStateQuery&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 9f8c3e4f-e2e3-4402-9760-03bf918ece7b
ms.openlocfilehash: 3c6243e6b8e1d2b32dc830609a5d4df474f48e61
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2018
ms.locfileid: "53151175"
---
# <a name="ltactivitystatequerygt"></a><span data-ttu-id="9cf85-102">&lt;activityStateQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="9cf85-102">&lt;activityStateQuery&gt;</span></span>
<span data-ttu-id="9cf85-103">ワークフロー インスタンスを構成するアクティビティのライフサイクルの変化を追跡するために使用されるクエリを表します。</span><span class="sxs-lookup"><span data-stu-id="9cf85-103">Represents a query that is used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="9cf85-104">たとえば、ワークフロー インスタンス内で、「電子メールの送信」アクティビティが完了するたびの追跡する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9cf85-104">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="9cf85-105">追跡参加要素がアクティビティ状態レコード オブジェクトを定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="9cf85-105">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="9cf85-106">定期受信可能な状態は ActivityStates で指定します。</span><span class="sxs-lookup"><span data-stu-id="9cf85-106">The available states to subscribe to are specified in ActivityStates.</span></span>  
  
 <span data-ttu-id="9cf85-107">追跡プロファイルのクエリの詳細については、次を参照してください。[追跡プロファイル](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)します。</span><span class="sxs-lookup"><span data-stu-id="9cf85-107">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="9cf85-108">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="9cf85-108">\<system.serviceModel></span></span>  
<span data-ttu-id="9cf85-109">\<追跡 ></span><span class="sxs-lookup"><span data-stu-id="9cf85-109">\<tracking></span></span>  
<span data-ttu-id="9cf85-110">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="9cf85-110">\<trackingProfile></span></span>  
<span data-ttu-id="9cf85-111">\<ワークフロー ></span><span class="sxs-lookup"><span data-stu-id="9cf85-111">\<workflow></span></span>  
<span data-ttu-id="9cf85-112">\<activityStateQueries ></span><span class="sxs-lookup"><span data-stu-id="9cf85-112">\<activityStateQueries></span></span>  
<span data-ttu-id="9cf85-113">\<activityStateQuery ></span><span class="sxs-lookup"><span data-stu-id="9cf85-113">\<activityStateQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9cf85-114">構文</span><span class="sxs-lookup"><span data-stu-id="9cf85-114">Syntax</span></span>  
  
```xml
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityStateQueries>
        <activityStateQuery activityName="String" />
        <arguments>
          <argument name="String"/>
        </arguments>
        <states>
          <state name="String"/>
        </states>
        <variables>
          <variable name="String"/>
        </variables>
      </activityStateQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9cf85-115">属性および要素</span><span class="sxs-lookup"><span data-stu-id="9cf85-115">Attributes and Elements</span></span>  
 <span data-ttu-id="9cf85-116">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="9cf85-116">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9cf85-117">属性</span><span class="sxs-lookup"><span data-stu-id="9cf85-117">Attributes</span></span>  
  
|<span data-ttu-id="9cf85-118">属性</span><span class="sxs-lookup"><span data-stu-id="9cf85-118">Attribute</span></span>|<span data-ttu-id="9cf85-119">説明</span><span class="sxs-lookup"><span data-stu-id="9cf85-119">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9cf85-120">activityName</span><span class="sxs-lookup"><span data-stu-id="9cf85-120">activityName</span></span>|<span data-ttu-id="9cf85-121"><xref:System.Activities.Tracking.ActivityStateRecord> インスタンスをフィルターするために、アクティビティの名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="9cf85-121">A string that specifies the name of the activity to filter <xref:System.Activities.Tracking.ActivityStateRecord> instances on.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9cf85-122">子要素</span><span class="sxs-lookup"><span data-stu-id="9cf85-122">Child Elements</span></span>  
  
|<span data-ttu-id="9cf85-123">要素</span><span class="sxs-lookup"><span data-stu-id="9cf85-123">Element</span></span>|<span data-ttu-id="9cf85-124">説明</span><span class="sxs-lookup"><span data-stu-id="9cf85-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9cf85-125">\<引数 ></span><span class="sxs-lookup"><span data-stu-id="9cf85-125">\<arguments></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md)|<span data-ttu-id="9cf85-126">このアクティビティ クエリに関連付けられている引数のコレクション。</span><span class="sxs-lookup"><span data-stu-id="9cf85-126">A collection of arguments associated with this activity query.</span></span>|  
|[<span data-ttu-id="9cf85-127">\<状態 ></span><span class="sxs-lookup"><span data-stu-id="9cf85-127">\<states></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|<span data-ttu-id="9cf85-128">追跡レコードを生成する必要がある定期受信済みアクティビティの状態を含む構成要素のコレクション。</span><span class="sxs-lookup"><span data-stu-id="9cf85-128">A collection of configuration elements that contain the states of the subscribed activity for which a tracking record should be emitted.</span></span>|  
|[<span data-ttu-id="9cf85-129">\<状態 ></span><span class="sxs-lookup"><span data-stu-id="9cf85-129">\<states></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|<span data-ttu-id="9cf85-130">このアクティビティ クエリに関連付けられている変数のコレクション。</span><span class="sxs-lookup"><span data-stu-id="9cf85-130">A collection of variables associated with this activity query.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9cf85-131">親要素</span><span class="sxs-lookup"><span data-stu-id="9cf85-131">Parent Elements</span></span>  
  
|<span data-ttu-id="9cf85-132">要素</span><span class="sxs-lookup"><span data-stu-id="9cf85-132">Element</span></span>|<span data-ttu-id="9cf85-133">説明</span><span class="sxs-lookup"><span data-stu-id="9cf85-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9cf85-134">\<faultPropagationQuery ></span><span class="sxs-lookup"><span data-stu-id="9cf85-134">\<faultPropagationQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationquery.md)|<span data-ttu-id="9cf85-135">親アクティビティが子アクティビティを取り消すための要求を追跡するのに使用する構成要素の一覧を表します。</span><span class="sxs-lookup"><span data-stu-id="9cf85-135">Represents a list of configuration elements that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="9cf85-136">追跡参加要素がキャンセル要求レコード オブジェクトを定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="9cf85-136">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9cf85-137">Remarks</span><span class="sxs-lookup"><span data-stu-id="9cf85-137">Remarks</span></span>  
 <span data-ttu-id="9cf85-138">ActivityStateQuery の固有の機能の 1 つは、ワークフローの実行を追跡するときにデータを抽出する機能です。</span><span class="sxs-lookup"><span data-stu-id="9cf85-138">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="9cf85-139">これにより、実行後に追跡レコードにアクセスするときにコンテキストが追加されます。</span><span class="sxs-lookup"><span data-stu-id="9cf85-139">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="9cf85-140">使用することができます、 [\<引数 >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md)、 [\<状態 >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)と[\<状態 >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)任意の変数または引数を抽出する要素ワークフロー内の任意のアクティビティから</span><span class="sxs-lookup"><span data-stu-id="9cf85-140">You can use the [\<arguments>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) and [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="9cf85-141">次の例は、アクティビティの `Closed` 追跡レコードが生成されたときに変数と引数を抽出するアクティビティ状態クエリを示しています。</span><span class="sxs-lookup"><span data-stu-id="9cf85-141">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="9cf85-142">ActivityStateRecord でのみ抽出できるし、追跡のため購読中の変数と引数を使用してプロファイル[ \<activityStateQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md)します。</span><span class="sxs-lookup"><span data-stu-id="9cf85-142">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="9cf85-143">関連項目</span><span class="sxs-lookup"><span data-stu-id="9cf85-143">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElement?displayProperty=nameWithType>       
 <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>       
 [<span data-ttu-id="9cf85-144">ワークフローの追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="9cf85-144">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="9cf85-145">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="9cf85-145">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
