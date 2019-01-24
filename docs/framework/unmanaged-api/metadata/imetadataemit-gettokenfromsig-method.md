---
title: IMetaDataEmit::GetTokenFromSig メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.GetTokenFromSig
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::GetTokenFromSig
helpviewer_keywords:
- IMetaDataEmit::GetTokenFromSig method [.NET Framework metadata]
- GetTokenFromSig method [.NET Framework metadata]
ms.assetid: 50a58a83-6287-40a4-b315-47823cea0a5c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 940d913b2b04a510e2ae0e33eaa78b07ba4237c2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54676797"
---
# <a name="imetadataemitgettokenfromsig-method"></a><span data-ttu-id="0edf9-102">IMetaDataEmit::GetTokenFromSig メソッド</span><span class="sxs-lookup"><span data-stu-id="0edf9-102">IMetaDataEmit::GetTokenFromSig Method</span></span>
<span data-ttu-id="0edf9-103">指定されたメタデータ署名のトークンを取得します。</span><span class="sxs-lookup"><span data-stu-id="0edf9-103">Gets a token for the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0edf9-104">構文</span><span class="sxs-lookup"><span data-stu-id="0edf9-104">Syntax</span></span>  
  
```  
HRESULT GetTokenFromSig (   
    [in]  PCCOR_SIGNATURE pvSig,   
    [in]  ULONG       cbSig,   
    [out] mdSignature *pmsig   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0edf9-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0edf9-105">Parameters</span></span>  
 `pvSig`  
 <span data-ttu-id="0edf9-106">[in]永続化して、格納されている署名。</span><span class="sxs-lookup"><span data-stu-id="0edf9-106">[in] The signature to be persisted and stored.</span></span>  
  
 `cbSig`  
 <span data-ttu-id="0edf9-107">[in]内のバイト数`pvSig`します。</span><span class="sxs-lookup"><span data-stu-id="0edf9-107">[in] The count of bytes in `pvSig`.</span></span>  
  
 `pmsig`  
 <span data-ttu-id="0edf9-108">[out]`mdSignature`に割り当てられたトークン。</span><span class="sxs-lookup"><span data-stu-id="0edf9-108">[out] The `mdSignature` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0edf9-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="0edf9-109">Requirements</span></span>  
 <span data-ttu-id="0edf9-110">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0edf9-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0edf9-111">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="0edf9-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0edf9-112">**ライブラリ:** MSCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="0edf9-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0edf9-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0edf9-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0edf9-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="0edf9-114">See also</span></span>
- [<span data-ttu-id="0edf9-115">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0edf9-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="0edf9-116">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0edf9-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
