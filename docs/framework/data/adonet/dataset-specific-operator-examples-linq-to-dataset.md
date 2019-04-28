---
title: DataSet 固有の演算子の例 (LINQ to DataSet)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8fdd64af-6ad0-46cd-91c8-dbe26620eeb1
ms.openlocfilehash: 27a48b7ffe5466c52f19f15cf3c1a6cb558028b2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61607030"
---
# <a name="dataset-specific-operator-examples-linq-to-dataset"></a><span data-ttu-id="36d11-102">DataSet 固有の演算子の例 (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="36d11-102">DataSet-Specific Operator Examples (LINQ to DataSet)</span></span>
<span data-ttu-id="36d11-103">このトピックでは、<xref:System.Data.DataTableExtensions.CopyToDataTable%2A> メソッドおよび <xref:System.Data.DataRowComparer> クラスの使用例を紹介しています。</span><span class="sxs-lookup"><span data-stu-id="36d11-103">The examples in this topic demonstrate how to use the <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> method and the <xref:System.Data.DataRowComparer> class.</span></span>  
  
 <span data-ttu-id="36d11-104">`FillDataSet`でこれらの例で使用されるメソッドが指定された[をデータセットにデータを読み込む](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)します。</span><span class="sxs-lookup"><span data-stu-id="36d11-104">The `FillDataSet` method used in these examples is specified in [Loading Data Into a DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span></span>  
  
 <span data-ttu-id="36d11-105">このトピックの例には、AdventureWorks サンプル データベースの Contact、Address、Product、SalesOrderHeader、SalesOrderDetail の各テーブルが使用されています。</span><span class="sxs-lookup"><span data-stu-id="36d11-105">The examples in this topic use the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="36d11-106">このトピックの例では、次を使用して`using` / `Imports`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="36d11-106">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 <span data-ttu-id="36d11-107">詳細については、「[方法 :Visual Studio での LINQ to DataSet プロジェクトの作成](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md)です。</span><span class="sxs-lookup"><span data-stu-id="36d11-107">For more information, see [How to: Create a LINQ to DataSet Project In Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).</span></span>  
  
## <a name="copytodatatable"></a><span data-ttu-id="36d11-108">CopyToDataTable</span><span class="sxs-lookup"><span data-stu-id="36d11-108">CopyToDataTable</span></span>  
  
### <a name="example"></a><span data-ttu-id="36d11-109">例</span><span class="sxs-lookup"><span data-stu-id="36d11-109">Example</span></span>  
 <span data-ttu-id="36d11-110">この例では、<xref:System.Data.DataTable> メソッドを使用して、<xref:System.Data.DataTableExtensions.CopyToDataTable%2A> にクエリ結果を読み込みます。</span><span class="sxs-lookup"><span data-stu-id="36d11-110">This example loads a <xref:System.Data.DataTable> with query results by using the <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> method.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#LoadDataTableWithQueryResults](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#loaddatatablewithqueryresults)]
 [!code-vb[DP LINQ to DataSet Examples#LoadDataTableWithQueryResults](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#loaddatatablewithqueryresults)]  
  
## <a name="datarowcomparer"></a><span data-ttu-id="36d11-111">DataRowComparer</span><span class="sxs-lookup"><span data-stu-id="36d11-111">DataRowComparer</span></span>  
  
### <a name="example"></a><span data-ttu-id="36d11-112">例</span><span class="sxs-lookup"><span data-stu-id="36d11-112">Example</span></span>  
 <span data-ttu-id="36d11-113">この例では 2 つの異なるデータ行を <xref:System.Data.DataRowComparer> を使用して比較します。</span><span class="sxs-lookup"><span data-stu-id="36d11-113">This example compares two different data rows by using <xref:System.Data.DataRowComparer>.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#CompareDifferentDataRows](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#comparedifferentdatarows)]  
  
## <a name="see-also"></a><span data-ttu-id="36d11-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="36d11-114">See also</span></span>

- [<span data-ttu-id="36d11-115">DataSet へのデータの読み込み</span><span class="sxs-lookup"><span data-stu-id="36d11-115">Loading Data Into a DataSet</span></span>](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)
- [<span data-ttu-id="36d11-116">LINQ to DataSet の例</span><span class="sxs-lookup"><span data-stu-id="36d11-116">LINQ to DataSet Examples</span></span>](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)
