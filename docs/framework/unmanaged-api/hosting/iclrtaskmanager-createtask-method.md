---
title: ICLRTaskManager::CreateTask メソッド
ms.date: 03/30/2017
api_name:
- ICLRTaskManager.CreateTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTaskManager::CreateTask
helpviewer_keywords:
- ICLRTaskManager::CreateTask method [.NET Framework hosting]
- CreateTask method, ICLRTaskManager interface [.NET Framework hosting]
ms.assetid: eea570d9-2e53-4320-9ea0-eb777bf9dcf3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8833daa9cd385a1a76c5b706f15a76bb15139b84
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59079683"
---
# <a name="iclrtaskmanagercreatetask-method"></a><span data-ttu-id="d0007-102">ICLRTaskManager::CreateTask メソッド</span><span class="sxs-lookup"><span data-stu-id="d0007-102">ICLRTaskManager::CreateTask Method</span></span>
<span data-ttu-id="d0007-103">共通言語ランタイム (CLR) が新しいタスクを作成することを明示的に要求します。</span><span class="sxs-lookup"><span data-stu-id="d0007-103">Requests explicitly that the common language runtime (CLR) create a new task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0007-104">構文</span><span class="sxs-lookup"><span data-stu-id="d0007-104">Syntax</span></span>  
  
```  
HRESULT CreateTask (  
    [out] ICLRTask **pTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d0007-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d0007-105">Parameters</span></span>  
 `pTask`  
 <span data-ttu-id="d0007-106">[out]新しく作成されたのアドレスへのポインター [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)、または null の場合は、タスクを作成できませんでした。</span><span class="sxs-lookup"><span data-stu-id="d0007-106">[out] A pointer to the address of a newly created [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md), or null, if the task could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d0007-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="d0007-107">Return Value</span></span>  
  
|<span data-ttu-id="d0007-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d0007-108">HRESULT</span></span>|<span data-ttu-id="d0007-109">説明</span><span class="sxs-lookup"><span data-stu-id="d0007-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d0007-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="d0007-110">S_OK</span></span>|<span data-ttu-id="d0007-111">メソッドが正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="d0007-111">The method returned successfully.</span></span>|  
|<span data-ttu-id="d0007-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d0007-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d0007-113">プロセスに CLR が読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="d0007-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d0007-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d0007-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d0007-115">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="d0007-115">The call timed out.</span></span>|  
|<span data-ttu-id="d0007-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d0007-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d0007-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="d0007-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d0007-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d0007-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d0007-119">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="d0007-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d0007-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d0007-120">E_FAIL</span></span>|<span data-ttu-id="d0007-121">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="d0007-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d0007-122">メソッドには、E_FAIL が返される、ときに、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="d0007-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d0007-123">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="d0007-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="d0007-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="d0007-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="d0007-125">メモリが不足していますが、要求されたリソースを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="d0007-125">Not enough memory is available to allocate the requested resource.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d0007-126">Remarks</span><span class="sxs-lookup"><span data-stu-id="d0007-126">Remarks</span></span>  
 <span data-ttu-id="d0007-127">ユーザー コードで型を使用してスレッドを作成するときに、CLR が初期化時に自動的に新しいタスクを作成、<xref:System.Threading>名前空間には、スレッド プールのサイズを増加する場合またはします。</span><span class="sxs-lookup"><span data-stu-id="d0007-127">The CLR creates a new task automatically upon initialization, when user code creates a thread by using types in the <xref:System.Threading> namespace, or when the size of the thread pool is increased.</span></span> <span data-ttu-id="d0007-128">また、アンマネージ コードがマネージ関数の呼び出しを行うときにも、タスクを作成します。</span><span class="sxs-lookup"><span data-stu-id="d0007-128">It also creates tasks when unmanaged code makes a call to a managed function.</span></span>  
  
 <span data-ttu-id="d0007-129">`CreateTask` により、CLR が新しいタスクを作成することが明示的に要求をホストできます。</span><span class="sxs-lookup"><span data-stu-id="d0007-129">`CreateTask` allows the host to make an explicit request that the CLR create a new task.</span></span> <span data-ttu-id="d0007-130">たとえば、ホストは、このメソッドを呼び出してデータ構造を呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="d0007-130">For example, the host can invoke this method to preinitialize data structures.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="d0007-131">新しいタスクが中断状態に返され、ホストを明示的に呼び出すまで、中断されたまま[ihosttask::start](../../../../docs/framework/unmanaged-api/hosting/ihosttask-start-method.md)します。</span><span class="sxs-lookup"><span data-stu-id="d0007-131">The new task is returned in a suspended state and remains suspended until the host explicitly calls [IHostTask::Start](../../../../docs/framework/unmanaged-api/hosting/ihosttask-start-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d0007-132">必要条件</span><span class="sxs-lookup"><span data-stu-id="d0007-132">Requirements</span></span>  
 <span data-ttu-id="d0007-133">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0007-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d0007-134">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d0007-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d0007-135">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="d0007-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d0007-136">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d0007-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0007-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="d0007-137">See also</span></span>

- [<span data-ttu-id="d0007-138">ICLRTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d0007-138">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="d0007-139">ICLRTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d0007-139">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="d0007-140">IHostTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d0007-140">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="d0007-141">IHostTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d0007-141">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
