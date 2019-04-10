---
title: '方法: ワークフローの複数のバージョンを同時にホストする'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 09c575df-e0a3-4f3b-9e01-a7ac59d65287
ms.openlocfilehash: 4fc4565db58d008f52bc047d26118fc849648770
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2019
ms.locfileid: "59329454"
---
# <a name="how-to-host-multiple-versions-of-a-workflow-side-by-side"></a><span data-ttu-id="c566b-102">方法: ワークフローの複数のバージョンを同時にホストする</span><span class="sxs-lookup"><span data-stu-id="c566b-102">How to: Host Multiple Versions of a Workflow Side-by-Side</span></span>
`WorkflowIdentity` <span data-ttu-id="c566b-103">ワークフロー アプリケーションの開発者に関連付けるワークフロー定義、名前とバージョンをこの情報を永続化されたワークフロー インスタンスに関連付けられた方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="c566b-103">provides a way for workflow application developers to associate a name and a version with a workflow definition, and for this information to be associated with a persisted workflow instance.</span></span> <span data-ttu-id="c566b-104">この ID 情報は、ワークフロー アプリケーションの開発者がワークフロー定義の複数のバージョンの side-by-side 実行などのシナリオを有効にするために使用できます。また、動的更新などの他の機能の基礎となります。</span><span class="sxs-lookup"><span data-stu-id="c566b-104">This identity information can be used by workflow application developers to enable scenarios such as side-by-side execution of multiple versions of a workflow definition, and provides the cornerstone for other functionality such as dynamic update.</span></span> <span data-ttu-id="c566b-105">チュートリアルのこの手順では、`WorkflowIdentity` を使用してワークフローの複数のバージョンを同時にホストする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c566b-105">This step in the tutorial demonstrates how to use `WorkflowIdentity` to host multiple versions of a workflow at the same time.</span></span>

