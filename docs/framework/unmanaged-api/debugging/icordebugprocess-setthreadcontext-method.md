---
title: ICorDebugProcess::SetThreadContext メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.SetThreadContext
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::SetThreadContext
helpviewer_keywords:
- ICorDebugProcess::SetThreadContext method [.NET Framework debugging]
- SetThreadContext method, ICorDebugProcess interface [.NET Framework debugging]
ms.assetid: a7b50175-2bf1-40be-8f65-64aec7aa1247
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e281022cd7bc9b2095fdbd3964061b811ef60e0d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61949033"
---
# <a name="icordebugprocesssetthreadcontext-method"></a><span data-ttu-id="82f1a-102">ICorDebugProcess::SetThreadContext メソッド</span><span class="sxs-lookup"><span data-stu-id="82f1a-102">ICorDebugProcess::SetThreadContext Method</span></span>
<span data-ttu-id="82f1a-103">このプロセスでは、特定のスレッドのコンテキストを設定します。</span><span class="sxs-lookup"><span data-stu-id="82f1a-103">Sets the context for the given thread in this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82f1a-104">構文</span><span class="sxs-lookup"><span data-stu-id="82f1a-104">Syntax</span></span>  
  
```  
HRESULT SetThreadContext(  
    [in] DWORD threadID,  
    [in] ULONG32 contextSize,  
    [in, length_is(contextSize), size_is(contextSize)]  
    BYTE context[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="82f1a-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="82f1a-105">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="82f1a-106">[in]コンテキストを設定する対象のスレッドの ID。</span><span class="sxs-lookup"><span data-stu-id="82f1a-106">[in] The ID of the thread for which to set the context.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="82f1a-107">[in] `context` 配列のサイズ。</span><span class="sxs-lookup"><span data-stu-id="82f1a-107">[in] The size of the `context` array.</span></span>  
  
 `context`  
 <span data-ttu-id="82f1a-108">[in]スレッドのコンテキストを表すバイトの配列。</span><span class="sxs-lookup"><span data-stu-id="82f1a-108">[in] An array of bytes that describe the thread's context.</span></span>  
  
 <span data-ttu-id="82f1a-109">コンテキストには、スレッドが実行されているプロセッサのアーキテクチャを指定します。</span><span class="sxs-lookup"><span data-stu-id="82f1a-109">The context specifies the architecture of the processor on which the thread is executing.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="82f1a-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="82f1a-110">Remarks</span></span>  
 <span data-ttu-id="82f1a-111">デバッガーは、Win32 ではなく、このメソッドを呼び出す必要があります`SetThreadContext`関数は、スレッドは、「ハイジャック」をそのコンテキストが一時的に変更された状態で実際にできるためです。</span><span class="sxs-lookup"><span data-stu-id="82f1a-111">The debugger should call this method rather than the Win32 `SetThreadContext` function, because the thread may actually be in a "hijacked" state, in which its context has been temporarily changed.</span></span> <span data-ttu-id="82f1a-112">ネイティブ コードでスレッドがある場合にのみ、このメソッドを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="82f1a-112">This method should be used only when a thread is in native code.</span></span> <span data-ttu-id="82f1a-113">使用[ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)マネージ コード内のスレッドにします。</span><span class="sxs-lookup"><span data-stu-id="82f1a-113">Use [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) for threads in managed code.</span></span> <span data-ttu-id="82f1a-114">帯域外の (OOB) のデバッグ イベント時に、スレッドのコンテキストを変更する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="82f1a-114">You should never need to modify the context of a thread during an out-of-band (OOB) debug event.</span></span>  
  
 <span data-ttu-id="82f1a-115">渡されたデータは、現在のプラットフォームの context 構造体である必要があります。</span><span class="sxs-lookup"><span data-stu-id="82f1a-115">The data passed must be a context structure for the current platform.</span></span>  
  
 <span data-ttu-id="82f1a-116">このメソッドは、誤って使用すると、ランタイムを破壊できます。</span><span class="sxs-lookup"><span data-stu-id="82f1a-116">This method can corrupt the runtime if used improperly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="82f1a-117">必要条件</span><span class="sxs-lookup"><span data-stu-id="82f1a-117">Requirements</span></span>  
 <span data-ttu-id="82f1a-118">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="82f1a-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="82f1a-119">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="82f1a-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="82f1a-120">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="82f1a-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="82f1a-121">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="82f1a-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
