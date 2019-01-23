---
title: ICLRRuntimeInfo::BindAsLegacyV2Runtime メソッド
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.BindAsLegacyV2Runtime
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::BindAsLegacyV2Runtime
helpviewer_keywords:
- ICLRRuntimeInfo::BindAsLegacyV2Runtime method [.NET Framework hosting]
- BindAsLegacyV2Runtime method [.NET Framework hosting]
ms.assetid: 65fd55ac-4a24-4479-9384-a2e8013bfb2b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6c85888e9d29e7b3ae6ad76d1e534e08a4603ed2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54499026"
---
# <a name="iclrruntimeinfobindaslegacyv2runtime-method"></a>ICLRRuntimeInfo::BindAsLegacyV2Runtime メソッド
すべてレガシ共通言語ランタイム (CLR) バージョン 2 のライセンス認証ポリシーの決定の現在のランタイムをバインドします。  
  
## <a name="syntax"></a>構文  
  
```  
HRESULT BindAsLegacyV2Runtime ();  
```  
  
## <a name="return-value"></a>戻り値  
 このメソッドは、次の特定の Hresult を返します。  
  
|HRESULT|説明|  
|-------------|-----------------|  
|S_OK|バインドが成功したか、このランタイムは、従来の CLR バージョン 2 のアクティブ化ポリシー ランタイムと既にバインドされています。|  
|CLR_E_SHIM_LEGACYRUNTIMEALREADYBOUND|別のランタイムは、従来の CLR バージョン 2 のアクティブ化ポリシーに既にバインドされています。|  
  
## <a name="remarks"></a>Remarks  
 現在のランタイムがすべてレガシ CLR バージョン 2 のライセンス認証ポリシーの決定に既にバインドされている場合 (などを使用して、`useLegacyV2RuntimeActivationPolicy`属性を[ \<startup > 要素](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)構成ファイルで)、このメソッドエラーの結果を返しません代わりに、なりますメソッドがレガシ アクティブ化ポリシーを正常にバインドしたかどうかと同様に、結果は、s_ok を返します。  
  
## <a name="requirements"></a>必要条件  
 **プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。  
  
 **ヘッダー:** MetaHost.h  
  
 **ライブラリ:** MSCorEE.dll でリソースとして含まれます  
  
 **.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>関連項目
- [ICLRRuntimeInfo インターフェイス](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [ホスト インターフェイス](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [ホスティング](../../../../docs/framework/unmanaged-api/hosting/index.md)
- [\<startup> 要素](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)
