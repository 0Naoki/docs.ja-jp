---
title: "ECustomDumpFlavor 列挙型"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ECustomDumpFlavor
api_location: mscoree.dll
api_type: COM
f1_keywords: ECustomDumpFlavor
helpviewer_keywords: ECustomDumpFlavor enumeration [.NET Framework hosting]
ms.assetid: b39b3320-fac7-41f1-9a03-ab6fb0cd89c7
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2a7317a3a12acef2a16deebab9a1e1b10205ebf6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2017
---
# <a name="ecustomdumpflavor-enumeration"></a>ECustomDumpFlavor 列挙型
エラーを報告するときに、ヒープのカスタムのサブセットに含めるには、どの項目がダンプを示す値を含みます。  
  
## <a name="syntax"></a>構文  
  
```  
typedef enum {  
    DUMP_FLAVOR_Mini            = 1,  
    DUMP_FLAVOR_NonHeapCLRState = 2  
} ECustomDumpFlavor;  
```  
  
## <a name="members"></a>メンバー  
  
|メンバー|説明|  
|------------|-----------------|  
|`DUMP_FLAVOR_Mini`|カスタム ヒープ ダンプする必要があります、ミニダンプとして起動し、いずれかで指定された追加のデータを含めることを示す[CustomDumpItem](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md)インスタンスが同じメソッドに渡されます。|  
|`DUMP_FLAVOR_NonHeapCLRState`|カスタム ヒープ ダンプが動的に割り当てられていないすべての実行時の状態データを収集する必要がありますを指定します。|  
  
## <a name="remarks"></a>コメント  
 型のパラメーター`ECustomDumpFlavor`に渡される、 [iclrerrorreportingmanager::begincustomdump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md)メソッドです。  
  
## <a name="requirements"></a>要件  
 **プラットフォーム:**を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。  
  
 **ヘッダー:** MSCorEE.h  
  
 **ライブラリ:** MSCorEE.dll  
  
 **.NET framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>関連項目  
 [ECustomDumpItemKind 列挙型](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpitemkind-enumeration.md)  
 [ICLRErrorReportingManager インターフェイス](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)  
 [ホスティングの列挙体](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
