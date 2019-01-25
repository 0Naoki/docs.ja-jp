---
title: ECustomDumpFlavor 列挙型
ms.date: 03/30/2017
api_name:
- ECustomDumpFlavor
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ECustomDumpFlavor
helpviewer_keywords:
- ECustomDumpFlavor enumeration [.NET Framework hosting]
ms.assetid: b39b3320-fac7-41f1-9a03-ab6fb0cd89c7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2be9f112d5997ec8a6b126229eb8608eb8dd8520
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54627643"
---
# <a name="ecustomdumpflavor-enumeration"></a>ECustomDumpFlavor 列挙型
エラーを報告するときにカスタム ヒープのサブセットに含める項目のダンプを示す値が含まれています。  
  
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
|`DUMP_FLAVOR_Mini`|カスタム ヒープ ダンプがミニダンプとして起動し、いずれかで指定された追加のデータを含めることを指定します[CustomDumpItem](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md)インスタンスが同じメソッドに渡されます。|  
|`DUMP_FLAVOR_NonHeapCLRState`|カスタム ヒープ ダンプが動的に割り当てられていないすべての実行時の状態データを収集する必要がありますを指定します。|  
  
## <a name="remarks"></a>Remarks  
 型のパラメーター`ECustomDumpFlavor`に渡される、 [iclrerrorreportingmanager::begincustomdump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md)メソッド。  
  
## <a name="requirements"></a>必要条件  
 **プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。  
  
 **ヘッダー:** MSCorEE.h  
  
 **ライブラリ:** MSCorEE.dll  
  
 **.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>関連項目
- [ECustomDumpItemKind 列挙型](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpitemkind-enumeration.md)
- [ICLRErrorReportingManager インターフェイス](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)
- [ホスティングの列挙型](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
