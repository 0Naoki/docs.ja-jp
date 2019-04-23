---
title: ICorDebugManagedCallback::BreakpointSetError メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.BreakpointSetError
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::BreakpointSetError
helpviewer_keywords:
- BreakpointSetError method [.NET Framework debugging]
- ICorDebugManagedCallback::BreakpointSetError method [.NET Framework debugging]
ms.assetid: f2b773a4-c4d0-429c-9717-51d6e2ed86af
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 27d5b8e0127971cc3a46560590fd9d95f0ffd1f0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59151022"
---
# <a name="icordebugmanagedcallbackbreakpointseterror-method"></a><span data-ttu-id="c205c-102">ICorDebugManagedCallback::BreakpointSetError メソッド</span><span class="sxs-lookup"><span data-stu-id="c205c-102">ICorDebugManagedCallback::BreakpointSetError Method</span></span>
<span data-ttu-id="c205c-103">共通言語ランタイムが関数の just-in-time (JIT) コンパイル前に設定されたブレークポイントを正確にバインドできなかったことをデバッガーに通知します。</span><span class="sxs-lookup"><span data-stu-id="c205c-103">Notifies the debugger that the common language runtime was unable to accurately bind a breakpoint that was set before a function was just-in-time (JIT) compiled.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c205c-104">構文</span><span class="sxs-lookup"><span data-stu-id="c205c-104">Syntax</span></span>  
  
```  
HRESULT BreakpointSetError (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] ICorDebugBreakpoint *pBreakpoint,  
    [in] DWORD                dwError  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c205c-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c205c-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="c205c-106">[in]バインドされていないブレークポイントを含むアプリケーション ドメインを表す ICorDebugAppDomain オブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="c205c-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contains the unbound breakpoint.</span></span>  
  
 `pThread`  
 <span data-ttu-id="c205c-107">[in]バインドされていないブレークポイントを含むスレッドを表す ICorDebugThread オブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="c205c-107">[in] A pointer to an ICorDebugThread object that represents the thread that contains the unbound breakpoint.</span></span>  
  
 `pBreakpoint`  
 <span data-ttu-id="c205c-108">[in]バインドされていない、ブレークポイントを表す ICorDebugBreakpoint オブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="c205c-108">[in] A pointer to an ICorDebugBreakpoint object that represents the unbound breakpoint.</span></span>  
  
 `dwError`  
 <span data-ttu-id="c205c-109">[in]エラーを示す整数。</span><span class="sxs-lookup"><span data-stu-id="c205c-109">[in] An integer that indicates the error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c205c-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="c205c-110">Remarks</span></span>  
 <span data-ttu-id="c205c-111">特定のブレークポイントに到達しません。</span><span class="sxs-lookup"><span data-stu-id="c205c-111">The given breakpoint will never be hit.</span></span> <span data-ttu-id="c205c-112">デバッガーは、非アクティブ化し、再バインドする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c205c-112">The debugger should deactivate and rebind it.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c205c-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="c205c-113">Requirements</span></span>  
 <span data-ttu-id="c205c-114">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c205c-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c205c-115">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c205c-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c205c-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c205c-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c205c-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c205c-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c205c-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="c205c-118">See also</span></span>

- [<span data-ttu-id="c205c-119">ICorDebugManagedCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c205c-119">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
