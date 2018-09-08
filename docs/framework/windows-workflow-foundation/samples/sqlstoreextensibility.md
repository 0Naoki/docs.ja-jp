---
title: SQLStoreExtensibility
ms.date: 03/30/2017
ms.assetid: 5da1b5a3-f144-41ba-b9c4-02818b28b15d
ms.openlocfilehash: f49d05244cf9f65a8e06f39c7e40391aaebd9f77
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/08/2018
ms.locfileid: "44202376"
---
# <a name="sqlstoreextensibility"></a><span data-ttu-id="40e1a-102">SQLStoreExtensibility</span><span class="sxs-lookup"><span data-stu-id="40e1a-102">SQLStoreExtensibility</span></span>
<span data-ttu-id="40e1a-103">このサンプルでは、SQL ワークフロー インスタンス ストアの昇格したプロパティの使用法と構成を示します。</span><span class="sxs-lookup"><span data-stu-id="40e1a-103">This sample demonstrates the use and configuration of promoted properties in the SQL workflow instance store.</span></span> <span data-ttu-id="40e1a-104">SQL Workflow Instance Store は、SQL ベースのインスタンス ストアの実装です。</span><span class="sxs-lookup"><span data-stu-id="40e1a-104">The SQL workflow instance store is a SQL-based implementation of an instance store.</span></span> <span data-ttu-id="40e1a-105">SQL Workflow Instance Store を使用すると、インスタンスの状態を SQL Server データベースや SQL Server Express データベースに保存したり読み込んだりすることができます。</span><span class="sxs-lookup"><span data-stu-id="40e1a-105">It allows an instance to save its state and load its state to and from a SQL Server or SQL Server Express database.</span></span> <span data-ttu-id="40e1a-106">ストア拡張機能を使用すると、ユーザーは、インスタンス ストアに格納されるプロパティを定義できます。</span><span class="sxs-lookup"><span data-stu-id="40e1a-106">The store extensibility feature allows the user to define properties that are stored in the instance store.</span></span> <span data-ttu-id="40e1a-107">このようなプロパティは、ユーザーがクエリを実行できる昇格したプロパティ ビューに表示されます。</span><span class="sxs-lookup"><span data-stu-id="40e1a-107">These properties are displayed in a promoted properties view that allows the user to query for them.</span></span>  
  
 <span data-ttu-id="40e1a-108">このサンプルは、カウント サービスを実装するワークフローで構成されています。</span><span class="sxs-lookup"><span data-stu-id="40e1a-108">This sample consists of a workflow that implements a counting service.</span></span> <span data-ttu-id="40e1a-109">サービスの start メソッドが呼び出されると、0 から 29 までのカウントが行われます。</span><span class="sxs-lookup"><span data-stu-id="40e1a-109">Once the service's start method is invoked, the service counts from 0 to 29.</span></span> <span data-ttu-id="40e1a-110">カウンターは 2 秒ごとにインクリメントされ、</span><span class="sxs-lookup"><span data-stu-id="40e1a-110">The counter is incremented once every 2 seconds.</span></span> <span data-ttu-id="40e1a-111">カウントのたびにワークフローが永続化されます。</span><span class="sxs-lookup"><span data-stu-id="40e1a-111">After each count, the workflow persists.</span></span> <span data-ttu-id="40e1a-112">現在のカウンター値は、昇格したプロパティとしてインスタンス ストアに格納されます。</span><span class="sxs-lookup"><span data-stu-id="40e1a-112">The current counter value is stored in the instance store as a promoted property.</span></span>  
  
 <span data-ttu-id="40e1a-113">このカウント ワークフローは、ワークフロー サービス ホストによってホストされる自己ホスト型サービスです。</span><span class="sxs-lookup"><span data-stu-id="40e1a-113">The Counting Workflow is self-hosted by a Workflow Service Host.</span></span> <span data-ttu-id="40e1a-114">プログラムの `Main` メソッドは、次のアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="40e1a-114">The program's `Main` method performs the following actions:</span></span>  
  
