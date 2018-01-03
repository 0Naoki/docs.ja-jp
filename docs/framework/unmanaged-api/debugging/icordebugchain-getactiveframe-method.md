---
title: "ICorDebugChain::GetActiveFrame メソッド"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugChain.GetActiveFrame
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugChain::GetActiveFrame
helpviewer_keywords:
- ICorDebugChain::GetActiveFrame method [.NET Framework debugging]
- GetActiveFrame method, ICorDebugChain interface [.NET Framework debugging]
ms.assetid: 36887017-670b-4f21-b406-8fab956f84a3
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7498e031b74bd904b908342b663e4421432e6d95
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugchaingetactiveframe-method"></a>ICorDebugChain::GetActiveFrame メソッド
アクティブなを取得 (つまり、最新) のフレーム チェーンをします。  
  
## <a name="syntax"></a>構文  
  
```  
HRESULT GetActiveFrame (  
    [out] ICorDebugFrame   **ppFrame  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `ppFrame`  
 [out]アクティブなを表す ICorDebugFrame オブジェクトのアドレスへのポインター (つまり、最新) のフレーム チェーンをします。  
  
## <a name="remarks"></a>コメント  
 マネージ スタック フレームが使用できない場合`ppFrame`設定を null にします。  
  
 アクティブなフレームが使用できない場合、呼び出しが成功し、`ppFrame`は null になります。 アクティブなフレームはチェーン CHAIN_ENTER_UNMANAGED、により開始されるのと CHAIN_CLASS_INIT により開始されるいくつかのチェーンを利用できません。 CorDebugChainReason 列挙型を参照してください。  
  
## <a name="requirements"></a>必要条件  
 **プラットフォーム:**を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。  
  
 **ヘッダー:** CorDebug.idl、CorDebug.h  
  
 **ライブラリ:** CorGuids.lib  
  
 **.NET framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
