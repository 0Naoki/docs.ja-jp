---
title: ICorProfilerCallback::ModuleLoadStarted メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ModuleLoadStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ModuleLoadStarted
helpviewer_keywords:
- ModuleLoadStarted method [.NET Framework profiling]
- ICorProfilerCallback::ModuleLoadStarted method [.NET Framework profiling]
ms.assetid: 9cd2fe75-408a-400f-a6b1-9979624a2fe2
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e9d6c322d82b34af908065106ef03ccf5ff846e0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33451731"
---
# <a name="icorprofilercallbackmoduleloadstarted-method"></a><span data-ttu-id="3cdeb-102">ICorProfilerCallback::ModuleLoadStarted メソッド</span><span class="sxs-lookup"><span data-stu-id="3cdeb-102">ICorProfilerCallback::ModuleLoadStarted Method</span></span>
<span data-ttu-id="3cdeb-103">モジュールが読み込まれていることをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="3cdeb-103">Notifies the profiler that a module is being loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3cdeb-104">構文</span><span class="sxs-lookup"><span data-stu-id="3cdeb-104">Syntax</span></span>  
  
```  
HRESULT ModuleLoadStarted(  
    [in] ModuleID moduleId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3cdeb-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3cdeb-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="3cdeb-106">[in]読み込まれているモジュールの ID。</span><span class="sxs-lookup"><span data-stu-id="3cdeb-106">[in] The ID of the module that is being loaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3cdeb-107">コメント</span><span class="sxs-lookup"><span data-stu-id="3cdeb-107">Remarks</span></span>  
 <span data-ttu-id="3cdeb-108">値`moduleId`まで情報の要求に対して無効です、 [icorprofilercallback::moduleloadfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)メソッドが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="3cdeb-108">The value of `moduleId` is not valid for an information request until the [ICorProfilerCallback::ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3cdeb-109">要件</span><span class="sxs-lookup"><span data-stu-id="3cdeb-109">Requirements</span></span>  
 <span data-ttu-id="3cdeb-110">**プラットフォーム:** を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。</span><span class="sxs-lookup"><span data-stu-id="3cdeb-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3cdeb-111">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3cdeb-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3cdeb-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3cdeb-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3cdeb-113">**.NET framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3cdeb-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3cdeb-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="3cdeb-114">See Also</span></span>  
 [<span data-ttu-id="3cdeb-115">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3cdeb-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
