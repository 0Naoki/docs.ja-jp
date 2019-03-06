---
title: '方法: カスタム インスタンス ストアを作成します。'
ms.date: 03/30/2017
ms.assetid: 593c4e9d-8a49-4e12-8257-cee5e6b4c075
ms.openlocfilehash: de3602b928a861500e7984fe88bbb2176d58b840
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57503191"
---
# <a name="how-to-create-a-custom-instance-store"></a><span data-ttu-id="a567f-102">方法: カスタム インスタンス ストアを作成します。</span><span class="sxs-lookup"><span data-stu-id="a567f-102">How to: Create a Custom Instance Store</span></span>

[!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] <span data-ttu-id="a567f-103">には、<xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> という、SQL Server を使用してワークフロー データの永続化を行うインスタンス ストアが含まれています。</span><span class="sxs-lookup"><span data-stu-id="a567f-103">contains <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>, an instance store that uses SQL Server to persist workflow data.</span></span> <span data-ttu-id="a567f-104">ワークフロー データの永続化を別のメディアで行う、つまり、別のデータベースやファイル システムなどを使用して行う必要があるアプリケーションの場合は、カスタム インスタンス ストアを実装できます。</span><span class="sxs-lookup"><span data-stu-id="a567f-104">If your application is required to persist workflow data to another medium, such as a different database or a file system, you can implement a custom instance store.</span></span> <span data-ttu-id="a567f-105">カスタム インスタンス ストアを作成するには、抽象 <xref:System.Runtime.DurableInstancing.InstanceStore> クラスを拡張し、その実装に必要なメソッドを実装します。</span><span class="sxs-lookup"><span data-stu-id="a567f-105">A custom instance store is created by extending the abstract <xref:System.Runtime.DurableInstancing.InstanceStore> class and implementing the methods that are required for the implementation.</span></span> <span data-ttu-id="a567f-106">カスタム インスタンス ストアの完全な実装を参照してください、[企業の購買プロセス](../../../docs/framework/windows-workflow-foundation/samples/corporate-purchase-process.md)サンプル。</span><span class="sxs-lookup"><span data-stu-id="a567f-106">For a complete implementation of a custom instance store, see the [Corporate Purchase Process](../../../docs/framework/windows-workflow-foundation/samples/corporate-purchase-process.md) sample.</span></span>

## <a name="implementing-the-begintrycommand-method"></a><span data-ttu-id="a567f-107">BeginTryCommand メソッドの実装</span><span class="sxs-lookup"><span data-stu-id="a567f-107">Implementing the BeginTryCommand method</span></span>

