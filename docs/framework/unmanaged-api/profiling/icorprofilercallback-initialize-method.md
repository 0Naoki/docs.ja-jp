---
title: ICorProfilerCallback::Initialize メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.Initialize
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::Initialize
helpviewer_keywords:
- Initialize method, ICorProfilerCallback interface [.NET Framework profiling]
- ICorProfilerCallback::Initialize method [.NET Framework profiling]
ms.assetid: dc5fab2a-4b45-4b12-8727-b89c9915f23e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5aa1025d3f24126c6f8b8585e39dda0201fad3d7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54623314"
---
# <a name="icorprofilercallbackinitialize-method"></a>ICorProfilerCallback::Initialize メソッド
新しい共通言語ランタイム (CLR) アプリケーションを起動するたびに、コード プロファイラーを初期化するために呼び出されます。  
  
## <a name="syntax"></a>構文  
  
```  
HRESULT Initialize(  
    [in] IUnknown     *pICorProfilerInfoUnk);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pICorProfilerInfoUnk`  
 [に](/cpp/atl/iunknown)インターフェイスのクエリを実行する必要があります、プロファイラーを[ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)インターフェイス ポインター。  
  
## <a name="remarks"></a>Remarks  
 `Initialize`呼び出しは不変のコールバックを有効にする (または無効化) するだけの機会です。 によってコールバックが有効にすると、`Initialize`を呼び出すと、後で使用すると無効にできません[icorprofilerinfo::seteventmask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md)します。 COR_PRF_MONITOR_IMMUTABLE 値、 [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md)列挙型では、イベントは変更を示します。  
  
## <a name="requirements"></a>必要条件  
 **プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。  
  
 **ヘッダー:** CorProf.idl、CorProf.h  
  
 **ライブラリ:** CorGuids.lib  
  
 **.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>関連項目
- [ICorProfilerCallback インターフェイス](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [Shutdown メソッド](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-shutdown-method.md)
