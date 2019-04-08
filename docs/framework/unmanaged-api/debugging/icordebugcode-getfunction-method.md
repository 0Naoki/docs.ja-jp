---
title: ICorDebugCode::GetFunction メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugCode.GetFunction
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::GetFunction
helpviewer_keywords:
- GetFunction method, ICorDebugCode interface [.NET Framework debugging]
- ICorDebugCode::GetFunction method [.NET Framework debugging]
ms.assetid: c568b737-fdb2-4816-accd-051f5ab760f1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0104a52c3aa206f86daff30d9d16298e6beae324
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59099457"
---
# <a name="icordebugcodegetfunction-method"></a><span data-ttu-id="6b93b-102">ICorDebugCode::GetFunction メソッド</span><span class="sxs-lookup"><span data-stu-id="6b93b-102">ICorDebugCode::GetFunction Method</span></span>
<span data-ttu-id="6b93b-103">この"ICorDebugCode"に関連付けられている"ICorDebugFunction"を取得します。</span><span class="sxs-lookup"><span data-stu-id="6b93b-103">Gets the "ICorDebugFunction" associated with this "ICorDebugCode".</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b93b-104">構文</span><span class="sxs-lookup"><span data-stu-id="6b93b-104">Syntax</span></span>  
  
```  
HRESULT GetFunction (  
    [out] ICorDebugFunction **ppFunction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6b93b-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6b93b-105">Parameters</span></span>  
 `ppFunction`  
 <span data-ttu-id="6b93b-106">[out]関数のアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="6b93b-106">[out] A pointer to the address of the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6b93b-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="6b93b-107">Remarks</span></span>  
 `ICorDebugCode` <span data-ttu-id="6b93b-108">`ICorDebugFunction`一対一の関係を維持します。</span><span class="sxs-lookup"><span data-stu-id="6b93b-108">and `ICorDebugFunction` maintain a one-to-one relationship.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6b93b-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="6b93b-109">Requirements</span></span>  
 <span data-ttu-id="6b93b-110">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6b93b-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6b93b-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6b93b-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6b93b-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6b93b-112">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="6b93b-113">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="6b93b-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="6b93b-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="6b93b-114">See also</span></span>
