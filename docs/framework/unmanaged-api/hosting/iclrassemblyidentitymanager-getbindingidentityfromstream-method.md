---
title: ICLRAssemblyIdentityManager::GetBindingIdentityFromStream メソッド
ms.date: 03/30/2017
api_name:
- ICLRAssemblyIdentityManager.GetBindingIdentityFromStream
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyIdentityManager::GetBindingIdentityFromStream
helpviewer_keywords:
- GetBindingIdentityFromStream method [.NET Framework hosting]
- ICLRAssemblyIdentityManager::GetBindingIdentityFromStream method [.NET Framework hosting]
ms.assetid: 40123b30-a589-46b3-95d3-af7b2b0baa05
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1b0f4b184a11e769291c64d83d11d57b5b3d19c7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54498805"
---
# <a name="iclrassemblyidentitymanagergetbindingidentityfromstream-method"></a><span data-ttu-id="94de7-102">ICLRAssemblyIdentityManager::GetBindingIdentityFromStream メソッド</span><span class="sxs-lookup"><span data-stu-id="94de7-102">ICLRAssemblyIdentityManager::GetBindingIdentityFromStream Method</span></span>
<span data-ttu-id="94de7-103">指定されたストリーム内のアセンブリの標準アセンブリの id データを取得します。</span><span class="sxs-lookup"><span data-stu-id="94de7-103">Gets the canonical assembly identity data for the assembly in the specified stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94de7-104">構文</span><span class="sxs-lookup"><span data-stu-id="94de7-104">Syntax</span></span>  
  
```  
HRESULT GetBindingIdentityFromStream (  
    [in] IStream    *pStream,  
    [in] DWORD       dwFlags,  
    [out, size_is(*pcchBufferSize)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBufferSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="94de7-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="94de7-105">Parameters</span></span>  
 `pStream`  
 <span data-ttu-id="94de7-106">[in]評価するアセンブリのストリーム。</span><span class="sxs-lookup"><span data-stu-id="94de7-106">[in] The assembly stream to be evaluated.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="94de7-107">[in]将来の機能拡張を提供します。</span><span class="sxs-lookup"><span data-stu-id="94de7-107">[in] Provided for future extensibility.</span></span> <span data-ttu-id="94de7-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT は、共通言語ランタイム (CLR) の現在のバージョンをサポートする唯一の値です。</span><span class="sxs-lookup"><span data-stu-id="94de7-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT is the only value that the current version of the common language runtime (CLR) supports.</span></span>  
  
 `pwzBuffer`  
 <span data-ttu-id="94de7-109">[out]非透過的なアセンブリの id データを格納するバッファー。</span><span class="sxs-lookup"><span data-stu-id="94de7-109">[out] A buffer containing the opaque assembly identity data.</span></span>  
  
 `pcchBufferSize`  
 <span data-ttu-id="94de7-110">[入力、出力]サイズ`pwzBuffer`します。</span><span class="sxs-lookup"><span data-stu-id="94de7-110">[in, out] The size of `pwzBuffer`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="94de7-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="94de7-111">Return Value</span></span>  
  
|<span data-ttu-id="94de7-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="94de7-112">HRESULT</span></span>|<span data-ttu-id="94de7-113">説明</span><span class="sxs-lookup"><span data-stu-id="94de7-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="94de7-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="94de7-114">S_OK</span></span>|<span data-ttu-id="94de7-115">メソッドが正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="94de7-115">The method returned successfully.</span></span>|  
|<span data-ttu-id="94de7-116">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="94de7-116">E_INVALIDARG</span></span>|<span data-ttu-id="94de7-117">指定された`pStream`が null です。</span><span class="sxs-lookup"><span data-stu-id="94de7-117">The supplied `pStream` is null.</span></span>|  
|<span data-ttu-id="94de7-118">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="94de7-118">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="94de7-119">サイズ`pwzBuffer`が小さすぎます。</span><span class="sxs-lookup"><span data-stu-id="94de7-119">The size of `pwzBuffer` is too small.</span></span>|  
|<span data-ttu-id="94de7-120">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="94de7-120">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="94de7-121">プロセスに CLR が読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="94de7-121">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="94de7-122">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="94de7-122">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="94de7-123">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="94de7-123">The call timed out.</span></span>|  
|<span data-ttu-id="94de7-124">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="94de7-124">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="94de7-125">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="94de7-125">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="94de7-126">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="94de7-126">HOST_E_ABANDONED</span></span>|<span data-ttu-id="94de7-127">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="94de7-127">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="94de7-128">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="94de7-128">E_FAIL</span></span>|<span data-ttu-id="94de7-129">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="94de7-129">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="94de7-130">メソッドから E_FAIL が返された場合、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="94de7-130">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="94de7-131">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="94de7-131">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="94de7-132">必要条件</span><span class="sxs-lookup"><span data-stu-id="94de7-132">Requirements</span></span>  
 <span data-ttu-id="94de7-133">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="94de7-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="94de7-134">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="94de7-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="94de7-135">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="94de7-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="94de7-136">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="94de7-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94de7-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="94de7-137">See also</span></span>
- [<span data-ttu-id="94de7-138">ICLRAssemblyIdentityManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="94de7-138">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="94de7-139">ICLRAssemblyReferenceList インターフェイス</span><span class="sxs-lookup"><span data-stu-id="94de7-139">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
