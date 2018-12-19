---
title: == 演算子 - C# リファレンス
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- ==_CSharpKeyword
helpviewer_keywords:
- == operator [C#]
- equality operator [C#]
ms.assetid: 34c6b597-caa2-4855-a7cd-38ecdd11bd07
ms.openlocfilehash: c6f93be4d422fe42787e36f5b86e2cccbfc645b7
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2018
ms.locfileid: "53239015"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="c2edc-102">== 演算子 (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="c2edc-102">== Operator (C# Reference)</span></span>
<span data-ttu-id="c2edc-103">組み込みの値型の場合、等値演算子 (`==`) ではオペランドの値が等しい場合に true が返され、それ以外の場合は `false` が返されます。</span><span class="sxs-lookup"><span data-stu-id="c2edc-103">For predefined value types, the equality operator (`==`) returns true if the values of its operands are equal, `false` otherwise.</span></span> <span data-ttu-id="c2edc-104">[string](../../../csharp/language-reference/keywords/string.md) 以外の参照型の場合、`==` では 2 つのオペランドが同じオブジェクトを参照する場合に `true` が返されます。</span><span class="sxs-lookup"><span data-stu-id="c2edc-104">For reference types other than [string](../../../csharp/language-reference/keywords/string.md), `==` returns `true` if its two operands refer to the same object.</span></span> <span data-ttu-id="c2edc-105">`string` 型の場合は、`==` は文字列の値を比較します。</span><span class="sxs-lookup"><span data-stu-id="c2edc-105">For the `string` type, `==` compares the values of the strings.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c2edc-106">コメント</span><span class="sxs-lookup"><span data-stu-id="c2edc-106">Remarks</span></span>  
 <span data-ttu-id="c2edc-107">ユーザー定義の値の型は `==` 演算子をオーバーロードできます (「[演算子](../../../csharp/language-reference/keywords/operator.md)」を参照)。</span><span class="sxs-lookup"><span data-stu-id="c2edc-107">User-defined value types can overload the `==` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="c2edc-108">ユーザー定義参照型もオーバーロードはできますが、既定では、組み込み参照型とユーザー定義参照型のいずれに対しても `==` は前述のとおりに機能します。</span><span class="sxs-lookup"><span data-stu-id="c2edc-108">So can user-defined reference types, although by default `==` behaves as described above for both predefined and user-defined reference types.</span></span> <span data-ttu-id="c2edc-109">`==` をオーバーロードする場合は、[!=](../../../csharp/language-reference/operators/not-equal-operator.md) もオーバーロードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c2edc-109">If `==` is overloaded, [!=](../../../csharp/language-reference/operators/not-equal-operator.md) must also be overloaded.</span></span> <span data-ttu-id="c2edc-110">整数型に対する演算は、通常、列挙型で使用できます。</span><span class="sxs-lookup"><span data-stu-id="c2edc-110">Operations on integral types are generally allowed on enumeration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c2edc-111">例</span><span class="sxs-lookup"><span data-stu-id="c2edc-111">Example</span></span>  
 [!code-csharp[csRefOperators#36](../../../csharp/language-reference/operators/codesnippet/CSharp/equality-comparison-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="c2edc-112">参照</span><span class="sxs-lookup"><span data-stu-id="c2edc-112">See Also</span></span>

- [<span data-ttu-id="c2edc-113">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="c2edc-113">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="c2edc-114">C# プログラミングガイド</span><span class="sxs-lookup"><span data-stu-id="c2edc-114">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="c2edc-115">C# 演算子</span><span class="sxs-lookup"><span data-stu-id="c2edc-115">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
