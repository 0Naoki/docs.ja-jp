---
title: IHostAutoEvent インターフェイス
ms.date: 03/30/2017
api_name:
- IHostAutoEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAutoEvent
helpviewer_keywords:
- IHostAutoEvent interface [.NET Framework hosting]
ms.assetid: 6c1d15c1-a80a-4ee9-b1e4-6e859db6575a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fb5fea403f8210ea93d240aa3aabd4325524b987
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59080944"
---
# <a name="ihostautoevent-interface"></a><span data-ttu-id="c0157-102">IHostAutoEvent インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c0157-102">IHostAutoEvent Interface</span></span>
<span data-ttu-id="c0157-103">ホストの自動リセット イベントの実装の表現を提供します。</span><span class="sxs-lookup"><span data-stu-id="c0157-103">Provides a representation of the host's implementation of an auto-reset event.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c0157-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="c0157-104">Methods</span></span>  
  
|<span data-ttu-id="c0157-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="c0157-105">Method</span></span>|<span data-ttu-id="c0157-106">説明</span><span class="sxs-lookup"><span data-stu-id="c0157-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c0157-107">Set メソッド</span><span class="sxs-lookup"><span data-stu-id="c0157-107">Set Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-set-method.md)|<span data-ttu-id="c0157-108">現在の設定`IHostAutoEvent`インスタンスがシグナル状態にします。</span><span class="sxs-lookup"><span data-stu-id="c0157-108">Sets the current `IHostAutoEvent` instance to a signaled state.</span></span>|  
|[<span data-ttu-id="c0157-109">Wait メソッド</span><span class="sxs-lookup"><span data-stu-id="c0157-109">Wait Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-wait-method.md)|<span data-ttu-id="c0157-110">現在`IHostAutoEvent`イベントを所有するまで待機するインスタンスまたは一定の時間が経過するとします。</span><span class="sxs-lookup"><span data-stu-id="c0157-110">Causes the current `IHostAutoEvent` instance to wait until the event is owned or a specified amount of time elapses.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c0157-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="c0157-111">Requirements</span></span>  
 <span data-ttu-id="c0157-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c0157-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c0157-113">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c0157-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c0157-114">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="c0157-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c0157-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c0157-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0157-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="c0157-116">See also</span></span>

- [<span data-ttu-id="c0157-117">ICLRSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c0157-117">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="c0157-118">IHostManualEvent インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c0157-118">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="c0157-119">IHostSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c0157-119">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
- [<span data-ttu-id="c0157-120">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c0157-120">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
