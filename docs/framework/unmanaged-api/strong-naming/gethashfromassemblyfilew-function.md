---
title: GetHashFromAssemblyFileW 関数
ms.date: 03/30/2017
api_name:
- GetHashFromAssemblyFileW
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetHashFromAssemblyFileW
helpviewer_keywords:
- GetHashFromAssemblyFileW function [.NET Framework strong naming]
ms.assetid: d1b2b172-5353-42af-a877-cf653c68ece0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6fda1964ab29287b2a3a108a15f42d1ea28a4feb
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57486917"
---
# <a name="gethashfromassemblyfilew-function"></a><span data-ttu-id="8c969-102">GetHashFromAssemblyFileW 関数</span><span class="sxs-lookup"><span data-stu-id="8c969-102">GetHashFromAssemblyFileW Function</span></span>
<span data-ttu-id="8c969-103">指定したハッシュ アルゴリズムを使用して、指定したアセンブリ ファイルのハッシュ値が取得されます。</span><span class="sxs-lookup"><span data-stu-id="8c969-103">Gets a hash of the specified assembly file, using the specified hash algorithm.</span></span> <span data-ttu-id="8c969-104">アセンブリ ファイルへのパスは、Unicode 文字列として指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8c969-104">The path to the assembly file must be specified as a Unicode string.</span></span>  
  
 <span data-ttu-id="8c969-105">この関数は非推奨とされました。</span><span class="sxs-lookup"><span data-stu-id="8c969-105">This function has been deprecated.</span></span> <span data-ttu-id="8c969-106">使用して、 [iclrstrongname::gethashfromassemblyfilew](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfilew-method.md)メソッド代わりにします。</span><span class="sxs-lookup"><span data-stu-id="8c969-106">Use the [ICLRStrongName::GetHashFromAssemblyFileW](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfilew-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c969-107">構文</span><span class="sxs-lookup"><span data-stu-id="8c969-107">Syntax</span></span>  
  
```  
HRESULT GetHashFromAssemblyFileW (  
    [in]  LPCWSTR   wszFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE      *pbHash,  
    [in]  DWORD     cchHash,  
    [out] DWORD     *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8c969-108">パラメーター</span><span class="sxs-lookup"><span data-stu-id="8c969-108">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="8c969-109">[in]ハッシュされるファイルへのパス。</span><span class="sxs-lookup"><span data-stu-id="8c969-109">[in] The path to the file to be hashed.</span></span> <span data-ttu-id="8c969-110">このパラメーターは、Unicode 文字列である必要があります。</span><span class="sxs-lookup"><span data-stu-id="8c969-110">This parameter must be a Unicode string.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="8c969-111">[入力、出力]ハッシュ アルゴリズムを指定する定数。</span><span class="sxs-lookup"><span data-stu-id="8c969-111">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="8c969-112">既定のハッシュ アルゴリズムのゼロを使用します。</span><span class="sxs-lookup"><span data-stu-id="8c969-112">Use zero for the default hash algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="8c969-113">[out]返されたハッシュ バッファー。</span><span class="sxs-lookup"><span data-stu-id="8c969-113">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="8c969-114">[in]要求の最大サイズの`pbHash`します。</span><span class="sxs-lookup"><span data-stu-id="8c969-114">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="8c969-115">[out]サイズ (バイト単位) が返されますの`pbHash`します。</span><span class="sxs-lookup"><span data-stu-id="8c969-115">[out] The returned size, in bytes, of `pbHash`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8c969-116">必要条件</span><span class="sxs-lookup"><span data-stu-id="8c969-116">Requirements</span></span>  
 <span data-ttu-id="8c969-117">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8c969-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8c969-118">**ヘッダー:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="8c969-118">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="8c969-119">**ライブラリ:** MsCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="8c969-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8c969-120">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8c969-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c969-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="8c969-121">See also</span></span>
- [<span data-ttu-id="8c969-122">GetHashFromAssemblyFileW メソッド</span><span class="sxs-lookup"><span data-stu-id="8c969-122">GetHashFromAssemblyFileW Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfilew-method.md)
- [<span data-ttu-id="8c969-123">GetHashFromAssemblyFile メソッド</span><span class="sxs-lookup"><span data-stu-id="8c969-123">GetHashFromAssemblyFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfile-method.md)
- [<span data-ttu-id="8c969-124">ICLRStrongName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8c969-124">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
