---
title: ICorProfilerInfo4::EnumThreads メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4.EnumThreads
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::EnumThreads
helpviewer_keywords:
- ICorProfilerInfo4::EnumThreads method [.NET Framework profiling]
- EnumThreads method, ICorProfilerInfo4 interface [.NET Framework profiling]
ms.assetid: bca7a5b4-c207-4894-918c-0733926296dd
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8cfb474eaa0a770c2bb101787d34072e4ed98714
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54501738"
---
# <a name="icorprofilerinfo4enumthreads-method"></a>ICorProfilerInfo4::EnumThreads メソッド
プロファイリングされたプロセスのすべてのマネージ スレッドのコレクションを順番に反復処理するメソッドを提供する列挙子を返します。  
  
## <a name="syntax"></a>構文  
  
```  
HRESULT EnumThreads([out]  
            ICorProfilerThreadEnum** ppEnum);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `ppEnum`  
 [out]ポインター、 [ICorProfilerThreadEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md)インターフェイス。  
  
## <a name="remarks"></a>Remarks  
  
## <a name="requirements"></a>必要条件  
 **プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。  
  
 **ヘッダー:** CorProf.idl、CorProf.h  
  
 **ライブラリ:** CorGuids.lib  
  
 **.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>関連項目
- [ICorProfilerThreadEnum インターフェイス](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md)
- [ICorProfilerInfo4 インターフェイス](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)
- [プロファイリングのインターフェイス](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [プロファイル](../../../../docs/framework/unmanaged-api/profiling/index.md)
