---
title: "CorDebugUserState 列挙型"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- CorDebugUserState
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugUserState
helpviewer_keywords:
- CorDebugUserState enumeration [.NET Framework debugging]
ms.assetid: 5f6c2bcd-8102-4e3b-abc5-86ab0bd62def
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 57fd9df27b1911c90bd11712b67e6e64588c2b5f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="cordebuguserstate-enumeration"></a>CorDebugUserState 列挙型
スレッドのユーザーの状態を示します。  
  
## <a name="syntax"></a>構文  
  
```  
typedef enum CorDebugUserState {  
    USER_STOP_REQUESTED     =  0x01,  
    USER_SUSPEND_REQUESTED  =  0x02,  
    USER_BACKGROUND         =  0x04,  
    USER_UNSTARTED          =  0x08,  
    USER_STOPPED            =  0x10,  
    USER_WAIT_SLEEP_JOIN    =  0x20,  
    USER_SUSPENDED          =  0x40,  
    USER_UNSAFE_POINT       =  0x80,  
    USER_THREADPOOL         = 0x100  
} CorDebugUserState;  
```  
  
## <a name="members"></a>メンバー  
  
|値|説明|  
|-----------|-----------------|  
|`USER_STOP_REQUESTED`|スレッドの終了が要求されました。|  
|`USER_SUSPEND_REQUESTED`|スレッドの中断が要求されました。|  
|`USER_BACKGROUND`|スレッドのバック グラウンドで実行します。|  
|`USER_UNSTARTED`|スレッドは、実行を開始していません。|  
|`USER_STOPPED`|スレッドが終了しました。|  
|`USER_WAIT_SLEEP_JOIN`|スレッドは、別のスレッドにタスクの完了を待機しています。|  
|`USER_SUSPENDED`|スレッドが中断されました。|  
|`USER_UNSAFE_POINT`|スレッドは、アンセーフ ポイントでです。 つまり、スレッドはポイントで実行ガベージ コレクションを妨げること可能性があります。<br /><br /> デバッグ イベントは、安全でないポイントからディスパッチすることがありますが、安全でない時点でスレッドを中断する可能性が高いデッドロックが発生スレッドが再開されるまでです。 安全性と安全でないポイントは、・ イン タイム (JIT) とガベージ コレクションの実装によって決まります。|  
|`USER_THREADPOOL`|スレッドはスレッド プールです。|  
  
## <a name="remarks"></a>コメント  
 スレッドのユーザーの状態は、スレッドが、デバッガーがチェック時に状態です。 スレッドは、ユーザー状態の組み合わせがあります。  
  
 使用して、 [icordebugthread::getuserstate](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getuserstate-method.md)スレッドのユーザー状態を取得します。  
  
## <a name="requirements"></a>必要条件  
 **プラットフォーム:**を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。  
  
 **ヘッダー:** CorDebug.idl、CorDebug.h  
  
 **ライブラリ:** CorGuids.lib  
  
 **.NET framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>参照  
 [列挙型のデバッグ](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
