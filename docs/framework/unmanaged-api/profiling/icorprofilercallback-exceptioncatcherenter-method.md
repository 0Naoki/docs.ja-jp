---
title: ICorProfilerCallback::ExceptionCatcherEnter メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionCatcherEnter
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionCatcherEnter
helpviewer_keywords:
- ICorProfilerCallback::ExceptionCatcherEnter method [.NET Framework profiling]
- ExceptionCatcherEnter method [.NET Framework profiling]
ms.assetid: 41462329-a648-46f0-ae6d-728b94c31aa9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: cb31da8b3fb9148bb41cf7216b44e7cbf610eaee
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54671617"
---
# <a name="icorprofilercallbackexceptioncatcherenter-method"></a><span data-ttu-id="2db14-102">ICorProfilerCallback::ExceptionCatcherEnter メソッド</span><span class="sxs-lookup"><span data-stu-id="2db14-102">ICorProfilerCallback::ExceptionCatcherEnter Method</span></span>
<span data-ttu-id="2db14-103">適切な制御が渡されることをプロファイラーに通知`catch`ブロックします。</span><span class="sxs-lookup"><span data-stu-id="2db14-103">Notifies the profiler that control is being passed to the appropriate `catch` block.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2db14-104">構文</span><span class="sxs-lookup"><span data-stu-id="2db14-104">Syntax</span></span>  
  
```  
HRESULT ExceptionCatcherEnter(  
    [in] FunctionID functionId,  
    [in] ObjectID   objectId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2db14-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2db14-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="2db14-106">[in]格納されている関数の識別子、`catch`ブロックします。</span><span class="sxs-lookup"><span data-stu-id="2db14-106">[in] The identifier of the function containing the `catch` block.</span></span>  
  
 `objectId`  
 <span data-ttu-id="2db14-107">[in]処理中の例外の識別子。</span><span class="sxs-lookup"><span data-stu-id="2db14-107">[in] The identifier of the exception being handled.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2db14-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="2db14-108">Remarks</span></span>  
 <span data-ttu-id="2db14-109">`ExceptionCatcherEnter` Catch ポイントが・ イン タイム (JIT) コンパイラでコンパイルされたコードの場合にのみ、メソッドが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="2db14-109">The `ExceptionCatcherEnter` method is called only if the catch point is in code compiled with the just-in-time (JIT) compiler.</span></span> <span data-ttu-id="2db14-110">アンマネージ コードまたはランタイムの内部のコードでキャッチされた例外には、この通知は呼び出しません。</span><span class="sxs-lookup"><span data-stu-id="2db14-110">An exception that is caught in unmanaged code or in the internal code of the runtime will not call this notification.</span></span> <span data-ttu-id="2db14-111">`objectId`ガベージ コレクションからオブジェクトが移動がでしたので、値をもう一度渡す、`ExceptionThrown`通知します。</span><span class="sxs-lookup"><span data-stu-id="2db14-111">The `objectId` value is passed again since a garbage collection could have moved the object since the `ExceptionThrown` notification.</span></span>  
  
 <span data-ttu-id="2db14-112">プロファイラーでは、スタックはガベージ コレクションを許可する状態にできない可能性がありますので、このメソッドの実装でブロックしないでくださいし、そのため、プリエンプティブなガベージ コレクションを有効にできません。</span><span class="sxs-lookup"><span data-stu-id="2db14-112">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="2db14-113">ここで、プロファイラーをブロックする場合とは、ガベージ コレクションが試行されると、ランタイムがこのコールバックが戻るまでブロックされます。</span><span class="sxs-lookup"><span data-stu-id="2db14-113">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="2db14-114">このメソッドのプロファイラーの実装には、任意の方法で管理されているメモリの割り当てが発生またはマネージ コードを呼び出さないでください。</span><span class="sxs-lookup"><span data-stu-id="2db14-114">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2db14-115">必要条件</span><span class="sxs-lookup"><span data-stu-id="2db14-115">Requirements</span></span>  
 <span data-ttu-id="2db14-116">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2db14-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2db14-117">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2db14-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2db14-118">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2db14-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2db14-119">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2db14-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2db14-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="2db14-120">See also</span></span>
- [<span data-ttu-id="2db14-121">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2db14-121">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="2db14-122">ExceptionCatcherLeave メソッド</span><span class="sxs-lookup"><span data-stu-id="2db14-122">ExceptionCatcherLeave Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherleave-method.md)
