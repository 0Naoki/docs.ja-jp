---
title: '*= 演算子 (C# リファレンス)'
ms.date: 07/20/2015
f1_keywords:
- '*=_CSharpKeyword'
helpviewer_keywords:
- '*= operator [C#]'
- binary multiplication assignment operator (*=) [C#]
ms.assetid: 2e472155-59db-4dbf-bb94-bcccfa1a794d
ms.openlocfilehash: e47bc5c681c94ac3fc5c345c56b3814350ffa5ec
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2018
ms.locfileid: "42932351"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="6605f-102">\*= 演算子 (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="6605f-102">\*= Operator (C# Reference)</span></span>
<span data-ttu-id="6605f-103">二項乗算代入演算子です。</span><span class="sxs-lookup"><span data-stu-id="6605f-103">The binary multiplication assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6605f-104">コメント</span><span class="sxs-lookup"><span data-stu-id="6605f-104">Remarks</span></span>  
 <span data-ttu-id="6605f-105">次のような `*=` 代入演算子を使用する式があるとします</span><span class="sxs-lookup"><span data-stu-id="6605f-105">An expression using the `*=` assignment operator, such as</span></span>  
  
```csharp  
x *= y  
```  
  
 <span data-ttu-id="6605f-106">上記の式は、次の式と同じです。</span><span class="sxs-lookup"><span data-stu-id="6605f-106">is equivalent to</span></span>  
  
```csharp  
x = x * y  
```  
  
 <span data-ttu-id="6605f-107">ただし、`x` が評価されるのは 1 回だけです。</span><span class="sxs-lookup"><span data-stu-id="6605f-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="6605f-108">[\* 演算子](../../../csharp/language-reference/operators/multiplication-operator.md)は、数値型の乗算のために事前定義されています。</span><span class="sxs-lookup"><span data-stu-id="6605f-108">The [\* operator](../../../csharp/language-reference/operators/multiplication-operator.md) is predefined for numeric types to perform multiplication.</span></span>  
  
 <span data-ttu-id="6605f-109">`*=` 演算子は直接オーバーロードできませんが、ユーザー定義型は [* 演算子](../../../csharp/language-reference/operators/multiplication-operator.md)をオーバーロードできます (「[operator](../../../csharp/language-reference/keywords/operator.md)」参照)。</span><span class="sxs-lookup"><span data-stu-id="6605f-109">The `*=` operator cannot be overloaded directly, but user-defined types can overload the [* operator](../../../csharp/language-reference/operators/multiplication-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="6605f-110">例</span><span class="sxs-lookup"><span data-stu-id="6605f-110">Example</span></span>  
 [!code-csharp[csRefOperators#13](../../../csharp/language-reference/operators/codesnippet/CSharp/multiplication-assignment-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="6605f-111">参照</span><span class="sxs-lookup"><span data-stu-id="6605f-111">See Also</span></span>

- [<span data-ttu-id="6605f-112">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="6605f-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="6605f-113">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="6605f-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="6605f-114">C# 演算子</span><span class="sxs-lookup"><span data-stu-id="6605f-114">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
