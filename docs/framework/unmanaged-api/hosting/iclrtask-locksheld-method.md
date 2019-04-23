---
title: ICLRTask::LocksHeld メソッド
ms.date: 03/30/2017
api_name:
- ICLRTask.LocksHeld
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::LocksHeld
helpviewer_keywords:
- LocksHeld method [.NET Framework hosting]
- ICLRTask::LocksHeld method [.NET Framework hosting]
ms.assetid: e88a4dc3-02cc-4703-a474-292b71c40657
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3f548d8b19a76aaccbae276dd63f091e4488690b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59106809"
---
# <a name="iclrtasklocksheld-method"></a><span data-ttu-id="a670a-102">ICLRTask::LocksHeld メソッド</span><span class="sxs-lookup"><span data-stu-id="a670a-102">ICLRTask::LocksHeld Method</span></span>
<span data-ttu-id="a670a-103">タスクで現在保持されているロックの数を取得します。</span><span class="sxs-lookup"><span data-stu-id="a670a-103">Gets the number of locks currently held on the task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a670a-104">構文</span><span class="sxs-lookup"><span data-stu-id="a670a-104">Syntax</span></span>  
  
```  
HRESULT LocksHeld (  
    [out] SIZE_T *pLockCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a670a-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a670a-105">Parameters</span></span>  
 `pLockCount`  
 <span data-ttu-id="a670a-106">[out]メソッドの呼び出し時に、タスクで保持されているロックの数。</span><span class="sxs-lookup"><span data-stu-id="a670a-106">[out] The number of locks held on the task at the time of the method call.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a670a-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="a670a-107">Return Value</span></span>  
  
|<span data-ttu-id="a670a-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a670a-108">HRESULT</span></span>|<span data-ttu-id="a670a-109">説明</span><span class="sxs-lookup"><span data-stu-id="a670a-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a670a-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="a670a-110">S_OK</span></span>|<span data-ttu-id="a670a-111">`LocksHeld` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="a670a-111">`LocksHeld` returned successfully.</span></span>|  
|<span data-ttu-id="a670a-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a670a-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a670a-113">共通言語ランタイム (CLR) は、プロセスに読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="a670a-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a670a-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a670a-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a670a-115">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="a670a-115">The call timed out.</span></span>|  
|<span data-ttu-id="a670a-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a670a-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a670a-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="a670a-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a670a-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a670a-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a670a-119">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="a670a-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a670a-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a670a-120">E_FAIL</span></span>|<span data-ttu-id="a670a-121">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="a670a-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a670a-122">メソッドには、E_FAIL が返される、ときに、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="a670a-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a670a-123">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="a670a-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a670a-124">必要条件</span><span class="sxs-lookup"><span data-stu-id="a670a-124">Requirements</span></span>  
 <span data-ttu-id="a670a-125">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a670a-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a670a-126">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a670a-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a670a-127">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="a670a-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a670a-128">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a670a-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a670a-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="a670a-129">See also</span></span>

- [<span data-ttu-id="a670a-130">ICLRTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a670a-130">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="a670a-131">ICLRTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a670a-131">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="a670a-132">IHostTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a670a-132">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="a670a-133">IHostTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a670a-133">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
