---
title: バルク コピー操作の複数実行
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5ad12f94-7459-4a93-a421-4160d1a90715
ms.openlocfilehash: 405a82c625853d242ca68088ffdf81b6bcd7c518
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59209763"
---
# <a name="multiple-bulk-copy-operations"></a><span data-ttu-id="1eafd-102">バルク コピー操作の複数実行</span><span class="sxs-lookup"><span data-stu-id="1eafd-102">Multiple Bulk Copy Operations</span></span>
<span data-ttu-id="1eafd-103"><xref:System.Data.SqlClient.SqlBulkCopy> クラスのインスタンスを 1 つ使用すると、バルク コピー操作を複数回実行できます。</span><span class="sxs-lookup"><span data-stu-id="1eafd-103">You can perform multiple bulk copy operations using a single instance of a <xref:System.Data.SqlClient.SqlBulkCopy> class.</span></span> <span data-ttu-id="1eafd-104">後続の呼び出しの前に更新する必要があります (たとえば、レプリケーション先テーブルの名前) のコピー間で操作のパラメーターを変更する場合、 **WriteToServer**メソッドは、次の例に示すよう。</span><span class="sxs-lookup"><span data-stu-id="1eafd-104">If the operation parameters change between copies (for example, the name of the destination table), you must update them prior to any subsequent calls to any of the **WriteToServer** methods, as demonstrated in the following example.</span></span> <span data-ttu-id="1eafd-105">明示的に変更されている場合を除き、すべてのプロパティ値は、任意のインスタンスに対する前回のバルク コピー操作の状態のまま残っています。</span><span class="sxs-lookup"><span data-stu-id="1eafd-105">Unless explicitly changed, all property values remain the same as they were on the previous bulk copy operation for a given instance.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1eafd-106">通常、バルク コピー操作を複数回実行する場合は、同じ <xref:System.Data.SqlClient.SqlBulkCopy> のインスタンスを使用する方が各操作ごとに別のインスタンスを使用するよりも効率的です。</span><span class="sxs-lookup"><span data-stu-id="1eafd-106">Performing multiple bulk copy operations using the same instance of <xref:System.Data.SqlClient.SqlBulkCopy> is usually more efficient than using a separate instance for each operation.</span></span>  
  
 <span data-ttu-id="1eafd-107">同じ <xref:System.Data.SqlClient.SqlBulkCopy> オブジェクトを使用してバルク コピー操作を複数回実行する場合は、コピー元またはコピー先の情報が各操作ごとに一致しているかまたは異なっているかどうかは制限されません。</span><span class="sxs-lookup"><span data-stu-id="1eafd-107">If you perform several bulk copy operations using the same <xref:System.Data.SqlClient.SqlBulkCopy> object, there are no restrictions on whether source or target information is equal or different in each operation.</span></span> <span data-ttu-id="1eafd-108">ただし、サーバーに書き込み処理を行うときは、列の関連情報を毎回正しく設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1eafd-108">However, you must ensure that column association information is properly set each time you write to the server.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="1eafd-109">このサンプルでは」の説明に従って、作業テーブルを作成していない限りは実行されません[バルク コピー サンプルのセットアップ](../../../../../docs/framework/data/adonet/sql/bulk-copy-example-setup.md)します。</span><span class="sxs-lookup"><span data-stu-id="1eafd-109">This sample will not run unless you have created the work tables as described in [Bulk Copy Example Setup](../../../../../docs/framework/data/adonet/sql/bulk-copy-example-setup.md).</span></span> <span data-ttu-id="1eafd-110">使用する構文を示すためにこのコードが提供される**SqlBulkCopy**のみです。</span><span class="sxs-lookup"><span data-stu-id="1eafd-110">This code is provided to demonstrate the syntax for using **SqlBulkCopy** only.</span></span> <span data-ttu-id="1eafd-111">コピー元およびコピー先のテーブルが同一の SQL Server インスタンス内に存在する場合、Transact-SQL `INSERT … SELECT` ステートメントを使用すれば簡単かつ高速にデータをコピーすることができます。</span><span class="sxs-lookup"><span data-stu-id="1eafd-111">If the source and destination tables are located in the same SQL Server instance, it is easier and faster to use a Transact-SQL `INSERT … SELECT` statement to copy the data.</span></span>  
  
 [!code-csharp[DataWorks SqlBulkCopy.ColumnMappingOrdersDetails#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlBulkCopy.ColumnMappingOrdersDetails/CS/source.cs#1)]
 [!code-vb[DataWorks SqlBulkCopy.ColumnMappingOrdersDetails#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlBulkCopy.ColumnMappingOrdersDetails/VB/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="1eafd-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="1eafd-112">See also</span></span>

- [<span data-ttu-id="1eafd-113">SQL Server でのバルク コピー操作</span><span class="sxs-lookup"><span data-stu-id="1eafd-113">Bulk Copy Operations in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/bulk-copy-operations-in-sql-server.md)
- [<span data-ttu-id="1eafd-114">ADO.NET のマネージド プロバイダーと DataSet デベロッパー センター</span><span class="sxs-lookup"><span data-stu-id="1eafd-114">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
