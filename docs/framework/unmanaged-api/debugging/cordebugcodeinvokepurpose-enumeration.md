---
title: CorDebugCodeInvokePurpose 列挙体
ms.date: 03/30/2017
api_name:
- CorDebugInvokePurpose
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 31833a2d-a0d6-48a1-b05f-995ca307a08f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 79730bb98a7e2d84517ed068a52614ad8650f541
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33406222"
---
# <a name="cordebugcodeinvokepurpose-enumeration"></a>CorDebugCodeInvokePurpose 列挙体
エクスポートされた関数がマネージ コードを呼び出す理由を示します。  
  
## <a name="syntax"></a>構文  
  
```  
typedef enum CorDebugCodeInvokePurpose  
{  
    CODE_INVOKE_PURPOSE_NONE,  
    CODE_INVOKE_PURPOSE_NATIVE_TO_MANAGED_TRANSITION,    
    CODE_INVOKE_PURPOSE_CLASS_INIT,  
    CODE_INVOKE_PURPOSE_INTERFACE_DISPATCH,  
} CorDebugCodeInvokePurpose;  
```  
  
## <a name="members"></a>メンバー  
  
|メンバー|説明|  
|------------|-----------------|  
|`CODE_INVOKE_PURPOSE_NONE`|None または不明です。|  
|`CODE_INVOKE_PURPOSE_NATIVE_TO_MANAGED_TRANSITION`|マネージ コードは、逆 p-invoke などのすべてのマネージ エントリ ポイントを実行します。 より詳細な目的は、ランタイムによって認識されません。|  
|`CODE_INVOKE_PURPOSE_CLASS_INIT`|マネージ コードは、静的コンストラクターを実行します。|  
|`CODE_INVOKE_PURPOSE_INTERFACE_DISPATCH`|マネージ コードは、呼び出されたいくつかのインターフェイス メソッドの実装を実行します。|  
  
## <a name="remarks"></a>コメント  
 この列挙体を使って、 [icordebugprocess 6::getexportstepinfo](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-getexportstepinfo-method.md)マネージ コードをステップ実行に関する情報を提供するメソッド。  
  
> [!NOTE]
>  この列挙体は .NET ネイティブのデバッグ シナリオのみで使用することを目的としています。  
  
## <a name="requirements"></a>要件  
 **プラットフォーム:** を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。  
  
 **ヘッダー:** CorDebug.idl、CorDebug.h  
  
 **ライブラリ:** CorGuids.lib  
  
 **.NET framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>関連項目  
 [列挙型のデバッグ](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)  
 [デバッグ](../../../../docs/framework/unmanaged-api/debugging/index.md)
