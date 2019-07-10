---
title: ICLRStrongName::StrongNameTokenFromPublicKey メソッド
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameTokenFromPublicKey
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameTokenFromPublicKey
helpviewer_keywords:
- ICLRStrongName::StrongNameTokenFromPublicKey method [.NET Framework hosting]
- StrongNameTokenFromPublicKey method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 7962ce88-7e86-4a6f-8298-621b01ffc3c2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 17947526513bd1fbe3cb093e8ecaa7ed67983a7c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67759167"
---
# <a name="iclrstrongnamestrongnametokenfrompublickey-method"></a><span data-ttu-id="36f3b-102">ICLRStrongName::StrongNameTokenFromPublicKey メソッド</span><span class="sxs-lookup"><span data-stu-id="36f3b-102">ICLRStrongName::StrongNameTokenFromPublicKey Method</span></span>
<span data-ttu-id="36f3b-103">公開キーを表すトークンを取得します。</span><span class="sxs-lookup"><span data-stu-id="36f3b-103">Gets a token that represents a public key.</span></span> <span data-ttu-id="36f3b-104">厳密な名前トークンは、公開キーの短縮形です。</span><span class="sxs-lookup"><span data-stu-id="36f3b-104">A strong name token is the shortened form of a public key.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36f3b-105">構文</span><span class="sxs-lookup"><span data-stu-id="36f3b-105">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameTokenFromPublicKey (   
    [in]  BYTE    *pbPublicKeyBlob,  
    [in]  ULONG   cbPublicKeyBlob,  
    [out] BYTE    **ppbStrongNameToken,  
    [out] ULONG   *pcbStrongNameToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="36f3b-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="36f3b-106">Parameters</span></span>  
 `pbPublicKeyBlob`  
 <span data-ttu-id="36f3b-107">[in]型の構造体[PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)厳密な名前の署名を生成するためのキー ペアの公開部分を格納しています。</span><span class="sxs-lookup"><span data-stu-id="36f3b-107">[in] A structure of type [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) that contains the public portion of the key pair used to generate the strong name signature.</span></span>  
  
 `cbPublicKeyBlob`  
 <span data-ttu-id="36f3b-108">[in]サイズ (バイト単位) の`pbPublicKeyBlob`します。</span><span class="sxs-lookup"><span data-stu-id="36f3b-108">[in] The size, in bytes, of `pbPublicKeyBlob`.</span></span>  
  
 `ppbStrongNameToken`  
 <span data-ttu-id="36f3b-109">[out]渡されたキーに対応する厳密な名前トークン`pbPublicKeyBlob`します。</span><span class="sxs-lookup"><span data-stu-id="36f3b-109">[out] The strong name token corresponding to the key passed in `pbPublicKeyBlob`.</span></span> <span data-ttu-id="36f3b-110">共通言語ランタイムでは、トークンが返されるメモリを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="36f3b-110">The common language runtime allocates the memory in which to return the token.</span></span> <span data-ttu-id="36f3b-111">呼び出し元を使用してこのメモリを解放する必要があります、 [iclrstrongname::strongnamefreebuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="36f3b-111">The caller must free this memory by using the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method.</span></span>  
  
 `pcbStrongNameToken`  
 <span data-ttu-id="36f3b-112">[out]厳密な名前が返されたトークンのバイト単位のサイズ。</span><span class="sxs-lookup"><span data-stu-id="36f3b-112">[out] The size, in bytes, of the returned strong name token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="36f3b-113">戻り値</span><span class="sxs-lookup"><span data-stu-id="36f3b-113">Return Value</span></span>  
 <span data-ttu-id="36f3b-114">`S_OK` メソッドが正常に完了した場合それ以外の場合、エラーを示す HRESULT 値 (を参照してください[の共通 HRESULT 値](https://go.microsoft.com/fwlink/?LinkId=213878)一覧については)。</span><span class="sxs-lookup"><span data-stu-id="36f3b-114">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="36f3b-115">Remarks</span><span class="sxs-lookup"><span data-stu-id="36f3b-115">Remarks</span></span>  
 <span data-ttu-id="36f3b-116">厳密な名前トークンは、メタデータにキー情報を格納する場合は、スペースを節約するために使用する公開キーの短縮形です。</span><span class="sxs-lookup"><span data-stu-id="36f3b-116">A strong name token is the shortened form of a public key that is used to save space when storing key information in metadata.</span></span> <span data-ttu-id="36f3b-117">具体的には、厳密な名前トークンは、依存アセンブリを参照するアセンブリ参照で使用されます。</span><span class="sxs-lookup"><span data-stu-id="36f3b-117">Specifically, strong name tokens are used in assembly references to refer to the dependent assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="36f3b-118">必要条件</span><span class="sxs-lookup"><span data-stu-id="36f3b-118">Requirements</span></span>  
 <span data-ttu-id="36f3b-119">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="36f3b-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="36f3b-120">**ヘッダー:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="36f3b-120">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="36f3b-121">**ライブラリ:** Mscoree.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="36f3b-121">**Library:** Included as a resource in mscoree.dll</span></span>  
  
 <span data-ttu-id="36f3b-122">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="36f3b-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36f3b-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="36f3b-123">See also</span></span>

- [<span data-ttu-id="36f3b-124">StrongNameGetPublicKey メソッド</span><span class="sxs-lookup"><span data-stu-id="36f3b-124">StrongNameGetPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md)
- [<span data-ttu-id="36f3b-125">PublicKeyBlob 構造体</span><span class="sxs-lookup"><span data-stu-id="36f3b-125">PublicKeyBlob Structure</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)
- [<span data-ttu-id="36f3b-126">ICLRStrongName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="36f3b-126">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
