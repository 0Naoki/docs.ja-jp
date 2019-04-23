---
title: ICorDebugILCode2::GetInstrumentedILMap メソッド
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugILCode2.GetInstrumentedILMap
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 7a4e3085-8f95-40ef-a4be-7d6146f47ce2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4197b018ea85402762a8591b40f3503c02af3974
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59222875"
---
# <a name="icordebugilcode2getinstrumentedilmap-method"></a><span data-ttu-id="d4bd2-102">ICorDebugILCode2::GetInstrumentedILMap メソッド</span><span class="sxs-lookup"><span data-stu-id="d4bd2-102">ICorDebugILCode2::GetInstrumentedILMap Method</span></span>
<span data-ttu-id="d4bd2-103">[.NET Framework 4.5.2 以降のバージョンでのみでサポート]</span><span class="sxs-lookup"><span data-stu-id="d4bd2-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="d4bd2-104">このインスタンスについて、プロファイラー インストルメント中間言語 (IL: intermediate language) オフセットから、元のメソッドの IL オフセットまでのマップを返します。</span><span class="sxs-lookup"><span data-stu-id="d4bd2-104">Returns a map from profiler-instrumented intermediate language (IL) offsets to original method IL offsets for this instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4bd2-105">構文</span><span class="sxs-lookup"><span data-stu-id="d4bd2-105">Syntax</span></span>  
  
```cpp
HRESULT GetInstrumentedILMap(  
   [in] ULONG32 cMap,  
   [out] ULONG32 *pcMap,  
   [out, size_is(cMap), length_is(*pcMap)] COR_IL_MAP map[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d4bd2-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d4bd2-106">Parameters</span></span>  
 <span data-ttu-id="d4bd2-107">cMap</span><span class="sxs-lookup"><span data-stu-id="d4bd2-107">cMap</span></span>  
 <span data-ttu-id="d4bd2-108">[入力] `map` 配列の記憶容量。</span><span class="sxs-lookup"><span data-stu-id="d4bd2-108">[in] The storage capacity of the `map` array.</span></span> <span data-ttu-id="d4bd2-109">詳細については、次の「解説」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d4bd2-109">See the Remarks section for more information.</span></span>  
  
 <span data-ttu-id="d4bd2-110">pcMap</span><span class="sxs-lookup"><span data-stu-id="d4bd2-110">pcMap</span></span>  
 <span data-ttu-id="d4bd2-111">[out]マップ配列へ書き込まれた COR_IL_MAP 値の数。</span><span class="sxs-lookup"><span data-stu-id="d4bd2-111">[out] The number of COR_IL_MAP values written to the map array.</span></span>  
  
 <span data-ttu-id="d4bd2-112">map</span><span class="sxs-lookup"><span data-stu-id="d4bd2-112">map</span></span>  
 <span data-ttu-id="d4bd2-113">[out]マッピングでプロファイラー インストルメント IL から元のメソッドの IL に情報を提供する COR_IL_MAP 値の配列。</span><span class="sxs-lookup"><span data-stu-id="d4bd2-113">[out] An array of COR_IL_MAP values that provide information on mappings from profiler-instrumented IL to the IL of the original method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d4bd2-114">Remarks</span><span class="sxs-lookup"><span data-stu-id="d4bd2-114">Remarks</span></span>  
 <span data-ttu-id="d4bd2-115">プロファイラーを呼び出して、マッピングを設定する場合、 [icorprofilerinfo::setilinstrumentedcodemap](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilinstrumentedcodemap-method.md)メソッド、デバッガーはスタックのオフセット IL を計算するときに、マッピングを内部的に使用して、マッピングの取得には、このメソッドを呼び出すことができますトレースと変数の有効期間。</span><span class="sxs-lookup"><span data-stu-id="d4bd2-115">If the profiler sets the mapping by calling the [ICorProfilerInfo::SetILInstrumentedCodeMap](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilinstrumentedcodemap-method.md) method, the debugger can call this method to retrieve the mapping and to use the mapping internally when calculating IL offsets for stack traces and variable lifetimes.</span></span>  
  
 <span data-ttu-id="d4bd2-116">場合`cMap`は 0 と`pcMap`以外**null**、 `pcMap` COR_IL_MAP の使用可能な値の数に設定されています。</span><span class="sxs-lookup"><span data-stu-id="d4bd2-116">If `cMap` is 0 and `pcMap` is non-**null**, `pcMap` is set to the number of available COR_IL_MAP values.</span></span> <span data-ttu-id="d4bd2-117">`cMap` が 0 以外の場合は、`map` アレイの記憶容量を表します。</span><span class="sxs-lookup"><span data-stu-id="d4bd2-117">If `cMap` is non-zero, it represents the storage capacity of the `map` array.</span></span> <span data-ttu-id="d4bd2-118">メソッドが戻るときに`map`の最大値が含まれています`cMap`項目、および`pcMap`に実際に書き込まれた COR_IL_MAP 値の数に設定されている、`map`配列。</span><span class="sxs-lookup"><span data-stu-id="d4bd2-118">When the method returns, `map` contains a maximum of `cMap` items, and `pcMap` is set to the number of COR_IL_MAP values actually written to the `map` array.</span></span>  
  
 <span data-ttu-id="d4bd2-119">IL がインストルメント化されていない、またはプロファイラーによってマッピングが指定されなかった場合、このメソッドは `S_OK` を返し、`pcMap` を 0 に設定します。</span><span class="sxs-lookup"><span data-stu-id="d4bd2-119">If the IL hasn't been instrumented or the mapping wasn't provided by a profiler, this method returns `S_OK` and sets `pcMap` to 0.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d4bd2-120">必要条件</span><span class="sxs-lookup"><span data-stu-id="d4bd2-120">Requirements</span></span>  
 <span data-ttu-id="d4bd2-121">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d4bd2-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d4bd2-122">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d4bd2-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d4bd2-123">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d4bd2-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d4bd2-124">**.NET Framework のバージョン:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d4bd2-124">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4bd2-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="d4bd2-125">See also</span></span>

- [<span data-ttu-id="d4bd2-126">ICorProfilerInfo::SetILInstrumentedCodeMap</span><span class="sxs-lookup"><span data-stu-id="d4bd2-126">ICorProfilerInfo::SetILInstrumentedCodeMap</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilinstrumentedcodemap-method.md)
- [<span data-ttu-id="d4bd2-127">ICorDebugILCode2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d4bd2-127">ICorDebugILCode2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode2-interface.md)
- [<span data-ttu-id="d4bd2-128">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d4bd2-128">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
