---
title: ICLRMetaHostPolicy インターフェイス
ms.date: 03/30/2017
api_name:
- ICLRMetaHostPolicy
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHostPolicy
helpviewer_keywords:
- ICLRMetaHostPolicy interface [.NET Framework hosting]
ms.assetid: 1bdeccb6-0698-4c97-ad69-eae2b69e59f1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 46576552db6e3c9aa06646b260e74cb4b7890d9d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54559230"
---
# <a name="iclrmetahostpolicy-interface"></a>ICLRMetaHostPolicy インターフェイス
提供、 [GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md)メソッドで、ポリシーの条件に基づいて、共通言語ランタイム (CLR) インターフェイスへのポインターを返します、アセンブリ、バージョン、および構成ファイルを管理します。  
  
## <a name="methods"></a>メソッド  
  
|メソッド|説明|  
|------------|-----------------|  
|[GetRequestedRuntime メソッド](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md)|推奨される CLR インターフェイスがポリシーの条件に基づいて、アセンブリ、バージョン、および構成ファイルの管理を提供します。|  
  
## <a name="remarks"></a>Remarks  
 このインターフェイスへの参照を呼び出して取得することができます、 [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md)次のコードに示すように機能します。  
  
```  
ICLRMetaHostPolicy *pMetaHostPolicy = NULL;  
HRESULT hr = CLRCreateInstance(CLSID_CLRMetaHostPolicy,  
                   IID_ICLRMetaHostPolicy, (LPVOID*)&pMetaHostPolicy);  
```  
  
> [!NOTE]
>  このインターフェイスは、実際に読み込むか、CLR が推奨の CLR バージョンがインストールされるか読み込まれている使用可能なバージョンに基づく返しますだけをアクティブ化。  
  
 [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] API をホストしている、ポリシーを統合できるように、特定のニーズを持つホストは意図しない低下を発生させずに基本的な機能を使用する場合があります。 たとえば、メソッドが論理的にも必要ありませんが、特定の CLR にバインド MSCorEE.dll エクスポートの多くされます。 [METAHOST_POLICY_FLAGS](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md)列挙体は、多数のホストに共通するバインディング ポリシーを提供します。  
  
## <a name="requirements"></a>必要条件  
 **プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。  
  
 **ヘッダー:** MetaHost.h  
  
 **ライブラリ:** MSCorEE.dll でリソースとして含まれます  
  
 **.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>関連項目
- [.NET Framework 4 および 4.5 で追加された CLR ホスト インターフェイス](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)
- [ホスト インターフェイス](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [ホスティング](../../../../docs/framework/unmanaged-api/hosting/index.md)
