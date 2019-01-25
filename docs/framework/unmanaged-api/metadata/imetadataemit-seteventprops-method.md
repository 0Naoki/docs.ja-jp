---
title: IMetaDataEmit::SetEventProps メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetEventProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetEventProps
helpviewer_keywords:
- IMetaDataEmit::SetEventProps method [.NET Framework metadata]
- SetEventProps method [.NET Framework metadata]
ms.assetid: 3b039e50-63ec-4730-99ff-2327408de477
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ab479aab56b429c104a44b1fae192bc7f20a389d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54656922"
---
# <a name="imetadataemitseteventprops-method"></a><span data-ttu-id="a2d45-102">IMetaDataEmit::SetEventProps メソッド</span><span class="sxs-lookup"><span data-stu-id="a2d45-102">IMetaDataEmit::SetEventProps Method</span></span>
<span data-ttu-id="a2d45-103">前回の呼び出しで定義されたイベントの指定した機能の更新を設定または[imetadataemit::defineevent](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineevent-method.md)します。</span><span class="sxs-lookup"><span data-stu-id="a2d45-103">Sets or updates the specified feature of an event defined by a prior call to [IMetaDataEmit::DefineEvent](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineevent-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a2d45-104">構文</span><span class="sxs-lookup"><span data-stu-id="a2d45-104">Syntax</span></span>  
  
```  
HRESULT SetEventProps (  
    [in]  mdEvent     ev,   
    [in]  DWORD       dwEventFlags,   
    [in]  mdToken     tkEventType,   
    [in]  mdMethodDef mdAddOn,   
    [in]  mdMethodDef mdRemoveOn,   
    [in]  mdMethodDef mdFire,   
    [in]  mdMethodDef rmdOtherMethods[]   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a2d45-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a2d45-105">Parameters</span></span>  
 `ev`  
 <span data-ttu-id="a2d45-106">[in]イベント トークンです。</span><span class="sxs-lookup"><span data-stu-id="a2d45-106">[in] The event token.</span></span>  
  
 `dwEventFlags`  
 <span data-ttu-id="a2d45-107">[in]イベントのフラグ。</span><span class="sxs-lookup"><span data-stu-id="a2d45-107">[in] Event flags.</span></span> <span data-ttu-id="a2d45-108">これは、ビットマスクの`CorEventAttr`値。</span><span class="sxs-lookup"><span data-stu-id="a2d45-108">This is a bitmask of `CorEventAttr` values.</span></span>  
  
 `tkEventType`  
 <span data-ttu-id="a2d45-109">[in]イベント クラスのトークンです。</span><span class="sxs-lookup"><span data-stu-id="a2d45-109">[in] The token for the event class.</span></span> <span data-ttu-id="a2d45-110">いずれかになります、`mdTypeDef`または`mdTypeRef`トークンです。</span><span class="sxs-lookup"><span data-stu-id="a2d45-110">This is either a `mdTypeDef` or a `mdTypeRef` token.</span></span>  
  
 `mdAddOn`  
 <span data-ttu-id="a2d45-111">[in]イベント、または null をサブスクライブするために使用するメソッド。</span><span class="sxs-lookup"><span data-stu-id="a2d45-111">[in] The method used to subscribe to the event, or null.</span></span>  
  
 `mdRemoveOn`  
 <span data-ttu-id="a2d45-112">[in]イベント、または null をアンサブスク ライブするメソッド。</span><span class="sxs-lookup"><span data-stu-id="a2d45-112">[in] The method used to unsubscribe to the event, or null.</span></span>  
  
 `mdFire`  
 <span data-ttu-id="a2d45-113">[in]イベントを発生させる (派生クラス) を使用するメソッド。</span><span class="sxs-lookup"><span data-stu-id="a2d45-113">[in] The method used (by a derived class) to raise the event.</span></span>  
  
 `rmdOtherMethods[]`  
 <span data-ttu-id="a2d45-114">[in]イベントに関連付けられているその他のメソッドのトークンの配列。</span><span class="sxs-lookup"><span data-stu-id="a2d45-114">[in] An array of tokens for other methods associated with the event.</span></span> <span data-ttu-id="a2d45-115">配列の最後の要素である必要があります`mdMethodDefNil`します。</span><span class="sxs-lookup"><span data-stu-id="a2d45-115">The last element of the array must be `mdMethodDefNil`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a2d45-116">必要条件</span><span class="sxs-lookup"><span data-stu-id="a2d45-116">Requirements</span></span>  
 <span data-ttu-id="a2d45-117">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a2d45-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a2d45-118">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="a2d45-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a2d45-119">**ライブラリ:** MSCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="a2d45-119">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a2d45-120">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a2d45-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2d45-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="a2d45-121">See also</span></span>
- [<span data-ttu-id="a2d45-122">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a2d45-122">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="a2d45-123">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a2d45-123">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
