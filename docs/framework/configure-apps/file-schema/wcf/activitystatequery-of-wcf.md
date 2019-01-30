---
title: <activityStateQuery> WCF の
ms.date: 03/30/2017
ms.assetid: d6cdc04b-6f3a-4097-a623-ee4a1be3b5c4
ms.openlocfilehash: 97fce512415ad6ae165b29c7e8eff3394d5e675a
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/30/2019
ms.locfileid: "55254796"
---
# <a name="activitystatequery-of-wcf"></a><span data-ttu-id="28946-102">\<activityStateQuery > の WCF</span><span class="sxs-lookup"><span data-stu-id="28946-102">\<activityStateQuery> of WCF</span></span>

<span data-ttu-id="28946-103">ワークフロー インスタンスを構成するアクティビティのライフサイクルの変化を追跡するために使用されるクエリを表します。</span><span class="sxs-lookup"><span data-stu-id="28946-103">Represents a query that is used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="28946-104">たとえば、ワークフロー インスタンス内で、「電子メールの送信」アクティビティが完了するたびの追跡する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="28946-104">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="28946-105">追跡参加要素がアクティビティ状態レコード オブジェクトを定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="28946-105">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="28946-106">定期受信可能な状態は ActivityStates で指定します。</span><span class="sxs-lookup"><span data-stu-id="28946-106">The available states to subscribe to are specified in ActivityStates.</span></span>  
  
<span data-ttu-id="28946-107">追跡プロファイルのクエリの詳細については、次を参照してください。[追跡プロファイル](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)します。</span><span class="sxs-lookup"><span data-stu-id="28946-107">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>

<span data-ttu-id="28946-108">\<system.serviceModel> \<tracking></span><span class="sxs-lookup"><span data-stu-id="28946-108">\<system.serviceModel> \<tracking></span></span>  
<span data-ttu-id="28946-109">\<プロファイル > \<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="28946-109">\<profiles> \<trackingProfile></span></span>  
<span data-ttu-id="28946-110">\<ワークフロー ></span><span class="sxs-lookup"><span data-stu-id="28946-110">\<workflow></span></span>  
<span data-ttu-id="28946-111">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="28946-111">\<activityStateQueries></span></span>  
<span data-ttu-id="28946-112">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="28946-112">\<activityStateQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28946-113">構文</span><span class="sxs-lookup"><span data-stu-id="28946-113">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <activityStateQueries>
          <activityStateQuery activityName="String">
            <arguments>
              <argument name="String" />
            </arguments>
            <states>
              <state name="String" />
            </states>
            <variables>
              <variable name="String" />
            </variables>
          </activityStateQuery>
        </activityStateQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="28946-114">属性と要素</span><span class="sxs-lookup"><span data-stu-id="28946-114">Attributes and elements</span></span>  

<span data-ttu-id="28946-115">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="28946-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="28946-116">属性</span><span class="sxs-lookup"><span data-stu-id="28946-116">Attributes</span></span>  
  
|<span data-ttu-id="28946-117">属性</span><span class="sxs-lookup"><span data-stu-id="28946-117">Attribute</span></span>|<span data-ttu-id="28946-118">説明</span><span class="sxs-lookup"><span data-stu-id="28946-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="28946-119">activityName</span><span class="sxs-lookup"><span data-stu-id="28946-119">activityName</span></span>|<span data-ttu-id="28946-120"><xref:System.Activities.Tracking.ActivityStateRecord> インスタンスをフィルターするために、アクティビティの名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="28946-120">A string that specifies the name of the activity to filter <xref:System.Activities.Tracking.ActivityStateRecord> instances on.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="28946-121">子要素</span><span class="sxs-lookup"><span data-stu-id="28946-121">Child elements</span></span>  
  
