---
title: ICorDebugValue::GetAddress メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugValue.GetAddress
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue::GetAddress
helpviewer_keywords:
- ICorDebugValue::GetAddress method [.NET Framework debugging]
- GetAddress method, ICorDebugValue interface [.NET Framework debugging]
ms.assetid: a247c792-45e1-4538-9e1f-b46acca4a463
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b88c49ba93ff3c4cc3f5c7a656dfa5da6e82109e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54559843"
---
# <a name="icordebugvaluegetaddress-method"></a>ICorDebugValue::GetAddress メソッド
デバッグ対象プロセスでは、この"ICorDebugValue"オブジェクトのアドレスを取得します。  
  
## <a name="syntax"></a>構文  
  
```  
HRESULT GetAddress (  
    [out] CORDB_ADDRESS   *pAddress  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pAddress`  
 [out]ポインターを`CORDB_ADDRESS`値オブジェクトのアドレスを指定するオブジェクト。  
  
## <a name="remarks"></a>Remarks  
 値が使用できない場合は、0 (ゼロ) が返されます。 これは、値は、レジスタで少なくとも一部場合に発生する可能性がありますまたはガベージ コレクター ハンドルに格納されている (`GCHandle`)。  
  
## <a name="requirements"></a>必要条件  
 **プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。  
  
 **ヘッダー:** CorDebug.idl、CorDebug.h  
  
 **ライブラリ:** CorGuids.lib  
  
 **.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>関連項目

