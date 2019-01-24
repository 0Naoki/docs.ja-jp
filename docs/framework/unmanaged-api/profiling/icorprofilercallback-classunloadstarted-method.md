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
ms.openlocfilehash: 217e0942e523b533656f4d194d2b3e3ec63c6db7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54683350"
---
# <a name="icorprofilercallbackclassunloadstarted-method"></a><span data-ttu-id="6294e-102">ICorProfilerCallback::ClassUnloadStarted メソッド</span><span class="sxs-lookup"><span data-stu-id="6294e-102">ICorProfilerCallback::ClassUnloadStarted Method</span></span>
<span data-ttu-id="6294e-103">クラスがアンロードされることをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="6294e-103">Notifies the profiler that a class is being unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6294e-104">構文</span><span class="sxs-lookup"><span data-stu-id="6294e-104">Syntax</span></span>  
  
```  
HRESULT ClassUnloadStarted(  
    [in] ClassID classId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6294e-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6294e-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="6294e-106">[in]アンロードされているクラスを識別します。</span><span class="sxs-lookup"><span data-stu-id="6294e-106">[in] Identifies the class that is being unloaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6294e-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="6294e-107">Remarks</span></span>  
 <span data-ttu-id="6294e-108">値`classId`は後の情報の要求は無効です、`ClassUnloadStarted`メソッドを返します。-これは、プロファイラーの最後のチャンスをこのクラスについての情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="6294e-108">The value of `classId` is not valid for an information request after the `ClassUnloadStarted` method returns — this is the profiler's last chance to obtain information about this class.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6294e-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="6294e-109">Requirements</span></span>  
 <span data-ttu-id="6294e-110">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6294e-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6294e-111">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6294e-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="6294e-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6294e-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6294e-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6294e-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6294e-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="6294e-114">See also</span></span>
- [<span data-ttu-id="6294e-115">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6294e-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="6294e-116">ClassUnloadFinished メソッド</span><span class="sxs-lookup"><span data-stu-id="6294e-116">ClassUnloadFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classunloadfinished-method.md)
