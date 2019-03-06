---
title: IHostCrst::Enter メソッド
ms.date: 03/30/2017
api_name:
- IHostCrst.Enter
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostCrst::Enter
helpviewer_keywords:
- Enter method [.NET Framework hosting]
- IHostCrst::Enter method [.NET Framework hosting]
ms.assetid: 100dd7eb-7053-4295-9bb3-32ba47f6ec79
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: de249928f853c5384db7a2e7615eb425109fd572
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57497432"
---
# <a name="ihostcrstenter-method"></a><span data-ttu-id="c2023-102">IHostCrst::Enter メソッド</span><span class="sxs-lookup"><span data-stu-id="c2023-102">IHostCrst::Enter Method</span></span>
<span data-ttu-id="c2023-103">現在で表される重要なセクションに入ります[IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)インスタンス。</span><span class="sxs-lookup"><span data-stu-id="c2023-103">Enters the critical section that is represented by the current [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2023-104">構文</span><span class="sxs-lookup"><span data-stu-id="c2023-104">Syntax</span></span>  
  
```  
HRESULT Enter (  
    [in] DWORD option  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c2023-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c2023-105">Parameters</span></span>  
 `option`  
 <span data-ttu-id="c2023-106">[in]1 つ、 [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md)場合、ホストが実行するアクションを示す値、操作がブロックされます。</span><span class="sxs-lookup"><span data-stu-id="c2023-106">[in] One of the [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) values, indicating what action the host should take if the operation blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c2023-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="c2023-107">Return Value</span></span>  
  
|<span data-ttu-id="c2023-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c2023-108">HRESULT</span></span>|<span data-ttu-id="c2023-109">説明</span><span class="sxs-lookup"><span data-stu-id="c2023-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c2023-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="c2023-110">S_OK</span></span>|<span data-ttu-id="c2023-111">`Enter` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="c2023-111">`Enter` returned successfully.</span></span>|  
|<span data-ttu-id="c2023-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c2023-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c2023-113">共通言語ランタイム (CLR) は、プロセスに読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="c2023-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c2023-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c2023-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c2023-115">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="c2023-115">The call timed out.</span></span>|  
|<span data-ttu-id="c2023-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c2023-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c2023-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="c2023-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c2023-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c2023-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c2023-119">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="c2023-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c2023-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c2023-120">E_FAIL</span></span>|<span data-ttu-id="c2023-121">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="c2023-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c2023-122">メソッドには、E_FAIL が返される、ときに、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="c2023-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c2023-123">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="c2023-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c2023-124">Remarks</span><span class="sxs-lookup"><span data-stu-id="c2023-124">Remarks</span></span>  
 <span data-ttu-id="c2023-125">`Enter` Win32 をミラー化`EnterCriticalSection`関数。</span><span class="sxs-lookup"><span data-stu-id="c2023-125">`Enter` mirrors the Win32 `EnterCriticalSection` function.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c2023-126">クリティカル セクションが入力されるまで、このメソッドは返しません。</span><span class="sxs-lookup"><span data-stu-id="c2023-126">This method does not return until the critical section is entered.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c2023-127">必要条件</span><span class="sxs-lookup"><span data-stu-id="c2023-127">Requirements</span></span>  
 <span data-ttu-id="c2023-128">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c2023-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c2023-129">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c2023-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c2023-130">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="c2023-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c2023-131">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c2023-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2023-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="c2023-132">See also</span></span>
- [<span data-ttu-id="c2023-133">ICLRSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c2023-133">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="c2023-134">IHostCrst インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c2023-134">IHostCrst Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)
- [<span data-ttu-id="c2023-135">IHostSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c2023-135">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
