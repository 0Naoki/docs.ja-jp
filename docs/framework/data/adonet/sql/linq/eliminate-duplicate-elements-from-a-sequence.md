---
title: シーケンスからの重複する要素の削除
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 2b224a84-bad5-4843-adcc-14e784d280f5
ms.openlocfilehash: 49138e9b130b1a2137b5e9e779875d6107972578
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59211531"
---
# <a name="eliminate-duplicate-elements-from-a-sequence"></a><span data-ttu-id="b555a-102">シーケンスからの重複する要素の削除</span><span class="sxs-lookup"><span data-stu-id="b555a-102">Eliminate Duplicate Elements from a Sequence</span></span>
<span data-ttu-id="b555a-103">重複する要素をシーケンスから削除するには、<xref:System.Linq.Queryable.Distinct%2A> 演算子を使用します。</span><span class="sxs-lookup"><span data-stu-id="b555a-103">Use the <xref:System.Linq.Queryable.Distinct%2A> operator to eliminate duplicate elements from a sequence.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b555a-104">例</span><span class="sxs-lookup"><span data-stu-id="b555a-104">Example</span></span>  
 <span data-ttu-id="b555a-105">次の例では、<xref:System.Linq.Queryable.Distinct%2A> を使用して、顧客の住所がある市のシーケンスを選択します。それぞれの市はシーケンス内で重複しません。</span><span class="sxs-lookup"><span data-stu-id="b555a-105">The following example uses <xref:System.Linq.Queryable.Distinct%2A> to select a sequence of the unique cities that have customers.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#36](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#36)]
 [!code-vb[DLinqQueryExamples#36](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#36)]  
  
## <a name="see-also"></a><span data-ttu-id="b555a-106">関連項目</span><span class="sxs-lookup"><span data-stu-id="b555a-106">See also</span></span>

- [<span data-ttu-id="b555a-107">クエリの例</span><span class="sxs-lookup"><span data-stu-id="b555a-107">Query Examples</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)
