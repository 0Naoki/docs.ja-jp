---
title: "CorDebugBlockingObject 構造体"
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
- CorDebugBlockingObject Structure
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugBlockingObject
helpviewer_keywords:
- CorDebugBlockingObject structure [.NET Framework debugging]
ms.assetid: 5944edd1-0914-4efa-aba0-d5a277c38b1a
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 85b48fd565d7cc4bb158260df167477d3e61d81e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="cordebugblockingobject-structure"></a>CorDebugBlockingObject 構造体
スレッドとスレッドがブロックされている特定の理由をブロックしているオブジェクトを定義します。  
  
## <a name="syntax"></a>構文  
  
```  
Typedef struct CorDebugBlockingObject  
{  
ICorDebugValue pBlockingObject;  
DWORD dwTimeout;  
CorDebugBlockingReason blockingReason;  
}  CorDebugBlockingObject;  
```  
  
## <a name="members"></a>メンバー  
  
|メンバー|説明|  
|------------|-----------------|  
|`pBlockingObject`|スレッドがブロックしているオブジェクト。 このオブジェクトは、現在の同期状態の期間に対してのみ有効です。 予想される場合があります、同じ同期された状態で同じオブジェクトで 2 つのスレッドのブロックは場合、 [icordebugvalue::getaddress](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getaddress-method.md)を同じ値を返すメソッド。 ただし、インターフェイスは、同等のポインターができない可能性があります。|  
|`dwTimeout`|ブロックしている操作の前に時間をミリ秒単位は、タイムアウト、または値を示すものではタイムアウトしない INFINITE されます。タイムアウト値は、時間が残っているではなく、ブロック操作の時間の合計の長さを指定します。|  
|`blockingReason`|このオブジェクトのスレッドがブロックされている理由です。|  
  
## <a name="remarks"></a>コメント  
  
## <a name="requirements"></a>必要条件  
 **プラットフォーム:**を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。  
  
 **ヘッダー:** CorDebug.idl  
  
 **ライブラリ:** CorGuids.lib  
  
 **.NET framework のバージョン:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>参照  
 [デバッグ構造体](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [デバッグ](../../../../docs/framework/unmanaged-api/debugging/index.md)
