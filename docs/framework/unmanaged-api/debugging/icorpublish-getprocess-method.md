---
title: ICorPublish::GetProcess メソッド
ms.date: 03/30/2017
api_name:
- ICorPublish.GetProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublish::GetProcess
helpviewer_keywords:
- ICorPublish::GetProcess method [.NET Framework debugging]
- GetProcess method, ICorPublish interface [.NET Framework debugging]
ms.assetid: c5143805-2eb7-45b8-85ed-c8fb34df1084
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 021068caa8f1ad2c64e5ca3d18ea25dc827563a4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59085005"
---
# <a name="icorpublishgetprocess-method"></a><span data-ttu-id="4c2d2-102">ICorPublish::GetProcess メソッド</span><span class="sxs-lookup"><span data-stu-id="4c2d2-102">ICorPublish::GetProcess Method</span></span>
<span data-ttu-id="4c2d2-103">取得、 [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)指定の識別子を持つプロセスを表すインスタンス。</span><span class="sxs-lookup"><span data-stu-id="4c2d2-103">Gets an [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) instance that represents the process with the specified identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4c2d2-104">構文</span><span class="sxs-lookup"><span data-stu-id="4c2d2-104">Syntax</span></span>  
  
```  
HRESULT GetProcess(  
    [in] unsigned              pid,   
    [out] ICorPublishProcess   **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4c2d2-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="4c2d2-105">Parameters</span></span>  
 `pid`  
 <span data-ttu-id="4c2d2-106">[in]プロセスの識別子です。</span><span class="sxs-lookup"><span data-stu-id="4c2d2-106">[in] The identifier of the process.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="4c2d2-107">[out]アドレスへのポインター、`ICorPublishProcess`プロセスを表すインスタンス。</span><span class="sxs-lookup"><span data-stu-id="4c2d2-107">[out] A pointer to the address of an `ICorPublishProcess` instance that represents the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4c2d2-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="4c2d2-108">Remarks</span></span>  
 `GetProcess` <span data-ttu-id="4c2d2-109">プロセスが存在しないか、現在のユーザーがデバッグ可能なマネージ プロセスがない場合は失敗します。</span><span class="sxs-lookup"><span data-stu-id="4c2d2-109">fails if the process doesn't exist, or isn't a managed process that can be debugged by the current user.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4c2d2-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="4c2d2-110">Requirements</span></span>  
 <span data-ttu-id="4c2d2-111">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4c2d2-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4c2d2-112">**ヘッダー:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="4c2d2-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="4c2d2-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4c2d2-113">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="4c2d2-114">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="4c2d2-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="4c2d2-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="4c2d2-115">See also</span></span>

- [<span data-ttu-id="4c2d2-116">ICorPublish インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4c2d2-116">ICorPublish Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md)
