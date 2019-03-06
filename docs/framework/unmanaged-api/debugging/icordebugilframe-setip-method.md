---
title: ICorDebugILFrame::SetIP メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame.SetIP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame::SetIP
helpviewer_keywords:
- SetIP method, ICorDebugILFrame interface [.NET Framework debugging]
- ICorDebugILFrame::SetIP method [.NET Framework debugging]
ms.assetid: 23f38dc1-85e4-4263-9235-2d05bbb6a833
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a25e52c6b858aaa602ffade0e407b1aaf6e5c67e
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57471395"
---
# <a name="icordebugilframesetip-method"></a><span data-ttu-id="4a714-102">ICorDebugILFrame::SetIP メソッド</span><span class="sxs-lookup"><span data-stu-id="4a714-102">ICorDebugILFrame::SetIP Method</span></span>
<span data-ttu-id="4a714-103">命令ポインターを Microsoft intermediate language (MSIL) コードで指定されたオフセット位置に設定します。</span><span class="sxs-lookup"><span data-stu-id="4a714-103">Sets the instruction pointer to the specified offset location in the Microsoft intermediate language (MSIL) code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a714-104">構文</span><span class="sxs-lookup"><span data-stu-id="4a714-104">Syntax</span></span>  
  
```  
HRESULT SetIP (  
    [in] ULONG32 nOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4a714-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="4a714-105">Parameters</span></span>  
 `nOffset`  
 <span data-ttu-id="4a714-106">MSIL コード内のオフセット位置。</span><span class="sxs-lookup"><span data-stu-id="4a714-106">The offset location in the MSIL code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4a714-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="4a714-107">Remarks</span></span>  
 <span data-ttu-id="4a714-108">呼び出す`SetIP`すぐにすべてのフレームと現在のスレッドのチェーンが無効にします。</span><span class="sxs-lookup"><span data-stu-id="4a714-108">Calls to `SetIP` immediately invalidate all frames and chains for the current thread.</span></span> <span data-ttu-id="4a714-109">デバッガーには、呼び出しの後にフレーム情報が必要がある場合`SetIP`、新しいスタック トレースを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4a714-109">If the debugger needs frame information after a call to `SetIP`, it must perform a new stack trace.</span></span>  
  
 <span data-ttu-id="4a714-110">[ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)有効な状態でスタック フレームを保持します。</span><span class="sxs-lookup"><span data-stu-id="4a714-110">[ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) will attempt to keep the stack frame in a valid state.</span></span> <span data-ttu-id="4a714-111">ただし、場合でも、フレームは、有効な状態では、まだある可能性があります初期化されていないローカル変数などの問題。</span><span class="sxs-lookup"><span data-stu-id="4a714-111">However, even if the frame is in a valid state, there still may be problems such as uninitialized local variables.</span></span> <span data-ttu-id="4a714-112">呼び出し元は、実行中のプログラムの一貫性を保証します。</span><span class="sxs-lookup"><span data-stu-id="4a714-112">The caller is responsible for ensuring the coherency of the running program.</span></span>  
  
 <span data-ttu-id="4a714-113">64 ビットのプラットフォームでのうち、命令ポインターを移動できません、`catch`または`finally`ブロックします。</span><span class="sxs-lookup"><span data-stu-id="4a714-113">On 64-bit platforms, the instruction pointer cannot be moved out of a `catch` or `finally` block.</span></span> <span data-ttu-id="4a714-114">場合`SetIP`というはエラーを示す HRESULT を返す、64 ビット プラットフォームで、このような移動するために、します。</span><span class="sxs-lookup"><span data-stu-id="4a714-114">If `SetIP` is called to make such a move on a 64-bit platform, it will return an HRESULT indicating failure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4a714-115">必要条件</span><span class="sxs-lookup"><span data-stu-id="4a714-115">Requirements</span></span>  
 <span data-ttu-id="4a714-116">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4a714-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4a714-117">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4a714-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4a714-118">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4a714-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4a714-119">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4a714-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
