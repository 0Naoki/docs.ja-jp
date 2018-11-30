---
title: 配列 (C# プログラミング ガイド)
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [C#]
- C# language, arrays
ms.assetid: bb79bdde-e570-4c30-adb0-1dd5759ae041
ms.openlocfilehash: 2c3f22cb2a011aea9f0fff9ef49d1fd780d6d832
ms.sourcegitcommit: 7f7664837d35320a0bad3f7e4ecd68d6624633b2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/30/2018
ms.locfileid: "52671979"
---
# <a name="arrays-c-programming-guide"></a><span data-ttu-id="9c4ca-102">配列 (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="9c4ca-102">Arrays (C# Programming Guide)</span></span>

<span data-ttu-id="9c4ca-103">配列データ構造体には、同じ型の複数の変数を格納できます。</span><span class="sxs-lookup"><span data-stu-id="9c4ca-103">You can store multiple variables of the same type in an array data structure.</span></span> <span data-ttu-id="9c4ca-104">配列は、要素の型を指定することで宣言します。</span><span class="sxs-lookup"><span data-stu-id="9c4ca-104">You declare an array by specifying the type of its elements.</span></span>  
  
 `type[] arrayName;`  
  
 <span data-ttu-id="9c4ca-105">次の例では、1 次元配列、多次元配列、およびジャグ配列を作成しています。</span><span class="sxs-lookup"><span data-stu-id="9c4ca-105">The following examples create single-dimensional, multidimensional, and jagged arrays:</span></span>  
  
 [!code-csharp[csProgGuideArrays#1](../../../csharp/programming-guide/arrays/codesnippet/CSharp/index_1.cs)]  
  
## <a name="array-overview"></a><span data-ttu-id="9c4ca-106">配列の概要</span><span class="sxs-lookup"><span data-stu-id="9c4ca-106">Array Overview</span></span>

 <span data-ttu-id="9c4ca-107">配列には、次の特徴があります。</span><span class="sxs-lookup"><span data-stu-id="9c4ca-107">An array has the following properties:</span></span>  
  
-   <span data-ttu-id="9c4ca-108">配列は、[1 次元配列](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md)、[多次元配列](../../../csharp/programming-guide/arrays/multidimensional-arrays.md)、または[ジャグ配列](../../../csharp/programming-guide/arrays/jagged-arrays.md)のいずれかになります。</span><span class="sxs-lookup"><span data-stu-id="9c4ca-108">An array can be [Single-Dimensional](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md), [Multidimensional](../../../csharp/programming-guide/arrays/multidimensional-arrays.md) or [Jagged](../../../csharp/programming-guide/arrays/jagged-arrays.md).</span></span>  
  
-   <span data-ttu-id="9c4ca-109">次元数と各次元の長さは、配列インスタンスの作成時に設定されます。</span><span class="sxs-lookup"><span data-stu-id="9c4ca-109">The number of dimensions and the length of each dimension are established when the array instance is created.</span></span> <span data-ttu-id="9c4ca-110">インスタンスの有効期間中にこれらの値を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="9c4ca-110">These values can't be changed during the lifetime of the instance.</span></span>  
  
-   <span data-ttu-id="9c4ca-111">数値配列要素の既定値はゼロに設定され、参照要素は null に設定されます。</span><span class="sxs-lookup"><span data-stu-id="9c4ca-111">The default values of numeric array elements are set to zero, and reference elements are set to null.</span></span>  
  
-   <span data-ttu-id="9c4ca-112">ジャグ配列は配列の配列です。そのため、配列要素は参照型で、`null` に初期化されます。</span><span class="sxs-lookup"><span data-stu-id="9c4ca-112">A jagged array is an array of arrays, and therefore its elements are reference types and are initialized to `null`.</span></span>  
  
-   <span data-ttu-id="9c4ca-113">配列には、ゼロから始まるインデックスが付けられます。`n` 個の要素を含む配列には、`0` から `n-1` までのインデックスが付けられます。</span><span class="sxs-lookup"><span data-stu-id="9c4ca-113">Arrays are zero indexed: an array with `n` elements is indexed from `0` to `n-1`.</span></span>  
  
-   <span data-ttu-id="9c4ca-114">配列の要素および配列型は、どのような型でもかまいません。</span><span class="sxs-lookup"><span data-stu-id="9c4ca-114">Array elements can be of any type, including an array type.</span></span>  
  
-   <span data-ttu-id="9c4ca-115">配列型は、抽象基本型 <xref:System.Array> から派生した[参照型](../../../csharp/language-reference/keywords/reference-types.md)です。</span><span class="sxs-lookup"><span data-stu-id="9c4ca-115">Array types are [reference types](../../../csharp/language-reference/keywords/reference-types.md) derived from the abstract base type <xref:System.Array>.</span></span> <span data-ttu-id="9c4ca-116">この型は <xref:System.Collections.IEnumerable> と <xref:System.Collections.Generic.IEnumerable%601> を実装するので、C# のすべての配列で [foreach](../../../csharp/language-reference/keywords/foreach-in.md) 反復処理を使用できます。</span><span class="sxs-lookup"><span data-stu-id="9c4ca-116">Since this type implements <xref:System.Collections.IEnumerable> and <xref:System.Collections.Generic.IEnumerable%601>, you can use [foreach](../../../csharp/language-reference/keywords/foreach-in.md) iteration on all arrays in C#.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="9c4ca-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="9c4ca-117">Related Sections</span></span>  
  
-   [<span data-ttu-id="9c4ca-118">オブジェクトとしての配列</span><span class="sxs-lookup"><span data-stu-id="9c4ca-118">Arrays as Objects</span></span>](../../../csharp/programming-guide/arrays/arrays-as-objects.md)  
  
-   [<span data-ttu-id="9c4ca-119">配列での foreach の使用</span><span class="sxs-lookup"><span data-stu-id="9c4ca-119">Using foreach with Arrays</span></span>](../../../csharp/programming-guide/arrays/using-foreach-with-arrays.md)  
  
-   [<span data-ttu-id="9c4ca-120">引数としての配列の受け渡し</span><span class="sxs-lookup"><span data-stu-id="9c4ca-120">Passing Arrays as Arguments</span></span>](../../../csharp/programming-guide/arrays/passing-arrays-as-arguments.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="9c4ca-121">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="9c4ca-121">C# Language Specification</span></span>

 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="9c4ca-122">参照</span><span class="sxs-lookup"><span data-stu-id="9c4ca-122">See Also</span></span>

- [<span data-ttu-id="9c4ca-123">C# プログラミングガイド</span><span class="sxs-lookup"><span data-stu-id="9c4ca-123">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="9c4ca-124">コレクション</span><span class="sxs-lookup"><span data-stu-id="9c4ca-124">Collections</span></span>](../../../csharp/programming-guide/concepts/collections.md)
