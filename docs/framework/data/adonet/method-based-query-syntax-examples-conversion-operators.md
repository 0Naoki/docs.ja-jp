---
title: メソッド ベースのクエリ構文例:変換演算子 (LINQ to DataSet)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a084c16b-9b55-4690-aefd-f8e0810a92c3
ms.openlocfilehash: 7fb9a6c7cfd891e6a4384f081992a6b185951931
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54688234"
---
# <a name="method-based-query-syntax-examples-conversion-operators-linq-to-dataset"></a><span data-ttu-id="622c8-102">メソッド ベースのクエリ構文例:変換演算子 (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="622c8-102">Method-Based Query Syntax Examples: Conversion Operators (LINQ to DataSet)</span></span>
<span data-ttu-id="622c8-103">このトピックでは、<xref:System.Linq.Enumerable.ToArray%2A>、<xref:System.Linq.Enumerable.ToDictionary%2A>、<xref:System.Linq.Enumerable.ToList%2A> の各メソッドを使ってクエリ式を即時実行する例を示しています。</span><span class="sxs-lookup"><span data-stu-id="622c8-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.ToArray%2A>, <xref:System.Linq.Enumerable.ToDictionary%2A>, and <xref:System.Linq.Enumerable.ToList%2A> methods to immediately execute a query expression.</span></span>  
  
 <span data-ttu-id="622c8-104">`FillDataSet`でこれらの例で使用されるメソッドが指定された[をデータセットにデータを読み込む](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)します。</span><span class="sxs-lookup"><span data-stu-id="622c8-104">The `FillDataSet` method used in these examples is specified in [Loading Data Into a DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span></span>  
  
 <span data-ttu-id="622c8-105">このトピックの例には、AdventureWorks サンプル データベースの Contact、Address、Product、SalesOrderHeader、SalesOrderDetail の各テーブルが使用されています。</span><span class="sxs-lookup"><span data-stu-id="622c8-105">The examples in this topic use the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="622c8-106">このトピックの例では、次を使用して`using` / `Imports`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="622c8-106">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 <span data-ttu-id="622c8-107">詳細については、「[方法 :Visual Studio での LINQ to DataSet プロジェクトの作成](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md)です。</span><span class="sxs-lookup"><span data-stu-id="622c8-107">For more information, see [How to: Create a LINQ to DataSet Project In Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).</span></span>  
  
## <a name="toarray"></a><span data-ttu-id="622c8-108">ToArray</span><span class="sxs-lookup"><span data-stu-id="622c8-108">ToArray</span></span>  
  
### <a name="example"></a><span data-ttu-id="622c8-109">例</span><span class="sxs-lookup"><span data-stu-id="622c8-109">Example</span></span>  
 <span data-ttu-id="622c8-110">この例では、<xref:System.Linq.Enumerable.ToArray%2A> メソッドを使用して、シーケンスを配列として即時評価します。</span><span class="sxs-lookup"><span data-stu-id="622c8-110">This example uses the <xref:System.Linq.Enumerable.ToArray%2A> method to immediately evaluate a sequence into an array.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ToArray](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#toarray)]
 [!code-vb[DP LINQ to DataSet Examples#ToArray](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#toarray)]  
  
## <a name="todictionary"></a><span data-ttu-id="622c8-111">ToDictionary</span><span class="sxs-lookup"><span data-stu-id="622c8-111">ToDictionary</span></span>  
  
### <a name="example"></a><span data-ttu-id="622c8-112">例</span><span class="sxs-lookup"><span data-stu-id="622c8-112">Example</span></span>  
 <span data-ttu-id="622c8-113">この例では、<xref:System.Linq.Enumerable.ToDictionary%2A> メソッドを使用して、シーケンスおよび関連するキー式をディクショナリとして即時評価します。</span><span class="sxs-lookup"><span data-stu-id="622c8-113">This example uses the <xref:System.Linq.Enumerable.ToDictionary%2A> method to immediately evaluate a sequence and a related key expression into a dictionary.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ToDictionary](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#todictionary)]
 [!code-vb[DP LINQ to DataSet Examples#ToDictionary](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#todictionary)]  
  
## <a name="tolist"></a><span data-ttu-id="622c8-114">ToList</span><span class="sxs-lookup"><span data-stu-id="622c8-114">ToList</span></span>  
  
### <a name="example"></a><span data-ttu-id="622c8-115">例</span><span class="sxs-lookup"><span data-stu-id="622c8-115">Example</span></span>  
 <span data-ttu-id="622c8-116">この例では、<xref:System.Linq.Enumerable.ToList%2A> メソッドを使用して、シーケンスを <xref:System.Collections.Generic.List%601> として即時評価します。ここで、`T` は <xref:System.Data.DataRow> 型を表します。</span><span class="sxs-lookup"><span data-stu-id="622c8-116">This example uses the <xref:System.Linq.Enumerable.ToList%2A> method to immediately evaluate a sequence into a <xref:System.Collections.Generic.List%601>, where `T` is of type <xref:System.Data.DataRow>.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ToList](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#tolist)]
 [!code-vb[DP LINQ to DataSet Examples#ToList](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#tolist)]  
  
## <a name="see-also"></a><span data-ttu-id="622c8-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="622c8-117">See also</span></span>
- [<span data-ttu-id="622c8-118">DataSet へのデータの読み込み</span><span class="sxs-lookup"><span data-stu-id="622c8-118">Loading Data Into a DataSet</span></span>](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)
- [<span data-ttu-id="622c8-119">LINQ to DataSet の例</span><span class="sxs-lookup"><span data-stu-id="622c8-119">LINQ to DataSet Examples</span></span>](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)
- [<span data-ttu-id="622c8-120">標準クエリ演算子の概要</span><span class="sxs-lookup"><span data-stu-id="622c8-120">Standard Query Operators Overview</span></span>](https://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2)
