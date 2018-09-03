---
title: 'メソッド ベースのクエリ構文例 : 集合演算子 (LINQ to DataSet)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: fa93af15-28af-4b5e-846b-897308410edb
ms.openlocfilehash: 75918450d3e08436578b1535316f19d2adf32695
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/02/2018
ms.locfileid: "43476236"
---
# <a name="method-based-query-syntax-examples-set-operators-linq-to-dataset"></a><span data-ttu-id="09ee9-102">メソッド ベースのクエリ構文例 : 集合演算子 (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="09ee9-102">Method-Based Query Syntax Examples: Set Operators (LINQ to DataSet)</span></span>
<span data-ttu-id="09ee9-103">このトピックの例では、使用する方法を示します、 <xref:System.Linq.Enumerable.Distinct%2A>、 <xref:System.Linq.Enumerable.Except%2A>、 <xref:System.Linq.Enumerable.Intersect%2A>、および<xref:System.Linq.Enumerable.Union%2A>データ行の集合に対する値ベースの比較操作を実行する演算子[。データセットにデータを読み込んで](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)を参照してください[Datarow の比較](../../../../docs/framework/data/adonet/comparing-datarows-linq-to-dataset.md)の詳細については<xref:System.Data.DataRowComparer>します。</span><span class="sxs-lookup"><span data-stu-id="09ee9-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Distinct%2A>, <xref:System.Linq.Enumerable.Except%2A>, <xref:System.Linq.Enumerable.Intersect%2A>, and <xref:System.Linq.Enumerable.Union%2A> operators to perform value-based comparison operations on sets of data rows.[Loading Data Into a DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md) See [Comparing DataRows](../../../../docs/framework/data/adonet/comparing-datarows-linq-to-dataset.md) for more information on <xref:System.Data.DataRowComparer>.</span></span>  
  
 <span data-ttu-id="09ee9-104">`FillDataSet`でこれらの例で使用されるメソッドが指定された[をデータセットにデータを読み込む](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)します。</span><span class="sxs-lookup"><span data-stu-id="09ee9-104">The `FillDataSet` method used in these examples is specified in [Loading Data Into a DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span></span>  
  
 <span data-ttu-id="09ee9-105">このトピックの例には、AdventureWorks サンプル データベースの Contact、Address、Product、SalesOrderHeader、SalesOrderDetail の各テーブルが使用されています。</span><span class="sxs-lookup"><span data-stu-id="09ee9-105">The examples in this topic use the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="09ee9-106">このトピックの例では、次を使用して`using` / `Imports`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="09ee9-106">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 <span data-ttu-id="09ee9-107">詳細については、次を参照してください。[方法: LINQ to Visual Studio でデータセット プロジェクトを作成](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md)です。</span><span class="sxs-lookup"><span data-stu-id="09ee9-107">For more information, see [How to: Create a LINQ to DataSet Project In Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).</span></span>  
  
## <a name="distinct"></a><span data-ttu-id="09ee9-108">Distinct</span><span class="sxs-lookup"><span data-stu-id="09ee9-108">Distinct</span></span>  
  
### <a name="example"></a><span data-ttu-id="09ee9-109">例</span><span class="sxs-lookup"><span data-stu-id="09ee9-109">Example</span></span>  
 <span data-ttu-id="09ee9-110">この例では、<xref:System.Linq.Enumerable.Distinct%2A> メソッドを使用してシーケンス内の重複する要素を削除します。</span><span class="sxs-lookup"><span data-stu-id="09ee9-110">This example uses the <xref:System.Linq.Enumerable.Distinct%2A> method to remove duplicate elements in a sequence.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#DistinctRows](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#distinctrows)]
 [!code-vb[DP LINQ to DataSet Examples#DistinctRows](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#distinctrows)]  
  
## <a name="except"></a><span data-ttu-id="09ee9-111">Except</span><span class="sxs-lookup"><span data-stu-id="09ee9-111">Except</span></span>  
  
### <a name="example"></a><span data-ttu-id="09ee9-112">例</span><span class="sxs-lookup"><span data-stu-id="09ee9-112">Example</span></span>  
 <span data-ttu-id="09ee9-113">この例では、最初のテーブルにのみ存在し、かつ 2 つ目のテーブルには存在しない連絡先だけを、<xref:System.Linq.Enumerable.Except%2A> メソッドを使用して取得します。</span><span class="sxs-lookup"><span data-stu-id="09ee9-113">This example uses the <xref:System.Linq.Enumerable.Except%2A> method to return contacts that appear in the first table but not in the second.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Except2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#except2)]
 [!code-vb[DP LINQ to DataSet Examples#Except2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#except2)]  
  
## <a name="intersect"></a><span data-ttu-id="09ee9-114">交差</span><span class="sxs-lookup"><span data-stu-id="09ee9-114">Intersect</span></span>  
  
### <a name="example"></a><span data-ttu-id="09ee9-115">例</span><span class="sxs-lookup"><span data-stu-id="09ee9-115">Example</span></span>  
 <span data-ttu-id="09ee9-116">この例では、両方のテーブルに存在する連絡先を <xref:System.Linq.Enumerable.Intersect%2A> メソッドを使用して取得します。</span><span class="sxs-lookup"><span data-stu-id="09ee9-116">This example uses the <xref:System.Linq.Enumerable.Intersect%2A> method to return contacts that appear in both tables.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Intersect2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#intersect2)]
 [!code-vb[DP LINQ to DataSet Examples#Intersect2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#intersect2)]  
  
## <a name="union"></a><span data-ttu-id="09ee9-117">和集合</span><span class="sxs-lookup"><span data-stu-id="09ee9-117">Union</span></span>  
  
### <a name="example"></a><span data-ttu-id="09ee9-118">例</span><span class="sxs-lookup"><span data-stu-id="09ee9-118">Example</span></span>  
 <span data-ttu-id="09ee9-119">この例では、<xref:System.Linq.Enumerable.Union%2A> メソッドを使用して、2 つのテーブルのいずれかから一意の連絡先を取得します。</span><span class="sxs-lookup"><span data-stu-id="09ee9-119">This example uses the <xref:System.Linq.Enumerable.Union%2A> method to return unique contacts from either of the two tables.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Union2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#union2)]
 [!code-vb[DP LINQ to DataSet Examples#Union2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#union2)]  
  
## <a name="see-also"></a><span data-ttu-id="09ee9-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="09ee9-120">See Also</span></span>  
 [<span data-ttu-id="09ee9-121">DataSet へのデータの読み込み</span><span class="sxs-lookup"><span data-stu-id="09ee9-121">Loading Data Into a DataSet</span></span>](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)  
 [<span data-ttu-id="09ee9-122">LINQ to DataSet の例</span><span class="sxs-lookup"><span data-stu-id="09ee9-122">LINQ to DataSet Examples</span></span>](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)  
 [<span data-ttu-id="09ee9-123">標準クエリ演算子の概要</span><span class="sxs-lookup"><span data-stu-id="09ee9-123">Standard Query Operators Overview</span></span>](https://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2)
