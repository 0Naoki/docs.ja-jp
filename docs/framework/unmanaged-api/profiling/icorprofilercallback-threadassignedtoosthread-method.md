---
title: ICorProfilerCallback::ThreadAssignedToOSThread メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ThreadAssignedToOSThread
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ThreadAssignedToOSThread
helpviewer_keywords:
- ThreadAssignedToOSThread method [.NET Framework profiling]
- ICorProfilerCallback::ThreadAssignedToOSThread method [.NET Framework profiling]
ms.assetid: f9671e5a-7b14-4f5b-8404-58136422c8b2
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: eefcd4436a28fdf52cbe55da5d4bb7eea4449463
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59158458"
---
# <a name="icorprofilercallbackthreadassignedtoosthread-method"></a><span data-ttu-id="b1fb8-102">ICorProfilerCallback::ThreadAssignedToOSThread メソッド</span><span class="sxs-lookup"><span data-stu-id="b1fb8-102">ICorProfilerCallback::ThreadAssignedToOSThread Method</span></span>
<span data-ttu-id="b1fb8-103">特定のオペレーティング システム スレッドを使用して、マネージ スレッドが実装されることをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="b1fb8-103">Notifies the profiler that a managed thread is being implemented using a particular operating system thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b1fb8-104">構文</span><span class="sxs-lookup"><span data-stu-id="b1fb8-104">Syntax</span></span>  
  
```  
HRESULT ThreadAssignedToOSThread(  
    [in] ThreadID managedThreadId,  
    [in] DWORD    osThreadId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b1fb8-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b1fb8-105">Parameters</span></span>  
 `managedThreadId`  
 <span data-ttu-id="b1fb8-106">[in]マネージ スレッドの識別子。</span><span class="sxs-lookup"><span data-stu-id="b1fb8-106">[in] The identifier of the managed thread.</span></span>  
  
 `osThreadId`  
 <span data-ttu-id="b1fb8-107">[in]オペレーティング システム スレッドの識別子。</span><span class="sxs-lookup"><span data-stu-id="b1fb8-107">[in] The identifier of the operating system thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b1fb8-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="b1fb8-108">Remarks</span></span>  
 <span data-ttu-id="b1fb8-109">`ThreadAssignedToOSThread`コールバックが存在できるように、プロファイラーはマネージ スレッドをオペレーティング システムのスレッドのファイバー間での正確なマッピングを維持することができます。</span><span class="sxs-lookup"><span data-stu-id="b1fb8-109">The `ThreadAssignedToOSThread` callback exists so that the profiler can maintain an accurate mapping across fibers of operating system threads to managed threads.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b1fb8-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="b1fb8-110">Requirements</span></span>  
 <span data-ttu-id="b1fb8-111">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b1fb8-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b1fb8-112">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b1fb8-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b1fb8-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b1fb8-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b1fb8-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b1fb8-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1fb8-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="b1fb8-115">See also</span></span>

- [<span data-ttu-id="b1fb8-116">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b1fb8-116">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
