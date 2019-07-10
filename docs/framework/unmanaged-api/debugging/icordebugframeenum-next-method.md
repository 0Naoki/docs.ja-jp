---
title: ICorDebugFrameEnum::Next メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugFrameEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrameEnum::Next
helpviewer_keywords:
- ICorDebugFrameEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugFrameEnum interface [.NET Framework debugging]
ms.assetid: 0bc96acb-6179-4328-a447-cda562ce9e98
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9be126e45d8428d8786e9aadf2195133d1957440
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67754824"
---
# <a name="icordebugframeenumnext-method"></a><span data-ttu-id="a764f-102">ICorDebugFrameEnum::Next メソッド</span><span class="sxs-lookup"><span data-stu-id="a764f-102">ICorDebugFrameEnum::Next Method</span></span>
<span data-ttu-id="a764f-103">ICorDebugFrame インスタンスの現在位置から指定の数を取得します。</span><span class="sxs-lookup"><span data-stu-id="a764f-103">Gets the specified number of ICorDebugFrame instances, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a764f-104">構文</span><span class="sxs-lookup"><span data-stu-id="a764f-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugFrame *frames[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a764f-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a764f-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="a764f-106">[in]数`ICorDebugFrame`インスタンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="a764f-106">[in] The number of `ICorDebugFrame` instances to be retrieved.</span></span>  
  
 `frames`  
 <span data-ttu-id="a764f-107">[out]それぞれが指すポインターの配列、`ICorDebugFrame`オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="a764f-107">[out] An array of pointers, each of which points to an `ICorDebugFrame` object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="a764f-108">[out]数へのポインター`ICorDebugFrame`インスタンスが実際に返されます。</span><span class="sxs-lookup"><span data-stu-id="a764f-108">[out] A pointer to the number of `ICorDebugFrame` instances actually returned.</span></span> <span data-ttu-id="a764f-109">この値は null になる場合`celt`は 1 つです。</span><span class="sxs-lookup"><span data-stu-id="a764f-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a764f-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="a764f-110">Requirements</span></span>  
 <span data-ttu-id="a764f-111">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a764f-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a764f-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a764f-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a764f-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a764f-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a764f-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a764f-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
