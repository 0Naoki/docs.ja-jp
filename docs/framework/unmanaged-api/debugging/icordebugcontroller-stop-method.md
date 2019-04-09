---
title: ICorDebugController::Stop メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugController.Stop
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::Stop
helpviewer_keywords:
- Stop method, ICorDebugController interface [.NET Framework debugging]
- ICorDebugController::Stop method [.NET Framework debugging]
ms.assetid: c34e79be-a7fb-479e-8dec-d126a4c330e5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 724db8c5c8dbb5bf3ff8bc7202a60397180b7b38
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59183392"
---
# <a name="icordebugcontrollerstop-method"></a><span data-ttu-id="a15de-102">ICorDebugController::Stop メソッド</span><span class="sxs-lookup"><span data-stu-id="a15de-102">ICorDebugController::Stop Method</span></span>
<span data-ttu-id="a15de-103">プロセスでマネージ コードを実行しているすべてのスレッドを協調停止を実行します。</span><span class="sxs-lookup"><span data-stu-id="a15de-103">Performs a cooperative stop on all threads that are running managed code in the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a15de-104">構文</span><span class="sxs-lookup"><span data-stu-id="a15de-104">Syntax</span></span>  
  
```  
HRESULT Stop (  
    [in] DWORD dwTimeoutIgnored  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a15de-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a15de-105">Parameters</span></span>  
 `dwTimeoutIgnored`  
 <span data-ttu-id="a15de-106">使用しません。</span><span class="sxs-lookup"><span data-stu-id="a15de-106">Not used.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a15de-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="a15de-107">Remarks</span></span>  
 `Stop` <span data-ttu-id="a15de-108">プロセスの管理を実行しているすべてのスレッドの協調停止コードを実行します。</span><span class="sxs-lookup"><span data-stu-id="a15de-108">performs a cooperative stop on all threads running managed code in the process.</span></span> <span data-ttu-id="a15de-109">マネージドのみのデバッグ セッション中に、アンマネージ スレッドが実行を続行できます (ただし、マネージ コードを呼び出すしようとするときはブロックされます)。</span><span class="sxs-lookup"><span data-stu-id="a15de-109">During a managed-only debugging session, unmanaged threads may continue to run (but will be blocked when trying to call managed code).</span></span> <span data-ttu-id="a15de-110">相互運用機能デバッグ セッション、中には、アンマネージ スレッドも停止されます。</span><span class="sxs-lookup"><span data-stu-id="a15de-110">During an interop debugging session, unmanaged threads will also be stopped.</span></span> <span data-ttu-id="a15de-111">`dwTimeoutIgnored`現在値が無視され、無限 (-1) として扱われます。</span><span class="sxs-lookup"><span data-stu-id="a15de-111">The `dwTimeoutIgnored` value is currently ignored and treated as INFINITE (-1).</span></span> <span data-ttu-id="a15de-112">協調停止は、デッドロックのため失敗した場合、すべてのスレッドが中断され、E_TIMEOUT が返されます。</span><span class="sxs-lookup"><span data-stu-id="a15de-112">If the cooperative stop fails due to a deadlock, all threads are suspended and E_TIMEOUT is returned.</span></span>  
  
> [!NOTE]
>  `Stop` <span data-ttu-id="a15de-113">デバッグ API でのみ同期メソッドです。</span><span class="sxs-lookup"><span data-stu-id="a15de-113">is the only synchronous method in the debugging API.</span></span> <span data-ttu-id="a15de-114">ときに`Stop`場合は s_ok、プロセスが停止します。</span><span class="sxs-lookup"><span data-stu-id="a15de-114">When `Stop` returns S_OK, the process is stopped.</span></span> <span data-ttu-id="a15de-115">停止のリスナーに通知するコールバックが指定されていません。</span><span class="sxs-lookup"><span data-stu-id="a15de-115">No callback is given to notify listeners of the stop.</span></span> <span data-ttu-id="a15de-116">デバッガーを呼び出す必要があります[icordebugcontroller::continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md)を再開するプロセスが可能にします。</span><span class="sxs-lookup"><span data-stu-id="a15de-116">The debugger must call [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) to allow the process to resume.</span></span>  
  
 <span data-ttu-id="a15de-117">デバッガーでは、停止カウンターを保持します。</span><span class="sxs-lookup"><span data-stu-id="a15de-117">The debugger maintains a stop counter.</span></span> <span data-ttu-id="a15de-118">カウンターがゼロに時に、コント ローラーが再開されます。</span><span class="sxs-lookup"><span data-stu-id="a15de-118">When the counter goes to zero, the controller is resumed.</span></span> <span data-ttu-id="a15de-119">呼び出しごとに`Stop`またはディスパッチされた各コールバックは、カウンターをインクリメントします。</span><span class="sxs-lookup"><span data-stu-id="a15de-119">Each call to `Stop` or each dispatched callback increments the counter.</span></span> <span data-ttu-id="a15de-120">呼び出しごとに`ICorDebugController::Continue`デクリメント カウンター。</span><span class="sxs-lookup"><span data-stu-id="a15de-120">Each call to `ICorDebugController::Continue` decrements the counter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a15de-121">必要条件</span><span class="sxs-lookup"><span data-stu-id="a15de-121">Requirements</span></span>  
 <span data-ttu-id="a15de-122">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a15de-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a15de-123">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a15de-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a15de-124">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a15de-124">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="a15de-125">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="a15de-125">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a15de-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="a15de-126">See also</span></span>
