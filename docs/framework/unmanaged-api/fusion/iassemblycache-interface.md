---
title: IAssemblyCache インターフェイス
ms.date: 03/30/2017
api_name:
- IAssemblyCache
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyCache
helpviewer_keywords:
- IAssemblyCache interface [.NET Framework fusion]
ms.assetid: 71ea170f-872d-4fc5-81b6-27da1dec9b19
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 157cc9f5f520f376c0c055ab49b116bc7961f421
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54641071"
---
# <a name="iassemblycache-interface"></a>IAssemblyCache インターフェイス
Fusion のテクノロジで使用するためのグローバル アセンブリ キャッシュを表します。  
  
## <a name="methods"></a>メソッド  
  
|メソッド|説明|  
|------------|-----------------|  
|[CreateAssemblyCacheItem メソッド](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-createassemblycacheitem-method.md)|新しいへの参照を取得します。 [IAssemblyCacheItem](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md)します。|  
|[CreateAssemblyScavenger メソッド](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-createassemblyscavenger-method.md)|Fusion のテクノロジでは、内部使用のため予約されています。|  
|[InstallAssembly メソッド](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-installassembly-method.md)|指定したアセンブリをグローバル アセンブリ キャッシュにインストールします。|  
|[QueryAssemblyInfo メソッド](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-queryassemblyinfo-method.md)|指定したアセンブリについて、要求されたデータを取得します。|  
|[UninstallAssembly メソッド](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-uninstallassembly-method.md)|指定したアセンブリをグローバル アセンブリ キャッシュからアンインストールします。|  
  
## <a name="requirements"></a>必要条件  
 **プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。  
  
 **ヘッダー:** Fusion.h  
  
 **.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>関連項目
- [Fusion インターフェイス](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
- [グローバル アセンブリ キャッシュ](../../../../docs/framework/app-domains/gac.md)
