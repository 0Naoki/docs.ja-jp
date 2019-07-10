---
title: IMetaDataEmit::SetCustomAttributeValue メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetCustomAttributeValue
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetCustomAttributeValue
helpviewer_keywords:
- SetCustomAttributeValue method [.NET Framework metadata]
- IMetaDataEmit::SetCustomAttributeValue method [.NET Framework metadata]
ms.assetid: f721c863-9642-4e64-917a-65f9e55c25b9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2a1f248cf800e9c2bf17d7849e449287cfc493f5
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67737208"
---
# <a name="imetadataemitsetcustomattributevalue-method"></a><span data-ttu-id="e647c-102">IMetaDataEmit::SetCustomAttributeValue メソッド</span><span class="sxs-lookup"><span data-stu-id="e647c-102">IMetaDataEmit::SetCustomAttributeValue Method</span></span>
<span data-ttu-id="e647c-103">設定または前回の呼び出しによって定義されたカスタム属性の値を更新[imetadataemit::definecustomattribute](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definecustomattribute-method.md)します。</span><span class="sxs-lookup"><span data-stu-id="e647c-103">Sets or updates the value of a custom attribute defined by a prior call to [IMetaDataEmit::DefineCustomAttribute](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definecustomattribute-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e647c-104">構文</span><span class="sxs-lookup"><span data-stu-id="e647c-104">Syntax</span></span>  
  
```cpp  
HRESULT SetCustomAttributeValue (   
    [in]  mdCustomAttribute       pcv,   
    [in]  void const              *pCustomAttribute,    
    [in]  ULONG                   cbCustomAttribute   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e647c-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e647c-105">Parameters</span></span>  
 `pcv`  
 <span data-ttu-id="e647c-106">[in]対象のカスタム属性のトークンです。</span><span class="sxs-lookup"><span data-stu-id="e647c-106">[in] The token of the target custom attribute.</span></span>  
  
 `pCustomAttribute`  
 <span data-ttu-id="e647c-107">[in]カスタム属性を格納している配列へのポインター。</span><span class="sxs-lookup"><span data-stu-id="e647c-107">[in] A pointer to the array that contains the custom attribute.</span></span>  
  
 `cbCustomAttribute`  
 <span data-ttu-id="e647c-108">[in]カスタム属性のバイト単位のサイズ。</span><span class="sxs-lookup"><span data-stu-id="e647c-108">[in] The size, in bytes, of the custom attribute.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e647c-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="e647c-109">Requirements</span></span>  
 <span data-ttu-id="e647c-110">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e647c-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e647c-111">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="e647c-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e647c-112">**ライブラリ:** MSCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="e647c-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e647c-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e647c-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e647c-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="e647c-114">See also</span></span>

- [<span data-ttu-id="e647c-115">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e647c-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="e647c-116">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e647c-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
