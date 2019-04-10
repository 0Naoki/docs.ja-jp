---
title: ICorPublishProcess::IsManaged メソッド
ms.date: 03/30/2017
api_name:
- ICorPublishProcess.IsManaged
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcess::IsManaged
helpviewer_keywords:
- IsManaged method, ICorPublishProcess interface [.NET Framework debugging]
- ICorPublishProcess::IsManaged method [.NET Framework debugging]
ms.assetid: 06b1f7cc-acdf-47a6-9d53-d9dec2424152
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 29c5f96bab374d6e2d43424370bff2a4a2ab6df3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59218291"
---
# <a name="icorpublishprocessismanaged-method"></a><span data-ttu-id="cad80-102">ICorPublishProcess::IsManaged メソッド</span><span class="sxs-lookup"><span data-stu-id="cad80-102">ICorPublishProcess::IsManaged Method</span></span>
<span data-ttu-id="cad80-103">これによって、プロセスが参照されるかどうかを示す値を取得します[ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)コード管理されていることがわかっています。</span><span class="sxs-lookup"><span data-stu-id="cad80-103">Gets a value that indicates whether the process referenced by this [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) is known to have managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cad80-104">構文</span><span class="sxs-lookup"><span data-stu-id="cad80-104">Syntax</span></span>  
  
```  
HRESULT IsManaged (  
    [out] BOOL   *pbManaged  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cad80-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="cad80-105">Parameters</span></span>  
 `pbManaged`  
 <span data-ttu-id="cad80-106">[out]プロセスにマネージ コードがあるかどうかを示すブール値へのポインター。</span><span class="sxs-lookup"><span data-stu-id="cad80-106">[out] A pointer to a Boolean value that indicates whether the process has managed code.</span></span> <span data-ttu-id="cad80-107">値が`true`場合は、プロセスにマネージ コードです。 それ以外の場合、`false`します。</span><span class="sxs-lookup"><span data-stu-id="cad80-107">The value is `true` if the process has managed code; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cad80-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="cad80-108">Remarks</span></span>  
 <span data-ttu-id="cad80-109">現在のバージョン以降`ICorPublishProcess`がマネージ コード、プロセスにのみアクセスできるように`IsManaged`は常に返します`true`します。</span><span class="sxs-lookup"><span data-stu-id="cad80-109">Since the current version of `ICorPublishProcess` allows access only to processes that have managed code, `IsManaged` always returns `true`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cad80-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="cad80-110">Requirements</span></span>  
 <span data-ttu-id="cad80-111">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cad80-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cad80-112">**ヘッダー:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="cad80-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="cad80-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cad80-113">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="cad80-114">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="cad80-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="cad80-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="cad80-115">See also</span></span>

- [<span data-ttu-id="cad80-116">ICorPublishProcess インターフェイス</span><span class="sxs-lookup"><span data-stu-id="cad80-116">ICorPublishProcess Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)
