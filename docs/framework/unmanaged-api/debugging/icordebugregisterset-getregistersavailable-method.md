---
title: ICorDebugRegisterSet::GetRegistersAvailable メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet.GetRegistersAvailable
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet::GetRegistersAvailable
helpviewer_keywords:
- ICorDebugRegisterSet::GetRegistersAvailable method [.NET Framework debugging]
- GetRegistersAvailable method, ICorDebugRegisterSet interface [.NET Framework debugging]
ms.assetid: 4ba08ffa-55a2-4662-9d6d-4738f1db60c9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f57e4a72828cdf744d5acd5483024de7d303f4a2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54743349"
---
# <a name="icordebugregistersetgetregistersavailable-method"></a><span data-ttu-id="81bac-102">ICorDebugRegisterSet::GetRegistersAvailable メソッド</span><span class="sxs-lookup"><span data-stu-id="81bac-102">ICorDebugRegisterSet::GetRegistersAvailable Method</span></span>
<span data-ttu-id="81bac-103">これで登録することを示す取得がビット マスク[ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)現在利用します。</span><span class="sxs-lookup"><span data-stu-id="81bac-103">Gets a bit mask indicating which registers in this [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) are currently available.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="81bac-104">構文</span><span class="sxs-lookup"><span data-stu-id="81bac-104">Syntax</span></span>  
  
```  
HRESULT GetRegistersAvailable (  
    [out] ULONG64   *pAvailable  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="81bac-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="81bac-105">Parameters</span></span>  
 `pAvailable`  
 <span data-ttu-id="81bac-106">[out]どのレジスタが現在の使用を示すビット マスクです。</span><span class="sxs-lookup"><span data-stu-id="81bac-106">[out] A bit mask that indicates which registers are currently available.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="81bac-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="81bac-107">Remarks</span></span>  
 <span data-ttu-id="81bac-108">レジスタは、その値は、特定の状況を特定できない場合に使用できない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="81bac-108">A register may be unavailable if its value cannot be determined for the given situation.</span></span>  
  
 <span data-ttu-id="81bac-109">返されたマスクには、各レジスタのビットが含まれています (1 << レジスタのインデックス)。</span><span class="sxs-lookup"><span data-stu-id="81bac-109">The returned mask contains a bit for each register (1 << the register index).</span></span> <span data-ttu-id="81bac-110">登録がある場合は、ビット値が 1 または 0 が使用できない場合。</span><span class="sxs-lookup"><span data-stu-id="81bac-110">The bit value is 1 if the register is available, or 0 if it is not available.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="81bac-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="81bac-111">Requirements</span></span>  
 <span data-ttu-id="81bac-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="81bac-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="81bac-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="81bac-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="81bac-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="81bac-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="81bac-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="81bac-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81bac-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="81bac-116">See also</span></span>
- [<span data-ttu-id="81bac-117">ICorDebugRegisterSet インターフェイス</span><span class="sxs-lookup"><span data-stu-id="81bac-117">ICorDebugRegisterSet Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)
- [<span data-ttu-id="81bac-118">ICorDebugRegisterSet2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="81bac-118">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
