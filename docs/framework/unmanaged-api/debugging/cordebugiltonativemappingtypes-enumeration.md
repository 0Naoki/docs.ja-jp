---
title: CorDebugIlToNativeMappingTypes 列挙型
ms.date: 03/30/2017
api_name:
- CorDebugIlToNativeMappingTypes
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugIlToNativeMappingTypes
helpviewer_keywords:
- CorDebugIIToNativeMappingTypes enumeration [.NET Framework debugging]
ms.assetid: c35e2919-42c3-4ba0-ae28-443c35f66f93
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 61b57d534770c6ab7cacbc2c084ac364dc31863f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54717611"
---
# <a name="cordebugiltonativemappingtypes-enumeration"></a>CorDebugIlToNativeMappingTypes 列挙型
COR_DEBUG_IL_TO_NATIVE_MAP 構造体のインスタンスによって表されるネイティブの命令の特定の範囲が特別なコード領域に対応するかどうかを示します。  
  
## <a name="syntax"></a>構文  
  
```  
typedef enum CorDebugIlToNativeMappingTypes {  
    NO_MAPPING = -1,  
    PROLOG     = -2,  
    EPILOG     = -3  
} CorDebugIlToNativeMappingTypes;  
```  
  
## <a name="members"></a>メンバー  
  
|メンバー|説明|  
|------------|-----------------|  
|`NO_MAPPING`|ネイティブ命令の範囲は、特別なコードの任意のリージョンに対応していません。|  
|`PROLOG`|ネイティブ命令の範囲は、プロローグに対応します。|  
|`EPILOG`|ネイティブ命令の範囲は、エピローグに対応します。|  
  
## <a name="requirements"></a>必要条件  
 **プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。  
  
 **ヘッダー:** CorDebug.idl、CorDebug.h  
  
 **ライブラリ:** CorGuids.lib  
  
 **.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>関連項目
- [GetILToNativeMapping メソッド](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getiltonativemapping-method.md)
- [列挙型のデバッグ](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
