---
title: ICLRGCManager::Collect メソッド
ms.date: 03/30/2017
api_name:
- ICLRGCManager.Collect
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRGCManager::Collect
helpviewer_keywords:
- ICLRGCManager::Collect method [.NET Framework hosting]
- Collect method, ICLRGCManager interface [.NET Framework hosting]
ms.assetid: 0c6cbbea-c27c-4695-bda3-17c1910d8ddb
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9b448892a58dd120fd0f30f2b61be59e579b629a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54651410"
---
# <a name="iclrgcmanagercollect-method"></a><span data-ttu-id="c35d0-102">ICLRGCManager::Collect メソッド</span><span class="sxs-lookup"><span data-stu-id="c35d0-102">ICLRGCManager::Collect Method</span></span>
<span data-ttu-id="c35d0-103">指定したジェネレーションのガベージ コレクションを強制します。</span><span class="sxs-lookup"><span data-stu-id="c35d0-103">Forces a garbage collection for the specified generation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c35d0-104">構文</span><span class="sxs-lookup"><span data-stu-id="c35d0-104">Syntax</span></span>  
  
```  
HRESULT Collect (  
    [in] LONG Generation  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c35d0-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c35d0-105">Parameters</span></span>  
 `Generation`  
 <span data-ttu-id="c35d0-106">[in]収集を生成します。</span><span class="sxs-lookup"><span data-stu-id="c35d0-106">[in] The generation to collect.</span></span> <span data-ttu-id="c35d0-107">-1 の値を強制的にすべてのジェネレーションのコレクション。</span><span class="sxs-lookup"><span data-stu-id="c35d0-107">A value of -1 forces a collection of all generations.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c35d0-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="c35d0-108">Return Value</span></span>  
  
|<span data-ttu-id="c35d0-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c35d0-109">HRESULT</span></span>|<span data-ttu-id="c35d0-110">説明</span><span class="sxs-lookup"><span data-stu-id="c35d0-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c35d0-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="c35d0-111">S_OK</span></span>|<span data-ttu-id="c35d0-112">`Collect` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="c35d0-112">`Collect` returned successfully.</span></span>|  
|<span data-ttu-id="c35d0-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c35d0-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c35d0-114">共通言語ランタイム (CLR) は、プロセスに読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="c35d0-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c35d0-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c35d0-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c35d0-116">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="c35d0-116">The call timed out.</span></span>|  
|<span data-ttu-id="c35d0-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c35d0-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c35d0-118">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="c35d0-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c35d0-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c35d0-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c35d0-120">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="c35d0-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c35d0-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c35d0-121">E_FAIL</span></span>|<span data-ttu-id="c35d0-122">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="c35d0-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c35d0-123">メソッドには、E_FAIL が返された、後に、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="c35d0-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c35d0-124">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="c35d0-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c35d0-125">Remarks</span><span class="sxs-lookup"><span data-stu-id="c35d0-125">Remarks</span></span>  
 <span data-ttu-id="c35d0-126">`Collect`メソッドは、現在の状態に関係なくコレクションを実行する CLR のガベージ コレクターを強制します。</span><span class="sxs-lookup"><span data-stu-id="c35d0-126">The `Collect` method forces the CLR's garbage collector to perform a collection regardless of its current state.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c35d0-127">必要条件</span><span class="sxs-lookup"><span data-stu-id="c35d0-127">Requirements</span></span>  
 <span data-ttu-id="c35d0-128">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c35d0-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c35d0-129">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c35d0-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c35d0-130">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="c35d0-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c35d0-131">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c35d0-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c35d0-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="c35d0-132">See also</span></span>
- [<span data-ttu-id="c35d0-133">自動メモリ管理</span><span class="sxs-lookup"><span data-stu-id="c35d0-133">Automatic Memory Management</span></span>](../../../../docs/standard/automatic-memory-management.md)
- [<span data-ttu-id="c35d0-134">ガベージ コレクション</span><span class="sxs-lookup"><span data-stu-id="c35d0-134">Garbage Collection</span></span>](../../../../docs/standard/garbage-collection/index.md)
- [<span data-ttu-id="c35d0-135">ICLRControl インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c35d0-135">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="c35d0-136">ICLRGCManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c35d0-136">ICLRGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md)
- [<span data-ttu-id="c35d0-137">CLR ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c35d0-137">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)
- [<span data-ttu-id="c35d0-138">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c35d0-138">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="c35d0-139">ホスティング</span><span class="sxs-lookup"><span data-stu-id="c35d0-139">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
