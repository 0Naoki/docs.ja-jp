---
title: ICorProfilerInfo3::SetFunctionIDMapper2 メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.SetFunctionIDMapper2 Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::SetFunctionIDMapper2
helpviewer_keywords:
- SetFunctionIDMapper2 method [.NET Framework profiling]
- ICorProfilerInfo3::SetFunctionIDMapper2 method [.NET Framework profiling]
ms.assetid: 8cdb1188-952a-4ba8-9f05-bfebc18cdd29
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5c3046b78aeaee2d9a6264cc68fc61d1fe02cbb5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54626512"
---
# <a name="icorprofilerinfo3setfunctionidmapper2-method"></a><span data-ttu-id="40e4a-102">ICorProfilerInfo3::SetFunctionIDMapper2 メソッド</span><span class="sxs-lookup"><span data-stu-id="40e4a-102">ICorProfilerInfo3::SetFunctionIDMapper2 Method</span></span>
<span data-ttu-id="40e4a-103">`FunctionID` 値を代替値に対応付けるために呼び出すプロファイラー実装関数を指定します。代替値は、プロファイラーの関数の開始フックと終了フックに渡されます。</span><span class="sxs-lookup"><span data-stu-id="40e4a-103">Specifies the profiler-implemented function that will be called to map `FunctionID` values to alternative values, which are passed to the profiler's function entry/exit hooks.</span></span> <span data-ttu-id="40e4a-104">このメソッドによって拡張、 [icorprofilerinfo::setfunctionidmapper](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)ランタイム間であいまいさを解消するプロファイラーを使用する、追加のデータのパラメーターを持つメソッド。</span><span class="sxs-lookup"><span data-stu-id="40e4a-104">This method extends the [ICorProfilerInfo::SetFunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md) method with an additional data parameter, which profilers may use to disambiguate among runtimes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40e4a-105">構文</span><span class="sxs-lookup"><span data-stu-id="40e4a-105">Syntax</span></span>  
  
```  
HRESULT SetFunctionIDMapper2(  
       [in] FunctionIDMapper2 *pFunc,  
       [in] void *clientData);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="40e4a-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="40e4a-106">Parameters</span></span>  
 `pFunc`  
 <span data-ttu-id="40e4a-107">[in]ポインターを[FunctionIDMapper2](../../../../docs/framework/unmanaged-api/profiling/functionidmapper2-function.md)実装にマップするときに呼び出される、`FunctionID`値の代替値にします。</span><span class="sxs-lookup"><span data-stu-id="40e4a-107">[in] A pointer to a [FunctionIDMapper2](../../../../docs/framework/unmanaged-api/profiling/functionidmapper2-function.md) implementation that will be called to map the `FunctionID` values to their alternative values.</span></span>  
  
 `clientData`  
 <span data-ttu-id="40e4a-108">[in]渡されるたびにポインター [FunctionIDMapper2](../../../../docs/framework/unmanaged-api/profiling/functionidmapper2-function.md)関数の現在のランタイムによって行われた呼び出しです。</span><span class="sxs-lookup"><span data-stu-id="40e4a-108">[in] A pointer that is passed to every [FunctionIDMapper2](../../../../docs/framework/unmanaged-api/profiling/functionidmapper2-function.md) function call made by the current runtime.</span></span> <span data-ttu-id="40e4a-109">プロファイラーは、ランタイム間の明確に区別する、この情報を使用できます。</span><span class="sxs-lookup"><span data-stu-id="40e4a-109">The profiler can use this information to disambiguate among runtimes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="40e4a-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="40e4a-110">Return Value</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="40e4a-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="40e4a-111">Remarks</span></span>  
 <span data-ttu-id="40e4a-112">FunctionID 値の代替手段は、プロファイラーの関数の開始/終了フックに渡されます ([FunctionEnter3](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md)、 [FunctionLeave3](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md)、および[FunctionTailcall3](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md);または[FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)、 [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)、および[FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)) で指定されている、 [SetEnterLeaveFunctionHooks3](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md)または[SetEnterLeaveFunctionHooks3WithInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="40e4a-112">The alternatives for the FunctionID values will be passed to the profiler's function entry/exit hooks ([FunctionEnter3](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md), [FunctionLeave3](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md), and [FunctionTailcall3](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md); or [FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md), [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md), and [FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)) that are specified by the [SetEnterLeaveFunctionHooks3](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md) or [SetEnterLeaveFunctionHooks3WithInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) method.</span></span>  
  
 <span data-ttu-id="40e4a-113">`FunctionIDMapper2`メソッドを 1 回だけ設定できます。 以外に設定することをお勧め、 [icorprofilercallback::initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md)コールバック。</span><span class="sxs-lookup"><span data-stu-id="40e4a-113">The `FunctionIDMapper2` method can be set only once; we recommend that you set it in the [ICorProfilerCallback::Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="40e4a-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="40e4a-114">Requirements</span></span>  
 <span data-ttu-id="40e4a-115">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="40e4a-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="40e4a-116">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="40e4a-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="40e4a-117">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="40e4a-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="40e4a-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="40e4a-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40e4a-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="40e4a-119">See also</span></span>
- [<span data-ttu-id="40e4a-120">SetFunctionIDMapper</span><span class="sxs-lookup"><span data-stu-id="40e4a-120">SetFunctionIDMapper</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)
- [<span data-ttu-id="40e4a-121">ICorProfilerInfo3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="40e4a-121">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [<span data-ttu-id="40e4a-122">プロファイリングのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="40e4a-122">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="40e4a-123">プロファイル</span><span class="sxs-lookup"><span data-stu-id="40e4a-123">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
