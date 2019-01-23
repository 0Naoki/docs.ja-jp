---
title: ストアド プロシージャのみによる操作のカスタマイズ
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 441e8ef3-998c-4d12-8825-ce66a178f90f
ms.openlocfilehash: 0dd8687bac8aa8ce046fb89c109debd91409aca8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54573544"
---
# <a name="customizing-operations-by-using-stored-procedures-exclusively"></a><span data-ttu-id="7df5f-102">ストアド プロシージャのみによる操作のカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="7df5f-102">Customizing Operations by Using Stored Procedures Exclusively</span></span>
<span data-ttu-id="7df5f-103">ストアド プロシージャのみを使用してデータにアクセスすることは、一般的なシナリオです。</span><span class="sxs-lookup"><span data-stu-id="7df5f-103">Access to data by using only stored procedures is a common scenario.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7df5f-104">例</span><span class="sxs-lookup"><span data-stu-id="7df5f-104">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="7df5f-105">説明</span><span class="sxs-lookup"><span data-stu-id="7df5f-105">Description</span></span>  
 <span data-ttu-id="7df5f-106">提供される例を変更する[カスタマイズ操作によってストアド プロシージャの使用](../../../../../../docs/framework/data/adonet/sql/linq/customizing-operations-by-using-stored-procedures.md)(これは、動的 SQL の実行をにより) 最初のクエリもストアド プロシージャをラップするメソッドの呼び出しに置き換えることによりします。</span><span class="sxs-lookup"><span data-stu-id="7df5f-106">You can modify the example provided in [Customizing Operations By Using Stored Procedures](../../../../../../docs/framework/data/adonet/sql/linq/customizing-operations-by-using-stored-procedures.md) by replacing even the first query (which causes dynamic SQL execution) with a method call that wraps a stored procedure.</span></span>  
  
 <span data-ttu-id="7df5f-107">次の例に示すように、`CustomersByCity` がこのメソッドであることを前提とします。</span><span class="sxs-lookup"><span data-stu-id="7df5f-107">Assume `CustomersByCity` is the method, as in the following example.</span></span>  
  
### <a name="code"></a><span data-ttu-id="7df5f-108">コード</span><span class="sxs-lookup"><span data-stu-id="7df5f-108">Code</span></span>  
 [!code-csharp[DLinqOverrideDefaultSproc#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefaultSproc/cs/northwind.cs#4)]
 [!code-vb[DLinqOverrideDefaultSproc#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefaultSproc/vb/northwind.vb#4)]  
  
 <span data-ttu-id="7df5f-109">次のコードは、動的 SQL を使わずに実行されます。</span><span class="sxs-lookup"><span data-stu-id="7df5f-109">The following code executes without any dynamic SQL.</span></span>  
  
 [!code-csharp[DLinqOverrideDefaultSproc#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefaultSproc/cs/Program.cs#5)]
 [!code-vb[DLinqOverrideDefaultSproc#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefaultSproc/vb/Module1.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="7df5f-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="7df5f-110">See also</span></span>
- [<span data-ttu-id="7df5f-111">既定の動作をオーバーライドするときの開発者の責任</span><span class="sxs-lookup"><span data-stu-id="7df5f-111">Responsibilities of the Developer In Overriding Default Behavior</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/responsibilities-of-the-developer-in-overriding-default-behavior.md)
