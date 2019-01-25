---
title: IMetaDataEmit::SetPinvokeMap メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetPinvokeMap
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetPinvokeMap
helpviewer_keywords:
- IMetaDataEmit::SetPinvokeMap method [.NET Framework metadata]
- SetPinvokeMap method [.NET Framework metadata]
ms.assetid: c6bfd574-1da3-4ba7-82f2-46ca5efcbaba
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7248f4c78684f7211c7b7633095fdc3f3f2fb1f3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54658625"
---
# <a name="imetadataemitsetpinvokemap-method"></a><span data-ttu-id="129f7-102">IMetaDataEmit::SetPinvokeMap メソッド</span><span class="sxs-lookup"><span data-stu-id="129f7-102">IMetaDataEmit::SetPinvokeMap Method</span></span>
<span data-ttu-id="129f7-103">前回の呼び出しで定義されているメソッドの PInvoke の署名の機能の変更を設定または[imetadataemit::definepinvokemap](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definepinvokemap-method.md)します。</span><span class="sxs-lookup"><span data-stu-id="129f7-103">Sets or changes features of a method's PInvoke signature, as defined by a prior call to [IMetaDataEmit::DefinePinvokeMap](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definepinvokemap-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="129f7-104">構文</span><span class="sxs-lookup"><span data-stu-id="129f7-104">Syntax</span></span>  
  
```  
HRESULT SetPinvokeMap (   
    [in]  mdToken      tk,   
    [in]  DWORD        dwMappingFlags,  
    [in]  LPCWSTR      szImportName,   
    [in]  mdModuleRef  mrImportDLL   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="129f7-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="129f7-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="129f7-106">[in]`mdToken`マッピング情報が適用されます。</span><span class="sxs-lookup"><span data-stu-id="129f7-106">[in] The `mdToken` to which mapping information applies.</span></span>  
  
 `dwMappingFlags`  
 <span data-ttu-id="129f7-107">[in]PInvoke によって、マッピングを行うために使用するフラグ。</span><span class="sxs-lookup"><span data-stu-id="129f7-107">[in] Flags used by PInvoke to do the mapping.</span></span> <span data-ttu-id="129f7-108">これは、ビットマスクの`CorPinvokeMap`値。</span><span class="sxs-lookup"><span data-stu-id="129f7-108">This is a bitmask of `CorPinvokeMap` values.</span></span>  
  
 `szImportName`  
 <span data-ttu-id="129f7-109">[in]ターゲットの名前は、ネイティブ DLL でエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="129f7-109">[in] The name of the target export in the native DLL.</span></span>  
  
 `mrImportDLL`  
 <span data-ttu-id="129f7-110">[in]`mdModuleRef`トークン ターゲットのアンマネージ DLL です。</span><span class="sxs-lookup"><span data-stu-id="129f7-110">[in] The `mdModuleRef` token for the target unmanaged DLL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="129f7-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="129f7-111">Requirements</span></span>  
 <span data-ttu-id="129f7-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="129f7-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="129f7-113">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="129f7-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="129f7-114">**ライブラリ:** MSCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="129f7-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="129f7-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="129f7-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="129f7-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="129f7-116">See also</span></span>
- [<span data-ttu-id="129f7-117">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="129f7-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="129f7-118">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="129f7-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
