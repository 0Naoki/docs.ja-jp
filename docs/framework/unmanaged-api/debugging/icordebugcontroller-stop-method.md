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
ms.openlocfilehash: fbe0459824499aba86c908012f038256f9923513
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57496692"
---
# <a name="icordebugcontrollerstop-method"></a><span data-ttu-id="dcd5d-102">ICorDebugController::Stop メソッド</span><span class="sxs-lookup"><span data-stu-id="dcd5d-102">ICorDebugController::Stop Method</span></span>
<span data-ttu-id="dcd5d-103">プロセスでマネージ コードを実行しているすべてのスレッドを協調停止を実行します。</span><span class="sxs-lookup"><span data-stu-id="dcd5d-103">Performs a cooperative stop on all threads that are running managed code in the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dcd5d-104">構文</span><span class="sxs-lookup"><span data-stu-id="dcd5d-104">Syntax</span></span>  
  
```  
HRESULT Stop (  
    [in] DWORD dwTimeoutIgnored  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dcd5d-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="dcd5d-105">Parameters</span></span>  
 `dwTimeoutIgnored`  
 <span data-ttu-id="dcd5d-106">使用しません。</span><span class="sxs-lookup"><span data-stu-id="dcd5d-106">Not used.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dcd5d-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="dcd5d-107">Remarks</span></span>  
 <span data-ttu-id="dcd5d-108">`Stop` プロセスの管理を実行しているすべてのスレッドの協調停止コードを実行します。</span><span class="sxs-lookup"><span data-stu-id="dcd5d-108">`Stop` performs a cooperative stop on all threads running managed code in the process.</span></span> <span data-ttu-id="dcd5d-109">マネージドのみのデバッグ セッション中に、アンマネージ スレッドが実行を続行できます (ただし、マネージ コードを呼び出すしようとするときはブロックされます)。</span><span class="sxs-lookup"><span data-stu-id="dcd5d-109">During a managed-only debugging session, unmanaged threads may continue to run (but will be blocked when trying to call managed code).</span></span> <span data-ttu-id="dcd5d-110">相互運用機能デバッグ セッション、中には、アンマネージ スレッドも停止されます。</span><span class="sxs-lookup"><span data-stu-id="dcd5d-110">During an interop debugging session, unmanaged threads will also be stopped.</span></span> <span data-ttu-id="dcd5d-111">`dwTimeoutIgnored`現在値が無視され、無限 (-1) として扱われます。</span><span class="sxs-lookup"><span data-stu-id="dcd5d-111">The `dwTimeoutIgnored` value is currently ignored and treated as INFINITE (-1).</span></span> <span data-ttu-id="dcd5d-112">協調停止は、デッドロックのため失敗した場合、すべてのスレッドが中断され、E_TIMEOUT が返されます。</span><span class="sxs-lookup"><span data-stu-id="dcd5d-112">If the cooperative stop fails due to a deadlock, all threads are suspended and E_TIMEOUT is returned.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dcd5d-113">`Stop` デバッグ API でのみ同期メソッドです。</span><span class="sxs-lookup"><span data-stu-id="dcd5d-113">`Stop` is the only synchronous method in the debugging API.</span></span> <span data-ttu-id="dcd5d-114">ときに`Stop`場合は s_ok、プロセスが停止します。</span><span class="sxs-lookup"><span data-stu-id="dcd5d-114">When `Stop` returns S_OK, the process is stopped.</span></span> <span data-ttu-id="dcd5d-115">停止のリスナーに通知するコールバックが指定されていません。</span><span class="sxs-lookup"><span data-stu-id="dcd5d-115">No callback is given to notify listeners of the stop.</span></span> <span data-ttu-id="dcd5d-116">デバッガーを呼び出す必要があります[icordebugcontroller::continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md)を再開するプロセスが可能にします。</span><span class="sxs-lookup"><span data-stu-id="dcd5d-116">The debugger must call [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) to allow the process to resume.</span></span>  
  
 <span data-ttu-id="dcd5d-117">デバッガーでは、停止カウンターを保持します。</span><span class="sxs-lookup"><span data-stu-id="dcd5d-117">The debugger maintains a stop counter.</span></span> <span data-ttu-id="dcd5d-118">カウンターがゼロに時に、コント ローラーが再開されます。</span><span class="sxs-lookup"><span data-stu-id="dcd5d-118">When the counter goes to zero, the controller is resumed.</span></span> <span data-ttu-id="dcd5d-119">呼び出しごとに`Stop`またはディスパッチされた各コールバックは、カウンターをインクリメントします。</span><span class="sxs-lookup"><span data-stu-id="dcd5d-119">Each call to `Stop` or each dispatched callback increments the counter.</span></span> <span data-ttu-id="dcd5d-120">呼び出しごとに`ICorDebugController::Continue`デクリメント カウンター。</span><span class="sxs-lookup"><span data-stu-id="dcd5d-120">Each call to `ICorDebugController::Continue` decrements the counter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dcd5d-121">必要条件</span><span class="sxs-lookup"><span data-stu-id="dcd5d-121">Requirements</span></span>  
 <span data-ttu-id="dcd5d-122">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="dcd5d-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dcd5d-123">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dcd5d-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dcd5d-124">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dcd5d-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dcd5d-125">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dcd5d-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dcd5d-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="dcd5d-126">See also</span></span>

