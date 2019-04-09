---
title: ICorDebugManagedCallback::ExitProcess メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.ExitProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::ExitProcess
helpviewer_keywords:
- ExitProcess method, ICorDebugManagedCallback interface [.NET Framework debugging]
- ICorDebugManagedCallback::ExitProcess method [.NET Framework debugging]
ms.assetid: 63a7d47a-0d54-4e29-9767-9f09feaa38b7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 51162bfb6f9763d2ab4ac1f86e0ccdc15b601271
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59159875"
---
# <a name="icordebugmanagedcallbackexitprocess-method"></a><span data-ttu-id="e05ab-102">ICorDebugManagedCallback::ExitProcess メソッド</span><span class="sxs-lookup"><span data-stu-id="e05ab-102">ICorDebugManagedCallback::ExitProcess Method</span></span>
<span data-ttu-id="e05ab-103">プロセスが終了していることをデバッガーに通知します。</span><span class="sxs-lookup"><span data-stu-id="e05ab-103">Notifies the debugger that a process has exited.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e05ab-104">構文</span><span class="sxs-lookup"><span data-stu-id="e05ab-104">Syntax</span></span>  
  
```  
HRESULT ExitProcess (  
    [in] ICorDebugProcess *pProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e05ab-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e05ab-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="e05ab-106">[in]プロセスを表す ICorDebugProcess オブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="e05ab-106">[in] A pointer to an ICorDebugProcess object that represents the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e05ab-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="e05ab-107">Remarks</span></span>  
 <span data-ttu-id="e05ab-108">継続することはできません、`ExitProcess`イベント。</span><span class="sxs-lookup"><span data-stu-id="e05ab-108">You cannot continue from an `ExitProcess` event.</span></span> <span data-ttu-id="e05ab-109">このイベントは、プロセスが停止するのに見えますが他のイベントに非同期的に発生可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e05ab-109">This event may fire asynchronously to other events while the process appears to be stopped.</span></span> <span data-ttu-id="e05ab-110">これは、停止している間、通常の外的要因により、プロセスが終了した場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="e05ab-110">This can occur if the process terminates while stopped, usually due to some external force.</span></span>  
  
 <span data-ttu-id="e05ab-111">共通言語ランタイム (CLR) では、マネージ コールバックをディスパッチは既に場合、そのコールバックが返された後に、このイベントはまで延期されます。</span><span class="sxs-lookup"><span data-stu-id="e05ab-111">If the common language runtime (CLR) is already dispatching a managed callback, this event will be delayed until after that callback has returned.</span></span>  
  
 <span data-ttu-id="e05ab-112">`ExitProcess`イベントは、シャット ダウン時に呼び出されることが保証される唯一の終了/アンロード イベント。</span><span class="sxs-lookup"><span data-stu-id="e05ab-112">The `ExitProcess` event is the only exit/unload event that is guaranteed to get called on shutdown.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e05ab-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="e05ab-113">Requirements</span></span>  
 <span data-ttu-id="e05ab-114">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e05ab-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e05ab-115">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e05ab-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e05ab-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e05ab-116">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="e05ab-117">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="e05ab-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e05ab-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="e05ab-118">See also</span></span>

- [<span data-ttu-id="e05ab-119">ICorDebugManagedCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e05ab-119">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