> [!NOTE]
>  <span data-ttu-id="c566b-106">完成版をダウンロードまたはチュートリアルのビデオ チュートリアルを表示を参照してください。 [Windows Workflow Foundation (WF45) - チュートリアル入門](https://go.microsoft.com/fwlink/?LinkID=248976)します。</span><span class="sxs-lookup"><span data-stu-id="c566b-106">To download a completed version or view a video walkthrough of the tutorial, see [Windows Workflow Foundation (WF45) - Getting Started Tutorial](https://go.microsoft.com/fwlink/?LinkID=248976).</span></span>  
  
## <a name="in-this-topic"></a><span data-ttu-id="c566b-107">このトピックの内容</span><span class="sxs-lookup"><span data-stu-id="c566b-107">In this topic</span></span>  
 <span data-ttu-id="c566b-108">チュートリアルのこの手順では、追加情報を提供するようにワークフローの `WriteLine` アクティビティが変更され、新しい `WriteLine` アクティビティが追加されます。</span><span class="sxs-lookup"><span data-stu-id="c566b-108">In this step of the tutorial, the `WriteLine` activities in the workflow are modified to provide additional information, and a new `WriteLine` activity is added.</span></span> <span data-ttu-id="c566b-109">元のワークフロー アセンブリのコピーが格納され、ホスト アプリケーションは、元のワークフローと更新されたワークフローの両方を同時に実行できるように更新されます。</span><span class="sxs-lookup"><span data-stu-id="c566b-109">A copy of the original workflow assembly is stored, and the host application is updated so that it can run both the original and the updated workflows at the same time.</span></span>  
  
-   [<span data-ttu-id="c566b-110">NumberGuessWorkflowActivities プロジェクトのコピーを作成するには</span><span class="sxs-lookup"><span data-stu-id="c566b-110">To make a copy of the NumberGuessWorkflowActivities project</span></span>](how-to-host-multiple-versions-of-a-workflow-side-by-side.md#BKMK_BackupCopy)  
  
-   [<span data-ttu-id="c566b-111">ワークフローを更新するには</span><span class="sxs-lookup"><span data-stu-id="c566b-111">To update the workflows</span></span>](how-to-host-multiple-versions-of-a-workflow-side-by-side.md#BKMK_UpdateWorkflows)  
  
    -   [<span data-ttu-id="c566b-112">StateMachine ワークフローを更新するには</span><span class="sxs-lookup"><span data-stu-id="c566b-112">To update the StateMachine workflow</span></span>](how-to-host-multiple-versions-of-a-workflow-side-by-side.md#BKMK_UpdateStateMachine)  
  
    -   [<span data-ttu-id="c566b-113">フローチャート ワークフローを更新するには</span><span class="sxs-lookup"><span data-stu-id="c566b-113">To update the Flowchart workflow</span></span>](how-to-host-multiple-versions-of-a-workflow-side-by-side.md#BKMK_UpdateFlowchart)  
  
    -   [<span data-ttu-id="c566b-114">シーケンシャル ワークフローを更新するには</span><span class="sxs-lookup"><span data-stu-id="c566b-114">To update the Sequential workflow</span></span>](how-to-host-multiple-versions-of-a-workflow-side-by-side.md#BKMK_UpdateSequential)  
  
-   [<span data-ttu-id="c566b-115">以前のワークフロー バージョンを含むように WorkflowVersionMap を更新するには</span><span class="sxs-lookup"><span data-stu-id="c566b-115">To update WorkflowVersionMap to include the previous workflow versions</span></span>](how-to-host-multiple-versions-of-a-workflow-side-by-side.md#BKMK_UpdateWorkflowVersionMap)  
  
-   [<span data-ttu-id="c566b-116">アプリケーションをビルドして実行するには</span><span class="sxs-lookup"><span data-stu-id="c566b-116">To build and run the application</span></span>](how-to-host-multiple-versions-of-a-workflow-side-by-side.md#BKMK_BuildAndRun)  
  
> [!NOTE]
>  <span data-ttu-id="c566b-117">このトピックの手順を実行する前に、アプリケーションを実行し、各種類のワークフローをいくつか開始して、ワークフローごとに 1 つまたは 2 つの推定値を作成します。</span><span class="sxs-lookup"><span data-stu-id="c566b-117">Before following the steps in this topic, run the application, start several workflows of each type, and making one or two guesses for each one.</span></span> <span data-ttu-id="c566b-118">これらの永続化されたワークフローがこの手順と次の手順で使用される[方法。実行中のワークフロー インスタンスの定義を更新](how-to-update-the-definition-of-a-running-workflow-instance.md)します。</span><span class="sxs-lookup"><span data-stu-id="c566b-118">These persisted workflows are used in this step and the following step, [How to: Update the Definition of a Running Workflow Instance](how-to-update-the-definition-of-a-running-workflow-instance.md).</span></span>

> [!NOTE]
>  <span data-ttu-id="c566b-119">チュートリアル入門の各手順は、その前の手順に応じて異なります。</span><span class="sxs-lookup"><span data-stu-id="c566b-119">Each step in the Getting Started tutorial depends on the previous steps.</span></span> <span data-ttu-id="c566b-120">前の手順を完了しなかった場合は、」からチュートリアルの完成版をダウンロードできます[Windows Workflow Foundation (WF45) - チュートリアル入門](https://go.microsoft.com/fwlink/?LinkID=248976)します。</span><span class="sxs-lookup"><span data-stu-id="c566b-120">If you did not complete the previous steps you can download a completed version of the tutorial from [Windows Workflow Foundation (WF45) - Getting Started Tutorial](https://go.microsoft.com/fwlink/?LinkID=248976).</span></span>  
  
### <a name="BKMK_BackupCopy"></a> <span data-ttu-id="c566b-121">NumberGuessWorkflowActivities プロジェクトのコピーを作成するには</span><span class="sxs-lookup"><span data-stu-id="c566b-121">To make a copy of the NumberGuessWorkflowActivities project</span></span>  
  
1. <span data-ttu-id="c566b-122">開く、 **WF45GettingStartedTutorial**が開いていない場合、Visual Studio 2012 でのソリューションです。</span><span class="sxs-lookup"><span data-stu-id="c566b-122">Open the **WF45GettingStartedTutorial** solution in Visual Studio 2012 if it is not open.</span></span>  
  
2. <span data-ttu-id="c566b-123">Ctrl キーと Shift キーを押しながら B キーを押して、ソリューションをビルドします。</span><span class="sxs-lookup"><span data-stu-id="c566b-123">Press CTRL+SHIFT+B to build the solution.</span></span>  
  
3. <span data-ttu-id="c566b-124">閉じる、 **WF45GettingStartedTutorial**ソリューション。</span><span class="sxs-lookup"><span data-stu-id="c566b-124">Close the **WF45GettingStartedTutorial** solution.</span></span>  
  
4. <span data-ttu-id="c566b-125">エクスプローラーを開き、チュートリアルのソリューション ファイルおよびプロジェクト フォルダーが格納されているフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="c566b-125">Open Windows Explorer and navigate to the folder where the tutorial solution file and the project folders are located.</span></span>  
  
5. <span data-ttu-id="c566b-126">という名前の新しいフォルダーを作成する**PreviousVersions**と同じフォルダーに**NumberGuessWorkflowHost**と**NumberGuessWorkflowActivities**します。</span><span class="sxs-lookup"><span data-stu-id="c566b-126">Create a new folder named **PreviousVersions** in the same folder as **NumberGuessWorkflowHost** and **NumberGuessWorkflowActivities**.</span></span> <span data-ttu-id="c566b-127">このフォルダーは、チュートリアルの以降の手順で使用されるワークフローの異なるバージョンを含むアセンブリを格納するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="c566b-127">This folder is used to contain the assemblies that contain the different versions of the workflows used in the subsequent tutorial steps.</span></span>  
  
6. <span data-ttu-id="c566b-128">移動し、 **NumberGuessWorkflowActivities\bin\debug**フォルダー (または**bin \release**プロジェクトの設定によって)。</span><span class="sxs-lookup"><span data-stu-id="c566b-128">Navigate to the **NumberGuessWorkflowActivities\bin\debug** folder (or **bin\release** depending on your project settings).</span></span> <span data-ttu-id="c566b-129">コピー **NumberGuessWorkflowActivities.dll**貼り付けます、 **PreviousVersions**フォルダー。</span><span class="sxs-lookup"><span data-stu-id="c566b-129">Copy **NumberGuessWorkflowActivities.dll** and paste it into the **PreviousVersions** folder.</span></span>  
  
7. <span data-ttu-id="c566b-130">名前を変更**NumberGuessWorkflowActivities.dll**で、 **PreviousVersions**フォルダー **NumberGuessWorkflowActivities_v1.dll**します。</span><span class="sxs-lookup"><span data-stu-id="c566b-130">Rename **NumberGuessWorkflowActivities.dll** in the **PreviousVersions** folder to **NumberGuessWorkflowActivities_v1.dll**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c566b-131">このトピックの手順では、ワークフローの複数のバージョンを格納するためのアセンブリを管理する 1 つの方法を示します。</span><span class="sxs-lookup"><span data-stu-id="c566b-131">The steps in this topic demonstrate one way to manage the assemblies used to contain multiple versions of the workflows.</span></span> <span data-ttu-id="c566b-132">アセンブリに厳密な名前を付けてグローバル アセンブリ キャッシュに登録するなど、他の方法も使用できます。</span><span class="sxs-lookup"><span data-stu-id="c566b-132">Other methods such as strong naming the assemblies and registering them in the global assembly cache could also be used.</span></span>

8. <span data-ttu-id="c566b-133">という名前の新しいフォルダーを作成する**NumberGuessWorkflowActivities_du**と同じフォルダーに**NumberGuessWorkflowHost**、 **NumberGuessWorkflowActivities**、し、新しく追加**PreviousVersions**フォルダーでは、すべてのファイルとサブフォルダーをコピーし、 **NumberGuessWorkflowActivities**を新しいフォルダー **NumberGuessWorkflowActivities_du**フォルダー。</span><span class="sxs-lookup"><span data-stu-id="c566b-133">Create a new folder named **NumberGuessWorkflowActivities_du** in the same folder as **NumberGuessWorkflowHost**, **NumberGuessWorkflowActivities**, and the newly added **PreviousVersions** folder, and copy all of the files and subfolders from the **NumberGuessWorkflowActivities** folder into the new **NumberGuessWorkflowActivities_du** folder.</span></span> <span data-ttu-id="c566b-134">アクティビティの最初のバージョンのプロジェクトのこのバックアップ コピーが使用される[方法。実行中のワークフロー インスタンスの定義を更新](how-to-update-the-definition-of-a-running-workflow-instance.md)します。</span><span class="sxs-lookup"><span data-stu-id="c566b-134">This backup copy of the project for the initial version of the activities is used in [How to: Update the Definition of a Running Workflow Instance](how-to-update-the-definition-of-a-running-workflow-instance.md).</span></span>

9. <span data-ttu-id="c566b-135">開き直す、 **WF45GettingStartedTutorial** Visual Studio 2012 でのソリューションです。</span><span class="sxs-lookup"><span data-stu-id="c566b-135">Re-open the **WF45GettingStartedTutorial** solution in Visual Studio 2012.</span></span>

### <a name="BKMK_UpdateWorkflows"></a> <span data-ttu-id="c566b-136">ワークフローを更新するには</span><span class="sxs-lookup"><span data-stu-id="c566b-136">To update the workflows</span></span>
 <span data-ttu-id="c566b-137">ここでは、ワークフロー定義が更新されます。</span><span class="sxs-lookup"><span data-stu-id="c566b-137">In this section, the workflow definitions are updated.</span></span> <span data-ttu-id="c566b-138">ユーザーの推定値についてフィードバックを返す 2 つの `WriteLine` アクティビティが更新され、新しい `WriteLine` アクティビティが追加されます。新しいアクティビティは、数値が推定されるとゲームに関する追加情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="c566b-138">The two `WriteLine` activities that give feedback on the user's guess are updated, and a new `WriteLine` activity is added that provides additional information about the game once the number is guessed.</span></span>

#### <a name="BKMK_UpdateStateMachine"></a> <span data-ttu-id="c566b-139">ステート マシン ワークフローを更新するには</span><span class="sxs-lookup"><span data-stu-id="c566b-139">To update the StateMachine workflow</span></span>

1. <span data-ttu-id="c566b-140">**ソリューション エクスプ ローラー**下で、 **NumberGuessWorkflowActivities**プロジェクトで、ダブルクリックして**StateMachineNumberGuessWorkflow.xaml**します。</span><span class="sxs-lookup"><span data-stu-id="c566b-140">In **Solution Explorer**, under the **NumberGuessWorkflowActivities** project, double-click **StateMachineNumberGuessWorkflow.xaml**.</span></span>

2. <span data-ttu-id="c566b-141">ダブルクリックして、 **Guess Incorrect**ステート マシンを移行します。</span><span class="sxs-lookup"><span data-stu-id="c566b-141">Double-click the **Guess Incorrect** transition on the state machine.</span></span>

3. <span data-ttu-id="c566b-142">`Text` アクティビティで、左端の `WriteLine` の `If` を更新します。</span><span class="sxs-lookup"><span data-stu-id="c566b-142">Update the `Text` of the left-most `WriteLine` in the `If` activity.</span></span>

    ```vb
    Guess & " is too low."
    ```

    ```csharp
    Guess + " is too low."
    ```

4. <span data-ttu-id="c566b-143">`Text` アクティビティで、右端の `WriteLine` の `If` を更新します。</span><span class="sxs-lookup"><span data-stu-id="c566b-143">Update the `Text` of the right-most `WriteLine` in the `If` activity.</span></span>

    ```vb
    Guess & " is too high."
    ```

    ```csharp
    Guess + " is too high."
    ```

5. <span data-ttu-id="c566b-144">全体に戻る をクリックして状態マシン ビューは、ワークフロー デザイナーに**StateMachine**階層リンクで、ワークフロー デザイナーの上部に表示します。</span><span class="sxs-lookup"><span data-stu-id="c566b-144">Return to the overall state machine view in the workflow designer by clicking **StateMachine** in the breadcrumb display at the top of the workflow designer.</span></span>

6. <span data-ttu-id="c566b-145">ダブルクリックして、 **Guess Correct**ステート マシンを移行します。</span><span class="sxs-lookup"><span data-stu-id="c566b-145">Double-click the **Guess Correct** transition on the state machine.</span></span>

7. <span data-ttu-id="c566b-146">ドラッグ、 **WriteLine**からのアクティビティ、**プリミティブ**のセクション、**ツールボックス**上にドロップし、**ここにアクティビティを Drop Action**のラベル、遷移します。</span><span class="sxs-lookup"><span data-stu-id="c566b-146">Drag a **WriteLine** activity from the **Primitives** section of the **Toolbox** and drop it on the **Drop Action activity here** label of the transition.</span></span>

8. <span data-ttu-id="c566b-147">`Text` プロパティ ボックスに、次の式を入力します。</span><span class="sxs-lookup"><span data-stu-id="c566b-147">Type the following expression into the `Text` property box.</span></span>

    ```vb
    Guess & " is correct. You guessed it in " & Turns & " turns."
    ```

    ```csharp
    Guess + " is correct. You guessed it in " + Turns + " turns."
    ```

#### <a name="BKMK_UpdateFlowchart"></a> <span data-ttu-id="c566b-148">フローチャート ワークフローを更新するには</span><span class="sxs-lookup"><span data-stu-id="c566b-148">To update the Flowchart workflow</span></span>

1. <span data-ttu-id="c566b-149">**ソリューション エクスプ ローラー**下で、 **NumberGuessWorkflowActivities**プロジェクトで、ダブルクリックして**FlowchartNumberGuessWorkflow.xaml**します。</span><span class="sxs-lookup"><span data-stu-id="c566b-149">In **Solution Explorer**, under the **NumberGuessWorkflowActivities** project, double-click **FlowchartNumberGuessWorkflow.xaml**.</span></span>

2. <span data-ttu-id="c566b-150">左端の `Text` アクティビティの `WriteLine` を更新します。</span><span class="sxs-lookup"><span data-stu-id="c566b-150">Update the `Text` of the left-most `WriteLine` activity.</span></span>

    ```vb
    Guess & " is too low."
    ```

    ```csharp
    Guess + " is too low."
    ```

3. <span data-ttu-id="c566b-151">右端の `Text` アクティビティの `WriteLine` を更新します。</span><span class="sxs-lookup"><span data-stu-id="c566b-151">Update the `Text` of the right-most `WriteLine` activity.</span></span>

    ```vb
    Guess & " is too high."
    ```

    ```csharp
    Guess + " is too high."
    ```

4. <span data-ttu-id="c566b-152">ドラッグ、 **WriteLine**からのアクティビティ、**プリミティブ**のセクション、**ツールボックス**のドロップ ポイント上にドロップし、`True`の最上位にあるアクション`FlowDecision`.</span><span class="sxs-lookup"><span data-stu-id="c566b-152">Drag a **WriteLine** activity from the **Primitives** section of the **Toolbox** and drop it on the drop point of the `True` action of the topmost `FlowDecision`.</span></span> <span data-ttu-id="c566b-153">`WriteLine` アクティビティがフローチャートに追加され、`True` の `FlowDecision` アクションにリンクされます。</span><span class="sxs-lookup"><span data-stu-id="c566b-153">The `WriteLine` activity is added to the flowchart and linked to the `True` action of the `FlowDecision`.</span></span>

5. <span data-ttu-id="c566b-154">`Text` プロパティ ボックスに、次の式を入力します。</span><span class="sxs-lookup"><span data-stu-id="c566b-154">Type the following expression into the `Text` property box.</span></span>

    ```vb
    Guess & " is correct. You guessed it in " & Turns & " turns."
    ```

    ```csharp
    Guess + " is correct. You guessed it in " + Turns + " turns."
    ```

#### <a name="BKMK_UpdateSequential"></a> <span data-ttu-id="c566b-155">シーケンシャル ワークフローを更新するには</span><span class="sxs-lookup"><span data-stu-id="c566b-155">To update the Sequential workflow</span></span>

1. <span data-ttu-id="c566b-156">**ソリューション エクスプ ローラー**下で、 **NumberGuessWorkflowActivities**プロジェクトで、ダブルクリックして**SequentialNumberGuessWorkflow.xaml**します。</span><span class="sxs-lookup"><span data-stu-id="c566b-156">In **Solution Explorer**, under the **NumberGuessWorkflowActivities** project, double-click **SequentialNumberGuessWorkflow.xaml**.</span></span>

2. <span data-ttu-id="c566b-157">`Text` アクティビティで、左端の `WriteLine` の `If` を更新します。</span><span class="sxs-lookup"><span data-stu-id="c566b-157">Update the `Text` of the left-most `WriteLine` in the `If` activity.</span></span>

    ```vb
    Guess & " is too low."
    ```

    ```csharp
    Guess + " is too low."
    ```

3. <span data-ttu-id="c566b-158">`Text` アクティビティで、右端の `WriteLine` アクティビティの `If` を更新します。</span><span class="sxs-lookup"><span data-stu-id="c566b-158">Update the `Text` of the right-most `WriteLine` activity in the `If` activity.</span></span>

    ```vb
    Guess & " is too high."
    ```

    ```csharp
    Guess + " is too high."
    ```

4. <span data-ttu-id="c566b-159">ドラッグ、 **WriteLine**からのアクティビティ、**プリミティブ**のセクション、**ツールボックス**後ろにドロップし、 **DoWhile**アクティビティように、 **WriteLine**ルート内の最後の活動は、`Sequence`アクティビティ。</span><span class="sxs-lookup"><span data-stu-id="c566b-159">Drag a **WriteLine** activity from the **Primitives** section of the **Toolbox** and drop it after the **DoWhile** activity so that the **WriteLine** is the final activity in the root `Sequence` activity.</span></span>

5. <span data-ttu-id="c566b-160">`Text` プロパティ ボックスに、次の式を入力します。</span><span class="sxs-lookup"><span data-stu-id="c566b-160">Type the following expression into the `Text` property box.</span></span>

    ```vb
    Guess & " is correct. You guessed it in " & Turns & " turns."
    ```

    ```csharp
    Guess + " is correct. You guessed it in " + Turns + " turns."
    ```

### <a name="BKMK_UpdateWorkflowVersionMap"></a> <span data-ttu-id="c566b-161">ワークフローの以前のバージョンを含める WorkflowVersionMap を更新します。</span><span class="sxs-lookup"><span data-stu-id="c566b-161">To update WorkflowVersionMap to include the previous workflow versions</span></span>

1. <span data-ttu-id="c566b-162">ダブルクリック**WorkflowVersionMap.cs** (または**WorkflowVersionMap.vb**) の下、 **NumberGuessWorkflowHost**プロジェクトを開きます。</span><span class="sxs-lookup"><span data-stu-id="c566b-162">Double-click **WorkflowVersionMap.cs** (or **WorkflowVersionMap.vb**) under the **NumberGuessWorkflowHost** project to open it.</span></span>

2. <span data-ttu-id="c566b-163">次の `using` (または `Imports`) ステートメントを、他の `using` (または `Imports`) ステートメントを含むファイルの先頭に追加します。</span><span class="sxs-lookup"><span data-stu-id="c566b-163">Add the following `using` (or `Imports`) statements to the top of the file with the other `using` (or `Imports`) statements.</span></span>

    ```vb
    Imports System.Reflection
    Imports System.IO
    ```

    ```csharp
    using System.Reflection;
    using System.IO;
    ```

3. <span data-ttu-id="c566b-164">既存の 3 つのワークフロー ID 宣言の直後に、新しいワークフロー ID を 3 つ追加します。</span><span class="sxs-lookup"><span data-stu-id="c566b-164">Add three new workflow identities just below the three existing workflow identity declarations.</span></span> <span data-ttu-id="c566b-165">これらの新しい `v1` ワークフロー ID は、更新が行われる前に開始されたワークフローに対して正しいワークフロー定義を指定するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="c566b-165">These new `v1` workflow identities will be used provide the correct workflow definition to workflows started before the updates were made.</span></span>

    ```vb
    'Current version identities.
    Public StateMachineNumberGuessIdentity As WorkflowIdentity
    Public FlowchartNumberGuessIdentity As WorkflowIdentity
    Public SequentialNumberGuessIdentity As WorkflowIdentity

    'v1 Identities.
    Public StateMachineNumberGuessIdentity_v1 As WorkflowIdentity
    Public FlowchartNumberGuessIdentity_v1 As WorkflowIdentity
    Public SequentialNumberGuessIdentity_v1 As WorkflowIdentity
    ```

    ```csharp
    // Current version identities.
    static public WorkflowIdentity StateMachineNumberGuessIdentity;
    static public WorkflowIdentity FlowchartNumberGuessIdentity;
    static public WorkflowIdentity SequentialNumberGuessIdentity;

    // v1 identities.
    static public WorkflowIdentity StateMachineNumberGuessIdentity_v1;
    static public WorkflowIdentity FlowchartNumberGuessIdentity_v1;
    static public WorkflowIdentity SequentialNumberGuessIdentity_v1;
    ```

4. <span data-ttu-id="c566b-166">`WorkflowVersionMap` コンストラクターで、3 つの現在のワークフロー ID の `Version` プロパティを `2.0.0.0` に更新します。</span><span class="sxs-lookup"><span data-stu-id="c566b-166">In the `WorkflowVersionMap` constructor, update the `Version` property of the three current workflow identities to `2.0.0.0`.</span></span>

    ```vb
    'Add the current workflow version identities.
    StateMachineNumberGuessIdentity = New WorkflowIdentity With
    {
        .Name = "StateMachineNumberGuessWorkflow",
        .Version = New Version(2, 0, 0, 0)
    }

    FlowchartNumberGuessIdentity = New WorkflowIdentity With
    {
        .Name = "FlowchartNumberGuessWorkflow",
        .Version = New Version(2, 0, 0, 0)
    }

    SequentialNumberGuessIdentity = New WorkflowIdentity With
    {
        .Name = "SequentialNumberGuessWorkflow",
        .Version = New Version(2, 0, 0, 0)
    }

    map.Add(StateMachineNumberGuessIdentity, New StateMachineNumberGuessWorkflow())
    map.Add(FlowchartNumberGuessIdentity, New FlowchartNumberGuessWorkflow())
    map.Add(SequentialNumberGuessIdentity, New SequentialNumberGuessWorkflow())
    ```

    ```csharp
    // Add the current workflow version identities.
    StateMachineNumberGuessIdentity = new WorkflowIdentity
    {
        Name = "StateMachineNumberGuessWorkflow",
        // Version = new Version(1, 0, 0, 0),
        Version = new Version(2, 0, 0, 0)
    };

    FlowchartNumberGuessIdentity = new WorkflowIdentity
    {
        Name = "FlowchartNumberGuessWorkflow",
        // Version = new Version(1, 0, 0, 0),
        Version = new Version(2, 0, 0, 0)
    };

    SequentialNumberGuessIdentity = new WorkflowIdentity
    {
        Name = "SequentialNumberGuessWorkflow",
        // Version = new Version(1, 0, 0, 0),
        Version = new Version(2, 0, 0, 0)
    };

    map.Add(StateMachineNumberGuessIdentity, new StateMachineNumberGuessWorkflow());
    map.Add(FlowchartNumberGuessIdentity, new FlowchartNumberGuessWorkflow());
    map.Add(SequentialNumberGuessIdentity, new SequentialNumberGuessWorkflow());
    ```

     <span data-ttu-id="c566b-167">ワークフローの現在のバージョンをディクショナリに追加するコードでは、プロジェクトで参照されている現在のバージョンを使用しているため、ワークフロー定義を初期化するコードを更新する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="c566b-167">The code in that adds the current versions of the workflows to the dictionary uses the current versions that are referenced in the project, so the code that initializes the workflow definitions does not need to be updated.</span></span>

5. <span data-ttu-id="c566b-168">コンストラクターで、現在のバージョンをディクショナリに追加するコードの直後に、次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="c566b-168">Add the following code in the constructor just after the code that adds the current versions to the dictionary.</span></span>

    ```vb
    'Initialize the previous workflow version identities.
    StateMachineNumberGuessIdentity_v1 = New WorkflowIdentity With
    {
        .Name = "StateMachineNumberGuessWorkflow",
        .Version = New Version(1, 0, 0, 0)
    }

    FlowchartNumberGuessIdentity_v1 = New WorkflowIdentity With
    {
        .Name = "FlowchartNumberGuessWorkflow",
        .Version = New Version(1, 0, 0, 0)
    }

    SequentialNumberGuessIdentity_v1 = New WorkflowIdentity With
    {
        .Name = "SequentialNumberGuessWorkflow",
        .Version = New Version(1, 0, 0, 0)
    }
    ```

    ```csharp
    // Initialize the previous workflow version identities.
    StateMachineNumberGuessIdentity_v1 = new WorkflowIdentity
    {
        Name = "StateMachineNumberGuessWorkflow",
        Version = new Version(1, 0, 0, 0)
    };

    FlowchartNumberGuessIdentity_v1 = new WorkflowIdentity
    {
        Name = "FlowchartNumberGuessWorkflow",
        Version = new Version(1, 0, 0, 0)
    };

    SequentialNumberGuessIdentity_v1 = new WorkflowIdentity
    {
        Name = "SequentialNumberGuessWorkflow",
        Version = new Version(1, 0, 0, 0)
    };
    ```

     <span data-ttu-id="c566b-169">これらのワークフロー ID は、対応するワークフロー定義の最初のバージョンに関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="c566b-169">These workflow identities are associated with the initial versions of the corresponding workflow definitions.</span></span>

6. <span data-ttu-id="c566b-170">次に、ワークフロー定義の最初のバージョンを含むアセンブリを読み込み、対応するワークフロー定義を作成してそのディクショナリに追加します。</span><span class="sxs-lookup"><span data-stu-id="c566b-170">Next, load the assembly that contains the initial version of the workflow definitions, and create and add the corresponding workflow definitions to the dictionary.</span></span>

    ```vb
    'Add the previous version workflow identities to the dictionary along with
    'the corresponding workflow definitions loaded from the v1 assembly.
    'Assembly.LoadFile requires an absolute path so convert this relative path
    'to an absolute path.
    Dim v1AssemblyPath As String = "..\..\..\PreviousVersions\NumberGuessWorkflowActivities_v1.dll"
    v1AssemblyPath = Path.GetFullPath(v1AssemblyPath)
    Dim v1Assembly As Assembly = Assembly.LoadFile(v1AssemblyPath)

    map.Add(StateMachineNumberGuessIdentity_v1,
        v1Assembly.CreateInstance("NumberGuessWorkflowActivities.StateMachineNumberGuessWorkflow"))

    map.Add(SequentialNumberGuessIdentity_v1,
        v1Assembly.CreateInstance("NumberGuessWorkflowActivities.SequentialNumberGuessWorkflow"))

    map.Add(FlowchartNumberGuessIdentity_v1,
        v1Assembly.CreateInstance("NumberGuessWorkflowActivities.FlowchartNumberGuessWorkflow"))
    ```

    ```csharp
    // Add the previous version workflow identities to the dictionary along with
    // the corresponding workflow definitions loaded from the v1 assembly.
    // Assembly.LoadFile requires an absolute path so convert this relative path
    // to an absolute path.
    string v1AssemblyPath = @"..\..\..\PreviousVersions\NumberGuessWorkflowActivities_v1.dll";
    v1AssemblyPath = Path.GetFullPath(v1AssemblyPath);
    Assembly v1Assembly = Assembly.LoadFile(v1AssemblyPath);

    map.Add(StateMachineNumberGuessIdentity_v1,
        v1Assembly.CreateInstance("NumberGuessWorkflowActivities.StateMachineNumberGuessWorkflow") as Activity);

    map.Add(SequentialNumberGuessIdentity_v1,
        v1Assembly.CreateInstance("NumberGuessWorkflowActivities.SequentialNumberGuessWorkflow") as Activity);

    map.Add(FlowchartNumberGuessIdentity_v1,
        v1Assembly.CreateInstance("NumberGuessWorkflowActivities.FlowchartNumberGuessWorkflow") as Activity);
    ```

     <span data-ttu-id="c566b-171">次の例では、更新された `WorkflowVersionMap` クラス全体を示します。</span><span class="sxs-lookup"><span data-stu-id="c566b-171">The following example is the complete listing for the updated `WorkflowVersionMap` class.</span></span>

    ```vb
    Public Module WorkflowVersionMap
        Dim map As Dictionary(Of WorkflowIdentity, Activity)

        'Current version identities.
        Public StateMachineNumberGuessIdentity As WorkflowIdentity
        Public FlowchartNumberGuessIdentity As WorkflowIdentity
        Public SequentialNumberGuessIdentity As WorkflowIdentity

        'v1 Identities.
        Public StateMachineNumberGuessIdentity_v1 As WorkflowIdentity
        Public FlowchartNumberGuessIdentity_v1 As WorkflowIdentity
        Public SequentialNumberGuessIdentity_v1 As WorkflowIdentity

        Sub New()
            map = New Dictionary(Of WorkflowIdentity, Activity)

            'Add the current workflow version identities.
            StateMachineNumberGuessIdentity = New WorkflowIdentity With
            {
                .Name = "StateMachineNumberGuessWorkflow",
                .Version = New Version(2, 0, 0, 0)
            }

            FlowchartNumberGuessIdentity = New WorkflowIdentity With
            {
                .Name = "FlowchartNumberGuessWorkflow",
                .Version = New Version(2, 0, 0, 0)
            }

            SequentialNumberGuessIdentity = New WorkflowIdentity With
            {
                .Name = "SequentialNumberGuessWorkflow",
                .Version = New Version(2, 0, 0, 0)
            }

            map.Add(StateMachineNumberGuessIdentity, New StateMachineNumberGuessWorkflow())
            map.Add(FlowchartNumberGuessIdentity, New FlowchartNumberGuessWorkflow())
            map.Add(SequentialNumberGuessIdentity, New SequentialNumberGuessWorkflow())

            'Initialize the previous workflow version identities.
            StateMachineNumberGuessIdentity_v1 = New WorkflowIdentity With
            {
                .Name = "StateMachineNumberGuessWorkflow",
                .Version = New Version(1, 0, 0, 0)
            }

            FlowchartNumberGuessIdentity_v1 = New WorkflowIdentity With
            {
                .Name = "FlowchartNumberGuessWorkflow",
                .Version = New Version(1, 0, 0, 0)
            }

            SequentialNumberGuessIdentity_v1 = New WorkflowIdentity With
            {
                .Name = "SequentialNumberGuessWorkflow",
                .Version = New Version(1, 0, 0, 0)
            }

            'Add the previous version workflow identities to the dictionary along with
            'the corresponding workflow definitions loaded from the v1 assembly.
            'Assembly.LoadFile requires an absolute path so convert this relative path
            'to an absolute path.
            Dim v1AssemblyPath As String = "..\..\..\PreviousVersions\NumberGuessWorkflowActivities_v1.dll"
            v1AssemblyPath = Path.GetFullPath(v1AssemblyPath)
            Dim v1Assembly As Assembly = Assembly.LoadFile(v1AssemblyPath)

            map.Add(StateMachineNumberGuessIdentity_v1,
                v1Assembly.CreateInstance("NumberGuessWorkflowActivities.StateMachineNumberGuessWorkflow"))

            map.Add(SequentialNumberGuessIdentity_v1,
                v1Assembly.CreateInstance("NumberGuessWorkflowActivities.SequentialNumberGuessWorkflow"))

            map.Add(FlowchartNumberGuessIdentity_v1,
                v1Assembly.CreateInstance("NumberGuessWorkflowActivities.FlowchartNumberGuessWorkflow"))
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

        // v1 identities.
        static public WorkflowIdentity StateMachineNumberGuessIdentity_v1;
        static public WorkflowIdentity FlowchartNumberGuessIdentity_v1;
        static public WorkflowIdentity SequentialNumberGuessIdentity_v1;

        static WorkflowVersionMap()
        {
            map = new Dictionary<WorkflowIdentity, Activity>();

            // Add the current workflow version identities.
            StateMachineNumberGuessIdentity = new WorkflowIdentity
            {
                Name = "StateMachineNumberGuessWorkflow",
                // Version = new Version(1, 0, 0, 0),
                Version = new Version(2, 0, 0, 0)
            };

            FlowchartNumberGuessIdentity = new WorkflowIdentity
            {
                Name = "FlowchartNumberGuessWorkflow",
                // Version = new Version(1, 0, 0, 0),
                Version = new Version(2, 0, 0, 0)
            };

            SequentialNumberGuessIdentity = new WorkflowIdentity
            {
                Name = "SequentialNumberGuessWorkflow",
                // Version = new Version(1, 0, 0, 0),
                Version = new Version(2, 0, 0, 0)
            };

            map.Add(StateMachineNumberGuessIdentity, new StateMachineNumberGuessWorkflow());
            map.Add(FlowchartNumberGuessIdentity, new FlowchartNumberGuessWorkflow());
            map.Add(SequentialNumberGuessIdentity, new SequentialNumberGuessWorkflow());

            // Initialize the previous workflow version identities.
            StateMachineNumberGuessIdentity_v1 = new WorkflowIdentity
            {
                Name = "StateMachineNumberGuessWorkflow",
                Version = new Version(1, 0, 0, 0)
            };

            FlowchartNumberGuessIdentity_v1 = new WorkflowIdentity
            {
                Name = "FlowchartNumberGuessWorkflow",
                Version = new Version(1, 0, 0, 0)
            };

            SequentialNumberGuessIdentity_v1 = new WorkflowIdentity
            {
                Name = "SequentialNumberGuessWorkflow",
                Version = new Version(1, 0, 0, 0)
            };

            // Add the previous version workflow identities to the dictionary along with
            // the corresponding workflow definitions loaded from the v1 assembly.
            // Assembly.LoadFile requires an absolute path so convert this relative path
            // to an absolute path.
            string v1AssemblyPath = @"..\..\..\PreviousVersions\NumberGuessWorkflowActivities_v1.dll";
            v1AssemblyPath = Path.GetFullPath(v1AssemblyPath);
            Assembly v1Assembly = Assembly.LoadFile(v1AssemblyPath);

            map.Add(StateMachineNumberGuessIdentity_v1,
                v1Assembly.CreateInstance("NumberGuessWorkflowActivities.StateMachineNumberGuessWorkflow") as Activity);

            map.Add(SequentialNumberGuessIdentity_v1,
                v1Assembly.CreateInstance("NumberGuessWorkflowActivities.SequentialNumberGuessWorkflow") as Activity);

            map.Add(FlowchartNumberGuessIdentity_v1,
                v1Assembly.CreateInstance("NumberGuessWorkflowActivities.FlowchartNumberGuessWorkflow") as Activity);
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

### <a name="BKMK_BuildAndRun"></a> <span data-ttu-id="c566b-172">アプリケーションをビルドして実行するには</span><span class="sxs-lookup"><span data-stu-id="c566b-172">To build and run the application</span></span>

1. <span data-ttu-id="c566b-173">Ctrl キーと Shift キーを押しながら B キーを押してアプリケーションをビルドし、Ctrl キーを押しながら F5 キーを押して起動します。</span><span class="sxs-lookup"><span data-stu-id="c566b-173">Press CTRL+SHIFT+B to build the application, and then CTRL+F5 to start.</span></span>

2. <span data-ttu-id="c566b-174">クリックして新しいワークフローを開始**新しいゲーム**します。</span><span class="sxs-lookup"><span data-stu-id="c566b-174">Start a new workflow by clicking **New Game**.</span></span> <span data-ttu-id="c566b-175">ワークフローのバージョンは、ステータス ウィンドウの下に表示され、関連付けられた `WorkflowIdentity` から更新後のバージョンを反映します。</span><span class="sxs-lookup"><span data-stu-id="c566b-175">The version of the workflow is displayed under the status window and reflects the updated version from the associated `WorkflowIdentity`.</span></span> <span data-ttu-id="c566b-176">完了時にワークフローの追跡ファイルを確認できるように `InstanceId` を書き留めておき、ゲームが完了するまで推定値を入力します。</span><span class="sxs-lookup"><span data-stu-id="c566b-176">Make a note of the `InstanceId` so you can view the tracking file for the workflow when it completes, and then enter guesses until the game is complete.</span></span> <span data-ttu-id="c566b-177">`WriteLine` アクティビティに対する更新に基づき、ステータス ウィンドウに示される情報に、ユーザーの推定値がどのように表示されるかを確認します。</span><span class="sxs-lookup"><span data-stu-id="c566b-177">Note how the user's guess is displayed in the information displayed in the status window based on the updates to the `WriteLine` activities.</span></span>

 **<span data-ttu-id="c566b-178">Please enter a number between 1 and 10</span><span class="sxs-lookup"><span data-stu-id="c566b-178">Please enter a number between 1 and 10</span></span>**  
**<span data-ttu-id="c566b-179">5 is too high.</span><span class="sxs-lookup"><span data-stu-id="c566b-179">5 is too high.</span></span>**  
**<span data-ttu-id="c566b-180">Please enter a number between 1 and 10</span><span class="sxs-lookup"><span data-stu-id="c566b-180">Please enter a number between 1 and 10</span></span>**  
**<span data-ttu-id="c566b-181">3 is too high.</span><span class="sxs-lookup"><span data-stu-id="c566b-181">3 is too high.</span></span>**  
**<span data-ttu-id="c566b-182">Please enter a number between 1 and 10</span><span class="sxs-lookup"><span data-stu-id="c566b-182">Please enter a number between 1 and 10</span></span>**  
**<span data-ttu-id="c566b-183">1 is too low.</span><span class="sxs-lookup"><span data-stu-id="c566b-183">1 is too low.</span></span>**  
**<span data-ttu-id="c566b-184">Please enter a number between 1 and 10</span><span class="sxs-lookup"><span data-stu-id="c566b-184">Please enter a number between 1 and 10</span></span>**  
**<span data-ttu-id="c566b-185">Congratulations, you guessed the number in 4 turns.</span><span class="sxs-lookup"><span data-stu-id="c566b-185">Congratulations, you guessed the number in 4 turns.</span></span>**  

    > [!NOTE]
    >  <span data-ttu-id="c566b-186">`WriteLine` アクティビティから更新されたテキストは表示されますが、このトピックで追加された最後の `WriteLine` アクティビティの出力は表示されません。</span><span class="sxs-lookup"><span data-stu-id="c566b-186">The updated text from the `WriteLine` activities is displayed, but the output of the final `WriteLine` activity that was added in this topic is not.</span></span> <span data-ttu-id="c566b-187">これは、ステータス ウィンドウが `PersistableIdle` ハンドラーによって更新されるためです。</span><span class="sxs-lookup"><span data-stu-id="c566b-187">That is because the status window is updated by the `PersistableIdle` handler.</span></span> <span data-ttu-id="c566b-188">ワークフローは完了し、最後のアクティビティの後にアイドル状態にならないため、`PersistableIdle` ハンドラーは呼び出されません。</span><span class="sxs-lookup"><span data-stu-id="c566b-188">Because the workflow completes and does not go idle after the final activity, the `PersistableIdle` handler is not called.</span></span> <span data-ttu-id="c566b-189">ただし、`Completed` ハンドラーによって同様のメッセージがステータス ウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="c566b-189">However, a similar message is displayed in the status window by the `Completed` handler.</span></span> <span data-ttu-id="c566b-190">必要に応じて、コードを `Completed` ハンドラーに追加し、`StringWriter` からテキストを抽出してステータス ウィンドウに表示できます。</span><span class="sxs-lookup"><span data-stu-id="c566b-190">If desired, code could be added to the `Completed` handler to extract the text from the `StringWriter` and display it to the status window.</span></span>

3. <span data-ttu-id="c566b-191">Windows エクスプ ローラーを開きに移動、 **numberguessworkflowhost \bin\debug**フォルダー (または**bin \release**プロジェクトの設定によって) と、対応するメモ帳を使用して追跡ファイルを開く完了したワークフロー。</span><span class="sxs-lookup"><span data-stu-id="c566b-191">Open Windows Explorer and navigate to the **NumberGuessWorkflowHost\bin\debug** folder (or **bin\release** depending on your project settings) and open the tracking file using Notepad that corresponds to the completed workflow.</span></span> <span data-ttu-id="c566b-192">メモして行っていない場合、`InstanceId`を使用して正しい追跡ファイルを識別する、**に変更された日付**Windows エクスプ ローラーの情報。</span><span class="sxs-lookup"><span data-stu-id="c566b-192">If you did not make a note of the `InstanceId`, you can identify the correct tracking file by using the **Date modified** information in Windows Explorer.</span></span>

 <span data-ttu-id="c566b-193">**1 から 10 までの数値を入力してください**
**5 が多すぎます**。
 **1 から 10 までの数値を入力してください**
**3 が多すぎます**。
 **1 から 10 までの数値を入力してください**
**1 が小さすぎます**。
 **1 から 10 までの数値を入力してください**
**2 が正しい。察しのように 4 になります。**</span><span class="sxs-lookup"><span data-stu-id="c566b-193">**Please enter a number between 1 and 10**
**5 is too high.**
**Please enter a number between 1 and 10**
**3 is too high.**
**Please enter a number between 1 and 10**
**1 is too low.**
**Please enter a number between 1 and 10**
**2 is correct. You guessed it in 4 turns.**</span></span>      <span data-ttu-id="c566b-194">更新された `WriteLine` の出力は、このトピックで追加した `WriteLine` の出力を含む追跡ファイル内に含まれています。</span><span class="sxs-lookup"><span data-stu-id="c566b-194">The updated `WriteLine` output is contained within the tracking file, including the output of the `WriteLine` that was added in this topic.</span></span>

4. <span data-ttu-id="c566b-195">数値推測アプリケーションに戻り、更新が行われる前に開始したワークフローのうち 1 つを選択します。</span><span class="sxs-lookup"><span data-stu-id="c566b-195">Switch back to the number guessing application and select one of the workflows that was started before the updates were made.</span></span> <span data-ttu-id="c566b-196">現在選択されているワークフローのバージョンを特定するには、ステータス ウィンドウの下に表示されるバージョン情報を確認します。</span><span class="sxs-lookup"><span data-stu-id="c566b-196">You can identify the version of the currently selected workflow by looking at the version information that is displayed below the status window.</span></span> <span data-ttu-id="c566b-197">いくつかの推定値を入力し、ステータスの更新が前のバージョンからの `WriteLine` アクティビティの出力と一致しており、ユーザーの推定値が含まれていないことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="c566b-197">Enter some guesses and note that the status updates match the `WriteLine` activity output from the previous version, and do not include the user's guess.</span></span> <span data-ttu-id="c566b-198">これらのワークフローでは、`WriteLine` の更新を含まない以前のワークフロー定義を使用しているためです。</span><span class="sxs-lookup"><span data-stu-id="c566b-198">That is because these workflows are using the previous workflow definition that does not have the `WriteLine` updates.</span></span>

     <span data-ttu-id="c566b-199">次の手順で[方法。実行しているワークフロー インスタンスの定義を更新](how-to-update-the-definition-of-a-running-workflow-instance.md)、実行`v1`ワークフロー インスタンスが更新されるは、新しい機能が含まれているため、`v2`インスタンス。</span><span class="sxs-lookup"><span data-stu-id="c566b-199">In the next step, [How to: Update the Definition of a Running Workflow Instance](how-to-update-the-definition-of-a-running-workflow-instance.md), the running `v1` workflow instances are updated so they contain the new functionality as the `v2` instances.</span></span>
