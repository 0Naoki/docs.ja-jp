---
title: 2 つのシーケンスの差集合の取得
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 62efb546-c898-408f-af21-36e7c6fed217
ms.openlocfilehash: 282ec36a2ad489e77db9fb5b338d3189c3001f03
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54609032"
---
# <a name="return-the-set-difference-between-two-sequences"></a><span data-ttu-id="790d5-102">2 つのシーケンスの差集合の取得</span><span class="sxs-lookup"><span data-stu-id="790d5-102">Return the Set Difference Between Two Sequences</span></span>
<span data-ttu-id="790d5-103">2 つのシーケンスの差集合を返すには、<xref:System.Linq.Queryable.Except%2A> 演算子を使用します。</span><span class="sxs-lookup"><span data-stu-id="790d5-103">Use the <xref:System.Linq.Queryable.Except%2A> operator to return the set difference between two sequences.</span></span>  
  
## <a name="example"></a><span data-ttu-id="790d5-104">例</span><span class="sxs-lookup"><span data-stu-id="790d5-104">Example</span></span>  
 <span data-ttu-id="790d5-105">この例では、<xref:System.Linq.Queryable.Except%2A> を使用して、`Customers` は居住しているが `Employees` は居住していないすべての国のシーケンスを返します。</span><span class="sxs-lookup"><span data-stu-id="790d5-105">This example uses <xref:System.Linq.Queryable.Except%2A> to return a sequence of all countries in which `Customers` live but in which no `Employees` live.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#41](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#41)]
 [!code-vb[DLinqQueryExamples#41](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#41)]  
  
 <span data-ttu-id="790d5-106">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] では、<xref:System.Linq.Queryable.Except%2A> 演算は集合でのみ適切に定義されます。</span><span class="sxs-lookup"><span data-stu-id="790d5-106">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], the <xref:System.Linq.Queryable.Except%2A> operation is well defined only on sets.</span></span> <span data-ttu-id="790d5-107">マルチセットのセマンティクスは未定義です。</span><span class="sxs-lookup"><span data-stu-id="790d5-107">The semantics for multisets is undefined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="790d5-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="790d5-108">See also</span></span>
- [<span data-ttu-id="790d5-109">クエリの例</span><span class="sxs-lookup"><span data-stu-id="790d5-109">Query Examples</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)
- [<span data-ttu-id="790d5-110">標準クエリ演算子の変換</span><span class="sxs-lookup"><span data-stu-id="790d5-110">Standard Query Operator Translation</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/standard-query-operator-translation.md)
