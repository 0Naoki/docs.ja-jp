---
title: "GetVersionFromProcess 関数"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- GetVersionFromProcess
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- GetVersionFromProcess
helpviewer_keywords:
- GetVersionFromProcess function [.NET Framework hosting]
ms.assetid: a9f7f824-64a1-408d-8607-91c7f19d21fe
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: db5054ab9b71eb93005fc0315acba82d807487ec
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="getversionfromprocess-function"></a>GetVersionFromProcess 関数
指定されたプロセスのハンドルに関連付けられている共通言語ランタイム (CLR) のバージョン番号を取得します。  
  
 この関数は、[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] では推奨されていません。  
  
## <a name="syntax"></a>構文  
  
```  
HRESULT GetVersionFromProcess (  
    [in]  HANDLE  hProcess,   
    [out] LPWSTR  pVersion,   
    [in]  DWORD   cchBuffer,   
    [out] DWORD  *dwLength  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `hProcess`  
 [in]プロセスへのハンドル。  
  
 `pVersion`  
 [out]メソッドの正常完了時にバージョン番号の文字列を格納するバッファー。  
  
 `cchBuffer`  
 [in]バージョンのバッファーの長さ。  
  
 `pdwLength`  
 [out]バージョン番号の文字列の長さへのポインター。  
  
## <a name="return-value"></a>戻り値  
 このメソッドは、次の値に加え、WinError.h で定義されている標準のコンポーネント オブジェクト モデル (COM) エラー コードを返します。  
  
|リターン コード|説明|  
|-----------------|-----------------|  
|S_OK|メソッドは正常に完了しました。|  
|E_INVALIDARG|`pVersion`null と`cchBuffer`が null でないまたはその逆です。<br /><br /> - または -<br /><br /> `hProcess`プロセスに有効なハンドルではありません。<br /><br /> - または -<br /><br /> CLR が読み込まれていません。|  
|ERROR_INSUFFICIENT_BUFFER|`cchBuffer`null またはバージョン文字列の長さよりも小さいです。|  
|E_NOTIMPL|このメソッドでは、Microsoft Windows 95、Windows 98、または Microsoft Windows Millennium Edition オペレーティング システムで使用できません。|  
  
## <a name="requirements"></a>必要条件  
 **プラットフォーム:**を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。  
  
 **ヘッダー:** MSCorEE.h  
  
 **ライブラリ:** MSCorEE.dll  
  
 **.NET framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>参照  
 [GetRequestedRuntimeInfo 関数](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeinfo-function.md)  
 [GetRequestedRuntimeVersion 関数](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md)  
 [サポートされなくなった CLR ホスト関数](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
