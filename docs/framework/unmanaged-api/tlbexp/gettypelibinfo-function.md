---
title: GetTypeLibInfo 関数
ms.date: 03/30/2017
api_name:
- GetTypeLibInfo
api_location:
- TlbRef.dll
api_type:
- DLLExport
f1_keywords:
- GetTypeLibInfo
helpviewer_keywords:
- GetTypeLibInfo function [.NET Framework]
ms.assetid: a1c4d165-9bdc-4ca8-940e-292d4ffcc338
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0ec28c581b8e6e0aff3a2765720b6e9795be931b
ms.sourcegitcommit: ba5c189bf44d44204a3e8838e59ec378a62d82f3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/13/2018
ms.locfileid: "44756056"
---
# <a name="gettypelibinfo-function"></a>GetTypeLibInfo 関数
調べることで指定したタイプ ライブラリに関する情報を返します、 [TLIBATTR](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/ns-oaidl-tagtlibattr)構造体。  
  
## <a name="syntax"></a>構文  
  
```  
HRESULT GetTypeLibInfo(  
    [in]   LPWSTR     szFile,  
    [out]  GUID      *pTypeLibID,  
    [out]  LCID      *pTypeLibLCID,  
    [out]  SYSKIND   *pTypeLibPlatform,  
    [out]  USHORT    *pTypeLibMajorVer,  
    [out]  USHORT    *pTypeLibMinorVer  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `szFile`  
 [in]タイプ ライブラリのファイル名。  
  
 `pTypeLibID`  
 [out]タイプ ライブラリの GUID です。  
  
 `pTypeLibLCID`  
 [out]タイプ ライブラリのローカリゼーション ID。  
  
 `pTypeLibPlatform`  
 [out]A [SYSKIND](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/ne-oaidl-tagsyskind)タイプ ライブラリの対象のオペレーティング システムを識別するフラグ。 一般的な値は SYS_WIN32 および SYS_WIN64 です。  
  
 `pTypeLibMajorVer`  
 [out]タイプ ライブラリのメジャー バージョン番号。 たとえば、バージョン*x.y*、メジャー バージョン番号は*x*します。  
  
 `pTypeLibMinorVer`  
 [out]タイプ ライブラリのマイナー バージョン番号。 たとえば、バージョン*x.y*、マイナー バージョン番号は*y*します。  
  
## <a name="remarks"></a>Remarks  
 `GetTypeLibInfo`関数を呼び出して、 [Tlbexp.exe (タイプ ライブラリ エクスポーター)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md)します。 このツールは、共通言語ランタイム (CLR) アセンブリで型を記述するタイプ ライブラリを生成します。  
  
 任意のパラメーターが null 関数を返します、`HRESULT`の`E_POINTER`します。 返しますそれ以外の場合、`S_OK`します。  
  
## <a name="requirements"></a>要件  
 **:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。  
  
 **ヘッダー:** TlbRef.h  
  
 **ライブラリ:** TlbRef.lib  
  
 **.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>関連項目  
 [Tlbexp ヘルパー関数](../../../../docs/framework/unmanaged-api/tlbexp/index.md)  
 [LoadTypeLibEx 関数](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-loadtypelibex)
