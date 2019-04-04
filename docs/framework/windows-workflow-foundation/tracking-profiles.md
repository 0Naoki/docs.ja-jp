---
title: 追跡プロファイル
ms.date: 03/30/2017
ms.assetid: 22682566-1cd9-4672-9791-fb3523638e18
ms.openlocfilehash: 2fa4d65a6f0056824b2fc9dd67b93608777fc75d
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/09/2019
ms.locfileid: "57721373"
---
# <a name="tracking-profiles"></a><span data-ttu-id="4f36d-102">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="4f36d-102">Tracking Profiles</span></span>

<span data-ttu-id="4f36d-103">追跡プロファイルには、実行時にワークフロー インスタンスの状態が変化したときに生成されるワークフロー イベントを追跡参加要素が定期受信することを可能にする追跡クエリが含まれています。</span><span class="sxs-lookup"><span data-stu-id="4f36d-103">Tracking profiles contain tracking queries that permit a tracking participant to subscribe to workflow events that are emitted when the state of a workflow instance changes at runtime.</span></span>

## <a name="tracking-profiles"></a><span data-ttu-id="4f36d-104">追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="4f36d-104">Tracking Profiles</span></span>

<span data-ttu-id="4f36d-105">追跡プロファイルは、どの追跡情報をワーク フロー インスタンスに出力するかを指定するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="4f36d-105">Tracking profiles are used to specify which tracking information is emitted for a workflow instance.</span></span> <span data-ttu-id="4f36d-106">プロファイルが指定されていない場合、すべての追跡イベントが出力されます。</span><span class="sxs-lookup"><span data-stu-id="4f36d-106">If no profile is specified, then all tracking events are emitted.</span></span> <span data-ttu-id="4f36d-107">プロファイルを指定した場合、プロファイルで指定された追跡イベントが出力されます。</span><span class="sxs-lookup"><span data-stu-id="4f36d-107">If a profile is specified, then the tracking events specified in the profile will be emitted.</span></span> <span data-ttu-id="4f36d-108">監視の要件に応じて、ワークフローの主な状態変化の少数のセットを定期受信する、非常に一般的なプロファイルを作成できます。</span><span class="sxs-lookup"><span data-stu-id="4f36d-108">Depending on your monitoring requirements, you may write a profile that is very general, which subscribes to a small set of high-level state changes on a workflow.</span></span> <span data-ttu-id="4f36d-109">それとは反対に、結果として得られるイベントが、後で詳細な実行フローを十分に再構築できる極めて詳細なプロファイルを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="4f36d-109">Conversely, you may create a very detailed profile whose resulting events are rich enough to reconstruct a detailed execution flow later.</span></span>

<span data-ttu-id="4f36d-110">追跡プロファイルは、標準の [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] 構成ファイル内の XML 要素や、コードで指定される XML 要素として出現します。</span><span class="sxs-lookup"><span data-stu-id="4f36d-110">Tracking profiles manifest themselves as XML elements within a standard [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] configuration file or specified in code.</span></span> <span data-ttu-id="4f36d-111">追跡参加要素が [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] と `Started` のワークフロー イベントを定期受信できるようにする構成ファイルの `Completed` 追跡プロファイルの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="4f36d-111">The following example is of a [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] tracking profile in a configuration file that allows a tracking participant to subscribe to the `Started` and `Completed` workflow events.</span></span>

```xml
<system.serviceModel>
    ...
    <tracking>
      <trackingProfile name="Sample Tracking Profile">
        <workflow activityDefinitionId="*">
          <workflowInstanceQueries>
            <workflowInstanceQuery>
              <states>
                <state name="Started"/>
                <state name="Completed"/>
              </states>
            </workflowInstanceQuery>
          </workflowInstanceQueries>
        </workflow>
      </trackingProfile>
    </profiles>
  </tracking>
    ...
</system.serviceModel>
```

<span data-ttu-id="4f36d-112">次の例では、コードを使用して作成された同等の追跡プロファイルを示します。</span><span class="sxs-lookup"><span data-stu-id="4f36d-112">The following example shows the equivalent tracking profile created using code.</span></span>

```csharp
TrackingProfile profile = new TrackingProfile()
{
    Name = "CustomTrackingProfile",
    Queries =
    {
        new WorkflowInstanceQuery()
        {
            // Limit workflow instance tracking records for started and
            // completed workflow states.
            States = { WorkflowInstanceStates.Started, WorkflowInstanceStates.Completed },
        }
    }
};
```

