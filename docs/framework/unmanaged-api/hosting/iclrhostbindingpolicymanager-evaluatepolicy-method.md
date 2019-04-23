---
title: ICLRHostBindingPolicyManager::EvaluatePolicy メソッド
ms.date: 03/30/2017
api_name:
- ICLRHostBindingPolicyManager.EvaluatePolicy
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRHostBindingPolicyManager::EvaluatePolicy
helpviewer_keywords:
- ICLRHostBindingPolicyManager::EvaluatePolicy method [.NET Framework hosting]
- EvaluatePolicy method [.NET Framework hosting]
ms.assetid: 3a3a9446-7a4e-4836-9b27-5c536c15993d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ad7856a9376880f867e35f1e63bc2cac1ca216fa
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59130156"
---
# <a name="iclrhostbindingpolicymanagerevaluatepolicy-method"></a><span data-ttu-id="5e875-102">ICLRHostBindingPolicyManager::EvaluatePolicy メソッド</span><span class="sxs-lookup"><span data-stu-id="5e875-102">ICLRHostBindingPolicyManager::EvaluatePolicy Method</span></span>
<span data-ttu-id="5e875-103">ホストに代わってバインディング ポリシーを評価します。</span><span class="sxs-lookup"><span data-stu-id="5e875-103">Evaluates binding policy on behalf of the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5e875-104">構文</span><span class="sxs-lookup"><span data-stu-id="5e875-104">Syntax</span></span>  
  
```  
HRESULT EvaluatePolicy (  
    [in] LPCWSTR     pwzReferenceIdentity,  
    [in] BYTE       *pbApplicationPolicy,  
    [in] DWORD       cbAppPolicySize,  
    [out, size_is(*pcchPostPolicyReferenceIdentity)] LPWSTR pwzPostPolicyReferenceIdentity,  
    [in, out] DWORD *pcchPostPolicyReferenceIdentity,  
    [out] DWORD     *pdwPoliciesApplied  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5e875-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5e875-105">Parameters</span></span>  
 `pwzReferenceIdentity`  
 <span data-ttu-id="5e875-106">[in]ポリシーの評価する前にアセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="5e875-106">[in] A reference to the assembly before the policy evaluation.</span></span>  
  
 `pbApplicationPolicy`  
 <span data-ttu-id="5e875-107">[in]ポリシー データを格納しているバッファーへのポインター。</span><span class="sxs-lookup"><span data-stu-id="5e875-107">[in] A pointer to a buffer that contains the policy data.</span></span>  
  
 `cbAppPolicySize`  
 <span data-ttu-id="5e875-108">[in]サイズ、`pbApplicationPolicy`バッファー。</span><span class="sxs-lookup"><span data-stu-id="5e875-108">[in] The size of the `pbApplicationPolicy` buffer.</span></span>  
  
 `pwzPostPolicyReferenceIdentity`  
 <span data-ttu-id="5e875-109">[out]新しいポリシー データの評価した後、アセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="5e875-109">[out] A reference to the assembly after the evaluation of the new policy data.</span></span>  
  
 `pcchPostPolicyReferenceIdentity`  
 <span data-ttu-id="5e875-110">[入力、出力]新しいポリシー データの評価後アセンブリの id の参照をバッファーのサイズへのポインター。</span><span class="sxs-lookup"><span data-stu-id="5e875-110">[in, out] A pointer to the size of the assembly identity reference buffer after the evaluation of the new policy data.</span></span>  
  
 `pdwPoliciesApplied`  
 <span data-ttu-id="5e875-111">[out]論理 OR の組み合わせへのポインター [EBindPolicyLevels](../../../../docs/framework/unmanaged-api/hosting/ebindpolicylevels-enumeration.md)ポリシーが適用されていることを示す値。</span><span class="sxs-lookup"><span data-stu-id="5e875-111">[out] A pointer to a logical OR combination of [EBindPolicyLevels](../../../../docs/framework/unmanaged-api/hosting/ebindpolicylevels-enumeration.md) values, indicating which policies have been applied.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5e875-112">戻り値</span><span class="sxs-lookup"><span data-stu-id="5e875-112">Return Value</span></span>  
  
|<span data-ttu-id="5e875-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5e875-113">HRESULT</span></span>|<span data-ttu-id="5e875-114">説明</span><span class="sxs-lookup"><span data-stu-id="5e875-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5e875-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="5e875-115">S_OK</span></span>|<span data-ttu-id="5e875-116">評価が正常に完了しました。</span><span class="sxs-lookup"><span data-stu-id="5e875-116">The evaluation completed successfully.</span></span>|  
|<span data-ttu-id="5e875-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="5e875-117">E_INVALIDARG</span></span>|<span data-ttu-id="5e875-118">いずれか`pwzReferenceIdentity`または`pbApplicationPolicy`は null 参照です。</span><span class="sxs-lookup"><span data-stu-id="5e875-118">Either `pwzReferenceIdentity` or `pbApplicationPolicy` is a null reference.</span></span>|  
|<span data-ttu-id="5e875-119">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="5e875-119">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="5e875-120">`cbAppPolicySize` が小さすぎます。</span><span class="sxs-lookup"><span data-stu-id="5e875-120">`cbAppPolicySize` is too small.</span></span>|  
|<span data-ttu-id="5e875-121">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="5e875-121">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="5e875-122">共通言語ランタイム (CLR) は、プロセスに読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="5e875-122">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="5e875-123">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="5e875-123">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="5e875-124">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="5e875-124">The call timed out.</span></span>|  
|<span data-ttu-id="5e875-125">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="5e875-125">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="5e875-126">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="5e875-126">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="5e875-127">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="5e875-127">HOST_E_ABANDONED</span></span>|<span data-ttu-id="5e875-128">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="5e875-128">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="5e875-129">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="5e875-129">E_FAIL</span></span>|<span data-ttu-id="5e875-130">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="5e875-130">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="5e875-131">メソッドには、E_FAIL が返された、後に、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="5e875-131">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="5e875-132">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="5e875-132">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5e875-133">Remarks</span><span class="sxs-lookup"><span data-stu-id="5e875-133">Remarks</span></span>  
 <span data-ttu-id="5e875-134">`EvaluatePolicy`メソッドを使用するホスト固有のアセンブリを維持するためにバインディング ポリシーに影響を与えるホスト バージョン管理の要件。</span><span class="sxs-lookup"><span data-stu-id="5e875-134">The `EvaluatePolicy` method allows the host to influence binding policy to maintain host-specific assembly versioning requirements.</span></span> <span data-ttu-id="5e875-135">ポリシー エンジン自体は、CLR 内に残ります。</span><span class="sxs-lookup"><span data-stu-id="5e875-135">The policy engine itself remains inside the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5e875-136">必要条件</span><span class="sxs-lookup"><span data-stu-id="5e875-136">Requirements</span></span>  
 <span data-ttu-id="5e875-137">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5e875-137">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5e875-138">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="5e875-138">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5e875-139">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="5e875-139">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5e875-140">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5e875-140">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e875-141">関連項目</span><span class="sxs-lookup"><span data-stu-id="5e875-141">See also</span></span>

- [<span data-ttu-id="5e875-142">ICLRHostBindingPolicyManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5e875-142">ICLRHostBindingPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)
