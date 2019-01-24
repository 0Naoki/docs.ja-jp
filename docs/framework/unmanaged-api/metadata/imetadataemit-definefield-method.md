---
title: IMetaDataEmit::DefineField メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineField
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineField
helpviewer_keywords:
- IMetaDataEmit::DefineField method [.NET Framework metadata]
- DefineField method, IMetaDataEmit interface [.NET Framework metadata
ms.assetid: 6b5be4fc-2e86-499c-8b09-833160bca767
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: dfe888f74face85179306c982f7b5a888752987e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54742800"
---
# <a name="imetadataemitdefinefield-method"></a><span data-ttu-id="c6134-102">IMetaDataEmit::DefineField メソッド</span><span class="sxs-lookup"><span data-stu-id="c6134-102">IMetaDataEmit::DefineField Method</span></span>
<span data-ttu-id="c6134-103">指定したメタデータ シグネチャを持つフィールドの定義を作成し、そのフィールド定義トークンを取得します。</span><span class="sxs-lookup"><span data-stu-id="c6134-103">Creates a definition for a field with the specified metadata signature, and gets a token to that field definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6134-104">構文</span><span class="sxs-lookup"><span data-stu-id="c6134-104">Syntax</span></span>  
  
```  
HRESULT DefineField (   
    [in]  mdTypeDef   td,   
    [in]  LPCWSTR     szName,   
    [in]  DWORD       dwFieldFlags,   
    [in]  PCCOR_SIGNATURE pvSigBlob,   
    [in]  ULONG       cbSigBlob,   
    [in]  DWORD       dwCPlusTypeFlag,   
    [in]  void const  *pValue,   
    [in]  ULONG       cchValue,   
    [out] mdFieldDef  *pmd   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c6134-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c6134-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="c6134-106">[in]`mdTypeDef`外側のクラスまたはインターフェイスのトークン。</span><span class="sxs-lookup"><span data-stu-id="c6134-106">[in] The `mdTypeDef` token for the enclosing class or interface.</span></span>  
  
 `szName`  
 <span data-ttu-id="c6134-107">[in]Unicode でフィールド名です。</span><span class="sxs-lookup"><span data-stu-id="c6134-107">[in] The field name in Unicode.</span></span>  
  
 `dwFieldFlags`  
 <span data-ttu-id="c6134-108">[in]フィールドの属性。</span><span class="sxs-lookup"><span data-stu-id="c6134-108">[in] The field attributes.</span></span> <span data-ttu-id="c6134-109">これは、ビットマスクの`CorFieldAttr`値。</span><span class="sxs-lookup"><span data-stu-id="c6134-109">This is a bitmask of `CorFieldAttr` values.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="c6134-110">[in]BLOB としてフィールド シグネチャ。</span><span class="sxs-lookup"><span data-stu-id="c6134-110">[in] The field signature as a BLOB.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="c6134-111">[in]内のバイト数`pvSigBlob`します。</span><span class="sxs-lookup"><span data-stu-id="c6134-111">[in] The count of bytes in `pvSigBlob`.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="c6134-112">[in]`ELEMENT_TYPE_` *\** 定数の値。</span><span class="sxs-lookup"><span data-stu-id="c6134-112">[in] The `ELEMENT_TYPE_`*\** for the constant value.</span></span> <span data-ttu-id="c6134-113">これは、`CorElementType`値。</span><span class="sxs-lookup"><span data-stu-id="c6134-113">This is a `CorElementType` value.</span></span> <span data-ttu-id="c6134-114">場合は、フィールドの定数値を定義しないを使用して、`ELEMENT_TYPE_END`します。</span><span class="sxs-lookup"><span data-stu-id="c6134-114">If not defining a constant value for the field, use `ELEMENT_TYPE_END`.</span></span>  
  
 `pValue`  
 <span data-ttu-id="c6134-115">[in]フィールドの定数値。</span><span class="sxs-lookup"><span data-stu-id="c6134-115">[in] The constant value for the field.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="c6134-116">[in] \(Unicode) 文字のサイズ`pValue`します。</span><span class="sxs-lookup"><span data-stu-id="c6134-116">[in] The size in (Unicode) characters of `pValue`.</span></span>  
  
 `pmd`  
 <span data-ttu-id="c6134-117">[out]`mdFieldDef`に割り当てられたトークン。</span><span class="sxs-lookup"><span data-stu-id="c6134-117">[out] The `mdFieldDef` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c6134-118">必要条件</span><span class="sxs-lookup"><span data-stu-id="c6134-118">Requirements</span></span>  
 <span data-ttu-id="c6134-119">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c6134-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c6134-120">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="c6134-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c6134-121">**ライブラリ:** MSCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="c6134-121">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c6134-122">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c6134-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6134-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="c6134-123">See also</span></span>
- [<span data-ttu-id="c6134-124">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c6134-124">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="c6134-125">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c6134-125">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
