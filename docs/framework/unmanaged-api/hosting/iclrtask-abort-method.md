---
title: ICLRTask::Abort メソッド
ms.date: 03/30/2017
api_name:
- ICLRTask.Abort
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::Abort
helpviewer_keywords:
- ICLRTask::Abort method [.NET Framework hosting]
- Abort method, ICLRTask interface [.NET Framework hosting]
ms.assetid: b3594b5f-2e41-4e36-9096-3586276a138c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 57efd4f29ba7e28adf1af03030d7f83eb32c1c2b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59139777"
---
# <a name="iclrtaskabort-method"></a><span data-ttu-id="8d588-102">ICLRTask::Abort メソッド</span><span class="sxs-lookup"><span data-stu-id="8d588-102">ICLRTask::Abort Method</span></span>
<span data-ttu-id="8d588-103">共通言語ランタイム (CLR) がタスクを中止する要求を現在[ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)インスタンスが表す。</span><span class="sxs-lookup"><span data-stu-id="8d588-103">Requests that the common language runtime (CLR) abort the task that the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d588-104">構文</span><span class="sxs-lookup"><span data-stu-id="8d588-104">Syntax</span></span>  
  
```  
HRESULT Abort ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="8d588-105">戻り値</span><span class="sxs-lookup"><span data-stu-id="8d588-105">Return Value</span></span>  
  
|<span data-ttu-id="8d588-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8d588-106">HRESULT</span></span>|<span data-ttu-id="8d588-107">説明</span><span class="sxs-lookup"><span data-stu-id="8d588-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8d588-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="8d588-108">S_OK</span></span>|<span data-ttu-id="8d588-109">`Abort` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="8d588-109">`Abort` returned successfully.</span></span>|  
|<span data-ttu-id="8d588-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="8d588-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8d588-111">プロセスに CLR が読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="8d588-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="8d588-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="8d588-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="8d588-113">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="8d588-113">The call timed out.</span></span>|  
|<span data-ttu-id="8d588-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="8d588-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="8d588-115">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="8d588-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="8d588-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="8d588-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="8d588-117">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="8d588-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="8d588-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8d588-118">E_FAIL</span></span>|<span data-ttu-id="8d588-119">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="8d588-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="8d588-120">メソッドには、E_FAIL が返される、ときに、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="8d588-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="8d588-121">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="8d588-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8d588-122">Remarks</span><span class="sxs-lookup"><span data-stu-id="8d588-122">Remarks</span></span>  
 <span data-ttu-id="8d588-123">CLR の発生を<xref:System.Threading.ThreadAbortException>ホストを呼び出したときに`Abort`。</span><span class="sxs-lookup"><span data-stu-id="8d588-123">The CLR raises a <xref:System.Threading.ThreadAbortException> when the host calls `Abort`.</span></span> <span data-ttu-id="8d588-124">ファイナライザー、または例外処理機構を実行するなど、ユーザー コードを待つことがなく、例外情報が初期化された後すぐに返します。</span><span class="sxs-lookup"><span data-stu-id="8d588-124">It returns immediately after the exception information is initialized, without waiting for user code, such as finalizers or exception handling mechanisms, to execute.</span></span> <span data-ttu-id="8d588-125">呼び出す`Abort`のためです。</span><span class="sxs-lookup"><span data-stu-id="8d588-125">Calls to `Abort` thus return quickly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8d588-126">必要条件</span><span class="sxs-lookup"><span data-stu-id="8d588-126">Requirements</span></span>  
 <span data-ttu-id="8d588-127">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8d588-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8d588-128">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="8d588-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8d588-129">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="8d588-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8d588-130">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8d588-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d588-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="8d588-131">See also</span></span>

- [<span data-ttu-id="8d588-132">ICLRTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8d588-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="8d588-133">ICLRTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8d588-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="8d588-134">IHostTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8d588-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="8d588-135">IHostTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8d588-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
