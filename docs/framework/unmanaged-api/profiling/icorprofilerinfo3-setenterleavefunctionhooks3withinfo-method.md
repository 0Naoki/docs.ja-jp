---
title: ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.SetEnterLeaveFunctionHooks3WithInfo Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo
helpviewer_keywords:
- SetEnterLeaveFunctionHooks3WithInfo method [.NET Framework profiling]
- ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo method [.NET Framework profiling]
ms.assetid: ca8ea534-e441-47b8-be85-466410988c0a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: da3e51174d0b11f5cc706b7680048da519e2ed3e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62049493"
---
# <a name="icorprofilerinfo3setenterleavefunctionhooks3withinfo-method"></a><span data-ttu-id="07920-102">ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo メソッド</span><span class="sxs-lookup"><span data-stu-id="07920-102">ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo Method</span></span>
<span data-ttu-id="07920-103">呼び出されるプロファイラー実装関数を指定します、 [FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)、 [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)、および[FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)マネージ関数のフックします。</span><span class="sxs-lookup"><span data-stu-id="07920-103">Specifies the profiler-implemented functions that will be called on the [FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md), [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md), and [FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md) hooks of managed functions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="07920-104">構文</span><span class="sxs-lookup"><span data-stu-id="07920-104">Syntax</span></span>  
  
```  
HRESULT SetEnterLeaveFunctionHooks3WithInfo(  
            [in] FunctionEnter3WithInfo    *pFuncEnter3,  
            [in] FunctionLeave3withInfo    *pFuncLeave3,  
            [in] FunctionTailcall3WithInfo *pFuncTailcall3);  
```  
  
## <a name="parameters"></a><span data-ttu-id="07920-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="07920-105">Parameters</span></span>  
 `pFuncEnter3`  
 <span data-ttu-id="07920-106">[in]として使用する実装へのポインター、`FunctionEnter3WithInfo`コールバック。</span><span class="sxs-lookup"><span data-stu-id="07920-106">[in] A pointer to the implementation to be used as the `FunctionEnter3WithInfo` callback.</span></span>  
  
 `pFuncLeave3`  
 <span data-ttu-id="07920-107">[in]として使用する実装へのポインター、`FunctionLeave3WithInfo`コールバック。</span><span class="sxs-lookup"><span data-stu-id="07920-107">[in] A pointer to the implementation to be used as the `FunctionLeave3WithInfo` callback.</span></span>  
  
 `pFuncTailcall3`  
 <span data-ttu-id="07920-108">[in]として使用する実装へのポインター、`FunctionTailcall3WithInfo`コールバック。</span><span class="sxs-lookup"><span data-stu-id="07920-108">[in] A pointer to the implementation to be used as the `FunctionTailcall3WithInfo` callback.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="07920-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="07920-109">Remarks</span></span>  
 <span data-ttu-id="07920-110">[FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)、 [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)、および[FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)フックがスタック フレームおよび引数の検査を提供します。</span><span class="sxs-lookup"><span data-stu-id="07920-110">The [FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md), [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md), and [FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md) hooks provide stack frame and argument inspection.</span></span> <span data-ttu-id="07920-111">情報にアクセスする、 `COR_PRF_ENABLE_FUNCTION_ARGS`、 `COR_PRF_ENABLE_FUNCTION_RETVAL`、や`COR_PRF_ENABLE_FRAME_INFO`フラグを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="07920-111">To access that information, the `COR_PRF_ENABLE_FUNCTION_ARGS`, `COR_PRF_ENABLE_FUNCTION_RETVAL`, and/or `COR_PRF_ENABLE_FRAME_INFO` flags have to be set.</span></span> <span data-ttu-id="07920-112">プロファイラーは、使用、 [icorprofilerinfo::seteventmask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md)メソッド、イベント フラグを設定し、使用して、`SetEnterLeaveFunctionHooks3WithInfo`この関数の実装を登録するメソッド。</span><span class="sxs-lookup"><span data-stu-id="07920-112">The profiler can use the [ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) method to set the event flags, and then use the `SetEnterLeaveFunctionHooks3WithInfo` method to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="07920-113">時に、1 つだけの一連のコールバックがアクティブなあり、最新のバージョンが優先されます。</span><span class="sxs-lookup"><span data-stu-id="07920-113">Only one set of callbacks may be active at a time, and the newest version takes precedence.</span></span> <span data-ttu-id="07920-114">そのため、プロファイラーは、両方を呼び出す場合[SetEnterLeaveFunctionHooks2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)と`SetEnterLeaveFunctionHooks3WithInfo`、`SetEnterLeaveFunctionHooks3WithInfo`使用されます。</span><span class="sxs-lookup"><span data-stu-id="07920-114">Therefore, if a profiler calls both [SetEnterLeaveFunctionHooks2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md) and `SetEnterLeaveFunctionHooks3WithInfo`, `SetEnterLeaveFunctionHooks3WithInfo` is used.</span></span>  
  
 <span data-ttu-id="07920-115">`SetEnterLeaveFunctionHooks3WithInfo`メソッドは、プロファイラーからのみ呼び出すことが[icorprofilercallback::initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md)コールバック。</span><span class="sxs-lookup"><span data-stu-id="07920-115">The `SetEnterLeaveFunctionHooks3WithInfo` method may be called only from the profiler's [ICorProfilerCallback::Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="07920-116">必要条件</span><span class="sxs-lookup"><span data-stu-id="07920-116">Requirements</span></span>  
 <span data-ttu-id="07920-117">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="07920-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="07920-118">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="07920-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="07920-119">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="07920-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="07920-120">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="07920-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07920-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="07920-121">See also</span></span>

- [<span data-ttu-id="07920-122">SetEnterLeaveFunctionHooks3</span><span class="sxs-lookup"><span data-stu-id="07920-122">SetEnterLeaveFunctionHooks3</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md)
- [<span data-ttu-id="07920-123">FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="07920-123">FunctionEnter3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md)
- [<span data-ttu-id="07920-124">FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="07920-124">FunctionLeave3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md)
- [<span data-ttu-id="07920-125">FunctionTailcall3</span><span class="sxs-lookup"><span data-stu-id="07920-125">FunctionTailcall3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)
- [<span data-ttu-id="07920-126">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="07920-126">FunctionEnter3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)
- [<span data-ttu-id="07920-127">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="07920-127">FunctionLeave3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)
- [<span data-ttu-id="07920-128">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="07920-128">FunctionTailcall3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)
- [<span data-ttu-id="07920-129">グローバル静的関数のプロファイル</span><span class="sxs-lookup"><span data-stu-id="07920-129">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
- [<span data-ttu-id="07920-130">ICorProfilerInfo3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="07920-130">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [<span data-ttu-id="07920-131">プロファイリングのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="07920-131">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="07920-132">プロファイル</span><span class="sxs-lookup"><span data-stu-id="07920-132">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
