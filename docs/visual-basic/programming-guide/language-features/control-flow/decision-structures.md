---
title: 条件判断構造 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- statements [Visual Basic], control flow
- If statement [Visual Basic], decision structures
- If statement [Visual Basic], If...Then...Else
- control flow [Visual Basic], decision structures
- decision structures [Visual Basic]
- conditional statements [Visual Basic], decision structures
ms.assetid: 2e2e0895-4483-442a-b17c-26aead751ec2
ms.openlocfilehash: 20b60fb425278dacb56ee5f888967554a1f76aeb
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2019
ms.locfileid: "58825379"
---
# <a name="decision-structures-visual-basic"></a><span data-ttu-id="52601-102">条件判断構造 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="52601-102">Decision Structures (Visual Basic)</span></span>
<span data-ttu-id="52601-103">Visual Basic では、条件をテストし、そのテストの結果に応じてさまざまな操作を実行することができます。</span><span class="sxs-lookup"><span data-stu-id="52601-103">Visual Basic lets you test conditions and perform different operations depending on the results of that test.</span></span> <span data-ttu-id="52601-104">true または false の場合、さまざまな値の式、または一連のステートメントを実行するときに生成された例外のさまざまな条件をテストできます。</span><span class="sxs-lookup"><span data-stu-id="52601-104">You can test for a condition being true or false, for various values of an expression, or for various exceptions generated when you execute a series of statements.</span></span>  
  
 <span data-ttu-id="52601-105">次の図は、条件が真のテストが true か false かどうかに応じて異なるアクションを受け取っている意思決定構造を示します。</span><span class="sxs-lookup"><span data-stu-id="52601-105">The following illustration shows a decision structure that tests for a condition being true and takes different actions depending on whether it is true or false.</span></span>  
  
 <span data-ttu-id="52601-106">![If...Then...Else 構造](../../../../visual-basic/programming-guide/language-features/control-flow/media/ifthenelse.gif "IfThenElse")</span><span class="sxs-lookup"><span data-stu-id="52601-106">![Flow chart of an If...Then...Else construction](../../../../visual-basic/programming-guide/language-features/control-flow/media/ifthenelse.gif "IfThenElse")</span></span>  
<span data-ttu-id="52601-107">条件が true と false が別のアクションの実行</span><span class="sxs-lookup"><span data-stu-id="52601-107">Taking different actions when a condition is true and when it is false</span></span>  
  
## <a name="ifthenelse-construction"></a><span data-ttu-id="52601-108">If...Then...Else 構造</span><span class="sxs-lookup"><span data-stu-id="52601-108">If...Then...Else Construction</span></span>  
 <span data-ttu-id="52601-109">`If...Then...Else` 構造では、1 つまたは複数の条件をテストし、各条件に応じて 1 つまたは複数のステートメントを実行できます。</span><span class="sxs-lookup"><span data-stu-id="52601-109">`If...Then...Else` constructions let you test for one or more conditions and run one or more statements depending on each condition.</span></span> <span data-ttu-id="52601-110">条件をテストし、次の方法でアクションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="52601-110">You can test conditions and take actions in the following ways:</span></span>  
  
-   <span data-ttu-id="52601-111">条件の場合は、1 つまたは複数のステートメントを実行します。 `True`</span><span class="sxs-lookup"><span data-stu-id="52601-111">Run one or more statements if a condition is `True`</span></span>  
  
-   <span data-ttu-id="52601-112">条件の場合は、1 つまたは複数のステートメントを実行します。 `False`</span><span class="sxs-lookup"><span data-stu-id="52601-112">Run one or more statements if a condition is `False`</span></span>  
  
-   <span data-ttu-id="52601-113">条件の場合は、いくつかのステートメントを実行`True`や他のユーザーである場合 `False`</span><span class="sxs-lookup"><span data-stu-id="52601-113">Run some statements if a condition is `True` and others if it is `False`</span></span>  
  
-   <span data-ttu-id="52601-114">前の条件の場合、追加の条件をテストします。 `False`</span><span class="sxs-lookup"><span data-stu-id="52601-114">Test an additional condition if a prior condition is `False`</span></span>  
  
 <span data-ttu-id="52601-115">これらすべての可能性を提供する制御構造が、[If ... Then ... Else ステートメント](../../../../visual-basic/language-reference/statements/if-then-else-statement.md)です。</span><span class="sxs-lookup"><span data-stu-id="52601-115">The control structure that offers all these possibilities is the [If...Then...Else Statement](../../../../visual-basic/language-reference/statements/if-then-else-statement.md).</span></span> <span data-ttu-id="52601-116">1 つのテストと 1 つのステートメントを実行する必要がある場合は、単一行のバージョンを使用できます。</span><span class="sxs-lookup"><span data-stu-id="52601-116">You can use a single-line version if you have just one test and one statement to run.</span></span> <span data-ttu-id="52601-117">複雑な一連の条件とアクションがある場合は、複数行のバージョンを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="52601-117">If you have a more complex set of conditions and actions, you can use the multiple-line version.</span></span>  
  
