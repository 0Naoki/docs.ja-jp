---
title: "ICorDebugValue3::GetSize64 メソッド"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugValue3::GetSize64
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugValue3::GetSize64
helpviewer_keywords:
- GetSize64 method, ICorDebugValue3 interface [.NET Framework debugging]
- ICorDebugValue3::GetSize64 method [.NET Framework debugging]
ms.assetid: fee56a29-3154-4192-958d-71da2ced3740
topic_type: apiref
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b129ebe666972052775c2c3e44e38bb6a25a176e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugvalue3getsize64-method"></a>ICorDebugValue3::GetSize64 メソッド
サイズを取得します (バイト単位) のこの[ICorDebugValue3](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md)オブジェクト。  
  
## <a name="syntax"></a>構文  
  
```  
HRESULT GetSize64(  
    [out] ULONG64 *pSize  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 pSize  
 [out]このオブジェクトのバイト単位のサイズへのポインター。  
  
## <a name="remarks"></a>コメント  
 この値の型が参照型の場合は、このメソッドは、オブジェクトのサイズではなく、ポインターのサイズを返します。  
  
 `ICorDebugValue3::GetSize`メソッドとは異なります、 [icordebugvalue::getsize](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getsize-method.md)出力パラメーターの型のメソッドです。 [Icordebugvalue::getsize](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getsize-method.md)、出力パラメーターが、 `ULONG32``ICorDebugValue3::GetSize`は、`ULONG64`です。 これにより、 [ICorDebugValue3](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md) 2 GB を超える配列のサイズを報告するインターフェイスです。  
  
## <a name="requirements"></a>要件  
 **プラットフォーム:**を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。  
  
 **ヘッダー:** CorDebug.idl、CorDebug.h  
  
 **ライブラリ:** CorGuids.lib  
  
 **.NET framework のバージョン:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>関連項目  
 [ICorDebugValue3 インターフェイス](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md)  
 [デバッグのインターフェイス](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
