---
title: ICLRStrongName::StrongNameSignatureSize メソッド
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameSignatureSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameSignatureSize
helpviewer_keywords:
- ICLRStrongName::StrongNameSignatureSize method [.NET Framework hosting]
- StrongNameSignatureSize method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 76d4f93a-5e25-4399-abcc-a1389549481d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dc5a40a0e26f116ce1700973a5000e8d6bbbd890
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/01/2018
ms.locfileid: "43423832"
---
# <a name="iclrstrongnamestrongnamesignaturesize-method"></a><span data-ttu-id="3c78f-102">ICLRStrongName::StrongNameSignatureSize メソッド</span><span class="sxs-lookup"><span data-stu-id="3c78f-102">ICLRStrongName::StrongNameSignatureSize Method</span></span>
<span data-ttu-id="3c78f-103">厳密な名前の署名のサイズを返します。</span><span class="sxs-lookup"><span data-stu-id="3c78f-103">Returns the size of the strong name signature.</span></span> <span data-ttu-id="3c78f-104">このメソッドは、遅延署名アセンブリを作成するときに、ファイルに予約する領域の量を決定するコンパイラで通常使用されます。</span><span class="sxs-lookup"><span data-stu-id="3c78f-104">This method is typically used by compilers to determine how much space to reserve in the file when creating a delay-signed assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c78f-105">構文</span><span class="sxs-lookup"><span data-stu-id="3c78f-105">Syntax</span></span>  
  
```  
HRESULT StrongNameSignatureSize (   
    [in]  BYTE   *pbPublicKeyBlob,  
    [in]  ULONG  cbPublicKeyBlob,   
    [in]  DWORD  *pcbSize  
);   
```  
  
#### <a name="parameters"></a><span data-ttu-id="3c78f-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3c78f-106">Parameters</span></span>  
 `pbPublicKeyBlob`  
 <span data-ttu-id="3c78f-107">[in]型の構造体[PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)厳密な名前の署名を生成するためのキー ペアの公開部分を格納しています。</span><span class="sxs-lookup"><span data-stu-id="3c78f-107">[in] A structure of type [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) that contains the public portion of the key pair used to generate the strong name signature.</span></span>  
  
 `cbPublicKeyBlob`  
 <span data-ttu-id="3c78f-108">[in]サイズ (バイト単位) の`pbPublicKeyBlob`します。</span><span class="sxs-lookup"><span data-stu-id="3c78f-108">[in] The size, in bytes, of `pbPublicKeyBlob`.</span></span>  
  
 `pcbSize`  
 <span data-ttu-id="3c78f-109">[in]厳密な名前の署名を格納するために必要なバイト数。</span><span class="sxs-lookup"><span data-stu-id="3c78f-109">[in] The number of bytes required to store the strong name signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3c78f-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="3c78f-110">Return Value</span></span>  
 <span data-ttu-id="3c78f-111">`S_OK` メソッドが正常に完了した場合それ以外の場合、エラーを示す HRESULT 値 (を参照してください[の共通 HRESULT 値](https://go.microsoft.com/fwlink/?LinkId=213878)一覧については)。</span><span class="sxs-lookup"><span data-stu-id="3c78f-111">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3c78f-112">要件</span><span class="sxs-lookup"><span data-stu-id="3c78f-112">Requirements</span></span>  
 <span data-ttu-id="3c78f-113">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3c78f-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3c78f-114">**ヘッダー:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="3c78f-114">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="3c78f-115">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="3c78f-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3c78f-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3c78f-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c78f-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="3c78f-117">See Also</span></span>  
 [<span data-ttu-id="3c78f-118">ICLRStrongName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3c78f-118">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
