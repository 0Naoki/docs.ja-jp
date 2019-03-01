---
title: '方法: 変換演算子 (Visual Basic) を定義します。'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- operators [Visual Basic], defining
- procedures [Visual Basic], operator
- operators [Visual Basic], overloading
- return values [Visual Basic], Operator procedures
- operator overloading
ms.assetid: 54203dfa-c24b-463f-9942-d5153e89e762
ms.openlocfilehash: fe5c314fe4e39c8a06803037da29b51148188e14
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2019
ms.locfileid: "56974641"
---
# <a name="how-to-define-a-conversion-operator-visual-basic"></a><span data-ttu-id="0b511-102">方法: 変換演算子 (Visual Basic) を定義します。</span><span class="sxs-lookup"><span data-stu-id="0b511-102">How to: Define a Conversion Operator (Visual Basic)</span></span>
<span data-ttu-id="0b511-103">クラスまたは構造体を定義している場合は、クラスまたは構造体の型と別のデータ型の間の型変換演算子を定義することができます (など`Integer`、 `Double`、または`String`)。</span><span class="sxs-lookup"><span data-stu-id="0b511-103">If you have defined a class or structure, you can define a type conversion operator between the type of your class or structure and another data type (such as `Integer`, `Double`, or `String`).</span></span>  
  
 <span data-ttu-id="0b511-104">として型の変換を定義、 [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md)クラスまたは構造内のプロシージャです。</span><span class="sxs-lookup"><span data-stu-id="0b511-104">Define the type conversion as a [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md) procedure within the class or structure.</span></span> <span data-ttu-id="0b511-105">変換のすべてのプロシージャである必要があります`Public Shared`、いずれかを指定する必要がありますそれぞれ[Widening](../../../../visual-basic/language-reference/modifiers/widening.md)または[Narrowing](../../../../visual-basic/language-reference/modifiers/narrowing.md)します。</span><span class="sxs-lookup"><span data-stu-id="0b511-105">All conversion procedures must be `Public Shared`, and each one must specify either [Widening](../../../../visual-basic/language-reference/modifiers/widening.md) or [Narrowing](../../../../visual-basic/language-reference/modifiers/narrowing.md).</span></span>  
  
 <span data-ttu-id="0b511-106">クラスまたは構造体で演算子を定義が呼び出されますも*オーバー ロード*演算子。</span><span class="sxs-lookup"><span data-stu-id="0b511-106">Defining an operator on a class or structure is also called *overloading* the operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0b511-107">例</span><span class="sxs-lookup"><span data-stu-id="0b511-107">Example</span></span>  
 <span data-ttu-id="0b511-108">次の例と呼ばれる構造間の変換演算子を定義する`digit`と`Byte`します。</span><span class="sxs-lookup"><span data-stu-id="0b511-108">The following example defines conversion operators between a structure called `digit` and a `Byte`.</span></span>  
  
 [!code-vb[VbVbcnProcedures#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#27)]  
  
 <span data-ttu-id="0b511-109">構造体をテストする`digit`を次のコード。</span><span class="sxs-lookup"><span data-stu-id="0b511-109">You can test the structure `digit` with the following code.</span></span>  
  
 [!code-vb[VbVbcnProcedures#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#28)]  
  
## <a name="see-also"></a><span data-ttu-id="0b511-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="0b511-110">See also</span></span>
- [<span data-ttu-id="0b511-111">演算子プロシージャ</span><span class="sxs-lookup"><span data-stu-id="0b511-111">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="0b511-112">方法: 演算子を定義します。</span><span class="sxs-lookup"><span data-stu-id="0b511-112">How to: Define an Operator</span></span>](./how-to-define-an-operator.md)
- [<span data-ttu-id="0b511-113">方法: 演算子プロシージャを呼び出す</span><span class="sxs-lookup"><span data-stu-id="0b511-113">How to: Call an Operator Procedure</span></span>](./how-to-call-an-operator-procedure.md)
- [<span data-ttu-id="0b511-114">方法: 演算子を定義するクラスを使用して、</span><span class="sxs-lookup"><span data-stu-id="0b511-114">How to: Use a Class that Defines Operators</span></span>](./how-to-use-a-class-that-defines-operators.md)
- [<span data-ttu-id="0b511-115">Operator ステートメント</span><span class="sxs-lookup"><span data-stu-id="0b511-115">Operator Statement</span></span>](../../../../visual-basic/language-reference/statements/operator-statement.md)
- [<span data-ttu-id="0b511-116">Structure ステートメント</span><span class="sxs-lookup"><span data-stu-id="0b511-116">Structure Statement</span></span>](../../../../visual-basic/language-reference/statements/structure-statement.md)
- [<span data-ttu-id="0b511-117">方法: 構造体を宣言する</span><span class="sxs-lookup"><span data-stu-id="0b511-117">How to: Declare a Structure</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [<span data-ttu-id="0b511-118">暗黙の型変換と明示的な型変換</span><span class="sxs-lookup"><span data-stu-id="0b511-118">Implicit and Explicit Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [<span data-ttu-id="0b511-119">拡大変換と縮小変換</span><span class="sxs-lookup"><span data-stu-id="0b511-119">Widening and Narrowing Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