<span data-ttu-id="4f36d-113">追跡レコードは、<xref:System.Activities.Tracking.ImplementationVisibility> 属性を使用して、追跡プロファイル内部の表示モードを通じてフィルター処理されます。</span><span class="sxs-lookup"><span data-stu-id="4f36d-113">Tracking records are filtered through the visibility mode within a tracking profile by using the <xref:System.Activities.Tracking.ImplementationVisibility> attribute.</span></span> <span data-ttu-id="4f36d-114">複合アクティビティは、その実装を形成する他のアクティビティを含む最上位アクティビティです。</span><span class="sxs-lookup"><span data-stu-id="4f36d-114">A composite activity is a top-level activity that contains other activities that form its implementation.</span></span> <span data-ttu-id="4f36d-115">表示モードは、実装を形成するアクティビティが追跡されているかどうかを指定するために、ワークフロー アクティビティ内の複合アクティビティから生成された追跡レコードを指定します。</span><span class="sxs-lookup"><span data-stu-id="4f36d-115">The visibility mode specifies the tracking records emitted from composite activities within a workflow activity, to specify if activities that form the implementation are being tracked.</span></span> <span data-ttu-id="4f36d-116">表示モードは、追跡プロファイル レベルで適用されます。</span><span class="sxs-lookup"><span data-stu-id="4f36d-116">The visibility mode applies at the tracking profile level.</span></span> <span data-ttu-id="4f36d-117">ワークフロー内にある個々のアクティビティの追跡レコードのフィルター処理は、追跡プロファイル内のクエリによって制御されます。</span><span class="sxs-lookup"><span data-stu-id="4f36d-117">The filtering of tracking records for individual activities within a workflow is controlled by the queries within the tracking profile.</span></span> <span data-ttu-id="4f36d-118">詳細については、、**追跡プロファイルのクエリの種類**このドキュメントの「を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4f36d-118">For more information, see the **Tracking Profile Query Types** section in this document.</span></span>

<span data-ttu-id="4f36d-119">追跡プロファイルの `implementationVisibility` 属性で指定される 2 つの表示モードは、`RootScope` と `All` です。</span><span class="sxs-lookup"><span data-stu-id="4f36d-119">The two visibility modes specified by the `implementationVisibility` attribute in the tracking profile are `RootScope` and `All`.</span></span> <span data-ttu-id="4f36d-120">`RootScope` モードを使用すると、複合アクティビティがワークフローのルート アクティビティでない場合にアクティビティの実装を形成するアクティビティの追跡レコードが抑制されます。</span><span class="sxs-lookup"><span data-stu-id="4f36d-120">Using the `RootScope` mode suppresses the tracking records for activities that form the implementation of an activity in the case where a composite activity is not the root of a workflow.</span></span> <span data-ttu-id="4f36d-121">したがって、他のアクティビティを使用して実装されているアクティビティがワークフローに追加された場合、`implementationVisibility` が RootScope に設定されていると、その複合アクティビティ内の最上位アクティビティのみが追跡されます。</span><span class="sxs-lookup"><span data-stu-id="4f36d-121">This implies that, when an activity that is implemented using other activities is added to a workflow, and the `implementationVisibility` set to RootScope, only the top-level activity within that composite activity is tracked.</span></span> <span data-ttu-id="4f36d-122">アクティビティがワークフローのルート アクティビティである場合、アクティビティの実装はワークフローそのものであり、追跡レコードはその実装を形成するアクティビティを対象として生成されます。</span><span class="sxs-lookup"><span data-stu-id="4f36d-122">If an activity is the root of the workflow, then the implementation of the activity is the workflow itself and tracking records are emitted for activities that form the implementation.</span></span> <span data-ttu-id="4f36d-123">All モードを使用すると、ルート アクティビティとそのすべての複合アクティビティを対象として、すべての追跡レコードを生成できます。</span><span class="sxs-lookup"><span data-stu-id="4f36d-123">Using the All mode permits all tracking records to be emitted for the root activity and all its composite activities.</span></span>

<span data-ttu-id="4f36d-124">たとえば、 *MyActivity*複合アクティビティの実装には、2 つのアクティビティが含まれています*Activity1*と*Activity2*します。</span><span class="sxs-lookup"><span data-stu-id="4f36d-124">For example, suppose *MyActivity* is a composite activity whose implementation contains two activities, *Activity1* and *Activity2*.</span></span> <span data-ttu-id="4f36d-125">このアクティビティがワークフローに追加され、された追跡プロファイルの追跡が有効になっている`implementationVisibility`に設定`RootScope`、に対してのみ追跡レコードが出力されます*MyActivity*します。</span><span class="sxs-lookup"><span data-stu-id="4f36d-125">When this activity is added to a workflow and tracking is enabled with a tracking profile with `implementationVisibility` set to `RootScope`, tracking records are emitted only for *MyActivity*.</span></span> <span data-ttu-id="4f36d-126">ただし、レコードは生成されませんアクティビティ*Activity1*と*Activity2*します。</span><span class="sxs-lookup"><span data-stu-id="4f36d-126">However, no records are emitted for activities *Activity1* and *Activity2*.</span></span>

