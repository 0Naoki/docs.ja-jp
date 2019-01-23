---
title: IHostCrst::Leave メソッド
ms.date: 03/30/2017
api_name:
- IHostCrst.Leave
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostCrst::Leave
helpviewer_keywords:
- IHostCrst::Leave method [.NET Framework hosting]
- Leave method [.NET Framework hosting]
ms.assetid: dfc51d9e-b36d-4dba-9ea1-4f63fa0601ae
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e474a3cf92e818a3e58f4e97786c17af336fa791
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54549929"
---
# <a name="ihostcrstleave-method"></a><span data-ttu-id="0c5b7-102">IHostCrst::Leave メソッド</span><span class="sxs-lookup"><span data-stu-id="0c5b7-102">IHostCrst::Leave Method</span></span>
<span data-ttu-id="0c5b7-103">現在のインスタンスで表される、クリティカル セクションを離れる[IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)します。</span><span class="sxs-lookup"><span data-stu-id="0c5b7-103">Leaves the critical section that is represented by the current instance of [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c5b7-104">構文</span><span class="sxs-lookup"><span data-stu-id="0c5b7-104">Syntax</span></span>  
  
```  
HRESULT Leave ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="0c5b7-105">戻り値</span><span class="sxs-lookup"><span data-stu-id="0c5b7-105">Return Value</span></span>  
  
|<span data-ttu-id="0c5b7-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0c5b7-106">HRESULT</span></span>|<span data-ttu-id="0c5b7-107">説明</span><span class="sxs-lookup"><span data-stu-id="0c5b7-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0c5b7-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="0c5b7-108">S_OK</span></span>|<span data-ttu-id="0c5b7-109">`Leave` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="0c5b7-109">`Leave` returned successfully.</span></span>|  
|<span data-ttu-id="0c5b7-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0c5b7-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0c5b7-111">共通言語ランタイム (CLR) は、プロセスに読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="0c5b7-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="0c5b7-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0c5b7-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0c5b7-113">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="0c5b7-113">The call timed out.</span></span>|  
|<span data-ttu-id="0c5b7-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0c5b7-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0c5b7-115">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="0c5b7-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0c5b7-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0c5b7-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0c5b7-117">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="0c5b7-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0c5b7-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0c5b7-118">E_FAIL</span></span>|<span data-ttu-id="0c5b7-119">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="0c5b7-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="0c5b7-120">メソッドには、E_FAIL が返される、ときに、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="0c5b7-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="0c5b7-121">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="0c5b7-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0c5b7-122">Remarks</span><span class="sxs-lookup"><span data-stu-id="0c5b7-122">Remarks</span></span>  
 <span data-ttu-id="0c5b7-123">`Leave` により、ホストのスレッド、実装ではなく、対応する Win32 を使用して直接通信する CLR`LeaveCriticalSection`関数。</span><span class="sxs-lookup"><span data-stu-id="0c5b7-123">`Leave` allows the CLR to communicate directly with the host's threading implementation, rather than using the corresponding Win32 `LeaveCriticalSection` function.</span></span> <span data-ttu-id="0c5b7-124">現在によって表される、クリティカル セクションの所有権を取得したスレッド`IHostCrst`インスタンスを呼び出す必要があります`Leave`たびに、そのクリティカル セクションに入った。</span><span class="sxs-lookup"><span data-stu-id="0c5b7-124">A thread that takes ownership of the critical section represented by the current `IHostCrst` instance must call `Leave` once for each time it enters that critical section.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0c5b7-125">必要条件</span><span class="sxs-lookup"><span data-stu-id="0c5b7-125">Requirements</span></span>  
 <span data-ttu-id="0c5b7-126">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0c5b7-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0c5b7-127">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="0c5b7-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0c5b7-128">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="0c5b7-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0c5b7-129">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0c5b7-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c5b7-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="0c5b7-130">See also</span></span>
- [<span data-ttu-id="0c5b7-131">ICLRSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0c5b7-131">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="0c5b7-132">IHostCrst インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0c5b7-132">IHostCrst Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)
- [<span data-ttu-id="0c5b7-133">IHostSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0c5b7-133">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
