---
title: ICorDebugManagedCallback2::FunctionRemapComplete メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2.FunctionRemapComplete
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2::FunctionRemapComplete
helpviewer_keywords:
- FunctionRemapComplete method [.NET Framework debugging]
- ICorDebugManagedCallback2::FunctionRemapComplete method [.NET Framework debugging]
ms.assetid: 5396c4c3-4ec3-4e3a-a38d-d65b21f0a2fc
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a5f4c9b6afd9b0a7a43c279c9a070740100d8f86
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57478623"
---
# <a name="icordebugmanagedcallback2functionremapcomplete-method"></a><span data-ttu-id="f559e-102">ICorDebugManagedCallback2::FunctionRemapComplete メソッド</span><span class="sxs-lookup"><span data-stu-id="f559e-102">ICorDebugManagedCallback2::FunctionRemapComplete Method</span></span>
<span data-ttu-id="f559e-103">編集された関数の新しいバージョンにコードが実行を切り替えたことをデバッガーに通知します。</span><span class="sxs-lookup"><span data-stu-id="f559e-103">Notifies the debugger that code execution has switched to a new version of an edited function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f559e-104">構文</span><span class="sxs-lookup"><span data-stu-id="f559e-104">Syntax</span></span>  
  
```  
HRESULT FunctionRemapComplete (  
    [in] ICorDebugAppDomain   *pAppDomain,  
    [in] ICorDebugThread      *pThread,  
    [in] ICorDebugFunction    *pFunction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f559e-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f559e-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="f559e-106">[in]編集された関数を格納しているアプリケーション ドメインを表す ICorDebugAppDomain オブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="f559e-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the edited function.</span></span>  
  
 `pThread`  
 <span data-ttu-id="f559e-107">[in]リマップ ブレークポイントが発生しました、スレッドを表す ICorDebugThread オブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="f559e-107">[in] A pointer to an ICorDebugThread object that represents the thread on which the remap breakpoint was encountered.</span></span>  
  
 `pFunction`  
 <span data-ttu-id="f559e-108">[in]現在のスレッドで実行されている関数のバージョンを表す ICorDebugFunction オブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="f559e-108">[in] A pointer to an ICorDebugFunction object that represents the version of the function currently running on the thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f559e-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="f559e-109">Remarks</span></span>  
 <span data-ttu-id="f559e-110">このコールバックでは、デバッガーは既に存在していたステッパを再作成できます。</span><span class="sxs-lookup"><span data-stu-id="f559e-110">This callback gives the debugger an opportunity to recreate any steppers that previously existed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f559e-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="f559e-111">Requirements</span></span>  
 <span data-ttu-id="f559e-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f559e-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f559e-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f559e-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f559e-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f559e-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f559e-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f559e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f559e-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="f559e-116">See also</span></span>
- [<span data-ttu-id="f559e-117">ICorDebugManagedCallback2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f559e-117">ICorDebugManagedCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="f559e-118">ICorDebugManagedCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f559e-118">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
