---
title: IMetaDataTables2::GetMetaDataStorage メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataTables2.GetMetaDataStorage
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables2::GetMetaDataStorage
helpviewer_keywords:
- GetMetaDataStorage method [.NET Framework metadata]
- IMetaDataTables2::GetMetaDataStorage method [.NET Framework metadata]
ms.assetid: 667a6d1e-753d-4ea2-8fd8-a8337d1bb9cd
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f12243571262ad7511795c48721617932fc6b30b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59161409"
---
# <a name="imetadatatables2getmetadatastorage-method"></a><span data-ttu-id="95754-102">IMetaDataTables2::GetMetaDataStorage メソッド</span><span class="sxs-lookup"><span data-stu-id="95754-102">IMetaDataTables2::GetMetaDataStorage Method</span></span>
<span data-ttu-id="95754-103">指定されたセクションに格納されているメタデータの内容とサイズを取得します。</span><span class="sxs-lookup"><span data-stu-id="95754-103">Gets the size and contents of the metadata stored in the specified section.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95754-104">構文</span><span class="sxs-lookup"><span data-stu-id="95754-104">Syntax</span></span>  
  
```  
HRESULT GetMetaDataStorage (  
   [in, out] const void   **ppvMd,  
   [out] ULONG   *pcbMd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="95754-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="95754-105">Parameters</span></span>  
 `ppvMd`  
 <span data-ttu-id="95754-106">[入力、出力]メタデータ セクションへのポインター。</span><span class="sxs-lookup"><span data-stu-id="95754-106">[in, out] A pointer to a metadata section.</span></span>  
  
 `pcbMd`  
 <span data-ttu-id="95754-107">[out]メタデータ ストリームのサイズ。</span><span class="sxs-lookup"><span data-stu-id="95754-107">[out] The size of the metadata stream.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="95754-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="95754-108">Requirements</span></span>  
 <span data-ttu-id="95754-109">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="95754-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="95754-110">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="95754-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="95754-111">**ライブラリ:** MsCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="95754-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="95754-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="95754-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95754-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="95754-113">See also</span></span>

- [<span data-ttu-id="95754-114">IMetaDataTables2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="95754-114">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
- [<span data-ttu-id="95754-115">IMetaDataTables インターフェイス</span><span class="sxs-lookup"><span data-stu-id="95754-115">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
