---
title: ICorProfilerInfo3::GetFunctionEnter3Info メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.GetFunctionEnter3Info Method
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::GetFunctionEnter3Info
helpviewer_keywords:
- GetFunctionEnter3Info method [.NET Framework profiling]
- ICorProfilerInfo3::GetFunctionEnter3Info method [.NET Framework profiling]
ms.assetid: 542c7c65-dd56-4651-b76f-5db2465e4a15
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8df3700c6002e7a181d4882c4afd8542c6b6c93a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59164828"
---
# <a name="icorprofilerinfo3getfunctionenter3info-method"></a><span data-ttu-id="c0dcd-102">ICorProfilerInfo3::GetFunctionEnter3Info メソッド</span><span class="sxs-lookup"><span data-stu-id="c0dcd-102">ICorProfilerInfo3::GetFunctionEnter3Info Method</span></span>
<span data-ttu-id="c0dcd-103">によってプロファイラーに報告される関数のスタック フレームおよび引数情報を提供、 [FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)関数。</span><span class="sxs-lookup"><span data-stu-id="c0dcd-103">Provides the stack frame and argument information of the function that is being reported to the profiler by the [FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md) function.</span></span> <span data-ttu-id="c0dcd-104">このメソッドは、`FunctionEnter3WithInfo` コールバック中にのみ呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="c0dcd-104">This method can be called only during the `FunctionEnter3WithInfo` callback.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0dcd-105">構文</span><span class="sxs-lookup"><span data-stu-id="c0dcd-105">Syntax</span></span>  
  
```  
HRESULT GetFunctionEnter3Info(  
            [in]  FunctionID functionId,   
            [in]  COR_PRF_ELT_INFO eltInfo,  
            [out] COR_PRF_FRAME_INFO *pFrameInfo,  
            [in, out] ULONG *pcbArgumentInfo,  
            [out, size_is(*pcbArgumentInfo)]  
                  COR_PRF_FUNCTION_ARGUMENT_INFO *pArgumentInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c0dcd-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c0dcd-106">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="c0dcd-107">[in] 入力される関数の `FunctionID`。</span><span class="sxs-lookup"><span data-stu-id="c0dcd-107">[in] The `FunctionID` of the function that is being entered.</span></span>  
  
 `eltInfo`  
 <span data-ttu-id="c0dcd-108">[in] 特定のスタック フレームに関する情報を表す不透明ハンドル。</span><span class="sxs-lookup"><span data-stu-id="c0dcd-108">[in] An opaque handle that represents information about a given stack frame.</span></span> <span data-ttu-id="c0dcd-109">プロファイラーを提供する必要があります、同じ`eltInfo`によって指定されたもの、 [FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)関数。</span><span class="sxs-lookup"><span data-stu-id="c0dcd-109">The profiler should provide the same `eltInfo` that it was given by the [FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md) function.</span></span>  
  
 `pFrameInfo`  
 <span data-ttu-id="c0dcd-110">[out] 特定のスタック フレームに関するジェネリック情報を表す不透明ハンドル。</span><span class="sxs-lookup"><span data-stu-id="c0dcd-110">[out] An opaque handle that represents generics information about a given stack frame.</span></span> <span data-ttu-id="c0dcd-111">このハンドルは、プロファイラーが `FunctionEnter3WithInfo` メソッドを呼び出した `GetFunctionEnter3Info` コールバック内でのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="c0dcd-111">This handle is valid only during the `FunctionEnter3WithInfo` callback in which the profiler called the `GetFunctionEnter3Info` method.</span></span>  
  
 `pcbArgumentInfo`  
 <span data-ttu-id="c0dcd-112">[入力、出力]合計サイズ (バイト単位) へのポインターの[COR_PRF_FUNCTION_ARGUMENT_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-info-structure.md)構造 (、追加[COR_PRF_FUNCTION_ARGUMENT_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-range-structure.md) によって示される引数範囲内の構造体`pArgumentInfo`).</span><span class="sxs-lookup"><span data-stu-id="c0dcd-112">[in, out] A pointer to the total size, in bytes, of the [COR_PRF_FUNCTION_ARGUMENT_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-info-structure.md) structure (plus any additional [COR_PRF_FUNCTION_ARGUMENT_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-range-structure.md) structures for the argument ranges pointed to by `pArgumentInfo`).</span></span> <span data-ttu-id="c0dcd-113">指定されたサイズの大きさが十分でない場合、ERROR_INSUFFICIENT_BUFFER が戻り、必要なサイズが `pcbArgumentInfo` に格納されます。</span><span class="sxs-lookup"><span data-stu-id="c0dcd-113">If the specified size is not enough, ERROR_INSUFFICIENT_BUFFER is returned and the expected size is stored in `pcbArgumentInfo`.</span></span> <span data-ttu-id="c0dcd-114">`GetFunctionEnter3Info` を呼び出して `*pcbArgumentInfo` の必要な値を取得するには、`*pcbArgumentInfo` を 0 に、`pArgumentInfo` を NULL にそれぞれ設定します。</span><span class="sxs-lookup"><span data-stu-id="c0dcd-114">To call `GetFunctionEnter3Info` just to retrieve the expected value for `*pcbArgumentInfo`, set `*pcbArgumentInfo`=0 and `pArgumentInfo`=NULL.</span></span>  
  
 `pArgumentInfo`  
 <span data-ttu-id="c0dcd-115">[out]ポインターを[COR_PRF_FUNCTION_ARGUMENT_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-info-structure.md)左から右の順序でのメモリ内の関数の引数の場所を記述する構造体。</span><span class="sxs-lookup"><span data-stu-id="c0dcd-115">[out] A pointer to a [COR_PRF_FUNCTION_ARGUMENT_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-info-structure.md) structure that describes the locations of the function's arguments in memory, in left-to-right order.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c0dcd-116">Remarks</span><span class="sxs-lookup"><span data-stu-id="c0dcd-116">Remarks</span></span>  
 <span data-ttu-id="c0dcd-117">プロファイラーは、調べている関数の `COR_PRF_FUNCTION_ARGUMENT_INFO` 構造体に十分な領域を割り当て、`pcbArgumentInfo` パラメーターでサイズを示す必要があります。</span><span class="sxs-lookup"><span data-stu-id="c0dcd-117">The profiler must allocate sufficient space for the `COR_PRF_FUNCTION_ARGUMENT_INFO` structure of the function that is being inspected, and must indicate the size in the `pcbArgumentInfo` parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c0dcd-118">必要条件</span><span class="sxs-lookup"><span data-stu-id="c0dcd-118">Requirements</span></span>  
 <span data-ttu-id="c0dcd-119">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c0dcd-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c0dcd-120">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c0dcd-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c0dcd-121">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c0dcd-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c0dcd-122">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c0dcd-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0dcd-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="c0dcd-123">See also</span></span>

- [<span data-ttu-id="c0dcd-124">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="c0dcd-124">FunctionEnter3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)
- [<span data-ttu-id="c0dcd-125">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="c0dcd-125">FunctionLeave3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)
- [<span data-ttu-id="c0dcd-126">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="c0dcd-126">FunctionTailcall3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)
- [<span data-ttu-id="c0dcd-127">ICorProfilerInfo3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c0dcd-127">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [<span data-ttu-id="c0dcd-128">プロファイリングのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="c0dcd-128">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="c0dcd-129">プロファイル</span><span class="sxs-lookup"><span data-stu-id="c0dcd-129">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
