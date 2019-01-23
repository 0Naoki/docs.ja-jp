---
title: IHostTask::Start メソッド
ms.date: 03/30/2017
api_name:
- IHostTask.Start
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTask::Start
helpviewer_keywords:
- IHostTask::Start method [.NET Framework hosting]
- Start method, IHostTask interface [.NET Framework hosting]
ms.assetid: b18742b0-d8c4-401c-ae89-e6eccdaa81d0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ec781a4b51b425225339c08ec8fa194da1972462
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54625702"
---
# <a name="ihosttaskstart-method"></a><span data-ttu-id="f39ca-102">IHostTask::Start メソッド</span><span class="sxs-lookup"><span data-stu-id="f39ca-102">IHostTask::Start Method</span></span>
<span data-ttu-id="f39ca-103">ホストが現在によって表されるタスクを移動要求[IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)インスタンス、中断したからコードを実行できる、ライブの状態にします。</span><span class="sxs-lookup"><span data-stu-id="f39ca-103">Requests that the host move the task represented by the current [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance from a suspended to a live state, in which code can be executed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f39ca-104">構文</span><span class="sxs-lookup"><span data-stu-id="f39ca-104">Syntax</span></span>  
  
```  
HRESULT Start ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="f39ca-105">戻り値</span><span class="sxs-lookup"><span data-stu-id="f39ca-105">Return Value</span></span>  
  
|<span data-ttu-id="f39ca-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f39ca-106">HRESULT</span></span>|<span data-ttu-id="f39ca-107">説明</span><span class="sxs-lookup"><span data-stu-id="f39ca-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f39ca-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="f39ca-108">S_OK</span></span>|<span data-ttu-id="f39ca-109">開始は正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="f39ca-109">Start returned successfully.</span></span>|  
|<span data-ttu-id="f39ca-110">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f39ca-110">E_FAIL</span></span>|<span data-ttu-id="f39ca-111">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="f39ca-111">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f39ca-112">メソッドには、E_FAIL が返される、ときに、共通言語ランタイム (CLR) は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="f39ca-112">When a method returns E_FAIL, the common language runtime (CLR) is no longer usable within the process.</span></span> <span data-ttu-id="f39ca-113">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="f39ca-113">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f39ca-114">Remarks</span><span class="sxs-lookup"><span data-stu-id="f39ca-114">Remarks</span></span>  
 <span data-ttu-id="f39ca-115">`Start` 致命的な障害が発生した場合を除く、s_ok HRESULT 値を常に返します。</span><span class="sxs-lookup"><span data-stu-id="f39ca-115">`Start` always returns an HRESULT value of S_OK, except in cases where a catastrophic failure has occurred.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f39ca-116">必要条件</span><span class="sxs-lookup"><span data-stu-id="f39ca-116">Requirements</span></span>  
 <span data-ttu-id="f39ca-117">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f39ca-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f39ca-118">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f39ca-118">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f39ca-119">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="f39ca-119">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f39ca-120">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f39ca-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f39ca-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="f39ca-121">See also</span></span>
- [<span data-ttu-id="f39ca-122">ICLRTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f39ca-122">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="f39ca-123">ICLRTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f39ca-123">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="f39ca-124">IHostTask インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f39ca-124">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="f39ca-125">IHostTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f39ca-125">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
