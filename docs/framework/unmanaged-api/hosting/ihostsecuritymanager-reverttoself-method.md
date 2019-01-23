---
title: IHostSecurityManager::RevertToSelf メソッド
ms.date: 03/30/2017
api_name:
- IHostSecurityManager.RevertToSelf
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityManager::RevertToSelf
helpviewer_keywords:
- RevertToSelf method [.NET Framework hosting]
- IHostSecurityManager::RevertToSelf method [.NET Framework hosting]
ms.assetid: 189f28f8-f9a1-4192-aedc-91084e4f8b99
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 98af4c0d2e5f5930c179b4b96ffccd7ef0703211
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54562402"
---
# <a name="ihostsecuritymanagerreverttoself-method"></a><span data-ttu-id="6d874-102">IHostSecurityManager::RevertToSelf メソッド</span><span class="sxs-lookup"><span data-stu-id="6d874-102">IHostSecurityManager::RevertToSelf Method</span></span>
<span data-ttu-id="6d874-103">現在のユーザー id の権限の借用を終了し、元のスレッド トークンを返します。</span><span class="sxs-lookup"><span data-stu-id="6d874-103">Terminates impersonation of the current user identity and returns the original thread token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d874-104">構文</span><span class="sxs-lookup"><span data-stu-id="6d874-104">Syntax</span></span>  
  
```  
HRESULT RevertToSelf ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="6d874-105">戻り値</span><span class="sxs-lookup"><span data-stu-id="6d874-105">Return Value</span></span>  
  
|<span data-ttu-id="6d874-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6d874-106">HRESULT</span></span>|<span data-ttu-id="6d874-107">説明</span><span class="sxs-lookup"><span data-stu-id="6d874-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6d874-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="6d874-108">S_OK</span></span>|<span data-ttu-id="6d874-109">`RevertToSelf` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="6d874-109">`RevertToSelf` returned successfully.</span></span>|  
|<span data-ttu-id="6d874-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="6d874-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="6d874-111">共通言語ランタイム (CLR) は、プロセスに読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="6d874-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="6d874-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="6d874-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="6d874-113">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="6d874-113">The call timed out.</span></span>|  
|<span data-ttu-id="6d874-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="6d874-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="6d874-115">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="6d874-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="6d874-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="6d874-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="6d874-117">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="6d874-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="6d874-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="6d874-118">E_FAIL</span></span>|<span data-ttu-id="6d874-119">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="6d874-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="6d874-120">メソッドには、E_FAIL が返される、ときに、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="6d874-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="6d874-121">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="6d874-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6d874-122">Remarks</span><span class="sxs-lookup"><span data-stu-id="6d874-122">Remarks</span></span>  
 <span data-ttu-id="6d874-123">`RevertToSelf` 事前に呼び出した後に元のスレッド トークンを返すために呼び出される、 [ImpersonateLoggedOnUser](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-impersonateloggedonuser-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="6d874-123">`RevertToSelf` is called to return to the original thread token, after an earlier call to the [ImpersonateLoggedOnUser](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-impersonateloggedonuser-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6d874-124">必要条件</span><span class="sxs-lookup"><span data-stu-id="6d874-124">Requirements</span></span>  
 <span data-ttu-id="6d874-125">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6d874-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6d874-126">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="6d874-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6d874-127">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="6d874-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6d874-128">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6d874-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d874-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="6d874-129">See also</span></span>
- [<span data-ttu-id="6d874-130">IHostSecurityContext インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6d874-130">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)
- [<span data-ttu-id="6d874-131">IHostSecurityManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6d874-131">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
- [<span data-ttu-id="6d874-132">ImpersonateLoggedOnUser メソッド</span><span class="sxs-lookup"><span data-stu-id="6d874-132">ImpersonateLoggedOnUser Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-impersonateloggedonuser-method.md)
