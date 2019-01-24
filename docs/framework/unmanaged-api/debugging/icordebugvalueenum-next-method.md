---
title: ICorDebugValueEnum::Next メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugValueEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValueEnum::Next
helpviewer_keywords:
- ICorDebugValueEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugValueEnum interface [.NET Framework debugging]
ms.assetid: f5ef94dd-dfee-49d3-a398-b110f8906dd8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 020df45f7f18a029f8c098fcc4dea1c131da017c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54706918"
---
# <a name="icordebugvalueenumnext-method"></a><span data-ttu-id="0eff4-102">ICorDebugValueEnum::Next メソッド</span><span class="sxs-lookup"><span data-stu-id="0eff4-102">ICorDebugValueEnum::Next Method</span></span>
<span data-ttu-id="0eff4-103">列挙体の現在位置から指定された"ICorDebugValue"インスタンス数を取得します。</span><span class="sxs-lookup"><span data-stu-id="0eff4-103">Gets the specified number of "ICorDebugValue" instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0eff4-104">構文</span><span class="sxs-lookup"><span data-stu-id="0eff4-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in]  ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugValue *values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0eff4-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0eff4-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="0eff4-106">[in]数`ICorDebugValue`インスタンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="0eff4-106">[in] The number of `ICorDebugValue` instances to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="0eff4-107">[out]それぞれが指すポインターの配列、`ICorDebugValue`オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="0eff4-107">[out] An array of pointers, each of which points to an `ICorDebugValue` object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="0eff4-108">[out]数へのポインター`ICorDebugValue`インスタンスが実際に返されます。</span><span class="sxs-lookup"><span data-stu-id="0eff4-108">[out] Pointer to the number of `ICorDebugValue` instances actually returned.</span></span> <span data-ttu-id="0eff4-109">この値は null になる場合`celt`は 1 つです。</span><span class="sxs-lookup"><span data-stu-id="0eff4-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0eff4-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="0eff4-110">Requirements</span></span>  
 <span data-ttu-id="0eff4-111">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0eff4-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0eff4-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0eff4-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0eff4-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0eff4-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0eff4-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0eff4-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0eff4-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="0eff4-115">See also</span></span>


