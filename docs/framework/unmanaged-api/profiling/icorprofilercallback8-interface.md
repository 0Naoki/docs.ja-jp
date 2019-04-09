---
title: ICorProfilerCallback8 インターフェイス
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback8
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e536e61a8d812e442e1e54188c99d6a1d4586757
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59125568"
---
# <a name="icorprofilercallback8-interface"></a><span data-ttu-id="ac3d2-102">ICorProfilerCallback8 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ac3d2-102">ICorProfilerCallback8 Interface</span></span>
<span data-ttu-id="ac3d2-103">[.NET Framework 4.7 以降のバージョンでサポートされます]</span><span class="sxs-lookup"><span data-stu-id="ac3d2-103">[Supported in the .NET Framework 4.7 and later versions]</span></span>  

 <span data-ttu-id="ac3d2-104">サブクラス[ICorProfilerCallback7](icorprofilercallback7-interface.md)動的メソッドの JIT コンパイルが開始して完了したことをプロファイラーに通知する、共通言語ランタイムで使用されるコールバック メソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="ac3d2-104">A subclass of [ICorProfilerCallback7](icorprofilercallback7-interface.md) that provides callback methods used by the common language runtime to notify the profiler that JIT compilation of a dynamic method has started and finished.</span></span> 
  
## <a name="methods"></a><span data-ttu-id="ac3d2-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="ac3d2-105">Methods</span></span>  
  
|<span data-ttu-id="ac3d2-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="ac3d2-106">Method</span></span>|<span data-ttu-id="ac3d2-107">説明</span><span class="sxs-lookup"><span data-stu-id="ac3d2-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ac3d2-108">DynamicMethodJITCompilationStarted メソッド</span><span class="sxs-lookup"><span data-stu-id="ac3d2-108">DynamicMethodJITCompilationStarted Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)|<span data-ttu-id="ac3d2-109">動的メソッドの JIT コンパイルが開始されたことをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="ac3d2-109">Notifies the profiler that JIT compilation of a dynamic method has started.</span></span>|  
|[<span data-ttu-id="ac3d2-110">DynamicMethodJITCompilationFinished メソッド</span><span class="sxs-lookup"><span data-stu-id="ac3d2-110">DynamicMethodJITCompilationFinished Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)|<span data-ttu-id="ac3d2-111">動的メソッドの JIT コンパイルが完了したことをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="ac3d2-111">Notifies the profiler that JIT compilation of a dynamic method has finished.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ac3d2-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="ac3d2-112">Requirements</span></span>  
 <span data-ttu-id="ac3d2-113">**プラットフォーム:**[システム要件](../../get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ac3d2-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ac3d2-114">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ac3d2-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
**<span data-ttu-id="ac3d2-115">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="ac3d2-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a><span data-ttu-id="ac3d2-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="ac3d2-116">See also</span></span>

- [<span data-ttu-id="ac3d2-117">プロファイリングのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="ac3d2-117">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="ac3d2-118">ICorProfilerCallback9 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ac3d2-118">ICorProfilerCallback9 Interface</span></span>](icorprofilercallback9-interface.md)
