---
title: GetIdentityAuthority 関数
ms.date: 03/30/2017
api_name:
- GetIdentityAuthority
api_location:
- fusion.dll
- clr.dll
api_type:
- COM
f1_keywords:
- GetIdentityAuthority
helpviewer_keywords:
- GetIdentityAuthority function [.NET Framework fusion]
ms.assetid: 843cd5ab-d2b7-4ff6-86bd-e68c7a91c098
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1194ae12710ce9ef6d5f53e584493eec0541f3fd
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54569717"
---
# <a name="getidentityauthority-function"></a><span data-ttu-id="bb970-102">GetIdentityAuthority 関数</span><span class="sxs-lookup"><span data-stu-id="bb970-102">GetIdentityAuthority Function</span></span>
<span data-ttu-id="bb970-103">ポインターを取得、 [IIdentityAuthority](../../../../docs/framework/unmanaged-api/fusion/iidentityauthority-interface.md)コード オブジェクトのキーを管理するインスタンス。</span><span class="sxs-lookup"><span data-stu-id="bb970-103">Gets a pointer to an [IIdentityAuthority](../../../../docs/framework/unmanaged-api/fusion/iidentityauthority-interface.md) instance that manages keys for code objects.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb970-104">構文</span><span class="sxs-lookup"><span data-stu-id="bb970-104">Syntax</span></span>  
  
```  
HRESULT GetIdentityAuthority (  
    [out] IIdentityAuthority   **ppIIdentityAuthority  
 );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bb970-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="bb970-105">Parameters</span></span>  
 `ppIIdentityAuthority`  
 <span data-ttu-id="bb970-106">[out]返された`IIdentityAuthority`ポインター。</span><span class="sxs-lookup"><span data-stu-id="bb970-106">[out] The returned `IIdentityAuthority` pointer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bb970-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="bb970-107">Requirements</span></span>  
 <span data-ttu-id="bb970-108">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="bb970-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bb970-109">**ヘッダー:** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="bb970-109">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="bb970-110">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bb970-110">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb970-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="bb970-111">See also</span></span>
- [<span data-ttu-id="bb970-112">IIdentityAuthority インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bb970-112">IIdentityAuthority Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iidentityauthority-interface.md)
- [<span data-ttu-id="bb970-113">Fusion グローバル静的関数</span><span class="sxs-lookup"><span data-stu-id="bb970-113">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
