---
title: ICorProfilerCallback::RemotingServerReceivingMessage メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RemotingServerReceivingMessage
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RemotingServerReceivingMessage
helpviewer_keywords:
- ICorProfilerCallback::RemotingServerReceivingMessage method [.NET Framework profiling]
- RemotingServerReceivingMessage method [.NET Framework profiling]
ms.assetid: 5604d21f-e6b7-490e-b469-42122a7568e1
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 952ae17fa288abe6b97f1d8630da2c8f320f955b
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57476282"
---
# <a name="icorprofilercallbackremotingserverreceivingmessage-method"></a><span data-ttu-id="d928c-102">ICorProfilerCallback::RemotingServerReceivingMessage メソッド</span><span class="sxs-lookup"><span data-stu-id="d928c-102">ICorProfilerCallback::RemotingServerReceivingMessage Method</span></span>
<span data-ttu-id="d928c-103">プロセスがリモート メソッド呼び出しまたはアクティブ化要求を受信したことをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="d928c-103">Notifies the profiler that the process has received a remote method invocation or activation request.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d928c-104">構文</span><span class="sxs-lookup"><span data-stu-id="d928c-104">Syntax</span></span>  
  
```  
HRESULT RemotingClientSendingMessage(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d928c-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d928c-105">Parameters</span></span>  
 `pCookie`  
 <span data-ttu-id="d928c-106">[in]指定された値に対応する値[icorprofilercallback::remotingclientsendingmessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientsendingmessage-method.md)これらの条件下で。</span><span class="sxs-lookup"><span data-stu-id="d928c-106">[in] A value that will correspond with the value provided in [ICorProfilerCallback::RemotingClientSendingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientsendingmessage-method.md) under these conditions:</span></span>  
  
-   <span data-ttu-id="d928c-107">リモート処理の GUID の cookie はアクティブです。</span><span class="sxs-lookup"><span data-stu-id="d928c-107">Remoting GUID cookies are active.</span></span>  
  
-   <span data-ttu-id="d928c-108">チャネルは、メッセージの送信に成功します。</span><span class="sxs-lookup"><span data-stu-id="d928c-108">The channel succeeds in transmitting the message.</span></span>  
  
-   <span data-ttu-id="d928c-109">GUID の cookie は、クライアント側のプロセスでアクティブにします。</span><span class="sxs-lookup"><span data-stu-id="d928c-109">GUID cookies are active on the client-side process.</span></span>  
  
 <span data-ttu-id="d928c-110">これにより、リモート処理呼び出しと論理呼び出し履歴の作成のペアを容易にします。</span><span class="sxs-lookup"><span data-stu-id="d928c-110">This allows easy pairing of remoting calls and the creation of a logical call stack.</span></span>  
  
 `fIsAsync`  
 <span data-ttu-id="d928c-111">[in]値が`true`呼び出しが非同期。 それ以外の場合`false`します。</span><span class="sxs-lookup"><span data-stu-id="d928c-111">[in] A value that is `true` if the call is asynchronous; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d928c-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="d928c-112">Remarks</span></span>  
 <span data-ttu-id="d928c-113">メッセージの要求が非同期の場合は、任意のスレッドによって、要求を処理することができます。</span><span class="sxs-lookup"><span data-stu-id="d928c-113">If the message request is asynchronous, the request can be serviced by any arbitrary thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d928c-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="d928c-114">Requirements</span></span>  
 <span data-ttu-id="d928c-115">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d928c-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d928c-116">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d928c-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d928c-117">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d928c-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d928c-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d928c-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d928c-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="d928c-119">See also</span></span>
- [<span data-ttu-id="d928c-120">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d928c-120">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
