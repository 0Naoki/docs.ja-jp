---
title: ICorProfilerCallback9::DynamicMethodUnloaded メソッド
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback9.DynamicMethodUnloaded
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 658f5b7ede2895eaf774b2ef9cf7ca17f6682ac8
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57496795"
---
# <a name="icorprofilercallback9dynamicmethodunloaded-method"></a><span data-ttu-id="3e6a7-102">ICorProfilerCallback9::DynamicMethodUnloaded メソッド</span><span class="sxs-lookup"><span data-stu-id="3e6a7-102">ICorProfilerCallback9::DynamicMethodUnloaded Method</span></span>
<span data-ttu-id="3e6a7-103">[.NET Framework 4.7.2 以降のバージョンでサポートされます]</span><span class="sxs-lookup"><span data-stu-id="3e6a7-103">[Supported in the .NET Framework 4.7.2 and later versions]</span></span>  
  
<span data-ttu-id="3e6a7-104">動的メソッドは、ガベージ コレクションされ、その後アンロードされるたびに、プロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="3e6a7-104">Notifies the profiler whenever a dynamic method is garbage collected and subsequently unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3e6a7-105">構文</span><span class="sxs-lookup"><span data-stu-id="3e6a7-105">Syntax</span></span>  
  
```  
HRESULT DynamicMethodUnloaded(  
     [in]  FunctionID  functionId
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3e6a7-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3e6a7-106">Parameters</span></span>  
<span data-ttu-id="3e6a7-107">[入力] `functionId`</span><span class="sxs-lookup"><span data-stu-id="3e6a7-107">[in] `functionId`</span></span>  
<span data-ttu-id="3e6a7-108">ガベージ コレクションされ、アンロードされているメモリ内の関数の識別子。</span><span class="sxs-lookup"><span data-stu-id="3e6a7-108">The identifier of the in-memory function that has been garbage collected and unloaded.</span></span>   

## <a name="requirements"></a><span data-ttu-id="3e6a7-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="3e6a7-109">Requirements</span></span>  
 <span data-ttu-id="3e6a7-110">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e6a7-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3e6a7-111">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3e6a7-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3e6a7-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3e6a7-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3e6a7-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="3e6a7-113">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e6a7-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="3e6a7-114">See also</span></span>
- [<span data-ttu-id="3e6a7-115">ICorProfilerCallback8.DynamicMethodJITCompilationStarted メソッド</span><span class="sxs-lookup"><span data-stu-id="3e6a7-115">ICorProfilerCallback8.DynamicMethodJITCompilationStarted Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)
- [<span data-ttu-id="3e6a7-116">ICorProfilerCallback8.DynamicMethodJITCompilationFinished メソッド</span><span class="sxs-lookup"><span data-stu-id="3e6a7-116">ICorProfilerCallback8.DynamicMethodJITCompilationFinished Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)
- [<span data-ttu-id="3e6a7-117">ICorProfilerCallback9 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3e6a7-117">ICorProfilerCallback9 Interface</span></span>](icorprofilercallback9-interface.md)
- [<span data-ttu-id="3e6a7-118">COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS</span><span class="sxs-lookup"><span data-stu-id="3e6a7-118">COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS</span></span>](cor-prf-high-monitor-enumeration.md)
