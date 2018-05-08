---
title: ICorDebugILCode::GetEHClauses メソッド
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugILCode.GetEHClauses
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: cf7a0e00-06ae-47a5-8037-598b26196802
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8eca550130a22532cb781e09ec59c60c11a5ba33
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugilcodegetehclauses-method"></a>ICorDebugILCode::GetEHClauses メソッド
[.NET Framework 4.5.2 以降のバージョンでのみでサポート]  
  
 この中間言語 (IL) に対して定義されている例外処理 (EH) 句のリストへのポインターを返します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT GetEHClauses(  
   [in] ULONG32 cClauses,  
   [out] ULONG32 * pcClauses,  
   [out, size_is(cClauses), length_is(*pcClauses)] CorDebugEHClause clauses[]);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `cClauses`  
 [in] `clauses` アレイの記憶容量。 詳細については、次の「解説」を参照してください。  
  
 `pcClauses`  
 [out] 情報が `clauses` アレイに書き込まれる場合に、対象となる句の数。  
  
 clauses  
 [out]配列[CorDebugEHClause](../../../../docs/framework/unmanaged-api/debugging/cordebugehclause-structure.md)例外処理句のこの IL に対して定義されている情報を含むオブジェクト。  
  
## <a name="remarks"></a>コメント  
 場合`cClauses`0 と`pcClauses`以外**null**、`pcClauses`が利用可能な例外処理句の数に設定します。 `cClauses` が 0 以外の場合は、`clauses` アレイの記憶容量を表します。 メソッドが戻るとき、`clauses` には、`cClauses` の最大項目が含まれ、`pcClauses` は、実際に`clauses` アレイに書き込まれる句の数が設定されます。  
  
## <a name="requirements"></a>要件  
 **プラットフォーム:** を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。  
  
 **ヘッダー:** CorDebug.idl、CorDebug.h  
  
 **ライブラリ:** CorGuids.lib  
  
 **.NET framework のバージョン:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>関連項目  
 [ICorDebugILCode インターフェイス](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md)  
 [CorDebugEHClause 構造体](../../../../docs/framework/unmanaged-api/debugging/cordebugehclause-structure.md)  
 [デバッグ インターフェイス](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
