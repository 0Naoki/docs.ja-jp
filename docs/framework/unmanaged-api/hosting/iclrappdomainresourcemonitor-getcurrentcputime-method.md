---
title: ICLRAppDomainResourceMonitor::GetCurrentCpuTime メソッド
ms.date: 03/30/2017
api_name:
- ICLRAppDomainResourceMonitor.GetCurrentCpuTime
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAppDomainResourceMonitor::GetCurrentCpuTime
helpviewer_keywords:
- ICLRAppDomainResourceMonitor::GetCurrentCpuTime method [.NET Framework hosting]
- GetCurrentCpuTime method [.NET Framework hosting]
ms.assetid: ebc9cc33-fcd6-4cae-9ecb-ea21c51874e6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8022428c7f803f96e2fa150588edf95542bf19b3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59169859"
---
# <a name="iclrappdomainresourcemonitorgetcurrentcputime-method"></a><span data-ttu-id="64dcd-102">ICLRAppDomainResourceMonitor::GetCurrentCpuTime メソッド</span><span class="sxs-lookup"><span data-stu-id="64dcd-102">ICLRAppDomainResourceMonitor::GetCurrentCpuTime Method</span></span>
<span data-ttu-id="64dcd-103">アプリケーション ドメインが作成されたために、現在のアプリケーション ドメインで実行中にすべてのスレッドによって使用されているプロセッサの合計時間を取得します。</span><span class="sxs-lookup"><span data-stu-id="64dcd-103">Gets the total processor time that has been used by all threads while executing in the current application domain, since the application domain was created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64dcd-104">構文</span><span class="sxs-lookup"><span data-stu-id="64dcd-104">Syntax</span></span>  
  
```  
HRESULT GetCurrentCpuTime([in]  DWORD dwAppDomainId,  
                          [out] ULONGLONG* pMilliseconds);  
```  
  
## <a name="parameters"></a><span data-ttu-id="64dcd-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="64dcd-105">Parameters</span></span>  
 `dwAppDomainId`  
 <span data-ttu-id="64dcd-106">[in]要求されたアプリケーション ドメインの ID。</span><span class="sxs-lookup"><span data-stu-id="64dcd-106">[in] The ID of the requested application domain.</span></span>  
  
 `pMilliseconds`  
 <span data-ttu-id="64dcd-107">[out]アプリケーション ドメインが作成されたために、現在のアプリケーション ドメインで実行中にすべてのスレッドによって使用されているプロセッサの合計時間へのポインター。</span><span class="sxs-lookup"><span data-stu-id="64dcd-107">[out] A pointer to the total processor time that has been used by all threads while executing in the current application domain since the application domain was created.</span></span> <span data-ttu-id="64dcd-108">このパラメーターは、`null` に設定できます。</span><span class="sxs-lookup"><span data-stu-id="64dcd-108">This parameter can be `null`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="64dcd-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="64dcd-109">Return Value</span></span>  
  
|<span data-ttu-id="64dcd-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="64dcd-110">HRESULT</span></span>|<span data-ttu-id="64dcd-111">説明</span><span class="sxs-lookup"><span data-stu-id="64dcd-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="64dcd-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="64dcd-112">S_OK</span></span>|<span data-ttu-id="64dcd-113">メソッドは正常に完了しました。</span><span class="sxs-lookup"><span data-stu-id="64dcd-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="64dcd-114">COR_E_APPDOMAINUNLOADED</span><span class="sxs-lookup"><span data-stu-id="64dcd-114">COR_E_APPDOMAINUNLOADED</span></span>|<span data-ttu-id="64dcd-115">アプリケーション ドメインがアンロードされたか、存在しません。</span><span class="sxs-lookup"><span data-stu-id="64dcd-115">The application domain has been unloaded or does not exist.</span></span>|  
|<span data-ttu-id="64dcd-116">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="64dcd-116">E_FAIL</span></span>|<span data-ttu-id="64dcd-117">アプリケーション ドメインのリソース監視が有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="64dcd-117">Application domain resource monitoring is not enabled.</span></span><br /><br /> <span data-ttu-id="64dcd-118">- または -</span><span class="sxs-lookup"><span data-stu-id="64dcd-118">-or-</span></span><br /><br /> <span data-ttu-id="64dcd-119">その他のすべてのエラー。</span><span class="sxs-lookup"><span data-stu-id="64dcd-119">All other failures.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="64dcd-120">Remarks</span><span class="sxs-lookup"><span data-stu-id="64dcd-120">Remarks</span></span>  
 <span data-ttu-id="64dcd-121">このメソッドはアンマネージと同等のマネージ<xref:System.AppDomain.MonitoringTotalProcessorTime%2A?displayProperty=nameWithType>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="64dcd-121">This method is the unmanaged equivalent of the managed <xref:System.AppDomain.MonitoringTotalProcessorTime%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="64dcd-122">必要条件</span><span class="sxs-lookup"><span data-stu-id="64dcd-122">Requirements</span></span>  
 <span data-ttu-id="64dcd-123">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="64dcd-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="64dcd-124">**ヘッダー:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="64dcd-124">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="64dcd-125">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="64dcd-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="64dcd-126">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="64dcd-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64dcd-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="64dcd-127">See also</span></span>

- [<span data-ttu-id="64dcd-128">ICLRAppDomainResourceMonitor インターフェイス</span><span class="sxs-lookup"><span data-stu-id="64dcd-128">ICLRAppDomainResourceMonitor Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md)
- [<span data-ttu-id="64dcd-129">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="64dcd-129">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="64dcd-130">アプリケーション ドメインのリソース監視</span><span class="sxs-lookup"><span data-stu-id="64dcd-130">Application Domain Resource Monitoring</span></span>](../../../../docs/standard/garbage-collection/app-domain-resource-monitoring.md)
- [<span data-ttu-id="64dcd-131">ホスティング</span><span class="sxs-lookup"><span data-stu-id="64dcd-131">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
