---
title: ICorPublishEnum::Clone メソッド
ms.date: 03/30/2017
api_name:
- ICorPublishEnum.Clone
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishEnum::Clone
helpviewer_keywords:
- Clone method, ICorPublishEnum interface [.NET Framework debugging]
- ICorPublishEnum::Clone method [.NET Framework debugging]
ms.assetid: c9a26ea3-b8eb-4b8e-854f-9a2ca26b3b39
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e0ce1d8c0074f62d35e16465b368269e233a713b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59105132"
---
# <a name="icorpublishenumclone-method"></a><span data-ttu-id="3fda3-102">ICorPublishEnum::Clone メソッド</span><span class="sxs-lookup"><span data-stu-id="3fda3-102">ICorPublishEnum::Clone Method</span></span>
<span data-ttu-id="3fda3-103">このコピーを作成します[ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md)オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="3fda3-103">Creates a copy of this [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3fda3-104">構文</span><span class="sxs-lookup"><span data-stu-id="3fda3-104">Syntax</span></span>  
  
```  
HRESULT Clone (  
    [out] ICorPublishEnum   **ppEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3fda3-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3fda3-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="3fda3-106">[out]アドレスへのポインター、`ICorPublishEnum`オブジェクトのこのコピーである`ICorPublishEnum`オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="3fda3-106">[out] A pointer to the address of an `ICorPublishEnum` object that is a copy of this `ICorPublishEnum` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3fda3-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="3fda3-107">Requirements</span></span>  
 <span data-ttu-id="3fda3-108">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3fda3-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3fda3-109">**ヘッダー:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="3fda3-109">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="3fda3-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3fda3-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3fda3-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3fda3-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3fda3-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="3fda3-112">See also</span></span>

- [<span data-ttu-id="3fda3-113">ICorPublishEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3fda3-113">ICorPublishEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md)
