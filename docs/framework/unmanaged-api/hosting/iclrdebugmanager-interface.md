---
title: "ICLRDebugManager インターフェイス"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRDebugManager
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRDebugManager
helpviewer_keywords: ICLRDebugManager interface [.NET Framework hosting]
ms.assetid: e835062c-c7d6-4945-8a44-2de7ebf3928e
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8e712f22156e96cfc58e9c1a835077ba21ecd184
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="iclrdebugmanager-interface"></a>ICLRDebugManager インターフェイス
識別子と表示名に一連のタスクを関連付けるホストをできるようにするメソッドを提供します。  
  
## <a name="methods"></a>メソッド  
  
|メソッド|説明|  
|------------|-----------------|  
|[BeginConnection メソッド](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md)|識別子とフレンドリ名を持つタスクを関連付けるには、ホストとデバッガーの間の新しい接続を確立します。|  
|[EndConnection メソッド](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md)|タスクの一覧、識別子、およびフレンドリ名の間の関連付けを削除します。|  
|[GetDacl メソッド](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-getdacl-method.md)|このメソッドは実装されていません。|  
|[IsDebuggerAttached メソッド](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-isdebuggerattached-method.md)|デバッガーがプロセスにアタッチされているかどうかを示す値を取得します。|  
|[SetConnectionTasks メソッド](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md)|リストを関連付けます[ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)インスタンス識別子とフレンドリ名を使用します。|  
|[SetDacl メソッド](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setdacl-method.md)|このメソッドは実装されていません。|  
|[SetSymbolReadingPolicy メソッド](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setsymbolreadingpolicy-method.md)|プログラム データベース (PDB) ファイルを読み取るためのポリシーを設定します。 ポリシーは、呼び出し履歴に行番号およびファイルに関する情報が含まれているかどうかを判断します。|  
  
## <a name="remarks"></a>コメント  
 デバッグする場合、ホストは、独自のプログラミング ロジックに従ってタスクをグループ化をする可能性があります。 たとえば、グループ化では、開発者は、プロセスで実行されているすべてのタスクを表示せず、開発者の Api で必要なタスクのみが表示とできます。 `ICLRDebugManager`このようなグループ化を実装をホストできるようにします。  
  
> [!IMPORTANT]
>  次の 3 つ`ICLRDebugManager`メソッド、 `BeginConnection`、`SetConnectionTasks`と`EndConnection`、互いに依存します。 期待どおりに動作するように指定された順序で呼び出す必要があります。  
  
 グループ化識別子とホストは、グループに割り当てます。 フレンドリ名なしの意味を持ちます共通言語ランタイム (CLR)。 CLR は、デバッガーに情報を渡すだけです。  
  
## <a name="requirements"></a>必要条件  
 **プラットフォーム:**を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。  
  
 **ヘッダー:** MSCorEE.h  
  
 **ライブラリ:** MSCorEE.dll にリソースとして含まれています。  
  
 **.NET framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>参照  
 [ホスト インターフェイス](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
