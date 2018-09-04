---
title: '方法: ステート マシン ワークフローを作成する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 3ec60e8f-fad4-493e-a426-e7962d7aee8c
ms.openlocfilehash: 8098ab4b056ad6375c248e803134c35d67e3f27b
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "43519822"
---
# <a name="how-to-create-a-state-machine-workflow"></a><span data-ttu-id="a53dd-102">方法: ステート マシン ワークフローを作成する</span><span class="sxs-lookup"><span data-stu-id="a53dd-102">How to: Create a State Machine Workflow</span></span>
<span data-ttu-id="a53dd-103">ワークフローは、ビルトイン アクティビティおよびカスタム アクティビティから構築できます。</span><span class="sxs-lookup"><span data-stu-id="a53dd-103">Workflows can be constructed from built-in activities as well as from custom activities.</span></span> <span data-ttu-id="a53dd-104">など両方の組み込みのアクティビティを使用するワークフローを作成する手順をこのトピックで、<xref:System.Activities.Statements.StateMachine>アクティビティ、およびカスタム アクティビティ、前の[方法: アクティビティ作成](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md)トピック。</span><span class="sxs-lookup"><span data-stu-id="a53dd-104">This topic steps through creating a workflow that uses both built-in activities such as the <xref:System.Activities.Statements.StateMachine> activity, and the custom activities from the previous [How to: Create an Activity](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md) topic.</span></span> <span data-ttu-id="a53dd-105">このワークフローは、数値推測ゲームをモデル化しています。</span><span class="sxs-lookup"><span data-stu-id="a53dd-105">The workflow models a number guessing game.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a53dd-106">チュートリアル入門の各トピックは、前のトピックに応じて異なります。</span><span class="sxs-lookup"><span data-stu-id="a53dd-106">Each topic in the Getting Started tutorial depends on the previous topics.</span></span> <span data-ttu-id="a53dd-107">このトピックを完了する必要がありますを完了して[方法: アクティビティ作成](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md)です。</span><span class="sxs-lookup"><span data-stu-id="a53dd-107">To complete this topic, you must first complete [How to: Create an Activity](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a53dd-108">このチュートリアルの完成版をダウンロードするを参照してください。 [Windows Workflow Foundation (WF45) - チュートリアル入門](https://go.microsoft.com/fwlink/?LinkID=248976)します。</span><span class="sxs-lookup"><span data-stu-id="a53dd-108">To download a completed version of the tutorial, see [Windows Workflow Foundation (WF45) - Getting Started Tutorial](https://go.microsoft.com/fwlink/?LinkID=248976).</span></span>  
  
### <a name="to-create-the-workflow"></a><span data-ttu-id="a53dd-109">ワークフローを作成するには</span><span class="sxs-lookup"><span data-stu-id="a53dd-109">To create the workflow</span></span>  
  
1.  <span data-ttu-id="a53dd-110">右クリック**NumberGuessWorkflowActivities**で**ソリューション エクスプ ローラー**選択**追加**、**新しい項目の**します。</span><span class="sxs-lookup"><span data-stu-id="a53dd-110">Right-click **NumberGuessWorkflowActivities** in **Solution Explorer** and select **Add**, **New Item**.</span></span>  
  
2.  <span data-ttu-id="a53dd-111">**インストール済み**、**一般的な項目**ノードの **ワークフロー**します。</span><span class="sxs-lookup"><span data-stu-id="a53dd-111">In the **Installed**, **Common Items** node, select **Workflow**.</span></span> <span data-ttu-id="a53dd-112">選択**アクティビティ**から、**ワークフロー**一覧。</span><span class="sxs-lookup"><span data-stu-id="a53dd-112">Select **Activity** from the **Workflow** list.</span></span>  
  
3.  <span data-ttu-id="a53dd-113">型`StateMachineNumberGuessWorkflow`に、**名前**ボックスし、をクリックして**追加**します。</span><span class="sxs-lookup"><span data-stu-id="a53dd-113">Type `StateMachineNumberGuessWorkflow` into the **Name** box and click **Add**.</span></span>  
  
4.  <span data-ttu-id="a53dd-114">ドラッグ、 **StateMachine**からのアクティビティ、**ステート マシン**のセクション、**ツールボックス**にドロップし、**ここにアクティビティをドロップ**のラベルをワークフロー デザイン サーフェイス。</span><span class="sxs-lookup"><span data-stu-id="a53dd-114">Drag a **StateMachine** activity from the **State Machine** section of the **Toolbox** and drop it onto the **Drop activity here** label on the workflow design surface.</span></span>  
  
### <a name="to-create-the-workflow-variables-and-arguments"></a><span data-ttu-id="a53dd-115">ワークフロー変数および引数を作成するには</span><span class="sxs-lookup"><span data-stu-id="a53dd-115">To create the workflow variables and arguments</span></span>  
  
1.  <span data-ttu-id="a53dd-116">ダブルクリック**StateMachineNumberGuessWorkflow.xaml**で**ソリューション エクスプ ローラー**まだ表示されていない場合に、デザイナーでワークフローを表示します。</span><span class="sxs-lookup"><span data-stu-id="a53dd-116">Double-click **StateMachineNumberGuessWorkflow.xaml** in **Solution Explorer** to display the workflow in the designer, if it is not already displayed.</span></span>  
  
2.  <span data-ttu-id="a53dd-117">クリックして**引数**を表示するワークフロー デザイナーの左下で、**引数**ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="a53dd-117">Click **Arguments** in the lower-left side of the workflow designer to display the **Arguments** pane.</span></span>  
  
3.  <span data-ttu-id="a53dd-118">クリックして**引数の作成**です。</span><span class="sxs-lookup"><span data-stu-id="a53dd-118">Click **Create Argument**.</span></span>  
  
4.  <span data-ttu-id="a53dd-119">型`MaxNumber`に、**名前**ボックスで、**で**から、**方向**ドロップダウン リストで、 **Int32** から**引数の型**ドロップダウン リスト、および引数を保存するには ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="a53dd-119">Type `MaxNumber` into the **Name** box, select **In** from the **Direction** drop-down list, select **Int32** from the **Argument type** drop-down list, and then press ENTER to save the argument.</span></span>  
  
5.  <span data-ttu-id="a53dd-120">クリックして**引数の作成**です。</span><span class="sxs-lookup"><span data-stu-id="a53dd-120">Click **Create Argument**.</span></span>  
  
6.  <span data-ttu-id="a53dd-121">型`Turns`に、**名前**新しく追加された下にあるボックス`MaxNumber`引数で、**アウト**から、**方向**選択ドロップダウンリスト**Int32**から、**引数の型**ドロップダウン リスト、および ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="a53dd-121">Type `Turns` into the **Name** box that is below the newly added `MaxNumber` argument, select **Out** from the **Direction** drop-down list, select **Int32** from the **Argument type** drop-down list, and then press ENTER.</span></span>  
  
7.  <span data-ttu-id="a53dd-122">クリックして**引数**を閉じるアクティビティ デザイナーの左下で、**引数**ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="a53dd-122">Click **Arguments** in the lower-left side of the activity designer to close the **Arguments** pane.</span></span>  
  
8.  <span data-ttu-id="a53dd-123">クリックして**変数**を表示するワークフロー デザイナーの左下で、**変数**ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="a53dd-123">Click **Variables** in the lower-left side of the workflow designer to display the **Variables** pane.</span></span>  
  
9. <span data-ttu-id="a53dd-124">クリックして**変数作成**です。</span><span class="sxs-lookup"><span data-stu-id="a53dd-124">Click **Create Variable**.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="a53dd-125">ない場合は**変数の作成**ボックスが表示されたら、をクリックして、<xref:System.Activities.Statements.StateMachine>ことを選択するには、ワークフロー デザイナー画面上のアクティビティ。</span><span class="sxs-lookup"><span data-stu-id="a53dd-125">If no **Create Variable** box is displayed, click the <xref:System.Activities.Statements.StateMachine> activity on the workflow designer surface to select it.</span></span>  
  
10. <span data-ttu-id="a53dd-126">型`Guess`に、**名前**ボックスで、 **Int32**から、**変数の型**ドロップダウン リスト、および、変数に保存するには ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="a53dd-126">Type `Guess` into the **Name** box, select **Int32** from the **Variable type** drop-down list, and then press ENTER to save the variable.</span></span>  
  
11. <span data-ttu-id="a53dd-127">クリックして**変数作成**です。</span><span class="sxs-lookup"><span data-stu-id="a53dd-127">Click **Create Variable**.</span></span>  
  
12. <span data-ttu-id="a53dd-128">型`Target`に、**名前**ボックスで、 **Int32**から、**変数の型**ドロップダウン リスト、および、変数に保存するには ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="a53dd-128">Type `Target` into the **Name** box, select **Int32** from the **Variable type** drop-down list, and then press ENTER to save the variable.</span></span>  
  
13. <span data-ttu-id="a53dd-129">クリックして**変数**を閉じるアクティビティ デザイナーの左下で、**変数**ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="a53dd-129">Click **Variables** in the lower-left side of the activity designer to close the **Variables** pane.</span></span>  
  
### <a name="to-add-the-workflow-activities"></a><span data-ttu-id="a53dd-130">ワークフロー アクティビティを追加するには</span><span class="sxs-lookup"><span data-stu-id="a53dd-130">To add the workflow activities</span></span>  
  
1.  <span data-ttu-id="a53dd-131">クリックして**State1**をオンにします。</span><span class="sxs-lookup"><span data-stu-id="a53dd-131">Click **State1** to select it.</span></span> <span data-ttu-id="a53dd-132">**プロパティ ウィンドウ**、変更、 **DisplayName**に`Initialize Target`します。</span><span class="sxs-lookup"><span data-stu-id="a53dd-132">In the **Properties Window**, change the **DisplayName** to `Initialize Target`.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="a53dd-133">場合、**プロパティ ウィンドウ**が表示されている、選択**プロパティ ウィンドウ**から、**ビュー**メニュー。</span><span class="sxs-lookup"><span data-stu-id="a53dd-133">If the **Properties Window** is not displayed, select **Properties Window** from the **View** menu.</span></span>  
  
2.  <span data-ttu-id="a53dd-134">新しく名前を変更 をダブルクリックします**Initialize Target**ワークフロー デザイナーの展開の状態。</span><span class="sxs-lookup"><span data-stu-id="a53dd-134">Double-click the newly renamed **Initialize Target** state in the workflow designer to expand it.</span></span>  
  
3.  <span data-ttu-id="a53dd-135">ドラッグ、**割り当てる**からのアクティビティ、**プリミティブ**のセクション、**ツールボックス**にドロップし、**エントリ**状態のセクション。</span><span class="sxs-lookup"><span data-stu-id="a53dd-135">Drag an **Assign** activity from the **Primitives** section of the **Toolbox** and drop it onto the **Entry** section of the state.</span></span> <span data-ttu-id="a53dd-136">型`Target`に、**に**ボックスし、次の式を**c# 式を入力します**または**VB の式を入力します。** ボックス。</span><span class="sxs-lookup"><span data-stu-id="a53dd-136">Type `Target` into the **To** box and the following expression into the **Enter a C# expression** or **Enter a VB expression** box.</span></span>  
  
    ```vb  
    New System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    ```csharp  
    new System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    > [!TIP]
    >  <span data-ttu-id="a53dd-137">場合、**ツールボックス**ウィンドウが表示されない場合、選択**ツールボックス**から、**ビュー**メニュー。</span><span class="sxs-lookup"><span data-stu-id="a53dd-137">If the **Toolbox** window is not displayed, select **Toolbox** from the **View** menu.</span></span>  
  
4.  <span data-ttu-id="a53dd-138">全体に戻る をクリックして状態マシン ビューは、ワークフロー デザイナーに**StateMachine**階層リンクで、ワークフロー デザイナーの上部に表示します。</span><span class="sxs-lookup"><span data-stu-id="a53dd-138">Return to the overall state machine view in the workflow designer by clicking **StateMachine** in the breadcrumb display at the top of the workflow designer.</span></span>  
  
5.  <span data-ttu-id="a53dd-139">ドラッグ、**状態**からのアクティビティ、**ステート マシン**のセクション、**ツールボックス**ワークフロー デザイナーにそのポインターを合わせると、 **Initialize Target**状態。</span><span class="sxs-lookup"><span data-stu-id="a53dd-139">Drag a **State** activity from the **State Machine** section of the **Toolbox** onto the workflow designer and hover it over the **Initialize Target** state.</span></span> <span data-ttu-id="a53dd-140">周囲に 4 つの三角形が表示されることに注意してください、 **Initialize Target**新しい状態が上にあるときの状態。</span><span class="sxs-lookup"><span data-stu-id="a53dd-140">Note that four triangles will appear around the **Initialize Target** state when the new state is over it.</span></span> <span data-ttu-id="a53dd-141">すぐ下にある三角形の新しい状態をドロップ、 **Initialize Target**状態。</span><span class="sxs-lookup"><span data-stu-id="a53dd-141">Drop the new state on the triangle that is immediately below the **Initialize Target** state.</span></span> <span data-ttu-id="a53dd-142">これは、ワークフローの新しい状態しからの移行を作成、 **Initialize Target**新しい状態を状態。</span><span class="sxs-lookup"><span data-stu-id="a53dd-142">This places the new state onto the workflow and creates a transition from the **Initialize Target** state to the new state.</span></span>  
  
6.  <span data-ttu-id="a53dd-143">をクリックして**State1**ことを選択するには、変更、 **DisplayName**に`Enter Guess`、ワークフロー デザイナーの展開の状態をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="a53dd-143">Click **State1** to select it, change the **DisplayName** to `Enter Guess`, and then double-click the state in the workflow designer to expand it.</span></span>  
  
7.  <span data-ttu-id="a53dd-144">ドラッグ、 **WriteLine**からのアクティビティ、**プリミティブ**のセクション、**ツールボックス**にドロップし、**エントリ**状態のセクション。</span><span class="sxs-lookup"><span data-stu-id="a53dd-144">Drag a **WriteLine** activity from the **Primitives** section of the **Toolbox** and drop it onto the **Entry** section of the state.</span></span>  
  
8.  <span data-ttu-id="a53dd-145">次の式を入力、**テキスト**プロパティ ボックスの**WriteLine**します。</span><span class="sxs-lookup"><span data-stu-id="a53dd-145">Type the following expression into the **Text** property box of the **WriteLine**.</span></span>  
  
    ```vb  
    "Please enter a number between 1 and " & MaxNumber  
    ```  
  
    ```csharp  
    "Please enter a number between 1 and " + MaxNumber  
    ```  
  
9. <span data-ttu-id="a53dd-146">ドラッグ、**割り当てる**からのアクティビティ、**プリミティブ**のセクション、**ツールボックス**にドロップし、**終了**状態のセクション。</span><span class="sxs-lookup"><span data-stu-id="a53dd-146">Drag an **Assign** activity from the **Primitives** section of the **Toolbox** and drop onto the **Exit** section of the state.</span></span>  
  
10. <span data-ttu-id="a53dd-147">型`Turns`に、**に**ボックスと`Turns + 1`に、 **c# 式を入力します**または**VB の式を入力します。** ボックス。</span><span class="sxs-lookup"><span data-stu-id="a53dd-147">Type `Turns` into the **To** box and `Turns + 1` into the **Enter a C# expression** or **Enter a VB expression** box.</span></span>  
  
11. <span data-ttu-id="a53dd-148">全体に戻る をクリックして状態マシン ビューは、ワークフロー デザイナーに**StateMachine**階層リンクで、ワークフロー デザイナーの上部に表示します。</span><span class="sxs-lookup"><span data-stu-id="a53dd-148">Return to the overall state machine view in the workflow designer by clicking **StateMachine** in the breadcrumb display at the top of the workflow designer.</span></span>  
  
12. <span data-ttu-id="a53dd-149">ドラッグ、 **FinalState**からのアクティビティ、**ステート マシン**のセクション、**ツールボックス**、上にマウス ポインター、 **Enter Guess**状態、および削除右側に表示される三角形に、 **Enter Guess**状態間の遷移が作成されるように**Enter Guess**と**FinalState**します。</span><span class="sxs-lookup"><span data-stu-id="a53dd-149">Drag a **FinalState** activity from the **State Machine** section of the **Toolbox**, hover it over the **Enter Guess** state, and drop it onto the triangle that appears to the right of the **Enter Guess** state so that a transition is created between **Enter Guess** and **FinalState**.</span></span>  
  
13. <span data-ttu-id="a53dd-150">遷移の既定の名前は**T2**します。</span><span class="sxs-lookup"><span data-stu-id="a53dd-150">The default name of the transition is **T2**.</span></span> <span data-ttu-id="a53dd-151">それを選択し、設定するには、ワークフロー デザイナーで遷移をクリックします。 その**DisplayName**に**Guess Correct**します。</span><span class="sxs-lookup"><span data-stu-id="a53dd-151">Click the transition in the workflow designer to select it, and set its **DisplayName** to **Guess Correct**.</span></span> <span data-ttu-id="a53dd-152">クリックし、選択、 **FinalState**、2 つの状態のどちらにも重ならずに表示される完全な遷移名用の空きができるように、右にドラッグします。</span><span class="sxs-lookup"><span data-stu-id="a53dd-152">Then click and select the **FinalState**, and drag it to the right so that there is room for the full transition name to be displayed without overlaying either of the two states.</span></span> <span data-ttu-id="a53dd-153">これにより、チュートリアルの残りの手順をより簡単に実行できます。</span><span class="sxs-lookup"><span data-stu-id="a53dd-153">This will make it easier to complete the remaining steps in the tutorial.</span></span>  
  
14. <span data-ttu-id="a53dd-154">新しく名前を変更 をダブルクリックします**Guess Correct**して展開ワークフロー デザイナーで遷移します。</span><span class="sxs-lookup"><span data-stu-id="a53dd-154">Double-click the newly renamed **Guess Correct** transition in the workflow designer to expand it.</span></span>  
  
15. <span data-ttu-id="a53dd-155">ドラッグ、 **ReadInt**からのアクティビティ、 **NumberGuessWorkflowActivities**のセクション、**ツールボックス**にドロップし、**トリガー**セクション移行。</span><span class="sxs-lookup"><span data-stu-id="a53dd-155">Drag a **ReadInt** activity from the **NumberGuessWorkflowActivities** section of the **Toolbox** and drop it in the **Trigger** section of the transition.</span></span>  
  
16. <span data-ttu-id="a53dd-156">**プロパティ ウィンドウ**の**ReadInt**アクティビティで、「`"EnterGuess"`に引用符を含む、 **BookmarkName**プロパティ値ボックス、および種類`Guess`に、**結果**プロパティ値ボックス</span><span class="sxs-lookup"><span data-stu-id="a53dd-156">In the **Properties Window** for the **ReadInt** activity, type `"EnterGuess"` including the quotes into the **BookmarkName** property value box, and type `Guess` into the **Result** property value box</span></span>  
  
17. <span data-ttu-id="a53dd-157">次の式を入力、 **Guess Correct**遷移の**条件**プロパティ値ボックス。</span><span class="sxs-lookup"><span data-stu-id="a53dd-157">Type the following expression into the **Guess Correct** transition’s **Condition** property value box.</span></span>  
  
    ```vb  
    Guess = Target  
    ```  
  
    ```csharp  
    Guess == Target  
    ```  
  
18. <span data-ttu-id="a53dd-158">全体に戻る をクリックして状態マシン ビューは、ワークフロー デザイナーに**StateMachine**階層リンクで、ワークフロー デザイナーの上部に表示します。</span><span class="sxs-lookup"><span data-stu-id="a53dd-158">Return to the overall state machine view in the workflow designer by clicking **StateMachine** in the breadcrumb display at the top of the workflow designer.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a53dd-159">トリガー イベントが受け取られ、<xref:System.Activities.Statements.Transition.Condition%2A> (存在する場合) が `True` と評価される場合に遷移が発生します。</span><span class="sxs-lookup"><span data-stu-id="a53dd-159">A transition occurs when the trigger event is received and the <xref:System.Activities.Statements.Transition.Condition%2A>, if present, evaluates to `True`.</span></span> <span data-ttu-id="a53dd-160">この遷移で場合、ユーザーの`Guess`ランダムに生成されたと一致する`Target`に制御が渡されます。 その後、 **FinalState** 、ワークフローが完了するとします。</span><span class="sxs-lookup"><span data-stu-id="a53dd-160">For this transition, if the user’s `Guess` matches the randomly generated `Target`, then control passes to the **FinalState** and the workflow completes.</span></span>  
  
19. <span data-ttu-id="a53dd-161">推定値が正しいかどうか、によって、ワークフローが遷移するか、 **FinalState**またはに戻す、 **Enter Guess**もう一度実行状態。</span><span class="sxs-lookup"><span data-stu-id="a53dd-161">Depending on whether the guess is correct, the workflow should transition either to the **FinalState** or back to the **Enter Guess** state for another try.</span></span> <span data-ttu-id="a53dd-162">両方の遷移は、ユーザーの推定値経由で受信を待機するのと同じトリガーを共有、 **ReadInt**アクティビティ。</span><span class="sxs-lookup"><span data-stu-id="a53dd-162">Both transitions share the same trigger of waiting for the user’s guess to be received via the **ReadInt** activity.</span></span> <span data-ttu-id="a53dd-163">これは、共有遷移と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="a53dd-163">This is called a shared transition.</span></span> <span data-ttu-id="a53dd-164">共有遷移を作成するには、開始を示す円をクリックします。、 **Guess Correct**移行し、目的の状態にドラッグします。</span><span class="sxs-lookup"><span data-stu-id="a53dd-164">To create a shared transition, click the circle that indicates the start of the **Guess Correct** transition and drag it to the desired state.</span></span> <span data-ttu-id="a53dd-165">自己の遷移を遷移がここでは、そのための開始点をドラッグ、 **Guess Correct**の一番下にドロップしつつ、移行、 **Enter Guess**状態。</span><span class="sxs-lookup"><span data-stu-id="a53dd-165">In this case the transition is a self-transition, so drag the start point of the **Guess Correct** transition and drop it back onto the bottom of the **Enter Guess** state.</span></span> <span data-ttu-id="a53dd-166">遷移を作成した後、ワークフロー デザイナーで選択し、設定、 **DisplayName**プロパティを**Guess Incorrect**します。</span><span class="sxs-lookup"><span data-stu-id="a53dd-166">After creating the transition, select it in the workflow designer and set its **DisplayName** property to **Guess Incorrect**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a53dd-167">共有遷移も作成できますから、遷移デザイナー内をクリックして**追加共有トリガー遷移**から目的のターゲットの状態を選択し、遷移デザイナーの下部にある、 **使用可能な状態の接続に**ドロップダウンします。</span><span class="sxs-lookup"><span data-stu-id="a53dd-167">Shared transitions can also be created from within the transition designer by clicking **Add shared trigger transition** at the bottom of the transition designer, and then selecting the desired target state from the **Available states to connect** drop-down.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a53dd-168">遷移の <xref:System.Activities.Statements.Transition.Condition%2A> が `false` と評価された場合 (またはトリガーを共有する遷移すべての状態が `false` と評価された場合)、遷移は行われず、その状態からのすべての遷移のすべてのトリガーが再スケジュールされます。</span><span class="sxs-lookup"><span data-stu-id="a53dd-168">Note that if the <xref:System.Activities.Statements.Transition.Condition%2A> of a transition evaluates to `false` (or all of the conditions of a shared trigger transition evaluate to `false`), the transition will not occur and all triggers for all the transitions from the state will be rescheduled.</span></span> <span data-ttu-id="a53dd-169">このチュートリアルでは、条件の構成方法 (推定値が正しいか間違っているかを判断する特定のアクションが用意されています) により、この状況は発生しません。</span><span class="sxs-lookup"><span data-stu-id="a53dd-169">In this tutorial, this situation cannot happen because of the way the conditions are configured (we have specific actions for whether the guess is correct or incorrect).</span></span>  
  
20. <span data-ttu-id="a53dd-170">ダブルクリックして、 **Guess Incorrect**して展開ワークフロー デザイナーで遷移します。</span><span class="sxs-lookup"><span data-stu-id="a53dd-170">Double-click the **Guess Incorrect** transition in the workflow designer to expand it.</span></span> <span data-ttu-id="a53dd-171">なお、**トリガー**は既に同じに設定**ReadInt**アクティビティで使用された、 **Guess Correct**遷移します。</span><span class="sxs-lookup"><span data-stu-id="a53dd-171">Note that the **Trigger** is already set to the same **ReadInt** activity that was used by the **Guess Correct** transition.</span></span>  
  
21. <span data-ttu-id="a53dd-172">次の式を入力、**条件**プロパティ値ボックス。</span><span class="sxs-lookup"><span data-stu-id="a53dd-172">Type the following expression into the **Condition** property value box.</span></span>  
  
    ```vb  
    Guess <> Target  
    ```  
  
    ```csharp  
    Guess != Target  
    ```  
  
22. <span data-ttu-id="a53dd-173">ドラッグ、**場合**からのアクティビティ、**制御フロー**のセクション、**ツールボックス**にドロップし、**アクション**遷移のセクション。</span><span class="sxs-lookup"><span data-stu-id="a53dd-173">Drag an **If** activity from the **Control Flow** section of the **Toolbox** and drop it in the **Action** section of the transition.</span></span>  
  
23. <span data-ttu-id="a53dd-174">次の式を入力、**場合**アクティビティの**条件**プロパティ値ボックス。</span><span class="sxs-lookup"><span data-stu-id="a53dd-174">Type the following expression into the **If** activity’s **Condition** property value box.</span></span>  
  
    ```
    Guess < Target  
    ```  
  
24. <span data-ttu-id="a53dd-175">2 つをドラッグして**WriteLine**アクティビティから、**プリミティブ**のセクション、**ツールボックス**で 1 つがされるようにドロップし、**し**のセクション**場合**、もう 1 つは、 **Else**セクション。</span><span class="sxs-lookup"><span data-stu-id="a53dd-175">Drag two **WriteLine** activities from the **Primitives** section of the **Toolbox** and drop them so that one is in the **Then** section of the **If** activity, and one is in the **Else** section.</span></span>  
  
25. <span data-ttu-id="a53dd-176">をクリックして、 **WriteLine**内のアクティビティ、**し**セクションを選択しとには、次の式を入力、**テキスト**プロパティ値ボックス。</span><span class="sxs-lookup"><span data-stu-id="a53dd-176">Click the **WriteLine** activity in the **Then** section to select it, and type the following expression into the **Text** property value box.</span></span>  
  
    ```
    "Your guess is too low."  
    ```  
  
26. <span data-ttu-id="a53dd-177">をクリックして、 **WriteLine**内のアクティビティ、 **Else**セクションを選択しとには、次の式を入力、**テキスト**プロパティ値ボックス。</span><span class="sxs-lookup"><span data-stu-id="a53dd-177">Click the **WriteLine** activity in the **Else** section to select it, and type the following expression into the **Text** property value box.</span></span>  
  
    ```
    "Your guess is too high."  
    ```  
  
27. <span data-ttu-id="a53dd-178">全体に戻る をクリックして状態マシン ビューは、ワークフロー デザイナーに**StateMachine**階層リンクで、ワークフロー デザイナーの上部に表示します。</span><span class="sxs-lookup"><span data-stu-id="a53dd-178">Return to the overall state machine view in the workflow designer by clicking **StateMachine** in the breadcrumb display at the top of the workflow designer.</span></span>  
  
     <span data-ttu-id="a53dd-179">次の例は完成したワークフローを示しています。</span><span class="sxs-lookup"><span data-stu-id="a53dd-179">The following example illustrates the completed workflow.</span></span>  
  
     <span data-ttu-id="a53dd-180">![完成したステート マシン ワークフロー](../../../docs/framework/windows-workflow-foundation/media/wfstatemachinegettingstartedtutorialcomplete.JPG "WFStateMachineGettingStartedTutorialComplete")</span><span class="sxs-lookup"><span data-stu-id="a53dd-180">![Completed State Machine Workflow](../../../docs/framework/windows-workflow-foundation/media/wfstatemachinegettingstartedtutorialcomplete.JPG "WFStateMachineGettingStartedTutorialComplete")</span></span>  
  
### <a name="to-build-the-workflow"></a><span data-ttu-id="a53dd-181">ワークフローをビルドするには</span><span class="sxs-lookup"><span data-stu-id="a53dd-181">To build the workflow</span></span>  
  
1.  <span data-ttu-id="a53dd-182">Ctrl キーと Shift キーを押しながら B キーを押して、ソリューションをビルドします。</span><span class="sxs-lookup"><span data-stu-id="a53dd-182">Press CTRL+SHIFT+B to build the solution.</span></span>  
  
     <span data-ttu-id="a53dd-183">ワークフローを実行する方法について、次のトピックをご覧ください[方法: ワークフローを実行する](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md)します。</span><span class="sxs-lookup"><span data-stu-id="a53dd-183">For instructions on how to run the workflow, please see the next topic, [How to: Run a Workflow](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md).</span></span> <span data-ttu-id="a53dd-184">既に完了している場合、[方法: ワークフローを実行する](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md)さまざまなスタイルのワークフロー ステップ、状態マシン ワークフローは、この手順を使用してを実行してに進んで、 [のアプリケーションをビルドして、実行](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md#BKMK_ToRunTheApplication)の[方法: ワークフローを実行する](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md)します。</span><span class="sxs-lookup"><span data-stu-id="a53dd-184">If you have already completed the [How to: Run a Workflow](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md) step with a different style of workflow and wish to run it using the state machine workflow from this step, skip ahead to the [To build and run the application](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md#BKMK_ToRunTheApplication) section of [How to: Run a Workflow](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a53dd-185">関連項目</span><span class="sxs-lookup"><span data-stu-id="a53dd-185">See Also</span></span>  
 <xref:System.Activities.Statements.Flowchart>  
 <xref:System.Activities.Statements.FlowDecision>  
 [<span data-ttu-id="a53dd-186">Windows Workflow Foundation プログラミング</span><span class="sxs-lookup"><span data-stu-id="a53dd-186">Windows Workflow Foundation Programming</span></span>](../../../docs/framework/windows-workflow-foundation/programming.md)  
 [<span data-ttu-id="a53dd-187">ワークフローの設計</span><span class="sxs-lookup"><span data-stu-id="a53dd-187">Designing Workflows</span></span>](../../../docs/framework/windows-workflow-foundation/designing-workflows.md)  
 [<span data-ttu-id="a53dd-188">チュートリアル入門</span><span class="sxs-lookup"><span data-stu-id="a53dd-188">Getting Started Tutorial</span></span>](../../../docs/framework/windows-workflow-foundation/getting-started-tutorial.md)  
 [<span data-ttu-id="a53dd-189">アクティビティを作成する方法</span><span class="sxs-lookup"><span data-stu-id="a53dd-189">How to: Create an Activity</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md)  
 [<span data-ttu-id="a53dd-190">ワークフローを実行する方法</span><span class="sxs-lookup"><span data-stu-id="a53dd-190">How to: Run a Workflow</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md)
