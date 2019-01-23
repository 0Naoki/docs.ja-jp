---
title: Microsoft.Transactions.TransactionBridge.RegisterParticipantFailure
ms.date: 03/30/2017
ms.assetid: 3a4ead79-8550-4037-84e3-fd70ff56e001
ms.openlocfilehash: b94c017f6ed3a76a6bc5ed2cb970877ad18ef9ea
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54610423"
---
# <a name="microsofttransactionstransactionbridgeregisterparticipantfailure"></a><span data-ttu-id="0776d-102">Microsoft.Transactions.TransactionBridge.RegisterParticipantFailure</span><span class="sxs-lookup"><span data-stu-id="0776d-102">Microsoft.Transactions.TransactionBridge.RegisterParticipantFailure</span></span>
<span data-ttu-id="0776d-103">WS-AT プロトコル サービスは、制御プロトコルの参加要素の登録に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="0776d-103">The WS-AT protocol service failed to register a participant for a control protocol.</span></span>  
  
## <a name="description"></a><span data-ttu-id="0776d-104">説明</span><span class="sxs-lookup"><span data-stu-id="0776d-104">Description</span></span>  
 <span data-ttu-id="0776d-105">MSDTC により無効な登録要求が検出された場合にトレースされます。</span><span class="sxs-lookup"><span data-stu-id="0776d-105">Traced if MSDTC detects an invalid Registration request.</span></span> <span data-ttu-id="0776d-106">これは、複数の完了登録要求や内部エラーによって発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="0776d-106">This can be caused by  multiple Completion registration requests and internal errors.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="0776d-107">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="0776d-107">Troubleshooting</span></span>  
 <span data-ttu-id="0776d-108">完了を複数回登録しないでください。</span><span class="sxs-lookup"><span data-stu-id="0776d-108">Do not try to Register for Completion more than once.</span></span>  <span data-ttu-id="0776d-109">また、トレース メッセージ内のステータス文字列を調べて、アクション可能な項目が存在するかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="0776d-109">Also, inspect the status string within the trace message to determine if any actionable item exists.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0776d-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="0776d-110">See also</span></span>
- [<span data-ttu-id="0776d-111">トレース</span><span class="sxs-lookup"><span data-stu-id="0776d-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="0776d-112">トレースを使用したアプリケーションのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="0776d-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="0776d-113">管理と診断</span><span class="sxs-lookup"><span data-stu-id="0776d-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
