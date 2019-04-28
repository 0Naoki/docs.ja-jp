---
title: Visual Studio (Visual Basic) で式ツリーのデバッグ
ms.date: 07/20/2015
ms.assetid: 492cc28f-b7a2-4c47-b582-b3c437b8a5d5
ms.openlocfilehash: fb5905c3c1124dd64371216bddda0a17235abdce
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61787193"
---
# <a name="debugging-expression-trees-in-visual-studio-visual-basic"></a><span data-ttu-id="d9e8f-102">Visual Studio (Visual Basic) で式ツリーのデバッグ</span><span class="sxs-lookup"><span data-stu-id="d9e8f-102">Debugging Expression Trees in Visual Studio (Visual Basic)</span></span>

<span data-ttu-id="d9e8f-103">アプリケーションをデバッグするときに、式ツリーの構造および内容を分析できます。</span><span class="sxs-lookup"><span data-stu-id="d9e8f-103">You can analyze the structure and content of expression trees when you debug your applications.</span></span> <span data-ttu-id="d9e8f-104">式ツリーの構造を簡単に確認する場合は、`DebugView` プロパティを使用できます。このプロパティは、デバッグ モードでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="d9e8f-104">To get a quick overview of the expression tree structure, you can use the `DebugView` property, which is available only in debug mode.</span></span> <span data-ttu-id="d9e8f-105">デバッグの詳細については、「[Visual Studio でのデバッグ](/visualstudio/debugger/debugging-in-visual-studio)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d9e8f-105">For more information about debugging, see [Debugging in Visual Studio](/visualstudio/debugger/debugging-in-visual-studio).</span></span>

<span data-ttu-id="d9e8f-106">式ツリーの内容をわかりやすく表すために、`DebugView` プロパティでは Visual Studio ビジュアライザーを使用します。</span><span class="sxs-lookup"><span data-stu-id="d9e8f-106">To better represent the content of expression trees, the `DebugView` property uses Visual Studio visualizers.</span></span> <span data-ttu-id="d9e8f-107">詳細については、「[Create Custom Visualizers](/visualstudio/debugger/create-custom-visualizers-of-data)」 (カスタム ビジュアライザーを作成する) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d9e8f-107">For more information, see [Create Custom Visualizers](/visualstudio/debugger/create-custom-visualizers-of-data).</span></span>

### <a name="to-open-a-visualizer-for-an-expression-tree"></a><span data-ttu-id="d9e8f-108">式ツリーのビジュアライザーを開くには</span><span class="sxs-lookup"><span data-stu-id="d9e8f-108">To open a visualizer for an expression tree</span></span>

1. <span data-ttu-id="d9e8f-109">**[データヒント]**、**[ウォッチ]** ウィンドウ、**[自動変数]** ウィンドウ、または **[ローカル]** ウィンドウで、式ツリーの `DebugView` プロパティの横に表示されている虫眼鏡のアイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="d9e8f-109">Click the magnifying glass icon that appears next to the `DebugView` property of an expression tree in **DataTips**, a **Watch** window, the **Autos** window, or the **Locals** window.</span></span>

    <span data-ttu-id="d9e8f-110">ビジュアライザーの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d9e8f-110">A list of visualizers is displayed.</span></span>

2. <span data-ttu-id="d9e8f-111">使用するビジュアライザーをクリックします。</span><span class="sxs-lookup"><span data-stu-id="d9e8f-111">Click the visualizer you want to use.</span></span>

<span data-ttu-id="d9e8f-112">それぞれの式の型は、以下のセクションで説明するように、ビジュアライザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="d9e8f-112">Each expression type is displayed in the visualizer as described in the following sections.</span></span>

## <a name="parameterexpressions"></a><span data-ttu-id="d9e8f-113">ParameterExpressions</span><span class="sxs-lookup"><span data-stu-id="d9e8f-113">ParameterExpressions</span></span>

<span data-ttu-id="d9e8f-114"><xref:System.Linq.Expressions.ParameterExpression> 変数名は、先頭に記号 "$" を付けて表示されます。</span><span class="sxs-lookup"><span data-stu-id="d9e8f-114"><xref:System.Linq.Expressions.ParameterExpression> variable names are displayed with a "$" symbol at the beginning.</span></span>

