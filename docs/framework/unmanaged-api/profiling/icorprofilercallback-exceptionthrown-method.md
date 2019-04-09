---
title: ICorProfilerCallback::ExceptionThrown メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionThrown
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionThrown
helpviewer_keywords:
- ExceptionThrown method [.NET Framework profiling]
- ICorProfilerCallback::ExceptionThrown method [.NET Framework profiling]
ms.assetid: f1a23f3b-ac21-4905-8abf-8ea59f15af53
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e9cdbc2234519c0dba1a5004246492e7609ea2b3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59180493"
---
# <a name="icorprofilercallbackexceptionthrown-method"></a><span data-ttu-id="1a18a-102">ICorProfilerCallback::ExceptionThrown メソッド</span><span class="sxs-lookup"><span data-stu-id="1a18a-102">ICorProfilerCallback::ExceptionThrown Method</span></span>
<span data-ttu-id="1a18a-103">例外がスローされたことをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="1a18a-103">Notifies the profiler that an exception has been thrown.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1a18a-104">例外がマネージ コードに達した場合にのみ、この関数が呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="1a18a-104">This function is called only if the exception reaches managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1a18a-105">構文</span><span class="sxs-lookup"><span data-stu-id="1a18a-105">Syntax</span></span>  
  
```  
HRESULT ExceptionThrown(  
    [in] ObjectID thrownObjectId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1a18a-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1a18a-106">Parameters</span></span>  
 `thrownObjectId`  
 <span data-ttu-id="1a18a-107">[in]スローされる例外の原因となったオブジェクトの ID。</span><span class="sxs-lookup"><span data-stu-id="1a18a-107">[in] The ID of the object that caused the exception to be thrown.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1a18a-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="1a18a-108">Remarks</span></span>  
 <span data-ttu-id="1a18a-109">プロファイラーでは、スタックはガベージ コレクションを許可する状態にできない可能性がありますので、このメソッドの実装でブロックしないでくださいし、そのため、プリエンプティブなガベージ コレクションを有効にできません。</span><span class="sxs-lookup"><span data-stu-id="1a18a-109">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="1a18a-110">ここで、プロファイラーをブロックする場合とは、ガベージ コレクションが試行されると、ランタイムがこのコールバックが戻るまでブロックされます。</span><span class="sxs-lookup"><span data-stu-id="1a18a-110">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="1a18a-111">このメソッドのプロファイラーの実装には、任意の方法で管理されているメモリの割り当てが発生またはマネージ コードを呼び出さないでください。</span><span class="sxs-lookup"><span data-stu-id="1a18a-111">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1a18a-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="1a18a-112">Requirements</span></span>  
 <span data-ttu-id="1a18a-113">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1a18a-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1a18a-114">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1a18a-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1a18a-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1a18a-115">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="1a18a-116">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="1a18a-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="1a18a-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="1a18a-117">See also</span></span>

- [<span data-ttu-id="1a18a-118">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1a18a-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