## <a name="selectcase-construction"></a><span data-ttu-id="52601-118">Select...Case 構造</span><span class="sxs-lookup"><span data-stu-id="52601-118">Select...Case Construction</span></span>  
 <span data-ttu-id="52601-119">`Select...Case`構築では、1 つに式を評価し、異なる一連の別の使用可能な値に基づくステートメントを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="52601-119">The `Select...Case` construction lets you evaluate an expression one time and run different sets of statements based on different possible values.</span></span> <span data-ttu-id="52601-120">詳細については、[Select...Case ステートメント](../../../../visual-basic/language-reference/statements/select-case-statement.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="52601-120">For more information, see [Select...Case Statement](../../../../visual-basic/language-reference/statements/select-case-statement.md).</span></span>  
  
## <a name="trycatchfinally-construction"></a><span data-ttu-id="52601-121">Try...Catch...Finally 構造</span><span class="sxs-lookup"><span data-stu-id="52601-121">Try...Catch...Finally Construction</span></span>  
 <span data-ttu-id="52601-122">`Try...Catch...Finally` 構造では、一連のステートメント、ステートメントのいずれかの例外が発生した場合は、コントロールを保持する環境でを実行できます。</span><span class="sxs-lookup"><span data-stu-id="52601-122">`Try...Catch...Finally` constructions let you run a set of statements under an environment that retains control if any one of your statements causes an exception.</span></span> <span data-ttu-id="52601-123">さまざまな例外の別のアクションを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="52601-123">You can take different actions for different exceptions.</span></span> <span data-ttu-id="52601-124">必要に応じて、全体を終了する前に実行されるコードのブロックを指定することができます`Try...Catch...Finally`どうなるかに関係なく、構築します。</span><span class="sxs-lookup"><span data-stu-id="52601-124">You can optionally specify a block of code that runs before you exit the whole `Try...Catch...Finally` construction, regardless of what occurs.</span></span> <span data-ttu-id="52601-125">詳細については、[Try...Catch...Finally ステートメント](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="52601-125">For more information, see [Try...Catch...Finally Statement](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="52601-126">多くの制御構造のキーワードをクリックすると、すべての構造のキーワードが強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="52601-126">For many control structures, when you click a keyword, all of the keywords in the structure are highlighted.</span></span> <span data-ttu-id="52601-127">クリックすると、`If`で、`If...Then...Else`構築のすべてのインスタンス`If`、 `Then`、 `ElseIf`、 `Else`、および`End If`構築では強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="52601-127">For instance, when you click `If` in an `If...Then...Else` construction, all instances of `If`, `Then`, `ElseIf`, `Else`, and `End If` in the construction are highlighted.</span></span> <span data-ttu-id="52601-128">次または前の強調表示されているキーワードに移動するには、CTRL と shift キーを押しながら下方向キーまたは CTRL + SHIFT キーを押しながら上方向キーを押します。</span><span class="sxs-lookup"><span data-stu-id="52601-128">To move to the next or previous highlighted keyword, press CTRL+SHIFT+DOWN ARROW or CTRL+SHIFT+UP ARROW.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52601-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="52601-129">See also</span></span>

- [<span data-ttu-id="52601-130">制御フロー</span><span class="sxs-lookup"><span data-stu-id="52601-130">Control Flow</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)
- [<span data-ttu-id="52601-131">ループ構造</span><span class="sxs-lookup"><span data-stu-id="52601-131">Loop Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [<span data-ttu-id="52601-132">その他の制御構造</span><span class="sxs-lookup"><span data-stu-id="52601-132">Other Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)
- [<span data-ttu-id="52601-133">入れ子になった制御構造</span><span class="sxs-lookup"><span data-stu-id="52601-133">Nested Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [<span data-ttu-id="52601-134">If 演算子</span><span class="sxs-lookup"><span data-stu-id="52601-134">If Operator</span></span>](../../../../visual-basic/language-reference/operators/if-operator.md)
