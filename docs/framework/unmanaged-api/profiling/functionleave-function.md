---
title: FunctionLeave 関数
ms.date: 03/30/2017
api_name:
- FunctionLeave
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionLeave
helpviewer_keywords:
- FunctionLeave function [.NET Framework profiling]
ms.assetid: 18e89f45-e068-426a-be16-9f53a4346860
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b84b4b7ba96d39693abe238427983da086e62b1f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54634845"
---
# <a name="functionleave-function"></a><span data-ttu-id="327f5-102">FunctionLeave 関数</span><span class="sxs-lookup"><span data-stu-id="327f5-102">FunctionLeave Function</span></span>
<span data-ttu-id="327f5-103">関数が呼び出し元に戻ることをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="327f5-103">Notifies the profiler that a function is about to return to the caller.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="327f5-104">`FunctionLeave`関数が、.NET Framework 2.0 で非推奨とされます。</span><span class="sxs-lookup"><span data-stu-id="327f5-104">The `FunctionLeave` function is deprecated in the .NET Framework 2.0.</span></span> <span data-ttu-id="327f5-105">引き続き、動作しますが、パフォーマンスの低下が発生します。</span><span class="sxs-lookup"><span data-stu-id="327f5-105">It will continue to work, but will incur a performance penalty.</span></span> <span data-ttu-id="327f5-106">使用して、 [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)関数を使用します。</span><span class="sxs-lookup"><span data-stu-id="327f5-106">Use the [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md) function instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="327f5-107">構文</span><span class="sxs-lookup"><span data-stu-id="327f5-107">Syntax</span></span>  
  
```  
void __stdcall FunctionLeave (  
    [in] FunctionID funcID  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="327f5-108">パラメーター</span><span class="sxs-lookup"><span data-stu-id="327f5-108">Parameters</span></span>  
 `funcID`  
 <span data-ttu-id="327f5-109">[in]返す関数の識別子。</span><span class="sxs-lookup"><span data-stu-id="327f5-109">[in] The identifier of the function that is returning.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="327f5-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="327f5-110">Remarks</span></span>  
 <span data-ttu-id="327f5-111">`FunctionLeave`関数は、コールバックは、これを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="327f5-111">The `FunctionLeave` function is a callback; you must implement it.</span></span> <span data-ttu-id="327f5-112">実装を使用する必要があります、 `__declspec`(`naked`) ストレージ クラス属性。</span><span class="sxs-lookup"><span data-stu-id="327f5-112">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="327f5-113">実行エンジンは、この関数を呼び出す前に、レジスタを保存できません。</span><span class="sxs-lookup"><span data-stu-id="327f5-113">The execution engine does not save any registers before calling this function.</span></span>  
  
-   <span data-ttu-id="327f5-114">項目で、浮動小数点ユニット (FPU) にあるなど、使用するすべてのレジスタを保存する必要があります。</span><span class="sxs-lookup"><span data-stu-id="327f5-114">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
-   <span data-ttu-id="327f5-115">終了時に、その呼び出し元によってプッシュされたすべてのパラメーターをポップしてスタックを復元する必要があります。</span><span class="sxs-lookup"><span data-stu-id="327f5-115">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="327f5-116">実装`FunctionLeave`ガベージ コレクションは延期されますブロックしないでください。</span><span class="sxs-lookup"><span data-stu-id="327f5-116">The implementation of `FunctionLeave` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="327f5-117">実装は、ガベージ コレクションをしないで、スタックはガベージ コレクションに適した状態ではない可能性が。</span><span class="sxs-lookup"><span data-stu-id="327f5-117">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="327f5-118">ランタイムがまでブロックはガベージ コレクションが試行されると、`FunctionLeave`を返します。</span><span class="sxs-lookup"><span data-stu-id="327f5-118">If a garbage collection is attempted, the runtime will block until `FunctionLeave` returns.</span></span>  
  
 <span data-ttu-id="327f5-119">また、`FunctionLeave`関数を呼び出してはならないようにまたはマネージ コードにマネージ メモリの割り当て。</span><span class="sxs-lookup"><span data-stu-id="327f5-119">Also, the `FunctionLeave` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="327f5-120">必要条件</span><span class="sxs-lookup"><span data-stu-id="327f5-120">Requirements</span></span>  
 <span data-ttu-id="327f5-121">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="327f5-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="327f5-122">**ヘッダー:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="327f5-122">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="327f5-123">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="327f5-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="327f5-124">**.NET framework のバージョン:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="327f5-124">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="327f5-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="327f5-125">See also</span></span>
- [<span data-ttu-id="327f5-126">FunctionEnter2 関数</span><span class="sxs-lookup"><span data-stu-id="327f5-126">FunctionEnter2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)
- [<span data-ttu-id="327f5-127">FunctionLeave2 関数</span><span class="sxs-lookup"><span data-stu-id="327f5-127">FunctionLeave2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)
- [<span data-ttu-id="327f5-128">FunctionTailcall2 関数</span><span class="sxs-lookup"><span data-stu-id="327f5-128">FunctionTailcall2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)
- [<span data-ttu-id="327f5-129">SetEnterLeaveFunctionHooks2 メソッド</span><span class="sxs-lookup"><span data-stu-id="327f5-129">SetEnterLeaveFunctionHooks2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [<span data-ttu-id="327f5-130">グローバル静的関数のプロファイル</span><span class="sxs-lookup"><span data-stu-id="327f5-130">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
