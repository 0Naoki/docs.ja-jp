---
title: IMetaDataAssemblyImport::FindManifestResourceByName メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.FindManifestResourceByName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::FindManifestResourceByName
helpviewer_keywords:
- FindManifestResourceByName method [.NET Framework metadata]
- IMetaDataAssemblyImport::FindManifestResourceByName method [.NET Framework metadata]
ms.assetid: 7b72fa11-3866-402b-bdea-2b966b77cfe0
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bf61da362251577acadb83915404eba7508b3099
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59141571"
---
# <a name="imetadataassemblyimportfindmanifestresourcebyname-method"></a><span data-ttu-id="52358-102">IMetaDataAssemblyImport::FindManifestResourceByName メソッド</span><span class="sxs-lookup"><span data-stu-id="52358-102">IMetaDataAssemblyImport::FindManifestResourceByName Method</span></span>
<span data-ttu-id="52358-103">指定した名前、マニフェスト リソースへのポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="52358-103">Gets a pointer to the manifest resource with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52358-104">構文</span><span class="sxs-lookup"><span data-stu-id="52358-104">Syntax</span></span>  
  
```  
HRESULT FindManifestResourceByName (  
    [in]  LPCWSTR                szName,   
    [out] mdManifestResource     *ptkManifestResource  
);   
```  
  
## <a name="parameters"></a><span data-ttu-id="52358-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="52358-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="52358-106">[in]リソースの名前。</span><span class="sxs-lookup"><span data-stu-id="52358-106">[in] The name of the resource.</span></span>  
  
 `ptkManifestResource`  
 <span data-ttu-id="52358-107">[out]配列の格納に使用される、`mdManifestResource`マニフェスト リソースを表すメタデータ トークン。</span><span class="sxs-lookup"><span data-stu-id="52358-107">[out] The array used to store the `mdManifestResource` metadata tokens, each of which represents a manifest resource.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="52358-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="52358-108">Remarks</span></span>  
 <span data-ttu-id="52358-109">`FindManifestResourceByName`メソッドは、参照を解決するための共通言語ランタイムによって使用されている標準の規則を使用します。</span><span class="sxs-lookup"><span data-stu-id="52358-109">The `FindManifestResourceByName` method uses the standard rules employed by the common language runtime for resolving references.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="52358-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="52358-110">Requirements</span></span>  
 <span data-ttu-id="52358-111">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="52358-111">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="52358-112">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="52358-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="52358-113">**ライブラリ:** MsCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="52358-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="52358-114">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="52358-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="52358-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="52358-115">See also</span></span>

- [<span data-ttu-id="52358-116">IMetaDataAssemblyImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="52358-116">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
- [<span data-ttu-id="52358-117">ランタイムがアセンブリを検索する方法</span><span class="sxs-lookup"><span data-stu-id="52358-117">How the Runtime Locates Assemblies</span></span>](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
