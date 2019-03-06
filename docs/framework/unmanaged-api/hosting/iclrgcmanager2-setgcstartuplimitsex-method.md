---
title: ICLRGCManager2::SetGCStartupLimitsEx メソッド
ms.date: 03/30/2017
api_name:
- ICLRGCManager2.SetGCStartupLimitsEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRGCManager2::SetCLRGCStartupLimitsEx
helpviewer_keywords:
- ICLRGCManager2::SetGCStartupLimitsEx method [.NET Framework hosting]
- SetGCStartupLimitsEx method, ICLRGCManager2 interface [.NET Framework hosting]
ms.assetid: 6c3a08a9-5d65-48d4-8bbf-2a86ed7d356a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 708dd1e13fd999f9a3a11ce36248e82c15000bfc
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57479052"
---
# <a name="iclrgcmanager2setgcstartuplimitsex-method"></a><span data-ttu-id="708d7-102">ICLRGCManager2::SetGCStartupLimitsEx メソッド</span><span class="sxs-lookup"><span data-stu-id="708d7-102">ICLRGCManager2::SetGCStartupLimitsEx Method</span></span>
<span data-ttu-id="708d7-103">ガベージ コレクション セグメントのサイズと、ガベージ コレクション システムのジェネレーション 0 の最大サイズを設定します。</span><span class="sxs-lookup"><span data-stu-id="708d7-103">Sets the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="708d7-104">構文</span><span class="sxs-lookup"><span data-stu-id="708d7-104">Syntax</span></span>  
  
```  
HRESULT SetGCStartupLimitsEx (  
    [in] SIZE_T SegmentSize,   
    [in] SIZE_T MaxGen0Size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="708d7-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="708d7-105">Parameters</span></span>  
 `SegmentSize`  
 <span data-ttu-id="708d7-106">[in]ガベージ コレクション セグメントの指定されたサイズ。</span><span class="sxs-lookup"><span data-stu-id="708d7-106">[in] The specified size of a garbage collection segment.</span></span>  
  
 <span data-ttu-id="708d7-107">セグメントの最小サイズは、4 MB です。</span><span class="sxs-lookup"><span data-stu-id="708d7-107">The minimum segment size is 4 MB.</span></span> <span data-ttu-id="708d7-108">セグメントには、1 MB 単位で増加以上を指定できます。</span><span class="sxs-lookup"><span data-stu-id="708d7-108">Segments can be increased in increments of 1 MB or larger.</span></span>  
  
 `MaxGen0Size`  
 <span data-ttu-id="708d7-109">[in]ジェネレーション 0 の指定した最大サイズ。</span><span class="sxs-lookup"><span data-stu-id="708d7-109">[in] The specified maximum size for generation 0.</span></span>  
  
 <span data-ttu-id="708d7-110">ジェネレーション 0 の最小サイズは、64 KB です。</span><span class="sxs-lookup"><span data-stu-id="708d7-110">The minimum generation 0 size is 64 KB.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="708d7-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="708d7-111">Return Value</span></span>  
  
|<span data-ttu-id="708d7-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="708d7-112">HRESULT</span></span>|<span data-ttu-id="708d7-113">説明</span><span class="sxs-lookup"><span data-stu-id="708d7-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="708d7-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="708d7-114">S_OK</span></span>|<span data-ttu-id="708d7-115">`SetGCStartupLimitsEx` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="708d7-115">`SetGCStartupLimitsEx` returned successfully.</span></span>|  
|<span data-ttu-id="708d7-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="708d7-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="708d7-117">共通言語ランタイム (CLR) は、プロセスに読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="708d7-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="708d7-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="708d7-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="708d7-119">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="708d7-119">The call timed out.</span></span>|  
|<span data-ttu-id="708d7-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="708d7-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="708d7-121">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="708d7-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="708d7-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="708d7-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="708d7-123">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="708d7-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="708d7-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="708d7-124">E_FAIL</span></span>|<span data-ttu-id="708d7-125">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="708d7-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="708d7-126">メソッドには、E_FAIL が返された、後に、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="708d7-126">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="708d7-127">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="708d7-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="708d7-128">Remarks</span><span class="sxs-lookup"><span data-stu-id="708d7-128">Remarks</span></span>  
 <span data-ttu-id="708d7-129">値を`SetGCStartupLimitsEx`ホストを開始する前に、セットを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="708d7-129">The values that `SetGCStartupLimitsEx` sets can be specified only before the host is started.</span></span> <span data-ttu-id="708d7-130">後で呼び出し`SetGCStartupLimitsEx`は無視されます。</span><span class="sxs-lookup"><span data-stu-id="708d7-130">Later calls to `SetGCStartupLimitsEx` are ignored.</span></span>  
  
 <span data-ttu-id="708d7-131">を他の影響を与えずにどちらかのパラメーターを設定するには、変更するパラメーターの 0 (ゼロ) を指定します。</span><span class="sxs-lookup"><span data-stu-id="708d7-131">To set either parameter without affecting the other, specify 0 (zero) for the parameter you don't want to change.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="708d7-132">必要条件</span><span class="sxs-lookup"><span data-stu-id="708d7-132">Requirements</span></span>  
 <span data-ttu-id="708d7-133">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="708d7-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="708d7-134">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="708d7-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="708d7-135">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="708d7-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="708d7-136">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="708d7-136">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="708d7-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="708d7-137">See also</span></span>
- [<span data-ttu-id="708d7-138">自動メモリ管理</span><span class="sxs-lookup"><span data-stu-id="708d7-138">Automatic Memory Management</span></span>](../../../../docs/standard/automatic-memory-management.md)
- [<span data-ttu-id="708d7-139">ガベージ コレクション</span><span class="sxs-lookup"><span data-stu-id="708d7-139">Garbage Collection</span></span>](../../../../docs/standard/garbage-collection/index.md)
- [<span data-ttu-id="708d7-140">ICLRControl インターフェイス</span><span class="sxs-lookup"><span data-stu-id="708d7-140">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="708d7-141">ICLRGCManager2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="708d7-141">ICLRGCManager2 Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-interface.md)
