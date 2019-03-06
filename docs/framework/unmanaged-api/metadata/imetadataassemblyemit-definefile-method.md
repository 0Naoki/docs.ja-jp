---
title: IMetaDataAssemblyEmit::DefineFile メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.DefineFile
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::DefineFile
helpviewer_keywords:
- IMetaDataAssemblyEmit::DefineFile method [.NET Framework metadata]
- DefineFile method [.NET Framework metadata]
ms.assetid: c065aadf-c1ca-4981-bde6-597042cb29c4
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6dac6bb6790876e28f1a5cd72f0635a1155caa47
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57481041"
---
# <a name="imetadataassemblyemitdefinefile-method"></a><span data-ttu-id="25828-102">IMetaDataAssemblyEmit::DefineFile メソッド</span><span class="sxs-lookup"><span data-stu-id="25828-102">IMetaDataAssemblyEmit::DefineFile Method</span></span>
<span data-ttu-id="25828-103">このアセンブリが参照するアセンブリのメタデータを含む `File` メタデータ構造体を作成し、関連付けられたメタデータ トークンを返します。</span><span class="sxs-lookup"><span data-stu-id="25828-103">Creates a `File` metadata structure containing metadata for assembly referenced by this assembly, and returns the associated metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="25828-104">構文</span><span class="sxs-lookup"><span data-stu-id="25828-104">Syntax</span></span>  
  
```  
HRESULT DefineFile (  
    [in]  LPCWSTR        szName,   
    [in]  const void     *pbHashValue,   
    [in]  ULONG          cbHashValue,  
    [in]  DWORD          dwFileFlags,  
    [out] mdFile         *pmdf  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="25828-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="25828-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="25828-106">[in]使用するファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="25828-106">[in] The name of the file to be consumed.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="25828-107">[in]アセンブリに関連付けられているデータのハッシュへのポインター。</span><span class="sxs-lookup"><span data-stu-id="25828-107">[in] A pointer to the hash data associated with the assembly.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="25828-108">[in]バイト サイズ`pbHashValue`します。</span><span class="sxs-lookup"><span data-stu-id="25828-108">[in] The size in bytes of `pbHashValue`.</span></span>  
  
 `dwFileFlags`  
 <span data-ttu-id="25828-109">[in]ビットごとの組み合わせ`FileFlags`プロパティの設定を指定する値。</span><span class="sxs-lookup"><span data-stu-id="25828-109">[in] A bitwise combination of `FileFlags` values that specify property settings.</span></span>  
  
 `pmdf`  
 <span data-ttu-id="25828-110">[out]返されたポインター`File`トークンです。</span><span class="sxs-lookup"><span data-stu-id="25828-110">[out] A pointer to the returned `File` token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="25828-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="25828-111">Remarks</span></span>  
 <span data-ttu-id="25828-112">1 つ`File`メタデータを含むファイルを除く、このアセンブリの構築時にこのアセンブリの一部であった各ファイルのメタデータ構造を定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="25828-112">One `File` metadata structure must be defined for each file that was part of this assembly at the time that this assembly was built, excluding the file that contains the metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="25828-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="25828-113">Requirements</span></span>  
 <span data-ttu-id="25828-114">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="25828-114">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="25828-115">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="25828-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="25828-116">**ライブラリ:** MsCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="25828-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="25828-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="25828-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25828-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="25828-118">See also</span></span>
- [<span data-ttu-id="25828-119">IMetaDataAssemblyEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="25828-119">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
