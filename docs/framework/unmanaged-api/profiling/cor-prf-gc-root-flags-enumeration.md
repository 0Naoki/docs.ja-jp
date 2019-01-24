---
title: COR_PRF_GC_ROOT_FLAGS 列挙型
ms.date: 03/30/2017
api_name:
- COR_PRF_GC_ROOT_FLAGS
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_GC_ROOT_FLAGS
helpviewer_keywords:
- COR_PRF_GC_ROOT_FLAGS enumeration [.NET Framework profiling]
ms.assetid: 4611ee6f-0f05-4d84-91e1-e83d5e7dd7e4
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f4ce8fb8d9d941544982c8da852260b8018788a6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54680745"
---
# <a name="corprfgcrootflags-enumeration"></a><span data-ttu-id="1d035-102">COR_PRF_GC_ROOT_FLAGS 列挙型</span><span class="sxs-lookup"><span data-stu-id="1d035-102">COR_PRF_GC_ROOT_FLAGS Enumeration</span></span>
<span data-ttu-id="1d035-103">ガベージ コレクションのルートのプロパティを示します。</span><span class="sxs-lookup"><span data-stu-id="1d035-103">Indicates a property of a garbage collection root.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d035-104">構文</span><span class="sxs-lookup"><span data-stu-id="1d035-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PRF_GC_ROOT_PINNING = 0x1,  
    COR_PRF_GC_ROOT_WEAKREF = 0x2,  
    COR_PRF_GC_ROOT_INTERIOR = 0x4,  
    COR_PRF_GC_ROOT_REFCOUNTED = 0x8,  
} COR_PRF_GC_ROOT_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="1d035-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="1d035-105">Members</span></span>  
  
|<span data-ttu-id="1d035-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="1d035-106">Member</span></span>|<span data-ttu-id="1d035-107">説明</span><span class="sxs-lookup"><span data-stu-id="1d035-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_GC_ROOT_PINNING`|<span data-ttu-id="1d035-108">ルートでは、ガベージ コレクション オブジェクトを移動できないようにします。</span><span class="sxs-lookup"><span data-stu-id="1d035-108">The root prevents a garbage collection from moving the object.</span></span>|  
|`COR_PRF_GC_ROOT_WEAKREF`|<span data-ttu-id="1d035-109">ルートは、ガベージ コレクションを妨げません。</span><span class="sxs-lookup"><span data-stu-id="1d035-109">The root does not prevent garbage collection.</span></span>|  
|`COR_PRF_GC_ROOT_INTERIOR`|<span data-ttu-id="1d035-110">ルートは、オブジェクト自体ではなく、オブジェクトのフィールドを参照します。</span><span class="sxs-lookup"><span data-stu-id="1d035-110">The root refers to a field of the object rather than the object itself.</span></span>|  
|`COR_PRF_GC_ROOT_REFCOUNTED`|<span data-ttu-id="1d035-111">ルートでは、オブジェクトの参照カウントが特定の値の場合、ガベージ コレクションができないようにします。</span><span class="sxs-lookup"><span data-stu-id="1d035-111">The root prevents garbage collection if the reference count of the object is a certain value.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1d035-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="1d035-112">Remarks</span></span>  
 <span data-ttu-id="1d035-113">`COR_PRF_GC_ROOT_FLAGS` 特殊なルートに関する追加情報を提供するビットマスク。</span><span class="sxs-lookup"><span data-stu-id="1d035-113">`COR_PRF_GC_ROOT_FLAGS` is a bitmask that provides additional information about special roots.</span></span> <span data-ttu-id="1d035-114">ただし、すべてのルートは特別です。</span><span class="sxs-lookup"><span data-stu-id="1d035-114">However, not all roots are special.</span></span> <span data-ttu-id="1d035-115">たとえば、一部のルートを内部ポインター、固定、または参照カウントの弱い参照にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="1d035-115">For example, some roots are not weak references, interior pointers, pinned, or reference-counted.</span></span> <span data-ttu-id="1d035-116">このようなルートを伝達するためのフラグはありません。</span><span class="sxs-lookup"><span data-stu-id="1d035-116">For such roots, there are no flags to convey.</span></span> <span data-ttu-id="1d035-117">など、この列挙体を使用するメソッド、そのため、 [icorprofilercallback 2::rootreferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md)メソッドでは、送信 0 すべてフラグを設定するかを示す、フラグ ビットがオフになっています。</span><span class="sxs-lookup"><span data-stu-id="1d035-117">Therefore, methods that use this enumeration, such as the [ICorProfilerCallback2::RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md) method, send 0 for the flags bitmask, indicating that all flags are turned off.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1d035-118">必要条件</span><span class="sxs-lookup"><span data-stu-id="1d035-118">Requirements</span></span>  
 <span data-ttu-id="1d035-119">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1d035-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1d035-120">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1d035-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1d035-121">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1d035-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1d035-122">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1d035-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d035-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="1d035-123">See also</span></span>
- [<span data-ttu-id="1d035-124">列挙型のプロファイリング</span><span class="sxs-lookup"><span data-stu-id="1d035-124">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
