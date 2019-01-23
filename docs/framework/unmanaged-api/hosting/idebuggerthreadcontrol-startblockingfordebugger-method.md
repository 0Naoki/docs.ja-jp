---
title: IDebuggerThreadControl::StartBlockingForDebugger メソッド
ms.date: 03/30/2017
api_name:
- IDebuggerThreadControl.StartBlockingForDebugger
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- StartBlockingForDebugger
helpviewer_keywords:
- IDebuggerThreadControl::StartBlockingForDebugger method [.NET Framework hosting]
- StartBlockingForDebugger method [.NET Framework hosting]
ms.assetid: 5c8f11b4-35d3-4c39-9bbd-58b896ba5ba6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 746b61a303869ff03d41cd6005ca0f5635ac0fd5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54521722"
---
# <a name="idebuggerthreadcontrolstartblockingfordebugger-method"></a><span data-ttu-id="2e836-102">IDebuggerThreadControl::StartBlockingForDebugger メソッド</span><span class="sxs-lookup"><span data-stu-id="2e836-102">IDebuggerThreadControl::StartBlockingForDebugger Method</span></span>
<span data-ttu-id="2e836-103">デバッグ サービスがすべてのスレッドのブロックを開始しようとしていることをホストに通知します。</span><span class="sxs-lookup"><span data-stu-id="2e836-103">Notifies the host that the debugging services are about to start blocking all threads.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e836-104">構文</span><span class="sxs-lookup"><span data-stu-id="2e836-104">Syntax</span></span>  
  
```  
HRESULT StartBlockingForDebugger (  
    [in] DWORD dwUnused  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2e836-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2e836-105">Parameters</span></span>  
 `dwUnused`  
 <span data-ttu-id="2e836-106">[in]将来使用するために予約されています。</span><span class="sxs-lookup"><span data-stu-id="2e836-106">[in] Reserved for future use.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2e836-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="2e836-107">Remarks</span></span>  
 <span data-ttu-id="2e836-108">`StartBlockingForDebugger`ランタイムのスレッドでメソッドを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="2e836-108">The `StartBlockingForDebugger` method could be called on a runtime thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2e836-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="2e836-109">Requirements</span></span>  
 <span data-ttu-id="2e836-110">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2e836-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2e836-111">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2e836-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2e836-112">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="2e836-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2e836-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2e836-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e836-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="2e836-114">See also</span></span>
- [<span data-ttu-id="2e836-115">IDebuggerThreadControl インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2e836-115">IDebuggerThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-interface.md)