<span data-ttu-id="4f36d-127">ただし場合、`implementationVisibility`属性に設定されている追跡プロファイルを`All`、だけでなく追跡レコードが出力されますし、 *MyActivity*がアクティビティについても*Activity1*と*Activity2*します。</span><span class="sxs-lookup"><span data-stu-id="4f36d-127">However, if the `implementationVisibility` attribute for the tracking profile is  set to `All`, then tracking records are emitted not only for *MyActivity*, but also for activities *Activity1* and *Activity2*.</span></span>

<span data-ttu-id="4f36d-128">
  `implementationVisibility\` フラグは、次の追跡レコード タイプに適用されます。</span><span class="sxs-lookup"><span data-stu-id="4f36d-128">The `implementationVisibility` flag applies to following tracking record types:</span></span>

- <span data-ttu-id="4f36d-129">ActivityStateRecord</span><span class="sxs-lookup"><span data-stu-id="4f36d-129">ActivityStateRecord</span></span>

- <span data-ttu-id="4f36d-130">FaultPropagationRecord</span><span class="sxs-lookup"><span data-stu-id="4f36d-130">FaultPropagationRecord</span></span>

- <span data-ttu-id="4f36d-131">CancelRequestedRecord</span><span class="sxs-lookup"><span data-stu-id="4f36d-131">CancelRequestedRecord</span></span>

- <span data-ttu-id="4f36d-132">ActivityScheduledRecord</span><span class="sxs-lookup"><span data-stu-id="4f36d-132">ActivityScheduledRecord</span></span>

> [!NOTE]
> <span data-ttu-id="4f36d-133">アクティビティの実装から生成される CustomTrackingRecords は、implementationVisibility 設定によるフィルター処理で除外されません。</span><span class="sxs-lookup"><span data-stu-id="4f36d-133">CustomTrackingRecords emitted from activity implementation are not filtered out by the implementationVisibility setting.</span></span>

<span data-ttu-id="4f36d-134">`implementationVisibility` 機能は、コードの追跡プロファイルで <xref:System.Activities.Tracking.ImplementationVisibility.RootScope> として次のように指定されます。</span><span class="sxs-lookup"><span data-stu-id="4f36d-134">The `implementationVisibility` functionality is specified as <xref:System.Activities.Tracking.ImplementationVisibility.RootScope> on the tracking profile in code as follows:</span></span>

```csharp
TrackingProfile sampleTrackingProfile = new TrackingProfile()
{
    Name = "Sample Tracking Profile",
    ImplementationVisibility = ImplementationVisibility.RootScope
};
```

<span data-ttu-id="4f36d-135">`implementationVisibility` 機能は、<xref:System.Activities.Tracking.ImplementationVisibility.All> として、次のように構成ファイルの追跡プロファイルで指定されます。</span><span class="sxs-lookup"><span data-stu-id="4f36d-135">The `implementationVisibility` functionality is specified as <xref:System.Activities.Tracking.ImplementationVisibility.All> on the tracking profile in a configuration file as follows:</span></span>

```xml
<tracking>
      <profiles>
        <trackingProfile name="Shipping Monitoring" implementationVisibility="All">
          <workflow activityDefinitionId="*">
...
         </workflow>
        </trackingProfile>
      </profiles>
