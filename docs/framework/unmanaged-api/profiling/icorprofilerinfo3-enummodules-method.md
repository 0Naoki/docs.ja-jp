---
title: ICorProfilerInfo3::EnumModules メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.EnumModules Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::EnumModules
helpviewer_keywords:
- ICorProfilerInfo3::EnumModules method [.NET Framework profiling]
- EnumModules method [.NET Framework profiling]
ms.assetid: 1bf00b42-69da-4019-91b3-bf88026e83fb
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 91550d3328acfb5f3bf2ab461fb2d826ee34c580
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54545161"
---
# <a name="icorprofilerinfo3enummodules-method"></a>ICorProfilerInfo3::EnumModules メソッド
アプリケーションに読み込まれるマネージド モジュールのコレクションを順番に反復処理するメソッドを提供する列挙子を返します。  
  
## <a name="syntax"></a>構文  
  
```  
HRESULT EnumModules([out] ICorProfilerModuleEnum** ppEnum);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `ppEnum`  
 [out]ポインター、 [ICorProfilerModuleEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md)インターフェイス。  
  
## <a name="remarks"></a>Remarks  
  
## <a name="requirements"></a>必要条件  
 **プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。  
  
 **ヘッダー:** CorProf.idl、CorProf.h  
  
 **ライブラリ:** CorGuids.lib  
  
 **.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>関連項目
- [ICorProfilerFunctionEnum インターフェイス](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md)
- [ICorProfilerInfo3 インターフェイス](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [プロファイリングのインターフェイス](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [プロファイル](../../../../docs/framework/unmanaged-api/profiling/index.md)