<span data-ttu-id="d9e8f-115">パラメーターに名前がない場合、`$var1` や `$var2` など、自動的に生成された名前が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="d9e8f-115">If a parameter does not have a name, it is assigned an automatically generated name, such as `$var1` or `$var2`.</span></span>

### <a name="examples"></a><span data-ttu-id="d9e8f-116">使用例</span><span class="sxs-lookup"><span data-stu-id="d9e8f-116">Examples</span></span>

- `Expression`

    ```vb
    Dim numParam As ParameterExpression =
    Expression.Parameter(GetType(Integer), "num")
    ```

    <span data-ttu-id="d9e8f-117">`DebugView` プロパティ</span><span class="sxs-lookup"><span data-stu-id="d9e8f-117">`DebugView` property</span></span>

    `$num`

- `Expression`

    ```vb
    Dim numParam As ParameterExpression =
    Expression.Parameter(GetType(Integer))
    ```

    <span data-ttu-id="d9e8f-118">`DebugView` プロパティ</span><span class="sxs-lookup"><span data-stu-id="d9e8f-118">`DebugView` property</span></span>

    `$var1`

## <a name="constantexpressions"></a><span data-ttu-id="d9e8f-119">ConstantExpressions</span><span class="sxs-lookup"><span data-stu-id="d9e8f-119">ConstantExpressions</span></span>
 <span data-ttu-id="d9e8f-120">整数値、文字列、および `null` を表す <xref:System.Linq.Expressions.ConstantExpression> オブジェクトの場合、定数の値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d9e8f-120">For <xref:System.Linq.Expressions.ConstantExpression> objects that represent integer values, strings, and `null`, the value of the constant is displayed.</span></span>

### <a name="examples"></a><span data-ttu-id="d9e8f-121">使用例</span><span class="sxs-lookup"><span data-stu-id="d9e8f-121">Examples</span></span>

- `Expression`

    ```vb
    Dim num as Integer= 10
    Dim expr As ConstantExpression = Expression.Constant(num)
    ```

    <span data-ttu-id="d9e8f-122">`DebugView` プロパティ</span><span class="sxs-lookup"><span data-stu-id="d9e8f-122">`DebugView` property</span></span>

    <span data-ttu-id="d9e8f-123">10</span><span class="sxs-lookup"><span data-stu-id="d9e8f-123">10</span></span>

- `Expression`

    ```vb
    Dim num As Double = 10
    Dim expr As ConstantExpression = Expression.Constant(num)
    ```

    <span data-ttu-id="d9e8f-124">`DebugView` プロパティ</span><span class="sxs-lookup"><span data-stu-id="d9e8f-124">`DebugView` property</span></span>

    <span data-ttu-id="d9e8f-125">10D</span><span class="sxs-lookup"><span data-stu-id="d9e8f-125">10D</span></span>

## <a name="blockexpression"></a><span data-ttu-id="d9e8f-126">BlockExpression</span><span class="sxs-lookup"><span data-stu-id="d9e8f-126">BlockExpression</span></span>

<span data-ttu-id="d9e8f-127"><xref:System.Linq.Expressions.BlockExpression> オブジェクトの型が、ブロック内の最後の式の型と異なる場合、その型が `DebugInfo` プロパティに山かっこ (\< および >) で囲まれて表示されます。</span><span class="sxs-lookup"><span data-stu-id="d9e8f-127">If the type of a <xref:System.Linq.Expressions.BlockExpression> object differs from the type of the last expression in the block, the type is displayed in the `DebugInfo` property in angle brackets (\< and >).</span></span> <span data-ttu-id="d9e8f-128">それ以外の場合、<xref:System.Linq.Expressions.BlockExpression> オブジェクトの型は表示されません。</span><span class="sxs-lookup"><span data-stu-id="d9e8f-128">Otherwise, the type of the <xref:System.Linq.Expressions.BlockExpression> object is not displayed.</span></span>

