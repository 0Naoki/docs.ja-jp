---
title: IGCHost インターフェイス
ms.date: 03/30/2017
api_name:
- IGCHost
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IGCHost
helpviewer_keywords:
- IGCHost interface [.NET Framework hosting]
ms.assetid: 9ad70ffd-6963-4ab2-8c84-3d86c3fb8deb
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 123eda65510263951895f9c7ac4c6b1781bbd5f6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54736688"
---
# <a name="igchost-interface"></a>IGCHost インターフェイス
ガベージ コレクション システムに関する情報を取得するため、ガベージ コレクションの一部の側面を制御するためのメソッドを提供します。  
  
> [!NOTE]
>  以降では、 [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)]、使用することができます、 [igchost 2::setgcstartuplimitsex](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md)ガベージ コレクション セグメントのサイズと、ガベージ コレクション システムのジェネレーション 0 の最大サイズ値に設定するよりも大きいメソッド、`DWORD`はによって課される制限、 [SetGCStartupLimits](../../../../docs/framework/unmanaged-api/hosting/igchost-setgcstartuplimits-method.md)メソッド。  
  
> [!NOTE]
>  インターフェイスは、上級者のみです。 これは不適切に使用されている場合、アプリケーションのパフォーマンスに影響することができます。  
  
## <a name="methods"></a>メソッド  
  
|メソッド|説明|  
|------------|-----------------|  
|[Collect メソッド](../../../../docs/framework/unmanaged-api/hosting/igchost-collect-method.md)|コレクションの現在のガベージ コレクションの状態に関係なく、特定のジェネレーションの実行を強制します。|  
|[GetStats メソッド](../../../../docs/framework/unmanaged-api/hosting/igchost-getstats-method.md)|ガベージ コレクション システムの現在の状態の統計情報を取得します。|  
|[GetThreadStats メソッド](../../../../docs/framework/unmanaged-api/hosting/igchost-getthreadstats-method.md)|ガベージ コレクションのスレッドごとの統計情報を取得します。|  
|[SetGCStartupLimits メソッド](../../../../docs/framework/unmanaged-api/hosting/igchost-setgcstartuplimits-method.md)|ジェネレーション 0 のセグメントのサイズと最大サイズを設定します。|  
|[SetVirtualMemLimit メソッド](../../../../docs/framework/unmanaged-api/hosting/igchost-setvirtualmemlimit-method.md)|ランタイムの仮想メモリの最大サイズを設定します。|  
  
## <a name="requirements"></a>必要条件  
 **プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。  
  
 **ヘッダー:** GCHost.idl、GCHost.h  
  
 **ライブラリ:** MSCorEE.dll でリソースとして含まれます  
  
 **.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>関連項目
- [ホスト インターフェイス](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [CorRuntimeHost コクラス](../../../../docs/framework/unmanaged-api/hosting/corruntimehost-coclass.md)
