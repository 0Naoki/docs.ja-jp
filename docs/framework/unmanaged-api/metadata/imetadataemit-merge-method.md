---
title: IMetaDataEmit::Merge メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.Merge
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::Merge
helpviewer_keywords:
- IMetaDataEmit::Merge method [.NET Framework metadata]
- Merge method [.NET Framework metadata]
ms.assetid: 7596220c-f699-4b6c-8ae7-c83220610650
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 899f2ca5ef1b987687f5c065ad3e1965e142d103
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/08/2018
ms.locfileid: "44216107"
---
# <a name="imetadataemitmerge-method"></a>IMetaDataEmit::Merge メソッド
指定されたインポートされたスコープをマージするスコープの一覧に追加します。  
  
## <a name="syntax"></a>構文  
  
```  
HRESULT Merge (   
    [in]  IMetaDataImport  *pImport,   
    [in]  IMapToken        *pHostMapToken,   
    [in]  IUnknown         *pHandler   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pImport`  
 [in]ポインター、 [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)マージするインポートされたスコープを識別するオブジェクト。  
  
 `pIMap`  
 [in]ポインター、 [IMapToken](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md)トークンの再マップを指定するオブジェクト。  
  
 `pHandleer`  
 [in]ポインター、 [IUnknown](/cpp/atl/iunknown)エラーを指定するオブジェクト。  
  
## <a name="remarks"></a>Remarks  
 呼び出す[imetadataemit::mergeend](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-mergeend-method.md)を 1 つのスコープにメタデータの合併をトリガーします。  
  
## <a name="requirements"></a>要件  
 **:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。  
  
 **ヘッダー:** Cor.h  
  
 **ライブラリ:** MSCorEE.dll にリソースとして使用  
  
 **.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>関連項目  
 [IMetaDataEmit インターフェイス](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [IMetaDataEmit2 インターフェイス](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