-   <span data-ttu-id="40e1a-115">カウント ワークフローをホストするワークフロー サービス ホストのインスタンスを作成し、カウント ワークフローにアクセスできるエンドポイントを定義します。</span><span class="sxs-lookup"><span data-stu-id="40e1a-115">Creates an instance of the Workflow Service Host that hosts the Counting Workflow and defines the endpoints under which the Counting Workflow can be reached.</span></span>  
  
-   <span data-ttu-id="40e1a-116">SQL Workflow Instance Store を構成するために使用される SQL Workflow Instance Store の動作を定義します。</span><span class="sxs-lookup"><span data-stu-id="40e1a-116">Defines a SQL workflow instance store behavior, which is used to configure the SQL workflow instance store.</span></span> <span data-ttu-id="40e1a-117">このストアは、`CountStatus` を昇格したプロパティとして扱うように指示されます。</span><span class="sxs-lookup"><span data-stu-id="40e1a-117">The store is instructed to treat `CountStatus` as a promoted property.</span></span>  
  
-   <span data-ttu-id="40e1a-118">カウント ワークフローの start メソッドを呼び出すクライアントを作成します。</span><span class="sxs-lookup"><span data-stu-id="40e1a-118">Creates a client that calls the start method of the counting workflow.</span></span>  
  
 <span data-ttu-id="40e1a-119">プログラムを開始すると、カウンターが自動的にカウントを開始します。</span><span class="sxs-lookup"><span data-stu-id="40e1a-119">Once the program is started, the counter automatically starts counting.</span></span> <span data-ttu-id="40e1a-120">インスタンスを読み込んで SQL Workflow Instance Store を構成するのに数秒かかる場合もあります。</span><span class="sxs-lookup"><span data-stu-id="40e1a-120">Note that it might take a few seconds to load the instance and configure the SQL workflow instance store.</span></span>  
  
 <span data-ttu-id="40e1a-121">カウンター値をカスタム プロパティとして昇格するには、次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="40e1a-121">To promote the counter value as a custom property, the following steps must be taken:</span></span>  
  
1.  <span data-ttu-id="40e1a-122">クラス `CounterStatus` は、<xref:System.Activities.Persistence.PersistenceParticipant> 型のインスタンス拡張機能を定義し、これはアクティビティが状態変数を提供するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="40e1a-122">The class `CounterStatus` defines an instance extension of type <xref:System.Activities.Persistence.PersistenceParticipant>, which is used by activities to supply the state variables.</span></span> <span data-ttu-id="40e1a-123">`Count` は書き込み専用値として定義されます。</span><span class="sxs-lookup"><span data-stu-id="40e1a-123">`Count` is defined as a write-only value.</span></span> <span data-ttu-id="40e1a-124">ワークフロー インスタンスが永続性ポイントに達すると、インスタンス拡張機能によって、`Count` プロパティが永続性データ コレクションに保存されます。</span><span class="sxs-lookup"><span data-stu-id="40e1a-124">When a workflow instance comes to a persistence point, the instance extension saves the `Count` property into the persistence data collection.</span></span>  
  
2.  <span data-ttu-id="40e1a-125">インスタンス ストアの作成時に、新しいプロパティ `CountStatus` が `store.Promote()` を使用して定義されます。</span><span class="sxs-lookup"><span data-stu-id="40e1a-125">When creating the instance store, a new property, `CountStatus`, is defined through the `store.Promote()` method.</span></span>  
  
3.  <span data-ttu-id="40e1a-126">ワークフローの `SaveCounter` アクティビティによって、現在のカウンター値が `Count` 状態フィールドに代入されます。</span><span class="sxs-lookup"><span data-stu-id="40e1a-126">The workflow's `SaveCounter` activity assigns the current counter value to the `Count` status field.</span></span>  
  
### <a name="to-use-this-sample"></a><span data-ttu-id="40e1a-127">このサンプルを使用するには</span><span class="sxs-lookup"><span data-stu-id="40e1a-127">To use this sample</span></span>  
  
