---
title: 'クエリ式の構文例 : 制限 (LINQ to DataSet)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1daf42c2-c9f4-4cda-b291-7641b9c6d3fe
ms.openlocfilehash: 556b1cc31f42cecc19492412120b31da83eff609
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2018
ms.locfileid: "43800558"
---
# <a name="query-expression-syntax-examples-restriction-linq-to-dataset"></a><span data-ttu-id="2ede7-102">クエリ式の構文例 : 制限 (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="2ede7-102">Query Expression Syntax Examples: Restriction (LINQ to DataSet)</span></span>
<span data-ttu-id="2ede7-103">このトピックでは、<xref:System.Linq.Enumerable.Where%2A> メソッドで、クエリ式の構文を使って <xref:System.Data.DataSet> に対するクエリを実行する例を紹介しています。</span><span class="sxs-lookup"><span data-stu-id="2ede7-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Where%2A> method to query a <xref:System.Data.DataSet> using the query expression syntax.</span></span>  
  
 <span data-ttu-id="2ede7-104">`FillDataSet`でこれらの例で使用されるメソッドが指定された[をデータセットにデータを読み込む](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)します。</span><span class="sxs-lookup"><span data-stu-id="2ede7-104">The `FillDataSet` method used in these examples is specified in [Loading Data Into a DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span></span>  
  
 <span data-ttu-id="2ede7-105">このトピックの例には、AdventureWorks サンプル データベースの Contact、Address、Product、SalesOrderHeader、SalesOrderDetail の各テーブルが使用されています。</span><span class="sxs-lookup"><span data-stu-id="2ede7-105">The examples in this topic use the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="2ede7-106">このトピックの例では、次を使用して`using` / `Imports`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="2ede7-106">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
[!code-csharp[DP LINQ to DataSetExamples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]        
  
 <span data-ttu-id="2ede7-107">詳細については、次を参照してください。[方法: LINQ to Visual Studio でデータセット プロジェクトを作成](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md)です。</span><span class="sxs-lookup"><span data-stu-id="2ede7-107">For more information, see [How to: Create a LINQ to DataSet Project In Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).</span></span>  
  
## <a name="where"></a><span data-ttu-id="2ede7-108">Where</span><span class="sxs-lookup"><span data-stu-id="2ede7-108">Where</span></span>  
  
### <a name="example"></a><span data-ttu-id="2ede7-109">例</span><span class="sxs-lookup"><span data-stu-id="2ede7-109">Example</span></span>  
 <span data-ttu-id="2ede7-110">この例では、すべてのオンライン注文が返されます。</span><span class="sxs-lookup"><span data-stu-id="2ede7-110">This example returns all online orders.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Where1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#where1)]  
 [!code-vb[DP LINQ to DataSet Examples#Where1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#where1)]     
  
### <a name="example"></a><span data-ttu-id="2ede7-111">例</span><span class="sxs-lookup"><span data-stu-id="2ede7-111">Example</span></span>  
 <span data-ttu-id="2ede7-112">この例では、注文数量が 3 個以上で 5 個以下の注文が返されます。</span><span class="sxs-lookup"><span data-stu-id="2ede7-112">This example returns the orders where the order quantity is greater than 2 and less than 6.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Where2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#where2)]  
 [!code-vb[DP LINQ to DataSet Examples#Where2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#where2)]     
  
### <a name="example"></a><span data-ttu-id="2ede7-113">例</span><span class="sxs-lookup"><span data-stu-id="2ede7-113">Example</span></span>  
 <span data-ttu-id="2ede7-114">この例では、色が赤の製品がすべて返されます。</span><span class="sxs-lookup"><span data-stu-id="2ede7-114">This example returns all red colored products.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Where3](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#where3)]  
 [!code-vb[DP LINQ to DataSet Examples#Where3](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#where3)]     
  
### <a name="example"></a><span data-ttu-id="2ede7-115">例</span><span class="sxs-lookup"><span data-stu-id="2ede7-115">Example</span></span>  
 <span data-ttu-id="2ede7-116">この例では、<xref:System.Linq.Enumerable.Where%2A> メソッドを使用して、2002 年 12 月 1 日以降に受けた注文を検索します。次に、<xref:System.Data.DataRow.GetChildRows%2A> メソッドを使用して、各注文の詳細を取得します。</span><span class="sxs-lookup"><span data-stu-id="2ede7-116">This example uses the <xref:System.Linq.Enumerable.Where%2A> method to find orders that were made after December 1, 2002 and then uses the <xref:System.Data.DataRow.GetChildRows%2A> method to get the details for each order.</span></span>  
  
 [!code-csharp[DP LINQ to DataSetExamples#WhereDrillDown](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#wheredrilldown)]       
 [!code-vb[DP LINQ to DataSet Examples#WhereDrillDown](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#wheredrilldown)]  
  
## <a name="see-also"></a><span data-ttu-id="2ede7-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="2ede7-117">See Also</span></span>  
 [<span data-ttu-id="2ede7-118">DataSet へのデータの読み込み</span><span class="sxs-lookup"><span data-stu-id="2ede7-118">Loading Data Into a DataSet</span></span>](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)  
 [<span data-ttu-id="2ede7-119">LINQ to DataSet の例</span><span class="sxs-lookup"><span data-stu-id="2ede7-119">LINQ to DataSet Examples</span></span>](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)  
 [<span data-ttu-id="2ede7-120">標準クエリ演算子の概要</span><span class="sxs-lookup"><span data-stu-id="2ede7-120">Standard Query Operators Overview</span></span>](https://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2)
