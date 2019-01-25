---
title: IHostTask::SetPriority メソッド
ms.date: 03/30/2017
api_name:
- IHostTask.SetPriority
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTask::SetPriority
helpviewer_keywords:
- IHostTask::SetPriority method [.NET Framework hosting]
- SetPriority method [.NET Framework hosting]
ms.assetid: cd8c379b-c7a0-434f-8e23-899bd26be75d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9335cb182355931b31040f164c9e51a67598f7b5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54748039"
---
# <a name="ihosttasksetpriority-method"></a><span data-ttu-id="39b7d-102">IHostTask::SetPriority メソッド</span><span class="sxs-lookup"><span data-stu-id="39b7d-102">IHostTask::SetPriority Method</span></span>
<span data-ttu-id="39b7d-103">現在によって表されるタスクのスレッドの優先順位を変更するホストの要求レベル[IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)インスタンス。</span><span class="sxs-lookup"><span data-stu-id="39b7d-103">Requests that the host adjust the thread priority level for the task represented by the current [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39b7d-104">構文</span><span class="sxs-lookup"><span data-stu-id="39b7d-104">Syntax</span></span>  
  
```  
HRESULT SetPriority (  
    [in] int newPriority  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="39b7d-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="39b7d-105">Parameters</span></span>  
 `newPriority`  
 <span data-ttu-id="39b7d-106">[in]現在のタスクの要求されたスレッドの優先度の値を表す整数を`IHostTask`インスタンス。</span><span class="sxs-lookup"><span data-stu-id="39b7d-106">[in] An integer that represents the requested thread priority value for the task represented by the current `IHostTask` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="39b7d-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="39b7d-107">Return Value</span></span>  
  
|<span data-ttu-id="39b7d-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="39b7d-108">HRESULT</span></span>|<span data-ttu-id="39b7d-109">説明</span><span class="sxs-lookup"><span data-stu-id="39b7d-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="39b7d-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="39b7d-110">S_OK</span></span>|<span data-ttu-id="39b7d-111">`SetPriority` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="39b7d-111">`SetPriority` returned successfully.</span></span>|  
|<span data-ttu-id="39b7d-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="39b7d-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="39b7d-113">共通言語ランタイム (CLR) は、プロセスに読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="39b7d-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="39b7d-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="39b7d-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="39b7d-115">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="39b7d-115">The call timed out.</span></span>|  
|<span data-ttu-id="39b7d-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="39b7d-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="39b7d-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="39b7d-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="39b7d-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="39b7d-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="39b7d-119">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="39b7d-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="39b7d-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="39b7d-120">E_FAIL</span></span>|<span data-ttu-id="39b7d-121">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="39b7d-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="39b7d-122">メソッドには、E_FAIL が返される、ときに、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="39b7d-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="39b7d-123">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="39b7d-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="39b7d-124">Remarks</span><span class="sxs-lookup"><span data-stu-id="39b7d-124">Remarks</span></span>  
 <span data-ttu-id="39b7d-125">スレッドのスレッドの優先順位に基づく部分的ラウンド ロビン システムを使用して処理します。</span><span class="sxs-lookup"><span data-stu-id="39b7d-125">Threads are granted processing time using a round-robin system that is partly based on a thread's priority level.</span></span> <span data-ttu-id="39b7d-126">`SetPriority` 現在のタスクそのスレッドの優先度レベルを設定する CLR を使用できます。</span><span class="sxs-lookup"><span data-stu-id="39b7d-126">`SetPriority` allows the CLR to set that thread priority level for the current task.</span></span> <span data-ttu-id="39b7d-127">次`newPriority`値がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="39b7d-127">The following `newPriority` values are supported.</span></span>  
  
-   <span data-ttu-id="39b7d-128">THREAD_PRIORITY_ABOVE_NORMAL</span><span class="sxs-lookup"><span data-stu-id="39b7d-128">THREAD_PRIORITY_ABOVE_NORMAL</span></span>  
  
-   <span data-ttu-id="39b7d-129">THREAD_PRIORITY_BELOW_NORMAL</span><span class="sxs-lookup"><span data-stu-id="39b7d-129">THREAD_PRIORITY_BELOW_NORMAL</span></span>  
  
-   <span data-ttu-id="39b7d-130">THREAD_PRIORITY_HIGHEST</span><span class="sxs-lookup"><span data-stu-id="39b7d-130">THREAD_PRIORITY_HIGHEST</span></span>  
  
-   <span data-ttu-id="39b7d-131">THREAD_PRIORITY_IDLE</span><span class="sxs-lookup"><span data-stu-id="39b7d-131">THREAD_PRIORITY_IDLE</span></span>  
  
-   <span data-ttu-id="39b7d-132">THREAD_PRIORITY_LOWEST</span><span class="sxs-lookup"><span data-stu-id="39b7d-132">THREAD_PRIORITY_LOWEST</span></span>  
  
-   <span data-ttu-id="39b7d-133">THREAD_PRIORITY_NORMAL</span><span class="sxs-lookup"><span data-stu-id="39b7d-133">THREAD_PRIORITY_NORMAL</span></span>  
  
-   <span data-ttu-id="39b7d-134">THREAD_PRIORITY_TIME_CRITICAL</span><span class="sxs-lookup"><span data-stu-id="39b7d-134">THREAD_PRIORITY_TIME_CRITICAL</span></span>  
  
 <span data-ttu-id="39b7d-135">CLR 呼び出し`SetPriority`ときの値、<xref:System.Threading.Thread.Priority%2A?displayProperty=nameWithType>がユーザー コードによって変更します。</span><span class="sxs-lookup"><span data-stu-id="39b7d-135">The CLR calls `SetPriority` when the value of the <xref:System.Threading.Thread.Priority%2A?displayProperty=nameWithType> is modified by user code.</span></span> <span data-ttu-id="39b7d-136">ホストは、スレッドの優先度の割り当て、独自のアルゴリズムを定義でき、この要求を無視します。</span><span class="sxs-lookup"><span data-stu-id="39b7d-136">A host can define its own algorithms for thread priority assignment, and is free to ignore this request.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="39b7d-137">`SetPriority` スレッドの優先順位が変更されたかどうかは報告されません。</span><span class="sxs-lookup"><span data-stu-id="39b7d-137">`SetPriority` does not report whether the thread priority level was changed.</span></span> <span data-ttu-id="39b7d-138">呼び出す[ihosttask::getpriority](../../../../docs/framework/unmanaged-api/hosting/ihosttask-getpriority-method.md)タスクのスレッドの優先順位の値を確認します。</span><span class="sxs-lookup"><span data-stu-id="39b7d-138">Call [IHostTask::GetPriority](../../../../docs/framework/unmanaged-api/hosting/ihosttask-getpriority-method.md) to determine the value of the task's thread priority level.</span></span>  
  
 <span data-ttu-id="39b7d-139">によって Win32 スレッド優先度レベルの値が定義されている`SetThreadPriority`関数。</span><span class="sxs-lookup"><span data-stu-id="39b7d-139">Thread priority level values are defined by the Win32 `SetThreadPriority` function.</span></span> <span data-ttu-id="39b7d-140">スレッドの優先順位の詳細については、Windows プラットフォームのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="39b7d-140">For more information about thread priority, see the Windows Platform documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="39b7d-141">必要条件</span><span class="sxs-lookup"><span data-stu-id="39b7d-141">Requirements</span></span>  
 <span data-ttu-id="39b7d-142">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="39b7d-142">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="39b7d-143">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="39b7d-143">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="39b7d-144">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="39b7d-144">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="39b7d-145">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="39b7d-145">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39b7d-146">関連項目</span><span class="sxs-lookup"><span data-stu-id="39b7d-146">See also</span></span>
- <xref:System.Threading.Thread>
- [<span data-ttu-id="39b7d-147">ICLRTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="39b7d-147">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="39b7d-148">ICLRTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="39b7d-148">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="39b7d-149">IHostTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="39b7d-149">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="39b7d-150">GetPriority メソッド</span><span class="sxs-lookup"><span data-stu-id="39b7d-150">GetPriority Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-getpriority-method.md)
- [<span data-ttu-id="39b7d-151">IHostTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="39b7d-151">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
