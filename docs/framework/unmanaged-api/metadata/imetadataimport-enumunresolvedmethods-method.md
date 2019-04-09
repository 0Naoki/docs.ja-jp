---
title: IMetaDataImport::EnumUnresolvedMethods メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumUnresolvedMethods
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumUnresolvedMethods
helpviewer_keywords:
- EnumUnresolvedMethods method [.NET Framework metadata]
- IMetaDataImport::EnumUnresolvedMethods method [.NET Framework metadata]
ms.assetid: eb3187d7-74cf-44b1-aeeb-7a8d2b60e3b7
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2e6e53f69f58c2f5778083d9b8f8be466b952cdd
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59090252"
---
# <a name="imetadataimportenumunresolvedmethods-method"></a><span data-ttu-id="c899d-102">IMetaDataImport::EnumUnresolvedMethods メソッド</span><span class="sxs-lookup"><span data-stu-id="c899d-102">IMetaDataImport::EnumUnresolvedMethods Method</span></span>
<span data-ttu-id="c899d-103">現在のメタデータ スコープ内の未解決のメソッドを表す MemberDef トークンを列挙します。</span><span class="sxs-lookup"><span data-stu-id="c899d-103">Enumerates MemberDef tokens representing the unresolved methods in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c899d-104">構文</span><span class="sxs-lookup"><span data-stu-id="c899d-104">Syntax</span></span>  
  
```  
HRESULT EnumUnresolvedMethods (  
   [in, out] HCORENUM    *phEnum,  
   [out]     mdToken     rMethods[],  
   [in]      ULONG       cMax,  
   [out]     ULONG       *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c899d-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c899d-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="c899d-106">[入力、出力]列挙子へのポインター。</span><span class="sxs-lookup"><span data-stu-id="c899d-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="c899d-107">このメソッドの最初の呼び出しで NULL があります。</span><span class="sxs-lookup"><span data-stu-id="c899d-107">This must be NULL for the first call of this method.</span></span>  
  
 `rMethods`  
 <span data-ttu-id="c899d-108">[out]MemberDef トークンを格納するために使用する配列。</span><span class="sxs-lookup"><span data-stu-id="c899d-108">[out] The array used to store the MemberDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="c899d-109">[in] `rMethods` 配列の最大サイズ。</span><span class="sxs-lookup"><span data-stu-id="c899d-109">[in] The maximum size of the `rMethods` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="c899d-110">[out]返される MemberDef トークン数`rMethods`します。</span><span class="sxs-lookup"><span data-stu-id="c899d-110">[out] The number of MemberDef tokens returned in `rMethods`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c899d-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="c899d-111">Return Value</span></span>  
  
|<span data-ttu-id="c899d-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c899d-112">HRESULT</span></span>|<span data-ttu-id="c899d-113">説明</span><span class="sxs-lookup"><span data-stu-id="c899d-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|`EnumUnresolvedMethods` <span data-ttu-id="c899d-114">正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="c899d-114">returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="c899d-115">トークンを列挙することはありません。</span><span class="sxs-lookup"><span data-stu-id="c899d-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="c899d-116">その場合は、`pcTokens`は 0 です。</span><span class="sxs-lookup"><span data-stu-id="c899d-116">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c899d-117">Remarks</span><span class="sxs-lookup"><span data-stu-id="c899d-117">Remarks</span></span>  
 <span data-ttu-id="c899d-118">未解決のメソッドは宣言されましたが、実装されていません。</span><span class="sxs-lookup"><span data-stu-id="c899d-118">An unresolved method is one that has been declared but not implemented.</span></span> <span data-ttu-id="c899d-119">メソッドがマークされている場合に、列挙体のメソッドが含まれている`miForwardRef`、`mdPinvokeImpl`または`miRuntime`0 に設定されます。</span><span class="sxs-lookup"><span data-stu-id="c899d-119">A method is included in the enumeration if the method is marked `miForwardRef` and either `mdPinvokeImpl` or `miRuntime` is set to zero.</span></span> <span data-ttu-id="c899d-120">つまり、未解決のメソッドは、マークされているクラス メソッド`miForwardRef`(PInvoke 経由で到達)、アンマネージ コードで実装またはランタイム自体によって内部的に実装するはありませんが、</span><span class="sxs-lookup"><span data-stu-id="c899d-120">In other words, an unresolved method is a class method that is marked `miForwardRef` but which is not implemented in unmanaged code (reached via PInvoke) nor implemented internally by the runtime itself</span></span>  
  
 <span data-ttu-id="c899d-121">列挙体は、モジュール スコープ (グローバル) またはインターフェイスまたは抽象クラスで定義されているすべてのメソッドを除外します。</span><span class="sxs-lookup"><span data-stu-id="c899d-121">The enumeration excludes all methods that are defined either at module scope (globals) or in interfaces or abstract classes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c899d-122">必要条件</span><span class="sxs-lookup"><span data-stu-id="c899d-122">Requirements</span></span>  
 <span data-ttu-id="c899d-123">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c899d-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c899d-124">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="c899d-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c899d-125">**ライブラリ:** MsCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="c899d-125">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="c899d-126">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="c899d-126">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c899d-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="c899d-127">See also</span></span>

- [<span data-ttu-id="c899d-128">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c899d-128">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="c899d-129">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c899d-129">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
