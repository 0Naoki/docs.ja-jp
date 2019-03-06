---
title: ICorDebugManagedCallback::StepComplete メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.StepComplete
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::StepComplete
helpviewer_keywords:
- StepComplete method [.NET Framework debugging]
- ICorDebugManagedCallback::StepComplete method [.NET Framework debugging]
ms.assetid: 5e1f2c47-81df-4530-826d-96489cd68719
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f5b243d8c618559bd4371bf3acde1136f532f55e
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57476140"
---
# <a name="icordebugmanagedcallbackstepcomplete-method"></a><span data-ttu-id="454c5-102">ICorDebugManagedCallback::StepComplete メソッド</span><span class="sxs-lookup"><span data-stu-id="454c5-102">ICorDebugManagedCallback::StepComplete Method</span></span>
<span data-ttu-id="454c5-103">ステップが完了したことをデバッガーに通知します。</span><span class="sxs-lookup"><span data-stu-id="454c5-103">Notifies the debugger that a step has completed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="454c5-104">構文</span><span class="sxs-lookup"><span data-stu-id="454c5-104">Syntax</span></span>  
  
```  
HRESULT StepComplete (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] ICorDebugStepper    *pStepper,  
    [in] CorDebugStepReason   reason  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="454c5-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="454c5-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="454c5-106">[in]ステップが完了するスレッドを格納しているアプリケーション ドメインを表す ICorDebugAppDomain オブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="454c5-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the thread in which the step has completed.</span></span>  
  
 `pThread`  
 <span data-ttu-id="454c5-107">[in]ステップが完了するスレッドを表す ICorDebugThread オブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="454c5-107">[in] A pointer to an ICorDebugThread object that represents the thread in which the step has completed.</span></span>  
  
 `pStepper`  
 <span data-ttu-id="454c5-108">[in]コードの実行の手順を表す ICorDebugStepper オブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="454c5-108">[in] A pointer to an ICorDebugStepper object that represents the step in code execution.</span></span>  
  
 `reason`  
 <span data-ttu-id="454c5-109">[in]個々 のステップの結果を示す CorDebugStepReason 列挙型の値。</span><span class="sxs-lookup"><span data-stu-id="454c5-109">[in] A value of the CorDebugStepReason enumeration that indicates the outcome of an individual step.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="454c5-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="454c5-110">Remarks</span></span>  
 <span data-ttu-id="454c5-111">ステッパをステップ実行を続ける場合、必要に応じて、デバッグを終了しない限り、使用可能性があります。</span><span class="sxs-lookup"><span data-stu-id="454c5-111">The stepper may be used to continue stepping if desired, unless the debugging is terminated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="454c5-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="454c5-112">Requirements</span></span>  
 <span data-ttu-id="454c5-113">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="454c5-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="454c5-114">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="454c5-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="454c5-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="454c5-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="454c5-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="454c5-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="454c5-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="454c5-117">See also</span></span>
- [<span data-ttu-id="454c5-118">ICorDebugManagedCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="454c5-118">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
