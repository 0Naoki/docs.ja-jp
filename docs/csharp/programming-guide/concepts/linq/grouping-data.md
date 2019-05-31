---
title: データのグループ化 (C#)
ms.date: 07/20/2015
ms.assetid: e414e9e4-343a-4e6e-858f-4a30c5e64492
ms.openlocfilehash: a85babc43f673711fe1bdfa5cec1836a5073c785
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64753922"
---
# <a name="grouping-data-c"></a><span data-ttu-id="5f6c0-102">データのグループ化 (C#)</span><span class="sxs-lookup"><span data-stu-id="5f6c0-102">Grouping Data (C#)</span></span>
<span data-ttu-id="5f6c0-103">グループ化とは、各グループの要素が共通の属性を持つようにデータをグループに分ける操作を指します。</span><span class="sxs-lookup"><span data-stu-id="5f6c0-103">Grouping refers to the operation of putting data into groups so that the elements in each group share a common attribute.</span></span>  
  
 <span data-ttu-id="5f6c0-104">次の図は、文字のシーケンスをグループ化した結果を示しています。</span><span class="sxs-lookup"><span data-stu-id="5f6c0-104">The following illustration shows the results of grouping a sequence of characters.</span></span> <span data-ttu-id="5f6c0-105">各グループのキーは文字です。</span><span class="sxs-lookup"><span data-stu-id="5f6c0-105">The key for each group is the character.</span></span>  
  
 ![LINQ グループ化操作を示す図。](./media/grouping-data/linq-group-operation.png)  
  
 <span data-ttu-id="5f6c0-107">次のセクションでは、データ要素をグループ化する標準クエリ演算子メソッドの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="5f6c0-107">The standard query operator methods that group data elements are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5f6c0-108">メソッド</span><span class="sxs-lookup"><span data-stu-id="5f6c0-108">Methods</span></span>  
  
|<span data-ttu-id="5f6c0-109">メソッド名</span><span class="sxs-lookup"><span data-stu-id="5f6c0-109">Method Name</span></span>|<span data-ttu-id="5f6c0-110">説明</span><span class="sxs-lookup"><span data-stu-id="5f6c0-110">Description</span></span>|<span data-ttu-id="5f6c0-111">C# のクエリ式の構文</span><span class="sxs-lookup"><span data-stu-id="5f6c0-111">C# Query Expression Syntax</span></span>|<span data-ttu-id="5f6c0-112">説明</span><span class="sxs-lookup"><span data-stu-id="5f6c0-112">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="5f6c0-113">GroupBy</span><span class="sxs-lookup"><span data-stu-id="5f6c0-113">GroupBy</span></span>|<span data-ttu-id="5f6c0-114">共通の属性を共有する要素をグループ化します。</span><span class="sxs-lookup"><span data-stu-id="5f6c0-114">Groups elements that share a common attribute.</span></span> <span data-ttu-id="5f6c0-115">各グループは <xref:System.Linq.IGrouping%602> オブジェクトによって表されます。</span><span class="sxs-lookup"><span data-stu-id="5f6c0-115">Each group is represented by an <xref:System.Linq.IGrouping%602> object.</span></span>|`group … by`<br /><br /> <span data-ttu-id="5f6c0-116">- または -</span><span class="sxs-lookup"><span data-stu-id="5f6c0-116">-or-</span></span><br /><br /> `group … by … into …`|<xref:System.Linq.Enumerable.GroupBy%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.GroupBy%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="5f6c0-117">ToLookup</span><span class="sxs-lookup"><span data-stu-id="5f6c0-117">ToLookup</span></span>|<span data-ttu-id="5f6c0-118">キー セレクター関数に基づいて、<xref:System.Linq.Lookup%602> (一対多の辞書) に要素を挿入します。</span><span class="sxs-lookup"><span data-stu-id="5f6c0-118">Inserts elements into a <xref:System.Linq.Lookup%602> (a one-to-many dictionary) based on a key selector function.</span></span>|<span data-ttu-id="5f6c0-119">該当なし。</span><span class="sxs-lookup"><span data-stu-id="5f6c0-119">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-example"></a><span data-ttu-id="5f6c0-120">クエリ式の構文例</span><span class="sxs-lookup"><span data-stu-id="5f6c0-120">Query Expression Syntax Example</span></span>  
 <span data-ttu-id="5f6c0-121">次のコード例では、`group by` 句を使用して、偶数か奇数かによってリスト内の整数をグループ化します。</span><span class="sxs-lookup"><span data-stu-id="5f6c0-121">The following code example uses the `group by` clause to group integers in a list according to whether they are even or odd.</span></span>  
  
```csharp  
List<int> numbers = new List<int>() { 35, 44, 200, 84, 3987, 4, 199, 329, 446, 208 };  
  
IEnumerable<IGrouping<int, int>> query = from number in numbers  
                                         group number by number % 2;  
  
foreach (var group in query)  
{  
    Console.WriteLine(group.Key == 0 ? "\nEven numbers:" : "\nOdd numbers:");  
    foreach (int i in group)  
        Console.WriteLine(i);  
}  
  
/* This code produces the following output:  
  
    Odd numbers:  
    35  
    3987  
    199  
    329  
  
    Even numbers:  
    44  
    200  
    84  
    4  
    446  
    208  
*/  
```  
  
## <a name="see-also"></a><span data-ttu-id="5f6c0-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="5f6c0-122">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="5f6c0-123">標準クエリ演算子の概要 (C#)</span><span class="sxs-lookup"><span data-stu-id="5f6c0-123">Standard Query Operators Overview (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="5f6c0-124">group 句</span><span class="sxs-lookup"><span data-stu-id="5f6c0-124">group clause</span></span>](../../../../csharp/language-reference/keywords/group-clause.md)
- [<span data-ttu-id="5f6c0-125">方法: 入れ子になったグループの作成</span><span class="sxs-lookup"><span data-stu-id="5f6c0-125">How to: Create a Nested Group</span></span>](../../../../csharp/programming-guide/linq-query-expressions/how-to-create-a-nested-group.md)
- [<span data-ttu-id="5f6c0-126">方法: 拡張子別にファイルをグループ化する (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="5f6c0-126">How to: Group Files by Extension (LINQ) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-group-files-by-extension-linq.md)
- [<span data-ttu-id="5f6c0-127">方法: クエリ結果のグループ化</span><span class="sxs-lookup"><span data-stu-id="5f6c0-127">How to: Group Query Results</span></span>](../../../../csharp/programming-guide/linq-query-expressions/how-to-group-query-results.md)
- [<span data-ttu-id="5f6c0-128">方法: グループ化操作でのサブクエリの実行</span><span class="sxs-lookup"><span data-stu-id="5f6c0-128">How to: Perform a Subquery on a Grouping Operation</span></span>](../../../../csharp/programming-guide/linq-query-expressions/how-to-perform-a-subquery-on-a-grouping-operation.md)
- [<span data-ttu-id="5f6c0-129">方法: グループを使用して 1 つのファイルを複数のファイルに分割する (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="5f6c0-129">How to: Split a File Into Many Files by Using Groups (LINQ) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-split-a-file-into-many-files-by-using-groups-linq.md)
