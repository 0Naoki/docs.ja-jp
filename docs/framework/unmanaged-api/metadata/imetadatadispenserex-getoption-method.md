---
title: IMetaDataDispenserEx::GetOption メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataDispenserEx.GetOption
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenserEx::GetOption
helpviewer_keywords:
- GetOption method [.NET Framework metadata]
- IMetaDataDispenserEx::GetOption method [.NET Framework metadata]
ms.assetid: d7f794e5-8e25-4d65-850a-7c34fbfce87d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6287b7adf0ef6f6269a51f608657444f5fa7f74e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54580227"
---
# <a name="imetadatadispenserexgetoption-method"></a><span data-ttu-id="3b0fe-102">IMetaDataDispenserEx::GetOption メソッド</span><span class="sxs-lookup"><span data-stu-id="3b0fe-102">IMetaDataDispenserEx::GetOption Method</span></span>
<span data-ttu-id="3b0fe-103">現在のメタデータ スコープの指定したオプションの値を取得します。</span><span class="sxs-lookup"><span data-stu-id="3b0fe-103">Gets the value of the specified option for the current metadata scope.</span></span> <span data-ttu-id="3b0fe-104">オプションは、現在のメタデータ スコープへの呼び出しを処理する方法を制御します。</span><span class="sxs-lookup"><span data-stu-id="3b0fe-104">The option controls how calls to the current metadata scope are handled.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b0fe-105">構文</span><span class="sxs-lookup"><span data-stu-id="3b0fe-105">Syntax</span></span>  
  
```  
HRESULT GetOption (  
    [in]  REFGUID         optionId,   
    [out] const VARIANT   *pValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3b0fe-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3b0fe-106">Parameters</span></span>  
 `optionId`  
 <span data-ttu-id="3b0fe-107">[in]取得するオプションを指定する GUID へのポインター。</span><span class="sxs-lookup"><span data-stu-id="3b0fe-107">[in] A pointer to a GUID that specifies the option to be retrieved.</span></span> <span data-ttu-id="3b0fe-108">サポートされている Guid の一覧については、「解説」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3b0fe-108">See the Remarks section for a list of supported GUIDs.</span></span>  
  
 `pValue`  
 <span data-ttu-id="3b0fe-109">[out]返されるオプションの値。</span><span class="sxs-lookup"><span data-stu-id="3b0fe-109">[out] The value of the returned option.</span></span> <span data-ttu-id="3b0fe-110">この値の型は、指定したオプションの型のバリアントになります。</span><span class="sxs-lookup"><span data-stu-id="3b0fe-110">The type of this value will be a variant of the specified option's type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3b0fe-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="3b0fe-111">Remarks</span></span>  
 <span data-ttu-id="3b0fe-112">このメソッドがサポートされている Guid を次に示します。</span><span class="sxs-lookup"><span data-stu-id="3b0fe-112">The following list shows the GUIDs that are supported for this method.</span></span> <span data-ttu-id="3b0fe-113">詳細については、次を参照してください。、 [imetadatadispenserex::setoption](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-setoption-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="3b0fe-113">For descriptions, see the [IMetaDataDispenserEx::SetOption](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-setoption-method.md) method.</span></span> <span data-ttu-id="3b0fe-114">場合`optionId`は、この一覧にないは、このメソッドは HRESULT を返します。 `E_INVALIDARG`、無効なパラメーターを示します。</span><span class="sxs-lookup"><span data-stu-id="3b0fe-114">If `optionId` is not in this list, this method returns HRESULT `E_INVALIDARG`, indicating an incorrect parameter.</span></span>  
  
-   <span data-ttu-id="3b0fe-115">MetaDataCheckDuplicatesFor</span><span class="sxs-lookup"><span data-stu-id="3b0fe-115">MetaDataCheckDuplicatesFor</span></span>  
  
-   <span data-ttu-id="3b0fe-116">MetaDataRefToDefCheck</span><span class="sxs-lookup"><span data-stu-id="3b0fe-116">MetaDataRefToDefCheck</span></span>  
  
-   <span data-ttu-id="3b0fe-117">MetaDataNotificationForTokenMovement</span><span class="sxs-lookup"><span data-stu-id="3b0fe-117">MetaDataNotificationForTokenMovement</span></span>  
  
-   <span data-ttu-id="3b0fe-118">MetaDataSetENC</span><span class="sxs-lookup"><span data-stu-id="3b0fe-118">MetaDataSetENC</span></span>  
  
-   <span data-ttu-id="3b0fe-119">MetaDataErrorIfEmitOutOfOrder</span><span class="sxs-lookup"><span data-stu-id="3b0fe-119">MetaDataErrorIfEmitOutOfOrder</span></span>  
  
-   <span data-ttu-id="3b0fe-120">MetaDataGenerateTCEAdapters</span><span class="sxs-lookup"><span data-stu-id="3b0fe-120">MetaDataGenerateTCEAdapters</span></span>  
  
-   <span data-ttu-id="3b0fe-121">MetaDataLinkerOptions</span><span class="sxs-lookup"><span data-stu-id="3b0fe-121">MetaDataLinkerOptions</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3b0fe-122">必要条件</span><span class="sxs-lookup"><span data-stu-id="3b0fe-122">Requirements</span></span>  
 <span data-ttu-id="3b0fe-123">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3b0fe-123">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3b0fe-124">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="3b0fe-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3b0fe-125">**ライブラリ:** MsCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="3b0fe-125">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3b0fe-126">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3b0fe-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b0fe-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="3b0fe-127">See also</span></span>
- [<span data-ttu-id="3b0fe-128">IMetaDataDispenserEx インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3b0fe-128">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [<span data-ttu-id="3b0fe-129">IMetaDataDispenser インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3b0fe-129">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