</tracking>
```

<span data-ttu-id="4f36d-136">追跡プロファイルの `ImplementationVisibility` 設定は必要に応じて行います。</span><span class="sxs-lookup"><span data-stu-id="4f36d-136">The `ImplementationVisibility` setting on the tracking profile is optional.</span></span> <span data-ttu-id="4f36d-137">既定では、この値は `RootScope` に設定されます。</span><span class="sxs-lookup"><span data-stu-id="4f36d-137">By default, its value is set to `RootScope`.</span></span> <span data-ttu-id="4f36d-138">この属性の値も、大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="4f36d-138">The values for this attribute are also case-sensitive.</span></span>

### <a name="tracking-profile-query-types"></a><span data-ttu-id="4f36d-139">プロファイルのクエリの型の追跡</span><span class="sxs-lookup"><span data-stu-id="4f36d-139">Tracking Profile Query Types</span></span>

<span data-ttu-id="4f36d-140">追跡プロファイルは、特定の追跡レコードを対象としてワークフロー ランタイムを照会できる、追跡レコード用の宣言型のサブスクリプションとして構築されます。</span><span class="sxs-lookup"><span data-stu-id="4f36d-140">Tracking profiles are structured as declarative subscriptions for tracking records that allow you to query the workflow runtime for specific tracking records.</span></span> <span data-ttu-id="4f36d-141">クエリには、<xref:System.Activities.Tracking.TrackingRecord> オブジェクトのさまざまなクラスを定期受信できる型がいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="4f36d-141">There are several query types that allow you subscribe to different classes of <xref:System.Activities.Tracking.TrackingRecord> objects.</span></span> <span data-ttu-id="4f36d-142">追跡プロファイルは、構成で指定したり、コードで指定したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="4f36d-142">Tracking profiles can be specified in configuration or through code.</span></span> <span data-ttu-id="4f36d-143">最も一般的なクエリの型は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="4f36d-143">Here are the most common query types:</span></span>

- <span data-ttu-id="4f36d-144"><xref:System.Activities.Tracking.WorkflowInstanceQuery> - 前に説明した `Started` や `Completed` など、ワークフロー インスタンスのライフサイクルの変化を追跡するために使用します。</span><span class="sxs-lookup"><span data-stu-id="4f36d-144"><xref:System.Activities.Tracking.WorkflowInstanceQuery> - Use this to track workflow instance life cycle changes like the previously-demonstrated `Started` and `Completed`.</span></span> <span data-ttu-id="4f36d-145"><xref:System.Activities.Tracking.WorkflowInstanceQuery> は、次の <xref:System.Activities.Tracking.TrackingRecord> オブジェクトの定期受信に使用されます。</span><span class="sxs-lookup"><span data-stu-id="4f36d-145">The <xref:System.Activities.Tracking.WorkflowInstanceQuery> is used to subscribe to the following <xref:System.Activities.Tracking.TrackingRecord> objects:</span></span>

    - <xref:System.Activities.Tracking.WorkflowInstanceRecord>

    - <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>

    - <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>

    - <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>

    - <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>

    <span data-ttu-id="4f36d-146">定期受信可能な状態は、<xref:System.Activities.Tracking.WorkflowInstanceStates> クラスで指定します。</span><span class="sxs-lookup"><span data-stu-id="4f36d-146">The states that can be subscribed to are specified in the <xref:System.Activities.Tracking.WorkflowInstanceStates> class.</span></span>

    <span data-ttu-id="4f36d-147">`Started` を使用して <xref:System.Activities.Tracking.WorkflowInstanceQuery> インスタンス状態のワークフロー インスタンス レベルの追跡レコードを定期受信するために使用される構成またはコードを、次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="4f36d-147">The configuration or code used to subscribe to workflow instance-level tracking records for the `Started` instance state using the <xref:System.Activities.Tracking.WorkflowInstanceQuery> is shown in the following example.</span></span>

    ```xml
    <workflowInstanceQueries>
        <workflowInstanceQuery>
          <states>
            <state name="Started"/>
          </states>
        </workflowInstanceQuery>
    </workflowInstanceQueries>
    ```

    ```csharp
    TrackingProfile sampleTrackingProfile = new TrackingProfile()
    {
        Name = "Sample Tracking Profile",
        Queries =
        {
            new WorkflowInstanceQuery()
            {
                States = { WorkflowInstanceStates.Started}
            }
        }
    };
    ```

- <span data-ttu-id="4f36d-148"><xref:System.Activities.Tracking.ActivityStateQuery> - ワークフロー インスタンスを構成するアクティビティのライフ サイクルの変化を追跡するために使用します。</span><span class="sxs-lookup"><span data-stu-id="4f36d-148"><xref:System.Activities.Tracking.ActivityStateQuery> - Use this to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="4f36d-149">たとえば、ワークフロー インスタンス内で、「電子メールの送信」アクティビティが完了するたびの追跡する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4f36d-149">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="4f36d-150">このクエリは、<xref:System.Activities.Tracking.TrackingParticipant> が <xref:System.Activities.Tracking.ActivityStateRecord> オブジェクトを定期受信するのに必要です。</span><span class="sxs-lookup"><span data-stu-id="4f36d-150">This query is necessary for a <xref:System.Activities.Tracking.TrackingParticipant> to subscribe to <xref:System.Activities.Tracking.ActivityStateRecord> objects.</span></span> <span data-ttu-id="4f36d-151">定期受信可能な状態は <xref:System.Activities.Tracking.ActivityStates> で指定します。</span><span class="sxs-lookup"><span data-stu-id="4f36d-151">The available states to subscribe to are specified in <xref:System.Activities.Tracking.ActivityStates>.</span></span>

    <span data-ttu-id="4f36d-152"><xref:System.Activities.Tracking.ActivityStateQuery> アクティビティに `SendEmailActivity` を使用するアクティビティ状態の追跡レコードを定期受信するために使用される構成またはコードを、次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="4f36d-152">The configuration and code used to subscribe activity state tracking records that use the <xref:System.Activities.Tracking.ActivityStateQuery> for the `SendEmailActivity` activity is shown in the following example.</span></span>

    ```xml
    <activityStateQueries>
      <activityStateQuery activityName="SendEmailActivity">
        <states>
          <state name="Closed"/>
        </states>
      </activityStateQuery>
    </activityStateQueries>
    ```

    ```csharp
    TrackingProfile sampleTrackingProfile = new TrackingProfile()
    {
        Name = "Sample Tracking Profile",
        Queries =
        {
            new ActivityStateQuery()
            {
                ActivityName = "SendEmailActivity",
                States = { ActivityStates.Closed }
            }
        }
    };
    ```

    > [!NOTE]
    > <span data-ttu-id="4f36d-153">複数の activityStateQuery 要素が同じ名前である場合、最後の要素の状態のみが追跡プロファイルで使用されます。</span><span class="sxs-lookup"><span data-stu-id="4f36d-153">If multiple activityStateQuery elements have the same name, only the states in the last element are used in the tracking profile.</span></span>

- <span data-ttu-id="4f36d-154"><xref:System.Activities.Tracking.ActivityScheduledQuery> - このクエリを使用すると、親アクティビティによって実行がスケジュールされているアクティビティを追跡できます。</span><span class="sxs-lookup"><span data-stu-id="4f36d-154"><xref:System.Activities.Tracking.ActivityScheduledQuery> - This query allows you to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="4f36d-155">このクエリは、<xref:System.Activities.Tracking.TrackingParticipant> が <xref:System.Activities.Tracking.ActivityScheduledRecord> オブジェクトを定期受信するのに必要です。</span><span class="sxs-lookup"><span data-stu-id="4f36d-155">The query is necessary for a <xref:System.Activities.Tracking.TrackingParticipant> to subscribe to <xref:System.Activities.Tracking.ActivityScheduledRecord> objects.</span></span>

    <span data-ttu-id="4f36d-156">`SendEmailActivity` を使用して、スケジュールされている <xref:System.Activities.Tracking.ActivityScheduledQuery> 子アクティビティに関連するレコードを定期受信するために使用される構成またはコードを、次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="4f36d-156">The configuration and code used to subscribe to records related to the `SendEmailActivity` child activity being scheduled using the <xref:System.Activities.Tracking.ActivityScheduledQuery> is shown in the following example.</span></span>

    ```xml
    <activityScheduledQueries>
      <activityScheduledQuery activityName="ProcessNotificationsActivity" childActivityName="SendEmailActivity" />
     </activityScheduledQueries>
    ```

    ```csharp
    TrackingProfile sampleTrackingProfile = new TrackingProfile()
    {
        Name = "Sample Tracking Profile",
        Queries =
        {
            new ActivityScheduledQuery()
            {
                ActivityName = "ProcessNotificationsActivity",
                ChildActivityName = "SendEmailActivity"
            }
        }
    };
    ```

- <span data-ttu-id="4f36d-157"><xref:System.Activities.Tracking.FaultPropagationQuery> - アクティビティ内で発生したエラーの処理を追跡するために使用します。</span><span class="sxs-lookup"><span data-stu-id="4f36d-157"><xref:System.Activities.Tracking.FaultPropagationQuery> - Use this to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="4f36d-158">このクエリは、<xref:System.Activities.Tracking.TrackingParticipant> が <xref:System.Activities.Tracking.FaultPropagationRecord> オブジェクトを定期受信するのに必要です。</span><span class="sxs-lookup"><span data-stu-id="4f36d-158">The query is necessary for a <xref:System.Activities.Tracking.TrackingParticipant> to subscribe to <xref:System.Activities.Tracking.FaultPropagationRecord> objects.</span></span>

    <span data-ttu-id="4f36d-159"><xref:System.Activities.Tracking.FaultPropagationQuery> を使用して、エラー伝達に関連するレコードを定期受信するために使用される構成またはコードを、次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="4f36d-159">The configuration and code used to subscribe to records related to fault propagation using <xref:System.Activities.Tracking.FaultPropagationQuery> is shown in the following example.</span></span>

    ```xml
    <faultPropagationQueries>
      <faultPropagationQuery faultSourceActivityName="SendEmailActivity" faultHandlerActivityName="NotificationsFaultHandler" />
    </faultPropagationQueries>
    ```

    ```csharp
    TrackingProfile sampleTrackingProfile = new TrackingProfile()
    {
        Name = "Sample Tracking Profile",
        Queries =
        {
            new FaultPropagationQuery()
            {
                FaultSourceActivityName = "SendEmailActivity",
                FaultHandlerActivityName = "NotificationsFaultHandler"
            }
        }
    };
    ```

- <span data-ttu-id="4f36d-160"><xref:System.Activities.Tracking.CancelRequestedQuery> - 親アクティビティによって子アクティビティをキャンセルする要求を追跡するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="4f36d-160"><xref:System.Activities.Tracking.CancelRequestedQuery> - Use this to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="4f36d-161">このクエリは、<xref:System.Activities.Tracking.TrackingParticipant> が <xref:System.Activities.Tracking.CancelRequestedRecord> オブジェクトを定期受信するのに必要です。</span><span class="sxs-lookup"><span data-stu-id="4f36d-161">The query is necessary for a <xref:System.Activities.Tracking.TrackingParticipant> to subscribe to <xref:System.Activities.Tracking.CancelRequestedRecord> objects.</span></span>

    <span data-ttu-id="4f36d-162">構成とレコードを定期受信するためのコードに関連するアクティビティの取り消しを使用して<xref:System.Activities.Tracking.CancelRequestedQuery>次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="4f36d-162">The configuration and code used to subscribe to records related to activity cancellation using <xref:System.Activities.Tracking.CancelRequestedQuery> is shown in the following example.</span></span>

    ```xml
    <cancelRequestedQueries>
      <cancelRequestedQuery activityName="ProcessNotificationsActivity" childActivityName="SendEmailActivity" />
    </cancelRequestedQueries>
    ```

    ```csharp
    TrackingProfile sampleTrackingProfile = new TrackingProfile()
    {
        Name = "Sample Tracking Profile",
        Queries =
        {
            new CancelRequestedQuery()
            {
                ActivityName = "ProcessNotificationsActivity",
                ChildActivityName = "SendEmailActivity"
            }
        }
    };
    ```

- <span data-ttu-id="4f36d-163"><xref:System.Activities.Tracking.CustomTrackingQuery> - コード アクティビティで定義するイベントを追跡するために使用します。</span><span class="sxs-lookup"><span data-stu-id="4f36d-163"><xref:System.Activities.Tracking.CustomTrackingQuery> - Use this to track events that you define in your code activities.</span></span> <span data-ttu-id="4f36d-164">このクエリは、<xref:System.Activities.Tracking.TrackingParticipant> が <xref:System.Activities.Tracking.CustomTrackingRecord> オブジェクトを定期受信するのに必要です。</span><span class="sxs-lookup"><span data-stu-id="4f36d-164">The query is necessary for a <xref:System.Activities.Tracking.TrackingParticipant> to subscribe to <xref:System.Activities.Tracking.CustomTrackingRecord> objects.</span></span>

    <span data-ttu-id="4f36d-165"><xref:System.Activities.Tracking.CustomTrackingQuery> を使用して、カスタム追跡レコードに関連するレコードを定期受信するために使用される構成またはコードを、次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="4f36d-165">The configuration and code used to subscribe to records related to custom tracking records using <xref:System.Activities.Tracking.CustomTrackingQuery> is shown in the following example.</span></span>

    ```xml
    <customTrackingQueries>
      <customTrackingQuery name="EmailAddress" activityName="SendEmailActivity" />
    </customTrackingQueries>
    ```

    ```csharp
    TrackingProfile sampleTrackingProfile = new TrackingProfile()
    {
        Name = "Sample Tracking Profile",
        Queries =
        {
            new CustomTrackingQuery()
            {
                Name = "EmailAddress",
                ActivityName = "SendEmailActivity"
            }
        }
    };
    ```

- <span data-ttu-id="4f36d-166"><xref:System.Activities.Tracking.BookmarkResumptionQuery> - ワークフロー インスタンス内のブックマークの再開を追跡するために使用します。</span><span class="sxs-lookup"><span data-stu-id="4f36d-166"><xref:System.Activities.Tracking.BookmarkResumptionQuery> - Use this to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="4f36d-167">このクエリは、<xref:System.Activities.Tracking.TrackingParticipant> が <xref:System.Activities.Tracking.BookmarkResumptionRecord> オブジェクトを定期受信するのに必要です。</span><span class="sxs-lookup"><span data-stu-id="4f36d-167">This query is necessary for a <xref:System.Activities.Tracking.TrackingParticipant> to subscribe to <xref:System.Activities.Tracking.BookmarkResumptionRecord> objects.</span></span>

    <span data-ttu-id="4f36d-168"><xref:System.Activities.Tracking.BookmarkResumptionQuery> を使用して、ブックマークの再開に関連するレコードを定期受信するために使用される構成またはコードを、次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="4f36d-168">The configuration and code used to subscribe to records related to bookmark resumption using <xref:System.Activities.Tracking.BookmarkResumptionQuery> is shown in the following example.</span></span>

    ```xml
    <bookmarkResumptionQueries>
      <bookmarkResumptionQuery name="SentEmailBookmark" />
    </bookmarkResumptionQueries>
    ```

    ```csharp
    TrackingProfile sampleTrackingProfile = new TrackingProfile()
    {
        Name = "Sample Tracking Profile",
        Queries =
        {
            new BookmarkResumptionQuery()
            {
                Name = "sentEmailBookmark"
            }
        }
    };
    ```

### <a name="annotations"></a><span data-ttu-id="4f36d-169">コメント</span><span class="sxs-lookup"><span data-stu-id="4f36d-169">Annotations</span></span>

<span data-ttu-id="4f36d-170">注釈を使用すると、ビルド後に構成できる値を使用して、追跡レコードへのタグ付けを任意に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="4f36d-170">Annotations allow you to arbitrarily tag tracking records with a value that can be configured after build time.</span></span> <span data-ttu-id="4f36d-171">たとえば、"Mail Server"タグが付けられる複数のワークフロー追跡レコードをいくつかをする可能性があります"Mail Server1"= =。</span><span class="sxs-lookup"><span data-stu-id="4f36d-171">For example, you might want several tracking records across several workflows to be tagged with "Mail Server" == "Mail Server1".</span></span> <span data-ttu-id="4f36d-172">こうすると、後で追跡レコードのクエリを実行するときに、このタグの付いたすべてのレコードを簡単に見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="4f36d-172">This makes it easy to find all records with this tag when querying tracking records later.</span></span>

<span data-ttu-id="4f36d-173">これを可能にするために、次の例に示すように注釈が追跡クエリに追加されます。</span><span class="sxs-lookup"><span data-stu-id="4f36d-173">To accomplish this, an annotation is added to a tracking query as shown in the following example.</span></span>

```xml
<activityStateQuery activityName="SendEmailActivity">
  <states>
    <state name="Closed"/>
  </states>
  <annotations>
    <annotation name="MailServer" value="Mail Server1"/>
  </annotations>
