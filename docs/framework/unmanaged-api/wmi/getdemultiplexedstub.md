---
title: GetDemultiplexedStub 関数 (アンマネージ API リファレンス)
description: GetDemultiplexedStub 関数は、クライアントを Windows の管理から非同期呼び出しの受信を支援するために、オブジェクト転送シンクを作成します。
ms.date: 11/06/2017
api_name:
- GetDemultiplexedStub
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetDemultiplexedStub
helpviewer_keywords:
- GetDemultiplexedStub function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4311a77c9159428bf7beacc99d4479acb28b91b6
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/14/2018
ms.locfileid: "45625569"
---
# <a name="getdemultiplexedstub-function"></a>GetDemultiplexedStub 関数
Windows 管理から非同期呼び出しを受信する際にクライアントを支援するオブジェクト転送シンクが作成されます。
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>構文  
  
```  
HRESULT GetDemultiplexedStub (
   [in] IUnknown*    pObject, 
   [in] boolean      isLocal, 
   [out] IUnknown**  ppObject
); 
```  

## <a name="parameters"></a>パラメーター

`pObject`  
[in]クライアントのインプロセス実装へのポインター [IWbemObjectSink](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectsink)します。

`isLocal`  
[in]イベントがローカルかどうかを示すフラグ (`true`)、それ以外の`false`します。

`ppObject`  
[out]Windows の管理から非同期呼び出しの受信をクライアントを支援するためにオブジェクトのフォワーダー シンク。

## <a name="return-value"></a>戻り値

関数が成功した場合、戻り値は`S_OK`(0)。

関数が失敗した場合、戻り値が 0 以外のエラー コードにします。 拡張エラー情報を取得する、 [GetErrorInfo](geterrorinfo.md)関数。
    
## <a name="requirements"></a>要件  
 **:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。  
  
 **ヘッダー:** WMINet_Utils.idl  
  
 **.NET Framework のバージョン:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>関連項目  
[WMI およびパフォーマンス カウンター (アンマネージ API リファレンス)](index.md)
