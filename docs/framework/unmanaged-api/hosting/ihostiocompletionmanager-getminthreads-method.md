---
title: IHostIoCompletionManager::GetMinThreads メソッド
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.GetMinThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::GetMinThreads
helpviewer_keywords:
- GetMinThreads method, IHostIoCompletionManager interface [.NET Framework hosting]
- IHostIoCompletionManager::GetMinThreads method [.NET Framework hosting]
ms.assetid: d7a7f733-677d-481c-b3d5-444fcc502b8e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f0ba01b576903d08139cfa57c285d079ea692c78
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54614472"
---
# <a name="ihostiocompletionmanagergetminthreads-method"></a><span data-ttu-id="bcb5b-102">IHostIoCompletionManager::GetMinThreads メソッド</span><span class="sxs-lookup"><span data-stu-id="bcb5b-102">IHostIoCompletionManager::GetMinThreads Method</span></span>
<span data-ttu-id="bcb5b-103">I/O 要求を処理するため、ホストが提供するスレッドの最小数を取得します。</span><span class="sxs-lookup"><span data-stu-id="bcb5b-103">Gets the minimum number of threads that the host provides for processing I/O requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bcb5b-104">構文</span><span class="sxs-lookup"><span data-stu-id="bcb5b-104">Syntax</span></span>  
  
```  
HRESULT GetMinThreads (  
    [out] DWORD *pdwMinIOCompletionThreads  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bcb5b-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="bcb5b-105">Parameters</span></span>  
 `pdwMinIOCompletionThreads`  
 <span data-ttu-id="bcb5b-106">[out]プロセスの I/O 要求にホストを提供するスレッドの最小数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="bcb5b-106">[out] A pointer to the minimum number of threads that the host provides to process I/O requests.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bcb5b-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="bcb5b-107">Return Value</span></span>  
  
|<span data-ttu-id="bcb5b-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="bcb5b-108">HRESULT</span></span>|<span data-ttu-id="bcb5b-109">説明</span><span class="sxs-lookup"><span data-stu-id="bcb5b-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="bcb5b-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="bcb5b-110">S_OK</span></span>|<span data-ttu-id="bcb5b-111">`GetMinThreads` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="bcb5b-111">`GetMinThreads` returned successfully.</span></span>|  
|<span data-ttu-id="bcb5b-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="bcb5b-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="bcb5b-113">共通言語ランタイム (CLR) は、プロセスに読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="bcb5b-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="bcb5b-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="bcb5b-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="bcb5b-115">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="bcb5b-115">The call timed out.</span></span>|  
|<span data-ttu-id="bcb5b-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="bcb5b-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="bcb5b-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="bcb5b-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="bcb5b-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="bcb5b-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="bcb5b-119">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="bcb5b-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="bcb5b-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="bcb5b-120">E_FAIL</span></span>|<span data-ttu-id="bcb5b-121">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="bcb5b-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="bcb5b-122">メソッドには、E_FAIL が返される、ときに、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="bcb5b-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="bcb5b-123">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="bcb5b-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="bcb5b-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="bcb5b-124">E_NOTIMPL</span></span>|<span data-ttu-id="bcb5b-125">ホストがの実装を提供しない`GetMinThreads`します。</span><span class="sxs-lookup"><span data-stu-id="bcb5b-125">The host does not provide an implementation of `GetMinThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bcb5b-126">Remarks</span><span class="sxs-lookup"><span data-stu-id="bcb5b-126">Remarks</span></span>  
 <span data-ttu-id="bcb5b-127">ホストの実装、パフォーマンス、スケーラビリティなどの理由から、サービスの I/O 要求に割り当てられているスレッドの数を排他的に制御を必要があります。</span><span class="sxs-lookup"><span data-stu-id="bcb5b-127">A host might want exclusive control over the number of threads allotted to service I/O requests, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="bcb5b-128">このため、ホストする必要はありません実装`GetMinThreads`します。</span><span class="sxs-lookup"><span data-stu-id="bcb5b-128">For this reason, the host is not required to implement `GetMinThreads`.</span></span> <span data-ttu-id="bcb5b-129">この場合、ホストは、このメソッドから E_NOTIMPL を返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="bcb5b-129">In this case, the host should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bcb5b-130">必要条件</span><span class="sxs-lookup"><span data-stu-id="bcb5b-130">Requirements</span></span>  
 <span data-ttu-id="bcb5b-131">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="bcb5b-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bcb5b-132">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="bcb5b-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="bcb5b-133">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="bcb5b-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bcb5b-134">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bcb5b-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bcb5b-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="bcb5b-135">See also</span></span>
- [<span data-ttu-id="bcb5b-136">ICLRIoCompletionManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bcb5b-136">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [<span data-ttu-id="bcb5b-137">IHostIoCompletionManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bcb5b-137">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