</activityStateQuery>
```

### <a name="how-to-create-a-tracking-profile"></a><span data-ttu-id="4f36d-174">追跡プロファイルを作成する方法</span><span class="sxs-lookup"><span data-stu-id="4f36d-174">How to Create a Tracking Profile</span></span>

<span data-ttu-id="4f36d-175">追跡クエリ要素を使用することで、XML 構成ファイルまたは [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] のコードを使用した追跡プロファイルを作成できます。</span><span class="sxs-lookup"><span data-stu-id="4f36d-175">Tracking query elements are used to create a tracking profile using either an XML configuration file or [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)]code.</span></span> <span data-ttu-id="4f36d-176">次の例は、構成ファイルを使用して作成した追跡プロファイルです。</span><span class="sxs-lookup"><span data-stu-id="4f36d-176">Here is an example of a tracking profile created using a configuration file.</span></span>

```xml
<system.serviceModel>
  <tracking>
    <profiles>
      <trackingProfile name="Sample Tracking Profile ">
        <workflow activityDefinitionId="*">
          <!--Specify the tracking profile query elements to subscribe for tracking records-->
        </workflow>
      </trackingProfile>
    </profiles>
  </tracking>
</system.serviceModel>
```

> [!WARNING]
> <span data-ttu-id="4f36d-177">ワークフロー サービス ホストを使用する WF の場合、追跡プロファイルは構成ファイルを使用して作成されることがほとんどです。</span><span class="sxs-lookup"><span data-stu-id="4f36d-177">For a WF using the Workflow service host, the tracking profile is typically created using a configuration file.</span></span> <span data-ttu-id="4f36d-178">また、追跡プロファイルや追跡クエリ API を使用するコードで追跡プロファイルを作成することも可能です。</span><span class="sxs-lookup"><span data-stu-id="4f36d-178">It is also possible to create a tracking profile with code using the tracking profile and tracking query API.</span></span>

<span data-ttu-id="4f36d-179">XML 構成ファイルとして構成されるプロファイルは、動作拡張を使用して追跡参加要素に適用されます。</span><span class="sxs-lookup"><span data-stu-id="4f36d-179">A profile configured as an XML configuration file is applied to a tracking participant using a behavior extension.</span></span> <span data-ttu-id="4f36d-180">以降のセクションで説明した WorkflowServiceHost に追加されますこの[ワークフローの追跡を構成する](configuring-tracking-for-a-workflow.md)します。</span><span class="sxs-lookup"><span data-stu-id="4f36d-180">This is added to a WorkflowServiceHost as described in the later section [Configuring Tracking for a Workflow](configuring-tracking-for-a-workflow.md).</span></span>

<span data-ttu-id="4f36d-181">ホストが生成する追跡レコードの詳細度は、追跡プロファイルの構成の設定によって決まります。</span><span class="sxs-lookup"><span data-stu-id="4f36d-181">The verbosity of the tracking records emitted by the host is determined by configuration settings within the tracking profile.</span></span> <span data-ttu-id="4f36d-182">追跡参加要素は、クエリを追跡プロファイルに追加して追跡レコードを定期受信します。</span><span class="sxs-lookup"><span data-stu-id="4f36d-182">A tracking participant subscribes to tracking records by adding queries to a tracking profile.</span></span> <span data-ttu-id="4f36d-183">追跡プロファイルをサブスクライブするすべての追跡レコードを使用してすべての追跡クエリを指定する必要があります"\*"の各クエリ内の名前フィールドにします。</span><span class="sxs-lookup"><span data-stu-id="4f36d-183">To subscribe to all tracking records, the tracking profile needs to specify all tracking queries using "\*" in the name fields in each of the queries.</span></span>

<span data-ttu-id="4f36d-184">一般的な追跡プロファイルの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="4f36d-184">Here are some of the common examples of tracking profiles.</span></span>

- <span data-ttu-id="4f36d-185">ワークフロー インスタンスのレコードとエラーを取得する追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="4f36d-185">A tracking profile to obtain workflow instance records and faults.</span></span>

```xml
<trackingProfile name="Instance and Fault Records">
  <workflow activityDefinitionId="*">
    <workflowInstanceQueries>
      <workflowInstanceQuery>
        <states>
          <state name="*" />
        </states>
      </workflowInstanceQuery>
    </workflowInstanceQueries>
    <activityStateQueries>
      <activityStateQuery activityName="*">
        <states>
          <state name="Faulted"/>
        </states>
      </activityStateQuery>
    </activityStateQueries>
  </workflow>
