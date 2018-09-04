---
title: 'メソッド ベースのクエリ構文例: 要素演算子'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8438b995-bd07-4223-b22d-13adadef33fb
ms.openlocfilehash: 4215dcddf44647d98ee70c6f2d06345737cba5de
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "43503229"
---
# <a name="method-based-query-syntax-examples-element-operators"></a><span data-ttu-id="bb3e5-102">メソッド ベースのクエリ構文例: 要素演算子</span><span class="sxs-lookup"><span data-stu-id="bb3e5-102">Method-Based Query Syntax Examples: Element Operators</span></span>
<span data-ttu-id="bb3e5-103">このトピックの例では、使用する方法を示します、<xref:System.Linq.Enumerable.First%2A>メソッド クエリを[AdventureWorks Sales Model](https://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832)メソッド ベースのクエリ構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="bb3e5-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.First%2A> method to query the [AdventureWorks Sales Model](https://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832) using method-based query syntax.</span></span> <span data-ttu-id="bb3e5-104">これらの例で使用されている、AdventureWorks Sales Model は、AdventureWorks サンプル データベースの Contact、Address、Product、SalesOrderHeader、SalesOrderDetail の各テーブルから作成されています。</span><span class="sxs-lookup"><span data-stu-id="bb3e5-104">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="bb3e5-105">このトピックの例では、次を使用して`using` / `Imports`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="bb3e5-105">The example in this topic uses the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="first"></a><span data-ttu-id="bb3e5-106">First</span><span class="sxs-lookup"><span data-stu-id="bb3e5-106">First</span></span>  
  
### <a name="example"></a><span data-ttu-id="bb3e5-107">例</span><span class="sxs-lookup"><span data-stu-id="bb3e5-107">Example</span></span>  
 <span data-ttu-id="bb3e5-108">次の例では、 <xref:System.Linq.Enumerable.First%2A> 'caroline' で始まる最初の電子メール アドレスを検索するメソッド。</span><span class="sxs-lookup"><span data-stu-id="bb3e5-108">The following example uses the <xref:System.Linq.Enumerable.First%2A> method to find the first email address that starts with 'caroline'.</span></span>  
  
 [!code-csharp[DP L2E Examples#FirstCondition_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#firstcondition_mq)]
 [!code-vb[DP L2E Examples#FirstCondition_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#firstcondition_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="bb3e5-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="bb3e5-109">See Also</span></span>  
 [<span data-ttu-id="bb3e5-110">LINQ to Entities でのクエリ</span><span class="sxs-lookup"><span data-stu-id="bb3e5-110">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
