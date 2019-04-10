---
title: IHostIoCompletionManager::SetMaxThreads メソッド
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.SetMaxThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::SetMaxThreads
helpviewer_keywords:
- IHostIoCompletionManager::SetMaxThreads method [.NET Framework hosting]
- SetMaxThreads method, IHostIoCompletionManager interface [.NET Framework hosting]
ms.assetid: ebad4f40-d9f1-4dc6-9b27-a89c9eb3926f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 345c7b88b6967773a185538943591383a686748c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59224124"
---
# <a name="ihostiocompletionmanagersetmaxthreads-method"></a><span data-ttu-id="e282a-102">IHostIoCompletionManager::SetMaxThreads メソッド</span><span class="sxs-lookup"><span data-stu-id="e282a-102">IHostIoCompletionManager::SetMaxThreads Method</span></span>
<span data-ttu-id="e282a-103">I/O 要求を処理するため、ホストに割り当てるスレッドの最大数を設定します。</span><span class="sxs-lookup"><span data-stu-id="e282a-103">Sets the maximum number of threads that the host allots to service I/O requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e282a-104">構文</span><span class="sxs-lookup"><span data-stu-id="e282a-104">Syntax</span></span>  
  
```  
HRESULT SetMaxThreads (  
    [in] DWORD dwMaxIoCompletionThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e282a-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e282a-105">Parameters</span></span>  
 `dwMaxIoCompletionThreads`  
 <span data-ttu-id="e282a-106">[in]I/O 要求に割り当てるスレッドの最大数。</span><span class="sxs-lookup"><span data-stu-id="e282a-106">[in] The maximum number of threads to allot for I/O requests.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e282a-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="e282a-107">Return Value</span></span>  
  
|<span data-ttu-id="e282a-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e282a-108">HRESULT</span></span>|<span data-ttu-id="e282a-109">説明</span><span class="sxs-lookup"><span data-stu-id="e282a-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e282a-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="e282a-110">S_OK</span></span>|`SetMaxThreads` <span data-ttu-id="e282a-111">正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="e282a-111">returned successfully.</span></span>|  
|<span data-ttu-id="e282a-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e282a-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e282a-113">共通言語ランタイム (CLR) は、プロセスに読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="e282a-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="e282a-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e282a-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e282a-115">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="e282a-115">The call timed out.</span></span>|  
|<span data-ttu-id="e282a-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e282a-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e282a-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="e282a-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e282a-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e282a-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e282a-119">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="e282a-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e282a-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e282a-120">E_FAIL</span></span>|<span data-ttu-id="e282a-121">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="e282a-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e282a-122">メソッドには、E_FAIL が返される、ときに、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="e282a-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e282a-123">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="e282a-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="e282a-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="e282a-124">E_NOTIMPL</span></span>|<span data-ttu-id="e282a-125">ホストがの実装を提供しない`SetMaxThreads`します。</span><span class="sxs-lookup"><span data-stu-id="e282a-125">The host does not provide an implementation of `SetMaxThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e282a-126">Remarks</span><span class="sxs-lookup"><span data-stu-id="e282a-126">Remarks</span></span>  
 `SetMaxThreads` <span data-ttu-id="e282a-127">CLR は、I/O ポート上でサービス要求に使用できるスレッドの最大数を設定する機会を提供します。</span><span class="sxs-lookup"><span data-stu-id="e282a-127">provides the CLR with an opportunity to set the maximum number of threads that are available to service requests on I/O ports.</span></span> <span data-ttu-id="e282a-128">ホストの実装、パフォーマンス、スケーラビリティなどの理由から、スレッド プールのサイズを排他的に制御を必要があります。</span><span class="sxs-lookup"><span data-stu-id="e282a-128">A host might need exclusive control over the size of the thread pool, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="e282a-129">このため、ホストする必要はありません実装`SetMaxThreads`します。</span><span class="sxs-lookup"><span data-stu-id="e282a-129">For this reason, the host is not required to implement `SetMaxThreads`.</span></span> <span data-ttu-id="e282a-130">この場合、ホストは、このメソッドから E_NOTIMPL を返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="e282a-130">In this case, a host should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e282a-131">必要条件</span><span class="sxs-lookup"><span data-stu-id="e282a-131">Requirements</span></span>  
 <span data-ttu-id="e282a-132">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e282a-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e282a-133">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e282a-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e282a-134">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="e282a-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="e282a-135">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="e282a-135">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e282a-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="e282a-136">See also</span></span>

- [<span data-ttu-id="e282a-137">ICLRIoCompletionManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e282a-137">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [<span data-ttu-id="e282a-138">IHostIoCompletionManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e282a-138">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
