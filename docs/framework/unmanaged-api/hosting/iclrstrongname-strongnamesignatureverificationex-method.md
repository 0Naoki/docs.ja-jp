---
title: ICLRStrongName::StrongNameSignatureVerificationEx メソッド
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameSignatureVerificationEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameSignatureVerificationEx
helpviewer_keywords:
- StrongNameSignatureVerificationEx method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameSignatureVerificationEx method [.NET Framework hosting]
ms.assetid: dbd2f662-208b-4174-b301-5c99af91040f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: da9b0fd4fd7c7eadf09f0b76a17e60b1840fdf48
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2018
ms.locfileid: "43804907"
---
# <a name="iclrstrongnamestrongnamesignatureverificationex-method"></a><span data-ttu-id="d60ac-102">ICLRStrongName::StrongNameSignatureVerificationEx メソッド</span><span class="sxs-lookup"><span data-stu-id="d60ac-102">ICLRStrongName::StrongNameSignatureVerificationEx Method</span></span>
<span data-ttu-id="d60ac-103">指定されたパスにあるアセンブリ マニフェストが厳密な名前の署名を含むかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="d60ac-103">Gets a value that indicates whether the assembly manifest at the supplied path contains a strong name signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d60ac-104">構文</span><span class="sxs-lookup"><span data-stu-id="d60ac-104">Syntax</span></span>  
  
```  
HRESULT StrongNameSignatureVerificationEx (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  BOOLEAN   fForceVerification,  
    [out] BOOLEAN   *pfWasVerified  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d60ac-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d60ac-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="d60ac-106">[in]検証するアセンブリのポータブル実行可能 (.exe または .dll) ファイルへのパス。</span><span class="sxs-lookup"><span data-stu-id="d60ac-106">[in] The path to the portable executable (.exe or .dll) file for the assembly to be verified.</span></span>  
  
 `fForceVerification`  
 <span data-ttu-id="d60ac-107">[in]`true` 。 それ以外のレジストリ設定を上書きする必要がある場合でも、検証を実行する`false`します。</span><span class="sxs-lookup"><span data-stu-id="d60ac-107">[in] `true` to perform verification, even if it is necessary to override registry settings; otherwise, `false`.</span></span>  
  
 `pfWasVerified`  
 <span data-ttu-id="d60ac-108">[out]`true` 、厳密な名前の署名が確認済み。 それ以外の場合`false`します。</span><span class="sxs-lookup"><span data-stu-id="d60ac-108">[out] `true` if the strong name signature was verified; otherwise, `false`.</span></span> <span data-ttu-id="d60ac-109">`pfWasVerified` 設定されても`false`検証がレジストリ設定により成功した場合。</span><span class="sxs-lookup"><span data-stu-id="d60ac-109">`pfWasVerified` is also set to `false` if the verification was successful due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d60ac-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="d60ac-110">Return Value</span></span>  
 <span data-ttu-id="d60ac-111">`S_OK` 検証が成功した場合それ以外の場合、エラーを示す HRESULT 値 (を参照してください[の共通 HRESULT 値](https://go.microsoft.com/fwlink/?LinkId=213878)一覧については)。</span><span class="sxs-lookup"><span data-stu-id="d60ac-111">`S_OK` if the verification was successful; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d60ac-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="d60ac-112">Remarks</span></span>  
 <span data-ttu-id="d60ac-113">[Iclrstrongname::strongnamesignatureverificationex](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md)メソッドと似た機能を提供する、 [iclrstrongname::strongnamesignatureverification](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="d60ac-113">The [ICLRStrongName::StrongNameSignatureVerificationEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md) method provides a capability similar to the [ICLRStrongName::StrongNameSignatureVerification](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md) method.</span></span> <span data-ttu-id="d60ac-114">2 番目の入力パラメーターと出力パラメーター、 [iclrstrongname::strongnamesignatureverificationex](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md)型`BOOLEAN`の代わりに`DWORD`します。</span><span class="sxs-lookup"><span data-stu-id="d60ac-114">However, the second input parameter and the output parameter for [ICLRStrongName::StrongNameSignatureVerificationEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md) are of type `BOOLEAN` instead of `DWORD`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d60ac-115">要件</span><span class="sxs-lookup"><span data-stu-id="d60ac-115">Requirements</span></span>  
 <span data-ttu-id="d60ac-116">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d60ac-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d60ac-117">**ヘッダー:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="d60ac-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="d60ac-118">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="d60ac-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d60ac-119">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d60ac-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d60ac-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="d60ac-120">See Also</span></span>  
 [<span data-ttu-id="d60ac-121">StrongNameSignatureVerification メソッド</span><span class="sxs-lookup"><span data-stu-id="d60ac-121">StrongNameSignatureVerification Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md)  
 [<span data-ttu-id="d60ac-122">ICLRStrongName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d60ac-122">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
