---
title: ICLRDebugManager::IsDebuggerAttached メソッド
ms.date: 03/30/2017
api_name:
- ICLRDebugManager.IsDebuggerAttached
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDebugManager::IsDebuggerAttached
helpviewer_keywords:
- IsDebuggerAttached method, ICLRDebugManager interface [.NET Framework hosting]
- ICLRDebugManager::IsDebuggerAttached method [.NET Framework hosting]
ms.assetid: 2f105fe0-f52d-49c5-bda5-583fb27e3aa6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1d6c071b3ac68cb38fc85aff65fff49a71ea4275
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59095388"
---
# <a name="iclrdebugmanagerisdebuggerattached-method"></a><span data-ttu-id="6f649-102">ICLRDebugManager::IsDebuggerAttached メソッド</span><span class="sxs-lookup"><span data-stu-id="6f649-102">ICLRDebugManager::IsDebuggerAttached Method</span></span>
<span data-ttu-id="6f649-103">デバッガーがプロセスにアタッチされているかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="6f649-103">Gets a value that indicates whether a debugger is attached to the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f649-104">構文</span><span class="sxs-lookup"><span data-stu-id="6f649-104">Syntax</span></span>  
  
```  
HRESULT IsDebuggerAttached (  
    [out] BOOL *pbAttached  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6f649-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6f649-105">Parameters</span></span>  
 `pbAttached`  
 <span data-ttu-id="6f649-106">[out]`true`デバッガーがプロセスにアタッチされている。 それ以外の場合`false`します。</span><span class="sxs-lookup"><span data-stu-id="6f649-106">[out] `true` if a debugger is attached to the process; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6f649-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="6f649-107">Return Value</span></span>  
  
|<span data-ttu-id="6f649-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6f649-108">HRESULT</span></span>|<span data-ttu-id="6f649-109">説明</span><span class="sxs-lookup"><span data-stu-id="6f649-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6f649-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="6f649-110">S_OK</span></span>|<span data-ttu-id="6f649-111">`IsDebuggerAttached` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="6f649-111">`IsDebuggerAttached` returned successfully.</span></span>|  
|<span data-ttu-id="6f649-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="6f649-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="6f649-113">共通言語ランタイム (CLR) は、プロセスに読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="6f649-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="6f649-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="6f649-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="6f649-115">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="6f649-115">The call timed out.</span></span>|  
|<span data-ttu-id="6f649-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="6f649-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="6f649-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="6f649-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="6f649-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="6f649-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="6f649-119">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="6f649-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="6f649-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="6f649-120">E_FAIL</span></span>|<span data-ttu-id="6f649-121">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="6f649-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="6f649-122">メソッドには、E_FAIL が返された、後に、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="6f649-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="6f649-123">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="6f649-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6f649-124">Remarks</span><span class="sxs-lookup"><span data-stu-id="6f649-124">Remarks</span></span>  
 <span data-ttu-id="6f649-125">`IsDebuggerAttached` により、デバッガーがプロセスにアタッチされているかどうかを判断する CLR のクエリをホストできます。</span><span class="sxs-lookup"><span data-stu-id="6f649-125">`IsDebuggerAttached` allows the host to query the CLR to determine whether a debugger is attached to the process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6f649-126">必要条件</span><span class="sxs-lookup"><span data-stu-id="6f649-126">Requirements</span></span>  
 <span data-ttu-id="6f649-127">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6f649-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6f649-128">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="6f649-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6f649-129">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="6f649-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6f649-130">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6f649-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f649-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="6f649-131">See also</span></span>

- [<span data-ttu-id="6f649-132">ICLRControl インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6f649-132">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="6f649-133">ICLRDebugManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6f649-133">ICLRDebugManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)
- [<span data-ttu-id="6f649-134">IHostControl インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6f649-134">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
