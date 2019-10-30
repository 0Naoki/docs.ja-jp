---
title: ICLRRuntimeHost::SetHostControl メソッド
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.SetHostControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::SetHostControl
helpviewer_keywords:
- SetHostControl method [.NET Framework hosting]
- ICLRRuntimeHost::SetHostControl method [.NET Framework hosting]
ms.assetid: 6136be87-e631-4756-81ed-74b66581bad4
topic_type:
- apiref
ms.openlocfilehash: 68b06a2840de277bdaed1dc9ce0b51e6b363c897
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120451"
---
# <a name="iclrruntimehostsethostcontrol-method"></a><span data-ttu-id="46e3a-102">ICLRRuntimeHost::SetHostControl メソッド</span><span class="sxs-lookup"><span data-stu-id="46e3a-102">ICLRRuntimeHost::SetHostControl Method</span></span>
<span data-ttu-id="46e3a-103">[IHostControl インターフェイス](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)のホストの実装を取得するために共通言語ランタイム (CLR) が使用できるインターフェイスポインターを設定します。</span><span class="sxs-lookup"><span data-stu-id="46e3a-103">Sets the interface pointer that the common language runtime (CLR) can use to get the host's implementation of [IHostControl Interface](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46e3a-104">構文</span><span class="sxs-lookup"><span data-stu-id="46e3a-104">Syntax</span></span>  
  
```cpp  
HRESULT SetHostControl(  
    [in] IHostControl* pHostControl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="46e3a-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="46e3a-105">Parameters</span></span>  
 `pHostControl`  
 <span data-ttu-id="46e3a-106">から[IHostControl インターフェイス](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)のホストの実装へのインターフェイスポインター。</span><span class="sxs-lookup"><span data-stu-id="46e3a-106">[in] An interface pointer to the host's implementation of [IHostControl Interface](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="46e3a-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="46e3a-107">Return Value</span></span>  
  
|<span data-ttu-id="46e3a-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="46e3a-108">HRESULT</span></span>|<span data-ttu-id="46e3a-109">説明</span><span class="sxs-lookup"><span data-stu-id="46e3a-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="46e3a-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="46e3a-110">S_OK</span></span>|<span data-ttu-id="46e3a-111">`SetHostControl` が正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="46e3a-111">`SetHostControl` returned successfully.</span></span>|  
|<span data-ttu-id="46e3a-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="46e3a-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="46e3a-113">CLR がプロセスに読み込まれていないか、CLR がマネージドコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="46e3a-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="46e3a-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="46e3a-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="46e3a-115">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="46e3a-115">The call timed out.</span></span>|  
|<span data-ttu-id="46e3a-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="46e3a-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="46e3a-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="46e3a-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="46e3a-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="46e3a-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="46e3a-119">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="46e3a-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="46e3a-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="46e3a-120">E_FAIL</span></span>|<span data-ttu-id="46e3a-121">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="46e3a-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="46e3a-122">メソッドから E_FAIL が返された場合、そのプロセス内で CLR は使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="46e3a-122">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="46e3a-123">後続のホストメソッドの呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="46e3a-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="46e3a-124">E_CLR_ALREADY_STARTED</span><span class="sxs-lookup"><span data-stu-id="46e3a-124">E_CLR_ALREADY_STARTED</span></span>|<span data-ttu-id="46e3a-125">CLR は既に初期化されています。</span><span class="sxs-lookup"><span data-stu-id="46e3a-125">The CLR has already been initialized.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="46e3a-126">Remarks</span><span class="sxs-lookup"><span data-stu-id="46e3a-126">Remarks</span></span>  
 <span data-ttu-id="46e3a-127">CLR が初期化される前に、つまり、 [Start メソッド](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md)を呼び出すか、任意の[メタデータインターフェイス](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)を使用する前に、`SetHostControl` を呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="46e3a-127">You must call `SetHostControl` before the CLR is initialized, that is, before you call [Start Method](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) or use any of the [Metadata Interfaces](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md).</span></span> <span data-ttu-id="46e3a-128">[Corbindtoの Entruntime 関数](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)または[Corbindtocurrentruntime 関数](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)を呼び出した直後に `SetHostControl` を呼び出すことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="46e3a-128">It is recommended that you call `SetHostControl` immediately after calling [CorBindToCurrentRuntime Function](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md) or [CorBindToRuntimeEx Function](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="46e3a-129">［要件］</span><span class="sxs-lookup"><span data-stu-id="46e3a-129">Requirements</span></span>  
 <span data-ttu-id="46e3a-130">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="46e3a-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="46e3a-131">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="46e3a-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="46e3a-132">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="46e3a-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="46e3a-133">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="46e3a-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46e3a-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="46e3a-134">See also</span></span>

- [<span data-ttu-id="46e3a-135">ICLRRuntimeHost インターフェイス</span><span class="sxs-lookup"><span data-stu-id="46e3a-135">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
- [<span data-ttu-id="46e3a-136">IHostControl インターフェイス</span><span class="sxs-lookup"><span data-stu-id="46e3a-136">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
