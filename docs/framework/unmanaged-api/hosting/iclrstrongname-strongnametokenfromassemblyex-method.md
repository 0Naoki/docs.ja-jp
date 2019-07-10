---
title: ICLRStrongName::StrongNameTokenFromAssemblyEx メソッド
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameTokenFromAssemblyEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameTokenFromAssemblyEx
helpviewer_keywords:
- StrongNameTokenFromAssemblyEx method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameTokenFromAssemblyEx method [.NET Framework hosting]
ms.assetid: 648ea90e-5e60-40a0-a56a-3e61bf2fba7c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9fbac8263944ff0d009fcc7c5f6aecdc7faed089
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67759177"
---
# <a name="iclrstrongnamestrongnametokenfromassemblyex-method"></a><span data-ttu-id="734fb-102">ICLRStrongName::StrongNameTokenFromAssemblyEx メソッド</span><span class="sxs-lookup"><span data-stu-id="734fb-102">ICLRStrongName::StrongNameTokenFromAssemblyEx Method</span></span>
<span data-ttu-id="734fb-103">指定したアセンブリ ファイルから厳密な名前トークンを作成し、トークンが表す公開キーを返します。</span><span class="sxs-lookup"><span data-stu-id="734fb-103">Creates a strong name token from the specified assembly file, and returns the public key that the token represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="734fb-104">構文</span><span class="sxs-lookup"><span data-stu-id="734fb-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameTokenFromAssemblyEx (  
    [in]  LPCWSTR   wszFilePath,  
    [out] BYTE      **ppbStrongNameToken,  
    [out] ULONG     *pcbStrongNameToken,  
    [out] BYTE      **ppbPublicKeyBlob,  
    [out] ULONG     *pcbPublicKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="734fb-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="734fb-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="734fb-106">[in]アセンブリのポータブル実行可能 (PE) ファイルへのパス。</span><span class="sxs-lookup"><span data-stu-id="734fb-106">[in] The path to the portable executable (PE) file for the assembly.</span></span>  
  
 `ppbStrongNameToken`  
 <span data-ttu-id="734fb-107">[out]厳密な名前が返されたトークンです。</span><span class="sxs-lookup"><span data-stu-id="734fb-107">[out] The returned strong name token.</span></span>  
  
 `pcbStrongNameToken`  
 <span data-ttu-id="734fb-108">[out]厳密な名前トークンのバイト単位のサイズ。</span><span class="sxs-lookup"><span data-stu-id="734fb-108">[out] The size, in bytes, of the strong name token.</span></span>  
  
 `ppbPublicKeyBlob`  
 <span data-ttu-id="734fb-109">[out]返される公開キー。</span><span class="sxs-lookup"><span data-stu-id="734fb-109">[out] The returned public key.</span></span>  
  
 `pcbPublicKeyBlob`  
 <span data-ttu-id="734fb-110">[out]公開キーのバイト単位のサイズ。</span><span class="sxs-lookup"><span data-stu-id="734fb-110">[out] The size, in bytes, of the public key.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="734fb-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="734fb-111">Return Value</span></span>  
 <span data-ttu-id="734fb-112">`S_OK` メソッドが正常に完了した場合それ以外の場合、エラーを示す HRESULT 値 (を参照してください[の共通 HRESULT 値](https://go.microsoft.com/fwlink/?LinkId=213878)一覧については)。</span><span class="sxs-lookup"><span data-stu-id="734fb-112">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="734fb-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="734fb-113">Remarks</span></span>  
 <span data-ttu-id="734fb-114">厳密な名前トークンは、公開キーの短縮形です。</span><span class="sxs-lookup"><span data-stu-id="734fb-114">A strong name token is the shortened form of a public key.</span></span> <span data-ttu-id="734fb-115">トークンは、アセンブリの署名に使用する公開キーから作成される 64 ビット ハッシュです。</span><span class="sxs-lookup"><span data-stu-id="734fb-115">The token is a 64-bit hash that is created from the public key used to sign the assembly.</span></span> <span data-ttu-id="734fb-116">トークンは、アセンブリの厳密な名前の一部であるし、アセンブリのメタデータから読み取ることができます。</span><span class="sxs-lookup"><span data-stu-id="734fb-116">The token is a part of the strong name for the assembly, and can be read from the assembly metadata.</span></span>  
  
 <span data-ttu-id="734fb-117">呼び出す必要があります、キーを取得し、トークンを作成、後に、 [iclrstrongname::strongnamefreebuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md)を割り当てられたメモリを解放するメソッド。</span><span class="sxs-lookup"><span data-stu-id="734fb-117">After the key is retrieved and the token is created, you should call the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method to release the allocated memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="734fb-118">必要条件</span><span class="sxs-lookup"><span data-stu-id="734fb-118">Requirements</span></span>  
 <span data-ttu-id="734fb-119">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="734fb-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="734fb-120">**ヘッダー:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="734fb-120">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="734fb-121">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="734fb-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="734fb-122">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="734fb-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="734fb-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="734fb-123">See also</span></span>

- [<span data-ttu-id="734fb-124">StrongNameTokenFromAssembly メソッド</span><span class="sxs-lookup"><span data-stu-id="734fb-124">StrongNameTokenFromAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassembly-method.md)
- [<span data-ttu-id="734fb-125">ICLRStrongName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="734fb-125">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
