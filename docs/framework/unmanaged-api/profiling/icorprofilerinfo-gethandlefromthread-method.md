---
title: ICorProfilerInfo::GetHandleFromThread メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetHandleFromThread
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetHandleFromThread
helpviewer_keywords:
- GetHandleFromThread method [.NET Framework profiling]
- ICorProfilerInfo::GetHandleFromThread method [.NET Framework profiling]
ms.assetid: 36cdc9f5-7579-4cd2-aa36-fc05c741584c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ad9dc185514bfddd15a6110b1b0d80fc99230271
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57472279"
---
# <a name="icorprofilerinfogethandlefromthread-method"></a><span data-ttu-id="b2a40-102">ICorProfilerInfo::GetHandleFromThread メソッド</span><span class="sxs-lookup"><span data-stu-id="b2a40-102">ICorProfilerInfo::GetHandleFromThread Method</span></span>
<span data-ttu-id="b2a40-103">Win32 スレッドのハンドル、スレッドの ID にマップします。</span><span class="sxs-lookup"><span data-stu-id="b2a40-103">Maps the ID of a thread to a Win32 thread handle.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2a40-104">構文</span><span class="sxs-lookup"><span data-stu-id="b2a40-104">Syntax</span></span>  
  
```  
HRESULT GetHandleFromThread(  
    [in]  ThreadID threadId,  
    [out] HANDLE  *phThread);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b2a40-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b2a40-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="b2a40-106">[in]マップされることをスレッド ID です。</span><span class="sxs-lookup"><span data-stu-id="b2a40-106">[in] The thread ID to be mapped.</span></span>  
  
 `phThread`  
 <span data-ttu-id="b2a40-107">[out]Win32 スレッドのハンドルへのポインター。</span><span class="sxs-lookup"><span data-stu-id="b2a40-107">[out] A pointer to a Win32 thread handle.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b2a40-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="b2a40-108">Remarks</span></span>  
 <span data-ttu-id="b2a40-109">プロファイラーは、Win32 を呼び出す必要があります`DuplicateHandle`関数を使用する前に、ハンドル。</span><span class="sxs-lookup"><span data-stu-id="b2a40-109">The profiler must call the Win32 `DuplicateHandle` function on the handle before using it.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b2a40-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="b2a40-110">Requirements</span></span>  
 <span data-ttu-id="b2a40-111">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b2a40-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b2a40-112">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b2a40-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b2a40-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b2a40-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b2a40-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b2a40-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2a40-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="b2a40-115">See also</span></span>
- [<span data-ttu-id="b2a40-116">ICorProfilerInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b2a40-116">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
