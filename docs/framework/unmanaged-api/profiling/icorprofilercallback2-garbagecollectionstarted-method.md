---
title: "ICorProfilerCallback2::GarbageCollectionStarted メソッド"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback2.GarbageCollectionStarted
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback2::GarbageCollectionStarted
helpviewer_keywords:
- GarbageCollectionStarted method [.NET Framework profiling]
- ICorProfilerCallback2::GarbageCollectionStarted method [.NET Framework profiling]
ms.assetid: 44eef087-f21f-4fe2-b481-f8a0ee022e7d
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3b721b990312f9acda5c9e0208f998793735d2cd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallback2garbagecollectionstarted-method"></a>ICorProfilerCallback2::GarbageCollectionStarted メソッド
ガベージ コレクションが開始されたことをコード プロファイラーに通知します。  
  
## <a name="syntax"></a>構文  
  
```  
HRESULT GarbageCollectionStarted(  
    [in] int cGenerations,  
    [in, size_is(cGenerations), length_is(cGenerations)] BOOL generationCollected[],  
    [in] COR_PRF_GC_REASON reason);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `cGenerations`  
 [in]内のエントリの総数、`generationCollected`配列。  
  
 `generationCollected`  
 [in]ブール型の値の配列`true`このガベージ コレクションによって収集された、それ以外の配列インデックスに対応する生成されている場合`false`です。  
  
 配列のインデックスの値を[COR_PRF_GC_GENERATION](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-enumeration.md)列挙体は、生成されたことを示します。  
  
 `reason`  
 [in]値、 [COR_PRF_GC_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-reason-enumeration.md)をガベージ コレクションの理由を示す列挙体が発生しました。  
  
## <a name="remarks"></a>コメント  
 このガベージ コレクションに関連するすべてのコールバックの間で発生、`GarbageCollectionStarted`コールバックと、対応する[icorprofilercallback 2::garbagecollectionfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md)コールバック。 これらのコールバックは必要があります、同じスレッドでは発生しません。  
  
 プロファイラーの中に元の場所にオブジェクトを検査を安全では、`GarbageCollectionStarted`コールバック。 戻り値の後に、ガベージ コレクターがオブジェクト移動を開始`GarbageCollectionStarted`です。 プロファイラーが無効であることを受信するまでのすべてのオブジェクト Id を検討してください、プロファイラーがこのコールバックから返された後、`ICorProfilerCallback2::GarbageCollectionFinished`コールバック。  
  
## <a name="requirements"></a>必要条件  
 **プラットフォーム:**を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。  
  
 **ヘッダー** : CorProf.idl、CorProf.h  
  
 **ライブラリ:** CorGuids.lib  
  
 **.NET framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>参照  
 [ICorProfilerCallback インターフェイス](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [ICorProfilerCallback2 インターフェイス](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
