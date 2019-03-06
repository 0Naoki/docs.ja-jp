---
title: ICorProfilerCallback::ModuleUnloadStarted メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ModuleUnloadStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ModuleUnloadStarted
helpviewer_keywords:
- ModuleUnloadStarted method [.NET Framework profiling]
- ICorProfilerCallback::ModuleUnloadStarted method [.NET Framework profiling]
ms.assetid: 2debcaab-6005-4245-afdb-4268bb7e74bd
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2ebeaaa88f3c7320f38d33a9c027d5aa76bf9673
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57495872"
---
# <a name="icorprofilercallbackmoduleunloadstarted-method"></a><span data-ttu-id="aab46-102">ICorProfilerCallback::ModuleUnloadStarted メソッド</span><span class="sxs-lookup"><span data-stu-id="aab46-102">ICorProfilerCallback::ModuleUnloadStarted Method</span></span>
<span data-ttu-id="aab46-103">モジュールがアンロードされることをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="aab46-103">Notifies the profiler that a module is being unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aab46-104">構文</span><span class="sxs-lookup"><span data-stu-id="aab46-104">Syntax</span></span>  
  
```  
HRESULT ModuleUnloadStarted(  
    [in] ModuleID moduleId);   
```  
  
## <a name="parameters"></a><span data-ttu-id="aab46-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="aab46-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="aab46-106">[in]アンロードされているモジュールの ID。</span><span class="sxs-lookup"><span data-stu-id="aab46-106">[in] The ID of the module that is being unloaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="aab46-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="aab46-107">Remarks</span></span>  
 <span data-ttu-id="aab46-108">値`moduleId`は後の情報の要求は無効です、`ModuleUnloadStarted`メソッドを返します。-これは、このモジュールに関する情報を取得するプロファイラーの最後のチャンスです。</span><span class="sxs-lookup"><span data-stu-id="aab46-108">The value of `moduleId` is not valid for an information request after the `ModuleUnloadStarted` method returns — this is the profiler's last chance to get information about this module.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aab46-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="aab46-109">Requirements</span></span>  
 <span data-ttu-id="aab46-110">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="aab46-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aab46-111">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="aab46-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="aab46-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="aab46-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="aab46-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aab46-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aab46-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="aab46-114">See also</span></span>
- [<span data-ttu-id="aab46-115">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="aab46-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="aab46-116">ModuleUnloadFinished メソッド</span><span class="sxs-lookup"><span data-stu-id="aab46-116">ModuleUnloadFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleunloadfinished-method.md)
