---
title: IMetaDataImport::GetPermissionSetProps メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetPermissionSetProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetPermissionSetProps
helpviewer_keywords:
- GetPermissionSetProps method [.NET Framework metadata]
- IMetaDataImport::GetPermissionSetProps method [.NET Framework metadata]
ms.assetid: 9855f0e4-12c0-4d3d-ab5d-d6bc52d25eae
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 806f1ebcacb9e7ad27b7370f9976b3341bf64f8c
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57466935"
---
# <a name="imetadataimportgetpermissionsetprops-method"></a><span data-ttu-id="b4780-102">IMetaDataImport::GetPermissionSetProps メソッド</span><span class="sxs-lookup"><span data-stu-id="b4780-102">IMetaDataImport::GetPermissionSetProps Method</span></span>
<span data-ttu-id="b4780-103">関連付けられているメタデータを取得、<xref:System.Security.PermissionSet?displayProperty=nameWithType>指定した権限のトークンによって表されます。</span><span class="sxs-lookup"><span data-stu-id="b4780-103">Gets the metadata associated with the <xref:System.Security.PermissionSet?displayProperty=nameWithType> represented by the specified Permission token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4780-104">構文</span><span class="sxs-lookup"><span data-stu-id="b4780-104">Syntax</span></span>  
  
```  
HRESULT GetPermissionSetProps (  
   [in]  mdPermission      pm,  
   [out] DWORD             *pdwAction,   
   [out] void const        **ppvPermission,   
   [out] ULONG             *pcbPermission  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b4780-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b4780-105">Parameters</span></span>  
 `pm`  
 <span data-ttu-id="b4780-106">[in]アクセス許可セットのメタデータ プロパティの取得を表すアクセス許可のメタデータ トークンです。</span><span class="sxs-lookup"><span data-stu-id="b4780-106">[in] The Permission metadata token that represents the permission set to get the metadata properties for.</span></span>  
  
 `pdwAction`  
 <span data-ttu-id="b4780-107">[out]権限セットへのポインター。</span><span class="sxs-lookup"><span data-stu-id="b4780-107">[out] A pointer to the permission set.</span></span>  
  
 `ppvPermission`  
 <span data-ttu-id="b4780-108">[out]アクセス許可セットのバイナリ メタデータ シグネチャへのポインター。</span><span class="sxs-lookup"><span data-stu-id="b4780-108">[out] A pointer to the binary metadata signature of the permission set.</span></span>  
  
 `pcbPermission`  
 <span data-ttu-id="b4780-109">[out]バイト サイズ`ppvPermission`します。</span><span class="sxs-lookup"><span data-stu-id="b4780-109">[out] The size in bytes of `ppvPermission`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b4780-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="b4780-110">Requirements</span></span>  
 <span data-ttu-id="b4780-111">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b4780-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b4780-112">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="b4780-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b4780-113">**ライブラリ:** MsCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="b4780-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b4780-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b4780-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4780-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="b4780-115">See also</span></span>
- <xref:System.Security.PermissionSet>
- [<span data-ttu-id="b4780-116">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b4780-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="b4780-117">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b4780-117">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
