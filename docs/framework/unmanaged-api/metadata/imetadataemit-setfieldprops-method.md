---
title: IMetaDataEmit::SetFieldProps メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetFieldProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetFieldProps
helpviewer_keywords:
- IMetaDataEmit::SetFieldProps method [.NET Framework metadata]
- SetFieldProps method [.NET Framework metadata]
ms.assetid: 47132dda-fa92-4bd1-ae4b-24cd9a60665a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 94ba607669b4b1ca68294470cf1cc4fb27464d28
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61992486"
---
# <a name="imetadataemitsetfieldprops-method"></a><span data-ttu-id="aa248-102">IMetaDataEmit::SetFieldProps メソッド</span><span class="sxs-lookup"><span data-stu-id="aa248-102">IMetaDataEmit::SetFieldProps Method</span></span>
<span data-ttu-id="aa248-103">設定または指定したフィールドのトークンによって参照されるフィールドの既定値を更新します。</span><span class="sxs-lookup"><span data-stu-id="aa248-103">Sets or updates the default value for the field referenced by the specified field token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa248-104">構文</span><span class="sxs-lookup"><span data-stu-id="aa248-104">Syntax</span></span>  
  
```  
HRESULT SetFieldProps (  
    [in]  mdFieldDef  fd,   
    [in]  DWORD       dwFieldFlags,   
    [in]  DWORD       dwCPlusTypeFlag,   
    [in]  void const  *pValue,   
    [in]  ULONG       cchValue   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="aa248-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="aa248-105">Parameters</span></span>  
 `fd`  
 <span data-ttu-id="aa248-106">[in]対象フィールドのトークンです。</span><span class="sxs-lookup"><span data-stu-id="aa248-106">[in] The token for the target field.</span></span>  
  
 `dwFieldFlags`  
 <span data-ttu-id="aa248-107">[in]フィールドの属性。</span><span class="sxs-lookup"><span data-stu-id="aa248-107">[in] Field attributes.</span></span> <span data-ttu-id="aa248-108">これは、ビットマスクの`CorFieldAttr`値。</span><span class="sxs-lookup"><span data-stu-id="aa248-108">This is a bitmask of `CorFieldAttr` values.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="aa248-109">[in]`ELEMENT_TYPE_` *\** 定数の値。</span><span class="sxs-lookup"><span data-stu-id="aa248-109">[in] The `ELEMENT_TYPE_`*\** for the constant value.</span></span> <span data-ttu-id="aa248-110">これは、`CorElementType`値。</span><span class="sxs-lookup"><span data-stu-id="aa248-110">This is a `CorElementType` value.</span></span> <span data-ttu-id="aa248-111">定数が定義されていない場合は、この値を設定`ELEMENT_TYPE_END`します。</span><span class="sxs-lookup"><span data-stu-id="aa248-111">If a constant is not being defined, set this value to `ELEMENT_TYPE_END`.</span></span>  
  
 `pValue`  
 <span data-ttu-id="aa248-112">[in]フィールドの定数値。</span><span class="sxs-lookup"><span data-stu-id="aa248-112">[in] The constant value for the field.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="aa248-113">[in]Unicode 文字で、サイズの`pValue`します。</span><span class="sxs-lookup"><span data-stu-id="aa248-113">[in] The size, in Unicode characters, of `pValue`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aa248-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="aa248-114">Requirements</span></span>  
 <span data-ttu-id="aa248-115">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="aa248-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aa248-116">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="aa248-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="aa248-117">**ライブラリ:** MSCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="aa248-117">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="aa248-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aa248-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa248-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="aa248-119">See also</span></span>

- [<span data-ttu-id="aa248-120">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="aa248-120">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="aa248-121">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="aa248-121">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
