---
title: ICLRTask::NeedsPriorityScheduling メソッド
ms.date: 03/30/2017
api_name:
- ICLRTask.NeedsPriorityScheduling
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::NeedsPriorityScheduling
helpviewer_keywords:
- ICLRTask::NeedsPriorityScheduling method [.NET Framework hosting]
- NeedsPriorityScheduling method [.NET Framework hosting]
ms.assetid: 9c9db3f3-26bf-4317-88de-5eb926a22a1d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a2a26e32040f705fd46f9d9d8909fd47e963baa8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54510782"
---
# <a name="iclrtaskneedspriorityscheduling-method"></a><span data-ttu-id="ffccd-102">ICLRTask::NeedsPriorityScheduling メソッド</span><span class="sxs-lookup"><span data-stu-id="ffccd-102">ICLRTask::NeedsPriorityScheduling Method</span></span>
<span data-ttu-id="ffccd-103">アウト切り替わるは、現在のタスクを再スケジューリングの優先度の高いとしてマーク済みである必要があるかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="ffccd-103">Gets a value that indicates whether the current task, which is being switched out, needs to be marked as a high priority for rescheduling.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ffccd-104">構文</span><span class="sxs-lookup"><span data-stu-id="ffccd-104">Syntax</span></span>  
  
```  
HRESULT NeedsPriorityScheduling (  
    [out] BOOL *pbNeedsPriorityScheduling  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ffccd-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ffccd-105">Parameters</span></span>  
 `pbNeedsPriorityRescheduling`  
 <span data-ttu-id="ffccd-106">[out]`true`、できるだけ早く。 そうしないと、現在のタスク インスタンスを再スケジュールする、ホストを試みる必要がある場合は、`false`します。</span><span class="sxs-lookup"><span data-stu-id="ffccd-106">[out] `true`, if the host should attempt to reschedule the current task instance as soon as possible; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ffccd-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="ffccd-107">Return Value</span></span>  
  
|<span data-ttu-id="ffccd-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ffccd-108">HRESULT</span></span>|<span data-ttu-id="ffccd-109">説明</span><span class="sxs-lookup"><span data-stu-id="ffccd-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ffccd-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="ffccd-110">S_OK</span></span>|<span data-ttu-id="ffccd-111">`NeedsPriorityRescheduling` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="ffccd-111">`NeedsPriorityRescheduling` returned successfully.</span></span>|  
|<span data-ttu-id="ffccd-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ffccd-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ffccd-113">共通言語ランタイム (CLR) は、プロセスに読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="ffccd-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ffccd-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ffccd-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ffccd-115">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="ffccd-115">The call timed out.</span></span>|  
|<span data-ttu-id="ffccd-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ffccd-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ffccd-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="ffccd-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ffccd-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ffccd-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ffccd-119">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="ffccd-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ffccd-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ffccd-120">E_FAIL</span></span>|<span data-ttu-id="ffccd-121">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="ffccd-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ffccd-122">メソッドには、E_FAIL が返される、ときに、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="ffccd-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ffccd-123">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="ffccd-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ffccd-124">Remarks</span><span class="sxs-lookup"><span data-stu-id="ffccd-124">Remarks</span></span>  
 <span data-ttu-id="ffccd-125">CLR がの値を設定するタスクがガベージ コレクターによって収集されるデータに近い状況、`pbNeedsPriorityScheduling`に`true`、優先度の高い再スケジューリングを示します。</span><span class="sxs-lookup"><span data-stu-id="ffccd-125">In situations where the task is close to being collected by the garbage collector, the CLR sets the value of `pbNeedsPriorityScheduling` to `true`, indicating high-priority rescheduling.</span></span> <span data-ttu-id="ffccd-126">これにより、ガベージ コレクションで遅延が発生する可能性を最小限に抑えることと、メモリ リソースの節約に協力するには、ホストと、ランタイムを有効にするため、すぐに、タスクのスケジュールを変更するホストできます。</span><span class="sxs-lookup"><span data-stu-id="ffccd-126">This allows the host to reschedule the task quickly, thereby minimizing the potential for delays in garbage collection, and enabling the host and the runtime to cooperate in conserving memory resources.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ffccd-127">必要条件</span><span class="sxs-lookup"><span data-stu-id="ffccd-127">Requirements</span></span>  
 <span data-ttu-id="ffccd-128">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ffccd-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ffccd-129">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ffccd-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ffccd-130">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="ffccd-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ffccd-131">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ffccd-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ffccd-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="ffccd-132">See also</span></span>
- [<span data-ttu-id="ffccd-133">ICLRTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ffccd-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="ffccd-134">ICLRTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ffccd-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="ffccd-135">IHostTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ffccd-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="ffccd-136">IHostTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ffccd-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