</trackingProfile>
```

1. <span data-ttu-id="4f36d-186">すべてのカスタム追跡レコードを取得する追跡プロファイル</span><span class="sxs-lookup"><span data-stu-id="4f36d-186">A tracking profile to obtain all custom tracking records.</span></span>

```xml
<trackingProfile name="Instance_And_Custom_Records">
  <workflow activityDefinitionId="*">
    <customTrackingQueries>
      <customTrackingQuery name="*" activityName="*" />
    </customTrackingQueries>
  </workflow>
</trackingProfile>
```

## <a name="see-also"></a><span data-ttu-id="4f36d-187">関連項目</span><span class="sxs-lookup"><span data-stu-id="4f36d-187">See also</span></span>

- [<span data-ttu-id="4f36d-188">SQL 追跡</span><span class="sxs-lookup"><span data-stu-id="4f36d-188">SQL Tracking</span></span>](./samples/sql-tracking.md)
- [<span data-ttu-id="4f36d-189">Windows Server App Fabric の監視</span><span class="sxs-lookup"><span data-stu-id="4f36d-189">Windows Server App Fabric Monitoring</span></span>](https://go.microsoft.com/fwlink/?LinkId=201273)
- [<span data-ttu-id="4f36d-190">App Fabric でアプリケーションの監視</span><span class="sxs-lookup"><span data-stu-id="4f36d-190">Monitoring Applications with App Fabric</span></span>](https://go.microsoft.com/fwlink/?LinkId=201275)
