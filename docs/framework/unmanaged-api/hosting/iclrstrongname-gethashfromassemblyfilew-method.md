---
title: ICLRStrongName::GetHashFromAssemblyFileW メソッド
ms.date: 03/30/2017
api_name:
- ICLRStrongName.GetHashFromAssemblyFileW
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::GetHashFromAssemblyFileW
helpviewer_keywords:
- ICLRStrongName::GetHashFromAssemblyFileW method [.NET Framework hosting]
- GetHashFromAssemblyFileW method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 5d0b44a2-5a14-44a2-9a0e-e8682fd4e106
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 578dd7941ad7a2cf1d39a3aeed7fa823eb7efa79
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61984595"
---
# <a name="iclrstrongnamegethashfromassemblyfilew-method"></a><span data-ttu-id="fa9f1-102">ICLRStrongName::GetHashFromAssemblyFileW メソッド</span><span class="sxs-lookup"><span data-stu-id="fa9f1-102">ICLRStrongName::GetHashFromAssemblyFileW Method</span></span>
<span data-ttu-id="fa9f1-103">Unicode 文字列で指定されたファイルの内容に対してハッシュが作成されます。</span><span class="sxs-lookup"><span data-stu-id="fa9f1-103">Generates a hash over the contents of the file specified by a Unicode string.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa9f1-104">構文</span><span class="sxs-lookup"><span data-stu-id="fa9f1-104">Syntax</span></span>  
  
```  
HRESULT GetHashFromAssemblyFileW (  
    [in]  LPCWSTR   wszFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE      *pbHash,  
    [in]  DWORD     cchHash,  
    [out] DWORD     *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fa9f1-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="fa9f1-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="fa9f1-106">[in]ハッシュされるファイルへのパス。</span><span class="sxs-lookup"><span data-stu-id="fa9f1-106">[in] The path to the file to be hashed.</span></span> <span data-ttu-id="fa9f1-107">このパラメーターは、Unicode 文字列である必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa9f1-107">This parameter must be a Unicode string.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="fa9f1-108">[入力、出力]ハッシュ アルゴリズムを指定する定数。</span><span class="sxs-lookup"><span data-stu-id="fa9f1-108">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="fa9f1-109">既定のハッシュ アルゴリズムのゼロを使用します。</span><span class="sxs-lookup"><span data-stu-id="fa9f1-109">Use zero for the default hash algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="fa9f1-110">[out]返されたハッシュ バッファー。</span><span class="sxs-lookup"><span data-stu-id="fa9f1-110">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="fa9f1-111">[in]要求の最大サイズの`pbHash`します。</span><span class="sxs-lookup"><span data-stu-id="fa9f1-111">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="fa9f1-112">[out]サイズ (バイト単位) が返されますの`pbHash`します。</span><span class="sxs-lookup"><span data-stu-id="fa9f1-112">[out] The returned size, in bytes, of `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fa9f1-113">戻り値</span><span class="sxs-lookup"><span data-stu-id="fa9f1-113">Return Value</span></span>  
 <span data-ttu-id="fa9f1-114">`S_OK` メソッドが正常に完了した場合それ以外の場合、エラーを示す HRESULT 値 (を参照してください[の共通 HRESULT 値](https://go.microsoft.com/fwlink/?LinkId=213878)一覧については)。</span><span class="sxs-lookup"><span data-stu-id="fa9f1-114">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fa9f1-115">必要条件</span><span class="sxs-lookup"><span data-stu-id="fa9f1-115">Requirements</span></span>  
 <span data-ttu-id="fa9f1-116">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="fa9f1-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fa9f1-117">**ヘッダー:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="fa9f1-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="fa9f1-118">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="fa9f1-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fa9f1-119">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fa9f1-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa9f1-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="fa9f1-120">See also</span></span>

- [<span data-ttu-id="fa9f1-121">GetHashFromAssemblyFile メソッド</span><span class="sxs-lookup"><span data-stu-id="fa9f1-121">GetHashFromAssemblyFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfile-method.md)
- [<span data-ttu-id="fa9f1-122">ICLRStrongName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="fa9f1-122">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
