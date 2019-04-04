---
title: 長時間のワークフロー サービスの作成
ms.date: 03/30/2017
ms.assetid: 4c39bd04-5b8a-4562-a343-2c63c2821345
ms.openlocfilehash: 8fe1ad70db6c788a304d9099fb2f35a4d89db489
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2019
ms.locfileid: "57679438"
---
# <a name="creating-a-long-running-workflow-service"></a><span data-ttu-id="74e44-102">長時間のワークフロー サービスの作成</span><span class="sxs-lookup"><span data-stu-id="74e44-102">Creating a Long-running Workflow Service</span></span>
<span data-ttu-id="74e44-103">ここでは、実行時間の長いワークフロー サービスを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="74e44-103">This topic describes how to create a long-running workflow service.</span></span> <span data-ttu-id="74e44-104">実行時間の長いワークフロー サービスは、長期間にわたって実行できます。</span><span class="sxs-lookup"><span data-stu-id="74e44-104">Long running workflow services may run for long periods of time.</span></span> <span data-ttu-id="74e44-105">ワークフローでは、いくつかの追加情報を待つ間アイドル状態になることがあります。</span><span class="sxs-lookup"><span data-stu-id="74e44-105">At some point the workflow may go idle waiting for some additional information.</span></span> <span data-ttu-id="74e44-106">アイドル状態になると、ワークフローは SQL データベースに永続化され、メモリから削除されます。</span><span class="sxs-lookup"><span data-stu-id="74e44-106">When this occurs the workflow is persisted to a SQL database and is removed from memory.</span></span> <span data-ttu-id="74e44-107">追加情報が使用可能になると、ワークフロー インスタンスがメモリに読み込み直されて、実行を継続します。</span><span class="sxs-lookup"><span data-stu-id="74e44-107">When the additional information becomes available the workflow instance is loaded back into memory and continues executing.</span></span>  <span data-ttu-id="74e44-108">このシナリオでは、非常に簡略化された注文システムを実装します。</span><span class="sxs-lookup"><span data-stu-id="74e44-108">In this scenario you are implementing a very simplified ordering system.</span></span>  <span data-ttu-id="74e44-109">クライアントは、最初のメッセージをワークフロー サービスに送信して注文を開始します。</span><span class="sxs-lookup"><span data-stu-id="74e44-109">The client sends an initial message to the workflow service to start the order.</span></span> <span data-ttu-id="74e44-110">ワークフロー サービスは、注文 ID をクライアントに返します。</span><span class="sxs-lookup"><span data-stu-id="74e44-110">It returns an order ID to the client.</span></span> <span data-ttu-id="74e44-111">この時点で、ワークフロー サービスは、クライアントからの別のメッセージを待機しており、アイドル状態に入って、SQL Server データベースに永続化されます。</span><span class="sxs-lookup"><span data-stu-id="74e44-111">At this point the workflow service is waiting for another message from the client and goes into the idle state and is persisted to a SQL Server database.</span></span>  <span data-ttu-id="74e44-112">クライアントが次のメッセージを送信して項目を注文すると、ワークフロー サービスはメモリに読み込み直されて、注文の処理を終了します。</span><span class="sxs-lookup"><span data-stu-id="74e44-112">When the client sends the next message to order an item, the workflow service is loaded back into memory and finishes processing the order.</span></span> <span data-ttu-id="74e44-113">次のコード例では、項目が注文に追加されたことを示す文字列を返します。</span><span class="sxs-lookup"><span data-stu-id="74e44-113">In the code sample it returns a string stating the item has been added to the order.</span></span> <span data-ttu-id="74e44-114">このコード例は、テクノロジの実際の適用を意図するものではなく、実行時間の長いワークフロー サービスを示す簡単な例です。</span><span class="sxs-lookup"><span data-stu-id="74e44-114">The code sample is not meant to be a real world application of the technology, but rather a simple sample that illustrates long running workflow services.</span></span> <span data-ttu-id="74e44-115">このトピックでは、Visual Studio 2012 プロジェクトとソリューションの作成方法を知っていると仮定します。</span><span class="sxs-lookup"><span data-stu-id="74e44-115">This topic assumes you know how to create Visual Studio 2012 projects and solutions.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="74e44-116">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="74e44-116">Prerequisites</span></span>
 <span data-ttu-id="74e44-117">このチュートリアルを使用するには、次のソフトウェアがインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="74e44-117">You must have the following software installed to use this walkthrough:</span></span>

1.  <span data-ttu-id="74e44-118">Microsoft SQL Server 2008</span><span class="sxs-lookup"><span data-stu-id="74e44-118">Microsoft SQL Server 2008</span></span>

2.  <span data-ttu-id="74e44-119">Visual Studio 2012</span><span class="sxs-lookup"><span data-stu-id="74e44-119">Visual Studio 2012</span></span>

3.  <span data-ttu-id="74e44-120">Microsoft [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)]</span><span class="sxs-lookup"><span data-stu-id="74e44-120">Microsoft  [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)]</span></span>

