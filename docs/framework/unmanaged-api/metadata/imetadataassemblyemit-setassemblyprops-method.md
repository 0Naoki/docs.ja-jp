---
title: IMetaDataAssemblyEmit::SetAssemblyProps メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.SetAssemblyProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::SetAssemblyProps
helpviewer_keywords:
- SetAssemblyProps method [.NET Framework metadata]
- IMetaDataAssemblyEmit::SetAssemblyProps method [.NET Framework metadata]
ms.assetid: 91b633d7-9e75-43c3-a8d2-2144984e5f9e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 37d91ca7935e114504864683075f4809de7270fd
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54599115"
---
# <a name="imetadataassemblyemitsetassemblyprops-method"></a><span data-ttu-id="a89c0-102">IMetaDataAssemblyEmit::SetAssemblyProps メソッド</span><span class="sxs-lookup"><span data-stu-id="a89c0-102">IMetaDataAssemblyEmit::SetAssemblyProps Method</span></span>
<span data-ttu-id="a89c0-103">指定された `Assembly` メタデータ構造体を変更します。</span><span class="sxs-lookup"><span data-stu-id="a89c0-103">Modifies the specified `Assembly` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a89c0-104">構文</span><span class="sxs-lookup"><span data-stu-id="a89c0-104">Syntax</span></span>  
  
```  
HRESULT SetAssemblyProps (  
    [in] mdAssembly               pma,  
    [in] const void               *pbPublicKey,  
    [in] ULONG                    cbPublicKey,  
    [in] ULONG                    ulHashAlgId,  
    [in] LPCWSTR                  szName,  
    [in] const ASSEMBLYMETADATA   *pMetaData,  
    [in] DWORD                    dwAssemblyFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a89c0-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a89c0-105">Parameters</span></span>  
 `pma`  
 <span data-ttu-id="a89c0-106">[in]メタデータ トークンを指定する、`Assembly`メタデータ構造を変更します。</span><span class="sxs-lookup"><span data-stu-id="a89c0-106">[in] The metadata token that specifies the `Assembly` metadata structure to be modified.</span></span>  
  
 `pbPublicKey`  
 <span data-ttu-id="a89c0-107">[in]アセンブリの発行者の公開キーへのポインター。</span><span class="sxs-lookup"><span data-stu-id="a89c0-107">[in] A pointer to the public key of the publisher of the assembly.</span></span>  
  
 `cbPublicKey`  
 <span data-ttu-id="a89c0-108">[in]バイト サイズ`pbPublicKey`します。</span><span class="sxs-lookup"><span data-stu-id="a89c0-108">[in] The size in bytes of `pbPublicKey`.</span></span>  
  
 `ulHashAlgId`  
 <span data-ttu-id="a89c0-109">[in]アセンブリ ファイルをハッシュするために使用するハッシュ アルゴリズムの識別子。</span><span class="sxs-lookup"><span data-stu-id="a89c0-109">[in] The identifier for the hash algorithm used to hash the assembly files.</span></span>  
  
 `szName`  
 <span data-ttu-id="a89c0-110">[in]アセンブリの人間が判読できるテキストの名前。</span><span class="sxs-lookup"><span data-stu-id="a89c0-110">[in] The human-readable text name of the assembly.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="a89c0-111">[in]アセンブリのバージョン、プラットフォーム、およびロケールの情報を含む ASSEMBLYMETADATA へのポインター。</span><span class="sxs-lookup"><span data-stu-id="a89c0-111">[in] A pointer to the ASSEMBLYMETADATA that contains version, platform, and locale information for the assembly.</span></span>  
  
 `dwAssemblyFlags`  
 <span data-ttu-id="a89c0-112">[in]ビットごとの組み合わせ[AssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/assemblyflags-enumeration.md)アセンブリのさまざまな属性を指定する値。</span><span class="sxs-lookup"><span data-stu-id="a89c0-112">[in] A bitwise combination of [AssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/assemblyflags-enumeration.md) values that specify various attributes of the assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a89c0-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="a89c0-113">Remarks</span></span>  
 <span data-ttu-id="a89c0-114">作成する、`Assembly`メタデータ構造体を使用して、 [imetadataassemblyemit::defineassembly](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassembly-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="a89c0-114">To create an `Assembly` metadata structure, use the [IMetaDataAssemblyEmit::DefineAssembly](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassembly-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a89c0-115">必要条件</span><span class="sxs-lookup"><span data-stu-id="a89c0-115">Requirements</span></span>  
 <span data-ttu-id="a89c0-116">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a89c0-116">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a89c0-117">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="a89c0-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a89c0-118">**ライブラリ:** MsCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="a89c0-118">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a89c0-119">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a89c0-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a89c0-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="a89c0-120">See also</span></span>
- [<span data-ttu-id="a89c0-121">IMetaDataAssemblyEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a89c0-121">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
