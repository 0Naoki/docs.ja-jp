---
title: -&gt; 演算子 (C# リファレンス)
ms.date: 07/20/2015
f1_keywords:
- ->_CSharpKeyword
helpviewer_keywords:
- member access operator (->) [C#]
- -> operator [C#]
ms.assetid: e39ccdc1-f1ff-4a92-bf1d-ac2c8c11316a
ms.openlocfilehash: fb95e508ce1339868723bcc3178851e8c1355c1f
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/08/2018
ms.locfileid: "44190229"
---
# <a name="-gt-operator-c-reference"></a><span data-ttu-id="635a4-102">-&gt; 演算子 (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="635a4-102">-&gt; Operator (C# Reference)</span></span>
<span data-ttu-id="635a4-103">`->` 演算子は、ポインターの逆参照とメンバー アクセスを組み合わせます。</span><span class="sxs-lookup"><span data-stu-id="635a4-103">The `->` operator combines pointer dereferencing and member access.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="635a4-104">コメント</span><span class="sxs-lookup"><span data-stu-id="635a4-104">Remarks</span></span>  
 <span data-ttu-id="635a4-105">次のような形式の式があるとします。</span><span class="sxs-lookup"><span data-stu-id="635a4-105">An expression of the form,</span></span>  
  
```csharp  
x->y  
```  
  
 <span data-ttu-id="635a4-106">ここで、`x` は `T*` 型のポインター、`y` は `T` のメンバーです。この式は次の式と同じです。</span><span class="sxs-lookup"><span data-stu-id="635a4-106">(where `x` is a pointer of type `T*` and `y` is a member of `T`) is equivalent to,</span></span>  
  
```csharp  
(*x).y  
```  
  
 <span data-ttu-id="635a4-107">`->` 演算子は、[unsafe](../../../csharp/language-reference/keywords/unsafe.md) とマークされているコードでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="635a4-107">The `->` operator can be used only in code that is marked as [unsafe](../../../csharp/language-reference/keywords/unsafe.md).</span></span>  
  
 <span data-ttu-id="635a4-108">`->` 演算子はオーバーロードできません。</span><span class="sxs-lookup"><span data-stu-id="635a4-108">The `->` operator cannot be overloaded.</span></span>  
  
## <a name="example"></a><span data-ttu-id="635a4-109">例</span><span class="sxs-lookup"><span data-stu-id="635a4-109">Example</span></span>  
 [!code-csharp[csRefOperators#15](../../../csharp/language-reference/operators/codesnippet/CSharp/dereference-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="635a4-110">参照</span><span class="sxs-lookup"><span data-stu-id="635a4-110">See Also</span></span>

- [<span data-ttu-id="635a4-111">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="635a4-111">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="635a4-112">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="635a4-112">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="635a4-113">C# 演算子</span><span class="sxs-lookup"><span data-stu-id="635a4-113">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