4.  <span data-ttu-id="74e44-121">WCF と Visual Studio 2012 に精通し、プロジェクト/ソリューションを作成する方法を理解します。</span><span class="sxs-lookup"><span data-stu-id="74e44-121">You are familiar with WCF and Visual Studio 2012 and know how to create projects/solutions.</span></span>

### <a name="to-setup-the-sql-database"></a><span data-ttu-id="74e44-122">SQL データベースを設定するには</span><span class="sxs-lookup"><span data-stu-id="74e44-122">To Setup the SQL Database</span></span>

1.  <span data-ttu-id="74e44-123">ワークフロー サービス インスタンスが永続化されるようにするには、Microsoft SQL Server をインストールして、永続化ワークフロー インスタンスを保存するようにデータベースを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="74e44-123">In order for workflow service instances to be persisted you must have Microsoft SQL Server installed and you must configure a database to store the persisted workflow instances.</span></span> <span data-ttu-id="74e44-124">クリックして、Microsoft SQL Management Studio を実行、**開始**ボタンをクリックして**すべてのプログラム**、 **Microsoft SQL Server 2008**、および**Microsoft SQLManagement Studio**します。</span><span class="sxs-lookup"><span data-stu-id="74e44-124">Run Microsoft SQL Management Studio by clicking the **Start** button, selecting **All Programs**, **Microsoft SQL Server 2008**, and **Microsoft SQL Management Studio**.</span></span>

2.  <span data-ttu-id="74e44-125">をクリックして、 **Connect** SQL Server インスタンスにログオンする ボタン</span><span class="sxs-lookup"><span data-stu-id="74e44-125">Click the **Connect** button to log on to the SQL Server instance</span></span>

3.  <span data-ttu-id="74e44-126">右クリックして**データベース**クリックし、ツリー ビューで**新しいデータベース.**</span><span class="sxs-lookup"><span data-stu-id="74e44-126">Right click **Databases** in the tree view and select **New Database..**</span></span> <span data-ttu-id="74e44-127">という新しいデータベースを作成する`SQLPersistenceStore`します。</span><span class="sxs-lookup"><span data-stu-id="74e44-127">to create a new database called `SQLPersistenceStore`.</span></span>

4.  <span data-ttu-id="74e44-128">SQLPersistenceStore データベースの C:\Windows\Microsoft.NET\Framework\v4.0\SQL\en ディレクトリにある SqlWorkflowInstanceStoreSchema.sql スクリプト ファイルを実行して、必要なデータベース スキーマを設定します。</span><span class="sxs-lookup"><span data-stu-id="74e44-128">Run the SqlWorkflowInstanceStoreSchema.sql script file located in the C:\Windows\Microsoft.NET\Framework\v4.0\SQL\en directory on the SQLPersistenceStore database to set up the needed database schemas.</span></span>

5.  <span data-ttu-id="74e44-129">SQLPersistenceStore データベースの C:\Windows\Microsoft.NET\Framework\v4.0\SQL\en ディレクトリにある SqlWorkflowInstanceStoreLogic.sql スクリプト ファイルを実行して、必要なデータベース ロジックを設定します。</span><span class="sxs-lookup"><span data-stu-id="74e44-129">Run the SqlWorkflowInstanceStoreLogic.sql script file located in the C:\Windows\Microsoft.NET\Framework\v4.0\SQL\en directory on the SQLPersistenceStore database to set up the needed database logic.</span></span>

### <a name="to-create-the-web-hosted-workflow-service"></a><span data-ttu-id="74e44-130">Web ホスト ワークフロー サービスを作成するには</span><span class="sxs-lookup"><span data-stu-id="74e44-130">To Create the Web Hosted Workflow Service</span></span>

1.  <span data-ttu-id="74e44-131">空の Visual Studio 2012 ソリューションを作成、名前を付けます`OrderProcessing`します。</span><span class="sxs-lookup"><span data-stu-id="74e44-131">Create an empty Visual Studio 2012 solution, name it `OrderProcessing`.</span></span>

