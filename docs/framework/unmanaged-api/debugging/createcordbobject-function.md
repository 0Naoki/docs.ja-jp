---
title: "CreateCordbObject 関数"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CreateCoredbObject
api_location: mscordbi_macx86.dll
api_type: COM
f1_keywords: CreateCordbObject
helpviewer_keywords:
- remote debugging API [Silverlight]
- CreateCordbObject function
- Silverlight, remote debugging
ms.assetid: b259821d-4fa7-464d-85cf-304dfffc8089
topic_type: apiref
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 06e08148e5526d65d82eca52ffe8db66a4e7df6e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2017
---
# <a name="createcordbobject-function"></a>CreateCordbObject 関数
デバッガー インターフェイスを作成します ([ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md))、リモート プロセスでマネージ デバッグ セッションをインスタンス化するための機能を提供します。  
  
## <a name="syntax"></a>構文  
  
```  
HRESULT CordbCreateObject (  
       [in]  int         iDebuggerVersion,   
       [out] IUnknown**  ppCordb  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `iDebuggerVersion`  
 [in] ターゲット プロセスのデバッガー バージョン。 リモート デバッグの場合、このパラメーターは CorDebugVersion_2_0 である必要があります。  
  
 `ppCordb`  
 [out]キャストするオブジェクトへのポインターへのポインター、 [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)インターフェイスし、が返されます。  
  
## <a name="return-value"></a>戻り値  
 S_OK  
 プロセス内の CLR 数が正常に判別され、対応するハンドルとパスの配列が正しく入力されました。  
  
 E_INVALIDARG  
 `ppCordb` が null であるか、または `iDebuggerVersion` が CorDebugVersion_2_0 ではありません。  
  
 E_OUTOFMEMORY  
 `ppCordb` 用に十分なメモリを割り当てることができません。  
  
 E_FAIL (またはその他の E_ リターン コード)  
 その他のエラーが発生しました。  
  
## <a name="remarks"></a>コメント  
 [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)で返されるインターフェイス`ppCordb`はすべてのマネージ デバッグ サービスの最上位レベルのデバッグ インターフェイスです。  
  
## <a name="requirements"></a>要件  
 **プラットフォーム:**を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。  
  
 **ヘッダー:** CoreClrRemoteDebuggingInterfaces.h  
  
 **ライブラリ:** mscordbi_macx86.dll  
  
 **.NET framework のバージョン:** 3.5 SP1