1.  <span data-ttu-id="40e1a-128">インスタンス ストア データベースを作成します。</span><span class="sxs-lookup"><span data-stu-id="40e1a-128">Create the instance store database.</span></span>  
  
    1.  <span data-ttu-id="40e1a-129">[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] のコマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="40e1a-129">Open a [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] command prompt.</span></span>  
  
    2.  <span data-ttu-id="40e1a-130">[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] コマンド プロンプトでサンプル ディレクトリ (\WF\Basic\Persistence\SqlStoreExtensibility\CS) に移動して、CreateInstanceStore.cmd を実行します。</span><span class="sxs-lookup"><span data-stu-id="40e1a-130">Navigate to the sample directory (\WF\Basic\Persistence\SqlStoreExtensibility\CS) and run CreateInstanceStore.cmd in the [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] command prompt.</span></span>  
  
        > [!WARNING]
        >  <span data-ttu-id="40e1a-131">CreateInstanceStore.cmd スクリプトは、SQL Server 2008 Express の既定のインスタンスにデータベースを作成しようとします。</span><span class="sxs-lookup"><span data-stu-id="40e1a-131">The CreateInstanceStore.cmd script attempts to create the database on the default instance of SQL Server 2008 Express.</span></span> <span data-ttu-id="40e1a-132">別のインスタンスにデータベースをインストールする場合は、そのようにスクリプトを変更してください。</span><span class="sxs-lookup"><span data-stu-id="40e1a-132">If you want to install the database on a different instance, modify the script to do so.</span></span>  
  
2.  <span data-ttu-id="40e1a-133">[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] を開いて SqlStoreExtensibility.sln ソリューションを読み込み、Ctrl キーと Shift キーを押しながら B キーを押してビルドします。</span><span class="sxs-lookup"><span data-stu-id="40e1a-133">Open [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] and load the SqlStoreExtensibility.sln solution and build it by pressing CTRL+SHIFT+B.</span></span>  
  
    > [!WARNING]
    >  <span data-ttu-id="40e1a-134">SQL Server の既定以外のインスタンスにデータベースをインストールした場合は、ソリューションをビルドする前に、コードの接続文字列を更新してください。</span><span class="sxs-lookup"><span data-stu-id="40e1a-134">If you installed the database on a non-default instance of SQL Server, update the connection string in the code prior to building the solution.</span></span>  
  
3.  <span data-ttu-id="40e1a-135">プロジェクトの bin ディレクトリ (\WF\Basic\Persistence\SqlStoreExtensibility\bin\Debug) に移動して、サンプルを管理者特権で実行[!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)]SqlStoreExtensibility.exe を右クリックし、選択、**として実行管理者**します。</span><span class="sxs-lookup"><span data-stu-id="40e1a-135">Run the sample with administrator privileges by navigating to the project’s bin directory (\WF\Basic\Persistence\SqlStoreExtensibility\bin\Debug) in [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)], right-clicking SqlStoreExtensibility.exe and selecting **Run as Administrator**.</span></span>  
  
### <a name="to-verify-the-sample-is-working-correctly"></a><span data-ttu-id="40e1a-136">サンプルが正常に動作していることを確認するには</span><span class="sxs-lookup"><span data-stu-id="40e1a-136">To verify the sample is working correctly</span></span>  
  
