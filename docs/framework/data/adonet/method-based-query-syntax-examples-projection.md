---
title: 'メソッド ベースのクエリ構文例 : 射影 (LINQ to DataSet)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0fc2c8f0-1967-4f30-8b20-39b8dccfb82f
ms.openlocfilehash: 8d18ed04ad33fe88fb14fd7436ddfd7a164c4303
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "43554278"
---
# <a name="method-based-query-syntax-examples-projection-linq-to-dataset"></a><span data-ttu-id="1232d-102">メソッド ベースのクエリ構文例 : 射影 (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="1232d-102">Method-Based Query Syntax Examples: Projection (LINQ to DataSet)</span></span>
<span data-ttu-id="1232d-103">このトピックでは、<xref:System.Linq.Enumerable.Select%2A> メソッドおよび <xref:System.Linq.Enumerable.SelectMany%2A> メソッドで、メソッド ベースのクエリ構文を使って <xref:System.Data.DataSet> に対するクエリを実行する例を紹介しています。</span><span class="sxs-lookup"><span data-stu-id="1232d-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Select%2A> and <xref:System.Linq.Enumerable.SelectMany%2A> methods to query a <xref:System.Data.DataSet> using the method-based query syntax.</span></span>  
  
 <span data-ttu-id="1232d-104">`FillDataSet`でこれらの例で使用されるメソッドが指定された[をデータセットにデータを読み込む](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)します。</span><span class="sxs-lookup"><span data-stu-id="1232d-104">The `FillDataSet` method used in these examples is specified in [Loading Data Into a DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span></span>  
  
 <span data-ttu-id="1232d-105">このトピックの例には、AdventureWorks サンプル データベースの Contact、Address、Product、SalesOrderHeader、SalesOrderDetail の各テーブルが使用されています。</span><span class="sxs-lookup"><span data-stu-id="1232d-105">The examples in this topic use the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="1232d-106">このトピックの例では、次を使用して`using` / `Imports`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="1232d-106">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 <span data-ttu-id="1232d-107">詳細については、次を参照してください。[方法: LINQ to Visual Studio でデータセット プロジェクトを作成](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md)です。</span><span class="sxs-lookup"><span data-stu-id="1232d-107">For more information, see [How to: Create a LINQ to DataSet Project In Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).</span></span>  
  
## <a name="select"></a><span data-ttu-id="1232d-108">選択</span><span class="sxs-lookup"><span data-stu-id="1232d-108">Select</span></span>  
  
### <a name="example"></a><span data-ttu-id="1232d-109">例</span><span class="sxs-lookup"><span data-stu-id="1232d-109">Example</span></span>  
 <span data-ttu-id="1232d-110">この例では、<xref:System.Linq.Enumerable.Select%2A> メソッドを使用して、`Name`、`ProductNumber`、`ListPrice` の各プロパティを一連の匿名型に射影します。</span><span class="sxs-lookup"><span data-stu-id="1232d-110">This example uses the <xref:System.Linq.Enumerable.Select%2A> method to project the `Name`, `ProductNumber`, and `ListPrice` properties to a sequence of anonymous types.</span></span>  <span data-ttu-id="1232d-111">また、結果として得られる型では、`ListPrice` プロパティの名前が `Price` に変更されます。</span><span class="sxs-lookup"><span data-stu-id="1232d-111">The `ListPrice` property is also renamed to `Price` in the resulting type.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#SelectAnonymousTypes_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#selectanonymoustypes_mq)]
 [!code-vb[DP LINQ to DataSet Examples#SelectAnonymousTypes_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#selectanonymoustypes_mq)]  
  
## <a name="selectmany"></a><span data-ttu-id="1232d-112">SelectMany</span><span class="sxs-lookup"><span data-stu-id="1232d-112">SelectMany</span></span>  
  
### <a name="example"></a><span data-ttu-id="1232d-113">例</span><span class="sxs-lookup"><span data-stu-id="1232d-113">Example</span></span>  
 <span data-ttu-id="1232d-114">この例では、<xref:System.Linq.Enumerable.SelectMany%2A> メソッドを使用して、`TotalDue` が 500.00 に満たないすべての注文を選択します。</span><span class="sxs-lookup"><span data-stu-id="1232d-114">This example uses the <xref:System.Linq.Enumerable.SelectMany%2A> method to select all orders where `TotalDue` is less than 500.00.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#SelectManyCompoundFrom_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#selectmanycompoundfrom_mq)]
 [!code-vb[DP LINQ to DataSet Examples#SelectManyCompoundFrom_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#selectmanycompoundfrom_mq)]  
  
### <a name="example"></a><span data-ttu-id="1232d-115">例</span><span class="sxs-lookup"><span data-stu-id="1232d-115">Example</span></span>  
 <span data-ttu-id="1232d-116">この例では、<xref:System.Linq.Enumerable.SelectMany%2A> メソッドを使用して、2002 年 10 月 1 日以降に受けたすべての注文を選択します。</span><span class="sxs-lookup"><span data-stu-id="1232d-116">This example uses the <xref:System.Linq.Enumerable.SelectMany%2A> method to select all orders where the order was made on October 1, 2002 or later.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#SelectManyCompoundFrom2_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#selectmanycompoundfrom2_mq)]
 [!code-vb[DP LINQ to DataSet Examples#SelectManyCompoundFrom2_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#selectmanycompoundfrom2_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="1232d-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="1232d-117">See Also</span></span>  
 [<span data-ttu-id="1232d-118">DataSet へのデータの読み込み</span><span class="sxs-lookup"><span data-stu-id="1232d-118">Loading Data Into a DataSet</span></span>](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)  
 [<span data-ttu-id="1232d-119">LINQ to DataSet の例</span><span class="sxs-lookup"><span data-stu-id="1232d-119">LINQ to DataSet Examples</span></span>](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)  
 [<span data-ttu-id="1232d-120">標準クエリ演算子の概要</span><span class="sxs-lookup"><span data-stu-id="1232d-120">Standard Query Operators Overview</span></span>](https://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2)
