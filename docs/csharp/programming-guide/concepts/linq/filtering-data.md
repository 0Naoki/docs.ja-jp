---
title: データのフィルター処理 (C#)
ms.date: 07/20/2015
ms.assetid: fbaece0d-0f23-47f7-89c5-f3ea8db692b6
ms.openlocfilehash: df2f9f1bab7767365be65dbb60fb4af324ae3dab
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "43503298"
---
# <a name="filtering-data-c"></a><span data-ttu-id="50153-102">データのフィルター処理 (C#)</span><span class="sxs-lookup"><span data-stu-id="50153-102">Filtering Data (C#)</span></span>
<span data-ttu-id="50153-103">フィルター処理とは、特定の条件を満たす要素のみが含まれるように結果セットを限定する操作のことです。</span><span class="sxs-lookup"><span data-stu-id="50153-103">Filtering refers to the operation of restricting the result set to contain only those elements that satisfy a specified condition.</span></span> <span data-ttu-id="50153-104">選択とも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="50153-104">It is also known as selection.</span></span>  
  
 <span data-ttu-id="50153-105">次の図は、文字のシーケンスをフィルター処理した結果を示したものです。</span><span class="sxs-lookup"><span data-stu-id="50153-105">The following illustration shows the results of filtering a sequence of characters.</span></span> <span data-ttu-id="50153-106">フィルター処理操作の述語では、文字が "A" でなければならないことが指定されています。</span><span class="sxs-lookup"><span data-stu-id="50153-106">The predicate for the filtering operation specifies that the character must be 'A'.</span></span>  
  
 <span data-ttu-id="50153-107">![LINQ フィルター処理操作](../../../../csharp/programming-guide/concepts/linq/media/linq_filter.png "LINQ_Filter")</span><span class="sxs-lookup"><span data-stu-id="50153-107">![LINQ Filtering Operation](../../../../csharp/programming-guide/concepts/linq/media/linq_filter.png "LINQ_Filter")</span></span>  
  
 <span data-ttu-id="50153-108">次のセクションでは、選択を実行する標準クエリ演算子メソッドの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="50153-108">The standard query operator methods that perform selection are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="50153-109">メソッド</span><span class="sxs-lookup"><span data-stu-id="50153-109">Methods</span></span>  
  
|<span data-ttu-id="50153-110">メソッド名</span><span class="sxs-lookup"><span data-stu-id="50153-110">Method Name</span></span>|<span data-ttu-id="50153-111">説明</span><span class="sxs-lookup"><span data-stu-id="50153-111">Description</span></span>|<span data-ttu-id="50153-112">C# のクエリ式の構文</span><span class="sxs-lookup"><span data-stu-id="50153-112">C# Query Expression Syntax</span></span>|<span data-ttu-id="50153-113">説明</span><span class="sxs-lookup"><span data-stu-id="50153-113">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="50153-114">OfType</span><span class="sxs-lookup"><span data-stu-id="50153-114">OfType</span></span>|<span data-ttu-id="50153-115">指定した型にキャストできるかどうかにより、値を選択します。</span><span class="sxs-lookup"><span data-stu-id="50153-115">Selects values, depending on their ability to be cast to a specified type.</span></span>|<span data-ttu-id="50153-116">該当なし。</span><span class="sxs-lookup"><span data-stu-id="50153-116">Not applicable.</span></span>|<xref:System.Linq.Enumerable.OfType%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OfType%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="50153-117">Where</span><span class="sxs-lookup"><span data-stu-id="50153-117">Where</span></span>|<span data-ttu-id="50153-118">述語関数に基づいて値を選択します。</span><span class="sxs-lookup"><span data-stu-id="50153-118">Selects values that are based on a predicate function.</span></span>|`where`|<xref:System.Linq.Enumerable.Where%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Where%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-example"></a><span data-ttu-id="50153-119">クエリ式の構文例</span><span class="sxs-lookup"><span data-stu-id="50153-119">Query Expression Syntax Example</span></span>  
 <span data-ttu-id="50153-120">次の例では、`where` 句を使って、配列から特定の長さを持つ文字列をフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="50153-120">The following example uses the `where` clause to filter from an array those strings that have a specific length.</span></span>  
  
```csharp  
string[] words = { "the", "quick", "brown", "fox", "jumps" };  
  
IEnumerable<string> query = from word in words  
                            where word.Length == 3  
                            select word;  
  
foreach (string str in query)  
    Console.WriteLine(str);  
  
/* This code produces the following output:  
  
    the  
    fox  
*/  
```  
  
## <a name="see-also"></a><span data-ttu-id="50153-121">参照</span><span class="sxs-lookup"><span data-stu-id="50153-121">See Also</span></span>

- <xref:System.Linq>  
- [<span data-ttu-id="50153-122">標準クエリ演算子の概要 (C#)</span><span class="sxs-lookup"><span data-stu-id="50153-122">Standard Query Operators Overview (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)  
- [<span data-ttu-id="50153-123">where 句</span><span class="sxs-lookup"><span data-stu-id="50153-123">where clause</span></span>](../../../../csharp/language-reference/keywords/where-clause.md)  
- [<span data-ttu-id="50153-124">方法: 実行時に述語フィルターを動的に指定する</span><span class="sxs-lookup"><span data-stu-id="50153-124">How to: Dynamically Specify Predicate Filters at Runtime</span></span>](../../../../csharp/programming-guide/linq-query-expressions/how-to-dynamically-specify-predicate-filters-at-runtime.md)  
- [<span data-ttu-id="50153-125">方法: リフレクションを使用してアセンブリのメタデータを照会する (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="50153-125">How to: Query An Assembly's Metadata with Reflection (LINQ) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-query-an-assembly-s-metadata-with-reflection-linq.md)  
- [<span data-ttu-id="50153-126">方法: 指定された属性または名前のファイルを照会する (C#)</span><span class="sxs-lookup"><span data-stu-id="50153-126">How to: Query for Files with a Specified Attribute or Name (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-query-for-files-with-a-specified-attribute-or-name.md)  
- [<span data-ttu-id="50153-127">方法: 任意の単語またはフィールドを基準にテキスト データの並べ替えまたはフィルター処理を実行する (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="50153-127">How to: Sort or Filter Text Data by Any Word or Field (LINQ) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)
