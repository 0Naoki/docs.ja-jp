---
title: ICLRDebugManager::BeginConnection メソッド
ms.date: 03/30/2017
api_name:
- ICLRDebugManager.BeginConnection
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDebugManager::BeginConnection
helpviewer_keywords:
- ICLRDebugManager::BeginConnection method [.NET Framework hosting]
- BeginConnection method [.NET Framework hosting]
ms.assetid: bdd98146-ff4d-4150-a264-a4c1a32d31f3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b365aaa13b3070662a74ebcfc914f5ed3d291d76
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59133992"
---
# <a name="iclrdebugmanagerbeginconnection-method"></a><span data-ttu-id="edf29-102">ICLRDebugManager::BeginConnection メソッド</span><span class="sxs-lookup"><span data-stu-id="edf29-102">ICLRDebugManager::BeginConnection Method</span></span>
<span data-ttu-id="edf29-103">Id とフレンドリ名を関連付けるタスクの一覧には、ホストとデバッガーの間の新しい接続を確立します。</span><span class="sxs-lookup"><span data-stu-id="edf29-103">Establishes a new connection between the host and the debugger to associate a list of tasks with an identifier and a friendly name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="edf29-104">構文</span><span class="sxs-lookup"><span data-stu-id="edf29-104">Syntax</span></span>  
  
```  
HRESULT BeginConnection (  
    [in] CONNID dwConnectionId,  
    [in, string] wchar_t* szConnectionName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="edf29-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="edf29-105">Parameters</span></span>  
 `dwConnectionId`  
 <span data-ttu-id="edf29-106">[in]共通言語ランタイム (CLR) タスクの一覧に関連付ける識別子です。</span><span class="sxs-lookup"><span data-stu-id="edf29-106">[in] An identifier to associate with the list of common language runtime (CLR) tasks.</span></span>  
  
 `szConnectionName`  
 <span data-ttu-id="edf29-107">[in]CLR タスクの一覧に関連付ける表示名。</span><span class="sxs-lookup"><span data-stu-id="edf29-107">[in] A friendly name to associate with the list of CLR tasks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="edf29-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="edf29-108">Return Value</span></span>  
  
|<span data-ttu-id="edf29-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="edf29-109">HRESULT</span></span>|<span data-ttu-id="edf29-110">説明</span><span class="sxs-lookup"><span data-stu-id="edf29-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="edf29-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="edf29-111">S_OK</span></span>|<span data-ttu-id="edf29-112">`BeginConnection` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="edf29-112">`BeginConnection` returned successfully.</span></span>|  
|<span data-ttu-id="edf29-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="edf29-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="edf29-114">プロセスに CLR が読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="edf29-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="edf29-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="edf29-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="edf29-116">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="edf29-116">The call timed out.</span></span>|  
|<span data-ttu-id="edf29-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="edf29-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="edf29-118">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="edf29-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="edf29-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="edf29-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="edf29-120">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="edf29-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="edf29-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="edf29-121">E_FAIL</span></span>|<span data-ttu-id="edf29-122">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="edf29-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="edf29-123">メソッドには、E_FAIL が返された、後に、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="edf29-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="edf29-124">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="edf29-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="edf29-125">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="edf29-125">E_INVALIDARG</span></span>|<span data-ttu-id="edf29-126">`dwConnectionId` 0、または`BeginConnection`がこれを使用して既に呼び出さ`dwConnectionId`値、または`szConnectionName`が null でした。</span><span class="sxs-lookup"><span data-stu-id="edf29-126">`dwConnectionId` was zero, or `BeginConnection` was already called using this `dwConnectionId` value, or `szConnectionName` was null.</span></span>|  
|<span data-ttu-id="edf29-127">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="edf29-127">E_OUTOFMEMORY</span></span>|<span data-ttu-id="edf29-128">この接続に関連付けられているタスクの一覧を保持するために十分なメモリを割り当てる。</span><span class="sxs-lookup"><span data-stu-id="edf29-128">Not enough memory could be allocated to hold the list of tasks associated with this connection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="edf29-129">Remarks</span><span class="sxs-lookup"><span data-stu-id="edf29-129">Remarks</span></span>  
 <span data-ttu-id="edf29-130">[ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md) 3 つのメソッドを提供します`BeginConnection`、 [SetConnectionTasks](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md)、および[EndConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md)識別子とフレンドリ名をタスク一覧に関連付けるためです。</span><span class="sxs-lookup"><span data-stu-id="edf29-130">[ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md) provides three methods, `BeginConnection`, [SetConnectionTasks](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md), and [EndConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md), for associating task lists with identifiers and friendly names.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="edf29-131">タスクのセットごとに特定の順序では、これら 3 つのメソッドを呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="edf29-131">These three methods must be called in a specific order for each set of tasks.</span></span> <span data-ttu-id="edf29-132">`BeginConnection` 新しい接続を確立するためが最初に呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="edf29-132">`BeginConnection` is called first to establish a new connection.</span></span> <span data-ttu-id="edf29-133">`SetConnectionTasks` その接続に関連するタスクのセットを提供するが次に呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="edf29-133">`SetConnectionTasks` is called next to provide the set of tasks to be associated with that connection.</span></span> <span data-ttu-id="edf29-134">`EndConnection` タスク一覧と、識別子とフレンドリ名の間の関連付けを削除する最後に呼び出されます。ただし、異なる接続への呼び出しは入れ子にできます。</span><span class="sxs-lookup"><span data-stu-id="edf29-134">`EndConnection` is called last to remove the association between the task list and the identifier and friendly name.However, calls for different connections can be nested.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="edf29-135">必要条件</span><span class="sxs-lookup"><span data-stu-id="edf29-135">Requirements</span></span>  
 <span data-ttu-id="edf29-136">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="edf29-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="edf29-137">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="edf29-137">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="edf29-138">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="edf29-138">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="edf29-139">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="edf29-139">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="edf29-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="edf29-140">See also</span></span>

- [<span data-ttu-id="edf29-141">ICLRControl インターフェイス</span><span class="sxs-lookup"><span data-stu-id="edf29-141">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="edf29-142">ICLRDebugManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="edf29-142">ICLRDebugManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)
- [<span data-ttu-id="edf29-143">EndConnection メソッド</span><span class="sxs-lookup"><span data-stu-id="edf29-143">EndConnection Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md)
- [<span data-ttu-id="edf29-144">SetConnectionTasks メソッド</span><span class="sxs-lookup"><span data-stu-id="edf29-144">SetConnectionTasks Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md)
- [<span data-ttu-id="edf29-145">IHostControl インターフェイス</span><span class="sxs-lookup"><span data-stu-id="edf29-145">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
