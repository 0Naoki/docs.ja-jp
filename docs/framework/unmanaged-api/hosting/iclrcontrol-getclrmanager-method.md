---
title: "ICLRControl::GetCLRManager メソッド"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRControl.GetCLRManager
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRControl::GetCLRManager
helpviewer_keywords:
- GetCLRManager method [.NET Framework hosting]
- ICLRControl::GetCLRManager method [.NET Framework hosting]
ms.assetid: 8a11bfa4-cbb0-4082-82b5-f9fba66c93f5
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 197a3818de8d0b17331a9f9ac422ecaabb230a50
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="iclrcontrolgetclrmanager-method"></a>ICLRControl::GetCLRManager メソッド
ホストが共通言語ランタイム (CLR) の構成に使用できる、マネージャーの種類のいずれかのインスタンスへのインターフェイス ポインターを取得します。  
  
## <a name="syntax"></a>構文  
  
```  
HRESULT GetCLRManager (  
    [in]  REFIID  riid,  
    [out] void  **ppObject  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `riid`  
 [in]`IID`のマネージャーの種類を返します。 次`IID`値はサポートされています。  
  
-   IID_ICLRDebugManager: を指定する`ppObject`型である[ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)です。  
  
-   IID_ICLRErrorReportingManager: を指定する`ppObject`型である[ICLRErrorReportingManager](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)です。  
  
-   IID_ICLRGCManager: を指定する`ppObject`型である[ICLRGCManager](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md)です。  
  
-   IID_ICLRHostProtectionManager: を指定する`ppObject`型である[ICLRHostProtectionManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)です。  
  
-   IID_ICLROnEventManager: を指定する`ppObject`型である[ICLROnEventManager](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md)です。  
  
-   IID_ICLRPolicyManager: を指定する`ppObject`型である[ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)です。  
  
-   IID_ICLRTaskManager: speciries を`ppObject`型である[ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)です。  
  
 `ppObject`  
 [out]要求されたマネージャー、または、無効なマネージャーの種類が要求された場合は null にインターフェイス ポインター。  
  
## <a name="return-value"></a>戻り値  
  
|HRESULT|説明|  
|-------------|-----------------|  
|S_OK|メソッドが正常に返されます。|  
|HOST_E_CLRNOTAVAILABLE|CLR が、プロセスに読み込まれていませんまたは CLR は、状態をマネージ コードを実行またはできないの呼び出しは正常に処理します。|  
|HOST_E_TIMEOUT|呼び出しがタイムアウトしました。|  
|HOST_E_NOT_OWNER|呼び出し元は、ロックを所有していません。|  
|HOST_E_ABANDONED|イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。|  
|E_FAIL|不明な致命的なエラーが発生しました。 メソッドには、E_FAIL が返された、後に、CLR はプロセス内で使用可能ではなくなりました。 メソッドのホストに以降の呼び出しでは、HOST_E_CLRNOTAVAILABLE を返します。|  
|E_NOINTERFACE|インターフェイス型はサポートされていません。|  
  
## <a name="requirements"></a>必要条件  
 **プラットフォーム:**を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。  
  
 **ヘッダー:** MSCorEE.h  
  
 **ライブラリ:** MSCorEE.dll にリソースとして含まれています。  
  
 **.NET framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>参照  
 [ICLRControl インターフェイス](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [IHostControl インターフェイス](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
