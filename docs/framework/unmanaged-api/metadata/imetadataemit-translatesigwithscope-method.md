---
title: IMetaDataEmit::TranslateSigWithScope メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.TranslateSigWithScope
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::TranslateSigWithScope
helpviewer_keywords:
- TranslateSigWithScope method [.NET Framework metadata]
- IMetaDataEmit::TranslateSigWithScope method [.NET Framework metadata]
ms.assetid: 47915d33-b7bf-409e-b484-4ee1df15de22
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1243a5ed1a3b741f1691cc4f0847ddcf17ac9669
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57478389"
---
# <a name="imetadataemittranslatesigwithscope-method"></a><span data-ttu-id="fc969-102">IMetaDataEmit::TranslateSigWithScope メソッド</span><span class="sxs-lookup"><span data-stu-id="fc969-102">IMetaDataEmit::TranslateSigWithScope Method</span></span>
<span data-ttu-id="fc969-103">現在のスコープにアセンブリをインポートし、マージされたスコープの新しいメタデータ シグネチャを取得します。</span><span class="sxs-lookup"><span data-stu-id="fc969-103">Imports an assembly into the current scope and gets a new metadata signature for the merged scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc969-104">構文</span><span class="sxs-lookup"><span data-stu-id="fc969-104">Syntax</span></span>  
  
```  
HRESULT TranslateSigWithScope (   
    [in]  IMetaDataAssemblyImport   *pAssemImport,   
    [in]  const void                *pbHashValue,   
    [in]  ULONG                     cbHashValue,   
    [in]  IMetaDataImport           *import,   
    [in]  PCCOR_SIGNATURE           pbSigBlob,   
    [in]  ULONG                     cbSigBlob,  
    [in]  IMetaDataAssemblyEmit     *pAssemEmit,   
    [in]  IMetaDataEmit             *emit,   
    [out] PCOR_SIGNATURE            pvTranslatedSig,   
    [in]  ULONG                     cbTranslatedSigMax,   
    [out] ULONG                     *pcbTranslatedSig   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fc969-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="fc969-105">Parameters</span></span>  
 `pAssemImport`  
 <span data-ttu-id="fc969-106">[in] \(署名が定義されている\) インポート アセンブリのインターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="fc969-106">[in] The interface for import assembly (where the signature is defined).</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="fc969-107">[in]アセンブリのハッシュ blob。</span><span class="sxs-lookup"><span data-stu-id="fc969-107">[in] The hash blob for the assembly.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="fc969-108">[in]内のバイト数`pbHashValue`します。</span><span class="sxs-lookup"><span data-stu-id="fc969-108">[in] The count of bytes in `pbHashValue`.</span></span>  
  
 `import`  
 <span data-ttu-id="fc969-109">[in]インポートのメタデータ スコープのインターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="fc969-109">[in] The interface for import metadata scope.</span></span>  
  
 `pbSigBlob`  
 <span data-ttu-id="fc969-110">[in]インポートする署名します。</span><span class="sxs-lookup"><span data-stu-id="fc969-110">[in] The signature to be imported.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="fc969-111">[in]サイズ (バイト単位) の`pbSigBlob`します。</span><span class="sxs-lookup"><span data-stu-id="fc969-111">[in] The size, in bytes, of `pbSigBlob`.</span></span>  
  
 `pAssemEmit`  
 <span data-ttu-id="fc969-112">[in]エクスポートのアセンブリのインターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="fc969-112">[in] The interface for export assembly.</span></span>  
  
 `emit`  
 <span data-ttu-id="fc969-113">[in]エクスポートのメタデータ スコープのインターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="fc969-113">[in] The interface for export metadata scope.</span></span>  
  
 `pvTranslatedSig`  
 <span data-ttu-id="fc969-114">[out]翻訳されたシグネチャ blob を保持するバッファー。</span><span class="sxs-lookup"><span data-stu-id="fc969-114">[out] The buffer to hold the translated signature blob.</span></span>  
  
 `cbTranslatedSigMax`  
 <span data-ttu-id="fc969-115">[in] (バイト単位) の容量の`pvTranslatedSig`します。</span><span class="sxs-lookup"><span data-stu-id="fc969-115">[in] The capacity, in bytes, of `pvTranslatedSig`.</span></span>  
  
 `pcbTranslatedSig`  
 <span data-ttu-id="fc969-116">[out]翻訳されたシグネチャでの実際のバイト数。</span><span class="sxs-lookup"><span data-stu-id="fc969-116">[out] The number of actual bytes in the translated signature.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fc969-117">必要条件</span><span class="sxs-lookup"><span data-stu-id="fc969-117">Requirements</span></span>  
 <span data-ttu-id="fc969-118">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="fc969-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fc969-119">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="fc969-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="fc969-120">**ライブラリ:** MSCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="fc969-120">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fc969-121">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fc969-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc969-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="fc969-122">See also</span></span>
- [<span data-ttu-id="fc969-123">IMetaDataAssemblyEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="fc969-123">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
- [<span data-ttu-id="fc969-124">IMetaDataAssemblyImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="fc969-124">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
- [<span data-ttu-id="fc969-125">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="fc969-125">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="fc969-126">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="fc969-126">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="fc969-127">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="fc969-127">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
