---
title: ICorDebugManagedCallback::DebuggerError メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.DebuggerError
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::DebuggerError
helpviewer_keywords:
- DebuggerError method [.NET Framework debugging]
- ICorDebugManagedCallback::DebuggerError method [.NET Framework debugging]
ms.assetid: 9e983d11-eaf3-4741-b936-29ec456384a3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 25af2c8fa3e3d49b3c2832a69f14b2691585d775
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57489849"
---
# <a name="icordebugmanagedcallbackdebuggererror-method"></a><span data-ttu-id="27b28-102">ICorDebugManagedCallback::DebuggerError メソッド</span><span class="sxs-lookup"><span data-stu-id="27b28-102">ICorDebugManagedCallback::DebuggerError Method</span></span>
<span data-ttu-id="27b28-103">共通言語ランタイム (CLR) からのイベントの処理を試行中にエラーが発生したことをデバッガーに通知します。</span><span class="sxs-lookup"><span data-stu-id="27b28-103">Notifies the debugger that an error has occurred while attempting to handle an event from the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27b28-104">構文</span><span class="sxs-lookup"><span data-stu-id="27b28-104">Syntax</span></span>  
  
```  
HRESULT DebuggerError (  
    [in] ICorDebugProcess *pProcess,  
    [in] HRESULT           errorHR,  
    [in] DWORD             errorCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="27b28-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="27b28-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="27b28-106">[in]イベントが発生したプロセスを表す"ICorDebugProcess"オブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="27b28-106">[in] A pointer to an "ICorDebugProcess" object that represents the process in which the event occurred.</span></span>  
  
 `errorHR`  
 <span data-ttu-id="27b28-107">[in]イベント ハンドラーから返された HRESULT 値。</span><span class="sxs-lookup"><span data-stu-id="27b28-107">[in] The HRESULT value that was returned from the event handler.</span></span>  
  
 `errorCode`  
 <span data-ttu-id="27b28-108">[in]CLR エラーを示す整数。</span><span class="sxs-lookup"><span data-stu-id="27b28-108">[in] An integer that specifies the CLR error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="27b28-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="27b28-109">Remarks</span></span>  
 <span data-ttu-id="27b28-110">プロセスは、パススルー モードでは、エラーの性質によってに配置することがあります。</span><span class="sxs-lookup"><span data-stu-id="27b28-110">The process may be placed into pass-through mode, depending on the nature of the error.</span></span>  
  
 <span data-ttu-id="27b28-111">`DebugError`コールバックでは、デバッグ サービスが無効である、エラーのため、デバッガーは、エラー メッセージを使用できるように、ユーザーを示します。</span><span class="sxs-lookup"><span data-stu-id="27b28-111">The `DebugError` callback indicates that debugging services have been disabled due to an error, so debuggers should make the error message available to the user.</span></span> <span data-ttu-id="27b28-112">[Icordebugprocess::getid](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getid-method.md)など、他のすべてのメソッド呼び出しになれる[icordebug::terminate](../../../../docs/framework/unmanaged-api/debugging/icordebug-terminate-method.md)、呼び出すことはできません。</span><span class="sxs-lookup"><span data-stu-id="27b28-112">[ICorDebugProcess::GetID](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getid-method.md) will be safe to call, but all other methods, including [ICorDebug::Terminate](../../../../docs/framework/unmanaged-api/debugging/icordebug-terminate-method.md), should not be called.</span></span> <span data-ttu-id="27b28-113">デバッガーは、プロセスを終了するためにオペレーティング システムの機能を使用します。</span><span class="sxs-lookup"><span data-stu-id="27b28-113">The debugger should use operating-system facilities for terminating processes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="27b28-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="27b28-114">Requirements</span></span>  
 <span data-ttu-id="27b28-115">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="27b28-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="27b28-116">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="27b28-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="27b28-117">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="27b28-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="27b28-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="27b28-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27b28-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="27b28-119">See also</span></span>
- [<span data-ttu-id="27b28-120">ICorDebugManagedCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="27b28-120">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
