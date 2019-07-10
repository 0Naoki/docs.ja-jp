---
title: CorDebugBlockingObject 構造体
ms.date: 03/30/2017
api_name:
- CorDebugBlockingObject Structure
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugBlockingObject
helpviewer_keywords:
- CorDebugBlockingObject structure [.NET Framework debugging]
ms.assetid: 5944edd1-0914-4efa-aba0-d5a277c38b1a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 83dac3b9b2ac396cdef19695fcce0f7e20485a50
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67740396"
---
# <a name="cordebugblockingobject-structure"></a><span data-ttu-id="72614-102">CorDebugBlockingObject 構造体</span><span class="sxs-lookup"><span data-stu-id="72614-102">CorDebugBlockingObject Structure</span></span>
<span data-ttu-id="72614-103">スレッドおよびスレッドがブロックされている特定の理由をブロックしているオブジェクトを定義します。</span><span class="sxs-lookup"><span data-stu-id="72614-103">Defines an object that is blocking a thread and the specific reason that the thread is blocked.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72614-104">構文</span><span class="sxs-lookup"><span data-stu-id="72614-104">Syntax</span></span>  
  
```cpp  
Typedef struct CorDebugBlockingObject  
{  
ICorDebugValue pBlockingObject;  
DWORD dwTimeout;  
CorDebugBlockingReason blockingReason;  
}  CorDebugBlockingObject;  
```  
  
## <a name="members"></a><span data-ttu-id="72614-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="72614-105">Members</span></span>  
  
|<span data-ttu-id="72614-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="72614-106">Member</span></span>|<span data-ttu-id="72614-107">説明</span><span class="sxs-lookup"><span data-stu-id="72614-107">Description</span></span>|  
|------------|-----------------|  
|`pBlockingObject`|<span data-ttu-id="72614-108">スレッドがブロックしているオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="72614-108">The object on which the thread is blocking.</span></span> <span data-ttu-id="72614-109">このオブジェクトは、現在の同期状態の期間に対してのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="72614-109">This object is valid only for the duration of the current synchronized state.</span></span> <span data-ttu-id="72614-110">同じ同期された状態で同じオブジェクトでは、2 つのスレッドがブロックして、期待する場合は可能性があります、 [icordebugvalue::getaddress](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getaddress-method.md)メソッドを同じ値を返します。</span><span class="sxs-lookup"><span data-stu-id="72614-110">If two threads are blocking on the same object within the same synchronized state, you may expect the [ICorDebugValue::GetAddress](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getaddress-method.md) method to return the same value.</span></span> <span data-ttu-id="72614-111">ただし、インターフェイスは、同等のポインターができない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="72614-111">However, the interfaces may or may not be pointer equivalent.</span></span>|  
|`dwTimeout`|<span data-ttu-id="72614-112">ブロック操作までのミリ秒数は、タイムアウト、または、値は INFINITE で、ものではタイムアウトしないことを示します。タイムアウト値には、時間が残っているではなく、ブロック操作の時間の合計の長さを指定します。</span><span class="sxs-lookup"><span data-stu-id="72614-112">The number of milliseconds before the blocking operation will time out, or the value INFINITE, which indicates that it will not time out. The time-out value specifies the total length of time for the blocking operation, not the time that is still remaining.</span></span>|  
|`blockingReason`|<span data-ttu-id="72614-113">このオブジェクトのスレッドがブロックされている理由です。</span><span class="sxs-lookup"><span data-stu-id="72614-113">The reason that the thread is blocked on this object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="72614-114">Remarks</span><span class="sxs-lookup"><span data-stu-id="72614-114">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="72614-115">必要条件</span><span class="sxs-lookup"><span data-stu-id="72614-115">Requirements</span></span>  
 <span data-ttu-id="72614-116">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="72614-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="72614-117">**ヘッダー:** CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="72614-117">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="72614-118">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="72614-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="72614-119">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="72614-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72614-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="72614-120">See also</span></span>

- [<span data-ttu-id="72614-121">デバッグ構造体</span><span class="sxs-lookup"><span data-stu-id="72614-121">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="72614-122">デバッグ</span><span class="sxs-lookup"><span data-stu-id="72614-122">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
