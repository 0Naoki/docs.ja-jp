---
title: ICorDebugManagedCallback::LogSwitch メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.LogSwitch
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::LogSwitch
helpviewer_keywords:
- LogSwitch method [.NET Framework debugging]
- ICorDebugManagedCallback::LogSwitch method [.NET Framework debugging]
ms.assetid: 0ac59d27-783f-4a87-b7a8-baa3ccc54582
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4b8e0807cd03c7abfee0856d52cae0454b9f1a29
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54587792"
---
# <a name="icordebugmanagedcallbacklogswitch-method"></a><span data-ttu-id="6de27-102">ICorDebugManagedCallback::LogSwitch メソッド</span><span class="sxs-lookup"><span data-stu-id="6de27-102">ICorDebugManagedCallback::LogSwitch Method</span></span>
<span data-ttu-id="6de27-103">共通言語ランタイム (CLR) によって管理されるスレッドがメソッドを呼び出すことをデバッガーに通知、<xref:System.Diagnostics.Switch>クラスを作成、変更、またはデバッグとトレース スイッチを削除します。</span><span class="sxs-lookup"><span data-stu-id="6de27-103">Notifies the debugger that a common language runtime (CLR) managed thread has called a method in the <xref:System.Diagnostics.Switch> class to create, modify, or delete a debugging/tracing switch.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6de27-104">構文</span><span class="sxs-lookup"><span data-stu-id="6de27-104">Syntax</span></span>  
  
```  
HRESULT LogSwitch (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] LONG                 lLevel,  
    [in] ULONG                ulReason,  
    [in] WCHAR               *pLogSwitchName,  
    [in] WCHAR               *pParentName);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6de27-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6de27-105">Parameters</span></span>  
 `PAppDomain`  
 <span data-ttu-id="6de27-106">[in]ICorDebugAppDomain を表すオブジェクトを作成、変更、またはデバッグとトレース スイッチを削除するマネージ スレッドを格納しているアプリケーション ドメインへのポインター。</span><span class="sxs-lookup"><span data-stu-id="6de27-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the managed thread that created, modified, or deleted a debugging/tracing switch.</span></span>  
  
 `pThread`  
 <span data-ttu-id="6de27-107">[in]マネージ スレッドを表す ICorDebugThread オブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="6de27-107">[in] A pointer to an ICorDebugThread object that represents the managed thread.</span></span>  
  
 `lLevel`  
 <span data-ttu-id="6de27-108">[in]イベント ログに書き込まれた内容を示すメッセージの重大度レベルを示す値。</span><span class="sxs-lookup"><span data-stu-id="6de27-108">[in] A value that indicates the severity level of the descriptive message that was written to the event log.</span></span>  
  
 `ulReason`  
 <span data-ttu-id="6de27-109">[in]値、 [LogSwitchCallReason](../../../../docs/framework/unmanaged-api/debugging/logswitchcallreason-enumeration.md)デバッグとトレース スイッチの操作を示す列挙を実行します。</span><span class="sxs-lookup"><span data-stu-id="6de27-109">[in] A value of the [LogSwitchCallReason](../../../../docs/framework/unmanaged-api/debugging/logswitchcallreason-enumeration.md) enumeration that indicates the operation performed on the debugging/tracing switch.</span></span>  
  
 `pLogSwitchName`  
 <span data-ttu-id="6de27-110">[in]デバッグとトレース スイッチの名前へのポインター。</span><span class="sxs-lookup"><span data-stu-id="6de27-110">[in] A pointer to the name of the debugging/tracing switch.</span></span>  
  
 `pParentName`  
 <span data-ttu-id="6de27-111">[in]デバッグとトレース スイッチの親の名前へのポインター。</span><span class="sxs-lookup"><span data-stu-id="6de27-111">[in] A pointer to the name of the parent of the debugging/tracing switch.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6de27-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="6de27-112">Requirements</span></span>  
 <span data-ttu-id="6de27-113">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6de27-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6de27-114">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6de27-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6de27-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6de27-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6de27-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6de27-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6de27-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="6de27-117">See also</span></span>
- [<span data-ttu-id="6de27-118">ICorDebugManagedCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6de27-118">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
