---
title: ICorDebugModuleEnum::Next メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugModuleEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModuleEnum::Next
helpviewer_keywords:
- ICorDebugModuleEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugModuleEnum interface [.NET Framework debugging]
ms.assetid: 9ff3fcd6-38fe-41f8-bfd3-f0ab6c7d77ca
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: aa341c726ba84dc1d12b6c5628253a100d65a719
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59167103"
---
# <a name="icordebugmoduleenumnext-method"></a><span data-ttu-id="6350d-102">ICorDebugModuleEnum::Next メソッド</span><span class="sxs-lookup"><span data-stu-id="6350d-102">ICorDebugModuleEnum::Next Method</span></span>
<span data-ttu-id="6350d-103">指定された"ICorDebugModule"インスタンスの数を取得`celt`列挙体の現在位置から。</span><span class="sxs-lookup"><span data-stu-id="6350d-103">Gets the number of "ICorDebugModule" instances specified by `celt` from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6350d-104">構文</span><span class="sxs-lookup"><span data-stu-id="6350d-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in]  ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugModule *modules[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6350d-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6350d-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="6350d-106">[in]数`ICorDebugModule`インスタンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="6350d-106">[in] The number of `ICorDebugModule` instances to be retrieved.</span></span>  
  
 `modules`  
 <span data-ttu-id="6350d-107">[out]それぞれが指すポインターの配列、`ICorDebugModule`オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="6350d-107">[out] An array of pointers, each of which points to an `ICorDebugModule` object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="6350d-108">[out]数へのポインター`ICorDebugModule`インスタンスが実際に返されます。</span><span class="sxs-lookup"><span data-stu-id="6350d-108">[out] Pointer to the number of `ICorDebugModule` instances actually returned.</span></span> <span data-ttu-id="6350d-109">この値は null になる場合`celt`は 1 つです。</span><span class="sxs-lookup"><span data-stu-id="6350d-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6350d-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="6350d-110">Requirements</span></span>  
 <span data-ttu-id="6350d-111">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6350d-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6350d-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6350d-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6350d-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6350d-113">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="6350d-114">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="6350d-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="6350d-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="6350d-115">See also</span></span>
