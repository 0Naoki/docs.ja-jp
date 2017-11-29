---
title: "CorDebugChainReason 列挙型"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorDebugChainReason
api_location: mscordbi.dll
api_type: COM
f1_keywords: CorDebugChainReason
helpviewer_keywords: CorDebugChainReason enumeration [.NET Framework debugging]
ms.assetid: c915da51-50b2-41df-841a-2b971f4d0975
topic_type: apiref
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0d501db111256861a3d0a602712e4c32f40b7b6e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2017
---
# <a name="cordebugchainreason-enumeration"></a>CorDebugChainReason 列挙型
呼び出しチェーンが開始する理由を示します。  
  
## <a name="syntax"></a>構文  
  
```  
typedef enum CorDebugChainReason {  
    CHAIN_NONE              = 0x000,  
    CHAIN_CLASS_INIT        = 0x001,  
    CHAIN_EXCEPTION_FILTER  = 0x002,  
    CHAIN_SECURITY          = 0x004,  
    CHAIN_CONTEXT_POLICY    = 0x008,  
    CHAIN_INTERCEPTION      = 0x010,  
    CHAIN_PROCESS_START     = 0x020,  
    CHAIN_THREAD_START      = 0x040,  
    CHAIN_ENTER_MANAGED     = 0x080,  
    CHAIN_ENTER_UNMANAGED   = 0x100,  
    CHAIN_DEBUGGER_EVAL     = 0x200,  
    CHAIN_CONTEXT_SWITCH    = 0x400,  
    CHAIN_FUNC_EVAL         = 0x800  
} CorDebugChainReason;  
```  
  
## <a name="members"></a>メンバー  
  
|メンバー|説明|  
|------------|-----------------|  
|`CHAIN_NONE`|呼び出しチェーンが開始されていません。|  
|`CHAIN_CLASS_INIT`|コンストラクターによって、チェーンが開始されました。|  
|`CHAIN_EXCEPTION_FILTER`|例外フィルターによって、チェーンが開始されました。|  
|`CHAIN_SECURITY`|セキュリティを適用するコードによって、チェーンが開始されました。|  
|`CHAIN_CONTEXT_POLICY`|コンテキスト ポリシーによって、チェーンが開始されました。|  
|`CHAIN_INTERCEPTION`|使用しません。|  
|`CHAIN_PROCESS_START`|使用しません。|  
|`CHAIN_THREAD_START`|スレッド実行の開始によって、チェーンが開始されました。|  
|`CHAIN_ENTER_MANAGED`|マネージ コードへのエントリによって、チェーンが開始されました。|  
|`CHAIN_ENTER_UNMANAGED`|アンマネージ コードへのエントリによって、チェーンが開始されました。|  
|`CHAIN_DEBUGGER_EVAL`|使用しません。|  
|`CHAIN_CONTEXT_SWITCH`|使用しません。|  
|`CHAIN_FUNC_EVAL`|関数の評価によって、チェーンが開始されました。|  
  
## <a name="remarks"></a>コメント  
 使用して、 [icordebugchain::getreason](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getreason-method.md)メソッドの呼び出しチェーンが開始する理由を確認するためにします。  
  
## <a name="requirements"></a>要件  
 **プラットフォーム:**を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。  
  
 **ヘッダー:** CorDebug.idl、CorDebug.h  
  
 **ライブラリ:** CorGuids.lib  
  
 **.NET framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>関連項目  
 [列挙体のデバッグ](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
