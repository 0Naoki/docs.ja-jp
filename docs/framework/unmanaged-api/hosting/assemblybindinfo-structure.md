---
title: AssemblyBindInfo 構造体
ms.date: 03/30/2017
api_name:
- AssemblyBindInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- AssemblyBindInfo
helpviewer_keywords:
- AssemblyBindInfo structure [.NET Framework hosting]
ms.assetid: 6fc01e98-c2e7-49de-ab9f-95937cc89017
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0247f356bfc9f354edc420ea5460da02b17ab116
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54561141"
---
# <a name="assemblybindinfo-structure"></a>AssemblyBindInfo 構造体
参照アセンブリに関する詳細情報を提供します。  
  
## <a name="syntax"></a>構文  
  
```  
typedef struct _AssemblyBindInfo {  
    DWORD       dwAppDomainId;  
    LPCWSTR     lpReferencedIdentity;  
    LPCWSTR     lpPostPolicyIdentity;  
    DWORD       ePolicyLevel;  
} AssemblyBindInfo;  
```  
  
## <a name="members"></a>メンバー  
  
|メンバー|説明|  
|------------|-----------------|  
|`dwAppDomainId`|一意の識別子、`IStream`への呼び出しによって返される[ihostassemblystore::provideassembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md)、参照アセンブリが読み込まれます。|  
|`lpReferencedIdentity`|参照アセンブリの一意の識別子。|  
|`lpPostPolicyIdentity`|バインディング ポリシー値を適用した後、参照先アセンブリの識別子。|  
|`ePolicyLevel`|1 つ、 [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)されるバージョン管理ポリシー、適用するかどう参照されるアセンブリを示す値。|  
  
## <a name="remarks"></a>Remarks  
 ホスト提供の一意識別子`dwAppDomainId`共通言語ランタイム (CLR) にします。 呼び出しの後に`IHostAssemblyStore::ProvideAssembly`、ランタイムでは、識別子を使用して判断を返すかどうかの内容、`IStream`マップされています。 そうである場合、ランタイムは、ストリームを再マップするのではなく、既存のコピーを読み込みます。 ランタイムも識別子を使用してこのルックアップ キーとしてから返されるストリームの呼び出しを[ihostassemblystore::providemodule](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-providemodule-method.md)します。 そのため、識別子は、モジュールの要求とアセンブリの要求で一意である必要があります。  
  
## <a name="requirements"></a>必要条件  
 **プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。  
  
 **ヘッダー:** MSCorEE.idl  
  
 **ライブラリ:** MSCorEE.dll でリソースとして含まれます  
  
 **.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>関連項目
- [ホスト構造体](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
- [ICLRAssemblyIdentityManager インターフェイス](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [ICLRAssemblyReferenceList インターフェイス](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [IHostAssemblyManager インターフェイス](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [IHostAssemblyStore インターフェイス](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
- [ModuleBindInfo 構造体](../../../../docs/framework/unmanaged-api/hosting/modulebindinfo-structure.md)
