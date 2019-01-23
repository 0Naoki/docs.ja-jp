---
title: Do...Loop ステートメント (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Do
- vb.Loop
- vb.Until
helpviewer_keywords:
- conditional statements [Visual Basic], Do�Loop
- while statement [Visual Basic], Do...Loop
- execution [Visual Basic], conditional
- Do loops
- Until keyword [Visual Basic], Do...Loop statement
- Do...Loop statement
- instructions, repeating
- Do statement [Visual Basic]
- Exit statement [Visual Basic], in Do...Loop statements
- loop structures [Visual Basic], Do�Loop statements
- do-while statements [Visual Basic]
- loops, exiting
- Loop keyword [Visual Basic], Do...Loop statement
ms.assetid: 892f9096-b3e2-4aee-834d-83bc4e2c379d
ms.openlocfilehash: 8c965dc89794654127e4b872c6aebf55c8902468
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54525150"
---
# <a name="doloop-statement-visual-basic"></a><span data-ttu-id="26b7d-102">Do...Loop ステートメント (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="26b7d-102">Do...Loop Statement (Visual Basic)</span></span>
<span data-ttu-id="26b7d-103">中にステートメント ブロックを繰り返します、`Boolean`条件が`True`まで、このような条件または`True`します。</span><span class="sxs-lookup"><span data-stu-id="26b7d-103">Repeats a block of statements while a `Boolean` condition is `True` or until the condition becomes `True`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26b7d-104">構文</span><span class="sxs-lookup"><span data-stu-id="26b7d-104">Syntax</span></span>  
  
```  
Do { While | Until } condition  
    [ statements ]  
    [ Continue Do ]  
    [ statements ]  
    [ Exit Do ]  
    [ statements ]  
Loop  
-or-  
Do  
    [ statements ]  
    [ Continue Do ]  
    [ statements ]  
    [ Exit Do ]  
    [ statements ]  
Loop { While | Until } condition  
```  
  
## <a name="parts"></a><span data-ttu-id="26b7d-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="26b7d-105">Parts</span></span>  
  
|<span data-ttu-id="26b7d-106">用語</span><span class="sxs-lookup"><span data-stu-id="26b7d-106">Term</span></span>|<span data-ttu-id="26b7d-107">定義</span><span class="sxs-lookup"><span data-stu-id="26b7d-107">Definition</span></span>|  
|---|---|  
|`Do`|<span data-ttu-id="26b7d-108">必須。</span><span class="sxs-lookup"><span data-stu-id="26b7d-108">Required.</span></span> <span data-ttu-id="26b7d-109">定義を開始、`Do`ループします。</span><span class="sxs-lookup"><span data-stu-id="26b7d-109">Starts the definition of the `Do` loop.</span></span>|  
|`While`|<span data-ttu-id="26b7d-110">`Until` を使用しない場合に、必ず指定します。</span><span class="sxs-lookup"><span data-stu-id="26b7d-110">Required unless `Until` is used.</span></span> <span data-ttu-id="26b7d-111">までループを繰り返す`condition`は`False`します。</span><span class="sxs-lookup"><span data-stu-id="26b7d-111">Repeat the loop until `condition` is `False`.</span></span>|  
|`Until`|<span data-ttu-id="26b7d-112">`While` を使用しない場合に、必ず指定します。</span><span class="sxs-lookup"><span data-stu-id="26b7d-112">Required unless `While` is used.</span></span> <span data-ttu-id="26b7d-113">までループを繰り返す`condition`は`True`します。</span><span class="sxs-lookup"><span data-stu-id="26b7d-113">Repeat the loop until `condition` is `True`.</span></span>|  
|`condition`|<span data-ttu-id="26b7d-114">任意。</span><span class="sxs-lookup"><span data-stu-id="26b7d-114">Optional.</span></span> <span data-ttu-id="26b7d-115">`Boolean` 式。</span><span class="sxs-lookup"><span data-stu-id="26b7d-115">`Boolean` expression.</span></span> <span data-ttu-id="26b7d-116">場合`condition`は`Nothing`、Visual Basic として扱います`False`します。</span><span class="sxs-lookup"><span data-stu-id="26b7d-116">If `condition` is `Nothing`, Visual Basic treats it as `False`.</span></span>|  
|`statements`|<span data-ttu-id="26b7d-117">任意。</span><span class="sxs-lookup"><span data-stu-id="26b7d-117">Optional.</span></span> <span data-ttu-id="26b7d-118">1 つまたは複数のステートメント、まで、または while、繰り返される`condition`は`True`します。</span><span class="sxs-lookup"><span data-stu-id="26b7d-118">One or more statements that are repeated while, or until, `condition` is `True`.</span></span>|  
|`Continue Do`|<span data-ttu-id="26b7d-119">任意。</span><span class="sxs-lookup"><span data-stu-id="26b7d-119">Optional.</span></span> <span data-ttu-id="26b7d-120">次のイテレーションに制御を転送、`Do`ループします。</span><span class="sxs-lookup"><span data-stu-id="26b7d-120">Transfers control to the next iteration of the `Do` loop.</span></span>|  
|`Exit Do`|<span data-ttu-id="26b7d-121">任意。</span><span class="sxs-lookup"><span data-stu-id="26b7d-121">Optional.</span></span> <span data-ttu-id="26b7d-122">うちに制御を転送、`Do`ループします。</span><span class="sxs-lookup"><span data-stu-id="26b7d-122">Transfers control out of the `Do` loop.</span></span>|  
|`Loop`|<span data-ttu-id="26b7d-123">必須。</span><span class="sxs-lookup"><span data-stu-id="26b7d-123">Required.</span></span> <span data-ttu-id="26b7d-124">定義を終了、`Do`ループします。</span><span class="sxs-lookup"><span data-stu-id="26b7d-124">Terminates the definition of the `Do` loop.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="26b7d-125">Remarks</span><span class="sxs-lookup"><span data-stu-id="26b7d-125">Remarks</span></span>  
 <span data-ttu-id="26b7d-126">使用して、`Do...Loop`一連の条件が満たされるまで何度で不特定数のステートメントを繰り返し表示するときに構造体します。</span><span class="sxs-lookup"><span data-stu-id="26b7d-126">Use a `Do...Loop` structure when you want to repeat a set of statements an indefinite number of times, until a condition is satisfied.</span></span> <span data-ttu-id="26b7d-127">設定された数の時間、ステートメントを繰り返し表示する場合、[をしています.次のステートメントの](../../../visual-basic/language-reference/statements/for-next-statement.md)は、通常のことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="26b7d-127">If you want to repeat the statements a set number of times, the [For...Next Statement](../../../visual-basic/language-reference/statements/for-next-statement.md) is usually a better choice.</span></span>  
  
 <span data-ttu-id="26b7d-128">いずれかを使用する`While`または`Until`を指定する`condition`、両方ではないです。</span><span class="sxs-lookup"><span data-stu-id="26b7d-128">You can use either `While` or `Until` to specify `condition`, but not both.</span></span>  
  
 <span data-ttu-id="26b7d-129">テストすることができます`condition`先頭またはループの終了のいずれか 1 つだけの時間。</span><span class="sxs-lookup"><span data-stu-id="26b7d-129">You can test `condition` only one time, at either the start or the end of the loop.</span></span> <span data-ttu-id="26b7d-130">テストする場合`condition`、ループの先頭 (で、`Do`ステートメント)、ループでも 1 回を実行しない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="26b7d-130">If you test `condition` at the start of the loop (in the `Do` statement), the loop might not run even one time.</span></span> <span data-ttu-id="26b7d-131">ループの最後にテストする場合 (で、`Loop`ステートメント)、ループは、1 つ以上の時間を常に実行されます。</span><span class="sxs-lookup"><span data-stu-id="26b7d-131">If you test at the end of the loop (in the `Loop` statement), the loop always runs at least one time.</span></span>  
  
 <span data-ttu-id="26b7d-132">条件は、通常は 2 つの値の比較から結果しますが、任意に評価される式を[ブール データ型](../../../visual-basic/language-reference/data-types/boolean-data-type.md)値 (`True`または`False`)。</span><span class="sxs-lookup"><span data-stu-id="26b7d-132">The condition usually results from a comparison of two values, but it can be any expression that evaluates to a [Boolean Data Type](../../../visual-basic/language-reference/data-types/boolean-data-type.md) value (`True` or `False`).</span></span> <span data-ttu-id="26b7d-133">これにより、数値型に変換されたなどの他のデータ型の値が含まれます。`Boolean`します。</span><span class="sxs-lookup"><span data-stu-id="26b7d-133">This includes values of other data types, such as numeric types, that have been converted to `Boolean`.</span></span>  
  
 <span data-ttu-id="26b7d-134">入れ子にすることができます`Do`内に別の 1 つのループを配置することでループします。</span><span class="sxs-lookup"><span data-stu-id="26b7d-134">You can nest `Do` loops by putting one loop within another.</span></span> <span data-ttu-id="26b7d-135">さまざまな種類を 1 つの制御構造の入れ子にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="26b7d-135">You can also nest different kinds of control structures within each other.</span></span> <span data-ttu-id="26b7d-136">詳細については、次を参照してください。[制御構造の入れ子になった](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)します。</span><span class="sxs-lookup"><span data-stu-id="26b7d-136">For more information, see [Nested Control Structures](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="26b7d-137">`Do...Loop`構造より柔軟性、[中.End While ステートメント](../../../visual-basic/language-reference/statements/while-end-while-statement.md)、ループを終了するかどうかを決定することもできるため、ときに`condition`停止されている`True`がそのときまたは`True`します。</span><span class="sxs-lookup"><span data-stu-id="26b7d-137">The `Do...Loop` structure gives you more flexibility than the [While...End While Statement](../../../visual-basic/language-reference/statements/while-end-while-statement.md) because it enables you to decide whether to end the loop when `condition` stops being `True` or when it first becomes `True`.</span></span> <span data-ttu-id="26b7d-138">テストすることもできます`condition`先頭またはループの終了のいずれか。</span><span class="sxs-lookup"><span data-stu-id="26b7d-138">It also enables you to test `condition` at either the start or the end of the loop.</span></span>  
  
## <a name="exit-do"></a><span data-ttu-id="26b7d-139">操作を終了します。</span><span class="sxs-lookup"><span data-stu-id="26b7d-139">Exit Do</span></span>  
 <span data-ttu-id="26b7d-140">[Exit Do](../../../visual-basic/language-reference/statements/exit-statement.md)ステートメントが終了する別の方法を提供する`Do…Loop`します。</span><span class="sxs-lookup"><span data-stu-id="26b7d-140">The [Exit Do](../../../visual-basic/language-reference/statements/exit-statement.md) statement can provide an alternative way to exit a `Do…Loop`.</span></span> <span data-ttu-id="26b7d-141">`Exit Do` 続くステートメントに直ちに制御を移します、`Loop`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="26b7d-141">`Exit Do` transfers control immediately to the statement that follows the `Loop` statement.</span></span>  
  
 <span data-ttu-id="26b7d-142">`Exit Do` 例では、いくつかの条件が評価された後に多くの場合に使用される、`If...Then...Else`構造体。</span><span class="sxs-lookup"><span data-stu-id="26b7d-142">`Exit Do` is often used after some condition is evaluated, for example in an `If...Then...Else` structure.</span></span> <span data-ttu-id="26b7d-143">不要なまたは不可能なエラー値や終了要求など、反復処理を続行する条件を検出した場合、ループを終了する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="26b7d-143">You might want to exit a loop if you detect a condition that makes it unnecessary or impossible to continue iterating, such as an erroneous value or a termination request.</span></span> <span data-ttu-id="26b7d-144">用途の 1 つ`Exit Do`を引き起こす可能性のある条件をテストするには、*無限ループ*、これは、何度も長時間または無限でも実行できるループします。</span><span class="sxs-lookup"><span data-stu-id="26b7d-144">One use of `Exit Do` is to test for a condition that could cause an *endless loop*, which is a loop that could run a large or even infinite number of times.</span></span> <span data-ttu-id="26b7d-145">使用することができます`Exit Do`ループを抜けます。</span><span class="sxs-lookup"><span data-stu-id="26b7d-145">You can use `Exit Do` to escape the loop.</span></span>  
  
 <span data-ttu-id="26b7d-146">任意の数を含めることができます`Exit Do`でステートメントを任意の場所、`Do…Loop`します。</span><span class="sxs-lookup"><span data-stu-id="26b7d-146">You can include any number of `Exit Do` statements anywhere in a `Do…Loop`.</span></span>  
  
 <span data-ttu-id="26b7d-147">使用すると内で入れ子になった`Do`ループ、`Exit Do`上位レベルの入れ子にして、最も内側のループからコントロールを転送します。</span><span class="sxs-lookup"><span data-stu-id="26b7d-147">When used within nested `Do` loops, `Exit Do` transfers control out of the innermost loop and into the next higher level of nesting.</span></span>  
  
## <a name="example"></a><span data-ttu-id="26b7d-148">例</span><span class="sxs-lookup"><span data-stu-id="26b7d-148">Example</span></span>  
 <span data-ttu-id="26b7d-149">次の例では、ループ内のステートメントの続行までを実行する、`index`変数が 10 より大きい。</span><span class="sxs-lookup"><span data-stu-id="26b7d-149">In the following example, the statements in the loop continue to run until the `index` variable is greater than 10.</span></span> <span data-ttu-id="26b7d-150">`Until`句は、ループの最後に、します。</span><span class="sxs-lookup"><span data-stu-id="26b7d-150">The `Until` clause is at the end of the loop.</span></span>  
  
 [!code-vb[VbVbalrStatements#131](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/do-loop-statement_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="26b7d-151">例</span><span class="sxs-lookup"><span data-stu-id="26b7d-151">Example</span></span>  
 <span data-ttu-id="26b7d-152">次の例では、`While`句の代わりに、`Until`句と`condition`は最後の代わりに、ループの先頭にテストします。</span><span class="sxs-lookup"><span data-stu-id="26b7d-152">The following example uses a `While` clause instead of an `Until` clause, and `condition` is tested at the start of the loop instead of at the end.</span></span>  
  
 [!code-vb[VbVbalrStatements#132](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/do-loop-statement_2.vb)]  
  
## <a name="example"></a><span data-ttu-id="26b7d-153">例</span><span class="sxs-lookup"><span data-stu-id="26b7d-153">Example</span></span>  
 <span data-ttu-id="26b7d-154">次の例では、`condition`ループを停止するときに、`index`変数が 100 より大きい。</span><span class="sxs-lookup"><span data-stu-id="26b7d-154">In the following example, `condition` stops the loop when the `index` variable is greater than 100.</span></span> <span data-ttu-id="26b7d-155">`If`ループでは、ステートメントがただし、により、`Exit Do`インデックス変数が 10 より大きい場合は、ループを停止するステートメント。</span><span class="sxs-lookup"><span data-stu-id="26b7d-155">The `If` statement in the loop, however, causes the `Exit Do` statement to stop the loop when the index variable is greater than 10.</span></span>  
  
 [!code-vb[VbVbalrStatements#133](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/do-loop-statement_3.vb)]  
  
## <a name="example"></a><span data-ttu-id="26b7d-156">例</span><span class="sxs-lookup"><span data-stu-id="26b7d-156">Example</span></span>  
 <span data-ttu-id="26b7d-157">次の例では、テキスト ファイルのすべての行を読み取ります。</span><span class="sxs-lookup"><span data-stu-id="26b7d-157">The following example reads all lines in a text file.</span></span> <span data-ttu-id="26b7d-158"><xref:System.IO.File.OpenText%2A>メソッドは、ファイルを開くし、取得、<xref:System.IO.StreamReader>文字を読み取る。</span><span class="sxs-lookup"><span data-stu-id="26b7d-158">The <xref:System.IO.File.OpenText%2A> method opens the file and returns a <xref:System.IO.StreamReader> that reads the characters.</span></span> <span data-ttu-id="26b7d-159">`Do...Loop`条件、<xref:System.IO.StreamReader.Peek%2A>のメソッド、`StreamReader`追加の文字があるかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="26b7d-159">In the `Do...Loop` condition, the <xref:System.IO.StreamReader.Peek%2A> method of the `StreamReader` determines whether there are any additional characters.</span></span>  
  
 [!code-vb[VbVbalrStatements#134](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/do-loop-statement_4.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="26b7d-160">関連項目</span><span class="sxs-lookup"><span data-stu-id="26b7d-160">See also</span></span>
- [<span data-ttu-id="26b7d-161">ループ構造</span><span class="sxs-lookup"><span data-stu-id="26b7d-161">Loop Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [<span data-ttu-id="26b7d-162">For...Next ステートメント</span><span class="sxs-lookup"><span data-stu-id="26b7d-162">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [<span data-ttu-id="26b7d-163">Boolean データ型</span><span class="sxs-lookup"><span data-stu-id="26b7d-163">Boolean Data Type</span></span>](../../../visual-basic/language-reference/data-types/boolean-data-type.md)
- [<span data-ttu-id="26b7d-164">入れ子になった制御構造</span><span class="sxs-lookup"><span data-stu-id="26b7d-164">Nested Control Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [<span data-ttu-id="26b7d-165">Exit ステートメント</span><span class="sxs-lookup"><span data-stu-id="26b7d-165">Exit Statement</span></span>](../../../visual-basic/language-reference/statements/exit-statement.md)
- [<span data-ttu-id="26b7d-166">While...End While ステートメント</span><span class="sxs-lookup"><span data-stu-id="26b7d-166">While...End While Statement</span></span>](../../../visual-basic/language-reference/statements/while-end-while-statement.md)
