---
title: IMetaDataTables::GetNextBlob メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetNextBlob
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetNextBlob
helpviewer_keywords:
- IMetaDataTables::GetNextBlob method [.NET Framework metadata]
- GetNextBlob method [.NET Framework metadata]
ms.assetid: 017c8ab4-4c09-4754-9935-5b0b49cabecb
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9b8a91a2c1ef9b68dcfc293a870ce3e9b9499a8f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59204602"
---
# <a name="imetadatatablesgetnextblob-method"></a><span data-ttu-id="cbec9-102">IMetaDataTables::GetNextBlob メソッド</span><span class="sxs-lookup"><span data-stu-id="cbec9-102">IMetaDataTables::GetNextBlob Method</span></span>
<span data-ttu-id="cbec9-103">テーブル内には、次のバイナリ ラージ オブジェクト (BLOB) のインデックスを取得します。</span><span class="sxs-lookup"><span data-stu-id="cbec9-103">Gets the index of the next binary large object (BLOB) in the table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cbec9-104">構文</span><span class="sxs-lookup"><span data-stu-id="cbec9-104">Syntax</span></span>  
  
```  
HRESULT GetNextBlob (  
    [in]  ULONG   ixBlob,  
    [out] ULONG   *pNext  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cbec9-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="cbec9-105">Parameters</span></span>  
 `ixBlob`  
 <span data-ttu-id="cbec9-106">[in]Blob の列から返されるインデックス。</span><span class="sxs-lookup"><span data-stu-id="cbec9-106">[in] The index, as returned from a column of BLOBs.</span></span>  
  
 `pNext`  
 <span data-ttu-id="cbec9-107">[out]次の BLOB のインデックスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="cbec9-107">[out] A pointer to the index of the next BLOB.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cbec9-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="cbec9-108">Requirements</span></span>  
 <span data-ttu-id="cbec9-109">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cbec9-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cbec9-110">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="cbec9-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="cbec9-111">**ライブラリ:** MsCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="cbec9-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="cbec9-112">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="cbec9-112">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="cbec9-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="cbec9-113">See also</span></span>

- [<span data-ttu-id="cbec9-114">IMetaDataTables インターフェイス</span><span class="sxs-lookup"><span data-stu-id="cbec9-114">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="cbec9-115">IMetaDataTables2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="cbec9-115">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
