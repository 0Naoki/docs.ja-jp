---
title: "ICorDebugNativeFrame::SetIP メソッド"
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
- ICorDebugNativeFrame.SetIP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::SetIP
helpviewer_keywords:
- ICorDebugNativeFrame::SetIP method [.NET Framework debugging]
- SetIP method, ICorDebugNativeFrame interface [.NET Framework debugging]
ms.assetid: 57784a51-c76d-48f8-9392-584d0e1946d9
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 25b4f42eb6f10ecade468824d9d790a2bce740a1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugnativeframesetip-method"></a>ICorDebugNativeFrame::SetIP メソッド
命令ポインターをネイティブ コードで指定されたオフセット位置に設定します。  
  
## <a name="syntax"></a>構文  
  
```  
HRESULT SetIP (  
    [in] ULONG32 nOffset  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `nOffset`  
 [in]ネイティブ コード内のオフセットの位置。  
  
## <a name="remarks"></a>コメント  
 呼び出す`SetIP`すぐにすべてのフレームと現在のスレッドのチェーンが無効にします。 デバッガーには、呼び出しの後にフレーム情報が必要がある場合`SetIP`、新しいスタック トレースを実行する必要があります。  
  
 [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)に有効な状態でスタック フレームを維持しようとします。 ただし、場合でも、限り、ランタイムは、有効な状態では、フレームは、まだある可能性があります初期化されていないローカル変数などの問題です。 呼び出し元は、実行中のプログラムの一貫性を保証します。  
  
 64 ビット プラットフォームでは、上の命令ポインターを移動できません、`catch`または`finally`ブロックします。 場合`SetIP`が呼び出された 64 ビット プラットフォームで、このような移動をするためには、エラーを示す HRESULT を返します。  
  
## <a name="requirements"></a>必要条件  
 **プラットフォーム:**を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。  
  
 **ヘッダー:** CorDebug.idl、CorDebug.h  
  
 **ライブラリ:** CorGuids.lib  
  
 **.NET framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>参照  
 
