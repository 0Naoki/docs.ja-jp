---
title: CLRRuntimeHost コクラス
ms.date: 03/30/2017
api_name:
- CLRRuntimeHost Coclass
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CLRRuntimeHost
helpviewer_keywords:
- CLRRuntimeHost coclass [.NET Framework hosting]
ms.assetid: 2ac9cbf5-8a2d-4e4f-8831-0dad8ef0a897
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6e40f08a3dae6f17617e97e07a23b9d7eb611083
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54558632"
---
# <a name="clrruntimehost-coclass"></a>CLRRuntimeHost コクラス
ランタイムによってコードが実行を管理するためのインターフェイスを提供します。  
  
## <a name="syntax"></a>構文  
  
```  
coclass CLRRuntimeHost {  
    [default] interface  ICLRRuntimeHost;  
    interface            ICLRValidator;  
};  
```  
  
## <a name="interfaces"></a>インターフェイス  
  
|Interface|説明|  
|---------------|-----------------|  
|[ICLRRuntimeHost インターフェイス](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)|ランタイムによってアプリケーションの実行を制御するためのメソッドを提供します。|  
|[ICLRValidator インターフェイス](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-interface.md)|ポータブル実行可能イメージの検証し、検証エラーの詳細なレポートのメソッドを提供します。|  
  
## <a name="requirements"></a>必要条件  
 **プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。  
  
 **ヘッダー:** MSCorEE.idl  
  
 **ライブラリ:** MSCorEE.dll でリソースとして含まれます  
  
 **.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>関連項目
- [ホスト コクラス](../../../../docs/framework/unmanaged-api/hosting/hosting-coclasses.md)
