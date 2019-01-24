---
title: CorDebugExceptionObjectStackFrame 構造体
ms.date: 03/30/2017
api_name:
- CorDebugExceptionObjectStackFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugExceptionObjectStackFrame
helpviewer_keywords:
- CorDebugExceptionObjectStackFrame structure [.NET Framework debugging]
ms.assetid: 542cdd81-5ae7-4361-b0ef-1ae4775df258
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5e060fc62a93d98d8b86a244db1bc53a769cb31c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54717169"
---
# <a name="cordebugexceptionobjectstackframe-structure"></a><span data-ttu-id="600e9-102">CorDebugExceptionObjectStackFrame 構造体</span><span class="sxs-lookup"><span data-stu-id="600e9-102">CorDebugExceptionObjectStackFrame Structure</span></span>
<span data-ttu-id="600e9-103">例外オブジェクトのスタック フレームの情報を表しています。</span><span class="sxs-lookup"><span data-stu-id="600e9-103">Represents stack frame information from an exception object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="600e9-104">構文</span><span class="sxs-lookup"><span data-stu-id="600e9-104">Syntax</span></span>  
  
```  
typedef struct CorDebugExceptionObjectStackFrame {  
    ICorDebugModule* pModule;  
    CORDB_ADDRESS ip;  
    mdMethodDef methodDef;  
    BOOL isLastForeignExceptionFrame;  
} CorDebugExceptionObjectStackFrame;  
```  
  
## <a name="members"></a><span data-ttu-id="600e9-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="600e9-105">Members</span></span>  
  
|<span data-ttu-id="600e9-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="600e9-106">Member</span></span>|<span data-ttu-id="600e9-107">説明</span><span class="sxs-lookup"><span data-stu-id="600e9-107">Description</span></span>|  
|------------|-----------------|  
|`pModule`|<span data-ttu-id="600e9-108">現在のフレームの ICorDebugModule オブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="600e9-108">A pointer to the ICorDebugModule object for the current frame.</span></span>|  
|`ip`|<span data-ttu-id="600e9-109">現在のフレームの命令ポインター (EIP/RIP) の値。</span><span class="sxs-lookup"><span data-stu-id="600e9-109">The value of the instruction pointer (EIP/RIP) for the current frame.</span></span>|  
|`methodDef`|<span data-ttu-id="600e9-110">現在のフレーム メソッド トークンです。</span><span class="sxs-lookup"><span data-stu-id="600e9-110">The method token for the current frame.</span></span>|  
|`isLastForeignExceptionFrame`|<span data-ttu-id="600e9-111">フレームが外部例外の最後のフレームであるかどうかを示す値。</span><span class="sxs-lookup"><span data-stu-id="600e9-111">A value that indicates whether the frame is the last frame in a foreign exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="600e9-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="600e9-112">Remarks</span></span>  
 <span data-ttu-id="600e9-113">呼び出し元は、使用が ICorDebugModule オブジェクトへのポインターを解放する必要があります。</span><span class="sxs-lookup"><span data-stu-id="600e9-113">The caller must release the pointer to the ICorDebugModule object once it is no longer in use.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="600e9-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="600e9-114">Requirements</span></span>  
 <span data-ttu-id="600e9-115">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="600e9-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="600e9-116">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="600e9-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="600e9-117">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="600e9-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="600e9-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="600e9-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="600e9-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="600e9-119">See also</span></span>
- [<span data-ttu-id="600e9-120">デバッグ構造体</span><span class="sxs-lookup"><span data-stu-id="600e9-120">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="600e9-121">デバッグ</span><span class="sxs-lookup"><span data-stu-id="600e9-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
