---
title: IMetaDataTables::GetTableInfo メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetTableInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetTableInfo
helpviewer_keywords:
- IMetaDataTables::GetTableInfo method [.NET Framework metadata]
- GetTableInfo method [.NET Framework metadata]
ms.assetid: 50cbe557-2322-41aa-8e0d-f967602eaa0f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9bf3e5d427698673576f71e290fde54275b75317
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54683457"
---
# <a name="imetadatatablesgettableinfo-method"></a><span data-ttu-id="d9209-102">IMetaDataTables::GetTableInfo メソッド</span><span class="sxs-lookup"><span data-stu-id="d9209-102">IMetaDataTables::GetTableInfo Method</span></span>
<span data-ttu-id="d9209-103">名、行のサイズ、行の数、列の数と、指定したテーブルのキー列のインデックスを取得します。</span><span class="sxs-lookup"><span data-stu-id="d9209-103">Gets the name, row size, number of rows, number of columns, and key column index of the specified table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9209-104">構文</span><span class="sxs-lookup"><span data-stu-id="d9209-104">Syntax</span></span>  
  
```  
HRESULT GetTableInfo (  
    [in]  ULONG       ixTbl,  
    [out] ULONG       *pcbRow,  
    [out] ULONG       *pcRows,  
    [out] ULONG       *pcCols,  
    [out] ULONG       *piKey,  
    [out] const char  **ppName  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d9209-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d9209-105">Parameters</span></span>  
 `ixTbl`  
 <span data-ttu-id="d9209-106">[in]テーブルの識別子を返すプロパティを持つ。</span><span class="sxs-lookup"><span data-stu-id="d9209-106">[in] The identifier of the table whose properties to return.</span></span>  
  
 `pcbRow`  
 <span data-ttu-id="d9209-107">[out]サイズ (バイト単位)、テーブルの行へのポインター。</span><span class="sxs-lookup"><span data-stu-id="d9209-107">[out] A pointer to the size, in bytes, of a table row.</span></span>  
  
 `pcRows`  
 <span data-ttu-id="d9209-108">[out]テーブル内の行の数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="d9209-108">[out] A pointer to the number of rows in the table.</span></span>  
  
 `pcCols`  
 <span data-ttu-id="d9209-109">[out]テーブル内の列の数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="d9209-109">[out] A pointer to the number of columns in the table.</span></span>  
  
 `piKey`  
 <span data-ttu-id="d9209-110">[out]キーの列またはテーブルにキー列があるない場合は-1 のインデックスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="d9209-110">[out] A pointer to the index of the key column, or -1 if the table has no key column.</span></span>  
  
 `ppName`  
 <span data-ttu-id="d9209-111">[out]テーブル名へのポインターへのポインター。</span><span class="sxs-lookup"><span data-stu-id="d9209-111">[out] A pointer to a pointer to the table name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d9209-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="d9209-112">Requirements</span></span>  
 <span data-ttu-id="d9209-113">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d9209-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d9209-114">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="d9209-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d9209-115">**ライブラリ:** MsCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="d9209-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d9209-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d9209-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9209-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="d9209-117">See also</span></span>
- [<span data-ttu-id="d9209-118">IMetaDataTables インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d9209-118">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="d9209-119">IMetaDataTables2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d9209-119">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
