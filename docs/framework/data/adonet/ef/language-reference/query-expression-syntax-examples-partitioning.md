---
title: 'クエリ式の構文例: パーティション分割'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7e41aed0-3be9-4f75-98de-860a85552a3c
ms.openlocfilehash: e5539d0052d5d5847475b1902b5fc74566883057
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2018
ms.locfileid: "43855375"
---
# <a name="query-expression-syntax-examples-partitioning"></a><span data-ttu-id="52ddc-102">クエリ式の構文例: パーティション分割</span><span class="sxs-lookup"><span data-stu-id="52ddc-102">Query Expression Syntax Examples: Partitioning</span></span>
<span data-ttu-id="52ddc-103">このトピックの例では、使用する方法を示します、<xref:System.Linq.Enumerable.Skip%2A>と<xref:System.Linq.Enumerable.Take%2A>を照会する方法、 [AdventureWorks Sales Model](https://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832)クエリ式構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="52ddc-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Skip%2A> and <xref:System.Linq.Enumerable.Take%2A> methods to query the [AdventureWorks Sales Model](https://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832) using query expression syntax.</span></span> <span data-ttu-id="52ddc-104">これらの例で使用されている、AdventureWorks Sales Model は、AdventureWorks サンプル データベースの Contact、Address、Product、SalesOrderHeader、SalesOrderDetail の各テーブルから作成されています。</span><span class="sxs-lookup"><span data-stu-id="52ddc-104">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="52ddc-105">このトピックの例では、次を使用して`using` / `Imports`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="52ddc-105">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="skip"></a><span data-ttu-id="52ddc-106">Skip</span><span class="sxs-lookup"><span data-stu-id="52ddc-106">Skip</span></span>  
  
### <a name="example"></a><span data-ttu-id="52ddc-107">例</span><span class="sxs-lookup"><span data-stu-id="52ddc-107">Example</span></span>  
 <span data-ttu-id="52ddc-108">次の例では、Seattle から最初の 2 つを除くすべての住所を、<xref:System.Linq.Enumerable.Skip%2A> メソッドを使って取得します。</span><span class="sxs-lookup"><span data-stu-id="52ddc-108">The following example uses the <xref:System.Linq.Enumerable.Skip%2A> method to get all but the first two addresses in Seattle.</span></span>  
  
 [!code-csharp[DP L2E Examples#SkipNested](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#skipnested)]
 [!code-vb[DP L2E Examples#SkipNested](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#skipnested)]  
  
## <a name="take"></a><span data-ttu-id="52ddc-109">Take</span><span class="sxs-lookup"><span data-stu-id="52ddc-109">Take</span></span>  
  
### <a name="example"></a><span data-ttu-id="52ddc-110">例</span><span class="sxs-lookup"><span data-stu-id="52ddc-110">Example</span></span>  
 <span data-ttu-id="52ddc-111">次の例では、Seattle から最初の 3 つの住所を、<xref:System.Linq.Enumerable.Take%2A> メソッドを使って取得します。</span><span class="sxs-lookup"><span data-stu-id="52ddc-111">The following example uses the <xref:System.Linq.Enumerable.Take%2A> method to get the first three addresses in Seattle.</span></span>  
  
 [!code-csharp[DP L2E Examples#TakeNested](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#takenested)]
 [!code-vb[DP L2E Examples#TakeNested](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#takenested)]  
  
## <a name="see-also"></a><span data-ttu-id="52ddc-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="52ddc-112">See Also</span></span>  
 [<span data-ttu-id="52ddc-113">LINQ to Entities でのクエリ</span><span class="sxs-lookup"><span data-stu-id="52ddc-113">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
