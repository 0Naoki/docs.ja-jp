---
title: ICLRAppDomainResourceMonitor::GetCurrentAllocated メソッド
ms.date: 03/30/2017
api_name:
- ICLRAppDomainResourceMonitor.GetCurrentAllocated
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAppDomainResourceMonitor::GetCurrentAllocated
helpviewer_keywords:
- GetCurrentAllocated method [.NET Framework hosting]
- ICLRAppDomainResourceMonitor::GetCurrentAllocated method [.NET Framework hosting]
ms.assetid: 7bab209c-efd4-44c2-af30-61abab0ae2fc
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 43d3234a6bd579238068dba9b37ff48a758f6ed3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54693787"
---
# <a name="iclrappdomainresourcemonitorgetcurrentallocated-method"></a>ICLRAppDomainResourceMonitor::GetCurrentAllocated メソッド
ガベージ コレクトされているメモリを差し引くことがなく、作成されているため、アプリケーション ドメインによって行われたすべてのメモリ割り当てのバイト単位の合計サイズを取得します。  
  
## <a name="syntax"></a>構文  
  
```  
HRESULT GetCurrentAllocated([in]  DWORD dwAppDomainId,  
                            [out] ULONGLONG* pBytesAllocated);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `dwAppDomainId`  
 [in]要求されたアプリケーション ドメインの ID。  
  
 `pBytesAllocated`  
 [out]すべてのメモリ割り当ての合計サイズへのポインター。  
  
## <a name="return-value"></a>戻り値  
 このメソッドは、次の特定の HRESULT と、メソッドの失敗を示す HRESULT エラーも返します。  
  
|HRESULT|説明|  
|-------------|-----------------|  
|S_OK|メソッドは正常に完了しました。|  
|COR_E_APPDOMAINUNLOADED|アプリケーション ドメインがアンロードされたか、存在しません。|  
  
## <a name="remarks"></a>Remarks  
 このメソッドはアンマネージと同等のマネージ<xref:System.AppDomain.MonitoringTotalAllocatedMemorySize%2A?displayProperty=nameWithType>プロパティ。  
  
## <a name="requirements"></a>必要条件  
 **プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。  
  
 **ヘッダー:** MetaHost.h  
  
 **ライブラリ:** MSCorEE.dll でリソースとして含まれます  
  
 **.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>関連項目
- [ICLRAppDomainResourceMonitor インターフェイス](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md)
- [アプリケーション ドメインのリソース監視](../../../../docs/standard/garbage-collection/app-domain-resource-monitoring.md)
- [ホスト インターフェイス](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [ホスティング](../../../../docs/framework/unmanaged-api/hosting/index.md)
