---
title: IHostSyncManager::CreateSemaphore メソッド
ms.date: 03/30/2017
api_name:
- IHostSyncManager.CreateSemaphore
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager::CreateSemaphore
helpviewer_keywords:
- CreateSemaphore method [.NET Framework hosting]
- IHostSyncManager::CreateSemaphore method [.NET Framework hosting]
ms.assetid: 37679e94-5ff9-4173-8fa5-457febeb89bf
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3ef9a5896c2ecc54b7fd48670f751d193ac74554
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59138620"
---
# <a name="ihostsyncmanagercreatesemaphore-method"></a><span data-ttu-id="72024-102">IHostSyncManager::CreateSemaphore メソッド</span><span class="sxs-lookup"><span data-stu-id="72024-102">IHostSyncManager::CreateSemaphore Method</span></span>
<span data-ttu-id="72024-103">作成、 [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)待機イベントのセマフォとして使用する共通言語ランタイム (CLR) オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="72024-103">Creates an [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) object for the common language runtime (CLR) to use as a semaphore for wait events.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72024-104">構文</span><span class="sxs-lookup"><span data-stu-id="72024-104">Syntax</span></span>  
  
```  
HRESULT CreateSemaphore (  
    [in]  DWORD dwInitial,  
    [in]  DWORD dwMax,  
    [out] IHostSemaphore **ppSemaphore  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="72024-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="72024-105">Parameters</span></span>  
 `dwInitial`  
 <span data-ttu-id="72024-106">[in]最初の数の`ppSemaphore`します。</span><span class="sxs-lookup"><span data-stu-id="72024-106">[in] The initial count for `ppSemaphore`.</span></span>  
  
 `dwMax`  
 <span data-ttu-id="72024-107">[in]最大数は、`ppSemaphore`します。</span><span class="sxs-lookup"><span data-stu-id="72024-107">[in] The maximum count for `ppSemaphore`.</span></span>  
  
 `ppSemaphore`  
 <span data-ttu-id="72024-108">[out]アドレスへのポインター、`IHostSemaphore`インスタンス、またはセマフォを作成できなかった場合は null です。</span><span class="sxs-lookup"><span data-stu-id="72024-108">[out] A pointer to the address of an `IHostSemaphore` instance, or null if the semaphore could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="72024-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="72024-109">Return Value</span></span>  
  
|<span data-ttu-id="72024-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="72024-110">HRESULT</span></span>|<span data-ttu-id="72024-111">説明</span><span class="sxs-lookup"><span data-stu-id="72024-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="72024-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="72024-112">S_OK</span></span>|`CreateSemaphore` <span data-ttu-id="72024-113">正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="72024-113">returned successfully.</span></span>|  
|<span data-ttu-id="72024-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="72024-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="72024-115">プロセスに CLR が読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="72024-115">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="72024-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="72024-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="72024-117">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="72024-117">The call timed out.</span></span>|  
|<span data-ttu-id="72024-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="72024-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="72024-119">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="72024-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="72024-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="72024-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="72024-121">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="72024-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="72024-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="72024-122">E_FAIL</span></span>|<span data-ttu-id="72024-123">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="72024-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="72024-124">メソッドには、E_FAIL が返される、ときに、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="72024-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="72024-125">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="72024-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="72024-126">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="72024-126">E_OUTOFMEMORY</span></span>|<span data-ttu-id="72024-127">メモリ不足は、要求されたイベント オブジェクトを作成できませんでした。</span><span class="sxs-lookup"><span data-stu-id="72024-127">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="72024-128">Remarks</span><span class="sxs-lookup"><span data-stu-id="72024-128">Remarks</span></span>  
 `CreateSemaphore` <span data-ttu-id="72024-129">同じ名前を持つ Win32 関数をミラー化します。</span><span class="sxs-lookup"><span data-stu-id="72024-129">mirrors the Win32 function that has the same name.</span></span> <span data-ttu-id="72024-130">`dwInitial`と`dwMax`パラメーターとして、Win32 セマフォのカウントのと同じセマンティクスを使用して`lInitialCount`と`lMaximumCount`パラメーター、それぞれします。</span><span class="sxs-lookup"><span data-stu-id="72024-130">The `dwInitial` and `dwMax` parameters use the same semantics for the semaphore count as the Win32 `lInitialCount` and `lMaximumCount` parameters, respectively.</span></span> `dwInitial` <span data-ttu-id="72024-131">0 の間である必要がありますと`dwMax`までの値。</span><span class="sxs-lookup"><span data-stu-id="72024-131">must be between zero and `dwMax`, inclusive.</span></span> `dwMax` <span data-ttu-id="72024-132">0 より大きくなければなりません。</span><span class="sxs-lookup"><span data-stu-id="72024-132">must be greater than zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="72024-133">必要条件</span><span class="sxs-lookup"><span data-stu-id="72024-133">Requirements</span></span>  
 <span data-ttu-id="72024-134">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="72024-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="72024-135">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="72024-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="72024-136">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="72024-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="72024-137">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="72024-137">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="72024-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="72024-138">See also</span></span>

- [<span data-ttu-id="72024-139">ICLRSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="72024-139">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="72024-140">IHostSemaphore インターフェイス</span><span class="sxs-lookup"><span data-stu-id="72024-140">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)
- [<span data-ttu-id="72024-141">IHostSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="72024-141">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