### <a name="examples"></a><span data-ttu-id="d9e8f-129">使用例</span><span class="sxs-lookup"><span data-stu-id="d9e8f-129">Examples</span></span>

- `Expression`

    ```vb
    Dim block As BlockExpression = Expression.Block(Expression.Constant("test"))
    ```

    <span data-ttu-id="d9e8f-130">`DebugView` プロパティ</span><span class="sxs-lookup"><span data-stu-id="d9e8f-130">`DebugView` property</span></span>

    `.Block() {`

    `"test"`

    `}`

- `Expression`

    ```vb
    Dim block As BlockExpression =
    Expression.Block(GetType(Object), Expression.Constant("test"))
    ```

    <span data-ttu-id="d9e8f-131">`DebugView` プロパティ</span><span class="sxs-lookup"><span data-stu-id="d9e8f-131">`DebugView` property</span></span>

    `.Block<System.Object>() {`

    `"test"`

    `}`

## <a name="lambdaexpression"></a><span data-ttu-id="d9e8f-132">LambdaExpression</span><span class="sxs-lookup"><span data-stu-id="d9e8f-132">LambdaExpression</span></span>

<span data-ttu-id="d9e8f-133"><xref:System.Linq.Expressions.LambdaExpression> オブジェクトは、デリゲート型と共に表示されます。</span><span class="sxs-lookup"><span data-stu-id="d9e8f-133"><xref:System.Linq.Expressions.LambdaExpression> objects are displayed together with their delegate types.</span></span>

<span data-ttu-id="d9e8f-134">ラムダ式に名前がない場合、`#Lambda1` や `#Lambda2` など、自動的に生成された名前が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="d9e8f-134">If a lambda expression does not have a name, it is assigned an automatically generated name, such as `#Lambda1` or `#Lambda2`.</span></span>

### <a name="examples"></a><span data-ttu-id="d9e8f-135">使用例</span><span class="sxs-lookup"><span data-stu-id="d9e8f-135">Examples</span></span>

- `Expression`

    ```vb
    Dim lambda As LambdaExpression =
    Expression.Lambda(Of Func(Of Integer))(Expression.Constant(1))
    ```

    <span data-ttu-id="d9e8f-136">`DebugView` プロパティ</span><span class="sxs-lookup"><span data-stu-id="d9e8f-136">`DebugView` property</span></span>

    `.Lambda #Lambda1<System.Func'1[System.Int32]>() {`

    `1`

    `}`

- `Expression`

    ```vb
    Dim lambda As LambdaExpression =
    Expression.Lambda(Of Func(Of Integer))(Expression.Constant(1), "SampleLambda", Nothing)
    ```

    <span data-ttu-id="d9e8f-137">`DebugView` プロパティ</span><span class="sxs-lookup"><span data-stu-id="d9e8f-137">`DebugView` property</span></span>

    `.Lambda SampleLambda<System.Func'1[System.Int32]>() {`

    `1`

    `}`

## <a name="labelexpression"></a><span data-ttu-id="d9e8f-138">LabelExpression</span><span class="sxs-lookup"><span data-stu-id="d9e8f-138">LabelExpression</span></span>

<span data-ttu-id="d9e8f-139"><xref:System.Linq.Expressions.LabelExpression> オブジェクトの既定値を指定した場合、その値が <xref:System.Linq.Expressions.LabelTarget> オブジェクトの前に表示されます。</span><span class="sxs-lookup"><span data-stu-id="d9e8f-139">If you specify a default value for the <xref:System.Linq.Expressions.LabelExpression> object, this value is displayed before the <xref:System.Linq.Expressions.LabelTarget> object.</span></span>

<span data-ttu-id="d9e8f-140">`.Label` トークンは、ラベルの開始を示します。</span><span class="sxs-lookup"><span data-stu-id="d9e8f-140">The `.Label` token indicates the start of the label.</span></span> <span data-ttu-id="d9e8f-141">`.LabelTarget` トークンは、ジャンプ先のターゲットを示します。</span><span class="sxs-lookup"><span data-stu-id="d9e8f-141">The `.LabelTarget` token indicates the destination of the target to jump to.</span></span>

