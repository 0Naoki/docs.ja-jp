---
title: ICLRIoCompletionManager::OnComplete メソッド
ms.date: 03/30/2017
api_name:
- ICLRIoCompletionManager.OnComplete
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRIoCompletionManager::OnComplete
helpviewer_keywords:
- OnComplete method [.NET Framework hosting]
- ICLRIoCompletionManager::OnComplete method [.NET Framework hosting]
ms.assetid: 003f6974-9727-4322-bed5-e330d1224d0b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fd1763f4271c522c0cfc8731825d67f140b075f8
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57474411"
---
# <a name="iclriocompletionmanageroncomplete-method"></a><span data-ttu-id="78a2e-102">ICLRIoCompletionManager::OnComplete メソッド</span><span class="sxs-lookup"><span data-stu-id="78a2e-102">ICLRIoCompletionManager::OnComplete Method</span></span>
<span data-ttu-id="78a2e-103">共通言語ランタイム (CLR) の通知への呼び出しを使用して作成された I/O 要求の状態、 [ihostiocompletionmanager::bind](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="78a2e-103">Notifies the common language runtime (CLR) of the status of an I/O request that was made by using a call to the [IHostIoCompletionManager::Bind](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78a2e-104">構文</span><span class="sxs-lookup"><span data-stu-id="78a2e-104">Syntax</span></span>  
  
```  
HRESULT OnComplete (  
    [in] DWORD dwErrorCode,  
    [in] DWORD NumberOfBytesTransferred,  
    [in] void* pvOverlapped  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="78a2e-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="78a2e-105">Parameters</span></span>  
 `dwErrorCode`  
 <span data-ttu-id="78a2e-106">[in]バインド操作の状態を示す HRESULT 値。</span><span class="sxs-lookup"><span data-stu-id="78a2e-106">[in] An HRESULT value that indicates the status of the bind operation.</span></span>  
  
-   <span data-ttu-id="78a2e-107">S_OK では、操作が正常に完了したことを示します。</span><span class="sxs-lookup"><span data-stu-id="78a2e-107">S_OK indicates that the operation completed successfully.</span></span>  
  
-   <span data-ttu-id="78a2e-108">HOST_E_INTERRUPTED では、呼び出しが完了する前に終了したことを示します。</span><span class="sxs-lookup"><span data-stu-id="78a2e-108">HOST_E_INTERRUPTED indicates that the call terminated before completion.</span></span>  
  
-   <span data-ttu-id="78a2e-109">E_FAIL では、未知の回復不能な壊滅的なエラーが発生したことを示します。</span><span class="sxs-lookup"><span data-stu-id="78a2e-109">E_FAIL indicates that an unknown, unrecoverable, catastrophic failure occurred.</span></span>  
  
 `NumberOfBytesTransferred`  
 <span data-ttu-id="78a2e-110">[in]I/O 要求の処理中に転送されたバイト数。</span><span class="sxs-lookup"><span data-stu-id="78a2e-110">[in] The number of bytes transferred during the processing of the I/O request.</span></span>  
  
 `pvOverlapped`  
 <span data-ttu-id="78a2e-111">[in]ポインター、`OVERLAPPED`への呼び出しに渡された構造体、`IHostIoCompletionManager::Bind`メソッド。</span><span class="sxs-lookup"><span data-stu-id="78a2e-111">[in] A pointer to the `OVERLAPPED` structure that was passed to the call to the `IHostIoCompletionManager::Bind` method.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="78a2e-112">戻り値</span><span class="sxs-lookup"><span data-stu-id="78a2e-112">Return Value</span></span>  
  
|<span data-ttu-id="78a2e-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="78a2e-113">HRESULT</span></span>|<span data-ttu-id="78a2e-114">説明</span><span class="sxs-lookup"><span data-stu-id="78a2e-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="78a2e-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="78a2e-115">S_OK</span></span>|<span data-ttu-id="78a2e-116">`OnComplete` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="78a2e-116">`OnComplete` returned successfully.</span></span>|  
|<span data-ttu-id="78a2e-117">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="78a2e-117">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="78a2e-118">プロセスに CLR が読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="78a2e-118">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="78a2e-119">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="78a2e-119">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="78a2e-120">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="78a2e-120">The call timed out.</span></span>|  
|<span data-ttu-id="78a2e-121">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="78a2e-121">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="78a2e-122">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="78a2e-122">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="78a2e-123">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="78a2e-123">HOST_E_ABANDONED</span></span>|<span data-ttu-id="78a2e-124">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="78a2e-124">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="78a2e-125">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="78a2e-125">E_FAIL</span></span>|<span data-ttu-id="78a2e-126">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="78a2e-126">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="78a2e-127">メソッドには、E_FAIL が返された、後に、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="78a2e-127">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="78a2e-128">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="78a2e-128">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="78a2e-129">Remarks</span><span class="sxs-lookup"><span data-stu-id="78a2e-129">Remarks</span></span>  
 <span data-ttu-id="78a2e-130">ホストは、I/O 完了の抽象化を実装する場合、CLR がのメソッドを使用してホスト経由で I/O 要求は[IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)します。</span><span class="sxs-lookup"><span data-stu-id="78a2e-130">If the host implements an I/O completion abstraction, the CLR makes I/O requests through the host by using methods of [IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md).</span></span> <span data-ttu-id="78a2e-131">ホストを呼び出して、`OnComplete`このような要求の結果をランタイムに通知するメソッド。</span><span class="sxs-lookup"><span data-stu-id="78a2e-131">The host then calls the `OnComplete` method to notify the runtime of the outcome of such requests.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="78a2e-132">必要条件</span><span class="sxs-lookup"><span data-stu-id="78a2e-132">Requirements</span></span>  
 <span data-ttu-id="78a2e-133">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="78a2e-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="78a2e-134">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="78a2e-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="78a2e-135">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="78a2e-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="78a2e-136">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="78a2e-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78a2e-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="78a2e-137">See also</span></span>
- [<span data-ttu-id="78a2e-138">ICLRIoCompletionManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="78a2e-138">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [<span data-ttu-id="78a2e-139">IHostIoCompletionManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="78a2e-139">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
- [<span data-ttu-id="78a2e-140">IHostThreadPoolManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="78a2e-140">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
