---
title: IAssemblyCacheItem インターフェイス
ms.date: 03/30/2017
api_name:
- IAssemblyCacheItem
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyCacheItem
helpviewer_keywords:
- IAssemblyCacheItem interface [.NET Framework fusion]
ms.assetid: ccc9387a-9f44-4f4f-bf8f-0ea6d2afa21b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d89a531ad09e6865bd9c7dad00c1d8c1840fab8f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54662167"
---
# <a name="iassemblycacheitem-interface"></a>IAssemblyCacheItem インターフェイス
グローバル アセンブリ キャッシュ内の 1 つのアセンブリを表します。  
  
## <a name="methods"></a>メソッド  
  
|メソッド|説明|  
|------------|-----------------|  
|[AbortItem メソッド](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-abortitem-method.md)|リリースされる前に、クリーンアップ操作を実行する、グローバル アセンブリ キャッシュにアセンブリを使用します。|  
|[Commit メソッド](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-commit-method.md)|メモリにキャッシュされたアセンブリ参照をコミットします。|  
|[CreateStream メソッド](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-createstream-method.md)|指定した名前と形式を使用するストリームを作成します。|  
  
## <a name="requirements"></a>必要条件  
 **プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。  
  
 **ヘッダー:** Fusion.h  
  
 **.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>関連項目
- [Fusion インターフェイス](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
- [グローバル アセンブリ キャッシュ](../../../../docs/framework/app-domains/gac.md)
- [IAssemblyCache インターフェイス](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md)
