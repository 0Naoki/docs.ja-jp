---
title: '方法 : ポインターのインクリメントとデクリメント (C# プログラミング ガイド)'
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], increment and decrement
- pointer expressions [C#], increment and decrement
ms.assetid: 1b8b9281-44ee-485a-9045-3db38a4b4b89
ms.openlocfilehash: c75432d88a1e96742573a6e69a4e035066a387c4
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2018
ms.locfileid: "53128337"
---
# <a name="how-to-increment-and-decrement-pointers-c-programming-guide"></a><span data-ttu-id="44cce-102">方法 : ポインターのインクリメントとデクリメント (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="44cce-102">How to: increment and decrement pointers (C# Programming Guide)</span></span>

<span data-ttu-id="44cce-103">`pointer-type*` 型のポインターの `sizeof(pointer-type)` によってポインターの位置を変更するには、インクリメント演算子 (`++`) とデクリメント演算子 (`--`) を使用します。</span><span class="sxs-lookup"><span data-stu-id="44cce-103">Use the increment and the decrement operators, `++` and `--`, to change the pointer location by `sizeof(pointer-type)` for a pointer of the type `pointer-type*`.</span></span> <span data-ttu-id="44cce-104">インクリメント式とデクリメント式には、次の書式を使用します。</span><span class="sxs-lookup"><span data-stu-id="44cce-104">The increment and decrement expressions take the following form:</span></span>  
  
```csharp
++p;  
p++;  
--p;  
p--;  
```  
  
 <span data-ttu-id="44cce-105">インクリメント演算子とデクリメント演算子は、`void*` 以外のすべての型のポインターに適用できます。</span><span class="sxs-lookup"><span data-stu-id="44cce-105">The increment and decrement operators can be applied to pointers of any type except the type `void*`.</span></span>  
  
 <span data-ttu-id="44cce-106">`pointer-type*` 型のポインターにインクリメント演算子を適用すると、ポインター変数に格納されているアドレスに `sizeof(pointer-type)` が加算されます。</span><span class="sxs-lookup"><span data-stu-id="44cce-106">The effect of applying the increment operator to a pointer of the type `pointer-type*` is to add `sizeof(pointer-type)` to the address that is contained in the pointer variable.</span></span>  
  
 <span data-ttu-id="44cce-107">`pointer-type*` 型のポインターにデクリメント演算子を適用すると、ポインター変数に格納されているアドレスから `sizeof(pointer-type)` が減算されます。</span><span class="sxs-lookup"><span data-stu-id="44cce-107">The effect of applying the decrement operator to a pointer of the type `pointer-type*` is to subtract `sizeof(pointer-type)` from the address that is contained in the pointer variable.</span></span>  
  
 <span data-ttu-id="44cce-108">演算がポインターのドメインをオーバーフローしても例外は生成されません。生じる結果は実装によって異なります。</span><span class="sxs-lookup"><span data-stu-id="44cce-108">No exceptions are generated when the operation overflows the domain of the pointer, and the result depends on the implementation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="44cce-109">例</span><span class="sxs-lookup"><span data-stu-id="44cce-109">Example</span></span>  
 <span data-ttu-id="44cce-110">この例では、ポインターを `int` のサイズだけインクリメントして、配列をステップ実行します。</span><span class="sxs-lookup"><span data-stu-id="44cce-110">In this example, you step through an array by incrementing the pointer by the size of `int`.</span></span> <span data-ttu-id="44cce-111">ステップごとに、配列要素のアドレスと内容を表示します。</span><span class="sxs-lookup"><span data-stu-id="44cce-111">With each step, you display the address and the content of the array element.</span></span>  
  
 [!code-csharp[csProgGuidePointers#3](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-increment-and-decrement-pointers_1.cs)]  
  
 [!code-csharp[csProgGuidePointers#13](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-increment-and-decrement-pointers_2.cs)]  
  
<span data-ttu-id="44cce-112">**値:0 @ アドレス:12860272**
**値:1 @ アドレス:12860276**
**値:2 @ アドレス:12860280**
**値:3 @ アドレス:12860284**
**値:4 @ アドレス:12860288**</span><span class="sxs-lookup"><span data-stu-id="44cce-112">**Value:0 @ Address:12860272**
**Value:1 @ Address:12860276**
**Value:2 @ Address:12860280**
**Value:3 @ Address:12860284**
**Value:4 @ Address:12860288**</span></span>

## <a name="see-also"></a><span data-ttu-id="44cce-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="44cce-113">See also</span></span>

- [<span data-ttu-id="44cce-114">C# プログラミングガイド</span><span class="sxs-lookup"><span data-stu-id="44cce-114">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="44cce-115">ポインター式</span><span class="sxs-lookup"><span data-stu-id="44cce-115">Pointer Expressions</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)  
- [<span data-ttu-id="44cce-116">C# 演算子</span><span class="sxs-lookup"><span data-stu-id="44cce-116">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)  
- [<span data-ttu-id="44cce-117">ポインターの操作</span><span class="sxs-lookup"><span data-stu-id="44cce-117">Manipulating Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/manipulating-pointers.md)  
- [<span data-ttu-id="44cce-118">ポインター型</span><span class="sxs-lookup"><span data-stu-id="44cce-118">Pointer types</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)  
- [<span data-ttu-id="44cce-119">型</span><span class="sxs-lookup"><span data-stu-id="44cce-119">Types</span></span>](../../../csharp/language-reference/keywords/types.md)  
- [<span data-ttu-id="44cce-120">unsafe</span><span class="sxs-lookup"><span data-stu-id="44cce-120">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)  
- [<span data-ttu-id="44cce-121">fixed ステートメント</span><span class="sxs-lookup"><span data-stu-id="44cce-121">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)  
- [<span data-ttu-id="44cce-122">stackalloc</span><span class="sxs-lookup"><span data-stu-id="44cce-122">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)
- [<span data-ttu-id="44cce-123">sizeof</span><span class="sxs-lookup"><span data-stu-id="44cce-123">sizeof</span></span>](../../../csharp/language-reference/keywords/sizeof.md)
