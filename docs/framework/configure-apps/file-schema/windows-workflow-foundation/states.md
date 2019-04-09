---
title: <states>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: ebea5e7c-ad58-43c5-8f2d-cca25ae1b721
ms.openlocfilehash: 30cb2efa4c00c8b292a8ace6a03306d6ac76a7f4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59073123"
---
# <a name="states"></a><span data-ttu-id="17773-101">\<states></span><span class="sxs-lookup"><span data-stu-id="17773-101">\<states></span></span>
<span data-ttu-id="17773-102">追跡レコードが作成されたときの追跡ワークフロー インスタンスの定期受信済み状態のコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="17773-102">Represents a collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>  
  
 <span data-ttu-id="17773-103">追跡プロファイルのクエリの詳細については、次を参照してください[追跡プロファイル。](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="17773-103">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="17773-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="17773-104">\<system.serviceModel></span></span>  
<span data-ttu-id="17773-105">\<追跡 ></span><span class="sxs-lookup"><span data-stu-id="17773-105">\<tracking></span></span>  
<span data-ttu-id="17773-106">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="17773-106">\<trackingProfile></span></span>  
<span data-ttu-id="17773-107">\<ワークフロー ></span><span class="sxs-lookup"><span data-stu-id="17773-107">\<workflow></span></span>  
<span data-ttu-id="17773-108">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="17773-108">\<workflowInstanceQueries></span></span>  
<span data-ttu-id="17773-109">\<workflowInstanceQuery></span><span class="sxs-lookup"><span data-stu-id="17773-109">\<workflowInstanceQuery></span></span>  
<span data-ttu-id="17773-110">\<states></span><span class="sxs-lookup"><span data-stu-id="17773-110">\<states></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="17773-111">構文</span><span class="sxs-lookup"><span data-stu-id="17773-111">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <workflowInstanceQueries>
        <workflowInstanceQuery>
          <states>
            <state name="Name"/>
          </states>
        </workflowInstanceQuery>
      </workflowInstanceQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="17773-112">属性および要素</span><span class="sxs-lookup"><span data-stu-id="17773-112">Attributes and Elements</span></span>  
 <span data-ttu-id="17773-113">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="17773-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="17773-114">属性</span><span class="sxs-lookup"><span data-stu-id="17773-114">Attributes</span></span>  
 <span data-ttu-id="17773-115">なし。</span><span class="sxs-lookup"><span data-stu-id="17773-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="17773-116">子要素</span><span class="sxs-lookup"><span data-stu-id="17773-116">Child Elements</span></span>  
  
|<span data-ttu-id="17773-117">要素</span><span class="sxs-lookup"><span data-stu-id="17773-117">Element</span></span>|<span data-ttu-id="17773-118">説明</span><span class="sxs-lookup"><span data-stu-id="17773-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="17773-119">\<state></span><span class="sxs-lookup"><span data-stu-id="17773-119">\<state></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|<span data-ttu-id="17773-120">追跡レコードが作成されたときの追跡ワークフロー インスタンスの定期受信済み状態。</span><span class="sxs-lookup"><span data-stu-id="17773-120">A subscribed state from the tracked workflow instance when the tracking record is created.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="17773-121">親要素</span><span class="sxs-lookup"><span data-stu-id="17773-121">Parent Elements</span></span>  
  
|<span data-ttu-id="17773-122">要素</span><span class="sxs-lookup"><span data-stu-id="17773-122">Element</span></span>|<span data-ttu-id="17773-123">説明</span><span class="sxs-lookup"><span data-stu-id="17773-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="17773-124">\<workflowInstanceQuery></span><span class="sxs-lookup"><span data-stu-id="17773-124">\<workflowInstanceQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowinstancequery.md)|<span data-ttu-id="17773-125">開始したイベントや完了したイベントなど、ワークフロー インスタンスのライフサイクルの変化を追跡するクエリ。</span><span class="sxs-lookup"><span data-stu-id="17773-125">A query that tracks workflow instance life cycle changes such as a started or completed event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="17773-126">Remarks</span><span class="sxs-lookup"><span data-stu-id="17773-126">Remarks</span></span>  
 <span data-ttu-id="17773-127">返されたレコードは、このコレクションの状態でフィルター処理されます。</span><span class="sxs-lookup"><span data-stu-id="17773-127">The returned records are filtered by the states in this collection.</span></span>  
  
 <span data-ttu-id="17773-128">次の表に、有効な状態の値を示します。</span><span class="sxs-lookup"><span data-stu-id="17773-128">Possible state values are described in the following table.</span></span>  
  
|<span data-ttu-id="17773-129">状態</span><span class="sxs-lookup"><span data-stu-id="17773-129">State</span></span>|<span data-ttu-id="17773-130">説明</span><span class="sxs-lookup"><span data-stu-id="17773-130">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="17773-131">Aborted</span><span class="sxs-lookup"><span data-stu-id="17773-131">Aborted</span></span>|<span data-ttu-id="17773-132">ワークフロー インスタンスは中止されました。</span><span class="sxs-lookup"><span data-stu-id="17773-132">The workflow instance is aborted.</span></span>|  
|<span data-ttu-id="17773-133">完了</span><span class="sxs-lookup"><span data-stu-id="17773-133">Completed</span></span>|<span data-ttu-id="17773-134">ワークフロー インスタンスは完了しました。</span><span class="sxs-lookup"><span data-stu-id="17773-134">The workflow instance is completed.</span></span>|  
|<span data-ttu-id="17773-135">Deleted</span><span class="sxs-lookup"><span data-stu-id="17773-135">Deleted</span></span>|<span data-ttu-id="17773-136">ワークフロー インスタンスは削除されました。</span><span class="sxs-lookup"><span data-stu-id="17773-136">The workflow instance is deleted.</span></span>|  
|<span data-ttu-id="17773-137">Idle</span><span class="sxs-lookup"><span data-stu-id="17773-137">Idle</span></span>|<span data-ttu-id="17773-138">ワークフロー インスタンスはアイドル状態です。</span><span class="sxs-lookup"><span data-stu-id="17773-138">The workflow instance is idle.</span></span>|  
|<span data-ttu-id="17773-139">Persisted</span><span class="sxs-lookup"><span data-stu-id="17773-139">Persisted</span></span>|<span data-ttu-id="17773-140">ワークフロー インスタンスは永続化されました。</span><span class="sxs-lookup"><span data-stu-id="17773-140">The workflow instance is persisted.</span></span>|  
|<span data-ttu-id="17773-141">Resumed</span><span class="sxs-lookup"><span data-stu-id="17773-141">Resumed</span></span>|<span data-ttu-id="17773-142">ワークフロー インスタンスが再開されました。</span><span class="sxs-lookup"><span data-stu-id="17773-142">The workflow instance is resumed.</span></span>|  
|<span data-ttu-id="17773-143">開始</span><span class="sxs-lookup"><span data-stu-id="17773-143">Started</span></span>|<span data-ttu-id="17773-144">ワークフロー インスタンスが開始されました。</span><span class="sxs-lookup"><span data-stu-id="17773-144">The workflow instance is started.</span></span>|  
|<span data-ttu-id="17773-145">UnhandledException</span><span class="sxs-lookup"><span data-stu-id="17773-145">UnhandledException</span></span>|<span data-ttu-id="17773-146">ワークフロー インスタンスで未処理の例外が発生しました。</span><span class="sxs-lookup"><span data-stu-id="17773-146">The workflow instance encountered an unhandled exception.</span></span>|  
|<span data-ttu-id="17773-147">アンロードされました</span><span class="sxs-lookup"><span data-stu-id="17773-147">Unloaded</span></span>|<span data-ttu-id="17773-148">ワークフロー インスタンスはアンロードされました。</span><span class="sxs-lookup"><span data-stu-id="17773-148">The workflow instance is unloaded.</span></span>|  
|<span data-ttu-id="17773-149">Canceled</span><span class="sxs-lookup"><span data-stu-id="17773-149">Canceled</span></span>|<span data-ttu-id="17773-150">ワークフロー インスタンスは取り消されました。</span><span class="sxs-lookup"><span data-stu-id="17773-150">The workflow instance is canceled.</span></span>|  
|<span data-ttu-id="17773-151">Suspended</span><span class="sxs-lookup"><span data-stu-id="17773-151">Suspended</span></span>|<span data-ttu-id="17773-152">ワークフロー インスタンスが中断されています。</span><span class="sxs-lookup"><span data-stu-id="17773-152">The workflow instance is suspended.</span></span>|  
|<span data-ttu-id="17773-153">Terminated</span><span class="sxs-lookup"><span data-stu-id="17773-153">Terminated</span></span>|<span data-ttu-id="17773-154">ワークフロー インスタンスは終了しました。</span><span class="sxs-lookup"><span data-stu-id="17773-154">The workflow instance is terminated.</span></span>|  
|<span data-ttu-id="17773-155">Unsuspended</span><span class="sxs-lookup"><span data-stu-id="17773-155">Unsuspended</span></span>|<span data-ttu-id="17773-156">ワークフロー インスタンスの中断が解除されました。</span><span class="sxs-lookup"><span data-stu-id="17773-156">The workflow instance is unsuspended.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="17773-157">例</span><span class="sxs-lookup"><span data-stu-id="17773-157">Example</span></span>  
 <span data-ttu-id="17773-158">次の構成は、このクエリを使用して、`Started` インスタンス状態のワークフロー インスタンス レベルの追跡レコードを定期受信します。</span><span class="sxs-lookup"><span data-stu-id="17773-158">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="17773-159">関連項目</span><span class="sxs-lookup"><span data-stu-id="17773-159">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="17773-160">ワークフロー追跡とトレース</span><span class="sxs-lookup"><span data-stu-id="17773-160">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="17773-161">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="17773-161">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
