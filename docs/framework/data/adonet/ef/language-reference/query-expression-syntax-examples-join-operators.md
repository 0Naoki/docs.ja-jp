---
title: クエリ式の構文例:結合演算子
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 343e8dda-70b2-409d-9334-ce9a880c3cea
ms.openlocfilehash: da583ed207a8c4fc9e061d517895ca0f2fea2f5e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59168819"
---
# <a name="query-expression-syntax-examples-join-operators"></a><span data-ttu-id="9252c-102">クエリ式の構文例:結合演算子</span><span class="sxs-lookup"><span data-stu-id="9252c-102">Query Expression Syntax Examples: Join Operators</span></span>
<span data-ttu-id="9252c-103">結合は、リレーショナル データベース テーブルのように互いにナビゲート可能なリレーションシップを持たないデータ ソースをターゲットとするクエリにおいて重要な操作です。</span><span class="sxs-lookup"><span data-stu-id="9252c-103">Joining is an important operation in queries that target data sources that have no navigable relationships to each other, such as relational database tables.</span></span> <span data-ttu-id="9252c-104">2 つのデータ ソースを結合する操作とは、あるデータ ソース内のオブジェクトを、他方のデータ ソース内で共通の属性を持つオブジェクトと関連付けることです。</span><span class="sxs-lookup"><span data-stu-id="9252c-104">A join of two data sources is the association of objects in one data source with objects that share a common attribute in the other data source.</span></span> <span data-ttu-id="9252c-105">詳細については、次を参照してください。[標準クエリ演算子の概要](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/bb397896(v=vs.120))します。</span><span class="sxs-lookup"><span data-stu-id="9252c-105">For more information, see [Standard Query Operators Overview](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/bb397896(v=vs.120)).</span></span>  
  
 <span data-ttu-id="9252c-106">このトピックの例では、使用する方法を示します、<xref:System.Linq.Enumerable.GroupJoin%2A>と<xref:System.Linq.Enumerable.Join%2A>を照会する方法、 [AdventureWorks Sales Model](https://archive.codeplex.com/?p=msftdbprodsamples)クエリ式構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="9252c-106">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.GroupJoin%2A> and <xref:System.Linq.Enumerable.Join%2A> methods to query the [AdventureWorks Sales Model](https://archive.codeplex.com/?p=msftdbprodsamples) using query expression syntax.</span></span> <span data-ttu-id="9252c-107">これらの例で使用されている、AdventureWorks Sales Model は、AdventureWorks サンプル データベースの Contact、Address、Product、SalesOrderHeader、SalesOrderDetail の各テーブルから作成されています。</span><span class="sxs-lookup"><span data-stu-id="9252c-107">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="9252c-108">このトピックの例では、次を使用して`using` / `Imports`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="9252c-108">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="groupjoin"></a><span data-ttu-id="9252c-109">GroupJoin</span><span class="sxs-lookup"><span data-stu-id="9252c-109">GroupJoin</span></span>  
  
### <a name="example"></a><span data-ttu-id="9252c-110">例</span><span class="sxs-lookup"><span data-stu-id="9252c-110">Example</span></span>  
 <span data-ttu-id="9252c-111">次の例では、SalesOrderHeader テーブルおよび SalesOrderDetail テーブルに対して <xref:System.Linq.Enumerable.GroupJoin%2A> を実行することによって、顧客ごとの注文数を調べます。</span><span class="sxs-lookup"><span data-stu-id="9252c-111">The following example performs a <xref:System.Linq.Enumerable.GroupJoin%2A> over the SalesOrderHeader and SalesOrderDetail tables to find the number of orders per customer.</span></span> <span data-ttu-id="9252c-112">GroupJoin は、左外部結合に相当します。つまり、1 つ目 (左側) のデータ ソースに存在するすべての要素は、関連する要素がもう一方のデータ ソースに存在するかどうかに関係なく返されます。</span><span class="sxs-lookup"><span data-stu-id="9252c-112">A group join is the equivalent of a left outer join, which returns each element of the first (left) data source, even if no correlated elements are in the other data source.</span></span>  
  
 [!code-csharp[DP L2E Examples#GroupJoin2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupjoin2)]
 [!code-vb[DP L2E Examples#GroupJoin2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupjoin2)]  
  
### <a name="example"></a><span data-ttu-id="9252c-113">例</span><span class="sxs-lookup"><span data-stu-id="9252c-113">Example</span></span>  
 <span data-ttu-id="9252c-114">次の例では、Contact テーブルおよび SalesOrderHeader テーブルに対して <xref:System.Linq.Enumerable.GroupJoin%2A> を実行して、連絡先ごとの注文数を調べます。</span><span class="sxs-lookup"><span data-stu-id="9252c-114">The following example performs a <xref:System.Linq.Enumerable.GroupJoin%2A> over the Contact and SalesOrderHeader tables to find the number of orders per contact.</span></span> <span data-ttu-id="9252c-115">各連絡先の注文数と ID が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9252c-115">The order count and IDs for each contact are displayed.</span></span>  
  
 [!code-csharp[DP L2E Examples#GroupJoin](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupjoin)]
 [!code-vb[DP L2E Examples#GroupJoin](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupjoin)]  
  
## <a name="join"></a><span data-ttu-id="9252c-116">Join</span><span class="sxs-lookup"><span data-stu-id="9252c-116">Join</span></span>  
  
### <a name="example"></a><span data-ttu-id="9252c-117">例</span><span class="sxs-lookup"><span data-stu-id="9252c-117">Example</span></span>  
 <span data-ttu-id="9252c-118">次の例では、SalesOrderHeader テーブルと SalesOrderDetail テーブルを結合し、8 月以降のオンラインでの注文を取得します。</span><span class="sxs-lookup"><span data-stu-id="9252c-118">The following example performs a join over the SalesOrderHeader and SalesOrderDetail tables to get online orders from the month of August.</span></span>  
  
 [!code-csharp[DP L2E Examples#Join](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#join)]
 [!code-vb[DP L2E Examples#Join](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#join)]  
  
## <a name="see-also"></a><span data-ttu-id="9252c-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="9252c-119">See also</span></span>

- [<span data-ttu-id="9252c-120">LINQ to Entities でのクエリ</span><span class="sxs-lookup"><span data-stu-id="9252c-120">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
