---
title: System.Math メソッド
ms.date: 03/30/2017
ms.assetid: 0f299521-6f41-4720-bd70-67c93fc50948
ms.openlocfilehash: 1dae31b30962505c07c198f3bd35fceb8f400efb
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59141714"
---
# <a name="systemmath-methods"></a><span data-ttu-id="7552e-102">System.Math メソッド</span><span class="sxs-lookup"><span data-stu-id="7552e-102">System.Math Methods</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="7552e-103">は、次の <xref:System.Math> メソッドをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="7552e-103">does not support the following <xref:System.Math> methods.</span></span>  
  
-   <xref:System.Math.DivRem%28System.Int32%2CSystem.Int32%2CSystem.Int32%40%29?displayProperty=nameWithType>  
  
-   <xref:System.Math.DivRem%28System.Int64%2CSystem.Int64%2CSystem.Int64%40%29?displayProperty=nameWithType>  
  
-   <xref:System.Math.IEEERemainder%28System.Double%2CSystem.Double%29?displayProperty=nameWithType>  
  
## <a name="differences-from-net"></a><span data-ttu-id="7552e-104">.NET との相違</span><span class="sxs-lookup"><span data-stu-id="7552e-104">Differences from .NET</span></span>  
 <span data-ttu-id="7552e-105">.NET Framework で使用される丸めセマンティクスは SQL Server とは異なります。</span><span class="sxs-lookup"><span data-stu-id="7552e-105">The .NET Framework has different rounding semantics from SQL Server.</span></span> <span data-ttu-id="7552e-106"><xref:System.Math.Round%2A> In .NET Framework のメソッドを実行*銀行型丸めが*.5 で終わる数値を四捨五入するという、最も近い偶数の代わりに次の上位桁にします。</span><span class="sxs-lookup"><span data-stu-id="7552e-106">The <xref:System.Math.Round%2A> method in the .NET Framework performs *Banker's rounding*, where numbers that ends in .5 round to the nearest even digit instead of to the next higher digit.</span></span> <span data-ttu-id="7552e-107">たとえば、2.5 は 2 に丸められ、3.5 は 4 に丸められます </span><span class="sxs-lookup"><span data-stu-id="7552e-107">For example, 2.5 rounds to 2, while 3.5 rounds to 4.</span></span> <span data-ttu-id="7552e-108">(この方法は、大規模なデータ トランザクションで、値が大きくなる組織的バイアスの回避に役立ちます)。</span><span class="sxs-lookup"><span data-stu-id="7552e-108">(This technique helps avoid systematic bias toward higher values in large data transactions.)</span></span>  
  
 <span data-ttu-id="7552e-109">SQL では、`ROUND` 関数は常に、0 から遠ざかる方向に丸めを実行します。</span><span class="sxs-lookup"><span data-stu-id="7552e-109">In SQL, the `ROUND` function instead always rounds away from 0.</span></span> <span data-ttu-id="7552e-110">したがって、2.5 は 3 に丸められます。これは、2 に丸められる .NET Framework とは対照的です。</span><span class="sxs-lookup"><span data-stu-id="7552e-110">Therefore 2.5 rounds to 3, contrasted with its rounding to 2 in the .NET Framework.</span></span>  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="7552e-111">は、SQL の `ROUND` セマンティクスに到達するため、銀行型丸めを実装しようとしません。</span><span class="sxs-lookup"><span data-stu-id="7552e-111">passes through to the SQL `ROUND` semantics and does not try to implement Banker's rounding.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7552e-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="7552e-112">See also</span></span>

- [<span data-ttu-id="7552e-113">データ型と関数</span><span class="sxs-lookup"><span data-stu-id="7552e-113">Data Types and Functions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)
