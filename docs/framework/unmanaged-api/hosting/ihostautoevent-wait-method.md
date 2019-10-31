---
title: IHostAutoEvent::Wait メソッド
ms.date: 03/30/2017
api_name:
- IHostAutoEvent.Wait
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAutoEvent::Wait
helpviewer_keywords:
- Wait method, IHostAutoEvent interface [.NET Framework hosting]
- IHostAutoEvent::Wait method [.NET Framework hosting]
ms.assetid: 535d51c5-9112-401b-8c36-85f35d7ee609
topic_type:
- apiref
ms.openlocfilehash: 0258999bae8b04ddaccf264276d1439b027b4a43
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73195891"
---
# <a name="ihostautoeventwait-method"></a><span data-ttu-id="624e7-102">IHostAutoEvent::Wait メソッド</span><span class="sxs-lookup"><span data-stu-id="624e7-102">IHostAutoEvent::Wait Method</span></span>
<span data-ttu-id="624e7-103">現在の[IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)インスタンスが所有されるか、指定された時間が経過するまで待機するようにします。</span><span class="sxs-lookup"><span data-stu-id="624e7-103">Causes the current [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) instance to wait until it is owned or a specified amount of time elapses.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="624e7-104">構文</span><span class="sxs-lookup"><span data-stu-id="624e7-104">Syntax</span></span>  
  
```cpp  
HRESULT Wait (  
    [in] DWORD dwMilliseconds,  
    [in] DWORD option  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="624e7-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="624e7-105">Parameters</span></span>  
 `dwMilliseconds`  
 <span data-ttu-id="624e7-106">からスレッドまたはファイバーが所有権を取得しない場合に、現在の `IHostAutoEvent` インスタンスが戻る前に待機するミリ秒数。</span><span class="sxs-lookup"><span data-stu-id="624e7-106">[in] The number of milliseconds the current `IHostAutoEvent` instance should wait before returning, if no thread or fiber takes ownership.</span></span>  
  
 `option`  
 <span data-ttu-id="624e7-107">から[WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md)値の1つ。この操作がブロックされた場合にホストが実行するアクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="624e7-107">[in] One of the [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) values, specifying the action the host should take if this operation blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="624e7-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="624e7-108">Return Value</span></span>  
  
|<span data-ttu-id="624e7-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="624e7-109">HRESULT</span></span>|<span data-ttu-id="624e7-110">説明</span><span class="sxs-lookup"><span data-stu-id="624e7-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="624e7-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="624e7-111">S_OK</span></span>|<span data-ttu-id="624e7-112">`Wait` が正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="624e7-112">`Wait` returned successfully.</span></span>|  
|<span data-ttu-id="624e7-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="624e7-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="624e7-114">共通言語ランタイム (CLR) がプロセスに読み込まれていないか、CLR がマネージコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="624e7-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="624e7-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="624e7-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="624e7-116">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="624e7-116">The call timed out.</span></span>|  
|<span data-ttu-id="624e7-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="624e7-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="624e7-118">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="624e7-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="624e7-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="624e7-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="624e7-120">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="624e7-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="624e7-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="624e7-121">E_FAIL</span></span>|<span data-ttu-id="624e7-122">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="624e7-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="624e7-123">メソッドから E_FAIL が返された場合、そのプロセス内で CLR は使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="624e7-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="624e7-124">後続のホストメソッドの呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="624e7-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="624e7-125">HOST_E_DEADLOCK</span><span class="sxs-lookup"><span data-stu-id="624e7-125">HOST_E_DEADLOCK</span></span>|<span data-ttu-id="624e7-126">ホストは待機間隔中にデッドロックを検出し、現在の `IHostAutoEvent` インスタンスによって表されるイベントをデッドロックの対象として選択しました。</span><span class="sxs-lookup"><span data-stu-id="624e7-126">The host detected a deadlock during the wait interval, and chose the event represented by the current `IHostAutoEvent` instance as the deadlock victim.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="624e7-127">［要件］</span><span class="sxs-lookup"><span data-stu-id="624e7-127">Requirements</span></span>  
 <span data-ttu-id="624e7-128">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="624e7-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="624e7-129">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="624e7-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="624e7-130">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="624e7-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="624e7-131">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="624e7-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="624e7-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="624e7-132">See also</span></span>

- [<span data-ttu-id="624e7-133">ICLRSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="624e7-133">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="624e7-134">IHostAutoEvent インターフェイス</span><span class="sxs-lookup"><span data-stu-id="624e7-134">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="624e7-135">IHostManualEvent インターフェイス</span><span class="sxs-lookup"><span data-stu-id="624e7-135">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="624e7-136">IHostSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="624e7-136">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
