---
title: "CorDebugCodeInvokeKind 列挙体"
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
- CorDebugCodeInvokeKind
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: e795e6a2-1008-4a81-af88-d777888e942e
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 10b45938cfe63fa98fdb06bc20c66cc0f25c41a2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="cordebugcodeinvokekind-enumeration"></a>CorDebugCodeInvokeKind 列挙体
エクスポートされた関数がマネージ コードを呼び出す方法を示します。  
  
## <a name="syntax"></a>構文  
  
```  
typedef enum CorDebugCodeInvokeKind  
{  
    CODE_INVOKE_KIND_NONE,       
    CODE_INVOKE_KIND_RETURN,     
    CODE_INVOKE_KIND_TAILCALL,   
} CorDebugCodeInvokeKind;  
```  
  
## <a name="members"></a>メンバー  
  
|メンバー|説明|  
|------------|-----------------|  
|`CODE_INVOKE_KIND_NONE`|マネージ コードがこのメソッドによって呼び出される場合は、明示的なイベントまたはブレークポイントによって後で配置する必要があります。<br /><br /> または<br /><br /> このメソッドが呼び出すマネージ コードは、停止する簡単な方法がないため、一部を見逃す可能性があります。<br /><br /> または<br /><br /> メソッドがマネージ コードを呼び出さない可能性があります。|  
|`CODE_INVOKE_KIND_RETURN`|このメソッドは、戻り命令を使用してマネージ コードを呼び出します。 ステップ アウトは次のマネージ コードに到達する必要があります。|  
|`CODE_INVOKE_KIND_TAILCALL`|このメソッドは、末尾呼び出しを使用してマネージ コードを呼び出します。 いずれかの呼び出し命令をシングル ステップ実行およびステップ オーバーすると、マネージ コードに到達します。|  
  
## <a name="remarks"></a>コメント  
 この列挙体を使って、 [icordebugprocess 6::getexportstepinfo](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-getexportstepinfo-method.md)マネージ コードをステップ実行に関する情報を提供するメソッド。  
  
> [!NOTE]
>  この列挙体は .NET ネイティブのデバッグ シナリオのみで使用することを目的としています。  
  
## <a name="requirements"></a>必要条件  
 **プラットフォーム:**を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。  
  
 **ヘッダー:** CorDebug.idl、CorDebug.h  
  
 **ライブラリ:** CorGuids.lib  
  
 **.NET framework のバージョン:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>参照  
 [列挙型のデバッグ](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)  
 [デバッグ](../../../../docs/framework/unmanaged-api/debugging/index.md)
