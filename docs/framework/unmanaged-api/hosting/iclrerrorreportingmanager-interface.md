---
title: ICLRErrorReportingManager インターフェイス
ms.date: 03/30/2017
api_name:
- ICLRErrorReportingManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRErrorReportingManager
helpviewer_keywords:
- ICLRErrorReportingManager interface [.NET Framework hosting]
ms.assetid: ea8af0d5-4133-4472-8a1f-50570d7e85fa
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a20b79dd5eda9c431511cc49e7e3adaa9486b2aa
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59155988"
---
# <a name="iclrerrorreportingmanager-interface"></a><span data-ttu-id="7ca80-102">ICLRErrorReportingManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7ca80-102">ICLRErrorReportingManager Interface</span></span>
<span data-ttu-id="7ca80-103">エラー報告のカスタム スタック ダンプの構成をホストできるようにするメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="7ca80-103">Provides methods that allow the host to configure custom stack dumps for error reporting.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7ca80-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="7ca80-104">Methods</span></span>  
  
|<span data-ttu-id="7ca80-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="7ca80-105">Method</span></span>|<span data-ttu-id="7ca80-106">説明</span><span class="sxs-lookup"><span data-stu-id="7ca80-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7ca80-107">BeginCustomDump メソッド</span><span class="sxs-lookup"><span data-stu-id="7ca80-107">BeginCustomDump Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md)|<span data-ttu-id="7ca80-108">エラー報告のカスタム スタック ダンプの構成を指定します。</span><span class="sxs-lookup"><span data-stu-id="7ca80-108">Specifies the configuration of custom stack dumps for error reporting.</span></span>|  
|[<span data-ttu-id="7ca80-109">EndCustomDump メソッド</span><span class="sxs-lookup"><span data-stu-id="7ca80-109">EndCustomDump Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-endcustomdump-method.md)|<span data-ttu-id="7ca80-110">以前の呼び出しによって設定されたカスタム スタック ダンプ構成をクリアします`BeginCustomDump`します。</span><span class="sxs-lookup"><span data-stu-id="7ca80-110">Clears the custom stack dump configuration that was set by an earlier call to `BeginCustomDump`.</span></span>|  
|[<span data-ttu-id="7ca80-111">GetBucketParametersForCurrentException メソッド</span><span class="sxs-lookup"><span data-stu-id="7ca80-111">GetBucketParametersForCurrentException Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-getbucketparametersforcurrentexception-method.md)|<span data-ttu-id="7ca80-112">呼び出し元のスレッドで現在の例外のワトソン バケットを取得します。</span><span class="sxs-lookup"><span data-stu-id="7ca80-112">Gets the Watson bucket for the current exception on the calling thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7ca80-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="7ca80-113">Remarks</span></span>  
 <span data-ttu-id="7ca80-114">`BeginCustomDump`メソッドは、カスタムのスタック ダンプ構成を設定します。</span><span class="sxs-lookup"><span data-stu-id="7ca80-114">The `BeginCustomDump` method sets custom stack dump configuration.</span></span> <span data-ttu-id="7ca80-115">`EndCustomDump`メソッドは、カスタム スタック ダンプ構成をクリアし、関連付けられている状態を解放します。</span><span class="sxs-lookup"><span data-stu-id="7ca80-115">The `EndCustomDump` method clears the custom stack dump configuration and frees any associated state.</span></span> <span data-ttu-id="7ca80-116">これはカスタム ダンプの完了後に呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="7ca80-116">It should be called after the custom dump is complete.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="7ca80-117">呼び出しに失敗する`EndCustomDump`によりメモリ リークが発生します。</span><span class="sxs-lookup"><span data-stu-id="7ca80-117">Failure to call `EndCustomDump` causes memory to leak.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7ca80-118">必要条件</span><span class="sxs-lookup"><span data-stu-id="7ca80-118">Requirements</span></span>  
 <span data-ttu-id="7ca80-119">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7ca80-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7ca80-120">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="7ca80-120">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7ca80-121">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="7ca80-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7ca80-122">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7ca80-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ca80-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="7ca80-123">See also</span></span>

- [<span data-ttu-id="7ca80-124">ECustomDumpItemKind 列挙型</span><span class="sxs-lookup"><span data-stu-id="7ca80-124">ECustomDumpItemKind Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpitemkind-enumeration.md)
- [<span data-ttu-id="7ca80-125">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7ca80-125">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
