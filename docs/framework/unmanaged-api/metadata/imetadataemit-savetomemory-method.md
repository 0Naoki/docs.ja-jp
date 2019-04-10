---
title: IMetaDataEmit::SaveToMemory メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SaveToMemory
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SaveToMemory
helpviewer_keywords:
- IMetaDataEmit::SaveToMemory method [.NET Framework metadata]
- SaveToMemory method [.NET Framework metadata]
ms.assetid: d5237628-2675-45ed-a39e-65c0731b6a56
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bc840df9dd0793a7347b7f0d8a05296a09d634c8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59192109"
---
# <a name="imetadataemitsavetomemory-method"></a><span data-ttu-id="a092a-102">IMetaDataEmit::SaveToMemory メソッド</span><span class="sxs-lookup"><span data-stu-id="a092a-102">IMetaDataEmit::SaveToMemory Method</span></span>
<span data-ttu-id="a092a-103">メモリの指定された領域を現在のスコープ内のすべてのメタデータを保存します。</span><span class="sxs-lookup"><span data-stu-id="a092a-103">Saves all metadata in the current scope to the specified area of memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a092a-104">構文</span><span class="sxs-lookup"><span data-stu-id="a092a-104">Syntax</span></span>  
  
```  
HRESULT SaveToMemory (   
    [out]  void        *pbData,   
    [in]   ULONG       cbData   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a092a-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a092a-105">Parameters</span></span>  
 `pbData`  
 <span data-ttu-id="a092a-106">[out]メタデータの書き込みを開始する位置のアドレス。</span><span class="sxs-lookup"><span data-stu-id="a092a-106">[out] The address at which to begin writing metadata.</span></span>  
  
 `cbData`  
 <span data-ttu-id="a092a-107">[in]割り当てられたメモリのバイト単位のサイズ。</span><span class="sxs-lookup"><span data-stu-id="a092a-107">[in] The size, in bytes, of the allocated memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a092a-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="a092a-108">Requirements</span></span>  
 <span data-ttu-id="a092a-109">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a092a-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a092a-110">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="a092a-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a092a-111">**ライブラリ:** MSCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="a092a-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="a092a-112">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="a092a-112">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a092a-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="a092a-113">See also</span></span>

- [<span data-ttu-id="a092a-114">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a092a-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="a092a-115">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a092a-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
