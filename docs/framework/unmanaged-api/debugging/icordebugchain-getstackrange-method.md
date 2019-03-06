---
title: ICorDebugChain::GetStackRange メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetStackRange
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::GetStackRange
helpviewer_keywords:
- ICorDebugChain::GetStackRange method [.NET Framework debugging]
- GetStackRange method, ICorDebugChain interface [.NET Framework debugging]
ms.assetid: 554284e7-3f6c-4d40-8da5-1c9317fbd484
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ac40927ac9469e4a2fb74fb550287130b9bb9f83
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57481561"
---
# <a name="icordebugchaingetstackrange-method"></a><span data-ttu-id="66ea1-102">ICorDebugChain::GetStackRange メソッド</span><span class="sxs-lookup"><span data-stu-id="66ea1-102">ICorDebugChain::GetStackRange Method</span></span>
<span data-ttu-id="66ea1-103">このチェーンの履歴のセグメントのアドレス範囲を取得します。</span><span class="sxs-lookup"><span data-stu-id="66ea1-103">Gets the address range of the stack segment for this chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66ea1-104">構文</span><span class="sxs-lookup"><span data-stu-id="66ea1-104">Syntax</span></span>  
  
```  
HRESULT GetStackRange (  
    [out] CORDB_ADDRESS      *pStart,   
    [out] CORDB_ADDRESS      *pEnd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="66ea1-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="66ea1-105">Parameters</span></span>  
 `pStart`  
 <span data-ttu-id="66ea1-106">[out]ポインターを`CORDB_ADDRESS`値が履歴のセグメントの開始アドレスです。</span><span class="sxs-lookup"><span data-stu-id="66ea1-106">[out] A pointer to a `CORDB_ADDRESS` value that is the starting address of the stack segment.</span></span>  
  
 `pEnd`  
 <span data-ttu-id="66ea1-107">[out]ポインターを`CORDB_ADDRESS`スタック セグメントの終了アドレスである値。</span><span class="sxs-lookup"><span data-stu-id="66ea1-107">[out] A pointer to a `CORDB_ADDRESS` value that is the ending address of the stack segment.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="66ea1-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="66ea1-108">Remarks</span></span>  
 <span data-ttu-id="66ea1-109">数値の範囲は、スタック フレームの場所の比較についてのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="66ea1-109">The numeric range is meaningful only for comparison of stack frame locations.</span></span> <span data-ttu-id="66ea1-110">実際にスタックに格納されているものを想定することはできません。</span><span class="sxs-lookup"><span data-stu-id="66ea1-110">You cannot make any assumptions about what is actually stored on the stack.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="66ea1-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="66ea1-111">Requirements</span></span>  
 <span data-ttu-id="66ea1-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="66ea1-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="66ea1-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="66ea1-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="66ea1-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="66ea1-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="66ea1-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="66ea1-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
