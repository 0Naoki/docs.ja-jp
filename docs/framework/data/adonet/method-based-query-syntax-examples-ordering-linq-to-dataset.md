---
title: メソッド ベースのクエリ構文例:並べ替え (LINQ to DataSet)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8f9ce4fd-e84f-48c0-bb64-89e217236d3e
ms.openlocfilehash: 5e8a0669525e78f025d96b00edbaaf25486f339a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54632869"
---
# <a name="method-based-query-syntax-examples-ordering-linq-to-dataset"></a><span data-ttu-id="3719c-102">メソッド ベースのクエリ構文例:並べ替え (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="3719c-102">Method-Based Query Syntax Examples: Ordering (LINQ to DataSet)</span></span>
<span data-ttu-id="3719c-103">このトピックでは、<xref:System.Linq.Enumerable.OrderBy%2A> に対し、<xref:System.Linq.Enumerable.Reverse%2A>、<xref:System.Linq.Enumerable.ThenBy%2A>、<xref:System.Data.DataSet> の各メソッドを使ってクエリを実行し、その結果をメソッドのクエリ構文を使って並べ替える例を紹介しています。</span><span class="sxs-lookup"><span data-stu-id="3719c-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.OrderBy%2A>,  <xref:System.Linq.Enumerable.Reverse%2A>, and <xref:System.Linq.Enumerable.ThenBy%2A> methods to query a <xref:System.Data.DataSet> and order the results using the method query syntax.</span></span>  
  
 <span data-ttu-id="3719c-104">`FillDataSet`でこれらの例で使用されるメソッドが指定された[をデータセットにデータを読み込む](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)します。</span><span class="sxs-lookup"><span data-stu-id="3719c-104">The `FillDataSet` method used in these examples is specified in [Loading Data Into a DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span></span>  
  
 <span data-ttu-id="3719c-105">このトピックの例には、AdventureWorks サンプル データベースの Contact、Address、Product、SalesOrderHeader、SalesOrderDetail の各テーブルが使用されています。</span><span class="sxs-lookup"><span data-stu-id="3719c-105">The examples in this topic use the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="3719c-106">このトピックの例では、次を使用して`using` / `Imports`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="3719c-106">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 <span data-ttu-id="3719c-107">詳細については、「[方法 :Visual Studio での LINQ to DataSet プロジェクトの作成](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md)です。</span><span class="sxs-lookup"><span data-stu-id="3719c-107">For more information, see [How to: Create a LINQ to DataSet Project In Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).</span></span>  
  
## <a name="orderby"></a><span data-ttu-id="3719c-108">OrderBy</span><span class="sxs-lookup"><span data-stu-id="3719c-108">OrderBy</span></span>  
  
### <a name="example"></a><span data-ttu-id="3719c-109">例</span><span class="sxs-lookup"><span data-stu-id="3719c-109">Example</span></span>  
 <span data-ttu-id="3719c-110">この例では、<xref:System.Linq.Enumerable.OrderBy%2A> メソッドおよびカスタム Comparer を使用し、大文字と小文字を区別せずに姓の並べ替えを実行します。</span><span class="sxs-lookup"><span data-stu-id="3719c-110">This example uses the <xref:System.Linq.Enumerable.OrderBy%2A> method with a custom comparer to do a case-insensitive sort of last names.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#OrderByComparer_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#orderbycomparer_mq)]
 [!code-vb[DP LINQ to DataSet Examples#OrderByComparer_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#orderbycomparer_mq)]  
  
## <a name="reverse"></a><span data-ttu-id="3719c-111">Reverse</span><span class="sxs-lookup"><span data-stu-id="3719c-111">Reverse</span></span>  
  
### <a name="example"></a><span data-ttu-id="3719c-112">例</span><span class="sxs-lookup"><span data-stu-id="3719c-112">Example</span></span>  
 <span data-ttu-id="3719c-113">この例では、<xref:System.Linq.Enumerable.Reverse%2A> メソッドを使用し、`OrderDate` が 2002 年 2 月 20 日よりも前の日付である注文のリストを作成します。</span><span class="sxs-lookup"><span data-stu-id="3719c-113">This example uses the <xref:System.Linq.Enumerable.Reverse%2A> method to create a list of orders where `OrderDate` is earlier than Feb 20, 2002.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Reverse](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#reverse)]
 [!code-vb[DP LINQ to DataSet Examples#Reverse](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#reverse)]  
  
## <a name="thenby"></a><span data-ttu-id="3719c-114">ThenBy</span><span class="sxs-lookup"><span data-stu-id="3719c-114">ThenBy</span></span>  
  
### <a name="example"></a><span data-ttu-id="3719c-115">例</span><span class="sxs-lookup"><span data-stu-id="3719c-115">Example</span></span>  
 <span data-ttu-id="3719c-116">この例では、<xref:System.Linq.Enumerable.OrderBy%2A> メソッドと <xref:System.Linq.Enumerable.ThenBy%2A> メソッド、およびカスタム Comparer を使用して最初に表示価格で並べ替えた後、製品名の降順で大文字と小文字を区別せずに並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="3719c-116">This example uses <xref:System.Linq.Enumerable.OrderBy%2A> and <xref:System.Linq.Enumerable.ThenBy%2A> methods with a custom comparer to first sort by list price, and then perform a case-insensitive descending sort of the product names.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ThenByDescendingComparer_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#thenbydescendingcomparer_mq)]
 [!code-vb[DP LINQ to DataSet Examples#ThenByDescendingComparer_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#thenbydescendingcomparer_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="3719c-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="3719c-117">See also</span></span>
- [<span data-ttu-id="3719c-118">DataSet へのデータの読み込み</span><span class="sxs-lookup"><span data-stu-id="3719c-118">Loading Data Into a DataSet</span></span>](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)
- [<span data-ttu-id="3719c-119">LINQ to DataSet の例</span><span class="sxs-lookup"><span data-stu-id="3719c-119">LINQ to DataSet Examples</span></span>](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)
- [<span data-ttu-id="3719c-120">標準クエリ演算子の概要</span><span class="sxs-lookup"><span data-stu-id="3719c-120">Standard Query Operators Overview</span></span>](https://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2)
