---
title: IMetaDataImport::GetMemberRefProps メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetMemberRefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetMemberRefProps
helpviewer_keywords:
- GetMemberRefProps method [.NET Framework metadata]
- IMetaDataImport::GetMemberRefProps method [.NET Framework metadata]
ms.assetid: 0ea73055-ece0-4151-a094-414c88ef8941
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: fadc54d74ce6027bd021e148a14cb0c432eb41fe
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782343"
---
# <a name="imetadataimportgetmemberrefprops-method"></a><span data-ttu-id="70c51-102">IMetaDataImport::GetMemberRefProps メソッド</span><span class="sxs-lookup"><span data-stu-id="70c51-102">IMetaDataImport::GetMemberRefProps Method</span></span>
<span data-ttu-id="70c51-103">指定したトークンによって参照されるメンバーに関連付けられているメタデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="70c51-103">Gets metadata associated with the member referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70c51-104">構文</span><span class="sxs-lookup"><span data-stu-id="70c51-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMemberRefProps (  
   [in]  mdMemberRef       mr,   
   [out] mdToken           *ptk,   
   [out] LPWSTR            szMember,   
   [in]  ULONG             cchMember,   
   [out] ULONG             *pchMember,   
   [out] PCCOR_SIGNATURE   *ppvSigBlob,   
   [out] ULONG             *pbSig   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="70c51-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="70c51-105">Parameters</span></span>  
 `mr`  
 <span data-ttu-id="70c51-106">[in]関連付けられているメタデータを返す MemberRef トークンです。</span><span class="sxs-lookup"><span data-stu-id="70c51-106">[in] The MemberRef token to return associated metadata for.</span></span>  
  
 `ptk`  
 <span data-ttu-id="70c51-107">[out]メンバー、または、メンバーまたはメンバーを表す MethodDef を宣言するモジュールのクラスを表す ModuleRef トークンを宣言するクラスを表す TypeDef または TypeRef、TypeSpec トークンです。</span><span class="sxs-lookup"><span data-stu-id="70c51-107">[out] A TypeDef or TypeRef, or TypeSpec token that represents the class that declares the member, or a ModuleRef token that represents the module class that declares the member, or a MethodDef that represents the member.</span></span>  
  
 `szMember`  
 <span data-ttu-id="70c51-108">[out]メンバーの名前の文字列バッファー。</span><span class="sxs-lookup"><span data-stu-id="70c51-108">[out] A string buffer for the member's name.</span></span>  
  
 `cchMember`  
 <span data-ttu-id="70c51-109">[in]要求されたサイズのワイド文字単位`szMember`します。</span><span class="sxs-lookup"><span data-stu-id="70c51-109">[in] The requested size in wide characters of `szMember`.</span></span>  
  
 `pchMember`  
 <span data-ttu-id="70c51-110">[out]ワイド文字で返されるサイズ`szMember`します。</span><span class="sxs-lookup"><span data-stu-id="70c51-110">[out] The returned size in wide characters of `szMember`.</span></span>  
  
 `ppvSibBlob`  
 <span data-ttu-id="70c51-111">[out]メンバーのバイナリ メタデータ シグネチャへのポインター。</span><span class="sxs-lookup"><span data-stu-id="70c51-111">[out] A pointer to the binary metadata signature for the member.</span></span>  
  
 `pbSig`  
 <span data-ttu-id="70c51-112">[out]バイト サイズ`ppvSigBlob`します。</span><span class="sxs-lookup"><span data-stu-id="70c51-112">[out] The size in bytes of `ppvSigBlob`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="70c51-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="70c51-113">Requirements</span></span>  
 <span data-ttu-id="70c51-114">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="70c51-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="70c51-115">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="70c51-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="70c51-116">**ライブラリ:** MsCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="70c51-116">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="70c51-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="70c51-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70c51-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="70c51-118">See also</span></span>

- [<span data-ttu-id="70c51-119">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="70c51-119">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="70c51-120">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="70c51-120">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
