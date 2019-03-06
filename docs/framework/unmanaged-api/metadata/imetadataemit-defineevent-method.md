---
title: IMetaDataEmit::DefineEvent メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineEvent
helpviewer_keywords:
- IMetaDataEmit::DefineEvent method [.NET Framework metadata]
- DefineEvent method [.NET Framework metadata]
ms.assetid: cf064bac-9a9f-41c5-9e1d-108ff7af3afe
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 26fd4c89838912e4e07c1d9a8b84aa22f54adeff
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57501631"
---
# <a name="imetadataemitdefineevent-method"></a><span data-ttu-id="ad405-102">IMetaDataEmit::DefineEvent メソッド</span><span class="sxs-lookup"><span data-stu-id="ad405-102">IMetaDataEmit::DefineEvent Method</span></span>
<span data-ttu-id="ad405-103">指定したメタデータ シグネチャを持つイベントの定義を作成し、そのイベント定義トークンを取得します。</span><span class="sxs-lookup"><span data-stu-id="ad405-103">Creates a definition for an event with the specified metadata signature, and gets a token to that event definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad405-104">構文</span><span class="sxs-lookup"><span data-stu-id="ad405-104">Syntax</span></span>  
  
```  
HRESULT DefineEvent (   
    [in]  mdTypeDef    td,   
    [in]  LPCWSTR      szEvent,   
    [in]  DWORD        dwEventFlags,   
    [in]  mdToken      tkEventType,   
    [in]  mdMethodDef  mdAddOn,   
    [in]  mdMethodDef  mdRemoveOn,   
    [in]  mdMethodDef  mdFire,   
    [in]  mdMethodDef  rmdOtherMethods[],   
    [out] mdEvent      *pmdEvent   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ad405-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ad405-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="ad405-106">[in]ターゲット クラスまたはインターフェイスのトークンです。</span><span class="sxs-lookup"><span data-stu-id="ad405-106">[in] The token for the target class or interface.</span></span> <span data-ttu-id="ad405-107">いずれかになります、`mdTypeDef`または`mdTypeDefNil`トークンです。</span><span class="sxs-lookup"><span data-stu-id="ad405-107">This is either a `mdTypeDef` or `mdTypeDefNil` token.</span></span>  
  
 `szEvent`  
 <span data-ttu-id="ad405-108">[in]イベントの名前。</span><span class="sxs-lookup"><span data-stu-id="ad405-108">[in] The name of the event.</span></span>  
  
 `dwEventFlags`  
 <span data-ttu-id="ad405-109">[in]イベントのフラグ。</span><span class="sxs-lookup"><span data-stu-id="ad405-109">[in] Event flags.</span></span>  
  
 `tkEventType`  
 <span data-ttu-id="ad405-110">[in]イベント クラスのトークンです。</span><span class="sxs-lookup"><span data-stu-id="ad405-110">[in] The token for the event class.</span></span> <span data-ttu-id="ad405-111">これは、 `mdTypeDef`、 `mdTypeRef`、または`mdTokenNil`トークンです。</span><span class="sxs-lookup"><span data-stu-id="ad405-111">This is a `mdTypeDef`, a `mdTypeRef`, or a `mdTokenNil` token.</span></span>  
  
 `mdAddOn`  
 <span data-ttu-id="ad405-112">[in]イベント、または null をサブスクライブするために使用するメソッド。</span><span class="sxs-lookup"><span data-stu-id="ad405-112">[in] The method used to subscribe to the event, or null.</span></span>  
  
 `mdRemoveOn`  
 <span data-ttu-id="ad405-113">[in]イベント、または null をアンサブスク ライブするメソッド。</span><span class="sxs-lookup"><span data-stu-id="ad405-113">[in] The method used to unsubscribe to the event, or null.</span></span>  
  
 `mdFire`  
 <span data-ttu-id="ad405-114">[in]イベントを発生させる (派生クラス) を使用するメソッド。</span><span class="sxs-lookup"><span data-stu-id="ad405-114">[in] The method used (by a derived class) to raise the event.</span></span>  
  
 `rmdOtherMethods[]`  
 <span data-ttu-id="ad405-115">[in]イベントに関連付けられているその他のメソッドのトークンの配列。</span><span class="sxs-lookup"><span data-stu-id="ad405-115">[in] An array of tokens for other methods associated with the event.</span></span> <span data-ttu-id="ad405-116">配列が終了しました、`mdMethodDefNil`トークンです。</span><span class="sxs-lookup"><span data-stu-id="ad405-116">The array is terminated with a `mdMethodDefNil` token.</span></span>  
  
 `pmdEvent`  
 <span data-ttu-id="ad405-117">[out]イベントに割り当てられているメタデータ トークンです。</span><span class="sxs-lookup"><span data-stu-id="ad405-117">[out] The metadata token assigned to the event.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ad405-118">必要条件</span><span class="sxs-lookup"><span data-stu-id="ad405-118">Requirements</span></span>  
 <span data-ttu-id="ad405-119">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ad405-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ad405-120">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="ad405-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ad405-121">**ライブラリ:** MSCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="ad405-121">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ad405-122">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ad405-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad405-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="ad405-123">See also</span></span>
- [<span data-ttu-id="ad405-124">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ad405-124">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="ad405-125">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ad405-125">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
