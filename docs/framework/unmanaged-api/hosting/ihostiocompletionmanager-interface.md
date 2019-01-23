---
title: IHostIoCompletionManager インターフェイス
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager
helpviewer_keywords:
- IHostIoCompletionManager interface [.NET Framework hosting]
ms.assetid: c28d1983-83f7-46e2-990f-dbb9dc07c818
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 186f5618cce7a70bc4fab55616a0f8b08025a81f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54542536"
---
# <a name="ihostiocompletionmanager-interface"></a><span data-ttu-id="33307-102">IHostIoCompletionManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="33307-102">IHostIoCompletionManager Interface</span></span>
<span data-ttu-id="33307-103">共通言語ランタイム (CLR) に、ホストによって提供される I/O 完了ポートとやり取りできるようにするメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="33307-103">Provides methods that allow the common language runtime (CLR) to interact with I/O completion ports provided by the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="33307-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="33307-104">Methods</span></span>  
  
|<span data-ttu-id="33307-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="33307-105">Method</span></span>|<span data-ttu-id="33307-106">説明</span><span class="sxs-lookup"><span data-stu-id="33307-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="33307-107">Bind メソッド</span><span class="sxs-lookup"><span data-stu-id="33307-107">Bind Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md)|<span data-ttu-id="33307-108">I/O 完了ポートへのハンドルにバインドします。</span><span class="sxs-lookup"><span data-stu-id="33307-108">Binds a handle to an I/O completion port.</span></span>|  
|[<span data-ttu-id="33307-109">CloseIoCompletionPort メソッド</span><span class="sxs-lookup"><span data-stu-id="33307-109">CloseIoCompletionPort Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-closeiocompletionport-method.md)|<span data-ttu-id="33307-110">以前の呼び出しを使用して作成されたポートを閉じる`CreateIoCompletionPort`します。</span><span class="sxs-lookup"><span data-stu-id="33307-110">Closes a port that was created through an earlier call to `CreateIoCompletionPort`.</span></span>|  
|[<span data-ttu-id="33307-111">CreateIoCompletionPort メソッド</span><span class="sxs-lookup"><span data-stu-id="33307-111">CreateIoCompletionPort Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-createiocompletionport-method.md)|<span data-ttu-id="33307-112">ホストが新しい I/O 完了ポートを作成することを要求します。</span><span class="sxs-lookup"><span data-stu-id="33307-112">Requests that the host create a new I/O completion port.</span></span>|  
|[<span data-ttu-id="33307-113">GetAvailableThreads メソッド</span><span class="sxs-lookup"><span data-stu-id="33307-113">GetAvailableThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-getavailablethreads-method.md)|<span data-ttu-id="33307-114">現在の要求を処理していない I/O 完了スレッドの数を取得します。</span><span class="sxs-lookup"><span data-stu-id="33307-114">Gets the number of I/O completion threads that are not currently processing requests.</span></span>|  
|[<span data-ttu-id="33307-115">GetHostOverlappedSize メソッド</span><span class="sxs-lookup"><span data-stu-id="33307-115">GetHostOverlappedSize Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-gethostoverlappedsize-method.md)|<span data-ttu-id="33307-116">ホストが I/O 要求に追加するカスタム データのサイズを取得します。</span><span class="sxs-lookup"><span data-stu-id="33307-116">Gets the size of any custom data the host intends to append to I/O requests.</span></span>|  
|[<span data-ttu-id="33307-117">GetMaxThreads メソッド</span><span class="sxs-lookup"><span data-stu-id="33307-117">GetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-getmaxthreads-method.md)|<span data-ttu-id="33307-118">I/O 要求を処理するには、ホストに割り当てることができますのスレッドの最大数を取得します。</span><span class="sxs-lookup"><span data-stu-id="33307-118">Gets the maximum number of threads that the host can allot to service I/O requests.</span></span>|  
|[<span data-ttu-id="33307-119">GetMinThreads メソッド</span><span class="sxs-lookup"><span data-stu-id="33307-119">GetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-getminthreads-method.md)|<span data-ttu-id="33307-120">I/O 要求を処理するには、ホストを提供するスレッドの最小数を取得します。</span><span class="sxs-lookup"><span data-stu-id="33307-120">Gets the minimum number of threads that the host provides to service I/O requests.</span></span>|  
|[<span data-ttu-id="33307-121">InitializeHostOverlapped メソッド</span><span class="sxs-lookup"><span data-stu-id="33307-121">InitializeHostOverlapped Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-initializehostoverlapped-method.md)|<span data-ttu-id="33307-122">ホストを I/O 要求に関するすべてのカスタム データを初期化する機会を提供します。</span><span class="sxs-lookup"><span data-stu-id="33307-122">Provides the host with an opportunity to initialize any custom data about an I/O request.</span></span>|  
|[<span data-ttu-id="33307-123">SetCLRIoCompletionManager メソッド</span><span class="sxs-lookup"><span data-stu-id="33307-123">SetCLRIoCompletionManager Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-setclriocompletionmanager-method.md)|<span data-ttu-id="33307-124">により、ホストへのインターフェイス ポインターで、 [ICLRIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md) CLR で実装されているインスタンス。</span><span class="sxs-lookup"><span data-stu-id="33307-124">Provides the host with an interface pointer to an [ICLRIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md) instance implemented by the CLR.</span></span>|  
|[<span data-ttu-id="33307-125">SetMaxThreads メソッド</span><span class="sxs-lookup"><span data-stu-id="33307-125">SetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-setmaxthreads-method.md)|<span data-ttu-id="33307-126">I/O 要求を処理するため、ホストに割り当てるスレッドの最大数を設定します。</span><span class="sxs-lookup"><span data-stu-id="33307-126">Sets the maximum number of threads that the host allots to service I/O requests.</span></span>|  
|[<span data-ttu-id="33307-127">SetMinThreads メソッド</span><span class="sxs-lookup"><span data-stu-id="33307-127">SetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-setminthreads-method.md)|<span data-ttu-id="33307-128">I/O 完了するには、ホストを割り当てるスレッドの最小数を設定します。</span><span class="sxs-lookup"><span data-stu-id="33307-128">Sets the minimum number of threads that the host should allot to I/O completion.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="33307-129">Remarks</span><span class="sxs-lookup"><span data-stu-id="33307-129">Remarks</span></span>  
 <span data-ttu-id="33307-130">`IHostIoCompletionManager` 対応する、 `ICLRIoCompletionManager` CLR によって実装されるインターフェイス。</span><span class="sxs-lookup"><span data-stu-id="33307-130">`IHostIoCompletionManager` corresponds to the `ICLRIoCompletionManager` interface implemented by the CLR.</span></span> <span data-ttu-id="33307-131">CLR のメソッドを呼び出して、`IHostIoCompletionManager`ハンドルをホストを提供して、ホストのメソッドを呼び出すポートにバインドする`ICLRIoCompletionManager`I/O 要求の完了を報告します。</span><span class="sxs-lookup"><span data-stu-id="33307-131">The CLR calls the methods of `IHostIoCompletionManager` to bind handles to the ports that the host provides, and the host calls the methods of `ICLRIoCompletionManager` to report the completion of I/O requests.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="33307-132">必要条件</span><span class="sxs-lookup"><span data-stu-id="33307-132">Requirements</span></span>  
 <span data-ttu-id="33307-133">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="33307-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="33307-134">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="33307-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="33307-135">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="33307-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="33307-136">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="33307-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33307-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="33307-137">See also</span></span>
- [<span data-ttu-id="33307-138">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="33307-138">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