<span data-ttu-id="a567f-108"><xref:System.Runtime.DurableInstancing.InstanceStore.BeginTryCommand%2A> は永続化エンジンによってインスタンス ストアに送信されます。</span><span class="sxs-lookup"><span data-stu-id="a567f-108">The <xref:System.Runtime.DurableInstancing.InstanceStore.BeginTryCommand%2A> is sent to the instance store by the persistence engine.</span></span> <span data-ttu-id="a567f-109">
  `command\` パラメーターの型は、どのコマンドを実行するかを示します。このパラメーターは次のいずれかになります:</span><span class="sxs-lookup"><span data-stu-id="a567f-109">The type of the `command` parameter indicates which command is being executed; this parameter can be of the following types:</span></span>

- <span data-ttu-id="a567f-110"><xref:System.Activities.DurableInstancing.SaveWorkflowCommand>:永続化エンジンでは、ワークフローは、ストレージ メディアに永続化するときに、このコマンドをインスタンス ストアに送信します。</span><span class="sxs-lookup"><span data-stu-id="a567f-110"><xref:System.Activities.DurableInstancing.SaveWorkflowCommand>: The persistence engine sends this command to the instance store when a workflow is to be persisted to the storage medium.</span></span> <span data-ttu-id="a567f-111">ワーク フローの永続性データは、<xref:System.Activities.DurableInstancing.SaveWorkflowCommand.InstanceData%2A> パラメーターの `command` メンバー内のメソッドに提供されます。</span><span class="sxs-lookup"><span data-stu-id="a567f-111">The workflow persistence data is provided to the method in the <xref:System.Activities.DurableInstancing.SaveWorkflowCommand.InstanceData%2A> member of the `command` parameter.</span></span>

- <span data-ttu-id="a567f-112"><xref:System.Activities.DurableInstancing.LoadWorkflowCommand>:永続化エンジンでは、ワークフローは、ストレージ メディアから読み込まれるときに、このコマンドをインスタンス ストアに送信します。</span><span class="sxs-lookup"><span data-stu-id="a567f-112"><xref:System.Activities.DurableInstancing.LoadWorkflowCommand>: The persistence engine sends this command to the instance store when a workflow is to be loaded from the storage medium.</span></span> <span data-ttu-id="a567f-113">読み込むワークフローのインスタンス ID は、`instanceId` パラメーターの <xref:System.Runtime.DurableInstancing.InstancePersistenceContext.InstanceView%2A> プロパティの `context` パラメーター内のメソッドに提供されます。</span><span class="sxs-lookup"><span data-stu-id="a567f-113">The instance ID of the workflow to be loaded is provided to the method in the `instanceId` parameter of the <xref:System.Runtime.DurableInstancing.InstancePersistenceContext.InstanceView%2A> property of the `context` parameter.</span></span>

- <span data-ttu-id="a567f-114"><xref:System.Activities.DurableInstancing.CreateWorkflowOwnerCommand>:次のコマンド インスタンスを格納ときに永続化エンジンの送信、<xref:System.ServiceModel.Activities.WorkflowServiceHost>ロック所有者として登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a567f-114"><xref:System.Activities.DurableInstancing.CreateWorkflowOwnerCommand>: The persistence engine sends this command to the instance store when a <xref:System.ServiceModel.Activities.WorkflowServiceHost> must be registered as a lock owner.</span></span> <span data-ttu-id="a567f-115">現在のワーク フローのインスタンス ID を、<xref:System.Runtime.DurableInstancing.InstancePersistenceContext.BindInstanceOwner%2A> パラメーターの `context` メソッドを使用してインスタンス ストアに提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a567f-115">The instance ID of the current workflow should be provided to the instance store using <xref:System.Runtime.DurableInstancing.InstancePersistenceContext.BindInstanceOwner%2A> method of the `context` parameter.</span></span>

     <span data-ttu-id="a567f-116">次のコード スニペットは、CreateWorkflowOwner コマンドを実装して明示的なロック所有者を割り当てる方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="a567f-116">The following code snippet demonstrates how to implement the CreateWorkflowOwner command to assign an explicit lock owner.</span></span>

    ```csharp
    XName WFInstanceScopeName = XName.Get(scopeName, "<namespace>");
    ...
    CreateWorkflowOwnerCommand createCommand = new CreateWorkflowOwnerCommand()
    {
        InstanceOwnerMetadata =
        {
            { WorkflowHostTypeName, new InstanceValue(WFInstanceScopeName) },
        }
    };
    InstanceHandle ownerHandle = store.CreateInstanceHandle();
    store.DefaultInstanceOwner = store.Execute(
                                   ownerHandle,
                                   createCommand,
                                   TimeSpan.FromSeconds(30)).InstanceOwner;
    childInstance.AddInitialInstanceValues(new Dictionary<XName, object>() { { WorkflowHostTypeName, WFInstanceScopeName } });
    ```

- <span data-ttu-id="a567f-117"><xref:System.Activities.DurableInstancing.DeleteWorkflowOwnerCommand>:永続化エンジンでは、ロック所有者のインスタンス ID は、インスタンス ストアから削除できる場合、このコマンドをインスタンス ストアに送信します。</span><span class="sxs-lookup"><span data-stu-id="a567f-117"><xref:System.Activities.DurableInstancing.DeleteWorkflowOwnerCommand>: The persistence engine sends this command to the instance store when the instance ID of a lock owner can be removed from the instance store.</span></span> <span data-ttu-id="a567f-118">
  <xref:System.Activities.DurableInstancing.CreateWorkflowOwnerCommand> と同様に、アプリケーションがロック所有者の ID を提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a567f-118">As with <xref:System.Activities.DurableInstancing.CreateWorkflowOwnerCommand>, the ID of the lock owner should be provided by the application.</span></span>

     <span data-ttu-id="a567f-119">次のコード スニペットは、<xref:System.Activities.DurableInstancing.DeleteWorkflowOwnerCommand> を使用してロックを解除する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="a567f-119">The following code snippet demonstrates how to release a lock using <xref:System.Activities.DurableInstancing.DeleteWorkflowOwnerCommand>.</span></span>

    ```csharp
    static void FreeHandleAndDeleteOwner(InstanceStore store, InstanceHandle handle)
    {
        handle.Free();
        handle = store.CreateInstanceHandle(store.DefaultInstanceOwner);
        try
        {
            // We need this sleep so that we dont prematurely delete the owner, we need time to update the database.
            Thread.Sleep(10000);
            store.Execute(handle, new DeleteWorkflowOwnerCommand(), TimeSpan.FromSeconds(10));
        }
        catch (InstancePersistenceCommandException ex) { Log.Inform(ex.Message); }
        catch (InstanceOwnerException ex) { Log.Inform(ex.Message); }
        catch (OperationCanceledException ex) { Log.Inform(ex.Message); }
        catch (Exception ex) { Log.Inform(ex.Message); }
        finally
        {
            handle.Free();
            store.DefaultInstanceOwner = null;
        }
    }
    ```

     <span data-ttu-id="a567f-120">上のメソッドは、子インスタンスが実行されているときに Try ～ Catch ブロック内から呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="a567f-120">The above method should be called in a Try/Catch block when a child instance is run.</span></span>

    ```csharp
    try
    {
        childInstance.Run();
    }
    catch (Exception)
    {
        throw ;
    }
    finally
    {
        FreeHandleAndDeleteOwner(store, ownerHandle);
    }
    ```

- <span data-ttu-id="a567f-121"><xref:System.Activities.DurableInstancing.LoadWorkflowByInstanceKeyCommand>:永続化エンジンでは、ワークフロー インスタンスが、ワークフローのインスタンス キーを使用して読み込まれるときに、インスタンス ストアにこのコマンドを送信します。</span><span class="sxs-lookup"><span data-stu-id="a567f-121"><xref:System.Activities.DurableInstancing.LoadWorkflowByInstanceKeyCommand>: The persistence engine sends this command to the instance store when a workflow instance is to be loaded using the workflow’s instance key.</span></span> <span data-ttu-id="a567f-122">インスタンス キーの ID は、このコマンドの <xref:System.Activities.DurableInstancing.LoadWorkflowByInstanceKeyCommand.LookupInstanceKey%2A> パラメーターを使用して確認できます。</span><span class="sxs-lookup"><span data-stu-id="a567f-122">The ID of the instance key can be determined by using the <xref:System.Activities.DurableInstancing.LoadWorkflowByInstanceKeyCommand.LookupInstanceKey%2A> parameter of the command.</span></span>

- <span data-ttu-id="a567f-123"><xref:System.Activities.DurableInstancing.QueryActivatableWorkflowsCommand>:永続化エンジンは、ワークフローを読み込むワークフロー ホストを作成するには、永続化されたワークフローのアクティブ化パラメーターを取得する、インスタンス ストアにこのコマンドを送信します。</span><span class="sxs-lookup"><span data-stu-id="a567f-123"><xref:System.Activities.DurableInstancing.QueryActivatableWorkflowsCommand>: The persistence engine sends this command to the instance store to retrieve activation parameters for persisted workflows in order to create a workflow host that can then load workflows.</span></span> <span data-ttu-id="a567f-124">このコマンドは、インスタンス ストアがアクティブ化できるインスタンスを見つけて、ホストに <xref:System.Activities.DurableInstancing.HasActivatableWorkflowEvent> を発生させたとき、それに対する応答としてエンジンにより送信されます。</span><span class="sxs-lookup"><span data-stu-id="a567f-124">This command is sent by the engine in response to the instance store raising the <xref:System.Activities.DurableInstancing.HasActivatableWorkflowEvent> to the host when it locates an instance that can be activated.</span></span> <span data-ttu-id="a567f-125">アクティブ化できるワーク フローがあるかどうかを判別するには、インスタンス ストアをポーリングする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a567f-125">The instance store should be polled to determine if there are workflows that can be activated.</span></span>

- <span data-ttu-id="a567f-126"><xref:System.Activities.DurableInstancing.TryLoadRunnableWorkflowCommand>:永続化エンジンは、このコマンドを実行可能なワークフロー インスタンスの読み込みにインスタンス ストアに送信します。</span><span class="sxs-lookup"><span data-stu-id="a567f-126"><xref:System.Activities.DurableInstancing.TryLoadRunnableWorkflowCommand>: The persistence engine sends this command to the instance store to load runnable workflow instances.</span></span> <span data-ttu-id="a567f-127">このコマンドは、インスタンス ストアが実行できるインスタンスを見つけて、ホストに <xref:System.Activities.DurableInstancing.HasRunnableWorkflowEvent> を発生させたとき、それに対する応答としてエンジンにより送信されます。</span><span class="sxs-lookup"><span data-stu-id="a567f-127">This command is sent by the engine in response to the instance store raising the <xref:System.Activities.DurableInstancing.HasRunnableWorkflowEvent> to the host when it locates an instance that can be run.</span></span> <span data-ttu-id="a567f-128">実行できるワークフローを見つけるには、インスタンス ストアをポーリングする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a567f-128">The instance store should poll for workflows that can be run.</span></span> <span data-ttu-id="a567f-129">次のコード スニペットは、実行またはアクティブ化できるワークフローのために、インスタンス ストアのポーリングを行う方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="a567f-129">The following code snippet demonstrates polling an instance store for workflows that can be run or activated.</span></span>

    ```csharp
    public void PollForEvents()
    {
        InstanceOwner[] storeOwners = this.GetInstanceOwners();

        foreach (InstanceOwner owner in storeOwners)
        {
            foreach (InstancePersistenceEvent ppEvent in this.GetEvents(owner))
            {
                if (ppEvent.Equals(HasRunnableWorkflowEvent.Value))
                {
                    bool hasRunnable = GetRunnableEvents(this.StoreId, owner.InstanceOwnerId, isActivatable);
                    if (hasRunnable)
                    {
                        this.SignalEvent(ppEvent, owner);
                    }
                    else
                    {
                        this.ResetEvent(ppEvent, owner);
                    }
                }
                else if(ppEvent.Equals(HasActivatableWorkflowEvent.Value))
                {
                   bool hasActivatable = GetActivatableEvents(this.StoreId, owner.InstanceOwnerId);
                   if (hasActivatable)
                    {
                        this.SignalEvent(ppEvent, owner);
                    }
                    else
                    {
                        this.ResetEvent(ppEvent, owner);
                    }
                }
            }
        }
    }
    ```

     <span data-ttu-id="a567f-130">上のコード スニペットでは、インスタンス ストアが、使用できるイベントを探し、各イベントが <xref:System.Activities.DurableInstancing.HasRunnableWorkflowEvent> イベントであるかどうかを判断しています。</span><span class="sxs-lookup"><span data-stu-id="a567f-130">In the above code snippet, the instance store queries the events available and examines each one to determine if it is a <xref:System.Activities.DurableInstancing.HasRunnableWorkflowEvent> event.</span></span> <span data-ttu-id="a567f-131">使用できるイベントが見つかると、<xref:System.Runtime.DurableInstancing.InstanceStore.SignalEvent%2A> が呼び出され、インスタンス ストアにコマンドを送信することを指示する通知がホストに送信されます。</span><span class="sxs-lookup"><span data-stu-id="a567f-131">If one is found, <xref:System.Runtime.DurableInstancing.InstanceStore.SignalEvent%2A> is called to signal the host to send a command to the instance store.</span></span> <span data-ttu-id="a567f-132">次のコード スニペットはこのコマンドのハンドラーの実装を示します。</span><span class="sxs-lookup"><span data-stu-id="a567f-132">The following code snippet demonstrates an implementation of a handler for this command.</span></span>

    ```csharp
    If (command is TryLoadRunnableWorkflowCommand)
    {
        Owner owner;
        CheckOwner(context, command.Name, out owner);
        // Checking instance.Owner is like an InstanceLockQueryResult.
        context.QueriedInstanceStore(new InstanceLockQueryResult(context.InstanceView.InstanceId, context.InstanceView.InstanceOwner.InstanceOwnerId));

        XName ownerService = null;
        InstanceValue value;
        Instance runnableInstance = default(Instance);
        bool foundRunnableInstance = false;

        value = QueryPropertyBag(WorkflowNamespace.WorkflowHostType, owner.Data);
        if (value != null && value.Value is XName)
        {
            ownerService = (XName)value.Value;
        }

        foreach (KeyValuePair<Guid, Instance> instance in MemoryStore.instances)
        {
            if (instance.Value.Owner != Guid.Empty || instance.Value.Completed)
            {
                continue;
            }

            if (ownerService != null)
            {
                value = QueryPropertyBag(WorkflowNamespace.WorkflowHostType, instance.Value.Metadata);
                if (value == null || ((XName)value.Value) != ownerService)
                {
                    continue;
                }
            }

            value = QueryPropertyBag(WorkflowServiceNamespace.SuspendReason, instance.Value.Metadata);
            if (value != null && value.Value != null && value.Value is string)
            {
                continue;
            }

            value = QueryPropertyBag(WorkflowNamespace.Status, instance.Value.Data);
            if (value != null && value.Value is string && ((string)value.Value) == "Executing")
            {
                runnableInstance = instance.Value;
                foundRunnableInstance = true;
            }

            if (!foundRunnableInstance)
            {
                value = QueryPropertyBag(XNamespace.Get("urn:schemas-microsoft-com:System.Activities/4.0/properties").GetName("TimerExpirationTime"), instance.Value.Data);
                if (value != null && value.Value is DateTime && ((DateTime)value.Value) <= DateTime.UtcNow)
                {
                    runnableInstance = instance.Value;
                    foundRunnableInstance = true;
                }
            }

            if (foundRunnableInstance)
            {
                runnableInstance.LockVersion++;
                runnableInstance.Owner = context.InstanceView.InstanceOwner.InstanceOwnerId;
                MemoryStore.instances[instance.Key] = runnableInstance;
                context.BindInstance(instance.Key);
                context.BindAcquiredLock(runnableInstance.LockVersion);

                Dictionary<Guid, IDictionary<XName, InstanceValue>> associatedKeys = new Dictionary<Guid, IDictionary<XName, InstanceValue>>();
                Dictionary<Guid, IDictionary<XName, InstanceValue>> completedKeys = new Dictionary<Guid, IDictionary<XName, InstanceValue>>();
                foreach (KeyValuePair<Guid, Key> keyEntry in MemoryStore.keys)
                {
                if (keyEntry.Value.Instance == context.InstanceView.InstanceId)
                {
                    if (keyEntry.Value.Completed)
                    {
                        completedKeys.Add(keyEntry.Key, DeserializePropertyBag(keyEntry.Value.Metadata));
                    }
                    else
                    {
                        associatedKeys.Add(keyEntry.Key, DeserializePropertyBag(keyEntry.Value.Metadata));
                    }
                }
            }

            context.LoadedInstance(InstanceState.Initialized, DeserializePropertyBag(runnableInstance.Data), DeserializePropertyBag(runnableInstance.Metadata), associatedKeys, completedKeys);
            break;
        }
    }
    ```

    <span data-ttu-id="a567f-133">上のコード スニペットでは、インスタンス ストアは実行可能なインスタンスを検索します。</span><span class="sxs-lookup"><span data-stu-id="a567f-133">In the above code snippet, the instance store searches for runnable instances.</span></span> <span data-ttu-id="a567f-134">インスタンスが見つかると、そのインスタンスが実行コンテキストにバインドされ、読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="a567f-134">If an instance is found, it is bound to the execution context and loaded.</span></span>

## <a name="using-a-custom-instance-store"></a><span data-ttu-id="a567f-135">カスタム インスタンス ストアの使用</span><span class="sxs-lookup"><span data-stu-id="a567f-135">Using a custom instance store</span></span>

<span data-ttu-id="a567f-136">カスタム インスタンス ストアを実装するには、インスタンス ストアのインスタンスを <xref:System.Activities.WorkflowApplication.InstanceStore%2A> に割り当て、<xref:System.Activities.WorkflowApplication.PersistableIdle%2A> メソッドを実装します。</span><span class="sxs-lookup"><span data-stu-id="a567f-136">To implement a custom instance store, assign an instance of the instance store to the <xref:System.Activities.WorkflowApplication.InstanceStore%2A>, and implement the <xref:System.Activities.WorkflowApplication.PersistableIdle%2A> method.</span></span> <span data-ttu-id="a567f-137">参照してください、[方法。作成および実行 a Long Running Workflow](../../../docs/framework/windows-workflow-foundation/how-to-create-and-run-a-long-running-workflow.md)の仕様についてのチュートリアル。</span><span class="sxs-lookup"><span data-stu-id="a567f-137">See the [How to: Create and Run a Long Running Workflow](../../../docs/framework/windows-workflow-foundation/how-to-create-and-run-a-long-running-workflow.md) tutorial for specifics.</span></span>

## <a name="a-sample-instance-store"></a><span data-ttu-id="a567f-138">サンプル インスタンス ストア</span><span class="sxs-lookup"><span data-stu-id="a567f-138">A sample instance store</span></span>

<span data-ttu-id="a567f-139">次のコード サンプルから取得した、完成したインスタンス ストア実装は、[企業の購買プロセス](../../../docs/framework/windows-workflow-foundation/samples/corporate-purchase-process.md)サンプル。</span><span class="sxs-lookup"><span data-stu-id="a567f-139">The following code sample is a complete instance store implementation, taken from the [Corporate Purchase Process](../../../docs/framework/windows-workflow-foundation/samples/corporate-purchase-process.md) sample.</span></span> <span data-ttu-id="a567f-140">このインスタンス ストアは、XML を使用してファイルにワークフロー データを永続化します。</span><span class="sxs-lookup"><span data-stu-id="a567f-140">This instance store persists workflow data to a file using XML.</span></span>

```csharp
using System;
using System.Activities.DurableInstancing;
using System.Collections.Generic;
using System.IO;
using System.Runtime.DurableInstancing;
using System.Runtime.Serialization;
using System.ServiceModel.Persistence;
using System.Xml;
using System.Xml.Linq;

namespace Microsoft.Samples.WF.PurchaseProcess
{

    public class XmlWorkflowInstanceStore : InstanceStore
    {
        Guid ownerInstanceID;

        public XmlWorkflowInstanceStore() : this(Guid.NewGuid())
        {

        }

        public XmlWorkflowInstanceStore(Guid id)
        {
            ownerInstanceID = id;
        }

        //Synchronous version of the Begin/EndTryCommand functions
        protected override bool TryCommand(InstancePersistenceContext context, InstancePersistenceCommand command, TimeSpan timeout)
        {
            return EndTryCommand(BeginTryCommand(context, command, timeout, null, null));
        }

        //The persistence engine will send a variety of commands to the configured InstanceStore,
        //such as CreateWorkflowOwnerCommand, SaveWorkflowCommand, and LoadWorkflowCommand.
        //This method is where we will handle those commands
        protected override IAsyncResult BeginTryCommand(InstancePersistenceContext context, InstancePersistenceCommand command, TimeSpan timeout, AsyncCallback callback, object state)
        {
            IDictionary<XName, InstanceValue> data = null;

            //The CreateWorkflowOwner command instructs the instance store to create a new instance owner bound to the instanace handle
            if (command is CreateWorkflowOwnerCommand)
            {
                context.BindInstanceOwner(ownerInstanceID, Guid.NewGuid());
            }
            //The SaveWorkflow command instructs the instance store to modify the instance bound to the instance handle or an instance key
            else if (command is SaveWorkflowCommand)
            {
                SaveWorkflowCommand saveCommand = (SaveWorkflowCommand)command;
                data = saveCommand.InstanceData;

                Save(data);
            }
            //The LoadWorkflow command instructs the instance store to lock and load the instance bound to the identifier in the instance handle
            else if (command is LoadWorkflowCommand)
            {
                string fileName = IOHelper.GetFileName(this.ownerInstanceID);

                try
                {
                    using (FileStream inputStream = new FileStream(fileName, FileMode.Open))
                    {
                        data = LoadInstanceDataFromFile(inputStream);
                        //load the data into the persistence Context
                        context.LoadedInstance(InstanceState.Initialized, data, null, null, null);
                    }
                }
                catch (Exception exception)
                {
                    throw new PersistenceException(exception.Message);
                }
            }

            return new CompletedAsyncResult<bool>(true, callback, state);
        }

        protected override bool EndTryCommand(IAsyncResult result)
        {
            return CompletedAsyncResult<bool>.End(result);
        }

        //Reads data from xml file and creates a dictionary based off of that.
        IDictionary<XName, InstanceValue> LoadInstanceDataFromFile(Stream inputStream)
        {
            IDictionary<XName, InstanceValue> data = new Dictionary<XName, InstanceValue>();

            NetDataContractSerializer s = new NetDataContractSerializer();

            XmlReader rdr = XmlReader.Create(inputStream);
            XmlDocument doc = new XmlDocument();
            doc.Load(rdr);

            XmlNodeList instances = doc.GetElementsByTagName("InstanceValue");
            foreach (XmlElement instanceElement in instances)
            {
                XmlElement keyElement = (XmlElement)instanceElement.SelectSingleNode("descendant::key");
                XName key = (XName)DeserializeObject(s, keyElement);

                XmlElement valueElement = (XmlElement)instanceElement.SelectSingleNode("descendant::value");
                object value = DeserializeObject(s, valueElement);
                InstanceValue instVal = new InstanceValue(value);

                data.Add(key, instVal);
            }

            return data;
        }

        object DeserializeObject(NetDataContractSerializer serializer, XmlElement element)
        {
            object deserializedObject = null;

            MemoryStream stm = new MemoryStream();
            XmlDictionaryWriter wtr = XmlDictionaryWriter.CreateTextWriter(stm);
            element.WriteContentTo(wtr);
            wtr.Flush();
            stm.Position = 0;

            deserializedObject = serializer.Deserialize(stm);

            return deserializedObject;
        }

        //Saves the persistence data to an xml file.
        void Save(IDictionary<XName, InstanceValue> instanceData)
        {
            string fileName = IOHelper.GetFileName(this.ownerInstanceID);
            XmlDocument doc = new XmlDocument();
            doc.LoadXml("<InstanceValues/>");

            foreach (KeyValuePair<XName,InstanceValue> valPair in instanceData)
            {
                XmlElement newInstance = doc.CreateElement("InstanceValue");

                XmlElement newKey = SerializeObject("key", valPair.Key, doc);
                newInstance.AppendChild(newKey);

                XmlElement newValue = SerializeObject("value", valPair.Value.Value, doc);
                newInstance.AppendChild(newValue);

                doc.DocumentElement.AppendChild(newInstance);
            }
            doc.Save(fileName);
       }

        XmlElement SerializeObject(string elementName, object o, XmlDocument doc)
        {
            NetDataContractSerializer s = new NetDataContractSerializer();
            XmlElement newElement = doc.CreateElement(elementName);
            MemoryStream stm = new MemoryStream();

            s.Serialize(stm, o);
            stm.Position = 0;
            StreamReader rdr = new StreamReader(stm);
            newElement.InnerXml = rdr.ReadToEnd();

            return newElement;
        }
    }
}
```
