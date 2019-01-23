---
title: ICorProfilerCallback::JITFunctionPitched メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.JITFunctionPitched
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::JITFunctionPitched
helpviewer_keywords:
- JITFunctionPitched method [.NET Framework profiling]
- ICorProfilerCallback::JITFunctionPitched method [.NET Framework profiling]
ms.assetid: 116085df-7a77-404a-afac-d0557a12b986
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 91bc626e2c75cd7eb2eafad0fc26d343e5b278e0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54530727"
---
# <a name="icorprofilercallbackjitfunctionpitched-method"></a><span data-ttu-id="0bac3-102">ICorProfilerCallback::JITFunctionPitched メソッド</span><span class="sxs-lookup"><span data-stu-id="0bac3-102">ICorProfilerCallback::JITFunctionPitched Method</span></span>
<span data-ttu-id="0bac3-103">プロファイラーに通知を・ イン タイム (JIT) されている関数のコンパイル メモリから削除されました。</span><span class="sxs-lookup"><span data-stu-id="0bac3-103">Notifies the profiler that a function that has been just-in-time (JIT)-compiled has been removed from memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0bac3-104">構文</span><span class="sxs-lookup"><span data-stu-id="0bac3-104">Syntax</span></span>  
  
```  
HRESULT JITFunctionPitched(  
    [in] FunctionID functionId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0bac3-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0bac3-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="0bac3-106">[in]削除された関数の ID。</span><span class="sxs-lookup"><span data-stu-id="0bac3-106">[in] The ID of the function that was removed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0bac3-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="0bac3-107">Remarks</span></span>  
 <span data-ttu-id="0bac3-108">削除された関数が呼び出されると、プロファイラーは、関数が再コンパイルされるときに、新しい JIT コンパイル イベントを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="0bac3-108">If the removed function is called, the profiler will receive new JIT-compilation events when the function is recompiled.</span></span> <span data-ttu-id="0bac3-109">現時点では、共通言語ランタイム (CLR) の JIT コンパイラは削除されません関数をメモリからこのコールバックは現在は使用されませんし、プロファイラーでは受信できません。</span><span class="sxs-lookup"><span data-stu-id="0bac3-109">Currently, the common language runtime (CLR) JIT compiler does not remove functions from memory, so this callback is currently not used and will not be received by the profiler.</span></span>  
  
 <span data-ttu-id="0bac3-110">値`functionId`が、関数が再コンパイルされるまで、無効です。</span><span class="sxs-lookup"><span data-stu-id="0bac3-110">The value of `functionId` is not valid until the function is recompiled.</span></span> <span data-ttu-id="0bac3-111">関数を再コンパイルすると、同じ`functionId`値が使用されます。</span><span class="sxs-lookup"><span data-stu-id="0bac3-111">When the function is recompiled, the same `functionId` value will be used.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0bac3-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="0bac3-112">Requirements</span></span>  
 <span data-ttu-id="0bac3-113">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0bac3-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0bac3-114">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0bac3-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0bac3-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0bac3-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0bac3-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0bac3-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0bac3-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="0bac3-117">See also</span></span>
- [<span data-ttu-id="0bac3-118">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0bac3-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
