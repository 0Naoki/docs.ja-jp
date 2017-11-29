---
title: "ICorDebugAppDomain::GetName メソッド"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugAppDomain.GetName
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugAppDomain::GetName
helpviewer_keywords:
- ICorDebugAppDomain::GetName method [.NET Framework debugging]
- GetName method, ICorDebugAppDomain interface [.NET Framework debugging]
ms.assetid: 02c596d7-00b0-4e2c-856b-5425158fcefd
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 590bfb5d7d8cac8e322bddfe6258ad9bf377dad6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugappdomaingetname-method"></a>ICorDebugAppDomain::GetName メソッド
アプリケーション ドメインの名前を取得します。  
  
## <a name="syntax"></a>構文  
  
```  
HRESULT GetName (  
    [in]  ULONG32           cchName,  
    [out] ULONG32           *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]   
         WCHAR              szName[]  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `cchName`  
 [in] `szName` 配列のサイズ。 この値をクエリ モードでこのメソッドを格納する 0 に設定します。  
  
 `pcchName`  
 [out]名前またはで実際に返される文字数のサイズへのポインター`szName`です。 クエリ モードでこの値により、バッファーのサイズを呼び出し元に名前を割り当てられません。  
  
 `szName`  
 [out]アプリケーション ドメインの名前を格納する配列。  
  
## <a name="remarks"></a>コメント  
 デバッガーは、`GetName`メソッドを 1 回、名前に必要なバッファーのサイズを取得します。 デバッガーはバッファーを割り当てたし、メソッドを呼び出して、再度バッファーが満杯にします。 最初の呼び出しで、名前のサイズを取得すると呼びます*クエリ モード*です。  
  
## <a name="requirements"></a>要件  
 **プラットフォーム:**を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。  
  
 **ヘッダー:** CorDebug.idl、CorDebug.h  
  
 **ライブラリ:** CorGuids.lib  
  
 **.NET framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
