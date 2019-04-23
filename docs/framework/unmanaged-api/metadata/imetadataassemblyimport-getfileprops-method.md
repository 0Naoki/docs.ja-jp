---
title: IMetaDataAssemblyImport::GetFileProps メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.GetFileProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::GetFileProps
helpviewer_keywords:
- GetFileProps method [.NET Framework metadata]
- IMetaDataAssemblyImport::GetFileProps method [.NET Framework metadata]
ms.assetid: c5e6216f-ae3d-4697-9688-66b69c1251ec
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: da38c04f5d67dc0220b1828ba0e5cdeb84346bb6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59137944"
---
# <a name="imetadataassemblyimportgetfileprops-method"></a><span data-ttu-id="38bd1-102">IMetaDataAssemblyImport::GetFileProps メソッド</span><span class="sxs-lookup"><span data-stu-id="38bd1-102">IMetaDataAssemblyImport::GetFileProps Method</span></span>
<span data-ttu-id="38bd1-103">指定したメタデータ シグネチャを持つファイルのプロパティを取得します。</span><span class="sxs-lookup"><span data-stu-id="38bd1-103">Gets the properties of the file with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38bd1-104">構文</span><span class="sxs-lookup"><span data-stu-id="38bd1-104">Syntax</span></span>  
  
```  
HRESULT GetFileProps (  
    [in]  mdFile      mdf,   
    [out] LPWSTR      szName,   
    [in]  ULONG       cchName,   
    [out] ULONG       *pchName,   
    [out] const void  **ppbHashValue,   
    [out] ULONG       *pcbHashValue,   
    [out] DWORD       *pdwFileFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="38bd1-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="38bd1-105">Parameters</span></span>  
 `mdf`  
 <span data-ttu-id="38bd1-106">[in]`mdFile`プロパティを取得する対象のファイルを表すメタデータ トークン。</span><span class="sxs-lookup"><span data-stu-id="38bd1-106">[in] The `mdFile` metadata token that represents the file for which to get the properties.</span></span>  
  
 `szName`  
 <span data-ttu-id="38bd1-107">[out]ファイルの簡易名。</span><span class="sxs-lookup"><span data-stu-id="38bd1-107">[out] The simple name of the file.</span></span>  
  
 `cchName`  
 <span data-ttu-id="38bd1-108">[in]ワイド文字単位のサイズの`szName`します。</span><span class="sxs-lookup"><span data-stu-id="38bd1-108">[in] The size, in wide chars, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="38bd1-109">[out]実際に返されるワイド文字数`szName`します。</span><span class="sxs-lookup"><span data-stu-id="38bd1-109">[out] The number of wide chars actually returned in `szName`.</span></span>  
  
 `ppbHashValue`  
 <span data-ttu-id="38bd1-110">[out]ハッシュ値へのポインター。</span><span class="sxs-lookup"><span data-stu-id="38bd1-110">[out] A pointer to the hash value.</span></span> <span data-ttu-id="38bd1-111">これは、ファイルの sha-1 アルゴリズムを使用して、ハッシュです。</span><span class="sxs-lookup"><span data-stu-id="38bd1-111">This is the hash, using the SHA-1 algorithm, of the file.</span></span>  
  
 `pcbHashValue`  
 <span data-ttu-id="38bd1-112">[out]返されたハッシュ値のワイド文字の数。</span><span class="sxs-lookup"><span data-stu-id="38bd1-112">[out] The number of wide chars in the returned hash value.</span></span>  
  
 `pdwFileFlags`  
 <span data-ttu-id="38bd1-113">[out]ファイルに適用されるメタデータを記述するフラグへのポインター。</span><span class="sxs-lookup"><span data-stu-id="38bd1-113">[out] A pointer to the flags that describe the metadata applied to a file.</span></span> <span data-ttu-id="38bd1-114">フラグの値は、1 つ以上の組み合わせ[CorFileFlags](../../../../docs/framework/unmanaged-api/metadata/corfileflags-enumeration.md)値。</span><span class="sxs-lookup"><span data-stu-id="38bd1-114">The flags value is a combination of one or more [CorFileFlags](../../../../docs/framework/unmanaged-api/metadata/corfileflags-enumeration.md) values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="38bd1-115">必要条件</span><span class="sxs-lookup"><span data-stu-id="38bd1-115">Requirements</span></span>  
 <span data-ttu-id="38bd1-116">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="38bd1-116">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="38bd1-117">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="38bd1-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="38bd1-118">**ライブラリ:** MsCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="38bd1-118">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="38bd1-119">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="38bd1-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38bd1-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="38bd1-120">See also</span></span>

- [<span data-ttu-id="38bd1-121">IMetaDataAssemblyImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="38bd1-121">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