1.  <span data-ttu-id="40e1a-137">SQL Server Management Studio を使用して、選択してインスタンス テーブルの内容を表示する**データベース**、 **InstanceStore**、し**System.ServiceModel.Activities.DurableInstancing.InstanceTable**オブジェクト エクスプ ローラーで右クリックして**System.ServiceModel.Activities.DurableInstancing.InstanceTable** を選択します。**上位 1000 行を選択します。** します。</span><span class="sxs-lookup"><span data-stu-id="40e1a-137">Use SQL Server Management Studio to view the contents of the instance table by selecting **Databases**, **InstanceStore**, and then **System.ServiceModel.Activities.DurableInstancing.InstanceTable** in the Object Explorer, right-click **System.ServiceModel.Activities.DurableInstancing.InstanceTable** and select **Select Top 1000 Rows**.</span></span> <span data-ttu-id="40e1a-138">SQL Server Management Studio の詳細については、次を参照してください[SQL Server Management Studio の概要。](https://go.microsoft.com/fwlink/?LinkId=165645)</span><span class="sxs-lookup"><span data-stu-id="40e1a-138">For more information about SQL Server Management Studio, see [Introducing SQL Server Management Studio](https://go.microsoft.com/fwlink/?LinkId=165645)</span></span>  
  
2.  <span data-ttu-id="40e1a-139">一覧表示されるワークフロー インスタンスを確認します。</span><span class="sxs-lookup"><span data-stu-id="40e1a-139">Observe the workflow instances listed.</span></span>  
  
3.  <span data-ttu-id="40e1a-140">[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] コマンド プロンプトで、サンプル ディレクトリ (\WF\Basic\Persistence\SqlStoreExtensibility) にある QueryInstanceStore.cmd スクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="40e1a-140">In a [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] command prompt, run the QueryInstanceStore.cmd script located in the sample directory (\WF\Basic\Persistence\SqlStoreExtensibility).</span></span>  
  
4.  <span data-ttu-id="40e1a-141">下に表示されるカウンターの値を観察**CountStatus**します。</span><span class="sxs-lookup"><span data-stu-id="40e1a-141">Observe the counter value displayed under **CountStatus**.</span></span>  
  
5.  <span data-ttu-id="40e1a-142">何回かスクリプトを実行して、 **CountStats**値の変更。</span><span class="sxs-lookup"><span data-stu-id="40e1a-142">Run the script a few times to see the **CountStats** value change.</span></span>  
  
6.  <span data-ttu-id="40e1a-143">Enter キーを押してワークフロー アプリケーションを終了します。</span><span class="sxs-lookup"><span data-stu-id="40e1a-143">Press ENTER to terminate the workflow application.</span></span>  
  
### <a name="to-uninstall-the-sample"></a><span data-ttu-id="40e1a-144">サンプルをアンインストールするには</span><span class="sxs-lookup"><span data-stu-id="40e1a-144">To uninstall the sample</span></span>  
  
1.  <span data-ttu-id="40e1a-145">サンプル ディレクトリ (\WF\Basic\Persistence\SqlStoreExtensibility) にある RemoveInstanceStore.cmd スクリプトを実行して、インスタンス ストア データベースを削除します。</span><span class="sxs-lookup"><span data-stu-id="40e1a-145">Remove the instance store database by running the RemoveInstanceStore.cmd script located in the sample directory (\WF\Basic\Persistence\SqlStoreExtensibility).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="40e1a-146">サンプルは、既にコンピューターにインストールされている場合があります。</span><span class="sxs-lookup"><span data-stu-id="40e1a-146">The samples may already be installed on your machine.</span></span> <span data-ttu-id="40e1a-147">続行する前に、次の (既定の) ディレクトリを確認してください。</span><span class="sxs-lookup"><span data-stu-id="40e1a-147">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="40e1a-148">このディレクトリが存在しない場合に移動[Windows Communication Foundation (WCF) と .NET Framework 4 向けの Windows Workflow Foundation (WF) サンプル](https://go.microsoft.com/fwlink/?LinkId=150780)すべて Windows Communication Foundation (WCF) をダウンロードして[!INCLUDE[wf1](../../../../includes/wf1-md.md)]サンプル。</span><span class="sxs-lookup"><span data-stu-id="40e1a-148">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="40e1a-149">このサンプルは、次のディレクトリに格納されます。</span><span class="sxs-lookup"><span data-stu-id="40e1a-149">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Persistence\SQLStoreExtensibility`  
  
## <a name="see-also"></a><span data-ttu-id="40e1a-150">関連項目</span><span class="sxs-lookup"><span data-stu-id="40e1a-150">See Also</span></span>  
 [<span data-ttu-id="40e1a-151">ワークフローの永続性</span><span class="sxs-lookup"><span data-stu-id="40e1a-151">Workflow Persistence</span></span>](../../../../docs/framework/windows-workflow-foundation/workflow-persistence.md)  
 [<span data-ttu-id="40e1a-152">ワークフロー サービス</span><span class="sxs-lookup"><span data-stu-id="40e1a-152">Workflow Services</span></span>](../../../../docs/framework/wcf/feature-details/workflow-services.md)  
 [<span data-ttu-id="40e1a-153">AppFabric のホストおよび永続化のサンプル</span><span class="sxs-lookup"><span data-stu-id="40e1a-153">AppFabric Hosting and Persistence Samples</span></span>](https://go.microsoft.com/fwlink/?LinkId=193961)
