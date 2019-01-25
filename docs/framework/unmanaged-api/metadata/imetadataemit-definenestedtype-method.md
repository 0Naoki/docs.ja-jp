---
title: IMetaDataEmit::DefineNestedType メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineNestedType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineNestedType
helpviewer_keywords:
- IMetaDataEmit::DefineNestedType method [.NET Framework metadata]
- DefineNestedType method [.NET Framework metadata]
ms.assetid: 1e994de6-4628-459c-b967-b34be1e9fe4f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ee8e0dec469c7389a69c70567d7b2cb98d3404e6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54603912"
---
# <a name="imetadataemitdefinenestedtype-method"></a><span data-ttu-id="75c36-102">IMetaDataEmit::DefineNestedType メソッド</span><span class="sxs-lookup"><span data-stu-id="75c36-102">IMetaDataEmit::DefineNestedType Method</span></span>
<span data-ttu-id="75c36-103">型定義のメタデータ署名を作成し、返します、 `mdTypeDef` 、その型のトークンし、定義された型によって参照される型のメンバーであることを指定します、`tdEncloser`パラメーター。</span><span class="sxs-lookup"><span data-stu-id="75c36-103">Creates the metadata signature of a type definition, returns an `mdTypeDef` token for that type, and specifies that the defined type is a member of the type referenced by the `tdEncloser` parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75c36-104">構文</span><span class="sxs-lookup"><span data-stu-id="75c36-104">Syntax</span></span>  
  
```  
HRESULT DefineNestedType (   
    [in]  LPCWSTR     szTypeDef,  
    [in]  DWORD       dwTypeDefFlags,   
    [in]  mdToken     tkExtends,   
    [in]  mdToken     rtkImplements[],   
    [in]  mdTypeDef   tdEncloser,   
    [out] mdTypeDef   *ptd  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="75c36-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="75c36-105">Parameters</span></span>  
 `szTypeDef`  
 <span data-ttu-id="75c36-106">[in]Unicode での型の名前。</span><span class="sxs-lookup"><span data-stu-id="75c36-106">[in] The name of the type in Unicode.</span></span>  
  
 `dwTypeDefFlags`  
 <span data-ttu-id="75c36-107">[in]`TypeDef`属性。</span><span class="sxs-lookup"><span data-stu-id="75c36-107">[in] `TypeDef` attributes.</span></span> <span data-ttu-id="75c36-108">これは、ビットマスクの`CorTypeAttr`値。</span><span class="sxs-lookup"><span data-stu-id="75c36-108">This is a bitmask of `CorTypeAttr` values.</span></span>  
  
 `tkExtends`  
 <span data-ttu-id="75c36-109">[in]基底クラスのトークンです。</span><span class="sxs-lookup"><span data-stu-id="75c36-109">[in] The token of the base class.</span></span> <span data-ttu-id="75c36-110">いずれかになります、`mdTypeDef`または`mdTypeRef`トークンです。</span><span class="sxs-lookup"><span data-stu-id="75c36-110">This is either a `mdTypeDef` or a `mdTypeRef` token.</span></span>  
  
 <span data-ttu-id="75c36-111">`rtkImplements`[]</span><span class="sxs-lookup"><span data-stu-id="75c36-111">`rtkImplements`[]</span></span>  
 <span data-ttu-id="75c36-112">[in]このクラスまたはインターフェイスを実装するインターフェイスを指定するトークンの配列。</span><span class="sxs-lookup"><span data-stu-id="75c36-112">[in] An array of tokens that specify the interfaces that this class or interface implements.</span></span>  
  
 `tdEncloser`  
 <span data-ttu-id="75c36-113">[in]それを囲む型のトークンです。</span><span class="sxs-lookup"><span data-stu-id="75c36-113">[in] The token of the enclosing type.</span></span> <span data-ttu-id="75c36-114">配列の最後の要素である必要があります`mdTokenNil`します。</span><span class="sxs-lookup"><span data-stu-id="75c36-114">The last element of the array must be `mdTokenNil`.</span></span>  
  
 `ptd`  
 <span data-ttu-id="75c36-115">[out]`mdTypeDef`に割り当てられたトークン。</span><span class="sxs-lookup"><span data-stu-id="75c36-115">[out] The `mdTypeDef` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="75c36-116">必要条件</span><span class="sxs-lookup"><span data-stu-id="75c36-116">Requirements</span></span>  
 <span data-ttu-id="75c36-117">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="75c36-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="75c36-118">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="75c36-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="75c36-119">**ライブラリ:** MSCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="75c36-119">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="75c36-120">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="75c36-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75c36-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="75c36-121">See also</span></span>
- [<span data-ttu-id="75c36-122">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="75c36-122">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="75c36-123">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="75c36-123">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
