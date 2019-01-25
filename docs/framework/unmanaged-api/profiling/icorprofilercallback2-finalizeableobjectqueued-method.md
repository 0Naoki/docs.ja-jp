---
title: ICorProfilerCallback2::FinalizeableObjectQueued メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback2.FinalizeableObjectQueued
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback2::FinalizeableObjectQueued
helpviewer_keywords:
- FinalizeableObjectQueued method [.NET Framework profiling]
- ICorProfilerCallback2::FinalizeableObjectQueued method [.NET Framework profiling]
ms.assetid: 92d76893-683c-475d-9996-5bff03cdb10f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9b8a952bb2827d1946787f15151887fa25b8da52
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54733728"
---
# <a name="icorprofilercallback2finalizeableobjectqueued-method"></a><span data-ttu-id="39bc5-102">ICorProfilerCallback2::FinalizeableObjectQueued メソッド</span><span class="sxs-lookup"><span data-stu-id="39bc5-102">ICorProfilerCallback2::FinalizeableObjectQueued Method</span></span>
<span data-ttu-id="39bc5-103">コード プロファイラーに通知ファイナライザーを持つオブジェクトが、ファイナライザー スレッドを実行するためにキューに登録されましたが、`Finalize`メソッド。</span><span class="sxs-lookup"><span data-stu-id="39bc5-103">Notifies the code profiler that an object with a finalizer has been queued to the finalizer thread for execution of its `Finalize` method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39bc5-104">構文</span><span class="sxs-lookup"><span data-stu-id="39bc5-104">Syntax</span></span>  
  
```  
HRESULT FinalizeableObjectQueued(  
    [in] DWORD finalizerFlags,  
    [in] ObjectID objectID);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="39bc5-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="39bc5-105">Parameters</span></span>  
 `finalizerFlags`  
 <span data-ttu-id="39bc5-106">[in]値、 [COR_PRF_FINALIZER_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-finalizer-flags-enumeration.md)ファイナライザーの側面について説明する列挙体。</span><span class="sxs-lookup"><span data-stu-id="39bc5-106">[in] A value of the [COR_PRF_FINALIZER_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-finalizer-flags-enumeration.md) enumeration that describes aspects of the finalizer.</span></span>  
  
 `objectID`  
 <span data-ttu-id="39bc5-107">[in]キューに登録されているオブジェクトの ID。</span><span class="sxs-lookup"><span data-stu-id="39bc5-107">[in] The ID of the object that has been queued.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="39bc5-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="39bc5-108">Requirements</span></span>  
 <span data-ttu-id="39bc5-109">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="39bc5-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="39bc5-110">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="39bc5-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="39bc5-111">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="39bc5-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="39bc5-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="39bc5-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39bc5-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="39bc5-113">See also</span></span>
- [<span data-ttu-id="39bc5-114">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="39bc5-114">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="39bc5-115">ICorProfilerCallback2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="39bc5-115">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
