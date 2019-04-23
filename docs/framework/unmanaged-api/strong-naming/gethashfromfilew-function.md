---
title: GetHashFromFileW 関数
ms.date: 03/30/2017
api_name:
- GetHashFromFileW
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetHashFromFileW
helpviewer_keywords:
- GetHashFromFileW function [.NET Framework strong naming]
ms.assetid: 97c2d7a6-5376-45a1-ba65-146a249147cc
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9be512bab30e08ddeb7deadf8a29263e928549a1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59134616"
---
# <a name="gethashfromfilew-function"></a><span data-ttu-id="13fb3-102">GetHashFromFileW 関数</span><span class="sxs-lookup"><span data-stu-id="13fb3-102">GetHashFromFileW Function</span></span>
<span data-ttu-id="13fb3-103">Unicode 文字列で指定されたファイルの内容に対してハッシュが作成されます。</span><span class="sxs-lookup"><span data-stu-id="13fb3-103">Generates a hash over the contents of the file specified by a Unicode string.</span></span>  
  
 <span data-ttu-id="13fb3-104">この関数は非推奨とされました。</span><span class="sxs-lookup"><span data-stu-id="13fb3-104">This function has been deprecated.</span></span> <span data-ttu-id="13fb3-105">使用して、 [iclrstrongname::gethashfromfilew](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md)メソッド代わりにします。</span><span class="sxs-lookup"><span data-stu-id="13fb3-105">Use the [ICLRStrongName::GetHashFromFileW](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13fb3-106">構文</span><span class="sxs-lookup"><span data-stu-id="13fb3-106">Syntax</span></span>  
  
```  
HRESULT GetHashFromFileW (   
    [in]  LPCWSTR   wszFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE      *pbHash,  
    [in]  DWORD     cchHash,  
    [out] DWORD     *pchHash  
);   
```  
  
## <a name="parameters"></a><span data-ttu-id="13fb3-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="13fb3-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="13fb3-108">[in]ハッシュするファイルの Unicode の名前。</span><span class="sxs-lookup"><span data-stu-id="13fb3-108">[in] The Unicode name of the file to hash.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="13fb3-109">[入力、出力]ハッシュを生成するときに使用するアルゴリズム。</span><span class="sxs-lookup"><span data-stu-id="13fb3-109">[in, out] The algorithm to use when generating the hash.</span></span> <span data-ttu-id="13fb3-110">有効なアルゴリズムを使用して、Win32 CryptoAPI で定義されています。</span><span class="sxs-lookup"><span data-stu-id="13fb3-110">Valid algorithms are those defined by the Win32 CryptoAPI.</span></span> <span data-ttu-id="13fb3-111">場合`piHashAlg`CALG_SHA 1 が使用される既定のアルゴリズムを 0 に設定されます。</span><span class="sxs-lookup"><span data-stu-id="13fb3-111">If `piHashAlg` is set to 0, the default algorithm CALG_SHA-1 is used.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="13fb3-112">[out]生成されたハッシュを含むバイト配列。</span><span class="sxs-lookup"><span data-stu-id="13fb3-112">[out] A byte array containing the generated hash.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="13fb3-113">[in]によって示されるバッファーの最大サイズ`pbHash`します。</span><span class="sxs-lookup"><span data-stu-id="13fb3-113">[in] The maximum size of the buffer pointed to by `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="13fb3-114">[out]サイズ (バイト単位) の`pbHash`します。</span><span class="sxs-lookup"><span data-stu-id="13fb3-114">[out] The size, in bytes, of `pbHash`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="13fb3-115">Remarks</span><span class="sxs-lookup"><span data-stu-id="13fb3-115">Remarks</span></span>  
 <span data-ttu-id="13fb3-116">この関数は、同じ[GetHashFromFile](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromfile-function.md)ファイル名の指定は ANSI ではなく Unicode を点が異なります。</span><span class="sxs-lookup"><span data-stu-id="13fb3-116">This function is the same as [GetHashFromFile](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromfile-function.md), except that the file name specification is Unicode instead of ANSI.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="13fb3-117">必要条件</span><span class="sxs-lookup"><span data-stu-id="13fb3-117">Requirements</span></span>  
 <span data-ttu-id="13fb3-118">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="13fb3-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="13fb3-119">**ヘッダー:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="13fb3-119">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="13fb3-120">**ライブラリ:** MsCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="13fb3-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="13fb3-121">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="13fb3-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13fb3-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="13fb3-122">See also</span></span>

- [<span data-ttu-id="13fb3-123">GetHashFromFileW メソッド</span><span class="sxs-lookup"><span data-stu-id="13fb3-123">GetHashFromFileW Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md)
- [<span data-ttu-id="13fb3-124">GetHashFromFile メソッド</span><span class="sxs-lookup"><span data-stu-id="13fb3-124">GetHashFromFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md)
- [<span data-ttu-id="13fb3-125">ICLRStrongName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="13fb3-125">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