<span data-ttu-id="d9e8f-142">ラベルに名前がない場合、`#Label1` や `#Label2` など、自動的に生成された名前が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="d9e8f-142">If a label does not have a name, it is assigned an automatically generated name, such as `#Label1` or `#Label2`.</span></span>

### <a name="examples"></a><span data-ttu-id="d9e8f-143">使用例</span><span class="sxs-lookup"><span data-stu-id="d9e8f-143">Examples</span></span>

- `Expression`

    ```vb
    Dim target As LabelTarget = Expression.Label(GetType(Integer), "SampleLabel")
    Dim label1 As BlockExpression = Expression.Block(
    Expression.Goto(target, Expression.Constant(0)),
    Expression.Label(target, Expression.Constant(-1)))
    ```

    <span data-ttu-id="d9e8f-144">`DebugView` プロパティ</span><span class="sxs-lookup"><span data-stu-id="d9e8f-144">`DebugView` property</span></span>

    `.Block() {`

    `.Goto SampleLabel { 0 };`

    `.Label`

    `-1`

    `.LabelTarget SampleLabel:`

    `}`

- `Expression`

    ```vb
    Dim target As LabelTarget = Expression.Label()
    Dim block As BlockExpression = Expression.Block(
    Expression.Goto(target), Expression.Label(target))
    ```

    <span data-ttu-id="d9e8f-145">`DebugView` プロパティ</span><span class="sxs-lookup"><span data-stu-id="d9e8f-145">`DebugView` property</span></span>

    `.Block() {`

    `.Goto #Label1 { };`

    `.Label`

    `.LabelTarget #Label1:`

    `}`

## <a name="checked-operators"></a><span data-ttu-id="d9e8f-146">checked 演算子</span><span class="sxs-lookup"><span data-stu-id="d9e8f-146">Checked Operators</span></span>

<span data-ttu-id="d9e8f-147">checked 演算子は、演算子の前に "#" 記号が付く形式で表示されます。</span><span class="sxs-lookup"><span data-stu-id="d9e8f-147">Checked operators are displayed with the "#" symbol in front of the operator.</span></span> <span data-ttu-id="d9e8f-148">たとえば、checked 加算演算子は `#+` と表示されます。</span><span class="sxs-lookup"><span data-stu-id="d9e8f-148">For example, the checked addition operator is displayed as `#+`.</span></span>

### <a name="examples"></a><span data-ttu-id="d9e8f-149">使用例</span><span class="sxs-lookup"><span data-stu-id="d9e8f-149">Examples</span></span>

- `Expression`

    ```vb
    Dim expr As Expression = Expression.AddChecked(
    Expression.Constant(1), Expression.Constant(2))
    ```

    <span data-ttu-id="d9e8f-150">`DebugView` プロパティ</span><span class="sxs-lookup"><span data-stu-id="d9e8f-150">`DebugView` property</span></span>

    `1 #+ 2`

- `Expression`

    ```vb
    Dim expr As Expression = Expression.ConvertChecked(
    Expression.Constant(10.0), GetType(Integer))
    ```

    <span data-ttu-id="d9e8f-151">`DebugView` プロパティ</span><span class="sxs-lookup"><span data-stu-id="d9e8f-151">`DebugView` property</span></span>

    `#(System.Int32)10D`

## <a name="see-also"></a><span data-ttu-id="d9e8f-152">関連項目</span><span class="sxs-lookup"><span data-stu-id="d9e8f-152">See also</span></span>

- [<span data-ttu-id="d9e8f-153">式ツリー (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d9e8f-153">Expression Trees (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/expression-trees/index.md)
- [<span data-ttu-id="d9e8f-154">Visual Studio でのデバッグ</span><span class="sxs-lookup"><span data-stu-id="d9e8f-154">Debugging in Visual Studio</span></span>](/visualstudio/debugger/debugging-in-visual-studio)
- [<span data-ttu-id="d9e8f-155">カスタム ビジュアライザーを作成する</span><span class="sxs-lookup"><span data-stu-id="d9e8f-155">Create Custom Visualizers</span></span>](/visualstudio/debugger/create-custom-visualizers-of-data)
