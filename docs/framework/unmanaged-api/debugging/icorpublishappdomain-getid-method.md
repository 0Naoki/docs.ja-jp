---
title: ICorPublishAppDomain::GetID メソッド
ms.date: 03/30/2017
api_name:
- ICorPublishAppDomain.GetID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishAppDomain::GetID
helpviewer_keywords:
- GetID method, ICorPublishAppDomain interface [.NET Framework debugging]
- ICorPublishAppDomain::GetID method [.NET Framework debugging]
ms.assetid: 229437e3-1465-4bd8-8846-9804b2488133
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6a7541a2093fe877fb84a8a05237f18c4da43c44
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57465986"
---
# <a name="icorpublishappdomaingetid-method"></a><span data-ttu-id="fb8d0-102">ICorPublishAppDomain::GetID メソッド</span><span class="sxs-lookup"><span data-stu-id="fb8d0-102">ICorPublishAppDomain::GetID Method</span></span>
<span data-ttu-id="fb8d0-103">この一意識別子を取得します。 [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md)します。</span><span class="sxs-lookup"><span data-stu-id="fb8d0-103">Gets the unique identifier for this [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb8d0-104">構文</span><span class="sxs-lookup"><span data-stu-id="fb8d0-104">Syntax</span></span>  
  
```  
HRESULT GetID (  
    [out] ULONG32   *puId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fb8d0-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="fb8d0-105">Parameters</span></span>  
 `puId`  
 <span data-ttu-id="fb8d0-106">[out]アプリケーション ドメインの識別子へのポインター。</span><span class="sxs-lookup"><span data-stu-id="fb8d0-106">[out] A pointer to the identifier of the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fb8d0-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="fb8d0-107">Remarks</span></span>  
 <span data-ttu-id="fb8d0-108">識別子は、格納しているプロセスのスコープ内でのみ一意です。</span><span class="sxs-lookup"><span data-stu-id="fb8d0-108">The identifier is unique only in the scope of the containing process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fb8d0-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="fb8d0-109">Requirements</span></span>  
 <span data-ttu-id="fb8d0-110">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="fb8d0-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fb8d0-111">**ヘッダー:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="fb8d0-111">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="fb8d0-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fb8d0-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fb8d0-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fb8d0-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb8d0-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="fb8d0-114">See also</span></span>
- [<span data-ttu-id="fb8d0-115">ICorPublishAppDomain インターフェイス</span><span class="sxs-lookup"><span data-stu-id="fb8d0-115">ICorPublishAppDomain Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md)
