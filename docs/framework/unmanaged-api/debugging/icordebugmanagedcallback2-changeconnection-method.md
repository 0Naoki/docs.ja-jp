---
title: ICorDebugManagedCallback2::ChangeConnection メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2.ChangeConnection
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2::ChangeConnection
helpviewer_keywords:
- ICorDebugManagedCallback2::ChangeConnection method [.NET Framework debugging]
- ChangeConnection method [.NET Framework debugging]
ms.assetid: 7263f9a9-4c0b-4d82-a181-288873fb2b18
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b4eeecc22db5786f66b3d484b521989e71817d8e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61995120"
---
# <a name="icordebugmanagedcallback2changeconnection-method"></a><span data-ttu-id="80fe5-102">ICorDebugManagedCallback2::ChangeConnection メソッド</span><span class="sxs-lookup"><span data-stu-id="80fe5-102">ICorDebugManagedCallback2::ChangeConnection Method</span></span>
<span data-ttu-id="80fe5-103">指定された接続に関連付けられているタスクのセットが変更されたことをデバッガーに通知します。</span><span class="sxs-lookup"><span data-stu-id="80fe5-103">Notifies the debugger that the set of tasks associated with the specified connection has changed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80fe5-104">構文</span><span class="sxs-lookup"><span data-stu-id="80fe5-104">Syntax</span></span>  
  
```  
HRESULT ChangeConnection (  
    [in] ICorDebugProcess     *pProcess,  
    [in] CONNID               dwConnectionId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="80fe5-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="80fe5-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="80fe5-106">[in]変更された接続を含むプロセスを表す"ICorDebugProcess"オブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="80fe5-106">[in] A pointer to an "ICorDebugProcess" object that represents the process containing the connection that changed.</span></span>  
  
 `dwConnectionId`  
 <span data-ttu-id="80fe5-107">[in]変更された接続の ID。</span><span class="sxs-lookup"><span data-stu-id="80fe5-107">[in] The ID of the connection that changed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="80fe5-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="80fe5-108">Remarks</span></span>  
 <span data-ttu-id="80fe5-109">A`ChangeConnection`コールバックは、次の場合のいずれかで発生します。</span><span class="sxs-lookup"><span data-stu-id="80fe5-109">A `ChangeConnection` callback will be fired in either of the following cases:</span></span>  
  
- <span data-ttu-id="80fe5-110">ときに、デバッガーは、接続を含むプロセスにアタッチされます。</span><span class="sxs-lookup"><span data-stu-id="80fe5-110">When a debugger attaches to a process that contains connections.</span></span> <span data-ttu-id="80fe5-111">ランタイムの生成し、ディスパッチここを[icordebugmanagedcallback 2::createconnection](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-createconnection-method.md)イベントと`ChangeConnection`プロセス内の各接続のイベント。</span><span class="sxs-lookup"><span data-stu-id="80fe5-111">In this case, the runtime will generate and dispatch a [ICorDebugManagedCallback2::CreateConnection](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-createconnection-method.md) event and a `ChangeConnection` event for each connection in the process.</span></span> <span data-ttu-id="80fe5-112">A`ChangeConnection`その接続の一連のタスクが作成されてから変更されたかどうかに関係なく、すべての既存の接続のイベントが生成されます。</span><span class="sxs-lookup"><span data-stu-id="80fe5-112">A `ChangeConnection` event is generated for every existing connection, regardless of whether that connection’s set of tasks has been changed since its creation.</span></span>  
  
- <span data-ttu-id="80fe5-113">ホストが呼び出したときに[iclrdebugmanager::setconnectiontasks](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md)で、[ホスト API](../../../../docs/framework/unmanaged-api/hosting/index.md)します。</span><span class="sxs-lookup"><span data-stu-id="80fe5-113">When a host calls [ICLRDebugManager::SetConnectionTasks](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md) in the [Hosting API](../../../../docs/framework/unmanaged-api/hosting/index.md).</span></span>  
  
 <span data-ttu-id="80fe5-114">デバッガーでは、新しい変更を取得するプロセスのすべてのスレッドをスキャンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="80fe5-114">The debugger should scan all threads in the process to pick up the new changes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="80fe5-115">必要条件</span><span class="sxs-lookup"><span data-stu-id="80fe5-115">Requirements</span></span>  
 <span data-ttu-id="80fe5-116">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="80fe5-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="80fe5-117">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="80fe5-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="80fe5-118">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="80fe5-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="80fe5-119">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="80fe5-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80fe5-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="80fe5-120">See also</span></span>

- [<span data-ttu-id="80fe5-121">ICorDebugManagedCallback2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="80fe5-121">ICorDebugManagedCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="80fe5-122">ICorDebugManagedCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="80fe5-122">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
