---
title: ICorProfilerCallback::ExceptionSearchFilterLeave メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionSearchFilterLeave
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionSearchFilterLeave
helpviewer_keywords:
- ICorProfilerCallback::ExceptionSearchFilterLeave method [.NET Framework profiling]
- ExceptionSearchFilterLeave method [.NET Framework profiling]
ms.assetid: c28a2a82-dd11-4385-843f-b509fb61753b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3fcbd225acd3f4f24311d08b04c971e2550b8ef5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54533573"
---
# <a name="icorprofilercallbackexceptionsearchfilterleave-method"></a><span data-ttu-id="ab545-102">ICorProfilerCallback::ExceptionSearchFilterLeave メソッド</span><span class="sxs-lookup"><span data-stu-id="ab545-102">ICorProfilerCallback::ExceptionSearchFilterLeave Method</span></span>
<span data-ttu-id="ab545-103">ユーザー フィルターがだけ完了したことを実行するプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="ab545-103">Notifies the profiler that a user filter has just finished executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab545-104">構文</span><span class="sxs-lookup"><span data-stu-id="ab545-104">Syntax</span></span>  
  
```  
HRESULT ExceptionSearchFilterLeave();  
```  
  
## <a name="requirements"></a><span data-ttu-id="ab545-105">必要条件</span><span class="sxs-lookup"><span data-stu-id="ab545-105">Requirements</span></span>  
 <span data-ttu-id="ab545-106">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ab545-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ab545-107">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ab545-107">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ab545-108">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ab545-108">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ab545-109">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ab545-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab545-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="ab545-110">See also</span></span>
- [<span data-ttu-id="ab545-111">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ab545-111">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="ab545-112">ExceptionSearchFilterEnter メソッド</span><span class="sxs-lookup"><span data-stu-id="ab545-112">ExceptionSearchFilterEnter Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterenter-method.md)
