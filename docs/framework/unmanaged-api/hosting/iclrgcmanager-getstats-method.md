---
title: ICLRGCManager::GetStats メソッド
ms.date: 03/30/2017
api_name:
- ICLRGCManager.GetStats
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRGCManager::GetStats
helpviewer_keywords:
- GetStats method, ICLRGCManager interface [.NET Framework hosting]
- ICLRGCManager::GetStats method [.NET Framework hosting]
ms.assetid: ce259d1d-cd81-4490-a7a1-0d0ea0804872
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 784a879b262008e1d999498fcbf4b43bb1137e24
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54674246"
---
# <a name="iclrgcmanagergetstats-method"></a><span data-ttu-id="fc199-102">ICLRGCManager::GetStats メソッド</span><span class="sxs-lookup"><span data-stu-id="fc199-102">ICLRGCManager::GetStats Method</span></span>
<span data-ttu-id="fc199-103">共通言語ランタイムのガベージ コレクション システムに関する現在の統計情報のセットを取得します。</span><span class="sxs-lookup"><span data-stu-id="fc199-103">Gets a set of current statistics about the common language runtime's garbage collection system.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc199-104">構文</span><span class="sxs-lookup"><span data-stu-id="fc199-104">Syntax</span></span>  
  
```  
HRESULT GetStats (  
    [in, out] COR_GC_STATS *pStats  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fc199-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="fc199-105">Parameters</span></span>  
 `pStats`  
 <span data-ttu-id="fc199-106">[入力、出力]A [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)要求の統計情報を格納しているインスタンス。</span><span class="sxs-lookup"><span data-stu-id="fc199-106">[in, out] A [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) instance that contains the requested statistics.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fc199-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="fc199-107">Return Value</span></span>  
  
|<span data-ttu-id="fc199-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="fc199-108">HRESULT</span></span>|<span data-ttu-id="fc199-109">説明</span><span class="sxs-lookup"><span data-stu-id="fc199-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="fc199-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="fc199-110">S_OK</span></span>|<span data-ttu-id="fc199-111">`GetStats` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="fc199-111">`GetStats` returned successfully.</span></span>|  
|<span data-ttu-id="fc199-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="fc199-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="fc199-113">共通言語ランタイム (CLR) は、プロセスに読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="fc199-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="fc199-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="fc199-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="fc199-115">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="fc199-115">The call timed out.</span></span>|  
|<span data-ttu-id="fc199-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="fc199-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="fc199-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="fc199-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="fc199-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="fc199-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="fc199-119">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="fc199-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="fc199-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="fc199-120">E_FAIL</span></span>|<span data-ttu-id="fc199-121">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="fc199-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="fc199-122">メソッドには、E_FAIL が返された、後に、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="fc199-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="fc199-123">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="fc199-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fc199-124">Remarks</span><span class="sxs-lookup"><span data-stu-id="fc199-124">Remarks</span></span>  
 <span data-ttu-id="fc199-125">CLR を計算しで指定されている統計情報のみを返す、`Flags`フィールド`pStats`します。</span><span class="sxs-lookup"><span data-stu-id="fc199-125">The CLR calculates and returns only those statistics that are specified by the `Flags` field of `pStats`.</span></span>  
  
 <span data-ttu-id="fc199-126">設定、`Flags`フィールドの 1 つまたは複数の値を[COR_GC_STAT_TYPES](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md)で統計情報を指定する列挙体、 [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)は、構造体を設定します。</span><span class="sxs-lookup"><span data-stu-id="fc199-126">Set the `Flags` field to one or more values of the [COR_GC_STAT_TYPES](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md) enumeration to specify which statistics in the [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) structure are to be set.</span></span>  
  
 <span data-ttu-id="fc199-127">使用状況の例は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="fc199-127">An example of the usage is as follows:</span></span>  
  
```  
COR_GC_STATS GCStats;  
GCStats.Flags = COR_GC_COUNTS | COR_GC_MEMORYUSAGE;  
pCLRGCManager->GetStats(&GCStats);  
```  
  
## <a name="requirements"></a><span data-ttu-id="fc199-128">必要条件</span><span class="sxs-lookup"><span data-stu-id="fc199-128">Requirements</span></span>  
 <span data-ttu-id="fc199-129">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="fc199-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fc199-130">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="fc199-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fc199-131">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="fc199-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fc199-132">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fc199-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc199-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="fc199-133">See also</span></span>
- [<span data-ttu-id="fc199-134">自動メモリ管理</span><span class="sxs-lookup"><span data-stu-id="fc199-134">Automatic Memory Management</span></span>](../../../../docs/standard/automatic-memory-management.md)
- [<span data-ttu-id="fc199-135">COR_GC_STATS 構造体</span><span class="sxs-lookup"><span data-stu-id="fc199-135">COR_GC_STATS Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)
- [<span data-ttu-id="fc199-136">COR_GC_STAT_TYPES 列挙型</span><span class="sxs-lookup"><span data-stu-id="fc199-136">COR_GC_STAT_TYPES Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md)
- [<span data-ttu-id="fc199-137">ガベージ コレクション</span><span class="sxs-lookup"><span data-stu-id="fc199-137">Garbage Collection</span></span>](../../../../docs/standard/garbage-collection/index.md)
- [<span data-ttu-id="fc199-138">ICLRControl インターフェイス</span><span class="sxs-lookup"><span data-stu-id="fc199-138">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="fc199-139">ICLRGCManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="fc199-139">ICLRGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md)
- [<span data-ttu-id="fc199-140">CLR ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="fc199-140">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)
- [<span data-ttu-id="fc199-141">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="fc199-141">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="fc199-142">ホスティング</span><span class="sxs-lookup"><span data-stu-id="fc199-142">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
