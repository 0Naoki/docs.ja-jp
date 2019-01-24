---
title: ICorProfilerCallback2::HandleDestroyed メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback2.HandleDestroyed
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback2::HandleDestroyed
helpviewer_keywords:
- ICorProfilerCallback2::HandleDestroyed method [.NET Framework profiling]
- HandleDestroyed method [.NET Framework profiling]
ms.assetid: ab4f4bbd-40c7-4667-bfde-60cd73803110
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 57b814f01d7da8d5b3f9e5bda7d0cf517bb870ed
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54592316"
---
# <a name="icorprofilercallback2handledestroyed-method"></a><span data-ttu-id="794d8-102">ICorProfilerCallback2::HandleDestroyed メソッド</span><span class="sxs-lookup"><span data-stu-id="794d8-102">ICorProfilerCallback2::HandleDestroyed Method</span></span>
<span data-ttu-id="794d8-103">ガベージ コレクション ハンドルが破棄されたことをコード プロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="794d8-103">Notifies the code profiler that a garbage collection handle has been destroyed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="794d8-104">構文</span><span class="sxs-lookup"><span data-stu-id="794d8-104">Syntax</span></span>  
  
```  
HRESULT HandleDestroyed(  
    [in] GCHandleID handleId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="794d8-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="794d8-105">Parameters</span></span>  
 `handleId`  
 <span data-ttu-id="794d8-106">[in]ガベージ コレクション ハンドルの ID。</span><span class="sxs-lookup"><span data-stu-id="794d8-106">[in] The ID of the handle for the garbage collection.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="794d8-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="794d8-107">Requirements</span></span>  
 <span data-ttu-id="794d8-108">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="794d8-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="794d8-109">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="794d8-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="794d8-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="794d8-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="794d8-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="794d8-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="794d8-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="794d8-112">See also</span></span>
- [<span data-ttu-id="794d8-113">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="794d8-113">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="794d8-114">ICorProfilerCallback2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="794d8-114">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
