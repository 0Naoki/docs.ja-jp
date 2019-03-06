---
title: ICorDebugStepperEnum::Next メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugStepperEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepperEnum::Next
helpviewer_keywords:
- Next method, ICorDebugStepperEnum interface [.NET Framework debugging]
- ICorDebugStepperEnum::Next method [.NET Framework debugging]
ms.assetid: d0ea0f30-e8d2-48b0-8477-e1a029ceb4dd
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6ac3165ab17eb1b4bc55a4bee4d2d2b467f8aefe
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57494598"
---
# <a name="icordebugstepperenumnext-method"></a><span data-ttu-id="f17ca-102">ICorDebugStepperEnum::Next メソッド</span><span class="sxs-lookup"><span data-stu-id="f17ca-102">ICorDebugStepperEnum::Next Method</span></span>
<span data-ttu-id="f17ca-103">現在の位置から始まり、列挙体から ICorDebugStepper インスタンスの指定した数を取得します。</span><span class="sxs-lookup"><span data-stu-id="f17ca-103">Gets the specified number of ICorDebugStepper instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f17ca-104">構文</span><span class="sxs-lookup"><span data-stu-id="f17ca-104">Syntax</span></span>  
  
```  
HRESULT Next(  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugStepper *steppers[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f17ca-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f17ca-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="f17ca-106">[in]数`ICorDebugStepper`インスタンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="f17ca-106">[in] The number of `ICorDebugStepper` instances to be retrieved.</span></span>  
  
 `steppers`  
 <span data-ttu-id="f17ca-107">[out]それぞれが指すポインターの配列、`ICorDebugStepper`オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="f17ca-107">[out] An array of pointers, each of which points to an `ICorDebugStepper` object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="f17ca-108">[out]数へのポインター`ICorDebugStepper`インスタンスが実際に返されます。</span><span class="sxs-lookup"><span data-stu-id="f17ca-108">[out] Pointer to the number of `ICorDebugStepper` instances actually returned.</span></span> <span data-ttu-id="f17ca-109">この値は null になる場合`celt`は 1 つです。</span><span class="sxs-lookup"><span data-stu-id="f17ca-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f17ca-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="f17ca-110">Requirements</span></span>  
 <span data-ttu-id="f17ca-111">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f17ca-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f17ca-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f17ca-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f17ca-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f17ca-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f17ca-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f17ca-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
