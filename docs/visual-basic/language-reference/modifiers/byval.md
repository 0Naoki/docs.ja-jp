---
title: ByVal (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.ByVal
- ByVal
helpviewer_keywords:
- ByVal keyword [Visual Basic], contexts
- ByVal keyword [Visual Basic]
ms.assetid: 1eaf4e58-b305-4785-9e3d-e416b9c75598
ms.openlocfilehash: 6fa87db4fbab961dd1aa526e2ac8ff15b031005b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54650081"
---
# <a name="byval-visual-basic"></a><span data-ttu-id="e4588-102">ByVal (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e4588-102">ByVal (Visual Basic)</span></span>
<span data-ttu-id="e4588-103">呼び出されたプロシージャまたはプロパティが呼び出し元のコードで引数を基になる変数の値を変更できないように、引数が渡されることを指定します。</span><span class="sxs-lookup"><span data-stu-id="e4588-103">Specifies that an argument is passed in such a way that the called procedure or property cannot change the value of a variable underlying the argument in the calling code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e4588-104">Remarks</span><span class="sxs-lookup"><span data-stu-id="e4588-104">Remarks</span></span>  
 <span data-ttu-id="e4588-105">`ByVal` 修飾子は、次のコンテキストで使用できます。</span><span class="sxs-lookup"><span data-stu-id="e4588-105">The `ByVal` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="e4588-106">Declare ステートメント</span><span class="sxs-lookup"><span data-stu-id="e4588-106">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [<span data-ttu-id="e4588-107">Function ステートメント</span><span class="sxs-lookup"><span data-stu-id="e4588-107">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="e4588-108">Operator ステートメント</span><span class="sxs-lookup"><span data-stu-id="e4588-108">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 [<span data-ttu-id="e4588-109">Property ステートメント</span><span class="sxs-lookup"><span data-stu-id="e4588-109">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="e4588-110">Sub ステートメント</span><span class="sxs-lookup"><span data-stu-id="e4588-110">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="example"></a><span data-ttu-id="e4588-111">例</span><span class="sxs-lookup"><span data-stu-id="e4588-111">Example</span></span>  
 <span data-ttu-id="e4588-112">使用例を次に示します、`ByVal`パラメーターを渡す参照型の引数で機能します。</span><span class="sxs-lookup"><span data-stu-id="e4588-112">The following example demonstrates the use of the `ByVal` parameter passing mechanism with a reference type argument.</span></span> <span data-ttu-id="e4588-113">引数は、例では、 `c1`、クラスのインスタンス`Class1`します。</span><span class="sxs-lookup"><span data-stu-id="e4588-113">In the example, the argument is `c1`, an instance of class `Class1`.</span></span> <span data-ttu-id="e4588-114">`ByVal` 手順でコードの参照の引数の基になる値の変更を防止`c1`、アクセス可能なフィールドとのプロパティは保護されませんが、`c1`します。</span><span class="sxs-lookup"><span data-stu-id="e4588-114">`ByVal` prevents the code in the procedures from changing the underlying value of the reference argument, `c1`, but does not protect the accessible fields and properties of `c1`.</span></span>  
  
 [!code-vb[VbVbalrKeywords#10](../../../visual-basic/language-reference/codesnippet/VisualBasic/byval_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="e4588-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="e4588-115">See also</span></span>
- [<span data-ttu-id="e4588-116">キーワード</span><span class="sxs-lookup"><span data-stu-id="e4588-116">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
- [<span data-ttu-id="e4588-117">引数の値渡しと参照渡し</span><span class="sxs-lookup"><span data-stu-id="e4588-117">Passing Arguments by Value and by Reference</span></span>](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)
