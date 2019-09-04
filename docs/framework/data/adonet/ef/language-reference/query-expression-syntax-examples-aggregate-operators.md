---
title: クエリ式の構文例:集計演算子
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d729120c-4c1b-4f34-bbe9-33694fca2dde
ms.openlocfilehash: 5090616705c799f2905226b4892fa1fbe50bfbf3
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2019
ms.locfileid: "70249533"
---
# <a name="query-expression-syntax-examples-aggregate-operators"></a><span data-ttu-id="0f5bb-102">クエリ式の構文例:集計演算子</span><span class="sxs-lookup"><span data-stu-id="0f5bb-102">Query Expression Syntax Examples: Aggregate Operators</span></span>
<span data-ttu-id="0f5bb-103">このトピックの例では<xref:System.Linq.Enumerable.Average%2A> <xref:System.Linq.Enumerable.Max%2A>、クエリ式の構文を使用<xref:System.Linq.Enumerable.Min%2A>して<xref:System.Linq.Enumerable.Sum%2A> 、 <xref:System.Linq.Enumerable.Count%2A>、、、、およびの各メソッドを使用して、 [AdventureWorks Sales Model](https://archive.codeplex.com/?p=msftdbprodsamples)に対してクエリを実行する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="0f5bb-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Count%2A>, <xref:System.Linq.Enumerable.Max%2A>, <xref:System.Linq.Enumerable.Min%2A>, and <xref:System.Linq.Enumerable.Sum%2A> methods to query the [AdventureWorks Sales Model](https://archive.codeplex.com/?p=msftdbprodsamples) using query expression syntax.</span></span> <span data-ttu-id="0f5bb-104">これらの例で使用されている、AdventureWorks Sales Model は、AdventureWorks サンプル データベースの Contact、Address、Product、SalesOrderHeader、SalesOrderDetail の各テーブルから作成されています。</span><span class="sxs-lookup"><span data-stu-id="0f5bb-104">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="0f5bb-105">このトピックの例では、次`using` / `Imports`のステートメントを使用します。</span><span class="sxs-lookup"><span data-stu-id="0f5bb-105">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="average"></a><span data-ttu-id="0f5bb-106">平均</span><span class="sxs-lookup"><span data-stu-id="0f5bb-106">Average</span></span>  
  
### <a name="example"></a><span data-ttu-id="0f5bb-107">例</span><span class="sxs-lookup"><span data-stu-id="0f5bb-107">Example</span></span>  
 <span data-ttu-id="0f5bb-108">次の例では、<xref:System.Linq.Enumerable.Average%2A> メソッドを使用して、各スタイルの製品の平均表示価格を取得します。</span><span class="sxs-lookup"><span data-stu-id="0f5bb-108">The following example uses the <xref:System.Linq.Enumerable.Average%2A> method to find the average list price of the products of each style.</span></span>  
  
 [!code-csharp[DP L2E Examples#Average2_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#average2_mq)]
 [!code-vb[DP L2E Examples#Average2_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#average2_mq)]  
  
### <a name="example"></a><span data-ttu-id="0f5bb-109">例</span><span class="sxs-lookup"><span data-stu-id="0f5bb-109">Example</span></span>  
 <span data-ttu-id="0f5bb-110">次の例では、<xref:System.Linq.Enumerable.Average%2A> を使用して、それぞれの連絡先 ID について平均合計支払額を取得します。</span><span class="sxs-lookup"><span data-stu-id="0f5bb-110">The following example uses <xref:System.Linq.Enumerable.Average%2A> to get the average total due for each contact ID.</span></span>  
  
 [!code-csharp[DP L2E Examples#AverageGrouped_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#averagegrouped_mq)]
 [!code-vb[DP L2E Examples#AverageGrouped_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#averagegrouped_mq)]  
  
### <a name="example"></a><span data-ttu-id="0f5bb-111">例</span><span class="sxs-lookup"><span data-stu-id="0f5bb-111">Example</span></span>  
 <span data-ttu-id="0f5bb-112">次の例では、<xref:System.Linq.Enumerable.Average%2A> を使用して、それぞれの連絡先について合計支払額が平均値の注文を取得します。</span><span class="sxs-lookup"><span data-stu-id="0f5bb-112">The following example uses <xref:System.Linq.Enumerable.Average%2A> to get the orders with the average total due for each contact.</span></span>  
  
 [!code-csharp[DP L2E Examples#AverageElements_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#averageelements_mq)]
 [!code-vb[DP L2E Examples#AverageElements_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#averageelements_mq)]  
  
## <a name="count"></a><span data-ttu-id="0f5bb-113">カウント</span><span class="sxs-lookup"><span data-stu-id="0f5bb-113">Count</span></span>  
  
### <a name="example"></a><span data-ttu-id="0f5bb-114">例</span><span class="sxs-lookup"><span data-stu-id="0f5bb-114">Example</span></span>  
 <span data-ttu-id="0f5bb-115">次の例では、<xref:System.Linq.Enumerable.Count%2A> を使用して、連絡先 ID の一覧と、それぞれの注文数を返します。</span><span class="sxs-lookup"><span data-stu-id="0f5bb-115">The following example uses <xref:System.Linq.Enumerable.Count%2A> to return a list of contact IDs and how many orders each has.</span></span>  
  
 [!code-csharp[DP L2E Examples#CountNested](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#countnested)]
 [!code-vb[DP L2E Examples#CountNested](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#countnested)]  
  
### <a name="example"></a><span data-ttu-id="0f5bb-116">例</span><span class="sxs-lookup"><span data-stu-id="0f5bb-116">Example</span></span>  
 <span data-ttu-id="0f5bb-117">次の例では、製品を色でグループ分けし、<xref:System.Linq.Enumerable.Count%2A> を使用してそれぞれの色グループに含まれる製品の数を返します。</span><span class="sxs-lookup"><span data-stu-id="0f5bb-117">The following example groups products by color and uses <xref:System.Linq.Enumerable.Count%2A> to return the number of products in each color group.</span></span>  
  
 [!code-csharp[DP L2E Examples#CountGrouped](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#countgrouped)]
 [!code-vb[DP L2E Examples#CountGrouped](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#countgrouped)]  
  
## <a name="max"></a><span data-ttu-id="0f5bb-118">Max</span><span class="sxs-lookup"><span data-stu-id="0f5bb-118">Max</span></span>  
  
### <a name="example"></a><span data-ttu-id="0f5bb-119">例</span><span class="sxs-lookup"><span data-stu-id="0f5bb-119">Example</span></span>  
 <span data-ttu-id="0f5bb-120">次の例では、<xref:System.Linq.Enumerable.Max%2A> メソッドを使用して、それぞれの連絡先 ID について最大合計支払額を取得します。</span><span class="sxs-lookup"><span data-stu-id="0f5bb-120">The following example uses the <xref:System.Linq.Enumerable.Max%2A> method to get the largest total due for each contact ID.</span></span>  
  
 [!code-csharp[DP L2E Examples#MaxGrouped_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#maxgrouped_mq)]
 [!code-vb[DP L2E Examples#MaxGrouped_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#maxgrouped_mq)]  
  
### <a name="example"></a><span data-ttu-id="0f5bb-121">例</span><span class="sxs-lookup"><span data-stu-id="0f5bb-121">Example</span></span>  
 <span data-ttu-id="0f5bb-122">次の例では、<xref:System.Linq.Enumerable.Max%2A> メソッドを使用して、それぞれの連絡先 ID について合計支払額が最大の注文を取得します。</span><span class="sxs-lookup"><span data-stu-id="0f5bb-122">The following example uses the <xref:System.Linq.Enumerable.Max%2A> method to get the orders with the largest total due for each contact ID.</span></span>  
  
 [!code-csharp[DP L2E Examples#MaxElements_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#maxelements_mq)]
 [!code-vb[DP L2E Examples#MaxElements_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#maxelements_mq)]  
  
## <a name="min"></a><span data-ttu-id="0f5bb-123">Min</span><span class="sxs-lookup"><span data-stu-id="0f5bb-123">Min</span></span>  
  
### <a name="example"></a><span data-ttu-id="0f5bb-124">例</span><span class="sxs-lookup"><span data-stu-id="0f5bb-124">Example</span></span>  
 <span data-ttu-id="0f5bb-125">次の例では、<xref:System.Linq.Enumerable.Min%2A> メソッドを使用して、それぞれの連絡先 ID について最小合計支払額を取得します。</span><span class="sxs-lookup"><span data-stu-id="0f5bb-125">The following example uses the <xref:System.Linq.Enumerable.Min%2A> method to get the smallest total due for each contact ID.</span></span>  
  
 [!code-csharp[DP L2E Examples#MinGrouped_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#mingrouped_mq)]
 [!code-vb[DP L2E Examples#MinGrouped_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#mingrouped_mq)]  
  
### <a name="example"></a><span data-ttu-id="0f5bb-126">例</span><span class="sxs-lookup"><span data-stu-id="0f5bb-126">Example</span></span>  
 <span data-ttu-id="0f5bb-127">次の例では、<xref:System.Linq.Enumerable.Min%2A> メソッドを使用して、それぞれの連絡先について合計支払額が最小の注文を取得します。</span><span class="sxs-lookup"><span data-stu-id="0f5bb-127">The following example uses the <xref:System.Linq.Enumerable.Min%2A> method to get the orders with the smallest total due for each contact.</span></span>  
  
 [!code-csharp[DP L2E Examples#MinElements_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#minelements_mq)]
 [!code-vb[DP L2E Examples#MinElements_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#minelements_mq)]  
  
## <a name="sum"></a><span data-ttu-id="0f5bb-128">Sum</span><span class="sxs-lookup"><span data-stu-id="0f5bb-128">Sum</span></span>  
  
### <a name="example"></a><span data-ttu-id="0f5bb-129">例</span><span class="sxs-lookup"><span data-stu-id="0f5bb-129">Example</span></span>  
 <span data-ttu-id="0f5bb-130">次の例では、<xref:System.Linq.Enumerable.Sum%2A> メソッドを使用して、それぞれの連絡先 ID について合計支払額を取得します。</span><span class="sxs-lookup"><span data-stu-id="0f5bb-130">The following example uses the <xref:System.Linq.Enumerable.Sum%2A> method to get the total due for each contact ID.</span></span>  
  
 [!code-csharp[DP L2E Examples#SumGrouped_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#sumgrouped_mq)]
 [!code-vb[DP L2E Examples#SumGrouped_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#sumgrouped_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="0f5bb-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="0f5bb-131">See also</span></span>

- [<span data-ttu-id="0f5bb-132">LINQ to Entities でのクエリ</span><span class="sxs-lookup"><span data-stu-id="0f5bb-132">Queries in LINQ to Entities</span></span>](queries-in-linq-to-entities.md)
