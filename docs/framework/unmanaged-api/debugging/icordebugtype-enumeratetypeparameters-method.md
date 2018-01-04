---
title: "ICorDebugType::EnumerateTypeParameters メソッド"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugType.EnumerateTypeParameters
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugType::EnumerateTypeParameters
helpviewer_keywords:
- EnumerateTypeParameters method, ICorDebugType interface [.NET Framework debugging]
- ICorDebugType::EnumerateTypeParameters method [.NET Framework debugging]
ms.assetid: 1ee1f6e6-1bd7-4ebb-83b8-ff9a08ca03de
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d4b864b2b5fd4f2a6ed03218ce6e7b6f3bf62202
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugtypeenumeratetypeparameters-method"></a>ICorDebugType::EnumerateTypeParameters メソッド
含む ICorDebugTypeEnum へのインターフェイス ポインターを取得、<xref:System.Type>この ICorDebugType によって参照されるクラスのパラメーターです。  
  
## <a name="syntax"></a>構文  
  
```  
HRESULT EnumerateTypeParameters (  
    [out] ICorDebugTypeEnum   **ppTyParEnum  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `ppTyParEnum`  
 [out]アドレスへのポインター、`ICorDebugTypeEnum`型のパラメーターを格納しています。  
  
## <a name="remarks"></a>コメント  
 使用することができます`EnumerateTypeParameters`CorElementType 値がによって返される場合[icordebugtype::gettype](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md) ELEMENT_TYPE_CLASS ELEMENT_TYPE_VALUETYPE、ELEMENT_TYPE_ARRAY、インポートする場合、ELEMENT_TYPE_BYREF ELEMENT_TYPE にはPTR、または ELEMENT_TYPE_FNPTR します。 パラメーターとその順序の数は、型によって異なります。  
  
-   ELEMENT_TYPE_CLASS または ELEMENT_TYPE_VALUETYPE: に含まれている型パラメーターの数、`ICorDebugTypeEnum`このメソッドが戻るし、対応するクラスを仮引数型のパラメーターの数によって異なります。 たとえば、次の種類は`class Dict<String,int32>`、し`EnumerateTypeParameters`が返されます、`ICorDebugTypeEnum`を表すオブジェクトを格納している`String`と`int32`シーケンスでします。  
  
-   ELEMENT_TYPE_FNPTR: 含まれている型パラメーターの数の`ICorDebugTypeEnum`はいずれかに、関数が受け取る引数の数を超えています。 含まれる最初の型パラメーター、`ICorDebugTypeEnum`関数の戻り値の型であり、その後の型パラメーターは関数のパラメーターです。  
  
-   ELEMENT_TYPE_ARRAY、インポートする場合、ELEMENT_TYPE_BYREF、または ELEMENT_TYPE_PTR: 1 つの型パラメーターが返されます。 たとえば、次の型は、配列型など`int32[]`、`EnumerateTypeParameters`が返されます、`ICorDebugTypeEnum`を表すオブジェクトを格納している`int32`です。  
  
## <a name="requirements"></a>必要条件  
 **プラットフォーム:**を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。  
  
 **ヘッダー:** CorDebug.idl、CorDebug.h  
  
 **ライブラリ:** CorGuids.lib  
  
 **.NET framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
