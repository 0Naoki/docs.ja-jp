---
title: IMetaDataEmit::SetParent メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetParent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetParent
helpviewer_keywords:
- SetParent method [.NET Framework metadata]
- IMetaDataEmit::SetParent method [.NET Framework metadata]
ms.assetid: 02a02ff7-ae0e-4692-a20e-372405f23052
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1a37edd38cd8dc6971ee9185f73d6c6d8ab5332b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54657132"
---
# <a name="imetadataemitsetparent-method"></a><span data-ttu-id="097e6-102">IMetaDataEmit::SetParent メソッド</span><span class="sxs-lookup"><span data-stu-id="097e6-102">IMetaDataEmit::SetParent Method</span></span>
<span data-ttu-id="097e6-103">確立する前回の呼び出しで定義されている、指定されたメンバー [imetadataemit::definememberref](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md)、前回の呼び出しで定義されている、指定した型のメンバーである[imetadataemit::definetypedef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md)します。</span><span class="sxs-lookup"><span data-stu-id="097e6-103">Establishes that the specified member, as defined by a prior call to [IMetaDataEmit::DefineMemberRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md), is a member of the specified type, as defined by a prior call to [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="097e6-104">構文</span><span class="sxs-lookup"><span data-stu-id="097e6-104">Syntax</span></span>  
  
```  
HRESULT SetParent (   
    [in]  mdMemberRef mr,   
    [in]  mdToken     tk   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="097e6-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="097e6-105">Parameters</span></span>  
 `mr`  
 <span data-ttu-id="097e6-106">[in]`mdMemberRef`新しい親を受信するトークン。</span><span class="sxs-lookup"><span data-stu-id="097e6-106">[in] The `mdMemberRef` token to receive a new parent.</span></span>  
  
 `tk`  
 <span data-ttu-id="097e6-107">[in]`mdToken`新しい親。</span><span class="sxs-lookup"><span data-stu-id="097e6-107">[in] The `mdToken` for the new parent.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="097e6-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="097e6-108">Requirements</span></span>  
 <span data-ttu-id="097e6-109">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="097e6-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="097e6-110">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="097e6-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="097e6-111">**ライブラリ:** MSCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="097e6-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="097e6-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="097e6-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="097e6-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="097e6-113">See also</span></span>
- [<span data-ttu-id="097e6-114">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="097e6-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="097e6-115">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="097e6-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
