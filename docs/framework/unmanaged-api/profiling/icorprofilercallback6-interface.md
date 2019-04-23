---
title: ICorProfilerCallback6 インターフェイス
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback6
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.assetid: edc420b7-96d1-4dec-ace0-36d907f644bc
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8fda98c20b42355b9f52595929bbf5b980b5b857
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59077239"
---
# <a name="icorprofilercallback6-interface"></a><span data-ttu-id="5785d-102">ICorProfilerCallback6 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5785d-102">ICorProfilerCallback6 Interface</span></span>
<span data-ttu-id="5785d-103">[.NET Framework 4.5.2 以降のバージョンでのみでサポート]</span><span class="sxs-lookup"><span data-stu-id="5785d-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="5785d-104">サブクラス[ICorProfilerCallback5](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-interface.md)共通言語ランタイムを使用してアセンブリを読み込むことをプロファイラーに通知するコールバック メソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="5785d-104">A subclass of [ICorProfilerCallback5](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-interface.md) that provides a callback method that the common language runtime uses to notify a profiler that an assembly is loading.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5785d-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="5785d-105">Methods</span></span>  
  
|<span data-ttu-id="5785d-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="5785d-106">Method</span></span>|<span data-ttu-id="5785d-107">説明</span><span class="sxs-lookup"><span data-stu-id="5785d-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5785d-108">GetAssemblyReferences メソッド</span><span class="sxs-lookup"><span data-stu-id="5785d-108">GetAssemblyReferences Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md)|<span data-ttu-id="5785d-109">共通言語ランタイムがアセンブリ参照クロージャのウォークを実行するときに、アセンブリがごく初期のローディング状態であることをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="5785d-109">Notifies the profiler that an assembly is in a very early loading stage, when the common language runtime performs an assembly reference closure walk.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5785d-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="5785d-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5785d-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="5785d-111">Requirements</span></span>  
 <span data-ttu-id="5785d-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5785d-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5785d-113">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5785d-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5785d-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5785d-114">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5785d-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="5785d-115">See also</span></span>

- [<span data-ttu-id="5785d-116">プロファイリングのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="5785d-116">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
