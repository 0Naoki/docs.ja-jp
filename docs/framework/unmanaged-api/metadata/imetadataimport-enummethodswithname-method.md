---
title: IMetaDataImport::EnumMethodsWithName メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumMethodsWithName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumMethodsWithName
helpviewer_keywords:
- IMetaDataImport::EnumMethodsWithName method [.NET Framework metadata]
- EnumMethodsWithName method [.NET Framework metadata]
ms.assetid: a8624913-2e23-46ad-a0c1-bb8eccbbf20f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ab9a8a672095c31c5395251ce9af99667a7eea27
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57498446"
---
# <a name="imetadataimportenummethodswithname-method"></a><span data-ttu-id="d53e9-102">IMetaDataImport::EnumMethodsWithName メソッド</span><span class="sxs-lookup"><span data-stu-id="d53e9-102">IMetaDataImport::EnumMethodsWithName Method</span></span>
<span data-ttu-id="d53e9-103">指定された名前を持ち、指定された TypeDef トークンによって参照される型で定義されているメソッドを列挙します。</span><span class="sxs-lookup"><span data-stu-id="d53e9-103">Enumerates methods that have the specified name and that are defined by the type referenced by the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d53e9-104">構文</span><span class="sxs-lookup"><span data-stu-id="d53e9-104">Syntax</span></span>  
  
```  
HRESULT EnumMethodsWithName (  
   [in, out] HCORENUM    *phEnum,  
   [in]  mdTypeDef       cl,  
   [in]  LPCWSTR         szName,  
   [out] mdMethodDef     rMethods[],  
   [in]  ULONG           cMax,  
   [out] ULONG           *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d53e9-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d53e9-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="d53e9-106">[入力、出力]列挙子へのポインター。</span><span class="sxs-lookup"><span data-stu-id="d53e9-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="d53e9-107">このメソッドの最初の呼び出しで NULL があります。</span><span class="sxs-lookup"><span data-stu-id="d53e9-107">This must be NULL for the first call of this method.</span></span>  
  
 `cl`  
 <span data-ttu-id="d53e9-108">[in]列挙するメソッドを持つ型を表す TypeDef トークンです。</span><span class="sxs-lookup"><span data-stu-id="d53e9-108">[in] A TypeDef token representing the type whose methods to enumerate.</span></span>  
  
 `szName`  
 <span data-ttu-id="d53e9-109">[in]列挙体のスコープを制限する名前です。</span><span class="sxs-lookup"><span data-stu-id="d53e9-109">[in] The name that limits the scope of the enumeration.</span></span>  
  
 `rMethods`  
 <span data-ttu-id="d53e9-110">[out]MethodDef トークンを格納するために使用する配列。</span><span class="sxs-lookup"><span data-stu-id="d53e9-110">[out] The array used to store the MethodDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="d53e9-111">[in] `rMethods` 配列の最大サイズ。</span><span class="sxs-lookup"><span data-stu-id="d53e9-111">[in] The maximum size of the `rMethods` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="d53e9-112">[out]返される MethodDef トークン数`rMethods`します。</span><span class="sxs-lookup"><span data-stu-id="d53e9-112">[out] The number of MethodDef tokens returned in `rMethods`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d53e9-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="d53e9-113">Remarks</span></span>  
 <span data-ttu-id="d53e9-114">このメソッドは、フィールドと、メソッドがないプロパティまたはイベントを列挙します。</span><span class="sxs-lookup"><span data-stu-id="d53e9-114">This method enumerates fields and methods, but not properties or events.</span></span> <span data-ttu-id="d53e9-115">異なり[imetadataimport::enummethods](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enummethods-method.md)、`EnumMethodsWithName`を指定した名前を持たないすべてのメソッドのトークンを破棄します。</span><span class="sxs-lookup"><span data-stu-id="d53e9-115">Unlike [IMetaDataImport::EnumMethods](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enummethods-method.md), `EnumMethodsWithName` discards all method tokens that do not have the specified name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d53e9-116">戻り値</span><span class="sxs-lookup"><span data-stu-id="d53e9-116">Return Value</span></span>  
  
|<span data-ttu-id="d53e9-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d53e9-117">HRESULT</span></span>|<span data-ttu-id="d53e9-118">説明</span><span class="sxs-lookup"><span data-stu-id="d53e9-118">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="d53e9-119">`EnumMethodsWithName` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="d53e9-119">`EnumMethodsWithName` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="d53e9-120">トークンを列挙することはありません。</span><span class="sxs-lookup"><span data-stu-id="d53e9-120">There are no tokens to enumerate.</span></span> <span data-ttu-id="d53e9-121">その場合は、`pcTokens`は 0 です。</span><span class="sxs-lookup"><span data-stu-id="d53e9-121">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d53e9-122">必要条件</span><span class="sxs-lookup"><span data-stu-id="d53e9-122">Requirements</span></span>  
 <span data-ttu-id="d53e9-123">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d53e9-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d53e9-124">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="d53e9-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d53e9-125">**ライブラリ:** MsCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="d53e9-125">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d53e9-126">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d53e9-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d53e9-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="d53e9-127">See also</span></span>
- [<span data-ttu-id="d53e9-128">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d53e9-128">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="d53e9-129">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d53e9-129">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
