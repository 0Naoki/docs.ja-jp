---
title: Boolean 式 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- short-circuiting
- Boolean expressions
- logical operators [Visual Basic], Boolean expressions
- expressions [Visual Basic], Boolean
- expression evaluation [Visual Basic], Boolean expressions
- operators [Visual Basic], short-circuiting
- Visual Basic code, operators
- short-circuit evaluation
- logical operators [Visual Basic], short-circuiting
- operators [Visual Basic], Boolean
- Visual Basic code, expressions
ms.assetid: d3d90406-55c8-4404-8143-50fd7f0d0d1a
ms.openlocfilehash: a86df2734d315e5fed0784b0394bb305b15562a9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54562753"
---
# <a name="boolean-expressions-visual-basic"></a><span data-ttu-id="57725-102">Boolean 式 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="57725-102">Boolean Expressions (Visual Basic)</span></span>
<span data-ttu-id="57725-103">*ブール式*の値に評価される式を指定、[ブールのデータ型](../../../../visual-basic/language-reference/data-types/boolean-data-type.md):`True`または`False`です。</span><span class="sxs-lookup"><span data-stu-id="57725-103">A *Boolean expression* is an expression that evaluates to a value of the [Boolean Data Type](../../../../visual-basic/language-reference/data-types/boolean-data-type.md): `True` or `False`.</span></span> <span data-ttu-id="57725-104">`Boolean` 式には、いくつかの形式を取ります。</span><span class="sxs-lookup"><span data-stu-id="57725-104">`Boolean` expressions can take several forms.</span></span> <span data-ttu-id="57725-105">単純な形式の値を直接比較、`Boolean`変数を`Boolean`リテラルは、次の例に示すようにします。</span><span class="sxs-lookup"><span data-stu-id="57725-105">The simplest is the direct comparison of the value of a `Boolean` variable to a `Boolean` literal, as shown in the following example.</span></span>  
  
 [!code-vb[VbVbalrOperators#87](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/boolean-expressions_1.vb)]  
  
## <a name="two-meanings-of-the--operator"></a><span data-ttu-id="57725-106">2 つの意味、= 演算子</span><span class="sxs-lookup"><span data-stu-id="57725-106">Two Meanings of the = Operator</span></span>  
 <span data-ttu-id="57725-107">注意して代入ステートメント`newCustomer = True`前の例では、式と同じに見えますが、別の関数を実行して異なる方法で使用されます。</span><span class="sxs-lookup"><span data-stu-id="57725-107">Notice that the assignment statement `newCustomer = True` looks the same as the expression in the preceding example, but it performs a different function and is used differently.</span></span> <span data-ttu-id="57725-108">前の例では、式で`newCustomer = True`ブール値を表す、`=`記号は、比較演算子と解釈されます。</span><span class="sxs-lookup"><span data-stu-id="57725-108">In the preceding example, the expression `newCustomer = True` represents a Boolean value, and the `=` sign is interpreted as a comparison operator.</span></span> <span data-ttu-id="57725-109">スタンドアロンのステートメントで、`=`記号は、代入演算子と解釈され、左側の変数を右側にある値を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="57725-109">In a stand-alone statement, the `=` sign is interpreted as an assignment operator and assigns the value on the right to the variable on the left.</span></span> <span data-ttu-id="57725-110">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="57725-110">The following example illustrates this.</span></span>  
  
 [!code-vb[VbVbalrOperators#88](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/boolean-expressions_2.vb)]  
  
 <span data-ttu-id="57725-111">詳細については、次を参照してください。[値の比較](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)と[ステートメント](../../../../visual-basic/language-reference/statements/index.md)します。</span><span class="sxs-lookup"><span data-stu-id="57725-111">For further information, see [Value Comparisons](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md) and [Statements](../../../../visual-basic/language-reference/statements/index.md).</span></span>  
  
## <a name="comparison-operators"></a><span data-ttu-id="57725-112">比較演算子</span><span class="sxs-lookup"><span data-stu-id="57725-112">Comparison Operators</span></span>  
 <span data-ttu-id="57725-113">比較演算子`=`、 `<`、 `>`、 `<>`、 `<=`、および`>=`ブール式を右側にある式を演算子の左側にある式を比較することによって生成演算子と、結果としての評価の`True`または`False`します。</span><span class="sxs-lookup"><span data-stu-id="57725-113">Comparison operators such as `=`, `<`, `>`, `<>`, `<=`, and `>=` produce Boolean expressions by comparing the expression on the left side of the operator to the expression on the right side of the operator and evaluating the result as `True` or `False`.</span></span> <span data-ttu-id="57725-114">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="57725-114">The following example illustrates this.</span></span>  
  
 `42 < 81`  
  
 <span data-ttu-id="57725-115">上記の例ではブール式の評価が 42 81 未満なので`True`します。</span><span class="sxs-lookup"><span data-stu-id="57725-115">Because 42 is less than 81, the Boolean expression in the preceding example evaluates to `True`.</span></span> <span data-ttu-id="57725-116">このような式の詳細については、次を参照してください。[値の比較](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)します。</span><span class="sxs-lookup"><span data-stu-id="57725-116">For more information on this kind of expression, see [Value Comparisons](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md).</span></span>  
  
### <a name="comparison-operators-combined-with-logical-operators"></a><span data-ttu-id="57725-117">比較演算子が論理演算子と組み合わせる</span><span class="sxs-lookup"><span data-stu-id="57725-117">Comparison Operators Combined with Logical Operators</span></span>  
 <span data-ttu-id="57725-118">比較式より複雑なブール式を生成するために論理演算子を使用して結合できます。</span><span class="sxs-lookup"><span data-stu-id="57725-118">Comparison expressions can be combined using logical operators to produce more complex Boolean expressions.</span></span> <span data-ttu-id="57725-119">次の例では、論理演算子と組み合わせて比較演算子の使用を示します。</span><span class="sxs-lookup"><span data-stu-id="57725-119">The following example demonstrates the use of comparison operators in conjunction with a logical operator.</span></span>  
  
 `x > y And x < 1000`  
  
 <span data-ttu-id="57725-120">上記の例では、全体的な式の値がの両側の式の値に依存、`And`演算子。</span><span class="sxs-lookup"><span data-stu-id="57725-120">In the preceding example, the value of the overall expression depends on the values of the expressions on each side of the `And` operator.</span></span> <span data-ttu-id="57725-121">両方の式が場合`True`、全体的な式に評価し、`True`します。</span><span class="sxs-lookup"><span data-stu-id="57725-121">If both expressions are `True`, then the overall expression evaluates to `True`.</span></span> <span data-ttu-id="57725-122">いずれかの式が場合`False`、全体の式に評価し、`False`します。</span><span class="sxs-lookup"><span data-stu-id="57725-122">If either expression is `False`, then the entire expression evaluates to `False`.</span></span>  
  
## <a name="short-circuiting-operators"></a><span data-ttu-id="57725-123">ショート サーキット演算子</span><span class="sxs-lookup"><span data-stu-id="57725-123">Short-Circuiting Operators</span></span>  
 <span data-ttu-id="57725-124">論理演算子`AndAlso`と`OrElse`と呼ばれる現象が発生する*ショート サーキット*します。</span><span class="sxs-lookup"><span data-stu-id="57725-124">The logical operators `AndAlso` and `OrElse` exhibit behavior known as *short-circuiting*.</span></span> <span data-ttu-id="57725-125">ショート サーキット演算子は、まず、左側のオペランドを評価します。</span><span class="sxs-lookup"><span data-stu-id="57725-125">A short-circuiting operator evaluates the left operand first.</span></span> <span data-ttu-id="57725-126">左側のオペランドでは、式全体の値を決定、右の式を評価することがなくプログラムの実行が処理されます。</span><span class="sxs-lookup"><span data-stu-id="57725-126">If the left operand determines the value of the entire expression, then program execution proceeds without evaluating the right expression.</span></span> <span data-ttu-id="57725-127">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="57725-127">The following example illustrates this.</span></span>  
  
 [!code-vb[VbVbalrOperators#89](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/boolean-expressions_3.vb)]  
  
 <span data-ttu-id="57725-128">前の例では、演算子は、左の式を評価`45 < 12`します。</span><span class="sxs-lookup"><span data-stu-id="57725-128">In the preceding example, the operator evaluates the left expression, `45 < 12`.</span></span> <span data-ttu-id="57725-129">左の式が評価されるため`False`、論理式全体に評価される必要があります`False`します。</span><span class="sxs-lookup"><span data-stu-id="57725-129">Because the left expression evaluates to `False`, the entire logical expression must evaluate to `False`.</span></span> <span data-ttu-id="57725-130">プログラムの実行はそのためのコードの実行をスキップ、`If`右の式を評価することがなくブロック`testFunction(3)`します。</span><span class="sxs-lookup"><span data-stu-id="57725-130">Program execution thus skips execution of the code within the `If` block without evaluating the right expression, `testFunction(3)`.</span></span> <span data-ttu-id="57725-131">この例は呼び出しません`testFunction()`左の式が式全体を falsifies ためです。</span><span class="sxs-lookup"><span data-stu-id="57725-131">This example does not call `testFunction()` because the left expression falsifies the entire expression.</span></span>  
  
 <span data-ttu-id="57725-132">同様に場合、左の式を使用して、論理式で`OrElse`に評価される`True`、左の式が既に全体を検証するため、右の式を評価せず、次のコード行に実行されます式。</span><span class="sxs-lookup"><span data-stu-id="57725-132">Similarly, if the left expression in a logical expression using `OrElse` evaluates to `True`, execution proceeds to the next line of code without evaluating the right expression, because the left expression has already validated the entire expression.</span></span>  
  
### <a name="comparison-with-non-short-circuiting-operators"></a><span data-ttu-id="57725-133">非ショート サーキット演算子との比較</span><span class="sxs-lookup"><span data-stu-id="57725-133">Comparison with Non-Short-Circuiting Operators</span></span>  
 <span data-ttu-id="57725-134">これに対し、論理演算子の両辺が評価されるときに、論理演算子`And`と`Or`使用されます。</span><span class="sxs-lookup"><span data-stu-id="57725-134">By contrast, both sides of the logical operator are evaluated when the logical operators `And` and `Or` are used.</span></span> <span data-ttu-id="57725-135">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="57725-135">The following example illustrates this.</span></span>  
  
 [!code-vb[VbVbalrOperators#90](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/boolean-expressions_4.vb)]  
  
 <span data-ttu-id="57725-136">上記の例では、 `testFunction()` 、左の式を評価する場合でも`False`します。</span><span class="sxs-lookup"><span data-stu-id="57725-136">The preceding example calls `testFunction()` even though the left expression evaluates to `False`.</span></span>  
  
## <a name="parenthetical-expressions"></a><span data-ttu-id="57725-137">かっこで囲まれた式</span><span class="sxs-lookup"><span data-stu-id="57725-137">Parenthetical Expressions</span></span>  
 <span data-ttu-id="57725-138">ブール式の評価の順序を制御するのにかっこを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="57725-138">You can use parentheses to control the order of evaluation of Boolean expressions.</span></span> <span data-ttu-id="57725-139">かっこで囲まれた式が最初に評価されます。</span><span class="sxs-lookup"><span data-stu-id="57725-139">Expressions enclosed by parentheses evaluate first.</span></span> <span data-ttu-id="57725-140">複数のレベルの入れ子では、優先順位が最も深く入れ子になった式に付与されます。</span><span class="sxs-lookup"><span data-stu-id="57725-140">For multiple levels of nesting, precedence is granted to the most deeply nested expressions.</span></span> <span data-ttu-id="57725-141">かっこ内では、評価は演算子の優先順位の規則に従って処理されます。</span><span class="sxs-lookup"><span data-stu-id="57725-141">Within parentheses, evaluation proceeds according to the rules of operator precedence.</span></span> <span data-ttu-id="57725-142">詳細については、次を参照してください。 [Visual Basic における演算子の優先順位](../../../../visual-basic/language-reference/operators/operator-precedence.md)します。</span><span class="sxs-lookup"><span data-stu-id="57725-142">For more information, see [Operator Precedence in Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57725-143">関連項目</span><span class="sxs-lookup"><span data-stu-id="57725-143">See also</span></span>
- [<span data-ttu-id="57725-144">Visual Basic での論理とビット処理演算子</span><span class="sxs-lookup"><span data-stu-id="57725-144">Logical and Bitwise Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
- [<span data-ttu-id="57725-145">値の比較</span><span class="sxs-lookup"><span data-stu-id="57725-145">Value Comparisons</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)
- [<span data-ttu-id="57725-146">ステートメント</span><span class="sxs-lookup"><span data-stu-id="57725-146">Statements</span></span>](../../../../visual-basic/programming-guide/language-features/statements.md)
- [<span data-ttu-id="57725-147">比較演算子</span><span class="sxs-lookup"><span data-stu-id="57725-147">Comparison Operators</span></span>](../../../../visual-basic/language-reference/operators/comparison-operators.md)
- [<span data-ttu-id="57725-148">演算子の効率のよい組み合わせ</span><span class="sxs-lookup"><span data-stu-id="57725-148">Efficient Combination of Operators</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)
- [<span data-ttu-id="57725-149">Visual Basic における演算子の優先順位</span><span class="sxs-lookup"><span data-stu-id="57725-149">Operator Precedence in Visual Basic</span></span>](../../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="57725-150">Boolean データ型</span><span class="sxs-lookup"><span data-stu-id="57725-150">Boolean Data Type</span></span>](../../../../visual-basic/language-reference/data-types/boolean-data-type.md)
