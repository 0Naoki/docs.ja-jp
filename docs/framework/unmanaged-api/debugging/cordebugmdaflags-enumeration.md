---
title: CorDebugMDAFlags 列挙型
ms.date: 03/30/2017
api_name:
- CorDebugMDAFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugMDAFlags
helpviewer_keywords:
- CorDebugMDAFlags enumeration [.NET Framework debugging]
ms.assetid: 7c0c92fe-8bd2-477f-b307-aca0143732ca
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 732523935eec62bffbc15705bc93c97f14c90064
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59148422"
---
# <a name="cordebugmdaflags-enumeration"></a><span data-ttu-id="767b5-102">CorDebugMDAFlags 列挙型</span><span class="sxs-lookup"><span data-stu-id="767b5-102">CorDebugMDAFlags Enumeration</span></span>
<span data-ttu-id="767b5-103">マネージド デバッグ アシスタント (MDA) が生成されるスレッドのステータスを指定します。</span><span class="sxs-lookup"><span data-stu-id="767b5-103">Specifies the status of the thread on which the managed debugging assistant (MDA) is fired.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="767b5-104">構文</span><span class="sxs-lookup"><span data-stu-id="767b5-104">Syntax</span></span>  
  
```  
typedef enum CorDebugMDAFlags {  
    MDA_FLAG_SLIP = 0x2  
} CorDebugMDAFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="767b5-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="767b5-105">Members</span></span>  
  
|<span data-ttu-id="767b5-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="767b5-106">Member</span></span>|<span data-ttu-id="767b5-107">説明</span><span class="sxs-lookup"><span data-stu-id="767b5-107">Description</span></span>|  
|------------|-----------------|  
|`MDA_FLAG_SLIP`|<span data-ttu-id="767b5-108">MDA が起動されたので、MDA が起動されたスレッドが変更されました。</span><span class="sxs-lookup"><span data-stu-id="767b5-108">The thread on which the MDA was fired has slipped since the MDA was fired.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="767b5-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="767b5-109">Remarks</span></span>  
 <span data-ttu-id="767b5-110">呼び出し履歴では、この MDA が最初に発生した場所記述されていない、ときに、スレッドが持つと見なされます*スリップ*します。</span><span class="sxs-lookup"><span data-stu-id="767b5-110">When the call stack no longer describes where the MDA was originally raised, the thread is considered to have *slipped*.</span></span> <span data-ttu-id="767b5-111">これは、異常終了時に無効な操作のスレッドの実行によってもたらさです。</span><span class="sxs-lookup"><span data-stu-id="767b5-111">This is an unusual circumstance brought about by the thread's execution of an invalid operation upon exiting.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="767b5-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="767b5-112">Requirements</span></span>  
 <span data-ttu-id="767b5-113">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="767b5-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="767b5-114">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="767b5-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="767b5-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="767b5-115">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="767b5-116">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="767b5-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="767b5-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="767b5-117">See also</span></span>

- [<span data-ttu-id="767b5-118">列挙体のデバッグ</span><span class="sxs-lookup"><span data-stu-id="767b5-118">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
