---
title: IHostTaskManager::GetStackGuarantee メソッド
ms.date: 03/30/2017
api_name:
- IHostTaskManager.GetStackGuarantee
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::GetStackGuarantee
helpviewer_keywords:
- GetStackGuarantee method [.NET Framework hosting]
- IHostTaskManager::GetStackGuarantee method [.NET Framework hosting]
ms.assetid: 8176d732-c25c-4520-811d-e3310f339947
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 100bb73356379d2f251513bbbed0cf1e90752ff5
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57494374"
---
# <a name="ihosttaskmanagergetstackguarantee-method"></a><span data-ttu-id="2c8bb-102">IHostTaskManager::GetStackGuarantee メソッド</span><span class="sxs-lookup"><span data-stu-id="2c8bb-102">IHostTaskManager::GetStackGuarantee Method</span></span>
<span data-ttu-id="2c8bb-103">プロセスの終了前に、スタック操作の完了後に、使用することが保証されるスタック領域の量を取得します。</span><span class="sxs-lookup"><span data-stu-id="2c8bb-103">Gets the amount of stack space that is guaranteed to be available after a stack operation completes, but before the closing of a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c8bb-104">構文</span><span class="sxs-lookup"><span data-stu-id="2c8bb-104">Syntax</span></span>  
  
```  
HRESULT GetStackGuarantee(  
    [out] ULONG *pGuarantee  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2c8bb-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2c8bb-105">Parameters</span></span>  
 `pGuarantee`  
 <span data-ttu-id="2c8bb-106">[out]使用できるバイト数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="2c8bb-106">[out] A pointer to the number of bytes that are available.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2c8bb-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="2c8bb-107">Requirements</span></span>  
 <span data-ttu-id="2c8bb-108">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2c8bb-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2c8bb-109">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2c8bb-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2c8bb-110">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="2c8bb-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2c8bb-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2c8bb-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c8bb-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="2c8bb-112">See also</span></span>
- [<span data-ttu-id="2c8bb-113">IHostTaskManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2c8bb-113">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
