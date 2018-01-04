---
title: "IHostThreadPoolManager::GetMaxThreads メソッド"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostThreadPoolManager.GetMaxThreads
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostThreadPoolManager::GetMaxThreads
helpviewer_keywords:
- IHostThreadPoolManager::GetMaxThreads method [.NET Framework hosting]
- GetMaxThreads method, IHostThreadPoolManager interface [.NET Framework hosting]
ms.assetid: db268876-6178-4a81-aca3-318ee7f96001
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 84867f1b5dfdcfd7a50d01c9e51cb0c42da62f0e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="ihostthreadpoolmanagergetmaxthreads-method"></a>IHostThreadPoolManager::GetMaxThreads メソッド
スレッド プールに同時にホストで管理されるスレッドの最大数を取得します。  
  
## <a name="syntax"></a>構文  
  
```  
HRESULT GetMaxThreads (  
    [out] DWORD *pdwMaxWorkerThreads  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pdwMaxWorkerThreads`  
 [out]ホストがスレッド プールで保持するスレッドの最大数へのポインター。  
  
## <a name="return-value"></a>戻り値  
  
|HRESULT|説明|  
|-------------|-----------------|  
|S_OK|`GetMaxThreads`正常に返されます。|  
|HOST_E_CLRNOTAVAILABLE|共通言語ランタイム (CLR (をプロセスに読み込まれていないか、CLR は、状態でマネージ コードまたはプロセスの呼び出しは正しく実行されません。|  
|HOST_E_TIMEOUT|呼び出しがタイムアウトしました。|  
|HOST_E_NOT_OWNER|呼び出し元は、ロックを所有していません。|  
|HOST_E_ABANDONED|イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。|  
|E_FAIL|不明な致命的なエラーが発生しました。 メソッドには、E_FAIL が返される、ときに、CLR は、プロセス内で使用可能ではなくなりました。 メソッドのホストに以降の呼び出しでは、HOST_E_CLRNOTAVAILABLE を返します。|  
|E_NOTIMPL|ホストがの実装を提供していない`GetMaxThreads`です。|  
  
## <a name="remarks"></a>コメント  
 CLR 呼び出し`GetMaxThreads`をスレッド プール内のスレッドの合計数を決定します。 [GetAvailableThreads](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getavailablethreads-method.md)メソッドは現在の作業項目を処理していないスレッドの数を取得します。 戻り値を超える要求はすべて、`pdwMaxWorkerThreads`パラメーターは、スレッドが使用可能になるまでキューに置かれたままです。  
  
 ホストの実装を提供しない場合`GetMaxThreads`E_NOTIMPL の HRESULT 値を返す必要があります。  
  
## <a name="requirements"></a>必要条件  
 **プラットフォーム:**を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。  
  
 **ヘッダー:** MSCorEE.h  
  
 **ライブラリ:** MSCorEE.dll にリソースとして含まれています。  
  
 **.NET framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>参照  
 <xref:System.Threading.ThreadPool.GetMaxThreads%2A>  
 <xref:System.Threading.ThreadPool>  
 [GetMinThreads メソッド](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getminthreads-method.md)  
 [SetMaxThreads メソッド](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setmaxthreads-method.md)  
 [IHostThreadPoolManager インターフェイス](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
