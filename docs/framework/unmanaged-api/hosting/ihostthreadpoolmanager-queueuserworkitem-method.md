---
title: IHostThreadPoolManager::QueueUserWorkItem メソッド
ms.date: 03/30/2017
api_name:
- IHostThreadPoolManager.QueueUserWorkItem
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostThreadPoolManager::QueueUserWorkItem
helpviewer_keywords:
- IHostThreadPoolManager::QueueUserWorkItem method [.NET Framework hosting]
- QueueUserWorkItem method [.NET Framework hosting]
ms.assetid: 41602053-8670-4827-9d61-cbfcba509b9c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 03185f3f554c5454b23b0c72c42d68714488e6be
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57501709"
---
# <a name="ihostthreadpoolmanagerqueueuserworkitem-method"></a><span data-ttu-id="cb6ca-102">IHostThreadPoolManager::QueueUserWorkItem メソッド</span><span class="sxs-lookup"><span data-stu-id="cb6ca-102">IHostThreadPoolManager::QueueUserWorkItem Method</span></span>
<span data-ttu-id="cb6ca-103">キューに入れ、実行するための関数をその関数によって使用されるデータを格納しているオブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="cb6ca-103">Queues a function for execution, and specifies an object containing data to be used by that function.</span></span> <span data-ttu-id="cb6ca-104">スレッドが利用可能になったら、関数を実行します。</span><span class="sxs-lookup"><span data-stu-id="cb6ca-104">The function executes when a thread becomes available.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb6ca-105">構文</span><span class="sxs-lookup"><span data-stu-id="cb6ca-105">Syntax</span></span>  
  
```  
HRESULT QueueUserWorkItem (  
    [in] LPTHREAD_START_ROUTINE Function,  
    [in] PVOID Context,  
    [in] ULONG Flags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cb6ca-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="cb6ca-106">Parameters</span></span>  
 `Function`  
 <span data-ttu-id="cb6ca-107">[in]実行する関数を表す関数ポインター。</span><span class="sxs-lookup"><span data-stu-id="cb6ca-107">[in] A function pointer that represents the function to execute.</span></span>  
  
 `Context`  
 <span data-ttu-id="cb6ca-108">[in]使用されるデータを格納しているオブジェクト`Function`します。</span><span class="sxs-lookup"><span data-stu-id="cb6ca-108">[in] An object that contains data to be used by `Function`.</span></span>  
  
 `Flags`  
 <span data-ttu-id="cb6ca-109">[in]Win32 定義されている、フラグのいずれかの値`QueueUserWorkItem`メソッドは、実行を制御します。</span><span class="sxs-lookup"><span data-stu-id="cb6ca-109">[in] One of the flags values, as defined for the Win32 `QueueUserWorkItem` method, that control execution.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cb6ca-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="cb6ca-110">Return Value</span></span>  
  
|<span data-ttu-id="cb6ca-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="cb6ca-111">HRESULT</span></span>|<span data-ttu-id="cb6ca-112">説明</span><span class="sxs-lookup"><span data-stu-id="cb6ca-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="cb6ca-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="cb6ca-113">S_OK</span></span>|<span data-ttu-id="cb6ca-114">`QueueUserWorkItem` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="cb6ca-114">`QueueUserWorkItem` returned successfully.</span></span>|  
|<span data-ttu-id="cb6ca-115">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="cb6ca-115">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="cb6ca-116">共通言語ランタイム (CLR) は、プロセスに読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="cb6ca-116">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="cb6ca-117">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="cb6ca-117">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="cb6ca-118">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="cb6ca-118">The call timed out.</span></span>|  
|<span data-ttu-id="cb6ca-119">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="cb6ca-119">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="cb6ca-120">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="cb6ca-120">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="cb6ca-121">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="cb6ca-121">HOST_E_ABANDONED</span></span>|<span data-ttu-id="cb6ca-122">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="cb6ca-122">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="cb6ca-123">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="cb6ca-123">E_FAIL</span></span>|<span data-ttu-id="cb6ca-124">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="cb6ca-124">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="cb6ca-125">メソッドには、E_FAIL が返される、ときに、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="cb6ca-125">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="cb6ca-126">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="cb6ca-126">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cb6ca-127">Remarks</span><span class="sxs-lookup"><span data-stu-id="cb6ca-127">Remarks</span></span>  
 <span data-ttu-id="cb6ca-128">`QueueUserWorkItem` スレッド プールのワーカー スレッドに作業項目をキューに入れます。</span><span class="sxs-lookup"><span data-stu-id="cb6ca-128">`QueueUserWorkItem` queues a work item to a worker thread in the thread pool.</span></span> <span data-ttu-id="cb6ca-129">その署名とパラメーターの型は、同じ名前を持つ、対応する Win32 関数のと同じです。</span><span class="sxs-lookup"><span data-stu-id="cb6ca-129">Its signature and parameter types are identical to those of the corresponding Win32 function, which has the same name.</span></span> <span data-ttu-id="cb6ca-130">詳細については、Windows プラットフォームのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cb6ca-130">For more information, see the Windows Platform documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cb6ca-131">必要条件</span><span class="sxs-lookup"><span data-stu-id="cb6ca-131">Requirements</span></span>  
 <span data-ttu-id="cb6ca-132">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cb6ca-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cb6ca-133">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="cb6ca-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="cb6ca-134">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="cb6ca-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cb6ca-135">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cb6ca-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb6ca-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="cb6ca-136">See also</span></span>
- <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A>
- <xref:System.Threading.ThreadPool>
- [<span data-ttu-id="cb6ca-137">IHostThreadPoolManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="cb6ca-137">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
