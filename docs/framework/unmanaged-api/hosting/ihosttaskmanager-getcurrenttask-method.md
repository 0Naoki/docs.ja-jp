---
title: IHostTaskManager::GetCurrentTask メソッド
ms.date: 03/30/2017
api_name:
- IHostTaskManager.GetCurrentTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::GetCurrentTask
helpviewer_keywords:
- GetCurrentTask method, IHostTaskManager interface [.NET Framework hosting]
- IHostTaskManager::GetCurrentTask method [.NET Framework hosting]
ms.assetid: f17bca49-90bd-4dee-a5e1-b9a57ea46f85
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f53227908f263cceeb8677739c0bf5b5ba30cd5e
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57473982"
---
# <a name="ihosttaskmanagergetcurrenttask-method"></a><span data-ttu-id="fe155-102">IHostTaskManager::GetCurrentTask メソッド</span><span class="sxs-lookup"><span data-stu-id="fe155-102">IHostTaskManager::GetCurrentTask Method</span></span>
<span data-ttu-id="fe155-103">この呼び出しが行われた元のオペレーティング システム スレッドで現在実行しているタスクには、インターフェイス ポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="fe155-103">Gets an interface pointer to the task that is currently executing on the operating system thread from which this call is made.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe155-104">構文</span><span class="sxs-lookup"><span data-stu-id="fe155-104">Syntax</span></span>  
  
```  
HRESULT GetCurrentTask (  
    [out] IHostTask **pTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fe155-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="fe155-105">Parameters</span></span>  
 `pTask`  
 <span data-ttu-id="fe155-106">[out]アドレスへのポインター、 [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)タスクが現在実行されていない場合、現在実行中のタスク、または null を表すインスタンス。</span><span class="sxs-lookup"><span data-stu-id="fe155-106">[out] A pointer to the address of an [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance that represents the currently executing task, or null, if no task is currently executing.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fe155-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="fe155-107">Return Value</span></span>  
  
|<span data-ttu-id="fe155-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="fe155-108">HRESULT</span></span>|<span data-ttu-id="fe155-109">説明</span><span class="sxs-lookup"><span data-stu-id="fe155-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="fe155-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="fe155-110">S_OK</span></span>|<span data-ttu-id="fe155-111">`GetCurrentTask` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="fe155-111">`GetCurrentTask` returned successfully.</span></span>|  
|<span data-ttu-id="fe155-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="fe155-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="fe155-113">共通言語ランタイム (CLR) は、プロセスに読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="fe155-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="fe155-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="fe155-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="fe155-115">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="fe155-115">The call timed out.</span></span>|  
|<span data-ttu-id="fe155-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="fe155-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="fe155-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="fe155-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="fe155-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="fe155-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="fe155-119">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="fe155-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="fe155-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="fe155-120">E_FAIL</span></span>|<span data-ttu-id="fe155-121">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="fe155-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="fe155-122">メソッドには、E_FAIL が返される、ときに、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="fe155-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="fe155-123">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="fe155-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="fe155-124">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="fe155-124">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="fe155-125">`GetCurrentTask` ホストの制御範囲外のオペレーティング システム スレッドで呼び出されました。</span><span class="sxs-lookup"><span data-stu-id="fe155-125">`GetCurrentTask` was called on an operating system thread outside the control of the host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fe155-126">Remarks</span><span class="sxs-lookup"><span data-stu-id="fe155-126">Remarks</span></span>  
 <span data-ttu-id="fe155-127">ホストの設定もできます、`pTask`を開始しなかったタスクが CLR を入力するを防ぐために null パラメーター。</span><span class="sxs-lookup"><span data-stu-id="fe155-127">The host can also set the `pTask` parameter to null to prevent a task that it did not initiate from entering the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fe155-128">必要条件</span><span class="sxs-lookup"><span data-stu-id="fe155-128">Requirements</span></span>  
 <span data-ttu-id="fe155-129">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="fe155-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fe155-130">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="fe155-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fe155-131">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="fe155-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fe155-132">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fe155-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe155-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="fe155-133">See also</span></span>
- [<span data-ttu-id="fe155-134">ICLRTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="fe155-134">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="fe155-135">ICLRTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="fe155-135">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="fe155-136">IHostTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="fe155-136">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="fe155-137">IHostTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="fe155-137">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
