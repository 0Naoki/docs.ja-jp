---
title: ETaskType 列挙型
ms.date: 03/30/2017
api_name:
- ETaskType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ETaskType
helpviewer_keywords:
- ETaskType enumeration [.NET Framework hosting]
ms.assetid: aa527b31-89d4-41f2-ad6f-63b76950b7df
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 59fdc3d4682fe3c1967c8153043dc1bfe0668c35
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54610540"
---
# <a name="etasktype-enumeration"></a>ETaskType 列挙型
いずれかで表されるタスクの種類を示す値を含む、 [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)または[IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)インターフェイス。  
  
## <a name="syntax"></a>構文  
  
```  
typedef enum ETaskType {  
    TT_DEBUGGERHELPER           = 0x1,  
    TT_GC                       = 0x2,  
    TT_FINALIZER                = 0x4,  
    TT_THREADPOOL_TIMER         = 0x8,  
    TT_THREADPOOL_GATE          = 0x10,  
    TT_THREADPOOL_WORKER        = 0x20,  
    TT_THREADPOOL_IOCOMPLETION  = 0x40,  
    TT_ADUNLOAD                 = 0x80,  
    TT_USER                     = 0x100,  
    TT_THREADPOOL_WAIT          = 0x200,  
    TT_UNKNOWN                  = 0x80000000  
} ETaskType;  
```  
  
## <a name="members"></a>メンバー  
  
|メンバー|説明|  
|------------|-----------------|  
|`TT_ADUNLOAD`|このインターフェイスは、アプリケーション ドメインのアンロード タスクを表します。|  
|`TT_DEBUGGERHELPER`|このインターフェイスは、デバッガー ヘルパーのタスクを表します。|  
|`TT_FINALIZER`|このインターフェイスは、ファイナライザーのタスクを表します。|  
|`TT_GC`|このインターフェイスは、ガベージ コレクションのタスクを表します。|  
|`TT_THREADPOOL_GATE`|このインターフェイスは、ゲートのスレッドのタスクを表します。|  
|`TT_THREADPOOL_IOCOMPLETION`|このインターフェイスは、I/O スレッドのタスクまたはタスクの完了ポート スレッドを表します。|  
|`TT_THREADPOOL_TIMER`|このインターフェイスは、タイマー スレッドのタスクを表します。|  
|`TT_THREADPOOL_WAIT`|このインターフェイスは、待機スレッドのタスクを表します。|  
|`TT_THREADPOOL_WORKER`|このインターフェイスは、ワーカー スレッドのタスクを表します。|  
|`TT_UNKNOWN`|タスクが不明です。|  
|`TT_USER`|このインターフェイスは、ユーザーのタスクを表します。|  
  
## <a name="requirements"></a>必要条件  
 **プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。  
  
 **ヘッダー:** MSCorEE.h  
  
 **ライブラリ:** MSCorEE.dll  
  
 **.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>関連項目
- [ホスティングの列挙型](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
