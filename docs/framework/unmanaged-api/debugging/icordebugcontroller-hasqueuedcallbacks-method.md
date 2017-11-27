---
title: "ICorDebugController::HasQueuedCallbacks メソッド"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugController.HasQueuedCallbacks
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugController::HasQueuedCallbacks
helpviewer_keywords:
- HasQueuedCallbacks method [.NET Framework debugging]
- ICorDebugController::HasQueuedCallbacks method [.NET Framework debugging]
ms.assetid: 0d6a1cd9-370b-4462-adbf-e3980e897ea7
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 81830cbadcf9fb359b8e1a74cd47f9d18543c29c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugcontrollerhasqueuedcallbacks-method"></a>ICorDebugController::HasQueuedCallbacks メソッド
任意のマネージ コールバックが、指定されたスレッドの現在キューに登録するかどうかを示す値を取得します。  
  
## <a name="syntax"></a>構文  
  
```  
HRESULT HasQueuedCallbacks (  
    [in] ICorDebugThread *pThread,  
    [out] BOOL           *pbQueued  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pThread`  
 [in]スレッドを表す"ICorDebugThread"オブジェクトへのポインター。  
  
 `pbQueued`  
 [out]ある値へのポインター`true`任意のマネージ コールバックがいると、指定したスレッドのキューに置かれた、それ以外の場合は`false`します。  
  
 Null が指定されている場合、`pThread`パラメーター、`HasQueuedCallbacks`戻ります`true`マネージ コールバックが任意のスレッドのキューに存在している場合。  
  
## <a name="remarks"></a>コメント  
 コールバックに毎回、一度に 1 つのディスパッチなります[icordebugcontroller::continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md)と呼びます。 デバッガーは、同時に発生する複数のデバッグ イベントを報告する必要がある場合、このフラグを確認できます。  
  
 デバッグ イベントのキューに入っているときに、既に、発生したため、デバッガーがデバッグ対象の状態を確認するためのキュー全体をドレインする必要があります。 (呼び出し`ICorDebugController::Continue`するキューのドレインを実行します)。たとえば、キューには、スレッドで 2 つのデバッグ イベントが含まれている場合*X*、デバッガーがスレッドを中断および*X* 、最初のデバッグ イベントとし、呼び出しの後に`ICorDebugController::Continue`、2 番目のデバッグ イベントをスレッド*X*スレッドが中断されましたがディスパッチされます。  
  
## <a name="requirements"></a>要件  
 **プラットフォーム:**を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。  
  
 **ヘッダー:** CorDebug.idl、CorDebug.h  
  
 **ライブラリ:** CorGuids.lib  
  
 **.NET framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>関連項目  
 
