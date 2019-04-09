---
title: CorDebugUserState 列挙型
ms.date: 03/30/2017
api_name:
- CorDebugUserState
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugUserState
helpviewer_keywords:
- CorDebugUserState enumeration [.NET Framework debugging]
ms.assetid: 5f6c2bcd-8102-4e3b-abc5-86ab0bd62def
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c54b2af6e7a200db89bfd7335868a629d7a886fc
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59141311"
---
# <a name="cordebuguserstate-enumeration"></a><span data-ttu-id="29fcd-102">CorDebugUserState 列挙型</span><span class="sxs-lookup"><span data-stu-id="29fcd-102">CorDebugUserState Enumeration</span></span>
<span data-ttu-id="29fcd-103">スレッドのユーザーの状態を示します。</span><span class="sxs-lookup"><span data-stu-id="29fcd-103">Indicates the user state of a thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="29fcd-104">構文</span><span class="sxs-lookup"><span data-stu-id="29fcd-104">Syntax</span></span>  
  
```  
typedef enum CorDebugUserState {  
    USER_STOP_REQUESTED     =  0x01,  
    USER_SUSPEND_REQUESTED  =  0x02,  
    USER_BACKGROUND         =  0x04,  
    USER_UNSTARTED          =  0x08,  
    USER_STOPPED            =  0x10,  
    USER_WAIT_SLEEP_JOIN    =  0x20,  
    USER_SUSPENDED          =  0x40,  
    USER_UNSAFE_POINT       =  0x80,  
    USER_THREADPOOL         = 0x100  
} CorDebugUserState;  
```  
  
## <a name="members"></a><span data-ttu-id="29fcd-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="29fcd-105">Members</span></span>  
  
|<span data-ttu-id="29fcd-106">[値]</span><span class="sxs-lookup"><span data-stu-id="29fcd-106">Value</span></span>|<span data-ttu-id="29fcd-107">説明</span><span class="sxs-lookup"><span data-stu-id="29fcd-107">Description</span></span>|  
|-----------|-----------------|  
|`USER_STOP_REQUESTED`|<span data-ttu-id="29fcd-108">スレッドの終了が要求されています。</span><span class="sxs-lookup"><span data-stu-id="29fcd-108">A termination of the thread has been requested.</span></span>|  
|`USER_SUSPEND_REQUESTED`|<span data-ttu-id="29fcd-109">スレッドの中断が要求されています。</span><span class="sxs-lookup"><span data-stu-id="29fcd-109">A suspension of the thread has been requested.</span></span>|  
|`USER_BACKGROUND`|<span data-ttu-id="29fcd-110">スレッドのバック グラウンドで実行します。</span><span class="sxs-lookup"><span data-stu-id="29fcd-110">The thread is running in the background.</span></span>|  
|`USER_UNSTARTED`|<span data-ttu-id="29fcd-111">スレッドが実行を開始していません。</span><span class="sxs-lookup"><span data-stu-id="29fcd-111">The thread has not started executing.</span></span>|  
|`USER_STOPPED`|<span data-ttu-id="29fcd-112">スレッドが終了しました。</span><span class="sxs-lookup"><span data-stu-id="29fcd-112">The thread has been terminated.</span></span>|  
|`USER_WAIT_SLEEP_JOIN`|<span data-ttu-id="29fcd-113">スレッドがタスクを完了する別のスレッドを待機しています。</span><span class="sxs-lookup"><span data-stu-id="29fcd-113">The thread is waiting for another thread to complete a task.</span></span>|  
|`USER_SUSPENDED`|<span data-ttu-id="29fcd-114">スレッドが中断されました。</span><span class="sxs-lookup"><span data-stu-id="29fcd-114">The thread has been suspended.</span></span>|  
|`USER_UNSAFE_POINT`|<span data-ttu-id="29fcd-115">スレッドは、安全でない点になります。</span><span class="sxs-lookup"><span data-stu-id="29fcd-115">The thread is at an unsafe point.</span></span> <span data-ttu-id="29fcd-116">これは、スレッドがある実行の時点でガベージ コレクションを妨げること可能性があります。</span><span class="sxs-lookup"><span data-stu-id="29fcd-116">That is, the thread is at a point in execution where it may block garbage collection.</span></span><br /><br /> <span data-ttu-id="29fcd-117">デバッグ、安全でないポイントからイベントをディスパッチすることがありますが、安全でない時点でスレッドを中断する、多くの場合、デッドロックが発生、スレッドが再開されるまでです。</span><span class="sxs-lookup"><span data-stu-id="29fcd-117">Debug events may be dispatched from unsafe points, but suspending a thread at an unsafe point  will very likely cause a deadlock until the thread is resumed.</span></span> <span data-ttu-id="29fcd-118">安全性と安全でないポイントは、- イン タイム (JIT) およびガベージ コレクションの実装によって決まります。</span><span class="sxs-lookup"><span data-stu-id="29fcd-118">The safe and unsafe points are determined by the just-in-time (JIT) and garbage collection implementation.</span></span>|  
|`USER_THREADPOOL`|<span data-ttu-id="29fcd-119">スレッドはスレッド プールです。</span><span class="sxs-lookup"><span data-stu-id="29fcd-119">The thread is from the thread pool.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="29fcd-120">Remarks</span><span class="sxs-lookup"><span data-stu-id="29fcd-120">Remarks</span></span>  
 <span data-ttu-id="29fcd-121">スレッドのユーザー状態とは、状態、スレッドがデバッガーを調べることでです。</span><span class="sxs-lookup"><span data-stu-id="29fcd-121">The user state of a thread is the state that the thread has when the debugger examines it.</span></span> <span data-ttu-id="29fcd-122">スレッドは、ユーザー状態の組み合わせがあります。</span><span class="sxs-lookup"><span data-stu-id="29fcd-122">A thread may have a combination of user states.</span></span>  
  
 <span data-ttu-id="29fcd-123">使用して、 [icordebugthread::getuserstate](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getuserstate-method.md)スレッドのユーザーの状態を取得します。</span><span class="sxs-lookup"><span data-stu-id="29fcd-123">Use the [ICorDebugThread::GetUserState](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getuserstate-method.md) method to retrieve a thread's user state.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="29fcd-124">必要条件</span><span class="sxs-lookup"><span data-stu-id="29fcd-124">Requirements</span></span>  
 <span data-ttu-id="29fcd-125">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="29fcd-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="29fcd-126">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="29fcd-126">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="29fcd-127">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="29fcd-127">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="29fcd-128">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="29fcd-128">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="29fcd-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="29fcd-129">See also</span></span>

- [<span data-ttu-id="29fcd-130">列挙体のデバッグ</span><span class="sxs-lookup"><span data-stu-id="29fcd-130">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
