---
title: ICorProfilerCallback::COMClassicVTableCreated メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.COMClassicVTableCreated
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::COMClassicVTableCreated
helpviewer_keywords:
- COMClassicVTableCreated method [.NET Framework profiling]
- ICorProfilerCallback::COMClassicVTableCreated method [.NET Framework profiling]
ms.assetid: 6e1834ab-c359-498a-b10b-984ae23cdda4
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c23c52108c5c6534f5b8e8b41517ed2129590466
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54574834"
---
# <a name="icorprofilercallbackcomclassicvtablecreated-method"></a><span data-ttu-id="8f364-102">ICorProfilerCallback::COMClassicVTableCreated メソッド</span><span class="sxs-lookup"><span data-stu-id="8f364-102">ICorProfilerCallback::COMClassicVTableCreated Method</span></span>
<span data-ttu-id="8f364-103">指定された IID とクラスの COM 相互運用機能 vtable が作成されたことをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="8f364-103">Notifies the profiler that a COM interop vtable for the specified IID and class has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f364-104">構文</span><span class="sxs-lookup"><span data-stu-id="8f364-104">Syntax</span></span>  
  
```  
HRESULT COMClassicVTableCreated(  
    [in] ClassID wrappedClassId,  
    [in] REFGUID implementedIID,  
    [in] void    *pVTable,  
    [in] ULONG   cSlots);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8f364-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="8f364-105">Parameters</span></span>  
 `wrappedClasId`  
 <span data-ttu-id="8f364-106">[in]Vtable が作成されたクラスの ID。</span><span class="sxs-lookup"><span data-stu-id="8f364-106">[in] The ID of the class for which the vtable has been created.</span></span>  
  
 `implementedIID`  
 <span data-ttu-id="8f364-107">[in]クラスによって実装されるインターフェイスの ID。</span><span class="sxs-lookup"><span data-stu-id="8f364-107">[in] The ID of the interface implemented by the class.</span></span> <span data-ttu-id="8f364-108">インターフェイスが内部のみの場合、この値は NULL にすることがあります。</span><span class="sxs-lookup"><span data-stu-id="8f364-108">This value may be NULL if the interface is internal only.</span></span>  
  
 `pVTable`  
 <span data-ttu-id="8f364-109">[in]Vtable の先頭へのポインター。</span><span class="sxs-lookup"><span data-stu-id="8f364-109">[in] A pointer to the start of the vtable.</span></span>  
  
 `cSlots`  
 <span data-ttu-id="8f364-110">[in]Vtable に含まれるスロットの数。</span><span class="sxs-lookup"><span data-stu-id="8f364-110">[in] The number of slots that are in the vtable.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8f364-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="8f364-111">Remarks</span></span>  
 <span data-ttu-id="8f364-112">プロファイラーでは、スタックはガベージ コレクションを許可する状態にできない可能性がありますので、このメソッドの実装でブロックしないでくださいし、そのため、プリエンプティブなガベージ コレクションを有効にできません。</span><span class="sxs-lookup"><span data-stu-id="8f364-112">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="8f364-113">ここで、プロファイラーをブロックする場合とは、ガベージ コレクションが試行されると、ランタイムがこのコールバックが戻るまでブロックされます。</span><span class="sxs-lookup"><span data-stu-id="8f364-113">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="8f364-114">このメソッドのプロファイラーの実装には、任意の方法で管理されているメモリの割り当てが発生またはマネージ コードを呼び出さないでください。</span><span class="sxs-lookup"><span data-stu-id="8f364-114">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8f364-115">必要条件</span><span class="sxs-lookup"><span data-stu-id="8f364-115">Requirements</span></span>  
 <span data-ttu-id="8f364-116">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8f364-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8f364-117">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8f364-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8f364-118">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8f364-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8f364-119">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8f364-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f364-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="8f364-120">See also</span></span>
- [<span data-ttu-id="8f364-121">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8f364-121">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="8f364-122">COMClassicVTableDestroyed メソッド</span><span class="sxs-lookup"><span data-stu-id="8f364-122">COMClassicVTableDestroyed Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-comclassicvtabledestroyed-method.md)
