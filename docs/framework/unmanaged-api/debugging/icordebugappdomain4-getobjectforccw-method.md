---
title: ICorDebugAppDomain4::GetObjectForCCW メソッド
ms.date: 03/30/2017
ms.assetid: 2cacdb85-e7b8-42e7-b310-c3e8c22e5d33
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9eeb0b80ba691d813e3193f7ae746129c6725e1e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54506538"
---
# <a name="icordebugappdomain4getobjectforccw-method"></a>ICorDebugAppDomain4::GetObjectForCCW メソッド
COM 呼び出し可能ラッパー (CCW: COM Callable Wrapper) ポインターからマネージド オブジェクトを取得します。  
  
## <a name="syntax"></a>構文  
  
```  
HRESULT GetObjectForCCW(  
   [in]CORDB_ADDRESS ccwPointer,   
   [out]ICorDebugValue **ppManagedObject  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `ccwPointer`  
 [in] COM 呼び出し可能ラッパー (CCW) ポインター。  
  
 `ppManagedObject`  
 [out]指定の CCW ポインターに対応するマネージ オブジェクトを表す"ICorDebugValue"オブジェクトのアドレスへのポインター。  
  
## <a name="remarks"></a>Remarks  
  
## <a name="requirements"></a>必要条件  
 **プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。  
  
 **ヘッダー:** CorDebug.idl、CorDebug.h  
  
 **ライブラリ:** CorGuids.lib  
  
 **.NET Framework のバージョン:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]  
  
## <a name="see-also"></a>関連項目
- [ICorDebugAppDomain4 インターフェイス](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain4-interface.md)
- [デバッグ インターフェイス](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
