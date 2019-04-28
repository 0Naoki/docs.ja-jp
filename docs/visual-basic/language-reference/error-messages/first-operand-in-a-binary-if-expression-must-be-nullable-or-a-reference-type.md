---
title: バイナリ 'If' 式の最初のオペランドは Null 許容または参照型である必要があります
ms.date: 07/20/2015
f1_keywords:
- bc33107
- vbc33107
helpviewer_keywords:
- BC33107
ms.assetid: 493c8899-3f6b-4471-8eb6-9284e8492768
ms.openlocfilehash: 32ff0adca9d35e6b5439ae06be85414924dac2e6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61801297"
---
# <a name="first-operand-in-a-binary-if-expression-must-be-nullable-or-a-reference-type"></a><span data-ttu-id="5efd9-102">バイナリ 'If' 式の最初のオペランドは Null 許容または参照型である必要があります</span><span class="sxs-lookup"><span data-stu-id="5efd9-102">First operand in a binary 'If' expression must be nullable or a reference type</span></span>
<span data-ttu-id="5efd9-103">`If`式が 2 つまたは 3 つの引数を受け取ることができます。</span><span class="sxs-lookup"><span data-stu-id="5efd9-103">An `If` expression can take either two or three arguments.</span></span> <span data-ttu-id="5efd9-104">2 つの引数を送信すると、最初の引数は、参照型または null 許容型でする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5efd9-104">When you send only two arguments, the first argument must be a reference type or a nullable type.</span></span> <span data-ttu-id="5efd9-105">最初の引数の評価が何も以外の場合`Nothing`、その値が返されます。</span><span class="sxs-lookup"><span data-stu-id="5efd9-105">If the first argument evaluates to anything other than `Nothing`, its value is returned.</span></span> <span data-ttu-id="5efd9-106">最初の引数が評価された場合`Nothing`、2 番目の引数が評価され、返されます。</span><span class="sxs-lookup"><span data-stu-id="5efd9-106">If the first argument evaluates to `Nothing`, the second argument is evaluated and returned.</span></span>  
  
 <span data-ttu-id="5efd9-107">たとえば、次のコードには 2 つ`If`で 3 つの引数と 2 つの引数の式。</span><span class="sxs-lookup"><span data-stu-id="5efd9-107">For example, the following code contains two `If` expressions, one with three arguments and one with two arguments.</span></span> <span data-ttu-id="5efd9-108">式を計算し、同じ値を返します。</span><span class="sxs-lookup"><span data-stu-id="5efd9-108">The expressions calculate and return the same value.</span></span>  
  
```vb  
' firstChoice is a nullable value type.  
Dim firstChoice? As Integer = Nothing  
Dim secondChoice As Integer = 1128  
' If expression with three arguments.  
Console.WriteLine(If(firstChoice IsNot Nothing, firstChoice, secondChoice))  
' If expression with two arguments.  
Console.WriteLine(If(firstChoice, secondChoice))  
```  
  
 <span data-ttu-id="5efd9-109">次の式では、このエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="5efd9-109">The following expressions cause this error:</span></span>  
  
```vb  
Dim choice1 = 4  
Dim choice2 = 5  
Dim booleanVar = True  
  
' Not valid.  
'Console.WriteLine(If(choice1 < choice2, 1))  
' Not valid.  
'Console.WriteLine(If(booleanVar, "Test returns True."))  
```  
  
 <span data-ttu-id="5efd9-110">**エラー ID:** BC33107</span><span class="sxs-lookup"><span data-stu-id="5efd9-110">**Error ID:** BC33107</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="5efd9-111">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="5efd9-111">To correct this error</span></span>  
  
- <span data-ttu-id="5efd9-112">最初の引数が null 許容型または参照型であるようにコードを変更することはできない場合、は、3 つの引数に変換することを検討してください`If`式、または、`If...Then...Else`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="5efd9-112">If you cannot change the code so that the first argument is a nullable type or reference type, consider converting to a three-argument `If` expression, or to an `If...Then...Else` statement.</span></span>  
  
```vb  
Console.WriteLine(If(choice1 < choice2, 1, 2))  
Console.WriteLine(If(booleanVar, "Test returns True.", "Test returns False."))  
```  
  
## <a name="see-also"></a><span data-ttu-id="5efd9-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="5efd9-113">See also</span></span>

- [<span data-ttu-id="5efd9-114">If 演算子</span><span class="sxs-lookup"><span data-stu-id="5efd9-114">If Operator</span></span>](../../../visual-basic/language-reference/operators/if-operator.md)
- [<span data-ttu-id="5efd9-115">If...Then...Else ステートメント</span><span class="sxs-lookup"><span data-stu-id="5efd9-115">If...Then...Else Statement</span></span>](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
- [<span data-ttu-id="5efd9-116">null 許容値型</span><span class="sxs-lookup"><span data-stu-id="5efd9-116">Nullable Value Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
