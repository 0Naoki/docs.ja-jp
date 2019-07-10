---
title: IMetaDataImport::EnumCustomAttributes メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumCustomAttributes
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumCustomAttributes
helpviewer_keywords:
- EnumCustomAttributes method [.NET Framework metadata]
- IMetaDataImport::EnumCustomAttributes method [.NET Framework metadata]
ms.assetid: 798513a0-68b1-4d04-bc5b-782a4445ea68
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c38b7f060c34f7408195484dec2c49305db422fe
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781318"
---
# <a name="imetadataimportenumcustomattributes-method"></a><span data-ttu-id="c868c-102">IMetaDataImport::EnumCustomAttributes メソッド</span><span class="sxs-lookup"><span data-stu-id="c868c-102">IMetaDataImport::EnumCustomAttributes Method</span></span>
<span data-ttu-id="c868c-103">指定した型またはメンバーに関連付けられたカスタム属性定義トークンを列挙します。</span><span class="sxs-lookup"><span data-stu-id="c868c-103">Enumerates custom attribute-definition tokens associated with the specified type or member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c868c-104">構文</span><span class="sxs-lookup"><span data-stu-id="c868c-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumCustomAttributes (   
   [in, out] HCORENUM      *phEnum,  
   [in]  mdToken            tk,   
   [in]  mdToken            tkType,   
   [out] mdCustomAttribute  rCustomAttributes[],   
   [in]  ULONG              cMax,  
   [out, optional] ULONG   *pcCustomAttributes  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c868c-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c868c-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="c868c-106">[入力、出力]返された列挙子へのポインター。</span><span class="sxs-lookup"><span data-stu-id="c868c-106">[in, out] A pointer to the returned enumerator.</span></span>  
  
 `tk`  
 <span data-ttu-id="c868c-107">[in]列挙体、またはすべてのカスタム属性に 0 のスコープのトークンです。</span><span class="sxs-lookup"><span data-stu-id="c868c-107">[in] A token for the scope of the enumeration, or zero for all custom attributes.</span></span>  
  
 `tkType`  
 <span data-ttu-id="c868c-108">[in]列挙するには、属性の型のコンス トラクターのトークンまたは`null`すべての種類。</span><span class="sxs-lookup"><span data-stu-id="c868c-108">[in] A token for the constructor of the type of the attributes to be enumerated, or `null` for all types.</span></span>  
  
 `rCustomAttributes`  
 <span data-ttu-id="c868c-109">[out]トークンのカスタム属性の配列。</span><span class="sxs-lookup"><span data-stu-id="c868c-109">[out] An array of custom attribute tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="c868c-110">[in] `rCustomAttributes` 配列の最大サイズ。</span><span class="sxs-lookup"><span data-stu-id="c868c-110">[in] The maximum size of the `rCustomAttributes` array.</span></span>  
  
 `pcCustomAttributes`  
 <span data-ttu-id="c868c-111">[out] 省略可能実際に返されるトークンの値数`rCustomAttributes`します。</span><span class="sxs-lookup"><span data-stu-id="c868c-111">[out, optional] The actual number of token values returned in `rCustomAttributes`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c868c-112">戻り値</span><span class="sxs-lookup"><span data-stu-id="c868c-112">Return Value</span></span>  
  
|<span data-ttu-id="c868c-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c868c-113">HRESULT</span></span>|<span data-ttu-id="c868c-114">説明</span><span class="sxs-lookup"><span data-stu-id="c868c-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="c868c-115">`EnumCustomAttributes` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="c868c-115">`EnumCustomAttributes` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="c868c-116">カスタム属性を列挙することはありません。</span><span class="sxs-lookup"><span data-stu-id="c868c-116">There are no custom attributes to enumerate.</span></span> <span data-ttu-id="c868c-117">その場合は、`pcCustomAttributes`は 0 です。</span><span class="sxs-lookup"><span data-stu-id="c868c-117">In that case, `pcCustomAttributes` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c868c-118">必要条件</span><span class="sxs-lookup"><span data-stu-id="c868c-118">Requirements</span></span>  
 <span data-ttu-id="c868c-119">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c868c-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c868c-120">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="c868c-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c868c-121">**ライブラリ:** MsCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="c868c-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c868c-122">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c868c-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c868c-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="c868c-123">See also</span></span>

- [<span data-ttu-id="c868c-124">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c868c-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="c868c-125">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c868c-125">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