|<span data-ttu-id="28946-122">要素</span><span class="sxs-lookup"><span data-stu-id="28946-122">Element</span></span>|<span data-ttu-id="28946-123">説明</span><span class="sxs-lookup"><span data-stu-id="28946-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="28946-124">\<arguments></span><span class="sxs-lookup"><span data-stu-id="28946-124">\<arguments></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md)|<span data-ttu-id="28946-125">このアクティビティ クエリに関連付けられている引数のコレクション。</span><span class="sxs-lookup"><span data-stu-id="28946-125">A collection of arguments associated with this activity query.</span></span>|  
|[<span data-ttu-id="28946-126">\<states></span><span class="sxs-lookup"><span data-stu-id="28946-126">\<states></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|<span data-ttu-id="28946-127">追跡レコードを生成する必要がある定期受信済みアクティビティの状態を含む構成要素のコレクション。</span><span class="sxs-lookup"><span data-stu-id="28946-127">A collection of configuration elements that contain the states of the subscribed activity for which a tracking record should be emitted.</span></span>|  
|[<span data-ttu-id="28946-128">\<states></span><span class="sxs-lookup"><span data-stu-id="28946-128">\<states></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|<span data-ttu-id="28946-129">このアクティビティ クエリに関連付けられている変数のコレクション。</span><span class="sxs-lookup"><span data-stu-id="28946-129">A collection of variables associated with this activity query.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="28946-130">親要素</span><span class="sxs-lookup"><span data-stu-id="28946-130">Parent elements</span></span>  
  
|<span data-ttu-id="28946-131">要素</span><span class="sxs-lookup"><span data-stu-id="28946-131">Element</span></span>|<span data-ttu-id="28946-132">説明</span><span class="sxs-lookup"><span data-stu-id="28946-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="28946-133">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="28946-133">\<faultPropagationQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationquery.md)|<span data-ttu-id="28946-134">親アクティビティが子アクティビティを取り消すための要求を追跡するのに使用する構成要素の一覧を表します。</span><span class="sxs-lookup"><span data-stu-id="28946-134">Represents a list of configuration elements that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="28946-135">追跡参加要素がキャンセル要求レコード オブジェクトを定期受信するには、このクエリが必要です。</span><span class="sxs-lookup"><span data-stu-id="28946-135">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="28946-136">Remarks</span><span class="sxs-lookup"><span data-stu-id="28946-136">Remarks</span></span>

<span data-ttu-id="28946-137">ActivityStateQuery の固有の機能の 1 つは、ワークフローの実行を追跡するときにデータを抽出する機能です。</span><span class="sxs-lookup"><span data-stu-id="28946-137">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="28946-138">これにより、実行後に追跡レコードにアクセスするときにコンテキストが追加されます。</span><span class="sxs-lookup"><span data-stu-id="28946-138">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="28946-139">使用することができます、 [\<引数 >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md)、 [\<状態 >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)と[\<状態 >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)任意の変数または引数を抽出する要素ワークフロー内の任意のアクティビティから次の例では、アクティビティ状態クエリ変数と引数を抽出するときに、アクティビティの`Closed`追跡レコードが生成されます。</span><span class="sxs-lookup"><span data-stu-id="28946-139">You can use the [\<arguments>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) and [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="28946-140">ActivityStateRecord でのみ抽出できるし、追跡のため購読中の変数と引数を使用してプロファイル[ \<activityStateQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md)します。</span><span class="sxs-lookup"><span data-stu-id="28946-140">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span></span>  
  
```xml  
<activityStateQuery activityName="SendEmailActivity">
  <states>
    <state name="Closed" />
  </states>
  <variables>
    <variable name="FromAddress" />
  </variables>
  <arguments>
    <argument name="Result" />
  </arguments>
</activityStateQuery>
```  
  
## <a name="see-also"></a><span data-ttu-id="28946-141">関連項目</span><span class="sxs-lookup"><span data-stu-id="28946-141">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElement>
- <xref:System.Activities.Tracking.ActivityStateQuery>
- [<span data-ttu-id="28946-142">ワークフローの追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="28946-142">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="28946-143">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="28946-143">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
