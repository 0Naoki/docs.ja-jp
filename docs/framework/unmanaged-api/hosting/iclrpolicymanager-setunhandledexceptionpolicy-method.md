---
title: ICLRPolicyManager::SetUnhandledExceptionPolicy メソッド
ms.date: 03/30/2017
api_name:
- ICLRPolicyManager.SetUnhandledExceptionPolicy
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRPolicyManager::SetUnhandledExceptionPolicy
helpviewer_keywords:
- ICLRPolicyManager::SetUnhandledExceptionPolicy method [.NET Framework hosting]
- SetUnhandledExceptionPolicy method [.NET Framework hosting]
ms.assetid: 5268480e-280a-4931-b7a3-dc3ffdf7f78f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9f988084310b920907bb7f212e7d40ca0d1c91db
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59197517"
---
# <a name="iclrpolicymanagersetunhandledexceptionpolicy-method"></a><span data-ttu-id="d79ea-102">ICLRPolicyManager::SetUnhandledExceptionPolicy メソッド</span><span class="sxs-lookup"><span data-stu-id="d79ea-102">ICLRPolicyManager::SetUnhandledExceptionPolicy Method</span></span>
<span data-ttu-id="d79ea-103">ハンドルされない例外が発生したときに、共通言語ランタイム (CLR) の動作を指定します。</span><span class="sxs-lookup"><span data-stu-id="d79ea-103">Specifies the behavior of the common language runtime (CLR) when an unhandled exception occurs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d79ea-104">構文</span><span class="sxs-lookup"><span data-stu-id="d79ea-104">Syntax</span></span>  
  
```  
HRESULT SetUnhandledExceptionPolicy (  
    [in] EClrUnhandledExceptionPolicy policy  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d79ea-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d79ea-105">Parameters</span></span>  
 `policy`  
 <span data-ttu-id="d79ea-106">[in]1 つ、 [EClrUnhandledException](../../../../docs/framework/unmanaged-api/hosting/eclrunhandledexception-enumeration.md) CLR または、ホストによって動作が設定されているかどうかを示す値。</span><span class="sxs-lookup"><span data-stu-id="d79ea-106">[in] One of the [EClrUnhandledException](../../../../docs/framework/unmanaged-api/hosting/eclrunhandledexception-enumeration.md) values, indicating whether the behavior is set by the CLR or the host.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d79ea-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="d79ea-107">Return Value</span></span>  
  
|<span data-ttu-id="d79ea-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d79ea-108">HRESULT</span></span>|<span data-ttu-id="d79ea-109">説明</span><span class="sxs-lookup"><span data-stu-id="d79ea-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d79ea-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="d79ea-110">S_OK</span></span>|`SetUnhandledExceptionPolicy` <span data-ttu-id="d79ea-111">正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="d79ea-111">returned successfully.</span></span>|  
|<span data-ttu-id="d79ea-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d79ea-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d79ea-113">プロセスに CLR が読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="d79ea-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d79ea-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d79ea-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d79ea-115">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="d79ea-115">The call timed out.</span></span>|  
|<span data-ttu-id="d79ea-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d79ea-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d79ea-117">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="d79ea-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d79ea-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d79ea-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d79ea-119">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="d79ea-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d79ea-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d79ea-120">E_FAIL</span></span>|<span data-ttu-id="d79ea-121">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="d79ea-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d79ea-122">メソッドには、E_FAIL が返された、後に、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="d79ea-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d79ea-123">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="d79ea-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d79ea-124">Remarks</span><span class="sxs-lookup"><span data-stu-id="d79ea-124">Remarks</span></span>  
 <span data-ttu-id="d79ea-125">既定では、CLR は、すべてのハンドルされない例外、最後のハンドラーであり、その既定の動作はプロセスを破棄です。</span><span class="sxs-lookup"><span data-stu-id="d79ea-125">By default, the CLR is the final handler for all unhandled exceptions, and its default behavior is to tear down the process.</span></span> <span data-ttu-id="d79ea-126">ホストは設定してこの動作を変更することができます、 `policy` eHostDeterminedPolicy する値。</span><span class="sxs-lookup"><span data-stu-id="d79ea-126">The host can change this behavior by setting the `policy` value to eHostDeterminedPolicy.</span></span> <span data-ttu-id="d79ea-127">CLR の以前のバージョンと同じように、この値により、独自の既定の動作を実装するためにホストします。</span><span class="sxs-lookup"><span data-stu-id="d79ea-127">This value allows the host to implement its own default behavior, as with earlier versions of the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d79ea-128">必要条件</span><span class="sxs-lookup"><span data-stu-id="d79ea-128">Requirements</span></span>  
 <span data-ttu-id="d79ea-129">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d79ea-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d79ea-130">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d79ea-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d79ea-131">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="d79ea-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="d79ea-132">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="d79ea-132">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d79ea-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="d79ea-133">See also</span></span>

- [<span data-ttu-id="d79ea-134">EClrUnhandledException 列挙型</span><span class="sxs-lookup"><span data-stu-id="d79ea-134">EClrUnhandledException Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrunhandledexception-enumeration.md)
- [<span data-ttu-id="d79ea-135">ICLRControl インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d79ea-135">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="d79ea-136">ICLRPolicyManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d79ea-136">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [<span data-ttu-id="d79ea-137">IHostPolicyManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d79ea-137">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
