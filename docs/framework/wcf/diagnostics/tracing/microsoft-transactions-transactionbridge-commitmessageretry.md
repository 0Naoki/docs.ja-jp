---
title: Microsoft.Transactions.TransactionBridge.CommitMessageRetry
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4abe01f0-6398-4fba-b2f3-c054b7f7e971
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2e272ec6855edba1bb6a05c494270e08dffd29c1
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/02/2017
---
# <a name="microsofttransactionstransactionbridgecommitmessageretry"></a>Microsoft.Transactions.TransactionBridge.CommitMessageRetry
コミット メッセージの再試行は、応答しない参加要素に送信されました。  
  
## <a name="description"></a>説明  
 ローカル トランザクション マネージャーが一定時間内に応答を受信せず、下位の参加要素にコミット メッセージを再送信する必要があった場合にトレースされます。  
  
## <a name="troubleshooting"></a>トラブルシューティング  
 応答が時間どおりに配信されない原因となっている可能性のあるネットワークや製品の問題について調査します。  このメッセージが多数表示される場合、インフラストラクチャに問題があるか、または応答時間が異常にかかっていることを示します。 いずれの問題によっても、システム内のトランザクションのスループットが大幅に低下します。  
  
## <a name="see-also"></a>関連項目  
 [トレース](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [トレースを使用して、アプリケーションのトラブルシューティング](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [管理と診断](../../../../../docs/framework/wcf/diagnostics/index.md)