2.  <span data-ttu-id="74e44-132">
  `OrderService\` という新しい WCF ワークフロー サービス アプリケーション プロジェクトをソリューションに追加します。</span><span class="sxs-lookup"><span data-stu-id="74e44-132">Add a new WCF Workflow Service Application project called `OrderService` to the solution.</span></span>

3.  <span data-ttu-id="74e44-133">プロジェクトのプロパティ ダイアログ ボックスで、 **Web**タブ。</span><span class="sxs-lookup"><span data-stu-id="74e44-133">In the project properties dialog, select the **Web** tab.</span></span>

    1.  <span data-ttu-id="74e44-134">**開始動作**選択**特定のページ**指定`Service1.xamlx`。</span><span class="sxs-lookup"><span data-stu-id="74e44-134">Under **Start Action** select **Specific Page** and specify `Service1.xamlx`.</span></span>

         <span data-ttu-id="74e44-135">![ワークフロー サービス プロジェクトの Web プロパティ](./media/creating-a-long-running-workflow-service/start-action-specific-page-option.png "web ホスト ワークフロー サービス - 特定のページのオプションを作成します。")</span><span class="sxs-lookup"><span data-stu-id="74e44-135">![Workflow Service Project Web Properties](./media/creating-a-long-running-workflow-service/start-action-specific-page-option.png "Create the web hosted workflow service - Specific Page option")</span></span>

    2.  <span data-ttu-id="74e44-136">**サーバー**選択**使用ローカル IIS Web サーバー**します。</span><span class="sxs-lookup"><span data-stu-id="74e44-136">Under **Servers** select **Use Local IIS Web server**.</span></span>

         <span data-ttu-id="74e44-137">![ローカル Web サーバー設定](./media/creating-a-long-running-workflow-service/use-local-web-server.png "オプションを使用してローカル IIS Web サーバー - web ホスト ワークフロー サービスの作成")</span><span class="sxs-lookup"><span data-stu-id="74e44-137">![Local Web Server Settings](./media/creating-a-long-running-workflow-service/use-local-web-server.png "Create the web hosted workflow service - Use Local IIS Web Server option")</span></span>

        > [!WARNING]
        >  <span data-ttu-id="74e44-138">この設定を行うには管理者モードでは、Visual Studio 2012 を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="74e44-138">You must run Visual Studio 2012 in administrator mode to make this setting.</span></span>

         <span data-ttu-id="74e44-139">次の 2 つの手順で、ワークフロー サービス プロジェクトが IIS でホストされるように設定します。</span><span class="sxs-lookup"><span data-stu-id="74e44-139">These two steps configure the workflow service project to be hosted by IIS.</span></span>

4.  <span data-ttu-id="74e44-140">開く`Service1.xamlx`いない既にを開くし、既存の削除である場合**ReceiveRequest**と**SendResponse**アクティビティ。</span><span class="sxs-lookup"><span data-stu-id="74e44-140">Open `Service1.xamlx` if it is not open already and delete the existing **ReceiveRequest** and **SendResponse** activities.</span></span>

5.  <span data-ttu-id="74e44-141">選択、**シーケンシャル サービス**アクティビティをクリックして、**変数**リンクし、次の図に示すように変数を追加します。</span><span class="sxs-lookup"><span data-stu-id="74e44-141">Select the **Sequential Service** activity and click the **Variables** link and add the variables shown in the following illustration.</span></span> <span data-ttu-id="74e44-142">こうするといくつかの変数が追加され、後でワークフロー サービスで使用されます。</span><span class="sxs-lookup"><span data-stu-id="74e44-142">Doing this adds some variables that will be used later on in the workflow service.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="74e44-143">CorrelationHandle が変数の型のドロップダウン リストにない場合は、選択**型の参照**ドロップダウン リストから。</span><span class="sxs-lookup"><span data-stu-id="74e44-143">If CorrelationHandle is not in the Variable Type drop-down, select **Browse for types** from the drop-down.</span></span> <span data-ttu-id="74e44-144">CorrelationHandle を入力、**型名**ボックスで、リスト ボックスから CorrelationHandle を選択し、をクリックして**OK**します。</span><span class="sxs-lookup"><span data-stu-id="74e44-144">Type CorrelationHandle in the **Type name** box, select CorrelationHandle from the listbox and click **OK**.</span></span>

     <span data-ttu-id="74e44-145">![変数を追加](./media/creating-a-long-running-workflow-service/add-variables-sequential-service-activity.gif "変数シーケンシャル サービス アクティビティを追加します。")</span><span class="sxs-lookup"><span data-stu-id="74e44-145">![Add Variables](./media/creating-a-long-running-workflow-service/add-variables-sequential-service-activity.gif "Add variables to the Sequential Service activity.")</span></span>

6.  <span data-ttu-id="74e44-146">ドラッグ アンド ドロップ、 **ReceiveAndSendReply**アクティビティ テンプレートを**シーケンシャル サービス**アクティビティ。</span><span class="sxs-lookup"><span data-stu-id="74e44-146">Drag and drop a **ReceiveAndSendReply** activity template into the **Sequential Service** activity.</span></span> <span data-ttu-id="74e44-147">このアクティビティのセットは、クライアントからメッセージを受信して、返信を送信します。</span><span class="sxs-lookup"><span data-stu-id="74e44-147">This set of activities will receive a message from a client and send a reply back.</span></span>

    1.  <span data-ttu-id="74e44-148">選択、**受信**アクティビティとセットのプロパティは、次の図で強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="74e44-148">Select the **Receive** activity and set the properties highlighted in the following illustration.</span></span>

         <span data-ttu-id="74e44-149">![受信アクティビティのプロパティを設定](./media/creating-a-long-running-workflow-service/set-receive-activity-properties.png "受信アクティビティのプロパティを設定します。")</span><span class="sxs-lookup"><span data-stu-id="74e44-149">![Set Receive Activity Properties](./media/creating-a-long-running-workflow-service/set-receive-activity-properties.png "Set the Receive activity properties.")</span></span>

         <span data-ttu-id="74e44-150">DisplayName プロパティは、デザイナーに表示される Receive アクティビティの名前を設定します。</span><span class="sxs-lookup"><span data-stu-id="74e44-150">The DisplayName property sets the name displayed for the Receive activity in the designer.</span></span> <span data-ttu-id="74e44-151">ServiceContractName プロパティと OperationName プロパティは、Receive アクティビティで実装されるサービス コントラクトおよび操作の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="74e44-151">The ServiceContractName and OperationName properties specify the name of the service contract and operation that are implemented by the Receive activity.</span></span> <span data-ttu-id="74e44-152">ワークフロー サービスでのコントラクトの使用方法の詳細については、[ワークフローを使用してコントラクト](../../../../docs/framework/wcf/feature-details/using-contracts-in-workflow.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="74e44-152">For more information about how contracts are used in Workflow services see [Using Contracts in Workflow](../../../../docs/framework/wcf/feature-details/using-contracts-in-workflow.md).</span></span>

    2.  <span data-ttu-id="74e44-153">をクリックして、**を定義しています.** のリンクを**ReceiveStartOrder**活動し、次の図に示すようにプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="74e44-153">Click the **Define...** link in the **ReceiveStartOrder** activity and set the properties shown in the following illustration.</span></span>  <span data-ttu-id="74e44-154">注意、**パラメーター**オプション ボタンを選択すると、という名前のパラメーター`p_customerName`にバインドされて、`customerName`変数。</span><span class="sxs-lookup"><span data-stu-id="74e44-154">Notice that the **Parameters** radio button is selected, a parameter named `p_customerName` is bound to the `customerName` variable.</span></span> <span data-ttu-id="74e44-155">これにより、構成、**受信**アクティビティをいくつかのデータを受信し、そのデータをローカル変数にバインドします。</span><span class="sxs-lookup"><span data-stu-id="74e44-155">This configures the **Receive** activity to receive some data and bind that data to local variables.</span></span>

         <span data-ttu-id="74e44-156">![Receive アクティビティが受信するデータを設定](./media/creating-a-long-running-workflow-service/set-properties-for-receive-content.png "Receive アクティビティで受信したデータのプロパティを設定します。")</span><span class="sxs-lookup"><span data-stu-id="74e44-156">![Setting the data received by the Receive activity](./media/creating-a-long-running-workflow-service/set-properties-for-receive-content.png "Set the properties for data received by the Receive activity.")</span></span>

    3.  <span data-ttu-id="74e44-157">選択、 **SendReplyToReceive**活動し、次の図に示すように強調表示されているプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="74e44-157">Select The **SendReplyToReceive** activity and set the highlighted property shown in the following illustration.</span></span>

         <span data-ttu-id="74e44-158">![SendReply アクティビティのプロパティを設定](./media/creating-a-long-running-workflow-service/set-properties-for-reply-activities.png "SetReplyProperties")</span><span class="sxs-lookup"><span data-stu-id="74e44-158">![Setting the properties of the SendReply activity](./media/creating-a-long-running-workflow-service/set-properties-for-reply-activities.png "SetReplyProperties")</span></span>

    4.  <span data-ttu-id="74e44-159">をクリックして、**を定義しています.** のリンクを**SendReplyToStartOrder**活動し、次の図に示すようにプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="74e44-159">Click the **Define...** link in the **SendReplyToStartOrder** activity and set the properties shown in the following illustration.</span></span> <span data-ttu-id="74e44-160">注意、**パラメーター**ラジオ ボタンが選択されている; という名前のパラメーター`p_orderId`にバインドされて、`orderId`変数。</span><span class="sxs-lookup"><span data-stu-id="74e44-160">Notice that the **Parameters** radio button is selected; a parameter named `p_orderId` is bound to the `orderId` variable.</span></span> <span data-ttu-id="74e44-161">この設定により、SendReplyToStartOrder アクティビティが型文字列の値を呼び出し元に返すように指定されます。</span><span class="sxs-lookup"><span data-stu-id="74e44-161">This setting specifies that the SendReplyToStartOrder activity will return a value of type string to the caller.</span></span>

         <span data-ttu-id="74e44-162">![SendReply アクティビティのコンテンツ データを構成する](./media/creating-a-long-running-workflow-service/setreplycontent-for-sendreplytostartorder-activity.png "SetReplyToStartOrder アクティビティの設定を構成します。")</span><span class="sxs-lookup"><span data-stu-id="74e44-162">![Configuring the SendReply activity content data](./media/creating-a-long-running-workflow-service/setreplycontent-for-sendreplytostartorder-activity.png "Configure setting for SetReplyToStartOrder activity.")</span></span>

    5.  <span data-ttu-id="74e44-163">ドラッグ アンド間に、Assign アクティビティをドロップ、**受信**と**SendReply**活動し、次の図に示すようにプロパティを設定。</span><span class="sxs-lookup"><span data-stu-id="74e44-163">Drag and drop an Assign activity in between the **Receive** and **SendReply** activities and set the properties as shown in the following illustration:</span></span>

         <span data-ttu-id="74e44-164">![Assign アクティビティの追加](./media/creating-a-long-running-workflow-service/add-an-assign-activity.png "assign アクティビティを追加します。")</span><span class="sxs-lookup"><span data-stu-id="74e44-164">![Adding an assign activity](./media/creating-a-long-running-workflow-service/add-an-assign-activity.png "Add an assign activity.")</span></span>

         <span data-ttu-id="74e44-165">これにより、新しい注文 ID が作成され、orderId 変数に値が配置されます。</span><span class="sxs-lookup"><span data-stu-id="74e44-165">This creates a new order ID and places the value in the orderId variable.</span></span>

    6.  <span data-ttu-id="74e44-166">選択、 **ReplyToStartOrder**アクティビティ。</span><span class="sxs-lookup"><span data-stu-id="74e44-166">Select the **ReplyToStartOrder** activity.</span></span> <span data-ttu-id="74e44-167">[プロパティ] ウィンドウの省略記号ボタンをクリックします。 **CorrelationInitializers**します。</span><span class="sxs-lookup"><span data-stu-id="74e44-167">In the properties window click the ellipsis button for **CorrelationInitializers**.</span></span> <span data-ttu-id="74e44-168">選択、**初期化子を追加**リンクで、入力`orderIdHandle`初期化子のテキスト ボックスで、関連付けの種類のクエリ関連付け初期化子を選択し、XPATH クエリのドロップダウン ボックスの下の p_orderId を選択します。</span><span class="sxs-lookup"><span data-stu-id="74e44-168">Select the **Add initializer** link, enter `orderIdHandle` in the Initializer text box, select Query correlation initializer for the Correlation type, and select p_orderId under the XPATH Queries dropdown box.</span></span> <span data-ttu-id="74e44-169">これらの設定を次の図に示します。</span><span class="sxs-lookup"><span data-stu-id="74e44-169">These settings are shown in the following illustration.</span></span> <span data-ttu-id="74e44-170">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="74e44-170">Click **OK**.</span></span>  <span data-ttu-id="74e44-171">これにより、クライアントとワークフロー サービスのこのインスタンス間の相関関係が初期化されます。</span><span class="sxs-lookup"><span data-stu-id="74e44-171">This initializes a correlation between the client and this instance of the workflow service.</span></span> <span data-ttu-id="74e44-172">この注文 ID を含むメッセージが受信されると、ワークフロー サービスのこのインスタンスにルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="74e44-172">When a message containing this order ID is received it is routed to this instance of the workflow service.</span></span>

         <span data-ttu-id="74e44-173">![関連付け初期化子を追加する](./media/creating-a-long-running-workflow-service/add-correlationinitializers.png "関連付け初期化子を追加します。")</span><span class="sxs-lookup"><span data-stu-id="74e44-173">![Adding a correlation initializer](./media/creating-a-long-running-workflow-service/add-correlationinitializers.png "Add a correlation initializer.")</span></span>

7.  <span data-ttu-id="74e44-174">ドラッグ アンド ドロップ別**ReceiveAndSendReply**ワークフローの末尾にアクティビティ (外部、**シーケンス**最初を格納している**受信**と**SendReply**アクティビティ)。</span><span class="sxs-lookup"><span data-stu-id="74e44-174">Drag and drop another **ReceiveAndSendReply** activity to the end of the workflow (outside the **Sequence** containing the first **Receive** and **SendReply** activities).</span></span> <span data-ttu-id="74e44-175">これで、クライアントで送信された 2 つ目のメッセージを受信し、それに応答します。</span><span class="sxs-lookup"><span data-stu-id="74e44-175">This will receive the second message sent by the client and respond to it.</span></span>

    1.  <span data-ttu-id="74e44-176">選択、**シーケンス**、新しく追加したを格納している**受信**と**SendReply**アクティビティをクリックして、**変数**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="74e44-176">Select the **Sequence** that contains the newly added **Receive** and **SendReply** activities and click the **Variables** button.</span></span> <span data-ttu-id="74e44-177">次の図で強調表示されている変数を追加します。</span><span class="sxs-lookup"><span data-stu-id="74e44-177">Add the variable highlighted in the following illustration:</span></span>

         <span data-ttu-id="74e44-178">![新しい変数を追加する](./media/creating-a-long-running-workflow-service/add-the-itemid-variable.png "ItemId 変数を追加します。")</span><span class="sxs-lookup"><span data-stu-id="74e44-178">![Adding new variables](./media/creating-a-long-running-workflow-service/add-the-itemid-variable.png "Add the ItemId variable.")</span></span>

    2.  <span data-ttu-id="74e44-179">選択、**受信**アクティビティし、次の図に示すようにプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="74e44-179">Select the **Receive** activity and set the properties shown in the following illustration:</span></span>

         <span data-ttu-id="74e44-180">![Receive アクティビティのプロパティを設定](./media/creating-a-long-running-workflow-service/set-receive-activities-properties.png "受信アクティビティのプロパティを設定します。")</span><span class="sxs-lookup"><span data-stu-id="74e44-180">![Set the Receive acitivity properties](./media/creating-a-long-running-workflow-service/set-receive-activities-properties.png "Set the Receive activities properties.")</span></span>

    3.  <span data-ttu-id="74e44-181">をクリックして、**を定義しています.** のリンクを**ReceiveAddItem**アクティビティし、次の図に示すようにパラメーターを追加します。 注文 ID、および注文されている項目の ID の 2 つのパラメーターを受け入れるように、receive アクティビティを構成します。</span><span class="sxs-lookup"><span data-stu-id="74e44-181">Click the **Define...** link in the **ReceiveAddItem** activity and add the parameters shown in the following illustration:This configures the receive activity to accept two parameters, the order ID and the ID of the item being ordered.</span></span>

         <span data-ttu-id="74e44-182">![受信側の 2 番目のパラメーターを指定する](./media/creating-a-long-running-workflow-service/add-receive-two-parameters.png "2 つのパラメーターを受信する受信アクティビティを構成します。")</span><span class="sxs-lookup"><span data-stu-id="74e44-182">![Specifying parameters for the second receive](./media/creating-a-long-running-workflow-service/add-receive-two-parameters.png "Configure the receive activity to receive two parameters.")</span></span>

    4.  <span data-ttu-id="74e44-183">をクリックして、 **CorrelateOn**省略記号ボタンをクリックし、入力`orderIdHandle`します。</span><span class="sxs-lookup"><span data-stu-id="74e44-183">Click the **CorrelateOn** ellipsis button and enter `orderIdHandle`.</span></span> <span data-ttu-id="74e44-184">**XPath クエリ**ドロップダウン矢印をクリックし、選択`p_orderId`します。</span><span class="sxs-lookup"><span data-stu-id="74e44-184">Under **XPath Queries**, click the drop down arrow and select `p_orderId`.</span></span> <span data-ttu-id="74e44-185">これにより、2 つ目の Receive アクティビティに相関関係が設定されます。</span><span class="sxs-lookup"><span data-stu-id="74e44-185">This configures the correlation on the second receive activity.</span></span> <span data-ttu-id="74e44-186">相関関係の詳細については、[相関](../../../../docs/framework/wcf/feature-details/correlation.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="74e44-186">For more information about correlation see [Correlation](../../../../docs/framework/wcf/feature-details/correlation.md).</span></span>

         <span data-ttu-id="74e44-187">![CorrelatesOn プロパティの設定](./media/creating-a-long-running-workflow-service/correlateson-setting.png "CorrelatesOn プロパティを設定します。")</span><span class="sxs-lookup"><span data-stu-id="74e44-187">![Setting the CorrelatesOn property](./media/creating-a-long-running-workflow-service/correlateson-setting.png "Set the CorrelatesOn property.")</span></span>

    5.  <span data-ttu-id="74e44-188">ドラッグ アンド ドロップ、**場合**アクティビティの直後に、 **ReceiveAddItem**アクティビティ。</span><span class="sxs-lookup"><span data-stu-id="74e44-188">Drag and drop an **If** activity immediately after the **ReceiveAddItem** activity.</span></span> <span data-ttu-id="74e44-189">このアクティビティは、if ステートメントと同様に動作します。</span><span class="sxs-lookup"><span data-stu-id="74e44-189">This activity acts just like an if statement.</span></span>

        1.  <span data-ttu-id="74e44-190">設定、**条件**プロパティを `itemId=="Zune HD" (itemId="Zune HD" for Visual Basic)`</span><span class="sxs-lookup"><span data-stu-id="74e44-190">Set the **Condition** property to `itemId=="Zune HD" (itemId="Zune HD" for Visual Basic)`</span></span>

        2.  <span data-ttu-id="74e44-191">ドラッグ アンド ドロップ、**割り当てる**アクティビティを**し**セクションと、 **Else**セクションのプロパティを設定する、**割り当てる**次の図に示すように処理します。</span><span class="sxs-lookup"><span data-stu-id="74e44-191">Drag and drop an **Assign** activity in to the **Then** section and another into the **Else** section set the properties of the **Assign** activities as shown in the following illustration.</span></span>

             <span data-ttu-id="74e44-192">![サービス呼び出しの結果を代入](./media/creating-a-long-running-workflow-service/assign-result-of-service-call.png "サービス呼び出しの結果を代入します。")</span><span class="sxs-lookup"><span data-stu-id="74e44-192">![Assigning the result of the service call](./media/creating-a-long-running-workflow-service/assign-result-of-service-call.png "Assign the result of the service call.")</span></span>

             <span data-ttu-id="74e44-193">条件が場合`true`、**し**セクションが実行されます。</span><span class="sxs-lookup"><span data-stu-id="74e44-193">If the condition is `true` the **Then** section will be executed.</span></span> <span data-ttu-id="74e44-194">条件が場合`false`、 **Else**セクションが実行されます。</span><span class="sxs-lookup"><span data-stu-id="74e44-194">If the condition is `false` the **Else** section is executed.</span></span>

        3.  <span data-ttu-id="74e44-195">選択、 **SendReplyToReceive**アクティビティと設定、 **DisplayName**プロパティを次の図に示すようにします。</span><span class="sxs-lookup"><span data-stu-id="74e44-195">Select the **SendReplyToReceive** activity and set the **DisplayName** property shown in the following illustration.</span></span>

             <span data-ttu-id="74e44-196">![SendReply アクティビティのプロパティを設定](./media/creating-a-long-running-workflow-service/send-reply-activity-property.png "SendReply アクティビティのプロパティを設定します。")</span><span class="sxs-lookup"><span data-stu-id="74e44-196">![Setting the SendReply activity properties](./media/creating-a-long-running-workflow-service/send-reply-activity-property.png "Set the SendReply activity property.")</span></span>

        4.  <span data-ttu-id="74e44-197">をクリックして、**を定義しています.** のリンクを**SetReplyToAddItem**アクティビティの次の図に示すように構成します。</span><span class="sxs-lookup"><span data-stu-id="74e44-197">Click the **Define ...** link in the **SetReplyToAddItem** activity and configure it as shown in the following illustration.</span></span> <span data-ttu-id="74e44-198">これにより、構成、 **SendReplyToAddItem**で値を返すアクティビティ、`orderResult`変数。</span><span class="sxs-lookup"><span data-stu-id="74e44-198">This configures the **SendReplyToAddItem** activity to return the value in the `orderResult` variable.</span></span>

             <span data-ttu-id="74e44-199">![SendReply アクティビティのデータ バインディングの設定](./media/creating-a-long-running-workflow-service/set-property-for-sendreplytoadditem.gif "SendReplyToAddItem アクティビティのプロパティを設定します。")</span><span class="sxs-lookup"><span data-stu-id="74e44-199">![Setting the data binding for the SendReply activity](./media/creating-a-long-running-workflow-service/set-property-for-sendreplytoadditem.gif "Set property for SendReplyToAddItem activity.")</span></span>

8.  <span data-ttu-id="74e44-200">Web.config ファイルを開き、次の要素を追加、\<動作 > セクションは、ワークフローの永続化を有効にします。</span><span class="sxs-lookup"><span data-stu-id="74e44-200">Open the web.config file and add the following elements in the \<behavior> section to enable workflow persistence.</span></span>

    ```xml
    <sqlWorkflowInstanceStore connectionString="Data Source=your-machine\SQLExpress;Initial Catalog=SQLPersistenceStore;Integrated Security=True;Asynchronous Processing=True" instanceEncodingOption="None" instanceCompletionAction="DeleteAll" instanceLockedExceptionAction="BasicRetry" hostLockRenewalPeriod="00:00:30" runnableInstancesDetectionPeriod="00:00:02" />
              <workflowIdle timeToUnload="0"/>
    ```

    > [!WARNING]
    >  <span data-ttu-id="74e44-201">前のコード スニペットでホストと SQL Server インスタンス名を置換するようにします。</span><span class="sxs-lookup"><span data-stu-id="74e44-201">Make sure to replace your host and SQL server instance name in the previous code snippet.</span></span>

9. <span data-ttu-id="74e44-202">ソリューションをビルドします。</span><span class="sxs-lookup"><span data-stu-id="74e44-202">Build the solution.</span></span>

### <a name="to-create-a-client-application-to-call-the-workflow-service"></a><span data-ttu-id="74e44-203">クライアント アプリケーションを作成してワークフロー サービスを呼び出すには</span><span class="sxs-lookup"><span data-stu-id="74e44-203">To Create a Client Application to Call the Workflow Service</span></span>

1.  <span data-ttu-id="74e44-204">`OrderClient` という新しいコンソール アプリケーション プロジェクトをソリューションに追加します。</span><span class="sxs-lookup"><span data-stu-id="74e44-204">Add a new Console application project called `OrderClient` to the solution.</span></span>

2.  <span data-ttu-id="74e44-205">次のアセンブリへの参照を `OrderClient` プロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="74e44-205">Add references to the following assemblies to the `OrderClient` project</span></span>

    1.  <span data-ttu-id="74e44-206">System.ServiceModel.dll</span><span class="sxs-lookup"><span data-stu-id="74e44-206">System.ServiceModel.dll</span></span>

    2.  <span data-ttu-id="74e44-207">System.ServiceModel.Activities.dll</span><span class="sxs-lookup"><span data-stu-id="74e44-207">System.ServiceModel.Activities.dll</span></span>

3.  <span data-ttu-id="74e44-208">サービス参照をワークフロー サービスに追加し、`OrderService` を名前空間として指定します。</span><span class="sxs-lookup"><span data-stu-id="74e44-208">Add a service reference to the workflow service and specify `OrderService` as the namespace.</span></span>

4.  <span data-ttu-id="74e44-209">クライアント プロジェクトの `Main()` メソッド内に次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="74e44-209">In the `Main()` method of the client project add the following code:</span></span>

    ```
    static void Main(string[] args)
    {
       // Send initial message to start the workflow service
       Console.WriteLine("Sending start message");
       StartOrderClient startProxy = new StartOrderClient();
       string orderId = startProxy.StartOrder("Kim Abercrombie");

       // The workflow service is now waiting for the second message to be sent
       Console.WriteLine("Workflow service is idle...");
       Console.WriteLine("Press [ENTER] to send an add item message to reactivate the workflow service...");
       Console.ReadLine();

       // Send the second message
       Console.WriteLine("Sending add item message");
       AddItemClient addProxy = new AddItemClient();
       AddItem item = new AddItem();
       item.p_itemId = "Zune HD";
       item.p_orderId = orderId;

       string orderResult = addProxy.AddItem(item);
       Console.WriteLine("Service returned: " + orderResult);
    }
    ```

5.  <span data-ttu-id="74e44-210">ソリューションをビルドし、`OrderClient` アプリケーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="74e44-210">Build the solution and run the `OrderClient` application.</span></span> <span data-ttu-id="74e44-211">クライアントに次のテキストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="74e44-211">The client will display the following text:</span></span>

    ```Output
    Sending start messageWorkflow service is idle...Press [ENTER] to send an add item message to reactivate the workflow service...
    ```

6.  <span data-ttu-id="74e44-212">ワークフロー サービスが永続化されたことを確認するに移動して、SQL Server Management Studio を起動、**開始**] メニューの [選択**すべてのプログラム**、 **Microsoft SQL Server 2008**、 **SQL Server Management Studio**します。</span><span class="sxs-lookup"><span data-stu-id="74e44-212">To verify that the workflow service has been persisted, start the SQL Server Management Studio by going to the **Start** menu, Selecting **All Programs**, **Microsoft SQL Server 2008**, **SQL Server Management Studio**.</span></span>

    1.  <span data-ttu-id="74e44-213">左側のウィンドウで次のように展開して、**データベース**、 **SQLPersistenceStore**、**ビュー**を右クリックし、 **System.Activities.DurableInstancing.Instances**選択**上位 1000 行**します。</span><span class="sxs-lookup"><span data-stu-id="74e44-213">In the left hand pane expand, **Databases**, **SQLPersistenceStore**, **Views** and right click **System.Activities.DurableInstancing.Instances** and select **Select Top 1000 Rows**.</span></span> <span data-ttu-id="74e44-214">**結果**ウィンドウが表示されている少なくとも 1 つのインスタンスを参照してくださいを確認します。</span><span class="sxs-lookup"><span data-stu-id="74e44-214">In the **Results** pane verify you see at least one instance listed.</span></span> <span data-ttu-id="74e44-215">実行中に例外が発生した場合は、前の実行のその他のインスタンスがある可能性があります。</span><span class="sxs-lookup"><span data-stu-id="74e44-215">There may be other instances from prior runs if an exception occurred while running.</span></span> <span data-ttu-id="74e44-216">右クリックして既存の行を削除する**System.Activities.DurableInstancing.Instances**を選択して**編集上位 200 行**を**Execute**  ボタン結果ウィンドウで、すべての行を選択して、選択**削除**します。</span><span class="sxs-lookup"><span data-stu-id="74e44-216">You can delete existing rows by right clicking **System.Activities.DurableInstancing.Instances** and selecting **Edit Top 200 rows**, pressing the **Execute** button, selecting all rows in the results pane and selecting **delete**.</span></span>  <span data-ttu-id="74e44-217">データベースに表示されているインスタンスが、アプリケーションで作成されたインスタンスであることを確認するには、クライアントを実行する前に、Instances ビューが空であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="74e44-217">To verify the instance displayed in the database is the instance your application created, verify the instances view is empty prior to running the client.</span></span> <span data-ttu-id="74e44-218">クライアントが実行されると、クエリ ([上位 1000 行を選択]) を再実行し、新しいインスタンスが追加されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="74e44-218">Once the client is running re-run the query (Select Top 1000 Rows) and verify a new instance has been added.</span></span>

7.  <span data-ttu-id="74e44-219">Enter キーを押して、項目の追加メッセージをワークフロー サービスに送信します。</span><span class="sxs-lookup"><span data-stu-id="74e44-219">Press enter to send the add item message to the workflow service.</span></span> <span data-ttu-id="74e44-220">クライアントに次のテキストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="74e44-220">The client will display the following text:</span></span>

    ```Output
    Sending add item messageService returned: Item added to orderPress any key to continue . . .
    ```

## <a name="see-also"></a><span data-ttu-id="74e44-221">関連項目</span><span class="sxs-lookup"><span data-stu-id="74e44-221">See also</span></span>
- [<span data-ttu-id="74e44-222">ワークフロー サービス</span><span class="sxs-lookup"><span data-stu-id="74e44-222">Workflow Services</span></span>](../../../../docs/framework/wcf/feature-details/workflow-services.md)
