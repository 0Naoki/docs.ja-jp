---
title: StrongNameSignatureVerificationEx 関数
ms.date: 03/30/2017
api_name:
- StrongNameSignatureVerificationEx
api_location:
- mscoree.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameSignatureVerificationEx
helpviewer_keywords:
- StrongNameSignatureVerificationEx function [.NET Framework strong naming]
ms.assetid: cfe4b634-18bf-44b8-9773-d94fb7e8a480
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a9887a05236b213fb439e334cdf1455f8f445e7e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54671929"
---
# <a name="strongnamesignatureverificationex-function"></a><span data-ttu-id="af5ec-102">StrongNameSignatureVerificationEx 関数</span><span class="sxs-lookup"><span data-stu-id="af5ec-102">StrongNameSignatureVerificationEx Function</span></span>
<span data-ttu-id="af5ec-103">指定したパスにあるアセンブリ マニフェストに厳密な名前の署名が含まれるかどうかを示す値が取得されます。</span><span class="sxs-lookup"><span data-stu-id="af5ec-103">Gets a value indicating whether the assembly manifest at the supplied path contains a strong name signature.</span></span>  
  
 <span data-ttu-id="af5ec-104">この関数は非推奨とされました。</span><span class="sxs-lookup"><span data-stu-id="af5ec-104">This function has been deprecated.</span></span> <span data-ttu-id="af5ec-105">使用して、 [iclrstrongname::strongnamesignatureverificationex](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md)メソッド代わりにします。</span><span class="sxs-lookup"><span data-stu-id="af5ec-105">Use the [ICLRStrongName::StrongNameSignatureVerificationEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af5ec-106">構文</span><span class="sxs-lookup"><span data-stu-id="af5ec-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameSignatureVerificationEx (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  BOOLEAN   fForceVerification,  
    [out] BOOLEAN   *pfWasVerified  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="af5ec-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="af5ec-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="af5ec-108">[in]検証するアセンブリのポータブル実行可能 (.exe または .dll) ファイルへのパス。</span><span class="sxs-lookup"><span data-stu-id="af5ec-108">[in] The path to the portable executable (.exe or .dll) file for the assembly to be verified.</span></span>  
  
 `fForceVerification`  
 <span data-ttu-id="af5ec-109">[in]`true` 。 それ以外のレジストリ設定を上書きする必要がある場合でも、検証を実行する`false`します。</span><span class="sxs-lookup"><span data-stu-id="af5ec-109">[in] `true` to perform verification, even if it is necessary to override registry settings; otherwise, `false`.</span></span>  
  
 `pfWasVerified`  
 <span data-ttu-id="af5ec-110">[out]`true` 、厳密な名前の署名が確認済み。 それ以外の場合`false`します。</span><span class="sxs-lookup"><span data-stu-id="af5ec-110">[out] `true` if the strong name signature was verified; otherwise, `false`.</span></span> <span data-ttu-id="af5ec-111">`pfWasVerified` 設定されても`false`検証がレジストリ設定により成功した場合。</span><span class="sxs-lookup"><span data-stu-id="af5ec-111">`pfWasVerified` is also set to `false` if the verification was successful due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="af5ec-112">戻り値</span><span class="sxs-lookup"><span data-stu-id="af5ec-112">Return Value</span></span>  
 <span data-ttu-id="af5ec-113">`true` 検証が成功した場合それ以外の場合、`false`します。</span><span class="sxs-lookup"><span data-stu-id="af5ec-113">`true` if the verification was successful; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="af5ec-114">Remarks</span><span class="sxs-lookup"><span data-stu-id="af5ec-114">Remarks</span></span>  
 <span data-ttu-id="af5ec-115">`StrongNameSignatureVerificationEx` ような機能を提供します、 [StrongNameSignatureVerification](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignatureverification-function.md)関数。</span><span class="sxs-lookup"><span data-stu-id="af5ec-115">`StrongNameSignatureVerificationEx` provides a capability similar to the [StrongNameSignatureVerification](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignatureverification-function.md) function.</span></span> <span data-ttu-id="af5ec-116">2 番目の入力パラメーターと出力パラメーター、`StrongNameSignatureVerificationEx`型`BOOLEAN`の代わりに`DWORD`します。</span><span class="sxs-lookup"><span data-stu-id="af5ec-116">However, the second input parameter and the output parameter for `StrongNameSignatureVerificationEx` are of type `BOOLEAN` instead of `DWORD`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="af5ec-117">必要条件</span><span class="sxs-lookup"><span data-stu-id="af5ec-117">Requirements</span></span>  
 <span data-ttu-id="af5ec-118">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="af5ec-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="af5ec-119">**ヘッダー:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="af5ec-119">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="af5ec-120">**ライブラリ:** Mscoree.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="af5ec-120">**Library:** Included as a resource in mscoree.dll</span></span>  
  
 <span data-ttu-id="af5ec-121">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="af5ec-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af5ec-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="af5ec-122">See also</span></span>
- [<span data-ttu-id="af5ec-123">StrongNameSignatureVerificationEx メソッド</span><span class="sxs-lookup"><span data-stu-id="af5ec-123">StrongNameSignatureVerificationEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md)
- [<span data-ttu-id="af5ec-124">StrongNameSignatureVerification メソッド</span><span class="sxs-lookup"><span data-stu-id="af5ec-124">StrongNameSignatureVerification Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md)
- [<span data-ttu-id="af5ec-125">ICLRStrongName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="af5ec-125">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
