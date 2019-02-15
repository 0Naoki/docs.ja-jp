---
title: IHostTaskManager::ReverseLeaveRuntime メソッド
ms.date: 03/30/2017
api_name:
- IHostTaskManager.ReverseLeaveRuntime
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::ReverseLeaveRuntime
helpviewer_keywords:
- IHostTaskManager::ReverseLeaveRuntime method [.NET Framework hosting]
- ReverseLeaveRuntime method [.NET Framework hosting]
ms.assetid: 4837d398-16a1-4e32-902c-022cd1aad3ca
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0a7abcda5ecf56602e884e4d66e1c6900f17b4c6
ms.sourcegitcommit: bef803e2025642df39f2f1e046767d89031e0304
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2019
ms.locfileid: "56305884"
---
# <a name="ihosttaskmanagerreverseleaveruntime-method"></a><span data-ttu-id="7705a-102">IHostTaskManager::ReverseLeaveRuntime メソッド</span><span class="sxs-lookup"><span data-stu-id="7705a-102">IHostTaskManager::ReverseLeaveRuntime Method</span></span>
<span data-ttu-id="7705a-103">コントロールが共通言語ランタイム (CLR) のままであり、さらに、マネージ コードから呼び出されたアンマネージ関数を入力することをホストに通知します。</span><span class="sxs-lookup"><span data-stu-id="7705a-103">Notifies the host that control is leaving the common language runtime (CLR) and entering an unmanaged function that was, in turn, called from managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7705a-104">構文</span><span class="sxs-lookup"><span data-stu-id="7705a-104">Syntax</span></span>  
  
```  
HRESULT ReverseLeaveRuntime ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="7705a-105">戻り値</span><span class="sxs-lookup"><span data-stu-id="7705a-105">Return Value</span></span>  
  
|<span data-ttu-id="7705a-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7705a-106">HRESULT</span></span>|<span data-ttu-id="7705a-107">説明</span><span class="sxs-lookup"><span data-stu-id="7705a-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7705a-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="7705a-108">S_OK</span></span>|<span data-ttu-id="7705a-109">`ReverseLeaveRuntime` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="7705a-109">`ReverseLeaveRuntime` returned successfully.</span></span>|  
|<span data-ttu-id="7705a-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="7705a-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="7705a-111">プロセスに CLR が読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="7705a-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="7705a-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="7705a-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="7705a-113">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="7705a-113">The call timed out.</span></span>|  
|<span data-ttu-id="7705a-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="7705a-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="7705a-115">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="7705a-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="7705a-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="7705a-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="7705a-117">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="7705a-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="7705a-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7705a-118">E_FAIL</span></span>|<span data-ttu-id="7705a-119">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="7705a-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="7705a-120">メソッドには、E_FAIL が返される、ときに、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="7705a-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="7705a-121">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="7705a-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="7705a-122">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="7705a-122">E_OUTOFMEMORY</span></span>|<span data-ttu-id="7705a-123">十分なメモリが要求されたリソースの割り当てを完了します。</span><span class="sxs-lookup"><span data-stu-id="7705a-123">Not enough memory is available to complete the requested resource allocation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7705a-124">Remarks</span><span class="sxs-lookup"><span data-stu-id="7705a-124">Remarks</span></span>  
 <span data-ttu-id="7705a-125">CLR 呼び出し`ReverseLeaveRuntime`プラットフォームを通じてマネージ コードから呼び出されたにすると、さらに、アンマネージ関数に制御が呼び出しを現在実行中のタスクを返すホストに通知します。</span><span class="sxs-lookup"><span data-stu-id="7705a-125">The CLR calls `ReverseLeaveRuntime` to inform the host that the currently executing task is returning control to an unmanaged function that was, in turn, called from managed code through platform invoke.</span></span> <span data-ttu-id="7705a-126">呼び出しごとに`ReverseLeaveRuntime`に対応する呼び出しと一致する[ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md)します。</span><span class="sxs-lookup"><span data-stu-id="7705a-126">Each call to `ReverseLeaveRuntime` matches a corresponding call to [ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7705a-127">必要条件</span><span class="sxs-lookup"><span data-stu-id="7705a-127">Requirements</span></span>  
 <span data-ttu-id="7705a-128">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7705a-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7705a-129">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="7705a-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7705a-130">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="7705a-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7705a-131">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7705a-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7705a-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="7705a-132">See also</span></span>
- [<span data-ttu-id="7705a-133">CallNeedsHostHook メソッド</span><span class="sxs-lookup"><span data-stu-id="7705a-133">CallNeedsHostHook Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-callneedshosthook-method.md)
- [<span data-ttu-id="7705a-134">EnterRuntime メソッド</span><span class="sxs-lookup"><span data-stu-id="7705a-134">EnterRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md)
- [<span data-ttu-id="7705a-135">ICLRTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7705a-135">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="7705a-136">ICLRTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7705a-136">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="7705a-137">IHostTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7705a-137">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="7705a-138">IHostTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7705a-138">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="7705a-139">LeaveRuntime メソッド</span><span class="sxs-lookup"><span data-stu-id="7705a-139">LeaveRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md)
- <span data-ttu-id="7705a-140">[プラットフォーム呼び出しの詳細](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/0h9e9t7d(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="7705a-140">[A Closer Look at Platform Invoke](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/0h9e9t7d(v=vs.100))</span></span>
