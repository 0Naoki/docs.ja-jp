---
title: ICLRTask::SetTaskIdentifier メソッド
ms.date: 03/30/2017
api_name:
- ICLRTask.SetTaskIdentifier
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::SetTaskIdentifier
helpviewer_keywords:
- SetTaskIdentifier method [.NET Framework hosting]
- ICLRTask::SetTaskIdentifier method [.NET Framework hosting]
ms.assetid: bdb7f047-1e90-40fc-9e3b-d44a16509073
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0c57ac26fd08f585af7ff92f700c6cdd60815675
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54734302"
---
# <a name="iclrtasksettaskidentifier-method"></a><span data-ttu-id="eb589-102">ICLRTask::SetTaskIdentifier メソッド</span><span class="sxs-lookup"><span data-stu-id="eb589-102">ICLRTask::SetTaskIdentifier Method</span></span>
<span data-ttu-id="eb589-103">共通言語ランタイム (CLR) に指定した id 値を現在によって表されるタスクに関連付けるように指示します[ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)インスタンス。</span><span class="sxs-lookup"><span data-stu-id="eb589-103">Instructs the common language runtime (CLR) to associate the specified identifier value with the task represented by the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb589-104">構文</span><span class="sxs-lookup"><span data-stu-id="eb589-104">Syntax</span></span>  
  
```  
HRESULT SetTaskIdentifier (  
    [in] DWORD Asked  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="eb589-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="eb589-105">Parameters</span></span>  
 `Asked`  
 <span data-ttu-id="eb589-106">[in]現在によって表されるタスクに関連付け、共通言語ランタイムの一意の識別子`ICLRTask`インスタンス。</span><span class="sxs-lookup"><span data-stu-id="eb589-106">[in] The unique identifier for the common language runtime to associate with the task represented by the current `ICLRTask` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="eb589-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="eb589-107">Return Value</span></span>  
  
|<span data-ttu-id="eb589-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="eb589-108">HRESULT</span></span>|<span data-ttu-id="eb589-109">説明</span><span class="sxs-lookup"><span data-stu-id="eb589-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="eb589-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="eb589-110">S_OK</span></span>|<span data-ttu-id="eb589-111">`SetTaskIdentifier` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="eb589-111">`SetTaskIdentifier` returned successfully.</span></span>|  
|<span data-ttu-id="eb589-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="eb589-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="eb589-113">プロセスに CLR が読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="eb589-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="eb589-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="eb589-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="eb589-115">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="eb589-115">The call timed out.</span></span>|  
|<span data-ttu-id="eb589-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="eb589-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="eb589-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="eb589-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="eb589-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="eb589-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="eb589-119">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="eb589-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="eb589-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="eb589-120">E_FAIL</span></span>|<span data-ttu-id="eb589-121">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="eb589-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="eb589-122">メソッドには、E_FAIL が返される、ときに、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="eb589-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="eb589-123">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="eb589-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="eb589-124">Remarks</span><span class="sxs-lookup"><span data-stu-id="eb589-124">Remarks</span></span>  
 <span data-ttu-id="eb589-125">ホストは、CLR とデバッグ環境でホストと統合できるように、タスクの識別子を関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="eb589-125">The host can associate an identifier with a task to help integrate the CLR and the host in a debugging environment.</span></span> <span data-ttu-id="eb589-126">識別子には、CLR の意味はありません。</span><span class="sxs-lookup"><span data-stu-id="eb589-126">The identifier has no meaning for the CLR.</span></span> <span data-ttu-id="eb589-127">CLR に渡すデバッガー アプリケーション。</span><span class="sxs-lookup"><span data-stu-id="eb589-127">The CLR passes it along to a debugger application.</span></span> <span data-ttu-id="eb589-128">デバッガーでは、この識別子を使用して、ホストの呼び出し履歴と CLR の呼び出し履歴を関連付けるでき、統合デバッガーのユーザー インターフェイスで表示したときに、それぞれのトレース情報を有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="eb589-128">The debugger can use this identifier to associate a CLR call stack with a host call stack, and enable their respective trace information to be unified when viewed in the debugger's user interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eb589-129">必要条件</span><span class="sxs-lookup"><span data-stu-id="eb589-129">Requirements</span></span>  
 <span data-ttu-id="eb589-130">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="eb589-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eb589-131">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="eb589-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="eb589-132">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="eb589-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="eb589-133">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eb589-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb589-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="eb589-134">See also</span></span>
- [<span data-ttu-id="eb589-135">ICLRTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="eb589-135">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="eb589-136">ICLRTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="eb589-136">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="eb589-137">IHostTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="eb589-137">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="eb589-138">IHostTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="eb589-138">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
