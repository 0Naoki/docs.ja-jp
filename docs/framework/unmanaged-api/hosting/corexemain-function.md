---
title: "_CorExeMain 関数"
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
- _CorExeMain
api_location:
- mscoree.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- _CorExeMain
helpviewer_keywords:
- _CorExeMain function [.NET Framework hosting]
ms.assetid: 898f76e2-16f4-4a63-b7d9-dad2d3824d8a
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 5f5c0909db10c7bf8e15a7af998b78e0a193a908
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="corexemain-function"></a>_CorExeMain 関数
共通言語ランタイム (CLR) を初期化、実行可能アセンブリの CLR ヘッダーでマネージ エントリ ポイントを検索および実行を開始します。  
  
## <a name="syntax"></a>構文  
  
```  
__int32 STDMETHODCALLTYPE _CorExeMain ();  
```  
  
## <a name="remarks"></a>コメント  
 この関数は、マネージ実行可能アセンブリから作成されたプロセスにローダーによって呼び出されます。 DLL アセンブリ ローダーの呼び出し、 [_CorDllMain](../../../../docs/framework/unmanaged-api/hosting/cordllmain-function.md)関数を使用します。  
  
 オペレーティング システム ローダーでは、イメージ ファイルに指定されたエントリ ポイントに関係なく、このメソッドを呼び出します。  
  
 Windows 98、Windows ME、Windows NT、および Windows 2000 で、`_CorExeMain`関数は、間接的に呼び出される、オペレーティング システム ローダーで fixup を通じてします。 その他のすべてのバージョンの Windows では、オペレーティング システム ローダーによって直接呼び出されます。  
  
 詳細については、「解説」セクションを参照してください、 [_CorValidateImage](../../../../docs/framework/unmanaged-api/hosting/corvalidateimage-function.md)トピックです。  
  
## <a name="requirements"></a>必要条件  
 **プラットフォーム:**を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。  
  
 **ヘッダー:** Cor.h  
  
 **ライブラリ:** MsCorEE.dll にリソースとして含まれています。  
  
 **.NET framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>参照  
 [メタデータ グローバル静的関数](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
