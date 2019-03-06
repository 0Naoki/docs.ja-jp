---
title: ICorDebugChain::GetReason メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetReason
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- GetReason
helpviewer_keywords:
- GetReason method [.NET Framework debugging]
- ICorDebugChain::GetReason method [.NET Framework debugging]
ms.assetid: 9f9f62b9-113a-4a98-8f9b-b593cef27b03
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 48650a370f7d15724e20850e9d3b47dc8215f960
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57498355"
---
# <a name="icordebugchaingetreason-method"></a><span data-ttu-id="61b54-102">ICorDebugChain::GetReason メソッド</span><span class="sxs-lookup"><span data-stu-id="61b54-102">ICorDebugChain::GetReason Method</span></span>
<span data-ttu-id="61b54-103">この呼び出しチェーンの起源の理由を取得します。</span><span class="sxs-lookup"><span data-stu-id="61b54-103">Gets the reason for the genesis of this calling chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61b54-104">構文</span><span class="sxs-lookup"><span data-stu-id="61b54-104">Syntax</span></span>  
  
```  
HRESULT GetReason (  
    [out] CorDebugChainReason *pReason  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="61b54-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="61b54-105">Parameters</span></span>  
 `pReason`  
 <span data-ttu-id="61b54-106">[out]この呼び出しチェーンの起源の理由を示す CorDebugChainReason 列挙型の値 (ビットごとの組み合わせ) へのポインター。</span><span class="sxs-lookup"><span data-stu-id="61b54-106">[out] A pointer to a value (a bitwise combination) of the CorDebugChainReason enumeration that indicates the reason for the genesis of this calling chain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="61b54-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="61b54-107">Requirements</span></span>  
 <span data-ttu-id="61b54-108">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="61b54-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="61b54-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="61b54-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="61b54-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="61b54-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="61b54-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="61b54-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
