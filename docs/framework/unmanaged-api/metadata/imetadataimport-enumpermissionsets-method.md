---
title: IMetaDataImport::EnumPermissionSets メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumPermissionSets
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumPermissionSets
helpviewer_keywords:
- EnumPermissionSets method [.NET Framework metadata]
- IMetaDataImport::EnumPermissionSets method [.NET Framework metadata]
ms.assetid: 347d7e5c-c90f-45ad-bd1e-2c7912b0b19c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 990910b8b30e9794550d71cf9eaf8cd53639f696
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57492245"
---
# <a name="imetadataimportenumpermissionsets-method"></a><span data-ttu-id="074ab-102">IMetaDataImport::EnumPermissionSets メソッド</span><span class="sxs-lookup"><span data-stu-id="074ab-102">IMetaDataImport::EnumPermissionSets Method</span></span>
<span data-ttu-id="074ab-103">指定したメタデータ スコープ内のオブジェクトのアクセス許可を列挙します。</span><span class="sxs-lookup"><span data-stu-id="074ab-103">Enumerates permissions for the objects in a specified metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="074ab-104">構文</span><span class="sxs-lookup"><span data-stu-id="074ab-104">Syntax</span></span>  
  
```  
HRESULT EnumPermissionSets  
   [in, out] HCORENUM      *phEnum,   
   [in]      mdToken       tk,   
   [in]      DWORD         dwActions,  
   [out]     mdPermission  rPermission[],  
   [in]      ULONG         cMax,  
   [out]     ULONG         *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="074ab-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="074ab-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="074ab-106">[入力、出力]列挙子へのポインター。</span><span class="sxs-lookup"><span data-stu-id="074ab-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="074ab-107">このメソッドの最初の呼び出しで NULL があります。</span><span class="sxs-lookup"><span data-stu-id="074ab-107">This must be NULL for the first call of this method.</span></span>  
  
 `tk`  
 <span data-ttu-id="074ab-108">[in]できるだけ広い範囲を検索する検索のスコープを制限するメタデータ トークンです。</span><span class="sxs-lookup"><span data-stu-id="074ab-108">[in] A metadata token that limits the scope of the search, or NULL to search the widest scope possible.</span></span>  
  
 `dwActions`  
 <span data-ttu-id="074ab-109">[in]フラグを表す、<xref:System.Security.Permissions.SecurityAction>に含める値`rPermission`、またはすべてのアクションを返す 0。</span><span class="sxs-lookup"><span data-stu-id="074ab-109">[in] Flags representing the <xref:System.Security.Permissions.SecurityAction> values to include in `rPermission`, or zero to return all actions.</span></span>  
  
 `rPermission`  
 <span data-ttu-id="074ab-110">[out]アクセス許可のトークンを格納するために使用する配列。</span><span class="sxs-lookup"><span data-stu-id="074ab-110">[out] The array used to store the Permission tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="074ab-111">[in] `rPermission` 配列の最大サイズ。</span><span class="sxs-lookup"><span data-stu-id="074ab-111">[in] The maximum size of the `rPermission` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="074ab-112">[out]アクセス許可のトークンで返される数`rPermission`します。</span><span class="sxs-lookup"><span data-stu-id="074ab-112">[out] The number of Permission tokens returned in `rPermission`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="074ab-113">戻り値</span><span class="sxs-lookup"><span data-stu-id="074ab-113">Return Value</span></span>  
  
|<span data-ttu-id="074ab-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="074ab-114">HRESULT</span></span>|<span data-ttu-id="074ab-115">説明</span><span class="sxs-lookup"><span data-stu-id="074ab-115">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="074ab-116">`EnumPermissionSets` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="074ab-116">`EnumPermissionSets` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="074ab-117">トークンを列挙することはありません。</span><span class="sxs-lookup"><span data-stu-id="074ab-117">There are no tokens to enumerate.</span></span> <span data-ttu-id="074ab-118">その場合は、`pcTokens`は 0 です。</span><span class="sxs-lookup"><span data-stu-id="074ab-118">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="074ab-119">必要条件</span><span class="sxs-lookup"><span data-stu-id="074ab-119">Requirements</span></span>  
 <span data-ttu-id="074ab-120">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="074ab-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="074ab-121">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="074ab-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="074ab-122">**ライブラリ:** MsCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="074ab-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="074ab-123">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="074ab-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="074ab-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="074ab-124">See also</span></span>
- [<span data-ttu-id="074ab-125">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="074ab-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="074ab-126">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="074ab-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
