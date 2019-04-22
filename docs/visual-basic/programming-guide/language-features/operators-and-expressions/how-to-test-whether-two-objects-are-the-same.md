---
title: '方法: 2 つのオブジェクトが同じ (Visual Basic) であるかどうかをテストします。'
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], reference
- Is operator [Visual Basic], comparing objects
- reference variables [Visual Basic]
- variables [Visual Basic], referring to same object
- objects [Visual Basic], variables referring to same
- Visual Basic code, operators
ms.assetid: f760e828-8704-4256-bc2d-c22a4c93b524
ms.openlocfilehash: dbb268175d197e7b931af45a98f3a273c593e5a3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "58819127"
---
# <a name="how-to-test-whether-two-objects-are-the-same-visual-basic"></a><span data-ttu-id="f48cc-102">方法: 2 つのオブジェクトが同じ (Visual Basic) であるかどうかをテストします。</span><span class="sxs-lookup"><span data-stu-id="f48cc-102">How to: Test Whether Two Objects Are the Same (Visual Basic)</span></span>
<span data-ttu-id="f48cc-103">オブジェクトを参照する 2 つの変数があれば、いずれかを使用できる、`Is`または`IsNot`演算子、または両方を同じインスタンスを参照しているかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="f48cc-103">If you have two variables that refer to objects, you can use either the `Is` or `IsNot` operator, or both, to determine whether they refer to the same instance.</span></span>  
  
### <a name="to-test-whether-two-objects-are-the-same"></a><span data-ttu-id="f48cc-104">2 つのオブジェクトが等しいかどうかをテストするには</span><span class="sxs-lookup"><span data-stu-id="f48cc-104">To test whether two objects are the same</span></span>  
  
-   <span data-ttu-id="f48cc-105">使用して、 [Is 演算子](../../../../visual-basic/language-reference/operators/is-operator.md)または[IsNot 演算子](../../../../visual-basic/language-reference/operators/isnot-operator.md)オペランドとして 2 つの変数を使用します。</span><span class="sxs-lookup"><span data-stu-id="f48cc-105">Use the [Is Operator](../../../../visual-basic/language-reference/operators/is-operator.md) or the [IsNot Operator](../../../../visual-basic/language-reference/operators/isnot-operator.md) with the two variables as operands.</span></span>  
  
     [!code-vb[VbVbalrOperators#69](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#69)]  
  
 <span data-ttu-id="f48cc-106">2 つのオブジェクトが同じインスタンスを参照するかどうかに応じて特定のアクションを実行する場合があります。</span><span class="sxs-lookup"><span data-stu-id="f48cc-106">You might want to take a certain action depending on whether two objects refer to the same instance.</span></span> <span data-ttu-id="f48cc-107">上記の例では、コントロール`c`フォーム上のアクティブ コントロールに対して`f`します。</span><span class="sxs-lookup"><span data-stu-id="f48cc-107">The preceding example compares control `c` against the active control on form `f`.</span></span> <span data-ttu-id="f48cc-108">作業中のコントロールがないかがある場合はこれ以上にできない場合と同じコントロール インスタンス`c`、`If`ステートメントが失敗し、手順をさらに処理することがなく返します。</span><span class="sxs-lookup"><span data-stu-id="f48cc-108">If there is no active control, or if there is one but it is not the same control instance as `c`, then the `If` statement fails and the procedure returns without further processing.</span></span>  
  
 <span data-ttu-id="f48cc-109">使用するかどうか`Is`または`IsNot`に個人の利便性の問題です。</span><span class="sxs-lookup"><span data-stu-id="f48cc-109">Whether you use `Is` or `IsNot` is a matter of personal convenience to you.</span></span> <span data-ttu-id="f48cc-110">1 つは、指定された式で他よりも読みやすい可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f48cc-110">One might be easier to read than the other in a given expression.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f48cc-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="f48cc-111">See also</span></span>

- [<span data-ttu-id="f48cc-112">Visual Basic における比較演算子</span><span class="sxs-lookup"><span data-stu-id="f48cc-112">Comparison Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
