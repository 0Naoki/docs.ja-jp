---
title: ICorDebugUnmanagedCallback インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugUnmanagedCallback
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugUnmanagedCallback
helpviewer_keywords:
- ICorDebugUnmanagedCallback interface [.NET Framework debugging]
ms.assetid: bc71cbca-7d73-40e5-84dd-2109fade3c2a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fd61c8133d9f155ae8e15bbc6aa90b2b9de1aadd
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54647670"
---
# <a name="icordebugunmanagedcallback-interface"></a><span data-ttu-id="f6391-102">ICorDebugUnmanagedCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f6391-102">ICorDebugUnmanagedCallback Interface</span></span>
<span data-ttu-id="f6391-103">共通言語ランタイム (CLR) に直接関連していないネイティブ イベントについて通知を提供します。</span><span class="sxs-lookup"><span data-stu-id="f6391-103">Provides notification of native events that are not directly related to the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f6391-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="f6391-104">Methods</span></span>  
  
|<span data-ttu-id="f6391-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="f6391-105">Method</span></span>|<span data-ttu-id="f6391-106">説明</span><span class="sxs-lookup"><span data-stu-id="f6391-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f6391-107">DebugEvent メソッド</span><span class="sxs-lookup"><span data-stu-id="f6391-107">DebugEvent Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-debugevent-method.md)|<span data-ttu-id="f6391-108">ネイティブ イベントが発生したことをデバッガーに通知します。</span><span class="sxs-lookup"><span data-stu-id="f6391-108">Notifies the debugger that a native event has been fired.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f6391-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="f6391-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f6391-110">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="f6391-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f6391-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="f6391-111">Requirements</span></span>  
 <span data-ttu-id="f6391-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f6391-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f6391-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f6391-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f6391-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f6391-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f6391-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f6391-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6391-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="f6391-116">See also</span></span>
- [<span data-ttu-id="f6391-117">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f6391-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
