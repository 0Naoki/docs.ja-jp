---
title: "ICorDebugStepper::Step メソッド"
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
- ICorDebugStepper.Step
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::Step
helpviewer_keywords:
- Step method, ICorDebugStepper interface [.NET Framework debugging]
- ICorDebugStepper::Step method [.NET Framework debugging]
ms.assetid: 38c1940b-ada1-40ba-8295-4c0833744e1e
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: f921725d6794f08530a537462208264ced1dc089
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugstepperstep-method"></a>ICorDebugStepper::Step メソッド
Icordebugstepper にその格納スレッドおよび必要に応じて、1 ステップに、スレッド内で呼び出される関数をシングル ステップ実行を続行します。  
  
## <a name="syntax"></a>構文  
  
```  
HRESULT Step (  
    [in] BOOL   bStepIn  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `bStepIn`  
 [in]設定`true`スレッド内で呼び出される関数にステップ インします。 設定`false`をステップ オーバー関数。  
  
## <a name="remarks"></a>コメント  
 共通言語ランタイムがこのステッパのフレームで次のマネージ命令を実行するときに、手順を完了します。 場合`Step`は、ステッパで呼び出されると、マネージ コードのではない、スレッドがマネージ コードの次の命令を実行するとステップが完了します。  
  
## <a name="requirements"></a>必要条件  
 **プラットフォーム:**を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。  
  
 **ヘッダー:** CorDebug.idl、CorDebug.h  
  
 **ライブラリ:** CorGuids.lib  
  
 **.NET framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
