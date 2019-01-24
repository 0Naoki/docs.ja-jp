---
title: IInstallReferenceItem::GetReference メソッド
ms.date: 03/30/2017
api_name:
- IInstallReferenceItem.GetReference
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IInstallReferenceItem::GetReference
helpviewer_keywords:
- IInstallReferenceItem::GetReference method [.NET Framework fusion]
- GetReference method [.NET Framework fusion]
ms.assetid: 8960332f-c98a-405a-ba92-7003de0c1187
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c768091f84157ea651c018fa89cdeafcce6c02df
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54537674"
---
# <a name="iinstallreferenceitemgetreference-method"></a><span data-ttu-id="15e0c-102">IInstallReferenceItem::GetReference メソッド</span><span class="sxs-lookup"><span data-stu-id="15e0c-102">IInstallReferenceItem::GetReference Method</span></span>
<span data-ttu-id="15e0c-103">ポインターを取得、 [FUSION_INSTALL_REFERENCE](../../../../docs/framework/unmanaged-api/fusion/fusion-install-reference-structure.md)構造体によって表される[IInstallReferenceItem](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceitem-interface.md)オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="15e0c-103">Gets a pointer to the [FUSION_INSTALL_REFERENCE](../../../../docs/framework/unmanaged-api/fusion/fusion-install-reference-structure.md) structure represented by this [IInstallReferenceItem](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceitem-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15e0c-104">構文</span><span class="sxs-lookup"><span data-stu-id="15e0c-104">Syntax</span></span>  
  
```  
HRESULT GetReference (  
    [out] LPFUSION_INSTALL_REFERENCE *ppRefData,  
    [in]  DWORD dwFlags,  
    [in]  LPVOID pvReserved  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="15e0c-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="15e0c-105">Parameters</span></span>  
 `ppRefData`  
 <span data-ttu-id="15e0c-106">[out]返された`FUSION_INSTALL_REFERENCE`ポインター。</span><span class="sxs-lookup"><span data-stu-id="15e0c-106">[out] The returned `FUSION_INSTALL_REFERENCE` pointer.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="15e0c-107">[入力] 将来の機能拡張に備えて予約されています。</span><span class="sxs-lookup"><span data-stu-id="15e0c-107">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="15e0c-108">`dwFlags` 0 (ゼロ) である必要があります。</span><span class="sxs-lookup"><span data-stu-id="15e0c-108">`dwFlags` must be 0 (zero).</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="15e0c-109">[入力] 将来の機能拡張に備えて予約されています。</span><span class="sxs-lookup"><span data-stu-id="15e0c-109">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="15e0c-110">`pvReserved` null 参照である必要があります。</span><span class="sxs-lookup"><span data-stu-id="15e0c-110">`pvReserved` must be a null reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="15e0c-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="15e0c-111">Requirements</span></span>  
 <span data-ttu-id="15e0c-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="15e0c-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="15e0c-113">**ヘッダー:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="15e0c-113">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="15e0c-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="15e0c-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15e0c-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="15e0c-115">See also</span></span>
- [<span data-ttu-id="15e0c-116">IInstallReferenceItem インターフェイス</span><span class="sxs-lookup"><span data-stu-id="15e0c-116">IInstallReferenceItem Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceitem-interface.md)
- [<span data-ttu-id="15e0c-117">FUSION_INSTALL_REFERENCE 構造体</span><span class="sxs-lookup"><span data-stu-id="15e0c-117">FUSION_INSTALL_REFERENCE Structure</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-install-reference-structure.md)
