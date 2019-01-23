---
title: ICorProfilerCallback7::ModuleInMemorySymbolsUpdated Method
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback7.ModuleInMemorySymbolsUpdated
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.assetid: f362a896-3247-4894-9727-e48dbbcd2c78
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ae6183f33b784a0ff79d11310b952949cf13bf58
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54556195"
---
# <a name="icorprofilercallback7moduleinmemorysymbolsupdated-method"></a><span data-ttu-id="d85b5-102">ICorProfilerCallback7::ModuleInMemorySymbolsUpdated Method</span><span class="sxs-lookup"><span data-stu-id="d85b5-102">ICorProfilerCallback7::ModuleInMemorySymbolsUpdated Method</span></span>
<span data-ttu-id="d85b5-103">[.NET Framework 4.6.1 以降のバージョンでのみでサポート]</span><span class="sxs-lookup"><span data-stu-id="d85b5-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="d85b5-104">メモリ内のモジュールに関連付けられているシンボルのストリームが更新されるたびに、プロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="d85b5-104">Notifies the profiler whenever the symbol stream associated with an in-memory module is updated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d85b5-105">構文</span><span class="sxs-lookup"><span data-stu-id="d85b5-105">Syntax</span></span>  
  
```  
HRESULT ModuleInMemorySymbolsUpdated(  
     ModuleID moduleId  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d85b5-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d85b5-106">Parameters</span></span>  
 <span data-ttu-id="d85b5-107">[入力] `moduleId`</span><span class="sxs-lookup"><span data-stu-id="d85b5-107">[in] `moduleId`</span></span>  
 <span data-ttu-id="d85b5-108">シンボルのストリームが更新されたメモリ内モジュールの識別子。</span><span class="sxs-lookup"><span data-stu-id="d85b5-108">The identifier of the in-memory module whose symbol stream is updated.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d85b5-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="d85b5-109">Remarks</span></span>  
 <span data-ttu-id="d85b5-110">このコールバックは設定によって制御されます、 [COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md)イベント マスク フラグを呼び出すときに、 [ICorProfilerCallback5::SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="d85b5-110">This callback is controlled by setting the [COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md) event mask flag when calling the [ICorProfilerCallback5::SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d85b5-111">このイベントは、現在のシンボルを暗黙的に作成または使用して変更は発生しません<xref:System.Reflection.Emit>Api。</span><span class="sxs-lookup"><span data-stu-id="d85b5-111">This event is not currently raised for symbols implicitly created or modified via <xref:System.Reflection.Emit> APIs.</span></span>  
  
 <span data-ttu-id="d85b5-112">でもとシンボルで提供される事前、管理対象のオーバー ロードの 1 つの呼び出し<xref:System.Reflection.Assembly.Load*?displayProperty=nameWithType>メソッドを含む、`rawSymbolStore`ランタイム アセンブリのシンボルを指定する引数では実際にシンボリック データをモジュールに関連付けるいない可能性がありますまで後、 [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)コールバックが発生しました。</span><span class="sxs-lookup"><span data-stu-id="d85b5-112">Even when symbols are provided up front in a call to one of the overloads of the managed <xref:System.Reflection.Assembly.Load*?displayProperty=nameWithType> methods that includes a `rawSymbolStore` argument to specify the symbols for the assembly, the runtime may not actually associate the symbolic data with the module until after the [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback has occurred.</span></span> <span data-ttu-id="d85b5-113">このイベントは、このようなモジュールのシンボルを収集する以降の機会を提供します。</span><span class="sxs-lookup"><span data-stu-id="d85b5-113">This event provides a later opportunity to collect symbols for such modules.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d85b5-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="d85b5-114">Requirements</span></span>  
 <span data-ttu-id="d85b5-115">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d85b5-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d85b5-116">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d85b5-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d85b5-117">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d85b5-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d85b5-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d85b5-118">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d85b5-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="d85b5-119">See also</span></span>
- [<span data-ttu-id="d85b5-120">ModuleLoadFinished メソッド</span><span class="sxs-lookup"><span data-stu-id="d85b5-120">ModuleLoadFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)
- [<span data-ttu-id="d85b5-121">SetEventMask2 メソッド</span><span class="sxs-lookup"><span data-stu-id="d85b5-121">SetEventMask2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md)
- [<span data-ttu-id="d85b5-122">ICorProfilerCallback7 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d85b5-122">ICorProfilerCallback7 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback7-interface.md)
