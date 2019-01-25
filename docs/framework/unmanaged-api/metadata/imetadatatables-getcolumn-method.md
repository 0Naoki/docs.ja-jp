---
title: IMetaDataTables::GetColumn メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetColumn
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetColumn
helpviewer_keywords:
- IMetaDataTables::GetColumn method [.NET Framework metadata]
- GetColumn method [.NET Framework metadata]
ms.assetid: 1032055b-cabb-45c5-a50e-7e853201b175
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a88acf59043613bb216ffe84dfb1593bd6ebea00
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54651891"
---
# <a name="imetadatatablesgetcolumn-method"></a><span data-ttu-id="2948e-102">IMetaDataTables::GetColumn メソッド</span><span class="sxs-lookup"><span data-stu-id="2948e-102">IMetaDataTables::GetColumn Method</span></span>
<span data-ttu-id="2948e-103">指定した列と指定されたテーブル内の行のセルに含まれる値にポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="2948e-103">Gets a pointer to the value contained in the cell of the specified column and row in the given table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2948e-104">構文</span><span class="sxs-lookup"><span data-stu-id="2948e-104">Syntax</span></span>  
  
```  
HRESULT GetColumn (   
    [in]  ULONG   ixTbl,  
    [in]  ULONG   ixCol,  
    [in]  ULONG   rid,  
    [out] ULONG   *pVal  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2948e-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2948e-105">Parameters</span></span>  
 `ixTbl`  
 <span data-ttu-id="2948e-106">[in]テーブルのインデックス。</span><span class="sxs-lookup"><span data-stu-id="2948e-106">[in] The index of the table.</span></span>  
  
 `ixCol`  
 <span data-ttu-id="2948e-107">[in]テーブルの列のインデックス。</span><span class="sxs-lookup"><span data-stu-id="2948e-107">[in] The index of the column in the table.</span></span>  
  
 `rid`  
 <span data-ttu-id="2948e-108">[in]テーブルの行のインデックス。</span><span class="sxs-lookup"><span data-stu-id="2948e-108">[in] The index of the row in the table.</span></span>  
  
 `pVal`  
 <span data-ttu-id="2948e-109">[out]セルの値へのポインター。</span><span class="sxs-lookup"><span data-stu-id="2948e-109">[out] A pointer to the value in the cell.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2948e-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="2948e-110">Requirements</span></span>  
 <span data-ttu-id="2948e-111">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2948e-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2948e-112">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="2948e-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2948e-113">**ライブラリ:** MsCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="2948e-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2948e-114">**.NET framework のバージョン** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2948e-114">**.NET Framework Versions** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2948e-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="2948e-115">See also</span></span>
- [<span data-ttu-id="2948e-116">IMetaDataTables インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2948e-116">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="2948e-117">IMetaDataTables2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2948e-117">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
