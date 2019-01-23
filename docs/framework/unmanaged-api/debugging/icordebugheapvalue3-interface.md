---
title: ICorDebugHeapValue3 インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugHeapValue3
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapValue3
helpviewer_keywords:
- ICorDebugHeapValue3 interface [.NET Framework debugging]
ms.assetid: 9c421bb0-e647-4b2d-a986-f3d578cc7f20
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 08a9bc8aa4aa70ad6b01c58abccd145ae43d8a52
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54568294"
---
# <a name="icordebugheapvalue3-interface"></a><span data-ttu-id="7bae8-102">ICorDebugHeapValue3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7bae8-102">ICorDebugHeapValue3 Interface</span></span>
<span data-ttu-id="7bae8-103">オブジェクトのモニター ロック プロパティを公開します。</span><span class="sxs-lookup"><span data-stu-id="7bae8-103">Exposes the monitor lock properties of objects.</span></span> <span data-ttu-id="7bae8-104">このインターフェイスは、ICorDebugHeapValue および ICorDebugHeapValue2 インターフェイスを拡張します。</span><span class="sxs-lookup"><span data-stu-id="7bae8-104">This interface extends the ICorDebugHeapValue and ICorDebugHeapValue2 interfaces.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7bae8-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="7bae8-105">Methods</span></span>  
  
|<span data-ttu-id="7bae8-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="7bae8-106">Method</span></span>|<span data-ttu-id="7bae8-107">説明</span><span class="sxs-lookup"><span data-stu-id="7bae8-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7bae8-108">GetThreadOwningMonitorLock メソッド</span><span class="sxs-lookup"><span data-stu-id="7bae8-108">GetThreadOwningMonitorLock Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue3-getthreadowningmonitorlock-method.md)|<span data-ttu-id="7bae8-109">このオブジェクトのモニター ロックを所有しているマネージ スレッドを返します。</span><span class="sxs-lookup"><span data-stu-id="7bae8-109">Returns the managed thread that owns the monitor lock on this object.</span></span>|  
|[<span data-ttu-id="7bae8-110">GetMonitorEventWaitList メソッド</span><span class="sxs-lookup"><span data-stu-id="7bae8-110">GetMonitorEventWaitList Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue3-getmonitoreventwaitlist-method.md)|<span data-ttu-id="7bae8-111">モニター ロックに関連付けられているイベントをキューに置かれたスレッドの順序付きリストを提供します。</span><span class="sxs-lookup"><span data-stu-id="7bae8-111">Provides an ordered list of threads that are queued on the event that is associated with a monitor lock.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7bae8-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="7bae8-112">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7bae8-113">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="7bae8-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7bae8-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="7bae8-114">Requirements</span></span>  
 <span data-ttu-id="7bae8-115">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7bae8-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7bae8-116">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7bae8-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7bae8-117">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7bae8-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7bae8-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7bae8-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7bae8-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="7bae8-119">See also</span></span>
- [<span data-ttu-id="7bae8-120">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7bae8-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="7bae8-121">デバッグ</span><span class="sxs-lookup"><span data-stu-id="7bae8-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
