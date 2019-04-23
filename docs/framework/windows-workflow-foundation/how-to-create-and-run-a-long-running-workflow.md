---
title: '方法: 長時間にわたって実行されるワークフローを作成して実行する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c0043c89-2192-43c9-986d-3ecec4dd8c9c
ms.openlocfilehash: 7940d1d8869d3b82c1aa19cb038a68b8724345dd
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59320053"
---
# <a name="how-to-create-and-run-a-long-running-workflow"></a><span data-ttu-id="ca4d3-102">方法: 長時間にわたって実行されるワークフローを作成して実行する</span><span class="sxs-lookup"><span data-stu-id="ca4d3-102">How to: Create and Run a Long Running Workflow</span></span>
<span data-ttu-id="ca4d3-103">Windows Workflow Foundation (WF) のサーバーの全体の機能の 1 つは、永続化およびデータベースへのアイドル状態のワークフローをアンロードするランタイムの機能です。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-103">One of the central features of Windows Workflow Foundation (WF) is the runtime’s ability to persist and unload idle workflows to a database.</span></span> <span data-ttu-id="ca4d3-104">手順では、[方法。ワークフローを実行する](how-to-run-a-workflow.md)コンソール アプリケーションを使用したワークフロー ホスティングの基本を説明します。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-104">The steps in [How to: Run a Workflow](how-to-run-a-workflow.md) demonstrated the basics of workflow hosting using a console application.</span></span> <span data-ttu-id="ca4d3-105">ワークフローの開始、ワークフロー ライフサイクル ハンドラー、およびブックマークの再開の例を紹介しました。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-105">Examples were shown of starting workflows, workflow lifecycle handlers, and resuming bookmarks.</span></span> <span data-ttu-id="ca4d3-106">ワークフローの永続化を効果的に説明するためには、複数のワークフロー インスタンスの開始と再開をサポートするより複雑なワークフロー ホストが必要です。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-106">In order to demonstrate workflow persistence effectively, a more complex workflow host is required that supports starting and resuming multiple workflow instances.</span></span> <span data-ttu-id="ca4d3-107">チュートリアルのこの手順では、複数のワークフロー インスタンスの開始と再開およびワークフローの永続化をサポートする Windows フォーム ホスト アプリケーションを作成する方法について説明します。また、この手順は、以降の手順で説明する追跡やバージョン管理などの高度な機能の基礎となります。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-107">This step in the tutorial demonstrates how to create a Windows form host application that supports starting and resuming multiple workflow instances, workflow persistence, and provides a basis for the advanced features such as tracking and versioning that are demonstrated in subsequent tutorial steps.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ca4d3-108">このチュートリアルの手順と後続のステップから次の 3 つすべてのワークフロー型を使用して、[方法。ワークフロー作成](how-to-create-a-workflow.md)です。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-108">This tutorial step and the subsequent steps use all three workflow types from [How to: Create a Workflow](how-to-create-a-workflow.md).</span></span> <span data-ttu-id="ca4d3-109">3 種類すべてを完了していない場合から、手順の完成版をダウンロードできます[Windows Workflow Foundation (WF45) - チュートリアル入門](https://go.microsoft.com/fwlink/?LinkID=248976)します。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-109">If you did not complete all three types you can download a completed version of the steps from [Windows Workflow Foundation (WF45) - Getting Started Tutorial](https://go.microsoft.com/fwlink/?LinkID=248976).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ca4d3-110">完成版をダウンロードまたはチュートリアルのビデオ チュートリアルを表示を参照してください。 [Windows Workflow Foundation (WF45) - チュートリアル入門](https://go.microsoft.com/fwlink/?LinkID=248976)します。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-110">To download a completed version or view a video walkthrough of the tutorial, see [Windows Workflow Foundation (WF45) - Getting Started Tutorial](https://go.microsoft.com/fwlink/?LinkID=248976).</span></span>  
  
## <a name="in-this-topic"></a><span data-ttu-id="ca4d3-111">このトピックの内容</span><span class="sxs-lookup"><span data-stu-id="ca4d3-111">In this topic</span></span>  
  
-   [<span data-ttu-id="ca4d3-112">永続性データベースを作成するには</span><span class="sxs-lookup"><span data-stu-id="ca4d3-112">To create the persistence database</span></span>](how-to-create-and-run-a-long-running-workflow.md#BKMK_CreatePersistenceDatabase)  
  
-   [<span data-ttu-id="ca4d3-113">DurableInstancing アセンブリへの参照を追加するには</span><span class="sxs-lookup"><span data-stu-id="ca4d3-113">To add the reference to the DurableInstancing assemblies</span></span>](how-to-create-and-run-a-long-running-workflow.md#BKMK_AddReference)  
  
-   [<span data-ttu-id="ca4d3-114">ワークフロー ホスト フォームを作成するには</span><span class="sxs-lookup"><span data-stu-id="ca4d3-114">To create the workflow host form</span></span>](how-to-create-and-run-a-long-running-workflow.md#BKMK_CreateForm)  
  
-   [<span data-ttu-id="ca4d3-115">フォームのヘルパー メソッドとプロパティを追加するには</span><span class="sxs-lookup"><span data-stu-id="ca4d3-115">To add the properties and helper methods of the form</span></span>](how-to-create-and-run-a-long-running-workflow.md#BKMK_AddHelperMethods)  
  
-   [<span data-ttu-id="ca4d3-116">インスタンス ストア、ワークフロー ライフ サイクル ハンドラー、および拡張機能を構成するには</span><span class="sxs-lookup"><span data-stu-id="ca4d3-116">To configure the instance store, workflow lifecycle handlers, and extensions</span></span>](how-to-create-and-run-a-long-running-workflow.md#BKMK_ConfigureWorkflowApplication)  
  
-   [<span data-ttu-id="ca4d3-117">開始と再開の複数のワークフローの種類を有効にするには</span><span class="sxs-lookup"><span data-stu-id="ca4d3-117">To enable starting and resuming multiple workflow types</span></span>](how-to-create-and-run-a-long-running-workflow.md#BKMK_WorkflowVersionMap)  
  
-   [<span data-ttu-id="ca4d3-118">新しいワークフローを開始するには</span><span class="sxs-lookup"><span data-stu-id="ca4d3-118">To start a new workflow</span></span>](how-to-create-and-run-a-long-running-workflow.md#BKMK_StartWorkflow)  
  
-   [<span data-ttu-id="ca4d3-119">ワークフローを再開するには</span><span class="sxs-lookup"><span data-stu-id="ca4d3-119">To resume a workflow</span></span>](how-to-create-and-run-a-long-running-workflow.md#BKMK_ResumeWorkflow)  
  
-   [<span data-ttu-id="ca4d3-120">ワークフローを終了するには</span><span class="sxs-lookup"><span data-stu-id="ca4d3-120">To terminate a workflow</span></span>](how-to-create-and-run-a-long-running-workflow.md#BKMK_TerminateWorkflow)  
  
-   [<span data-ttu-id="ca4d3-121">ビルドして、アプリケーションの実行</span><span class="sxs-lookup"><span data-stu-id="ca4d3-121">To build and run the application</span></span>](how-to-create-and-run-a-long-running-workflow.md#BKMK_BuildAndRun)  
  
### <a name="BKMK_CreatePersistenceDatabase"></a> <span data-ttu-id="ca4d3-122">永続性データベースを作成するには</span><span class="sxs-lookup"><span data-stu-id="ca4d3-122">To create the persistence database</span></span>  
  
1. <span data-ttu-id="ca4d3-123">SQL Server Management Studio を開き、たとえば、ローカル サーバーに接続 **. \SQLEXPRESS**します。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-123">Open SQL Server Management Studio and connect to the local server, for example **.\SQLEXPRESS**.</span></span> <span data-ttu-id="ca4d3-124">右クリックし、**データベース**クリックし、ローカル サーバー上のノード**新しいデータベース**します。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-124">Right-click the **Databases** node on the local server, and select **New Database**.</span></span> <span data-ttu-id="ca4d3-125">新しいデータベースの名前**WF45GettingStartedTutorial**他のすべての値を受け入れて、選択**OK**します。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-125">Name the new database **WF45GettingStartedTutorial**, accept all other values, and select **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ca4d3-126">いる**Create Database**データベースを作成する前に、ローカル サーバーに対する権限。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-126">Ensure that you have **Create Database** permission on the local server before creating the database.</span></span>  
  
2. <span data-ttu-id="ca4d3-127">選択**オープン**、**ファイル**から、**ファイル**メニュー。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-127">Choose **Open**, **File** from the **File** menu.</span></span> <span data-ttu-id="ca4d3-128">次のフォルダーに移動します: `C:\Windows\Microsoft.NET\Framework\v4.0.30319\sql\en`。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-128">Browse to the following folder: `C:\Windows\Microsoft.NET\Framework\v4.0.30319\sql\en`</span></span>  
  
     <span data-ttu-id="ca4d3-129">次の 2 つのファイルを選択し、クリックして**オープン**します。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-129">Select the following two files and click **Open**.</span></span>  
  
    -   <span data-ttu-id="ca4d3-130">SqlWorkflowInstanceStoreLogic.sql</span><span class="sxs-lookup"><span data-stu-id="ca4d3-130">SqlWorkflowInstanceStoreLogic.sql</span></span>  
  
    -   <span data-ttu-id="ca4d3-131">SqlWorkflowInstanceStoreSchema.sql</span><span class="sxs-lookup"><span data-stu-id="ca4d3-131">SqlWorkflowInstanceStoreSchema.sql</span></span>  
  
3. <span data-ttu-id="ca4d3-132">選択**SqlWorkflowInstanceStoreSchema.sql**から、**ウィンドウ**メニュー。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-132">Choose **SqlWorkflowInstanceStoreSchema.sql** from the **Window** menu.</span></span> <span data-ttu-id="ca4d3-133">いることを確認**WF45GettingStartedTutorial**でが選択されている、**利用可能なデータベース**ドロップダウンをクリックし、選択**Execute**から、**クエリ**メニュー。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-133">Ensure that **WF45GettingStartedTutorial** is selected in the **Available Databases** drop-down and choose **Execute** from the **Query** menu.</span></span>  
  
4. <span data-ttu-id="ca4d3-134">選択**SqlWorkflowInstanceStoreLogic.sql**から、**ウィンドウ**メニュー。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-134">Choose **SqlWorkflowInstanceStoreLogic.sql** from the **Window** menu.</span></span> <span data-ttu-id="ca4d3-135">いることを確認**WF45GettingStartedTutorial**でが選択されている、**利用可能なデータベース**ドロップダウンをクリックし、選択**Execute**から、**クエリ**メニュー。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-135">Ensure that **WF45GettingStartedTutorial** is selected in the **Available Databases** drop-down and choose **Execute** from the **Query** menu.</span></span>  
  
    > [!WARNING]
    >  <span data-ttu-id="ca4d3-136">前の 2 つの手順を正しい順序で実行することが重要です。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-136">It is important to perform the previous two steps in the correct order.</span></span> <span data-ttu-id="ca4d3-137">クエリが正しい順序で実行されないと、エラーが発生し、永続性データベースは正しく構成されません。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-137">If the queries are executed out of order, errors occur and the persistence database is not configured correctly.</span></span>  
  
### <a name="BKMK_AddReference"></a> <span data-ttu-id="ca4d3-138">DurableInstancing アセンブリへの参照を追加するには</span><span class="sxs-lookup"><span data-stu-id="ca4d3-138">To add the reference to the DurableInstancing assemblies</span></span>  
  
1. <span data-ttu-id="ca4d3-139">右クリック**NumberGuessWorkflowHost**で**ソリューション エクスプ ローラー**選択**参照の追加**します。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-139">Right-click **NumberGuessWorkflowHost** in **Solution Explorer** and select **Add Reference**.</span></span>  
  
2. <span data-ttu-id="ca4d3-140">選択**アセンブリ**から、**参照の追加**リスト、および種類`DurableInstancing`に、**アセンブリの検索**ボックス。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-140">Select **Assemblies** from the **Add Reference** list, and type `DurableInstancing` into the **Search Assemblies** box.</span></span> <span data-ttu-id="ca4d3-141">これにより、アセンブリがフィルター処理され、目的の参照を簡単に選択できます。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-141">This filters the assemblies and makes the desired references easier to select.</span></span>  
  
3. <span data-ttu-id="ca4d3-142">横にあるチェック ボックスをオン**System.Activities.DurableInstancing**と**System.Runtime.DurableInstancing**から、**検索結果**一覧、およびをクリックします **。OK**します。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-142">Check the checkbox beside **System.Activities.DurableInstancing** and **System.Runtime.DurableInstancing** from the **Search Results** list, and click **OK**.</span></span>  
  
### <a name="BKMK_CreateForm"></a> <span data-ttu-id="ca4d3-143">ワークフロー ホスト フォームを作成するには</span><span class="sxs-lookup"><span data-stu-id="ca4d3-143">To create the workflow host form</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ca4d3-144">この手順では、フォームを手動で追加して構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-144">The steps in this procedure describe how to add and configure the form manually.</span></span> <span data-ttu-id="ca4d3-145">必要に応じて、チュートリアルのソリューション ファイルをダウンロードし、完成したフォームをプロジェクトに追加できます。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-145">If desired, you can download the solution files for the tutorial and add the completed form to the project.</span></span> <span data-ttu-id="ca4d3-146">チュートリアル ファイルをダウンロードするを参照してください。 [Windows Workflow Foundation (WF45) - チュートリアル入門](https://go.microsoft.com/fwlink/?LinkID=248976)します。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-146">To download the tutorial files, see [Windows Workflow Foundation (WF45) - Getting Started Tutorial](https://go.microsoft.com/fwlink/?LinkID=248976).</span></span> <span data-ttu-id="ca4d3-147">右クリックし、ファイルがダウンロードされると、 **NumberGuessWorkflowHost**選択**参照の追加**します。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-147">Once the files are downloaded, right-click **NumberGuessWorkflowHost** and choose **Add Reference**.</span></span> <span data-ttu-id="ca4d3-148">参照を追加**System.Windows.Forms**と**System.Drawing**します。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-148">Add a reference to **System.Windows.Forms** and **System.Drawing**.</span></span> <span data-ttu-id="ca4d3-149">新しいフォームを追加する場合、これらの参照が自動的に追加されます、**追加**、**新しい項目の** メニューがフォームをインポートするときに手動で追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-149">These references are added automatically if you add a new form from the **Add**, **New Item** menu, but must be added manually when importing a form.</span></span> <span data-ttu-id="ca4d3-150">右クリックし、参照が追加されると、 **NumberGuessWorkflowHost**で**ソリューション エクスプ ローラー**選択**追加**、**既存項目の**します。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-150">Once the references are added, right-click **NumberGuessWorkflowHost** in **Solution Explorer** and choose **Add**, **Existing Item**.</span></span> <span data-ttu-id="ca4d3-151">参照、`Form`選択、プロジェクト ファイル内のフォルダー **WorkflowHostForm.cs** (または**WorkflowHostForm.vb**)、をクリック**追加**します。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-151">Browse to the `Form` folder in the project files, select **WorkflowHostForm.cs** (or **WorkflowHostForm.vb**), and click **Add**.</span></span> <span data-ttu-id="ca4d3-152">フォームをインポートするかどうかは、次のセクションまでスキップできます[フォームのヘルパー メソッドとプロパティを追加する](how-to-create-and-run-a-long-running-workflow.md#BKMK_AddHelperMethods)します。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-152">If you choose to import the form, then you can skip down to the next section, [To add the properties and helper methods of the form](how-to-create-and-run-a-long-running-workflow.md#BKMK_AddHelperMethods).</span></span>  
  
1. <span data-ttu-id="ca4d3-153">右クリック**NumberGuessWorkflowHost**で**ソリューション エクスプ ローラー**選択**追加**、**新しい項目の**します。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-153">Right-click **NumberGuessWorkflowHost** in **Solution Explorer** and choose **Add**, **New Item**.</span></span>  
  
2. <span data-ttu-id="ca4d3-154">**インストール済み**テンプレート一覧から選択**Windows フォーム**、型`WorkflowHostForm`で、**名前**ボックスし、をクリックして**追加**します。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-154">In the **Installed** templates list, choose **Windows Form**, type `WorkflowHostForm` in the **Name** box, and click **Add**.</span></span>  
  
3. <span data-ttu-id="ca4d3-155">フォームの次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-155">Configure the following properties on the form.</span></span>  
  
    |<span data-ttu-id="ca4d3-156">プロパティ</span><span class="sxs-lookup"><span data-stu-id="ca4d3-156">Property</span></span>|<span data-ttu-id="ca4d3-157">[値]</span><span class="sxs-lookup"><span data-stu-id="ca4d3-157">Value</span></span>|  
    |--------------|-----------|  
    |<span data-ttu-id="ca4d3-158">FormBorderStyle</span><span class="sxs-lookup"><span data-stu-id="ca4d3-158">FormBorderStyle</span></span>|<span data-ttu-id="ca4d3-159">FixedSingle</span><span class="sxs-lookup"><span data-stu-id="ca4d3-159">FixedSingle</span></span>|  
    |<span data-ttu-id="ca4d3-160">MaximizeBox</span><span class="sxs-lookup"><span data-stu-id="ca4d3-160">MaximizeBox</span></span>|<span data-ttu-id="ca4d3-161">False</span><span class="sxs-lookup"><span data-stu-id="ca4d3-161">False</span></span>|  
    |<span data-ttu-id="ca4d3-162">サイズ</span><span class="sxs-lookup"><span data-stu-id="ca4d3-162">Size</span></span>|<span data-ttu-id="ca4d3-163">400, 420</span><span class="sxs-lookup"><span data-stu-id="ca4d3-163">400, 420</span></span>|  
  
4. <span data-ttu-id="ca4d3-164">次のコントロールを指定された順序でフォームに追加し、指示に従ってプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-164">Add the following controls to the form in the order specified and configure the properties as directed.</span></span>  
  
    |<span data-ttu-id="ca4d3-165">コントロール</span><span class="sxs-lookup"><span data-stu-id="ca4d3-165">Control</span></span>|<span data-ttu-id="ca4d3-166">プロパティ:[値]</span><span class="sxs-lookup"><span data-stu-id="ca4d3-166">Property: Value</span></span>|  
    |-------------|---------------------|  
    |<span data-ttu-id="ca4d3-167">**Button**</span><span class="sxs-lookup"><span data-stu-id="ca4d3-167">**Button**</span></span>|<span data-ttu-id="ca4d3-168">名前:NewGame</span><span class="sxs-lookup"><span data-stu-id="ca4d3-168">Name: NewGame</span></span><br /><br /> <span data-ttu-id="ca4d3-169">場所:13, 13</span><span class="sxs-lookup"><span data-stu-id="ca4d3-169">Location: 13, 13</span></span><br /><br /> <span data-ttu-id="ca4d3-170">サイズ:75, 23</span><span class="sxs-lookup"><span data-stu-id="ca4d3-170">Size: 75, 23</span></span><br /><br /> <span data-ttu-id="ca4d3-171">テキスト:New Game</span><span class="sxs-lookup"><span data-stu-id="ca4d3-171">Text: New Game</span></span>|  
    |<span data-ttu-id="ca4d3-172">**Label**</span><span class="sxs-lookup"><span data-stu-id="ca4d3-172">**Label**</span></span>|<span data-ttu-id="ca4d3-173">場所:94, 18</span><span class="sxs-lookup"><span data-stu-id="ca4d3-173">Location: 94, 18</span></span><br /><br /> <span data-ttu-id="ca4d3-174">テキスト:Guess a number from 1 to</span><span class="sxs-lookup"><span data-stu-id="ca4d3-174">Text: Guess a number from 1 to</span></span>|  
    |<span data-ttu-id="ca4d3-175">**ComboBox**</span><span class="sxs-lookup"><span data-stu-id="ca4d3-175">**ComboBox**</span></span>|<span data-ttu-id="ca4d3-176">名前:NumberRange</span><span class="sxs-lookup"><span data-stu-id="ca4d3-176">Name: NumberRange</span></span><br /><br /> <span data-ttu-id="ca4d3-177">DropDownStyle:DropDownList</span><span class="sxs-lookup"><span data-stu-id="ca4d3-177">DropDownStyle: DropDownList</span></span><br /><br /> <span data-ttu-id="ca4d3-178">項目:10, 100, 1000</span><span class="sxs-lookup"><span data-stu-id="ca4d3-178">Items: 10, 100, 1000</span></span><br /><br /> <span data-ttu-id="ca4d3-179">場所:228, 12</span><span class="sxs-lookup"><span data-stu-id="ca4d3-179">Location: 228, 12</span></span><br /><br /> <span data-ttu-id="ca4d3-180">サイズ:143, 21</span><span class="sxs-lookup"><span data-stu-id="ca4d3-180">Size: 143, 21</span></span>|  
    |<span data-ttu-id="ca4d3-181">**Label**</span><span class="sxs-lookup"><span data-stu-id="ca4d3-181">**Label**</span></span>|<span data-ttu-id="ca4d3-182">場所:13, 43</span><span class="sxs-lookup"><span data-stu-id="ca4d3-182">Location: 13, 43</span></span><br /><br /> <span data-ttu-id="ca4d3-183">テキスト:Workflow type</span><span class="sxs-lookup"><span data-stu-id="ca4d3-183">Text: Workflow type</span></span>|  
    |<span data-ttu-id="ca4d3-184">**ComboBox**</span><span class="sxs-lookup"><span data-stu-id="ca4d3-184">**ComboBox**</span></span>|<span data-ttu-id="ca4d3-185">名前:WorkflowType</span><span class="sxs-lookup"><span data-stu-id="ca4d3-185">Name: WorkflowType</span></span><br /><br /> <span data-ttu-id="ca4d3-186">DropDownStyle:DropDownList</span><span class="sxs-lookup"><span data-stu-id="ca4d3-186">DropDownStyle: DropDownList</span></span><br /><br /> <span data-ttu-id="ca4d3-187">項目:StateMachineNumberGuessWorkflow、FlowchartNumberGuessWorkflow、SequentialNumberGuessWorkflow</span><span class="sxs-lookup"><span data-stu-id="ca4d3-187">Items: StateMachineNumberGuessWorkflow, FlowchartNumberGuessWorkflow, SequentialNumberGuessWorkflow</span></span><br /><br /> <span data-ttu-id="ca4d3-188">場所:94, 40</span><span class="sxs-lookup"><span data-stu-id="ca4d3-188">Location: 94, 40</span></span><br /><br /> <span data-ttu-id="ca4d3-189">サイズ:277, 21</span><span class="sxs-lookup"><span data-stu-id="ca4d3-189">Size: 277, 21</span></span>|  
    |<span data-ttu-id="ca4d3-190">**Label**</span><span class="sxs-lookup"><span data-stu-id="ca4d3-190">**Label**</span></span>|<span data-ttu-id="ca4d3-191">名前:WorkflowVersion</span><span class="sxs-lookup"><span data-stu-id="ca4d3-191">Name: WorkflowVersion</span></span><br /><br /> <span data-ttu-id="ca4d3-192">場所:13, 362</span><span class="sxs-lookup"><span data-stu-id="ca4d3-192">Location: 13, 362</span></span><br /><br /> <span data-ttu-id="ca4d3-193">テキスト:Workflow version</span><span class="sxs-lookup"><span data-stu-id="ca4d3-193">Text: Workflow version</span></span>|  
    |<span data-ttu-id="ca4d3-194">**GroupBox**</span><span class="sxs-lookup"><span data-stu-id="ca4d3-194">**GroupBox**</span></span>|<span data-ttu-id="ca4d3-195">場所:13, 67</span><span class="sxs-lookup"><span data-stu-id="ca4d3-195">Location: 13, 67</span></span><br /><br /> <span data-ttu-id="ca4d3-196">サイズ:358, 287</span><span class="sxs-lookup"><span data-stu-id="ca4d3-196">Size: 358, 287</span></span><br /><br /> <span data-ttu-id="ca4d3-197">テキスト:Game</span><span class="sxs-lookup"><span data-stu-id="ca4d3-197">Text: Game</span></span>|  
  
    > [!NOTE]
    >  <span data-ttu-id="ca4d3-198">次のコントロールを追加するときに、GroupBox に配置します。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-198">When adding the following controls, put them into the GroupBox.</span></span>  
  
    |<span data-ttu-id="ca4d3-199">コントロール</span><span class="sxs-lookup"><span data-stu-id="ca4d3-199">Control</span></span>|<span data-ttu-id="ca4d3-200">プロパティ:[値]</span><span class="sxs-lookup"><span data-stu-id="ca4d3-200">Property: Value</span></span>|  
    |-------------|---------------------|  
    |<span data-ttu-id="ca4d3-201">**Label**</span><span class="sxs-lookup"><span data-stu-id="ca4d3-201">**Label**</span></span>|<span data-ttu-id="ca4d3-202">場所:7, 20</span><span class="sxs-lookup"><span data-stu-id="ca4d3-202">Location: 7, 20</span></span><br /><br /> <span data-ttu-id="ca4d3-203">テキスト:ワークフロー インスタンス ID </span><span class="sxs-lookup"><span data-stu-id="ca4d3-203">Text: Workflow Instance Id</span></span>|  
    |<span data-ttu-id="ca4d3-204">**ComboBox**</span><span class="sxs-lookup"><span data-stu-id="ca4d3-204">**ComboBox**</span></span>|<span data-ttu-id="ca4d3-205">名前:InstanceId</span><span class="sxs-lookup"><span data-stu-id="ca4d3-205">Name: InstanceId</span></span><br /><br /> <span data-ttu-id="ca4d3-206">DropDownStyle:DropDownList</span><span class="sxs-lookup"><span data-stu-id="ca4d3-206">DropDownStyle: DropDownList</span></span><br /><br /> <span data-ttu-id="ca4d3-207">場所:121, 17</span><span class="sxs-lookup"><span data-stu-id="ca4d3-207">Location: 121, 17</span></span><br /><br /> <span data-ttu-id="ca4d3-208">サイズ:227, 21</span><span class="sxs-lookup"><span data-stu-id="ca4d3-208">Size: 227, 21</span></span>|  
    |<span data-ttu-id="ca4d3-209">**Label**</span><span class="sxs-lookup"><span data-stu-id="ca4d3-209">**Label**</span></span>|<span data-ttu-id="ca4d3-210">場所:7, 47</span><span class="sxs-lookup"><span data-stu-id="ca4d3-210">Location: 7, 47</span></span><br /><br /> <span data-ttu-id="ca4d3-211">テキスト:Guess</span><span class="sxs-lookup"><span data-stu-id="ca4d3-211">Text: Guess</span></span>|  
    |<span data-ttu-id="ca4d3-212">**TextBox**</span><span class="sxs-lookup"><span data-stu-id="ca4d3-212">**TextBox**</span></span>|<span data-ttu-id="ca4d3-213">名前:Guess</span><span class="sxs-lookup"><span data-stu-id="ca4d3-213">Name: Guess</span></span><br /><br /> <span data-ttu-id="ca4d3-214">場所:50, 44</span><span class="sxs-lookup"><span data-stu-id="ca4d3-214">Location: 50, 44</span></span><br /><br /> <span data-ttu-id="ca4d3-215">サイズ:65, 20</span><span class="sxs-lookup"><span data-stu-id="ca4d3-215">Size: 65, 20</span></span>|  
    |<span data-ttu-id="ca4d3-216">**Button**</span><span class="sxs-lookup"><span data-stu-id="ca4d3-216">**Button**</span></span>|<span data-ttu-id="ca4d3-217">名前:EnterGuess</span><span class="sxs-lookup"><span data-stu-id="ca4d3-217">Name: EnterGuess</span></span><br /><br /> <span data-ttu-id="ca4d3-218">場所:121, 42</span><span class="sxs-lookup"><span data-stu-id="ca4d3-218">Location: 121, 42</span></span><br /><br /> <span data-ttu-id="ca4d3-219">サイズ:75, 23</span><span class="sxs-lookup"><span data-stu-id="ca4d3-219">Size: 75, 23</span></span><br /><br /> <span data-ttu-id="ca4d3-220">テキスト:Enter Guess</span><span class="sxs-lookup"><span data-stu-id="ca4d3-220">Text: Enter Guess</span></span>|  
    |<span data-ttu-id="ca4d3-221">**Button**</span><span class="sxs-lookup"><span data-stu-id="ca4d3-221">**Button**</span></span>|<span data-ttu-id="ca4d3-222">名前:QuitGame</span><span class="sxs-lookup"><span data-stu-id="ca4d3-222">Name: QuitGame</span></span><br /><br /> <span data-ttu-id="ca4d3-223">場所:274, 42</span><span class="sxs-lookup"><span data-stu-id="ca4d3-223">Location: 274, 42</span></span><br /><br /> <span data-ttu-id="ca4d3-224">サイズ:75, 23</span><span class="sxs-lookup"><span data-stu-id="ca4d3-224">Size: 75, 23</span></span><br /><br /> <span data-ttu-id="ca4d3-225">テキスト:終了</span><span class="sxs-lookup"><span data-stu-id="ca4d3-225">Text: Quit</span></span>|  
    |<span data-ttu-id="ca4d3-226">**TextBox**</span><span class="sxs-lookup"><span data-stu-id="ca4d3-226">**TextBox**</span></span>|<span data-ttu-id="ca4d3-227">名前:WorkflowStatus</span><span class="sxs-lookup"><span data-stu-id="ca4d3-227">Name: WorkflowStatus</span></span><br /><br /> <span data-ttu-id="ca4d3-228">場所:10, 73</span><span class="sxs-lookup"><span data-stu-id="ca4d3-228">Location: 10, 73</span></span><br /><br /> <span data-ttu-id="ca4d3-229">Multiline:True</span><span class="sxs-lookup"><span data-stu-id="ca4d3-229">Multiline: True</span></span><br /><br /> <span data-ttu-id="ca4d3-230">読み取り専用:True</span><span class="sxs-lookup"><span data-stu-id="ca4d3-230">ReadOnly: True</span></span><br /><br /> <span data-ttu-id="ca4d3-231">スクロール バー:Vertical</span><span class="sxs-lookup"><span data-stu-id="ca4d3-231">ScrollBars: Vertical</span></span><br /><br /> <span data-ttu-id="ca4d3-232">サイズ:338, 208</span><span class="sxs-lookup"><span data-stu-id="ca4d3-232">Size: 338, 208</span></span>|  
  
5. <span data-ttu-id="ca4d3-233">設定、 **AcceptButton**プロパティをフォームの**EnterGuess**します。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-233">Set the **AcceptButton** property of the form to **EnterGuess**.</span></span>  
  
 <span data-ttu-id="ca4d3-234">次の例は完成したフォームを示しています。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-234">The following example illustrates the completed form.</span></span>  
  
 <span data-ttu-id="ca4d3-235">![WF45 チュートリアル ワークフロー ホスト フォームを概要](./media/wf45gettingstartedtutorialworkflowhostform.png "WF45GettingStartedTutorialWorkflowHostForm")</span><span class="sxs-lookup"><span data-stu-id="ca4d3-235">![WF45 Getting Started Tutorial Workflow Host Form](./media/wf45gettingstartedtutorialworkflowhostform.png "WF45GettingStartedTutorialWorkflowHostForm")</span></span>  
  
### <a name="BKMK_AddHelperMethods"></a> <span data-ttu-id="ca4d3-236">フォームのヘルパー メソッドとプロパティを追加するには</span><span class="sxs-lookup"><span data-stu-id="ca4d3-236">To add the properties and helper methods of the form</span></span>  
 <span data-ttu-id="ca4d3-237">このセクションの手順では、フォーム クラスに、数値推測ワークフローの実行と再開をサポートするようフォームの UI を構成するプロパティとヘルパー メソッドを追加します。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-237">The steps in this section add properties and helper methods to the form class that configure the UI of the form to support running and resuming number guess workflows.</span></span>  
  
1. <span data-ttu-id="ca4d3-238">右クリックして**WorkflowHostForm**で**ソリューション エクスプ ローラー**選択**コードの表示**します。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-238">Right-click **WorkflowHostForm** in **Solution Explorer** and choose **View Code**.</span></span>  
  
2. <span data-ttu-id="ca4d3-239">次の `using` (または `Imports`) ステートメントを、他の `using` (または `Imports`) ステートメントを含むファイルの先頭に追加します。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-239">Add the following `using` (or `Imports`) statements at the top of the file with the other `using` (or `Imports`) statements.</span></span>  
  
    ```vb  
    Imports System.Windows.Forms  
    Imports System.Activities.DurableInstancing  
    Imports System.Activities  
    Imports System.Data.SqlClient  
    Imports System.IO  
    ```  
  
    ```csharp  
    using System.Windows.Forms;  
    using System.Activities.DurableInstancing;  
    using System.Activities;  
    using System.Data.SqlClient;  
    using System.IO;  
    ```  
  
3. <span data-ttu-id="ca4d3-240">次のメンバー宣言を追加、 **WorkflowHostForm**クラス。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-240">Add the following member declarations to the **WorkflowHostForm** class.</span></span>  
  
    ```vb  
    Const connectionString = "Server=.\SQLEXPRESS;Initial Catalog=WF45GettingStartedTutorial;Integrated Security=SSPI"  
    Dim store As SqlWorkflowInstanceStore  
    Dim WorkflowStarting As Boolean  
    ```  
  
    ```csharp  
    const string connectionString = "Server=.\\SQLEXPRESS;Initial Catalog=WF45GettingStartedTutorial;Integrated Security=SSPI";  
    SqlWorkflowInstanceStore store;  
    bool WorkflowStarting;  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="ca4d3-241">接続文字列が異なる場合は、使用しているデータベースを参照するように `connectionString` を更新してください。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-241">If your connection string is different, update `connectionString` to refer to your database.</span></span>  
  
4. <span data-ttu-id="ca4d3-242">`WorkflowInstanceId` プロパティを `WorkflowFormHost` クラスに追加します。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-242">Add a `WorkflowInstanceId` property to the `WorkflowFormHost` class.</span></span>  
  
    ```vb  
    Public ReadOnly Property WorkflowInstanceId() As Guid  
        Get  
            If InstanceId.SelectedIndex = -1 Then  
                Return Guid.Empty  
            Else  
                Return New Guid(InstanceId.SelectedItem.ToString())  
            End If  
        End Get  
    End Property  
    ```  
  
    ```csharp  
    public Guid WorkflowInstanceId  
    {  
        get  
        {  
            return InstanceId.SelectedIndex == -1 ? Guid.Empty : (Guid)InstanceId.SelectedItem;  
        }  
    }  
    ```  
  
     <span data-ttu-id="ca4d3-243">`InstanceId`コンボ ボックスには、永続化されたワークフロー インスタンスの id の一覧が表示されます、`WorkflowInstanceId`プロパティは、現在選択されているワークフローを返します。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-243">The `InstanceId` combo box displays a list of persisted workflow instance ids, and the `WorkflowInstanceId` property returns the currently selected workflow.</span></span>  
  
5. <span data-ttu-id="ca4d3-244">フォームの `Load` イベントのハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-244">Add a handler for the form `Load` event.</span></span> <span data-ttu-id="ca4d3-245">切り替えて、ハンドラーを追加するに**デザイン ビュー** 、フォームをクリックして、**イベント**の上部にあるアイコン、**プロパティ**ウィンドウ、およびダブルクリック**ロード**.</span><span class="sxs-lookup"><span data-stu-id="ca4d3-245">To add the handler, switch to **Design View** for the form, click the **Events** icon at the top of the **Properties** window, and double-click **Load**.</span></span>  
  
    ```vb  
    Private Sub WorkflowHostForm_Load(sender As Object, e As EventArgs) Handles Me.Load  
  
    End Sub  
    ```  
  
    ```csharp  
    private void WorkflowHostForm_Load(object sender, EventArgs e)  
    {  
  
    }  
    ```  
  
6. <span data-ttu-id="ca4d3-246">`WorkflowHostForm_Load` に次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-246">Add the following code to `WorkflowHostForm_Load`.</span></span>  
  
    ```vb  
    'Initialize the store and configure it so that it can be used for  
    'multiple WorkflowApplication instances.  
    store = New SqlWorkflowInstanceStore(connectionString)  
    WorkflowApplication.CreateDefaultInstanceOwner(store, Nothing, WorkflowIdentityFilter.Any)  
  
    'Set default ComboBox selections.  
    NumberRange.SelectedIndex = 0  
    WorkflowType.SelectedIndex = 0  
  
    ListPersistedWorkflows()  
    ```  
  
    ```csharp  
    // Initialize the store and configure it so that it can be used for  
    // multiple WorkflowApplication instances.  
    store = new SqlWorkflowInstanceStore(connectionString);  
    WorkflowApplication.CreateDefaultInstanceOwner(store, null, WorkflowIdentityFilter.Any);  
  
    // Set default ComboBox selections.  
    NumberRange.SelectedIndex = 0;  
    WorkflowType.SelectedIndex = 0;  
  
    ListPersistedWorkflows();  
    ```  
  
     <span data-ttu-id="ca4d3-247">フォームの読み込み時に、`SqlWorkflowInstanceStore` が構成され、範囲とワークフローの種類のコンボ ボックスが既定値に設定されます。さらに、永続化されたワークフロー インスタンスが `InstanceId` コンボ ボックスに追加されます。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-247">When the form loads, the `SqlWorkflowInstanceStore` is configured, the range and workflow type combo boxes are set to default values, and the persisted workflow instances are added to the `InstanceId` combo box.</span></span>  
  
7. <span data-ttu-id="ca4d3-248">`SelectedIndexChanged` の `InstanceId` ハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-248">Add a `SelectedIndexChanged` handler for `InstanceId`.</span></span> <span data-ttu-id="ca4d3-249">切り替えて、ハンドラーを追加する**デザイン ビュー** 、フォームの選択、`InstanceId`コンボ ボックスで、をクリックして、**イベント**の上部にあるアイコン、**プロパティ**ウィンドウとダブルクリック**SelectedIndexChanged**します。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-249">To add the handler, switch to **Design View** for the form, select the `InstanceId` combo box, click the **Events** icon at the top of the **Properties** window, and double-click **SelectedIndexChanged**.</span></span>  
  
    ```vb  
    Private Sub InstanceId_SelectedIndexChanged(sender As Object, e As EventArgs) Handles InstanceId.SelectedIndexChanged  
  
    End Sub  
    ```  
  
    ```csharp  
    private void InstanceId_SelectedIndexChanged(object sender, EventArgs e)  
    {  
  
    }  
    ```  
  
8. <span data-ttu-id="ca4d3-250">`InstanceId_SelectedIndexChanged` に次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-250">Add the following code to `InstanceId_SelectedIndexChanged`.</span></span> <span data-ttu-id="ca4d3-251">ユーザーがコンボ ボックスを使用してワークフローを選択するたびに、このハンドラーによってステータス ウィンドウが更新されます。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-251">Whenever the user selects a workflow by using the combo box this handler updates the status window.</span></span>  
  
    ```vb  
    If InstanceId.SelectedIndex = -1 Then  
        Return  
    End If  
  
    'Clear the status window.  
    WorkflowStatus.Clear()  
  
    'Get the workflow version and display it.  
    'If the workflow is just starting then this info will not  
    'be available in the persistence store so do not try and retrieve it.  
    If Not WorkflowStarting Then  
        Dim instance As WorkflowApplicationInstance = _  
            WorkflowApplication.GetInstance(WorkflowInstanceId, store)  
  
        WorkflowVersion.Text = _  
            WorkflowVersionMap.GetIdentityDescription(instance.DefinitionIdentity)  
  
        'Unload the instance.  
        instance.Abandon()  
    End If  
    ```  
  
    ```csharp  
    if (InstanceId.SelectedIndex == -1)  
    {  
        return;  
    }  
  
    // Clear the status window.  
    WorkflowStatus.Clear();  
  
    // Get the workflow version and display it.  
    // If the workflow is just starting then this info will not  
    // be available in the persistence store so do not try and retrieve it.  
    if (!WorkflowStarting)  
    {  
        WorkflowApplicationInstance instance =  
            WorkflowApplication.GetInstance(this.WorkflowInstanceId, store);  
  
        WorkflowVersion.Text =  
            WorkflowVersionMap.GetIdentityDescription(instance.DefinitionIdentity);  
  
        // Unload the instance.  
        instance.Abandon();  
    }  
    ```  
  
9. <span data-ttu-id="ca4d3-252">次の `ListPersistedWorkflows` メソッドをフォーム クラスに追加します。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-252">Add the following `ListPersistedWorkflows` method to the form class.</span></span>  
  
    ```vb  
    Private Sub ListPersistedWorkflows()  
        Using localCon As New SqlConnection(connectionString)  
            Dim localCmd As String = _  
                "Select [InstanceId] from [System.Activities.DurableInstancing].[Instances] Order By [CreationTime]"  
  
            Dim cmd As SqlCommand = localCon.CreateCommand()  
            cmd.CommandText = localCmd  
            localCon.Open()  
            Using reader As SqlDataReader = cmd.ExecuteReader(CommandBehavior.CloseConnection)  
  
                While (reader.Read())  
                    'Get the InstanceId of the persisted Workflow.  
                    Dim id As Guid = Guid.Parse(reader(0).ToString())  
                    InstanceId.Items.Add(id)  
                End While  
            End Using  
        End Using  
    End Sub  
    ```  
  
    ```csharp  
    using (SqlConnection localCon = new SqlConnection(connectionString))  
    {  
        string localCmd =  
            "Select [InstanceId] from [System.Activities.DurableInstancing].[Instances] Order By [CreationTime]";  
  
        SqlCommand cmd = localCon.CreateCommand();  
        cmd.CommandText = localCmd;  
        localCon.Open();  
        using (SqlDataReader reader = cmd.ExecuteReader(CommandBehavior.CloseConnection))  
        {  
            while (reader.Read())  
            {  
                // Get the InstanceId of the persisted Workflow  
                Guid id = Guid.Parse(reader[0].ToString());  
                InstanceId.Items.Add(id);  
            }  
        }  
    }  
    ```  
  
     <span data-ttu-id="ca4d3-253">`ListPersistedWorkflows` は、永続化されたワークフロー インスタンスのインスタンス ストアに対してクエリを実行し、`cboInstanceId` コンボ ボックスにインスタンス ID を追加します。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-253">`ListPersistedWorkflows` queries the instance store for persisted workflow instances, and adds the instance ids to the `cboInstanceId` combo box.</span></span>  
  
10. <span data-ttu-id="ca4d3-254">次の `UpdateStatus` メソッドと対応するデリゲートをフォーム クラスに追加します。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-254">Add the following `UpdateStatus` method and corresponding delegate to the form class.</span></span> <span data-ttu-id="ca4d3-255">このメソッドは、現在実行中のワークフローのステータスでフォーム上のステータス ウィンドウを更新します。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-255">This method updates the status window on the form with the status of the currently running workflow.</span></span>  
  
    ```vb  
    Private Delegate Sub UpdateStatusDelegate(msg As String)  
    Public Sub UpdateStatus(msg As String)  
        'We may be on a different thread so we need to  
        'make this call using BeginInvoke.  
        If InvokeRequired Then  
            BeginInvoke(New UpdateStatusDelegate(AddressOf UpdateStatus), msg)  
        Else  
            If Not msg.EndsWith(vbCrLf) Then  
                msg = msg & vbCrLf  
            End If  
  
            WorkflowStatus.AppendText(msg)  
  
            'Ensure that the newly added status is visible.  
            WorkflowStatus.SelectionStart = WorkflowStatus.Text.Length  
            WorkflowStatus.ScrollToCaret()  
        End If  
    End Sub  
    ```  
  
    ```csharp  
    private delegate void UpdateStatusDelegate(string msg);  
    public void UpdateStatus(string msg)  
    {  
        // We may be on a different thread so we need to  
        // make this call using BeginInvoke.  
        if (InvokeRequired)  
        {  
            BeginInvoke(new UpdateStatusDelegate(UpdateStatus), msg);  
        }  
        else  
        {  
            if (!msg.EndsWith("\r\n"))  
            {  
                msg += "\r\n";  
            }  
            WorkflowStatus.AppendText(msg);  
  
            WorkflowStatus.SelectionStart = WorkflowStatus.Text.Length;  
            WorkflowStatus.ScrollToCaret();  
        }  
    }  
    ```  
  
11. <span data-ttu-id="ca4d3-256">次の `GameOver` メソッドと対応するデリゲートをフォーム クラスに追加します。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-256">Add the following `GameOver` method and corresponding delegate to the form class.</span></span> <span data-ttu-id="ca4d3-257">このメソッドが完成したワークフローのインスタンス id を削除することで、フォームの UI を更新するワークフローが完了したらから、 **InstanceId**コンボ ボックス。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-257">When a workflow completes, this method updates the form UI by removing the instance id of the completed workflow from the **InstanceId** combo box.</span></span>  
  
    ```vb  
    Private Delegate Sub GameOverDelegate()  
    Private Sub GameOver()  
        If InvokeRequired Then  
            BeginInvoke(New GameOverDelegate(AddressOf GameOver))  
        Else  
            'Remove this instance from the InstanceId combo box.  
            InstanceId.Items.Remove(InstanceId.SelectedItem)  
            InstanceId.SelectedIndex = -1  
        End If  
    End Sub  
    ```  
  
    ```csharp  
    private delegate void GameOverDelegate();  
    private void GameOver()  
    {  
        if (InvokeRequired)  
        {  
            BeginInvoke(new GameOverDelegate(GameOver));  
        }  
        else  
        {  
            // Remove this instance from the combo box  
            InstanceId.Items.Remove(InstanceId.SelectedItem);  
            InstanceId.SelectedIndex = -1;  
        }  
    }  
    ```  
  
### <a name="BKMK_ConfigureWorkflowApplication"></a> <span data-ttu-id="ca4d3-258">インスタンス ストア、ワークフロー ライフ サイクル ハンドラー、および拡張機能を構成するには</span><span class="sxs-lookup"><span data-stu-id="ca4d3-258">To configure the instance store, workflow lifecycle handlers, and extensions</span></span>  
  
1. <span data-ttu-id="ca4d3-259">フォーム クラスに `ConfigureWorkflowApplication` メソッドを追加します。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-259">Add a `ConfigureWorkflowApplication` method to the form class.</span></span>  
  
    ```vb  
    Private Sub ConfigureWorkflowApplication(wfApp As WorkflowApplication)  
  
    End Sub  
    ```  
  
    ```csharp  
    private void ConfigureWorkflowApplication(WorkflowApplication wfApp)  
    {      
    }  
    ```  
  
     <span data-ttu-id="ca4d3-260">このメソッドは `WorkflowApplication` を構成し、目的の拡張機能を追加して、ワークフロー ライフサイクル イベントのハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-260">This method configures the `WorkflowApplication`, adds the desired extensions, and adds handlers for the workflow lifecycle events.</span></span>  
  
2. <span data-ttu-id="ca4d3-261">`ConfigureWorkflowApplication` で、`SqlWorkflowInstanceStore` の `WorkflowApplication` を指定します。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-261">In `ConfigureWorkflowApplication`, specify the `SqlWorkflowInstanceStore` for the `WorkflowApplication`.</span></span>  
  
    ```vb  
    'Configure the persistence store.  
    wfApp.InstanceStore = store  
    ```  
  
    ```csharp  
    // Configure the persistence store.  
    wfApp.InstanceStore = store;  
    ```  
  
3. <span data-ttu-id="ca4d3-262">次に、`StringWriter` インスタンスを作成して `Extensions` の `WorkflowApplication` コレクションに追加します。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-262">Next, create a `StringWriter` instance and add it to the `Extensions` collection of the `WorkflowApplication`.</span></span> <span data-ttu-id="ca4d3-263">ときに、`StringWriter`すべてキャプチャされます、拡張機能に追加されます`WriteLine`アクティビティの出力。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-263">When a `StringWriter` is added to the extensions it captures all `WriteLine` activity output.</span></span> <span data-ttu-id="ca4d3-264">ワークフローがアイドル状態になると、`WriteLine` の出力を `StringWriter` から抽出してフォームに表示できます。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-264">When the workflow becomes idle, the `WriteLine` output can be extracted from the `StringWriter` and displayed on the form.</span></span>  
  
    ```vb  
    'Add a StringWriter to the extensions. This captures the output  
    'from the WriteLine activities so we can display it in the form.  
    Dim sw As New StringWriter()  
    wfApp.Extensions.Add(sw)  
    ```  
  
    ```csharp  
    // Add a StringWriter to the extensions. This captures the output  
    // from the WriteLine activities so we can display it in the form.  
    StringWriter sw = new StringWriter();  
    wfApp.Extensions.Add(sw);  
    ```  
  
4. <span data-ttu-id="ca4d3-265">`Completed` イベントの次のハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-265">Add the following handler for the `Completed` event.</span></span> <span data-ttu-id="ca4d3-266">ワークフローが正常に完了すると、数値を推測するための順番の数がステータス ウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-266">When a workflow successfully completes, the number of turns taken to guess the number is displayed to the status window.</span></span> <span data-ttu-id="ca4d3-267">ワークフローが終了すると、終了の原因となった例外情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-267">If the workflow terminates, the exception information that caused the termination is displayed.</span></span> <span data-ttu-id="ca4d3-268">ハンドラーの末尾で、`GameOver` メソッドが呼び出され、完了したワークフローがワークフローの一覧から削除されます。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-268">At the end of the handler the `GameOver` method is called, which removes the completed workflow from the workflow list.</span></span>  
  
    ```vb  
    wfApp.Completed = _  
        Sub(e As WorkflowApplicationCompletedEventArgs)  
            If e.CompletionState = ActivityInstanceState.Faulted Then  
                UpdateStatus(String.Format("Workflow Terminated. Exception: {0}" & vbCrLf & "{1}", _  
                    e.TerminationException.GetType().FullName, _  
                    e.TerminationException.Message))  
            ElseIf e.CompletionState = ActivityInstanceState.Canceled Then  
                UpdateStatus("Workflow Canceled.")  
            Else  
                Dim Turns As Integer = Convert.ToInt32(e.Outputs("Turns"))  
                UpdateStatus(String.Format("Congratulations, you guessed the number in {0} turns.", Turns))  
            End If  
            GameOver()  
        End Sub  
    ```  
  
    ```csharp  
    wfApp.Completed = delegate(WorkflowApplicationCompletedEventArgs e)  
    {  
        if (e.CompletionState == ActivityInstanceState.Faulted)  
        {  
            UpdateStatus(string.Format("Workflow Terminated. Exception: {0}\r\n{1}",  
                e.TerminationException.GetType().FullName,  
                e.TerminationException.Message));  
        }  
        else if (e.CompletionState == ActivityInstanceState.Canceled)  
        {  
            UpdateStatus("Workflow Canceled.");  
        }  
        else  
        {  
            int Turns = Convert.ToInt32(e.Outputs["Turns"]);  
            UpdateStatus(string.Format("Congratulations, you guessed the number in {0} turns.", Turns));  
        }  
        GameOver();  
    };  
    ```  
  
5. <span data-ttu-id="ca4d3-269">次の `Aborted` ハンドラーと `OnUnhandledException` ハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-269">Add the following `Aborted` and `OnUnhandledException` handlers.</span></span> <span data-ttu-id="ca4d3-270">`GameOver` メソッドが `Aborted` ハンドラーから呼び出されることはありません。これは、ワークフロー インスタンスが中止された場合、そのインスタンスは終了せず、後で再開することができるためです。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-270">The `GameOver` method is not called from the `Aborted` handler because when a workflow instance is aborted, it does not terminate, and it is possible to resume the instance at a later time.</span></span>  
  
    ```vb  
    wfApp.Aborted = _  
        Sub(e As WorkflowApplicationAbortedEventArgs)  
            UpdateStatus(String.Format("Workflow Aborted. Exception: {0}" & vbCrLf & "{1}", _  
                e.Reason.GetType().FullName, _  
                e.Reason.Message))  
        End Sub  
  
    wfApp.OnUnhandledException = _  
        Function(e As WorkflowApplicationUnhandledExceptionEventArgs)  
            UpdateStatus(String.Format("Unhandled Exception: {0}" & vbCrLf & "{1}", _  
                e.UnhandledException.GetType().FullName, _  
                e.UnhandledException.Message))  
            GameOver()  
            Return UnhandledExceptionAction.Terminate  
        End Function  
    ```  
  
    ```csharp  
    wfApp.Aborted = delegate(WorkflowApplicationAbortedEventArgs e)  
    {  
        UpdateStatus(string.Format("Workflow Aborted. Exception: {0}\r\n{1}",  
                e.Reason.GetType().FullName,  
                e.Reason.Message));  
    };  
  
    wfApp.OnUnhandledException = delegate(WorkflowApplicationUnhandledExceptionEventArgs e)  
    {  
        UpdateStatus(string.Format("Unhandled Exception: {0}\r\n{1}",  
                e.UnhandledException.GetType().FullName,  
                e.UnhandledException.Message));  
        GameOver();  
        return UnhandledExceptionAction.Terminate;  
    };  
    ```  
  
6. <span data-ttu-id="ca4d3-271">次の `PersistableIdle` ハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-271">Add the following `PersistableIdle` handler.</span></span> <span data-ttu-id="ca4d3-272">このハンドラーは、追加された `StringWriter` 拡張機能を取得し、`WriteLine` アクティビティからの出力を抽出して、ステータス ウィンドウに表示します。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-272">This handler retrieves the `StringWriter` extension that was added, extracts the output from the `WriteLine` activities, and displays it in the status window.</span></span>  
  
    ```vb  
    wfApp.PersistableIdle = _  
        Function(e As WorkflowApplicationIdleEventArgs)  
            'Send the current WriteLine outputs to the status window.  
            Dim writers = e.GetInstanceExtensions(Of StringWriter)()  
            For Each writer In writers  
                UpdateStatus(writer.ToString())  
            Next  
            Return PersistableIdleAction.Unload  
        End Function  
    ```  
  
    ```csharp  
    wfApp.PersistableIdle = delegate(WorkflowApplicationIdleEventArgs e)  
    {  
        // Send the current WriteLine outputs to the status window.  
        var writers = e.GetInstanceExtensions<StringWriter>();  
        foreach (var writer in writers)  
        {  
            UpdateStatus(writer.ToString());  
        }  
        return PersistableIdleAction.Unload;  
    };  
    ```  
  
     <span data-ttu-id="ca4d3-273"><xref:System.Activities.PersistableIdleAction> 列挙体には、<xref:System.Activities.PersistableIdleAction.None>、<xref:System.Activities.PersistableIdleAction.Persist>、および <xref:System.Activities.PersistableIdleAction.Unload> の 3 つの値があります。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-273">The <xref:System.Activities.PersistableIdleAction> enumeration has three values: <xref:System.Activities.PersistableIdleAction.None>, <xref:System.Activities.PersistableIdleAction.Persist>, and <xref:System.Activities.PersistableIdleAction.Unload>.</span></span> <span data-ttu-id="ca4d3-274"><xref:System.Activities.PersistableIdleAction.Persist> により、ワークフローは永続化されますが、ワークフローがアンロードされることはありません。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-274"><xref:System.Activities.PersistableIdleAction.Persist> causes the workflow to persist but it does not cause the workflow to unload.</span></span> <span data-ttu-id="ca4d3-275"><xref:System.Activities.PersistableIdleAction.Unload> により、ワーク フローが永続化され、アンロードされます。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-275"><xref:System.Activities.PersistableIdleAction.Unload> causes the workflow to persist and be unloaded.</span></span>  
  
     <span data-ttu-id="ca4d3-276">完成した `ConfigureWorkflowApplication` メソッドは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-276">The following example is the completed `ConfigureWorkflowApplication` method.</span></span>  
  
    ```vb  
    Private Sub ConfigureWorkflowApplication(wfApp As WorkflowApplication)  
        'Configure the persistence store.  
        wfApp.InstanceStore = store  
  
        'Add a StringWriter to the extensions. This captures the output  
        'from the WriteLine activities so we can display it in the form.  
        Dim sw As New StringWriter()  
        wfApp.Extensions.Add(sw)  
  
        wfApp.Completed = _  
            Sub(e As WorkflowApplicationCompletedEventArgs)  
                If e.CompletionState = ActivityInstanceState.Faulted Then  
                    UpdateStatus(String.Format("Workflow Terminated. Exception: {0}" & vbCrLf & "{1}", _  
                        e.TerminationException.GetType().FullName, _  
                        e.TerminationException.Message))  
                ElseIf e.CompletionState = ActivityInstanceState.Canceled Then  
                    UpdateStatus("Workflow Canceled.")  
                Else  
                    Dim Turns As Integer = Convert.ToInt32(e.Outputs("Turns"))  
                    UpdateStatus(String.Format("Congratulations, you guessed the number in {0} turns.", Turns))  
                End If  
                GameOver()  
            End Sub  
  
        wfApp.Aborted = _  
            Sub(e As WorkflowApplicationAbortedEventArgs)  
                UpdateStatus(String.Format("Workflow Aborted. Exception: {0}" & vbCrLf & "{1}", _  
                    e.Reason.GetType().FullName, _  
                    e.Reason.Message))  
            End Sub  
  
        wfApp.OnUnhandledException = _  
            Function(e As WorkflowApplicationUnhandledExceptionEventArgs)  
                UpdateStatus(String.Format("Unhandled Exception: {0}" & vbCrLf & "{1}", _  
                    e.UnhandledException.GetType().FullName, _  
                    e.UnhandledException.Message))  
                GameOver()  
                Return UnhandledExceptionAction.Terminate  
            End Function  
  
        wfApp.PersistableIdle = _  
            Function(e As WorkflowApplicationIdleEventArgs)  
                'Send the current WriteLine outputs to the status window.  
                Dim writers = e.GetInstanceExtensions(Of StringWriter)()  
                For Each writer In writers  
                    UpdateStatus(writer.ToString())  
                Next  
                Return PersistableIdleAction.Unload  
            End Function  
    End Sub  
    ```  
  
    ```csharp  
    private void ConfigureWorkflowApplication(WorkflowApplication wfApp)  
    {  
        // Configure the persistence store.  
        wfApp.InstanceStore = store;  
  
        // Add a StringWriter to the extensions. This captures the output  
        // from the WriteLine activities so we can display it in the form.  
        StringWriter sw = new StringWriter();  
        wfApp.Extensions.Add(sw);  
  
        wfApp.Completed = delegate(WorkflowApplicationCompletedEventArgs e)  
        {  
            if (e.CompletionState == ActivityInstanceState.Faulted)  
            {  
                UpdateStatus(string.Format("Workflow Terminated. Exception: {0}\r\n{1}",  
                    e.TerminationException.GetType().FullName,  
                    e.TerminationException.Message));  
            }  
            else if (e.CompletionState == ActivityInstanceState.Canceled)  
            {  
                UpdateStatus("Workflow Canceled.");  
            }  
            else  
            {  
                int Turns = Convert.ToInt32(e.Outputs["Turns"]);  
                UpdateStatus(string.Format("Congratulations, you guessed the number in {0} turns.", Turns));  
            }  
            GameOver();  
        };  
  
        wfApp.Aborted = delegate(WorkflowApplicationAbortedEventArgs e)  
        {  
            UpdateStatus(string.Format("Workflow Aborted. Exception: {0}\r\n{1}",  
                    e.Reason.GetType().FullName,  
                    e.Reason.Message));  
        };  
  
        wfApp.OnUnhandledException = delegate(WorkflowApplicationUnhandledExceptionEventArgs e)  
        {  
            UpdateStatus(string.Format("Unhandled Exception: {0}\r\n{1}",  
                    e.UnhandledException.GetType().FullName,  
                    e.UnhandledException.Message));  
            GameOver();  
            return UnhandledExceptionAction.Terminate;  
        };  
  
        wfApp.PersistableIdle = delegate(WorkflowApplicationIdleEventArgs e)  
        {  
            // Send the current WriteLine outputs to the status window.  
            var writers = e.GetInstanceExtensions<StringWriter>();  
            foreach (var writer in writers)  
            {  
                UpdateStatus(writer.ToString());  
            }  
            return PersistableIdleAction.Unload;  
        };  
    }  
    ```  
  
### <a name="BKMK_WorkflowVersionMap"></a> <span data-ttu-id="ca4d3-277">開始と再開の複数のワークフローの種類を有効にするには</span><span class="sxs-lookup"><span data-stu-id="ca4d3-277">To enable starting and resuming multiple workflow types</span></span>  
 <span data-ttu-id="ca4d3-278">ワークフロー インスタンスを再開するには、ホストはワークフロー定義を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-278">In order to resume a workflow instance, the host has to provide the workflow definition.</span></span> <span data-ttu-id="ca4d3-279">このチュートリアルには 3 種類のワークフローがあり、以降の手順では、これらの種類の複数のバージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-279">In this tutorial there are three workflow types, and subsequent tutorial steps introduce multiple versions of these types.</span></span> <span data-ttu-id="ca4d3-280">`WorkflowIdentity` を使用すると、ホスト アプリケーションは、識別情報を永続化されたワークフロー インスタンスに関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-280">`WorkflowIdentity` provides a way for a host application to associate identifying information with a persisted workflow instance.</span></span> <span data-ttu-id="ca4d3-281">このセクションの手順では、永続化されたワークフロー インスタンスから対応するワークフロー定義へのワークフロー ID のマッピングに役立つユーティリティ クラスの作成方法を示します。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-281">The steps in this section demonstrate how to create a utility class to assist with mapping the workflow identity from a persisted workflow instance to the corresponding workflow definition.</span></span> <span data-ttu-id="ca4d3-282">詳細については`WorkflowIdentity`とバージョン管理を参照してください[を使用して WorkflowIdentity と Versioning](using-workflowidentity-and-versioning.md)します。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-282">For more information about `WorkflowIdentity` and versioning, see [Using WorkflowIdentity and Versioning](using-workflowidentity-and-versioning.md).</span></span>  
  
1. <span data-ttu-id="ca4d3-283">右クリックして**NumberGuessWorkflowHost**で**ソリューション エクスプ ローラー**選択**追加**、**クラス**します。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-283">Right-click **NumberGuessWorkflowHost** in **Solution Explorer** and choose **Add**, **Class**.</span></span> <span data-ttu-id="ca4d3-284">型`WorkflowVersionMap`に、**名前**ボックスし、をクリックして**追加**します。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-284">Type `WorkflowVersionMap` into the **Name** box and click **Add**.</span></span>  
  
2. <span data-ttu-id="ca4d3-285">次の `using` または `Imports` ステートメントを、他の `using` または `Imports` ステートメントを含むファイルの先頭に追加します。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-285">Add the following `using` or `Imports` statements at the top of the file with the other `using` or `Imports` statements.</span></span>  
  
    ```vb  
    Imports NumberGuessWorkflowActivities  
    Imports System.Activities  
    ```  
  
    ```csharp  
    using NumberGuessWorkflowActivities;  
    using System.Activities;  
    ```  
  
3. <span data-ttu-id="ca4d3-286">`WorkflowVersionMap` クラス宣言を次の宣言に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-286">Replace the `WorkflowVersionMap` class declaration with the following declaration.</span></span>  
  
    ```vb  
    Public Module WorkflowVersionMap  
        Dim map As Dictionary(Of WorkflowIdentity, Activity)  
  
        'Current version identities.  
        Public StateMachineNumberGuessIdentity As WorkflowIdentity  
        Public FlowchartNumberGuessIdentity As WorkflowIdentity  
        Public SequentialNumberGuessIdentity As WorkflowIdentity  
  
        Sub New()  
            map = New Dictionary(Of WorkflowIdentity, Activity)  
  
            'Add the current workflow version identities.  
            StateMachineNumberGuessIdentity = New WorkflowIdentity With  
            {  
                .Name = "StateMachineNumberGuessWorkflow",  
                .Version = New Version(1, 0, 0, 0)  
            }  
  
            FlowchartNumberGuessIdentity = New WorkflowIdentity With  
            {  
                .Name = "FlowchartNumberGuessWorkflow",  
                .Version = New Version(1, 0, 0, 0)  
            }  
  
            SequentialNumberGuessIdentity = New WorkflowIdentity With  
            {  
                .Name = "SequentialNumberGuessWorkflow",  
                .Version = New Version(1, 0, 0, 0)  
            }  
  
            map.Add(StateMachineNumberGuessIdentity, New StateMachineNumberGuessWorkflow())  
            map.Add(FlowchartNumberGuessIdentity, New FlowchartNumberGuessWorkflow())  
            map.Add(SequentialNumberGuessIdentity, New SequentialNumberGuessWorkflow())  
        End Sub  
  
        Public Function GetWorkflowDefinition(identity As WorkflowIdentity) As Activity  
            Return map(identity)  
        End Function  
  
        Public Function GetIdentityDescription(identity As WorkflowIdentity) As String  
            Return identity.ToString()  
        End Function  
    End Module  
    ```  
  
    ```csharp  
    public static class WorkflowVersionMap  
    {  
        static Dictionary<WorkflowIdentity, Activity> map;  
  
        // Current version identities.  
        static public WorkflowIdentity StateMachineNumberGuessIdentity;  
        static public WorkflowIdentity FlowchartNumberGuessIdentity;  
        static public WorkflowIdentity SequentialNumberGuessIdentity;  
  
        static WorkflowVersionMap()  
        {  
            map = new Dictionary<WorkflowIdentity, Activity>();  
  
            // Add the current workflow version identities.  
            StateMachineNumberGuessIdentity = new WorkflowIdentity  
            {  
                Name = "StateMachineNumberGuessWorkflow",  
                Version = new Version(1, 0, 0, 0)  
            };  
  
            FlowchartNumberGuessIdentity = new WorkflowIdentity  
            {  
                Name = "FlowchartNumberGuessWorkflow",  
                Version = new Version(1, 0, 0, 0)  
            };  
  
            SequentialNumberGuessIdentity = new WorkflowIdentity  
            {  
                Name = "SequentialNumberGuessWorkflow",  
                Version = new Version(1, 0, 0, 0)  
            };  
  
            map.Add(StateMachineNumberGuessIdentity, new StateMachineNumberGuessWorkflow());  
            map.Add(FlowchartNumberGuessIdentity, new FlowchartNumberGuessWorkflow());  
            map.Add(SequentialNumberGuessIdentity, new SequentialNumberGuessWorkflow());  
        }  
  
        public static Activity GetWorkflowDefinition(WorkflowIdentity identity)  
        {  
            return map[identity];  
        }  
  
        public static string GetIdentityDescription(WorkflowIdentity identity)  
        {          
            return identity.ToString();  
       }  
    }  
    ```  
  
     <span data-ttu-id="ca4d3-287">`WorkflowVersionMap` は、このチュートリアルの 3 つのワークフロー定義にマップされる 3 つのワークフロー ID を格納しており、以降のセクションでワークフローが開始および再開されるときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-287">`WorkflowVersionMap` contains three workflow identities that map to the three workflow definitions from this tutorial and is used in the following sections when workflows are started and resumed.</span></span>  
  
### <a name="BKMK_StartWorkflow"></a> <span data-ttu-id="ca4d3-288">新しいワークフローを開始するには</span><span class="sxs-lookup"><span data-stu-id="ca4d3-288">To start a new workflow</span></span>  
  
1. <span data-ttu-id="ca4d3-289">`Click` の `NewGame` ハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-289">Add a `Click` handler for `NewGame`.</span></span> <span data-ttu-id="ca4d3-290">ハンドラーを追加するに切り替える**デザイン ビュー**フォーム、およびダブルクリック`NewGame`します。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-290">To add the handler, switch to **Design View** for the form, and double-click `NewGame`.</span></span> <span data-ttu-id="ca4d3-291">`NewGame_Click` ハンドラーが追加され、ビューがフォームのコード ビューに切り替わります。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-291">A `NewGame_Click` handler is added and the view switches to code view for the form.</span></span> <span data-ttu-id="ca4d3-292">ユーザーがこのボタンをクリックするたびに、新しいワークフローが開始されます。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-292">Whenever the user clicks this button a new workflow is started.</span></span>  
  
    ```vb  
    Private Sub NewGame_Click(sender As Object, e As EventArgs) Handles NewGame.Click  
  
    End Sub  
    ```  
  
    ```csharp  
    private void NewGame_Click(object sender, EventArgs e)  
    {  
  
    }  
    ```  
  
2. <span data-ttu-id="ca4d3-293">Click ハンドラーに次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-293">Add the following code to the click handler.</span></span> <span data-ttu-id="ca4d3-294">このコードにより、引数名によってキー指定された、ワークフローの入力引数のディクショナリが作成されます。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-294">This code creates a dictionary of input arguments for the workflow, keyed by argument name.</span></span> <span data-ttu-id="ca4d3-295">このディクショナリには、範囲のコンボ ボックスから取得したランダムに生成された数値の範囲を含む 1 つのエントリがあります。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-295">This dictionary has one entry that contains the range of the randomly generated number retrieved from the range combo box.</span></span>  
  
    ```vb  
    Dim inputs As New Dictionary(Of String, Object)()  
    inputs.Add("MaxNumber", Convert.ToInt32(NumberRange.SelectedItem))  
    ```  
  
    ```csharp  
    var inputs = new Dictionary<string, object>();  
    inputs.Add("MaxNumber", Convert.ToInt32(NumberRange.SelectedItem));  
    ```  
  
3. <span data-ttu-id="ca4d3-296">次に、ワークフローを開始する次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-296">Next, add the following code that starts the workflow.</span></span> <span data-ttu-id="ca4d3-297">選択されたワークフローの種類に対応する `WorkflowIdentity` とワークフロー定義が `WorkflowVersionMap` ヘルパー クラスを使用して取得されます。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-297">The `WorkflowIdentity` and workflow definition corresponding to the type of workflow selected are retrieved using the `WorkflowVersionMap` helper class.</span></span> <span data-ttu-id="ca4d3-298">さらに、新しい `WorkflowApplication` インスタンスを作成するには、ワークフロー定義、`WorkflowIdentity`、および入力引数のディクショナリを使用します。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-298">Next, a new `WorkflowApplication` instance is created using the workflow definition, `WorkflowIdentity`, and dictionary of input arguments.</span></span>  
  
    ```vb  
    Dim identity As WorkflowIdentity = Nothing  
    Select Case WorkflowType.SelectedItem.ToString()  
        Case "SequentialNumberGuessWorkflow"  
            identity = WorkflowVersionMap.SequentialNumberGuessIdentity  
  
        Case "StateMachineNumberGuessWorkflow"  
            identity = WorkflowVersionMap.StateMachineNumberGuessIdentity  
  
        Case "FlowchartNumberGuessWorkflow"  
            identity = WorkflowVersionMap.FlowchartNumberGuessIdentity  
    End Select  
  
    Dim wf As Activity = WorkflowVersionMap.GetWorkflowDefinition(identity)  
  
    Dim wfApp = New WorkflowApplication(wf, inputs, identity)  
    ```  
  
    ```csharp  
    WorkflowIdentity identity = null;  
    switch (WorkflowType.SelectedItem.ToString())  
    {  
        case "SequentialNumberGuessWorkflow":  
            identity = WorkflowVersionMap.SequentialNumberGuessIdentity;  
            break;  
  
        case "StateMachineNumberGuessWorkflow":  
            identity = WorkflowVersionMap.StateMachineNumberGuessIdentity;  
            break;  
  
        case "FlowchartNumberGuessWorkflow":  
            identity = WorkflowVersionMap.FlowchartNumberGuessIdentity;  
            break;  
    };  
  
    Activity wf = WorkflowVersionMap.GetWorkflowDefinition(identity);  
  
    WorkflowApplication wfApp = new WorkflowApplication(wf, inputs, identity);  
    ```  
  
4. <span data-ttu-id="ca4d3-299">次に、ワークフローの一覧にワークフローを追加し、フォーム上にワークフローのバージョン情報を表示する次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-299">Next, add the following code which adds the workflow to the workflow list and displays the workflow's version information on the form.</span></span>  
  
    ```vb  
    'Add the workflow to the list and display the version information.  
    WorkflowStarting = True  
    InstanceId.SelectedIndex = InstanceId.Items.Add(wfApp.Id)  
    WorkflowVersion.Text = identity.ToString()  
    WorkflowStarting = False  
    ```  
  
    ```csharp  
    // Add the workflow to the list and display the version information.  
    WorkflowStarting = true;  
    InstanceId.SelectedIndex = InstanceId.Items.Add(wfApp.Id);  
    WorkflowVersion.Text = identity.ToString();  
    WorkflowStarting = false;  
    ```  
  
5. <span data-ttu-id="ca4d3-300">`ConfigureWorkflowApplication` を呼び出して、この `WorkflowApplication` インスタンスのインスタンス ストア、拡張機能、およびワークフロー ライフサイクル ハンドラーを構成します。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-300">Call `ConfigureWorkflowApplication` to configure the instance store, extensions, and workflow lifecycle handlers for this `WorkflowApplication` instance.</span></span>  
  
    ```vb  
    'Configure the instance store, extensions, and   
    'workflow lifecycle handlers.  
    ConfigureWorkflowApplication(wfApp)  
    ```  
  
    ```csharp  
    // Configure the instance store, extensions, and   
    // workflow lifecycle handlers.  
    ConfigureWorkflowApplication(wfApp);  
    ```  
  
6. <span data-ttu-id="ca4d3-301">最後に、`Run` を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-301">Finally, call `Run`.</span></span>  
  
    ```vb  
    'Start the workflow.  
    wfApp.Run()  
    ```  
  
    ```  
    // Start the workflow.  
    wfApp.Run();  
    ```  
  
     <span data-ttu-id="ca4d3-302">完成した `NewGame_Click` ハンドラーは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-302">The following example is the completed `NewGame_Click` handler.</span></span>  
  
    ```vb  
    Private Sub NewGame_Click(sender As Object, e As EventArgs) Handles NewGame.Click  
        'Start a new workflow.  
        Dim inputs As New Dictionary(Of String, Object)()  
        inputs.Add("MaxNumber", Convert.ToInt32(NumberRange.SelectedItem))  
  
        Dim identity As WorkflowIdentity = Nothing  
        Select Case WorkflowType.SelectedItem.ToString()  
            Case "SequentialNumberGuessWorkflow"  
                identity = WorkflowVersionMap.SequentialNumberGuessIdentity  
  
            Case "StateMachineNumberGuessWorkflow"  
                identity = WorkflowVersionMap.StateMachineNumberGuessIdentity  
  
            Case "FlowchartNumberGuessWorkflow"  
                identity = WorkflowVersionMap.FlowchartNumberGuessIdentity  
        End Select  
  
        Dim wf As Activity = WorkflowVersionMap.GetWorkflowDefinition(identity)  
  
        Dim wfApp = New WorkflowApplication(wf, inputs, identity)  
  
        'Add the workflow to the list and display the version information.  
        WorkflowStarting = True  
        InstanceId.SelectedIndex = InstanceId.Items.Add(wfApp.Id)  
        WorkflowVersion.Text = identity.ToString()  
        WorkflowStarting = False  
  
        'Configure the instance store, extensions, and   
        'workflow lifecycle handlers.  
        ConfigureWorkflowApplication(wfApp)  
  
        'Start the workflow.  
        wfApp.Run()  
    End Sub  
    ```  
  
    ```csharp  
    private void NewGame_Click(object sender, EventArgs e)  
    {  
        var inputs = new Dictionary<string, object>();  
        inputs.Add("MaxNumber", Convert.ToInt32(NumberRange.SelectedItem));  
  
        WorkflowIdentity identity = null;  
        switch (WorkflowType.SelectedItem.ToString())  
        {  
            case "SequentialNumberGuessWorkflow":  
                identity = WorkflowVersionMap.SequentialNumberGuessIdentity;  
                break;  
  
            case "StateMachineNumberGuessWorkflow":  
                identity = WorkflowVersionMap.StateMachineNumberGuessIdentity;  
                break;  
  
            case "FlowchartNumberGuessWorkflow":  
                identity = WorkflowVersionMap.FlowchartNumberGuessIdentity;  
                break;  
        };  
  
        Activity wf = WorkflowVersionMap.GetWorkflowDefinition(identity);  
  
        WorkflowApplication wfApp = new WorkflowApplication(wf, inputs, identity);  
  
        // Add the workflow to the list and display the version information.  
        WorkflowStarting = true;  
        InstanceId.SelectedIndex = InstanceId.Items.Add(wfApp.Id);  
        WorkflowVersion.Text = identity.ToString();  
        WorkflowStarting = false;  
  
        // Configure the instance store, extensions, and   
        // workflow lifecycle handlers.  
        ConfigureWorkflowApplication(wfApp);  
  
        // Start the workflow.  
        wfApp.Run();  
    }  
    ```  
  
### <a name="BKMK_ResumeWorkflow"></a> <span data-ttu-id="ca4d3-303">ワークフローを再開するには</span><span class="sxs-lookup"><span data-stu-id="ca4d3-303">To resume a workflow</span></span>  
  
1. <span data-ttu-id="ca4d3-304">`Click` の `EnterGuess` ハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-304">Add a `Click` handler for `EnterGuess`.</span></span> <span data-ttu-id="ca4d3-305">ハンドラーを追加するに切り替える**デザイン ビュー**フォーム、およびダブルクリック`EnterGuess`します。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-305">To add the handler, switch to **Design View** for the form, and double-click `EnterGuess`.</span></span> <span data-ttu-id="ca4d3-306">ユーザーがこのボタンをクリックするたびに、ワークフローが再開されます。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-306">Whenever the user clicks this button a workflow is resumed.</span></span>  
  
    ```vb  
    Private Sub EnterGuess_Click(sender As Object, e As EventArgs) Handles EnterGuess.Click  
  
    End Sub  
    ```  
  
    ```csharp  
    private void EnterGuess_Click(object sender, EventArgs e)  
    {  
  
    }  
    ```  
  
2. <span data-ttu-id="ca4d3-307">ワークフローがワークフローの一覧で選択され、ユーザーの推定値が有効であることを確認するために、次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-307">Add the following code to ensure that a workflow is selected in the workflow list, and that the user's guess is valid.</span></span>  
  
    ```vb  
    If WorkflowInstanceId = Guid.Empty Then  
        MessageBox.Show("Please select a workflow.")  
        Return  
    End If  
  
    Dim userGuess As Integer  
    If Not Int32.TryParse(Guess.Text, userGuess) Then  
        MessageBox.Show("Please enter an integer.")  
        Guess.SelectAll()  
        Guess.Focus()  
        Return  
    End If  
    ```  
  
    ```csharp  
    if (WorkflowInstanceId == Guid.Empty)  
    {  
        MessageBox.Show("Please select a workflow.");  
        return;  
    }  
  
    int guess;  
    if (!Int32.TryParse(Guess.Text, out guess))  
    {  
        MessageBox.Show("Please enter an integer.");  
        Guess.SelectAll();  
        Guess.Focus();  
        return;  
    }  
    ```  
  
3. <span data-ttu-id="ca4d3-308">次に、永続化されたワークフロー インスタンスの `WorkflowApplicationInstance` を取得します。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-308">Next, retrieve the `WorkflowApplicationInstance` of the persisted workflow instance.</span></span> <span data-ttu-id="ca4d3-309">`WorkflowApplicationInstance` は、ワークフロー定義にまだ関連付けられていない永続化されたワークフロー インスタンスを表します。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-309">A `WorkflowApplicationInstance` represents a persisted workflow instance that has not yet been associated with a workflow definition.</span></span> <span data-ttu-id="ca4d3-310">`DefinitionIdentity` の `WorkflowApplicationInstance` には、永続化されたワークフロー インスタンスの `WorkflowIdentity` が含まれます。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-310">The `DefinitionIdentity` of the `WorkflowApplicationInstance` contains the `WorkflowIdentity` of the persisted workflow instance.</span></span> <span data-ttu-id="ca4d3-311">このチュートリアルでは、`WorkflowVersionMap` を適切なワークフロー定義にマップするために、`WorkflowIdentity` ユーティリティ クラスが使用されます。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-311">In this tutorial, the `WorkflowVersionMap` utility class is used to map the `WorkflowIdentity` to the correct workflow definition.</span></span> <span data-ttu-id="ca4d3-312">ワークフロー定義が取得されると、`WorkflowApplication` が、適切なワークフロー定義を使用して作成されます。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-312">Once the workflow definition is retrieved, a `WorkflowApplication` is created, using the correct workflow definition.</span></span>  
  
    ```vb  
    Dim instance As WorkflowApplicationInstance = _  
        WorkflowApplication.GetInstance(WorkflowInstanceId, store)  
  
    'Use the persisted WorkflowIdentity to retrieve the correct workflow  
    'definition from the dictionary.  
    Dim wf As Activity = _  
        WorkflowVersionMap.GetWorkflowDefinition(instance.DefinitionIdentity)  
  
    'Associate the WorkflowApplication with the correct definition  
    Dim wfApp As WorkflowApplication = _  
        New WorkflowApplication(wf, instance.DefinitionIdentity)  
    ```  
  
    ```csharp  
    WorkflowApplicationInstance instance =  
        WorkflowApplication.GetInstance(WorkflowInstanceId, store);  
  
    // Use the persisted WorkflowIdentity to retrieve the correct workflow  
    // definition from the dictionary.  
    Activity wf =  
        WorkflowVersionMap.GetWorkflowDefinition(instance.DefinitionIdentity);  
  
    // Associate the WorkflowApplication with the correct definition  
    WorkflowApplication wfApp =  
        new WorkflowApplication(wf, instance.DefinitionIdentity);  
    ```  
  
4. <span data-ttu-id="ca4d3-313">`WorkflowApplication` が作成されたら、`ConfigureWorkflowApplication` を呼び出してインスタンス ストア、ワークフロー ライフサイクル ハンドラー、および拡張機能を構成します。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-313">Once the `WorkflowApplication` is created, configure the instance store, workflow lifecycle handlers, and extensions by calling `ConfigureWorkflowApplication`.</span></span> <span data-ttu-id="ca4d3-314">これらの手順は、新しい `WorkflowApplication` が作成されるたびに行う必要があります。また、ワークフロー インスタンスが `WorkflowApplication` に読み込まれる前に行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-314">These steps must be done every time a new `WorkflowApplication` is created, and they must be done before the workflow instance is loaded into the `WorkflowApplication`.</span></span> <span data-ttu-id="ca4d3-315">ワークフローは、読み込まれた後、ユーザーの推定値を使用して再開されます。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-315">After the workflow is loaded, it is resumed with the user's guess.</span></span>  
  
    ```vb  
    'Configure the extensions and lifecycle handlers.  
    'Do this before the instance is loaded. Once the instance is  
    'loaded it is too late to add extensions.  
    ConfigureWorkflowApplication(wfApp)  
  
    'Load the workflow.  
    wfApp.Load(instance)  
  
    'Resume the workflow.  
    wfApp.ResumeBookmark("EnterGuess", userGuess)  
    ```  
  
    ```csharp  
    // Configure the extensions and lifecycle handlers.  
    // Do this before the instance is loaded. Once the instance is  
    // loaded it is too late to add extensions.  
    ConfigureWorkflowApplication(wfApp);  
  
    // Load the workflow.  
    wfApp.Load(instance);  
  
    // Resume the workflow.  
    wfApp.ResumeBookmark("EnterGuess", guess);  
    ```  
  
5. <span data-ttu-id="ca4d3-316">最後に、Guess テキスト ボックスをクリアして、別の推定値を受け取るようにフォームを準備します。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-316">Finally, clear the guess textbox and prepare the form to accept another guess.</span></span>  
  
    ```vb  
    'Clear the Guess textbox.  
    Guess.Clear()  
    Guess.Focus()  
    ```  
  
    ```csharp  
    // Clear the Guess textbox.  
    Guess.Clear();  
    Guess.Focus();  
    ```  
  
     <span data-ttu-id="ca4d3-317">完成した `EnterGuess_Click` ハンドラーは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-317">The following example is the completed `EnterGuess_Click` handler.</span></span>  
  
    ```vb  
    Private Sub EnterGuess_Click(sender As Object, e As EventArgs) Handles EnterGuess.Click  
        If WorkflowInstanceId = Guid.Empty Then  
            MessageBox.Show("Please select a workflow.")  
            Return  
        End If  
  
        Dim userGuess As Integer  
        If Not Int32.TryParse(Guess.Text, userGuess) Then  
            MessageBox.Show("Please enter an integer.")  
            Guess.SelectAll()  
            Guess.Focus()  
            Return  
        End If  
  
        Dim instance As WorkflowApplicationInstance = _  
            WorkflowApplication.GetInstance(WorkflowInstanceId, store)  
  
        'Use the persisted WorkflowIdentity to retrieve the correct workflow  
        'definition from the dictionary.  
        Dim wf As Activity = _  
            WorkflowVersionMap.GetWorkflowDefinition(instance.DefinitionIdentity)  
  
        'Associate the WorkflowApplication with the correct definition  
        Dim wfApp As WorkflowApplication = _  
            New WorkflowApplication(wf, instance.DefinitionIdentity)  
  
        'Configure the extensions and lifecycle handlers.  
        'Do this before the instance is loaded. Once the instance is  
        'loaded it is too late to add extensions.  
        ConfigureWorkflowApplication(wfApp)  
  
        'Load the workflow.  
        wfApp.Load(instance)  
  
        'Resume the workflow.  
        wfApp.ResumeBookmark("EnterGuess", userGuess)  
  
        'Clear the Guess textbox.  
        Guess.Clear()  
        Guess.Focus()  
    End Sub  
    ```  
  
    ```csharp  
    private void EnterGuess_Click(object sender, EventArgs e)  
    {  
        if (WorkflowInstanceId == Guid.Empty)  
        {  
            MessageBox.Show("Please select a workflow.");  
            return;  
        }  
  
        int guess;  
        if (!Int32.TryParse(Guess.Text, out guess))  
        {  
            MessageBox.Show("Please enter an integer.");  
            Guess.SelectAll();  
            Guess.Focus();  
            return;  
        }  
  
        WorkflowApplicationInstance instance =  
            WorkflowApplication.GetInstance(WorkflowInstanceId, store);  
  
        // Use the persisted WorkflowIdentity to retrieve the correct workflow  
        // definition from the dictionary.  
        Activity wf =  
            WorkflowVersionMap.GetWorkflowDefinition(instance.DefinitionIdentity);  
  
        // Associate the WorkflowApplication with the correct definition  
        WorkflowApplication wfApp =  
            new WorkflowApplication(wf, instance.DefinitionIdentity);  
  
        // Configure the extensions and lifecycle handlers.  
        // Do this before the instance is loaded. Once the instance is  
        // loaded it is too late to add extensions.  
        ConfigureWorkflowApplication(wfApp);  
  
        // Load the workflow.  
        wfApp.Load(instance);  
  
        // Resume the workflow.  
        wfApp.ResumeBookmark("EnterGuess", guess);  
  
        // Clear the Guess textbox.  
        Guess.Clear();  
        Guess.Focus();  
    }  
    ```  
  
### <a name="BKMK_TerminateWorkflow"></a> <span data-ttu-id="ca4d3-318">ワークフローを終了するには</span><span class="sxs-lookup"><span data-stu-id="ca4d3-318">To terminate a workflow</span></span>  
  
1. <span data-ttu-id="ca4d3-319">`Click` の `QuitGame` ハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-319">Add a `Click` handler for `QuitGame`.</span></span> <span data-ttu-id="ca4d3-320">ハンドラーを追加するに切り替える**デザイン ビュー**フォーム、およびダブルクリック`QuitGame`します。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-320">To add the handler, switch to **Design View** for the form, and double-click `QuitGame`.</span></span> <span data-ttu-id="ca4d3-321">ユーザーがこのボタンをクリックするたびに、現在選択されているワークフローが終了します。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-321">Whenever the user clicks this button the currently selected workflow is terminated.</span></span>  
  
    ```vb  
    Private Sub QuitGame_Click(sender As Object, e As EventArgs) Handles QuitGame.Click  
  
    End Sub  
    ```  
  
    ```csharp  
    private void QuitGame_Click(object sender, EventArgs e)  
    {  
  
    }  
    ```  
  
2. <span data-ttu-id="ca4d3-322">次のコードを `QuitGame_Click` ハンドラーに追加します。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-322">Add the following code to the `QuitGame_Click` handler.</span></span> <span data-ttu-id="ca4d3-323">このコードは、まず、ワークフローの一覧でワークフローが選択されているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-323">This code first checks to ensure that a workflow is selected in the workflow list.</span></span> <span data-ttu-id="ca4d3-324">その後、永続化されたインスタンスが `WorkflowApplicationInstance` に読み込まれ、`DefinitionIdentity` を使用して適切なワークフロー定義を判断し、`WorkflowApplication` を初期化します。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-324">Then it loads the persisted instance into a `WorkflowApplicationInstance`, uses the `DefinitionIdentity` to determine the correct workflow definition, and then initializes the `WorkflowApplication`.</span></span> <span data-ttu-id="ca4d3-325">次に、拡張機能とワークフロー ライフサイクル ハンドラーは、`ConfigureWorkflowApplication` の呼び出しによって構成されます。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-325">Next the extensions and workflow lifecycle handlers are configured with a call to `ConfigureWorkflowApplication`.</span></span> <span data-ttu-id="ca4d3-326">`WorkflowApplication` は構成された後に読み込まれ、その後 `Terminate` によって呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-326">Once the `WorkflowApplication` is configured, it is loaded, and then `Terminate` is called.</span></span>  
  
    ```vb  
    If WorkflowInstanceId = Guid.Empty Then  
        MessageBox.Show("Please select a workflow.")  
        Return  
    End If  
  
    Dim instance As WorkflowApplicationInstance = _  
        WorkflowApplication.GetInstance(WorkflowInstanceId, store)  
  
    'Use the persisted WorkflowIdentity to retrieve the correct workflow  
    'definition from the dictionary.  
    Dim wf As Activity = WorkflowVersionMap.GetWorkflowDefinition(instance.DefinitionIdentity)  
  
    'Associate the WorkflowApplication with the correct definition.  
    Dim wfApp As WorkflowApplication = _  
        New WorkflowApplication(wf, instance.DefinitionIdentity)  
  
    'Configure the extensions and lifecycle handlers.  
    ConfigureWorkflowApplication(wfApp)  
  
    'Load the workflow.  
    wfApp.Load(instance)  
  
    'Terminate the workflow.  
    wfApp.Terminate("User resigns.")  
    ```  
  
    ```csharp  
    if (WorkflowInstanceId == Guid.Empty)  
    {  
        MessageBox.Show("Please select a workflow.");  
        return;  
    }  
  
    WorkflowApplicationInstance instance =  
        WorkflowApplication.GetInstance(WorkflowInstanceId, store);  
  
    // Use the persisted WorkflowIdentity to retrieve the correct workflow  
    // definition from the dictionary.  
    Activity wf = WorkflowVersionMap.GetWorkflowDefinition(instance.DefinitionIdentity);  
  
    // Associate the WorkflowApplication with the correct definition  
    WorkflowApplication wfApp =  
        new WorkflowApplication(wf, instance.DefinitionIdentity);  
  
    // Configure the extensions and lifecycle handlers  
    ConfigureWorkflowApplication(wfApp);  
  
    // Load the workflow.  
    wfApp.Load(instance);  
  
    // Terminate the workflow.  
    wfApp.Terminate("User resigns.");  
    ```  
  
### <a name="BKMK_BuildAndRun"></a> <span data-ttu-id="ca4d3-327">アプリケーションをビルドして実行するには</span><span class="sxs-lookup"><span data-stu-id="ca4d3-327">To build and run the application</span></span>  
  
1. <span data-ttu-id="ca4d3-328">ダブルクリック**Program.cs** (または**Module1.vb**) で**ソリューション エクスプ ローラー**コードを表示します。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-328">Double-click **Program.cs** (or **Module1.vb**) in **Solution Explorer** to display the code.</span></span>  
  
2. <span data-ttu-id="ca4d3-329">次の `using` (または `Imports`) ステートメントを、他の `using` (または `Imports`) ステートメントを含むファイルの先頭に追加します。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-329">Add the following `using` (or `Imports`) statement at the top of the file with the other `using` (or `Imports`) statements.</span></span>  
  
    ```vb  
    Imports System.Windows.Forms  
    ```  
  
    ```csharp  
    using System.Windows.Forms;  
    ```  
  
3. <span data-ttu-id="ca4d3-330">削除するか、既存のワークフロー ホスティング コードをコメント[方法。ワークフローを実行する](how-to-run-a-workflow.md)、し、次のコードに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-330">Remove or comment out the existing workflow hosting code from [How to: Run a Workflow](how-to-run-a-workflow.md), and replace it with the following code.</span></span>  
  
    ```vb  
    Sub Main()  
        Application.EnableVisualStyles()  
        Application.Run(New WorkflowHostForm())  
    End Sub  
    ```  
  
    ```csharp  
    static void Main(string[] args)  
    {  
        Application.EnableVisualStyles();  
        Application.Run(new WorkflowHostForm());  
    }  
    ```  
  
4. <span data-ttu-id="ca4d3-331">右クリックして**NumberGuessWorkflowHost**で**ソリューション エクスプ ローラー**選択**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-331">Right-click **NumberGuessWorkflowHost** in **Solution Explorer** and choose **Properties**.</span></span> <span data-ttu-id="ca4d3-332">**アプリケーション**タブで、指定**Windows アプリケーション**の**出力の種類**します。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-332">In the **Application** tab, specify **Windows Application** for the **Output type**.</span></span> <span data-ttu-id="ca4d3-333">この手順は省略可能ですが、省略した場合は、フォームに加えてコンソール ウィンドウが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-333">This step is optional, but if it is not followed the console window is displayed in addition to the form.</span></span>  
  
5. <span data-ttu-id="ca4d3-334">Ctrl キーと Shift キーを押しながら B キーを押してアプリケーションをビルドします。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-334">Press Ctrl+Shift+B to build the application.</span></span>  
  
6. <span data-ttu-id="ca4d3-335">いることを確認**NumberGuessWorkflowHost**は、スタートアップ アプリケーションとして設定し、アプリケーションを起動するには、Ctrl + F5 キーを押します。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-335">Ensure that **NumberGuessWorkflowHost** is set as the startup application, and press Ctrl+F5 to start the application.</span></span>  
  
7. <span data-ttu-id="ca4d3-336">推測ゲームとワークフローを開始、およびクリックしての種類の範囲を選択**新しいゲーム**します。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-336">Select a range for the guessing game and the type of workflow to start, and click **New Game**.</span></span> <span data-ttu-id="ca4d3-337">推定値を入力、**推測**ボックスし、をクリックして**移動**推定値を送信します。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-337">Enter a guess in the **Guess** box and click **Go** to submit your guess.</span></span> <span data-ttu-id="ca4d3-338">`WriteLine` アクティビティからの出力がフォームに表示されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-338">Note that the output from the `WriteLine` activities is displayed on the form.</span></span>  
  
8. <span data-ttu-id="ca4d3-339">ワークフローの種類と数値の範囲を使用して複数のワークフローを開始、いくつかの推定値を入力およびからを選択して、ワークフロー間の切り替え、**ワークフロー インスタンス Id**一覧。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-339">Start several workflows using different workflow types and number ranges, enter some guesses, and switch between the workflows by selecting from the **Workflow Instance Id** list.</span></span>  
  
     <span data-ttu-id="ca4d3-340">新しいワークフローに切り替えると、前の推定値とワークフローの進行状況はステータス ウィンドウに表示されません。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-340">Note that when you switch to a new workflow, the previous guesses and progress of the workflow are not displayed in the status window.</span></span> <span data-ttu-id="ca4d3-341">ステータスが利用できない理由は、ステータスがキャプチャされず、どこにも保存されないためです。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-341">The reason the status is not available is because it is not captured and saved anywhere.</span></span> <span data-ttu-id="ca4d3-342">チュートリアルの次の手順で[方法。カスタム追跡参加要素を作成](how-to-create-a-custom-tracking-participant.md)、この情報を保存するカスタム追跡参加要素を作成します。</span><span class="sxs-lookup"><span data-stu-id="ca4d3-342">In the next step of the tutorial, [How to: Create a Custom Tracking Participant](how-to-create-a-custom-tracking-participant.md), you create a custom tracking participant that saves this information.</span></span>
