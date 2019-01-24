---
title: IMetaDataEmit::SetMethodImplFlags メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetMethodImplFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetMethodImplFlags
helpviewer_keywords:
- IMetaDataEmit::SetMethodImplFlags method [.NET Framework metadata]
- SetMethodImpFlags method [.NET Framework metadata]
ms.assetid: 4bc82d9b-9544-4be3-ba51-a2d4d806158a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: cffbf01cb8098f30fb026491e0153ac9a651756a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54692394"
---
# <a name="imetadataemitsetmethodimplflags-method"></a><span data-ttu-id="38a54-102">IMetaDataEmit::SetMethodImplFlags メソッド</span><span class="sxs-lookup"><span data-stu-id="38a54-102">IMetaDataEmit::SetMethodImplFlags Method</span></span>
<span data-ttu-id="38a54-103">設定または指定したトークンによって参照されている継承されたメソッドの実装のメタデータ シグネチャを更新します。</span><span class="sxs-lookup"><span data-stu-id="38a54-103">Sets or updates the metadata signature of the inherited method implementation that is referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38a54-104">構文</span><span class="sxs-lookup"><span data-stu-id="38a54-104">Syntax</span></span>  
  
```  
HRESULT SetMethodImplFlags (   
    [in]  mdMethodDef   md,   
    [in]  DWORD         dwImplFlags   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="38a54-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="38a54-105">Parameters</span></span>  
 `md`  
 <span data-ttu-id="38a54-106">[in]変更するメソッドのトークン。</span><span class="sxs-lookup"><span data-stu-id="38a54-106">[in] The token for the method to be changed.</span></span>  
  
 `dwImplFlags`  
 <span data-ttu-id="38a54-107">[in]値の組み合わせ、 [CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md)メソッドの実装の機能を指定する列挙体。</span><span class="sxs-lookup"><span data-stu-id="38a54-107">[in] A combination of the values of the [CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md) enumeration that specifies the method implementation features.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="38a54-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="38a54-108">Requirements</span></span>  
 <span data-ttu-id="38a54-109">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="38a54-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="38a54-110">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="38a54-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="38a54-111">**ライブラリ:** MSCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="38a54-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="38a54-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="38a54-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38a54-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="38a54-113">See also</span></span>
- [<span data-ttu-id="38a54-114">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="38a54-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="38a54-115">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="38a54-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
