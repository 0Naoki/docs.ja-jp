---
title: ICorRuntimeHost::Stop メソッド
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.Stop
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::Stop
helpviewer_keywords:
- Stop method, ICorRuntimeHost interface [.NET Framework hosting]
- ICorRuntimeHost::Stop method [.NET Framework hosting]
ms.assetid: 46a0d450-b516-4bef-8b71-8d3bf265cbed
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3c59a0c5ef1e89c2853a566bd3b587d15a1ed80c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59119263"
---
# <a name="icorruntimehoststop-method"></a><span data-ttu-id="119b7-102">ICorRuntimeHost::Stop メソッド</span><span class="sxs-lookup"><span data-stu-id="119b7-102">ICorRuntimeHost::Stop Method</span></span>
<span data-ttu-id="119b7-103">現在のプロセスの実行時にコードの実行を停止します。</span><span class="sxs-lookup"><span data-stu-id="119b7-103">Stops the execution of code in the runtime for the current process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="119b7-104">構文</span><span class="sxs-lookup"><span data-stu-id="119b7-104">Syntax</span></span>  
  
```  
HRESULT Stop ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="119b7-105">戻り値</span><span class="sxs-lookup"><span data-stu-id="119b7-105">Return Value</span></span>  
  
|<span data-ttu-id="119b7-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="119b7-106">HRESULT</span></span>|<span data-ttu-id="119b7-107">説明</span><span class="sxs-lookup"><span data-stu-id="119b7-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="119b7-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="119b7-108">S_OK</span></span>|<span data-ttu-id="119b7-109">操作が正常に完了しました。</span><span class="sxs-lookup"><span data-stu-id="119b7-109">The operation was successful.</span></span>|  
|<span data-ttu-id="119b7-110">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="119b7-110">S_FALSE</span></span>|<span data-ttu-id="119b7-111">操作を完了できませんでした。</span><span class="sxs-lookup"><span data-stu-id="119b7-111">The operation failed to complete.</span></span>|  
|<span data-ttu-id="119b7-112">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="119b7-112">E_FAIL</span></span>|<span data-ttu-id="119b7-113">未知の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="119b7-113">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="119b7-114">場合は、メソッドは、E_FAIL を返します、共通言語ランタイム (CLR) はプロセスで使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="119b7-114">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="119b7-115">Api をホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="119b7-115">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="119b7-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="119b7-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="119b7-117">プロセスに CLR が読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="119b7-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="119b7-118">Remarks</span><span class="sxs-lookup"><span data-stu-id="119b7-118">Remarks</span></span>  
 <span data-ttu-id="119b7-119">通常を呼び出す必要はありません、`Stop`メソッド、コードは、プロセスの終了時に実行が停止されるためです。</span><span class="sxs-lookup"><span data-stu-id="119b7-119">It is typically unnecessary to call the `Stop` method, because the code stops executing when the process exits.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="119b7-120">呼び出しの後に`Stop`CLR は、同じプロセスに再初期化することはできません。</span><span class="sxs-lookup"><span data-stu-id="119b7-120">After a call to `Stop`, the CLR cannot be reinitialized into the same process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="119b7-121">必要条件</span><span class="sxs-lookup"><span data-stu-id="119b7-121">Requirements</span></span>  
 <span data-ttu-id="119b7-122">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="119b7-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="119b7-123">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="119b7-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="119b7-124">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="119b7-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="119b7-125">**.NET framework のバージョン:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="119b7-125">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="119b7-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="119b7-126">See also</span></span>

- [<span data-ttu-id="119b7-127">ICorRuntimeHost インターフェイス</span><span class="sxs-lookup"><span data-stu-id="119b7-127">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
