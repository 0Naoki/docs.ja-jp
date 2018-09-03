---
title: + 演算子 (C# リファレンス)
ms.date: 07/20/2015
f1_keywords:
- +_CSharpKeyword
helpviewer_keywords:
- + operator [C#]
- concatenation operator [C#]
- addition operator [C#]
ms.assetid: 93e56486-bb42-43c1-bd43-60af11e64e67
ms.openlocfilehash: b49694bc8937c58bd295f0f8e57c378802d0dfb9
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/01/2018
ms.locfileid: "43397119"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="cde3b-102">+ 演算子 (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="cde3b-102">+ Operator (C# Reference)</span></span>
<span data-ttu-id="cde3b-103">`+` 演算子には、単項演算子としての働きと 2 項演算子としての働きとがあります。</span><span class="sxs-lookup"><span data-stu-id="cde3b-103">The `+` operator can function as either a unary or a binary operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cde3b-104">コメント</span><span class="sxs-lookup"><span data-stu-id="cde3b-104">Remarks</span></span>  
 <span data-ttu-id="cde3b-105">すべての数値型には、単項 `+` 演算子が事前定義されています。</span><span class="sxs-lookup"><span data-stu-id="cde3b-105">Unary `+` operators are predefined for all numeric types.</span></span> <span data-ttu-id="cde3b-106">数値型に対する単項 `+` 演算の結果は、単にそのオペランドの値になります。</span><span class="sxs-lookup"><span data-stu-id="cde3b-106">The result of a unary `+` operation on a numeric type is just the value of the operand.</span></span>  
  
 <span data-ttu-id="cde3b-107">数値型と文字列型には、2 項 `+` 演算子が事前定義されています。</span><span class="sxs-lookup"><span data-stu-id="cde3b-107">Binary `+` operators are predefined for numeric and string types.</span></span> <span data-ttu-id="cde3b-108">数値型の場合、+ の 2 つのオペランドの合計が計算されます。</span><span class="sxs-lookup"><span data-stu-id="cde3b-108">For numeric types, + computes the sum of its two operands.</span></span> <span data-ttu-id="cde3b-109">一方または両方のオペランドが文字列型である場合、+ は、そのオペランドの文字列表現を連結します。</span><span class="sxs-lookup"><span data-stu-id="cde3b-109">When one or both operands are of type string, + concatenates the string representations of the operands.</span></span>  
  
 <span data-ttu-id="cde3b-110">2 項 `+` 演算子はデリゲート型にも備わっており、その場合、デリゲートの連結が実行されます。</span><span class="sxs-lookup"><span data-stu-id="cde3b-110">Delegate types also provide a binary `+` operator, which performs delegate concatenation.</span></span>  
  
 <span data-ttu-id="cde3b-111">単項 `+` 演算子と 2 項 `+` 演算子は、ユーザー定義型でオーバーロードすることができます。</span><span class="sxs-lookup"><span data-stu-id="cde3b-111">User-defined types can overload the unary `+` and binary `+` operators.</span></span> <span data-ttu-id="cde3b-112">整数型に対する演算は、通常、列挙型で使用できます。</span><span class="sxs-lookup"><span data-stu-id="cde3b-112">Operations on integral types are generally allowed on enumeration.</span></span> <span data-ttu-id="cde3b-113">詳細については、「[operator (C# Reference) (operator (C# リファレンス))](../../../csharp/language-reference/keywords/operator.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cde3b-113">For more information, see [operator (C# Reference)](../../../csharp/language-reference/keywords/operator.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="cde3b-114">例</span><span class="sxs-lookup"><span data-stu-id="cde3b-114">Example</span></span>  
 [!code-csharp[csRefOperators#28](../../../csharp/language-reference/operators/codesnippet/CSharp/addition-operator_1.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="cde3b-115">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="cde3b-115">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="cde3b-116">参照</span><span class="sxs-lookup"><span data-stu-id="cde3b-116">See Also</span></span>

- [<span data-ttu-id="cde3b-117">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="cde3b-117">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="cde3b-118">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="cde3b-118">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="cde3b-119">C# 演算子</span><span class="sxs-lookup"><span data-stu-id="cde3b-119">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)  
- [<span data-ttu-id="cde3b-120">演算子 (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="cde3b-120">operator (C# Reference)</span></span>](../../../csharp/language-reference/keywords/operator.md)
