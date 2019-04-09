---
title: ICorProfilerCallback::ClassUnloadStarted メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ClassUnloadStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ClassUnloadStarted
helpviewer_keywords:
- ClassUnloadStarted method [.NET Framework profiling]
- ICorProfilerCallback::ClassUnloadStarted method [.NET Framework profiling]
ms.assetid: bc93bead-f3a9-415c-b919-ddd3ca80facc
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f0707351d28ef75083b7bfb6ded38bc2a8460131
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59136215"
---
# <a name="icorprofilercallbackclassunloadstarted-method"></a><span data-ttu-id="37bbc-102">ICorProfilerCallback::ClassUnloadStarted メソッド</span><span class="sxs-lookup"><span data-stu-id="37bbc-102">ICorProfilerCallback::ClassUnloadStarted Method</span></span>
<span data-ttu-id="37bbc-103">クラスがアンロードされることをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="37bbc-103">Notifies the profiler that a class is being unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="37bbc-104">構文</span><span class="sxs-lookup"><span data-stu-id="37bbc-104">Syntax</span></span>  
  
```  
HRESULT ClassUnloadStarted(  
    [in] ClassID classId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="37bbc-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="37bbc-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="37bbc-106">[in]アンロードされているクラスを識別します。</span><span class="sxs-lookup"><span data-stu-id="37bbc-106">[in] Identifies the class that is being unloaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="37bbc-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="37bbc-107">Remarks</span></span>  
 <span data-ttu-id="37bbc-108">値`classId`は後の情報の要求は無効です、`ClassUnloadStarted`メソッドを返します。-これは、プロファイラーの最後のチャンスをこのクラスについての情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="37bbc-108">The value of `classId` is not valid for an information request after the `ClassUnloadStarted` method returns — this is the profiler's last chance to obtain information about this class.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="37bbc-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="37bbc-109">Requirements</span></span>  
 <span data-ttu-id="37bbc-110">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="37bbc-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="37bbc-111">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="37bbc-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="37bbc-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="37bbc-112">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="37bbc-113">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="37bbc-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="37bbc-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="37bbc-114">See also</span></span>

- [<span data-ttu-id="37bbc-115">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="37bbc-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="37bbc-116">ClassUnloadFinished メソッド</span><span class="sxs-lookup"><span data-stu-id="37bbc-116">ClassUnloadFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classunloadfinished-method.md)
