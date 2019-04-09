---
title: ICorProfilerCallback::RuntimeSuspendAborted メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RuntimeSuspendAborted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RuntimeSuspendAborted
helpviewer_keywords:
- ICorProfilerCallback::RuntimeSuspendAborted method [.NET Framework profiling]
- RuntimeSuspendAborted method [.NET Framework profiling]
ms.assetid: 5a8a4277-345b-448b-a028-fc8cff9998aa
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e9aaf7325b8e7e65aa98904513cc7efe94e35087
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59180574"
---
# <a name="icorprofilercallbackruntimesuspendaborted-method"></a><span data-ttu-id="92c00-102">ICorProfilerCallback::RuntimeSuspendAborted メソッド</span><span class="sxs-lookup"><span data-stu-id="92c00-102">ICorProfilerCallback::RuntimeSuspendAborted Method</span></span>
<span data-ttu-id="92c00-103">ランタイムで発生しているランタイムの中断が中止されたことをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="92c00-103">Notifies the profiler that the runtime has aborted the runtime suspension that was occurring.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="92c00-104">構文</span><span class="sxs-lookup"><span data-stu-id="92c00-104">Syntax</span></span>  
  
```  
HRESULT RuntimeSuspendAborted();  
```  
  
## <a name="remarks"></a><span data-ttu-id="92c00-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="92c00-105">Remarks</span></span>  
 <span data-ttu-id="92c00-106">2 つのスレッドが同時にランタイムの中断を試行した場合は、ランタイムの中断を中止する場合があります。</span><span class="sxs-lookup"><span data-stu-id="92c00-106">The run-time suspension might be aborted if two threads simultaneously attempt to suspend the runtime.</span></span>  
  
 <span data-ttu-id="92c00-107">いずれか、 [icorprofilercallback::runtimesuspendfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md)コールバックまたは`RuntimeSuspendAborted`1 つのスレッドの次のコールバックが実行され、 [icorprofilercallback::runtimesuspendstarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md)コールバック。</span><span class="sxs-lookup"><span data-stu-id="92c00-107">Either the [ICorProfilerCallback::RuntimeSuspendFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md) callback or the `RuntimeSuspendAborted` callback will occur on a single thread following a [ICorProfilerCallback::RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) callback.</span></span>  
  
 <span data-ttu-id="92c00-108">`RuntimeSuspendAborted`コールバックと同じスレッドで発生することが保証されます、`RuntimeSuspendStarted`コールバック。</span><span class="sxs-lookup"><span data-stu-id="92c00-108">The `RuntimeSuspendAborted` callback is guaranteed to occur on the same thread as the `RuntimeSuspendStarted` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="92c00-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="92c00-109">Requirements</span></span>  
 <span data-ttu-id="92c00-110">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="92c00-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="92c00-111">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="92c00-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="92c00-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="92c00-112">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="92c00-113">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="92c00-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="92c00-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="92c00-114">See also</span></span>

- [<span data-ttu-id="92c00-115">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="92c00-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
