---
title: シーケンスの要素の並べ替え
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d59b93a9-50c8-4770-a114-d902f6a0ea76
ms.openlocfilehash: 33473eadefabc2bcbbb552d225d021eae4bed0bb
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59169014"
---
# <a name="sort-elements-in-a-sequence"></a><span data-ttu-id="5d60f-102">シーケンスの要素の並べ替え</span><span class="sxs-lookup"><span data-stu-id="5d60f-102">Sort Elements in a Sequence</span></span>
<span data-ttu-id="5d60f-103">1 つ以上のキーに従ってシーケンスを並べ替えるには、<xref:System.Linq.Enumerable.OrderBy%2A> 演算子を使用します。</span><span class="sxs-lookup"><span data-stu-id="5d60f-103">Use the <xref:System.Linq.Enumerable.OrderBy%2A> operator to sort a sequence according to one or more keys.</span></span>  
  
> [!NOTE]
>  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="5d60f-104">などの単純なプリミティブ型による順序付けをサポートするように設計が`string`、`int`など。</span><span class="sxs-lookup"><span data-stu-id="5d60f-104">is designed to support ordering by simple primitive types, such as `string`, `int`, and so on.</span></span> <span data-ttu-id="5d60f-105">匿名型のように複数の値を持つ複雑なクラスでの順序付けはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="5d60f-105">It does not support ordering for complex multi-valued classes, such as anonymous types.</span></span> <span data-ttu-id="5d60f-106">また、`byte` データ型もサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="5d60f-106">It also does not support `byte` datatypes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5d60f-107">例</span><span class="sxs-lookup"><span data-stu-id="5d60f-107">Example</span></span>  
 <span data-ttu-id="5d60f-108">次の例は、`Employees` を入社日の順に並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="5d60f-108">The following example sorts `Employees` by date of hire.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#20](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#20)]
 [!code-vb[DLinqQueryExamples#20](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#20)]  
  
## <a name="example"></a><span data-ttu-id="5d60f-109">例</span><span class="sxs-lookup"><span data-stu-id="5d60f-109">Example</span></span>  
 <span data-ttu-id="5d60f-110">次の例は、`where` を使用して、`Orders` に出荷された `London` を運送料の順に並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="5d60f-110">The following example uses `where` to sort `Orders` shipped to `London` by freight.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#21](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#21)]
 [!code-vb[DLinqQueryExamples#21](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#21)]  
  
## <a name="example"></a><span data-ttu-id="5d60f-111">例</span><span class="sxs-lookup"><span data-stu-id="5d60f-111">Example</span></span>  
 <span data-ttu-id="5d60f-112">次の例は、`Products` を単価の高い順に並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="5d60f-112">The following example sorts `Products` by unit price from highest to lowest.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#22](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#22)]
 [!code-vb[DLinqQueryExamples#22](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#22)]  
  
## <a name="example"></a><span data-ttu-id="5d60f-113">例</span><span class="sxs-lookup"><span data-stu-id="5d60f-113">Example</span></span>  
 <span data-ttu-id="5d60f-114">次の例は、`OrderBy` で複数のフィールドを使用して、`Customers` を最初に都市の順に、次に連絡先の順に並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="5d60f-114">The following example uses a compound `OrderBy` to sort `Customers` by city and then by contact name.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#24](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#24)]
 [!code-vb[DLinqQueryExamples#24](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#24)]  
  
## <a name="example"></a><span data-ttu-id="5d60f-115">例</span><span class="sxs-lookup"><span data-stu-id="5d60f-115">Example</span></span>  
 <span data-ttu-id="5d60f-116">次の例は、`EmployeeID 1` からの注文を、最初に出荷先国の順に、次に運送料の高い順に並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="5d60f-116">The following example sorts Orders from `EmployeeID 1` by ship-to country, and then by highest to lowest freight.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#25](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#25)]
 [!code-vb[DLinqQueryExamples#25](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#25)]  
  
## <a name="example"></a><span data-ttu-id="5d60f-117">例</span><span class="sxs-lookup"><span data-stu-id="5d60f-117">Example</span></span>  
 <span data-ttu-id="5d60f-118">次の例は、<xref:System.Linq.Enumerable.OrderBy%2A> 演算子、<xref:System.Linq.Enumerable.Max%2A> 演算子、および <xref:System.Linq.Enumerable.GroupBy%2A> 演算子を組み合わせて、各カテゴリで単価の最も高い `Products` を特定し、そのグループをカテゴリ ID の順に並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="5d60f-118">The following example combines <xref:System.Linq.Enumerable.OrderBy%2A>, <xref:System.Linq.Enumerable.Max%2A>, and <xref:System.Linq.Enumerable.GroupBy%2A> operators to find the `Products` that have the highest unit price in each category, and then sorts the group by category id.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#26](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#26)]
 [!code-vb[DLinqQueryExamples#26](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#26)]  
  
 <span data-ttu-id="5d60f-119">Northwind サンプル データベースに対して前のクエリを実行すると、結果は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="5d60f-119">If you run the previous query against the Northwind sample database, the results will resemble the following:</span></span>  
  
 `1`  
  
 `Côte de Blaye`  
  
 `2`  
  
 `Vegie-spread`  
  
 `3`  
  
 `Sir Rodney's Marmalade`  
  
 `4`  
  
 `Raclette Courdavault`  
  
 `5`  
  
 `Gnocchi di nonna Alice`  
  
 `6`  
  
 `Thüringer Rostbratwurst`  
  
 `7`  
  
 `Manjimup Dried Apples`  
  
 `8`  
  
 `Carnarvon Tigers`  
  
## <a name="see-also"></a><span data-ttu-id="5d60f-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="5d60f-120">See also</span></span>

- [<span data-ttu-id="5d60f-121">クエリの例</span><span class="sxs-lookup"><span data-stu-id="5d60f-121">Query Examples</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)
- [<span data-ttu-id="5d60f-122">サンプル データベースのダウンロード</span><span class="sxs-lookup"><span data-stu-id="5d60f-122">Downloading Sample Databases</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)
