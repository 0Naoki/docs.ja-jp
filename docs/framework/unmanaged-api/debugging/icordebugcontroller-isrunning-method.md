---
title: ICorDebugController::IsRunning メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugController.IsRunning
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::IsRunning
helpviewer_keywords:
- IsRunning method [.NET Framework debugging]
- ICorDebugController::IsRunning method [.NET Framework debugging]
ms.assetid: b33ff059-40c4-4dfe-9cb2-21bfed2de0b0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a5eae9e14bcd0ca430f03a873818246896438463
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59227094"
---
# <a name="icordebugcontrollerisrunning-method"></a><span data-ttu-id="5cff6-102">ICorDebugController::IsRunning メソッド</span><span class="sxs-lookup"><span data-stu-id="5cff6-102">ICorDebugController::IsRunning Method</span></span>
<span data-ttu-id="5cff6-103">プロセスのスレッドが自由に実行して現在かどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="5cff6-103">Gets a value that indicates whether the threads in the process are currently running freely.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5cff6-104">構文</span><span class="sxs-lookup"><span data-stu-id="5cff6-104">Syntax</span></span>  
  
```  
HRESULT IsRunning (  
    [out] BOOL *pbRunning  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5cff6-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5cff6-105">Parameters</span></span>  
 `pbRunning`  
 <span data-ttu-id="5cff6-106">[out]ある値へのポインター`true`自由に。 そうしないと、プロセスのスレッドを実行している場合`false`します。</span><span class="sxs-lookup"><span data-stu-id="5cff6-106">[out] A pointer to a value that is `true` if the threads in the process are running freely; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5cff6-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="5cff6-107">Requirements</span></span>  
 <span data-ttu-id="5cff6-108">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5cff6-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5cff6-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5cff6-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5cff6-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5cff6-110">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="5cff6-111">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="5cff6-111">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="5cff6-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="5cff6-112">See also</span></span>
