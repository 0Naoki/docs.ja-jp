---
title: ICLRIoCompletionManager インターフェイス
ms.date: 03/30/2017
api_name:
- ICLRIoCompletionManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRIoCompletionManager
helpviewer_keywords:
- ICLRIoCompletionManager interface [.NET Framework hosting]
ms.assetid: c6c3ace6-e5e7-4450-8cc5-a9a48208c493
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7864bb81c3b457bf8ec07cd194d24b29a42bd441
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59156066"
---
# <a name="iclriocompletionmanager-interface"></a><span data-ttu-id="4c402-102">ICLRIoCompletionManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4c402-102">ICLRIoCompletionManager Interface</span></span>
<span data-ttu-id="4c402-103">実装により、指定した I/O の状態のホストが共通言語ランタイム (CLR) に通知するコールバック メソッドを要求します。</span><span class="sxs-lookup"><span data-stu-id="4c402-103">Implements a callback method that allows the host to notify the common language runtime (CLR) of the status of specified I/O requests.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4c402-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="4c402-104">Methods</span></span>  
  
|<span data-ttu-id="4c402-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="4c402-105">Method</span></span>|<span data-ttu-id="4c402-106">説明</span><span class="sxs-lookup"><span data-stu-id="4c402-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4c402-107">OnComplete メソッド</span><span class="sxs-lookup"><span data-stu-id="4c402-107">OnComplete Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md)|<span data-ttu-id="4c402-108">呼び出しを使用して作成された I/O 要求の状態の CLR に通知、 [ihostiocompletionmanager::bind](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="4c402-108">Notifies the CLR of the status of an I/O request that was made by using a call to the [IHostIoCompletionManager::Bind](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md) method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4c402-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="4c402-109">Remarks</span></span>  
 <span data-ttu-id="4c402-110">ホストを使用して、I/O 完了の抽象化を実装する、 [IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="4c402-110">The host implements the I/O completion abstraction by using the [IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md) interface.</span></span> <span data-ttu-id="4c402-111">CLR は、このインターフェイスでは、I/O 要求を行うし、ホストを使用してこのような要求の結果をランタイムに通知、`ICLRIoCompletionManager`インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="4c402-111">The CLR makes I/O requests through this interface, and the host notifies the runtime of the outcome of such requests by using the `ICLRIoCompletionManager` interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4c402-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="4c402-112">Requirements</span></span>  
 <span data-ttu-id="4c402-113">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4c402-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4c402-114">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="4c402-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4c402-115">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="4c402-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="4c402-116">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="4c402-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="4c402-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="4c402-117">See also</span></span>

- [<span data-ttu-id="4c402-118">IHostIoCompletionManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4c402-118">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
- [<span data-ttu-id="4c402-119">IHostThreadPoolManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4c402-119">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
- [<span data-ttu-id="4c402-120">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4c402-120">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
