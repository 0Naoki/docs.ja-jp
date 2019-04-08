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
ms.openlocfilehash: 3090887d3c670b2784b7b40c7d63832715596c3b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59141519"
---
# <a name="getidentityauthority-function"></a><span data-ttu-id="8a8a0-102">GetIdentityAuthority 関数</span><span class="sxs-lookup"><span data-stu-id="8a8a0-102">GetIdentityAuthority Function</span></span>
<span data-ttu-id="8a8a0-103">ポインターを取得、 [IIdentityAuthority](../../../../docs/framework/unmanaged-api/fusion/iidentityauthority-interface.md)コード オブジェクトのキーを管理するインスタンス。</span><span class="sxs-lookup"><span data-stu-id="8a8a0-103">Gets a pointer to an [IIdentityAuthority](../../../../docs/framework/unmanaged-api/fusion/iidentityauthority-interface.md) instance that manages keys for code objects.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a8a0-104">構文</span><span class="sxs-lookup"><span data-stu-id="8a8a0-104">Syntax</span></span>  
  
```  
HRESULT GetIdentityAuthority (  
    [out] IIdentityAuthority   **ppIIdentityAuthority  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="8a8a0-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="8a8a0-105">Parameters</span></span>  
 `ppIIdentityAuthority`  
 <span data-ttu-id="8a8a0-106">[out]返された`IIdentityAuthority`ポインター。</span><span class="sxs-lookup"><span data-stu-id="8a8a0-106">[out] The returned `IIdentityAuthority` pointer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8a8a0-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="8a8a0-107">Requirements</span></span>  
 <span data-ttu-id="8a8a0-108">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8a8a0-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8a8a0-109">**ヘッダー:** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="8a8a0-109">**Header:** Isolation.h</span></span>  
  
 **<span data-ttu-id="8a8a0-110">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="8a8a0-110">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="8a8a0-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="8a8a0-111">See also</span></span>

- [<span data-ttu-id="8a8a0-112">IIdentityAuthority インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8a8a0-112">IIdentityAuthority Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iidentityauthority-interface.md)
- [<span data-ttu-id="8a8a0-113">Fusion グローバル静的関数</span><span class="sxs-lookup"><span data-stu-id="8a8a0-113">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
