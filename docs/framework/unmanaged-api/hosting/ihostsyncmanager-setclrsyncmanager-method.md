---
title: IHostSyncManager::SetCLRSyncManager メソッド
ms.date: 03/30/2017
api_name:
- IHostSyncManager.SetCLRSyncManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager::SetCLRSyncManager
helpviewer_keywords:
- IHostSyncManager::SetCLRSyncManager method [.NET Framework hosting]
- SetCLRSyncManager method [.NET Framework hosting]
ms.assetid: 2b8bbe76-a45d-4989-bacb-11df42f8798c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5006e171e2d5bbdd0d9d4a484299b1860c079b3f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59105795"
---
# <a name="ihostsyncmanagersetclrsyncmanager-method"></a><span data-ttu-id="776a2-102">IHostSyncManager::SetCLRSyncManager メソッド</span><span class="sxs-lookup"><span data-stu-id="776a2-102">IHostSyncManager::SetCLRSyncManager Method</span></span>
<span data-ttu-id="776a2-103">セット、 [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)インスタンスに現在関連付ける[IHostSyncManager](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)インスタンス。</span><span class="sxs-lookup"><span data-stu-id="776a2-103">Sets the [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) instance to associate with the current [IHostSyncManager](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="776a2-104">構文</span><span class="sxs-lookup"><span data-stu-id="776a2-104">Syntax</span></span>  
  
```  
HRESULT SetCLRSyncManager (  
    [in] ICLRSyncManager *pManager  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="776a2-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="776a2-105">Parameters</span></span>  
 `pManager`  
 <span data-ttu-id="776a2-106">[in]ポインター、`ICLRSyncManager`共通言語ランタイム (CLR) で指定されたインスタンス。</span><span class="sxs-lookup"><span data-stu-id="776a2-106">[in] A pointer to an `ICLRSyncManager` instance supplied by the common language runtime (CLR).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="776a2-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="776a2-107">Return Value</span></span>  
  
|<span data-ttu-id="776a2-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="776a2-108">HRESULT</span></span>|<span data-ttu-id="776a2-109">説明</span><span class="sxs-lookup"><span data-stu-id="776a2-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="776a2-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="776a2-110">S_OK</span></span>|<span data-ttu-id="776a2-111">`SetCLRSyncManager` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="776a2-111">`SetCLRSyncManager` returned successfully.</span></span>|  
|<span data-ttu-id="776a2-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="776a2-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="776a2-113">プロセスに CLR が読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="776a2-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="776a2-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="776a2-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="776a2-115">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="776a2-115">The call timed out.</span></span>|  
|<span data-ttu-id="776a2-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="776a2-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="776a2-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="776a2-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="776a2-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="776a2-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="776a2-119">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="776a2-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="776a2-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="776a2-120">E_FAIL</span></span>|<span data-ttu-id="776a2-121">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="776a2-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="776a2-122">メソッドには、E_FAIL が返される、ときに、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="776a2-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="776a2-123">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="776a2-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="776a2-124">Remarks</span><span class="sxs-lookup"><span data-stu-id="776a2-124">Remarks</span></span>  
 <span data-ttu-id="776a2-125">ホストと CLR の間の通信を容易にホスト インターフェイスは、通常のペアになっています。</span><span class="sxs-lookup"><span data-stu-id="776a2-125">To facilitate communication between the host and the CLR, hosting interfaces generally come in pairs.</span></span> <span data-ttu-id="776a2-126">ペアの 1 つのメンバーは、ホストによって実装され、その他のメンバーは、CLR によって実装されます。</span><span class="sxs-lookup"><span data-stu-id="776a2-126">One member of the pair is implemented by the host, and the other member is implemented by the CLR.</span></span> <span data-ttu-id="776a2-127">ホスト側の実装として、`IHostSyncManager`インターフェイスに対応する、 `ICLRSyncManager` CLR によって実装されるインターフェイス。</span><span class="sxs-lookup"><span data-stu-id="776a2-127">As a host-side implementation, the `IHostSyncManager` interface corresponds to the `ICLRSyncManager` interface implemented by the CLR.</span></span> <span data-ttu-id="776a2-128">CLR 呼び出し`SetCLRSyncManager`を指定する、`ICLRSyncManager`に関連付ける、現在のホスト インスタンス`IHostSyncManager`インスタンス。</span><span class="sxs-lookup"><span data-stu-id="776a2-128">The CLR calls `SetCLRSyncManager` to supply an `ICLRSyncManager` instance for the host to associate with the current `IHostSyncManager` instance.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="776a2-129">必要条件</span><span class="sxs-lookup"><span data-stu-id="776a2-129">Requirements</span></span>  
 <span data-ttu-id="776a2-130">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="776a2-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="776a2-131">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="776a2-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="776a2-132">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="776a2-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="776a2-133">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="776a2-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="776a2-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="776a2-134">See also</span></span>

- [<span data-ttu-id="776a2-135">ICLRSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="776a2-135">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="776a2-136">IHostSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="776a2-136">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
