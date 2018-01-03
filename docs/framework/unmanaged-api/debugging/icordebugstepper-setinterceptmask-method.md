---
title: "ICorDebugStepper::SetInterceptMask メソッド"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugStepper.SetInterceptMask
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugStepper::SetInterceptMask
helpviewer_keywords:
- SetInterceptMask method [.NET Framework debugging]
- ICorDebugStepper::SetInterceptMask method [.NET Framework debugging]
ms.assetid: 6245e2ae-5cc2-43ff-8cc1-71953d12113a
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3ef03b63c4af79c01ba9962fcc6f106b3141b576
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugsteppersetinterceptmask-method"></a>ICorDebugStepper::SetInterceptMask メソッド
ステップ インできるコードの型を指定する値を設定します。  
  
## <a name="syntax"></a>構文  
  
```  
HRESULT SetInterceptMask (  
    [in] CorDebugIntercept    mask  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `mask`  
 [in]コードの種類を指定する CorDebugIntercept 列挙型の値の組み合わせ。  
  
## <a name="remarks"></a>コメント  
 インターセプターのビットが設定されている場合のコードをインターセプトし、指定された型が検出されたときに、ステッパが終了します。 ビットがオフの場合は傍受のコードはスキップされます。  
  
 `SetInterceptMask`メソッドには予期しない対話[icordebugstepper::setunmappedstopmask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) (ユーザーの観点から)。 たとえば場合、のみ表示 (は、非内部) クラスの初期化コードの一部のマッピング情報がないし、STOP_NO_MAPPING_INFO が設定されていない (を参照してください、 [icordebugstepper::setunmappedstopmask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md)メソッドおよびCorDebugUnmappedStop 列挙型)、ステッパはステップ オーバーはクラスの初期化します。 既定では、INTERCEPT_NONE 値のみ、`CorDebugIntercept`列挙が使用されます。  
  
## <a name="requirements"></a>必要条件  
 **プラットフォーム:**を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。  
  
 **ヘッダー:** CorDebug.idl、CorDebug.h  
  
 **ライブラリ:** CorGuids.lib  
  
 **.NET framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
