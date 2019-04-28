---
title: Microsoft.Transactions.TransactionBridge.RegistrationCoordinatorResponseInvalidMetadata
ms.date: 03/30/2017
ms.assetid: a174bbf5-0ffe-4fda-969d-e7fbd1996123
ms.openlocfilehash: 664fbad52cdb66d3bf7b58ff639c62c8c18b1e56
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61666860"
---
# <a name="microsofttransactionstransactionbridgeregistrationcoordinatorresponseinvalidmetadata"></a><span data-ttu-id="7993b-102">Microsoft.Transactions.TransactionBridge.RegistrationCoordinatorResponseInvalidMetadata</span><span class="sxs-lookup"><span data-stu-id="7993b-102">Microsoft.Transactions.TransactionBridge.RegistrationCoordinatorResponseInvalidMetadata</span></span>
<span data-ttu-id="7993b-103">WS-AtomicTransaction プロトコル サービスは、無効または互換性のないメタデータのあるエンドポイント参照を含むそのコーディネーターから、RegisterResponse メッセージを受信しました。</span><span class="sxs-lookup"><span data-stu-id="7993b-103">The WS-Atomic Transaction protocol service received a RegisterResponse message from its coordinator that contains an endpoint reference with invalid or incompatible metadata.</span></span>  
  
## <a name="description"></a><span data-ttu-id="7993b-104">説明</span><span class="sxs-lookup"><span data-stu-id="7993b-104">Description</span></span>  
 <span data-ttu-id="7993b-105">ローカルのトランザクション マネージャーが、その上位のトランザクション マネージャーに登録を試み、上位のトランザクション マネージャーが、RegisterResponse メッセージ内の無効なアドレスを返すときにトレースされます。</span><span class="sxs-lookup"><span data-stu-id="7993b-105">Traced when the local Transaction Manager tries to register with its superior Transaction Manager and the superior returns an invalid address within the RegisterResponse message.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7993b-106">関連項目</span><span class="sxs-lookup"><span data-stu-id="7993b-106">See also</span></span>

- [<span data-ttu-id="7993b-107">トレース</span><span class="sxs-lookup"><span data-stu-id="7993b-107">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="7993b-108">トレースを使用したアプリケーションのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="7993b-108">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="7993b-109">管理と診断</span><span class="sxs-lookup"><span data-stu-id="7993b-109">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
