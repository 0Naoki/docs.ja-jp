---
title: IHostIoCompletionManager::GetHostOverlappedSize メソッド
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.GetHostOverlappedSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::GetHostOverlappedSize
helpviewer_keywords:
- IHostIoCompletionManager::GetHostOverlappedSize method [.NET Framework hosting]
- GetHostOverlappedSize method [.NET Framework hosting]
ms.assetid: 2902578b-d5e2-4f8d-a103-0c7b6dceda9e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e4a5661128765cc058417fef6373767d46a4bd7b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59111801"
---
# <a name="ihostiocompletionmanagergethostoverlappedsize-method"></a><span data-ttu-id="789c9-102">IHostIoCompletionManager::GetHostOverlappedSize メソッド</span><span class="sxs-lookup"><span data-stu-id="789c9-102">IHostIoCompletionManager::GetHostOverlappedSize Method</span></span>
<span data-ttu-id="789c9-103">ホストが I/O 要求に追加するカスタム データのサイズを取得します。</span><span class="sxs-lookup"><span data-stu-id="789c9-103">Gets the size of any custom data the host intends to append to I/O requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="789c9-104">構文</span><span class="sxs-lookup"><span data-stu-id="789c9-104">Syntax</span></span>  
  
```  
HRESULT GetHostOverlappedSize (  
    [out] DWORD *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="789c9-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="789c9-105">Parameters</span></span>  
 `pcbSize`  
 <span data-ttu-id="789c9-106">[out]共通言語ランタイム (CLR) は、Win32 のサイズだけでなく割り当てる必要がありますバイト数へのポインター`OVERLAPPED`オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="789c9-106">[out] A pointer to the number of bytes that the common language runtime (CLR) should allocate in addition to the size of the Win32 `OVERLAPPED` object.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="789c9-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="789c9-107">Return Value</span></span>  
  
|<span data-ttu-id="789c9-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="789c9-108">HRESULT</span></span>|<span data-ttu-id="789c9-109">説明</span><span class="sxs-lookup"><span data-stu-id="789c9-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="789c9-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="789c9-110">S_OK</span></span>|`GetHostOverlappedSize` <span data-ttu-id="789c9-111">正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="789c9-111">returned successfully.</span></span>|  
|<span data-ttu-id="789c9-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="789c9-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="789c9-113">プロセスに CLR が読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="789c9-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="789c9-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="789c9-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="789c9-115">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="789c9-115">The call timed out.</span></span>|  
|<span data-ttu-id="789c9-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="789c9-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="789c9-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="789c9-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="789c9-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="789c9-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="789c9-119">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="789c9-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="789c9-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="789c9-120">E_FAIL</span></span>|<span data-ttu-id="789c9-121">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="789c9-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="789c9-122">メソッドには、E_FAIL が返される、ときに、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="789c9-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="789c9-123">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="789c9-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="789c9-124">Remarks</span><span class="sxs-lookup"><span data-stu-id="789c9-124">Remarks</span></span>  
 <span data-ttu-id="789c9-125">Windows プラットフォーム Api に対するすべての非同期 I/O 呼び出しを Win32`OVERLAPPED`オブジェクトで、ファイル ポインターの位置などの情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="789c9-125">All asynchronous I/O calls to Windows Platform APIs take a Win32 `OVERLAPPED` object, which provides information such as the file pointer position.</span></span> <span data-ttu-id="789c9-126">状態を維持するには、通常非同期 I/O 呼び出しを実行するアプリケーションは、構造にカスタム データを追加します。</span><span class="sxs-lookup"><span data-stu-id="789c9-126">To maintain state, applications that make asynchronous I/O calls typically add custom data to the structure.</span></span> `GetHostOverlappedSize` <span data-ttu-id="789c9-127">[ihostiocompletionmanager::initializehostoverlapped](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-initializehostoverlapped-method.md)ホストをこのようなカスタム データを含む機会を提供します。</span><span class="sxs-lookup"><span data-stu-id="789c9-127">and [IHostIoCompletionManager::InitializeHostOverlapped](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-initializehostoverlapped-method.md) provide an opportunity for the host to include such custom data.</span></span>  
  
 <span data-ttu-id="789c9-128">CLR の呼び出し、`GetHostOverlappedSize`ホストによって追加されるカスタム データのサイズを決定するメソッド、`OVERLAPPED`オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="789c9-128">The CLR calls the `GetHostOverlappedSize` method to determine the size of the custom data that the host intends to append to the `OVERLAPPED` object.</span></span>  
  
> [!NOTE]
>  `GetHostOverlappedSize` <span data-ttu-id="789c9-129">1 回だけ呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="789c9-129">is called only once.</span></span> <span data-ttu-id="789c9-130">ホストのカスタム データは、すべての I/O 要求のサイズと同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="789c9-130">The host's custom data must be the same size for every I/O request.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="789c9-131">サイズ、`OVERLAPPED`オブジェクト自体がの値に含まれていない`pcbSize`します。</span><span class="sxs-lookup"><span data-stu-id="789c9-131">The size of the `OVERLAPPED` object itself is not included in the value of `pcbSize`.</span></span>  
  
 <span data-ttu-id="789c9-132">詳細については、`OVERLAPPED`構造体を Windows プラットフォームのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="789c9-132">For more information about the `OVERLAPPED` structure, see the Windows Platform documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="789c9-133">必要条件</span><span class="sxs-lookup"><span data-stu-id="789c9-133">Requirements</span></span>  
 <span data-ttu-id="789c9-134">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="789c9-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="789c9-135">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="789c9-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="789c9-136">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="789c9-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="789c9-137">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="789c9-137">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="789c9-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="789c9-138">See also</span></span>

- <xref:System.Threading.NativeOverlapped>
- [<span data-ttu-id="789c9-139">ICLRIoCompletionManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="789c9-139">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [<span data-ttu-id="789c9-140">IHostIoCompletionManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="789c9-140">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
