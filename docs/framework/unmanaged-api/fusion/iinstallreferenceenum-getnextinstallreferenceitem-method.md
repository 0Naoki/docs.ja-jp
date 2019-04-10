---
title: IInstallReferenceEnum::GetNextInstallReferenceItem メソッド
ms.date: 03/30/2017
api_name:
- IInstallReferenceEnum.GetNextInstallReferenceItem
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IInstallReferenceEnum::GetNextInstallReferenceItem
helpviewer_keywords:
- IInstallReferenceEnum::GetNextInstallReferenceItem method [.NET Framework fusion]
- GetNextInstallReferenceItem method [.NET Framework fusion]
ms.assetid: ce969c9d-6538-4c34-8784-148ffd99fe7a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bc04bb12e4271a3237ebef140c481620fc01ad7e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59202379"
---
# <a name="iinstallreferenceenumgetnextinstallreferenceitem-method"></a><span data-ttu-id="857c9-102">IInstallReferenceEnum::GetNextInstallReferenceItem メソッド</span><span class="sxs-lookup"><span data-stu-id="857c9-102">IInstallReferenceEnum::GetNextInstallReferenceItem Method</span></span>
<span data-ttu-id="857c9-103">次のポインターを取得[IInstallReferenceItem](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceitem-interface.md)これに含まれるオブジェクト[IInstallReferenceEnum](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceenum-interface.md)オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="857c9-103">Gets a pointer to the next [IInstallReferenceItem](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceitem-interface.md) object contained in this [IInstallReferenceEnum](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceenum-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="857c9-104">構文</span><span class="sxs-lookup"><span data-stu-id="857c9-104">Syntax</span></span>  
  
```  
HRESULT GetNextInstallReferenceItem (  
    [out] IInstallReferenceItem **ppRefItem,  
    [in]  DWORD dwFlags,  
    [in]  LPVOID pvReserved  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="857c9-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="857c9-105">Parameters</span></span>  
 `ppRefItem`  
 <span data-ttu-id="857c9-106">[out]返された`IInstallReferenceItem`ポインター。</span><span class="sxs-lookup"><span data-stu-id="857c9-106">[out] The returned `IInstallReferenceItem` pointer.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="857c9-107">[入力] 将来の機能拡張に備えて予約されています。</span><span class="sxs-lookup"><span data-stu-id="857c9-107">[in] Reserved for future extensibility.</span></span> `dwFlags` <span data-ttu-id="857c9-108">0 (ゼロ) である必要があります。</span><span class="sxs-lookup"><span data-stu-id="857c9-108">must be 0 (zero).</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="857c9-109">[入力] 将来の機能拡張に備えて予約されています。</span><span class="sxs-lookup"><span data-stu-id="857c9-109">[in] Reserved for future extensibility.</span></span> `pvReserved` <span data-ttu-id="857c9-110">null 参照である必要があります。</span><span class="sxs-lookup"><span data-stu-id="857c9-110">must be a null reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="857c9-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="857c9-111">Requirements</span></span>  
 <span data-ttu-id="857c9-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="857c9-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="857c9-113">**ヘッダー:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="857c9-113">**Header:** Fusion.h</span></span>  
  
 **<span data-ttu-id="857c9-114">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="857c9-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="857c9-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="857c9-115">See also</span></span>

- [<span data-ttu-id="857c9-116">IInstallReferenceItem インターフェイス</span><span class="sxs-lookup"><span data-stu-id="857c9-116">IInstallReferenceItem Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceitem-interface.md)
- [<span data-ttu-id="857c9-117">IInstallReferenceEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="857c9-117">IInstallReferenceEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceenum-interface.md)
