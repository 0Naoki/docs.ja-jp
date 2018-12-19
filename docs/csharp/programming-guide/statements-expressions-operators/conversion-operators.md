---
title: 変換演算子 - C# プログラミング ガイド
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, conversion operators
- conversion operators [C#]
- operators [C#], conversion
- user-defined conversions [C#]
ms.assetid: c5ad73a3-d57b-4d2b-b4c9-24e3c2856efc
ms.openlocfilehash: a55a2148ce161deca79d8ba8e64a217e474f0284
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2018
ms.locfileid: "53236818"
---
# <a name="conversion-operators-c-programming-guide"></a><span data-ttu-id="ad784-102">変換演算子 (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="ad784-102">Conversion Operators (C# Programming Guide)</span></span>
<span data-ttu-id="ad784-103">C# を使用すると、クラスまたは構造体に関する変換を宣言し、クラスまたは構造体を別のクラスまたは構造体に、または基本型に変換することができます。</span><span class="sxs-lookup"><span data-stu-id="ad784-103">C# enables programmers to declare conversions on classes or structs so that classes or structs can be converted to and/or from other classes or structs, or basic types.</span></span> <span data-ttu-id="ad784-104">変換は演算子と同様の方法で定義され、変換先の型に由来する名前が付けられます。</span><span class="sxs-lookup"><span data-stu-id="ad784-104">Conversions are defined like operators and are named for the type to which they convert.</span></span> <span data-ttu-id="ad784-105">変換する引数の型と変換結果の型の両方ではなく一方を、含んでいる型にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ad784-105">Either the type of the argument to be converted, or the type of the result of the conversion, but not both, must be the containing type.</span></span>  
  
 [!code-csharp[csProgGuideStatements#10](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/conversion-operators_1.cs)]  
  
## <a name="conversion-operators-overview"></a><span data-ttu-id="ad784-106">変換演算子の概要</span><span class="sxs-lookup"><span data-stu-id="ad784-106">Conversion Operators Overview</span></span>  
 <span data-ttu-id="ad784-107">変換演算子には、次の特徴があります。</span><span class="sxs-lookup"><span data-stu-id="ad784-107">Conversion operators have the following properties:</span></span>  
  
-   <span data-ttu-id="ad784-108">`implicit` として宣言される変換は、必要なときに自動的に発生します。</span><span class="sxs-lookup"><span data-stu-id="ad784-108">Conversions declared as `implicit` occur automatically when it is required.</span></span>  
  
-   <span data-ttu-id="ad784-109">`explicit` として宣言される変換には、キャストの呼び出しが必要です。</span><span class="sxs-lookup"><span data-stu-id="ad784-109">Conversions declared as `explicit` require a cast to be called.</span></span>  
  
-   <span data-ttu-id="ad784-110">すべての変換は、`static` として宣言する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ad784-110">All conversions must be declared as `static`.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="ad784-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="ad784-111">Related Sections</span></span>  
 <span data-ttu-id="ad784-112">詳細情報</span><span class="sxs-lookup"><span data-stu-id="ad784-112">For more information:</span></span>  
  
-   [<span data-ttu-id="ad784-113">変換演算子の使用</span><span class="sxs-lookup"><span data-stu-id="ad784-113">Using Conversion Operators</span></span>](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md)  
  
-   [<span data-ttu-id="ad784-114">キャストと型変換</span><span class="sxs-lookup"><span data-stu-id="ad784-114">Casting and Type Conversions</span></span>](../../../csharp/programming-guide/types/casting-and-type-conversions.md)  
  
-   [<span data-ttu-id="ad784-115">方法: 構造体間にユーザー定義の変換を実装する</span><span class="sxs-lookup"><span data-stu-id="ad784-115">How to: Implement User-Defined Conversions Between Structs</span></span>](../../../csharp/programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)  
  
-   [<span data-ttu-id="ad784-116">explicit</span><span class="sxs-lookup"><span data-stu-id="ad784-116">explicit</span></span>](../../../csharp/language-reference/keywords/explicit.md)  
  
-   [<span data-ttu-id="ad784-117">implicit</span><span class="sxs-lookup"><span data-stu-id="ad784-117">implicit</span></span>](../../../csharp/language-reference/keywords/implicit.md)  
  
-   [<span data-ttu-id="ad784-118">static</span><span class="sxs-lookup"><span data-stu-id="ad784-118">static</span></span>](../../../csharp/language-reference/keywords/static.md)  
  
## <a name="see-also"></a><span data-ttu-id="ad784-119">参照</span><span class="sxs-lookup"><span data-stu-id="ad784-119">See Also</span></span>

- <xref:System.Convert>  
- [<span data-ttu-id="ad784-120">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="ad784-120">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- <span data-ttu-id="ad784-121">[Chained user-defined explicit conversions in C#](https://blogs.msdn.microsoft.com/ericlippert/2007/04/16/chained-user-defined-explicit-conversions-in-c/) (C# でのユーザー定義の明示的変換の連結)</span><span class="sxs-lookup"><span data-stu-id="ad784-121">[Chained user-defined explicit conversions in C#](https://blogs.msdn.microsoft.com/ericlippert/2007/04/16/chained-user-defined-explicit-conversions-in-c/)</span></span>
