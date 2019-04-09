---
title: IMetaDataImport::IsGlobal メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataImport.IsGlobal
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::IsGlobal
helpviewer_keywords:
- IsGlobal method [.NET Framework metadata]
- IMetaDataImport::IsGlobal method [.NET Framework metadata]
ms.assetid: 44cf6908-f555-4ae8-b2cf-24bd974bf2fe
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b956ac1717ffcb73e819e985450249754f80af2a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59136163"
---
# <a name="imetadataimportisglobal-method"></a><span data-ttu-id="87ebe-102">IMetaDataImport::IsGlobal メソッド</span><span class="sxs-lookup"><span data-stu-id="87ebe-102">IMetaDataImport::IsGlobal Method</span></span>
<span data-ttu-id="87ebe-103">指定したメタデータ トークンによって表されるフィールド、メソッド、または型がグローバル スコープを保持しているかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="87ebe-103">Gets a value indicating whether the field, method, or type represented by the specified metadata token has global scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87ebe-104">構文</span><span class="sxs-lookup"><span data-stu-id="87ebe-104">Syntax</span></span>  
  
```  
HRESULT IsGlobal (  
   [in]  mdToken     pd,  
   [out] int         *pbGlobal  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="87ebe-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="87ebe-105">Parameters</span></span>  
 `pd`  
 <span data-ttu-id="87ebe-106">[in]型、フィールド、またはメソッドを表すメタデータ トークン。</span><span class="sxs-lookup"><span data-stu-id="87ebe-106">[in] A metadata token that represents a type, field, or method.</span></span>  
  
 `pbGlobal`  
 <span data-ttu-id="87ebe-107">[out] の場合は、1 は、オブジェクトはグローバル スコープは; を持ちます。それ以外の場合、0 (ゼロ)。</span><span class="sxs-lookup"><span data-stu-id="87ebe-107">[out] 1 if the object has global scope; otherwise, 0 (zero).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="87ebe-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="87ebe-108">Requirements</span></span>  
 <span data-ttu-id="87ebe-109">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="87ebe-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="87ebe-110">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="87ebe-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="87ebe-111">**ライブラリ:** MsCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="87ebe-111">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="87ebe-112">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="87ebe-112">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="87ebe-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="87ebe-113">See also</span></span>

- [<span data-ttu-id="87ebe-114">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="87ebe-114">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="87ebe-115">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="87ebe-115">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
