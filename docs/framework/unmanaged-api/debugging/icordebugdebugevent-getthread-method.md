---
title: ICorDebugDebugEvent::GetThread メソッド
ms.date: 03/30/2017
ms.assetid: 4f2e9a2c-8369-4a07-a881-ad5422626353
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 403caa136f85904937bd5077a618e5aed788c86a
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57472305"
---
# <a name="icordebugdebugeventgetthread-method"></a><span data-ttu-id="baed2-102">ICorDebugDebugEvent::GetThread メソッド</span><span class="sxs-lookup"><span data-stu-id="baed2-102">ICorDebugDebugEvent::GetThread Method</span></span>
<span data-ttu-id="baed2-103">イベントが発生したスレッドを取得します。</span><span class="sxs-lookup"><span data-stu-id="baed2-103">Gets the thread on which the event occurred.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="baed2-104">構文</span><span class="sxs-lookup"><span data-stu-id="baed2-104">Syntax</span></span>  
  
```  
HRESULT GetThread(  
        [out]ICorDebugThread **ppThread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="baed2-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="baed2-105">Parameters</span></span>  
 <span data-ttu-id="baed2-106">ppThread</span><span class="sxs-lookup"><span data-stu-id="baed2-106">ppThread</span></span>  
 <span data-ttu-id="baed2-107">[out]イベントが発生したスレッドを表す ICorDebugThread オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="baed2-107">[out] A pointer to the address of an ICorDebugThread object that represents the thread on which the event occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="baed2-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="baed2-108">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="baed2-109">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="baed2-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="baed2-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="baed2-110">Requirements</span></span>  
 <span data-ttu-id="baed2-111">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="baed2-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="baed2-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="baed2-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="baed2-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="baed2-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="baed2-114">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="baed2-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="baed2-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="baed2-115">See also</span></span>
- [<span data-ttu-id="baed2-116">ICorDebugDebugEvent インターフェイス</span><span class="sxs-lookup"><span data-stu-id="baed2-116">ICorDebugDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md)
- [<span data-ttu-id="baed2-117">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="baed2-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
