---
title: ETaskType 列挙型
ms.date: 03/30/2017
api_name:
- ETaskType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ETaskType
helpviewer_keywords:
- ETaskType enumeration [.NET Framework hosting]
ms.assetid: aa527b31-89d4-41f2-ad6f-63b76950b7df
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f256195a4cd5b18f568e05156db867aa5dba9161
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59229824"
---
# <a name="etasktype-enumeration"></a><span data-ttu-id="a2c57-102">ETaskType 列挙型</span><span class="sxs-lookup"><span data-stu-id="a2c57-102">ETaskType Enumeration</span></span>
<span data-ttu-id="a2c57-103">いずれかで表されるタスクの種類を示す値を含む、 [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)または[IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="a2c57-103">Contains values that indicate the type of task that is represented by either an [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) or an [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a2c57-104">構文</span><span class="sxs-lookup"><span data-stu-id="a2c57-104">Syntax</span></span>  
  
```  
typedef enum ETaskType {  
    TT_DEBUGGERHELPER           = 0x1,  
    TT_GC                       = 0x2,  
    TT_FINALIZER                = 0x4,  
    TT_THREADPOOL_TIMER         = 0x8,  
    TT_THREADPOOL_GATE          = 0x10,  
    TT_THREADPOOL_WORKER        = 0x20,  
    TT_THREADPOOL_IOCOMPLETION  = 0x40,  
    TT_ADUNLOAD                 = 0x80,  
    TT_USER                     = 0x100,  
    TT_THREADPOOL_WAIT          = 0x200,  
    TT_UNKNOWN                  = 0x80000000  
} ETaskType;  
```  
  
## <a name="members"></a><span data-ttu-id="a2c57-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="a2c57-105">Members</span></span>  
  
|<span data-ttu-id="a2c57-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="a2c57-106">Member</span></span>|<span data-ttu-id="a2c57-107">説明</span><span class="sxs-lookup"><span data-stu-id="a2c57-107">Description</span></span>|  
|------------|-----------------|  
|`TT_ADUNLOAD`|<span data-ttu-id="a2c57-108">このインターフェイスは、アプリケーション ドメインのアンロード タスクを表します。</span><span class="sxs-lookup"><span data-stu-id="a2c57-108">The interface represents an application domain unloading task.</span></span>|  
|`TT_DEBUGGERHELPER`|<span data-ttu-id="a2c57-109">このインターフェイスは、デバッガー ヘルパーのタスクを表します。</span><span class="sxs-lookup"><span data-stu-id="a2c57-109">The interface represents a debugger helper task.</span></span>|  
|`TT_FINALIZER`|<span data-ttu-id="a2c57-110">このインターフェイスは、ファイナライザーのタスクを表します。</span><span class="sxs-lookup"><span data-stu-id="a2c57-110">The interface represents a finalizer task.</span></span>|  
|`TT_GC`|<span data-ttu-id="a2c57-111">このインターフェイスは、ガベージ コレクションのタスクを表します。</span><span class="sxs-lookup"><span data-stu-id="a2c57-111">The interface represents a garbage collection task.</span></span>|  
|`TT_THREADPOOL_GATE`|<span data-ttu-id="a2c57-112">このインターフェイスは、ゲートのスレッドのタスクを表します。</span><span class="sxs-lookup"><span data-stu-id="a2c57-112">The interface represents a gate thread task.</span></span>|  
|`TT_THREADPOOL_IOCOMPLETION`|<span data-ttu-id="a2c57-113">このインターフェイスは、I/O スレッドのタスクまたはタスクの完了ポート スレッドを表します。</span><span class="sxs-lookup"><span data-stu-id="a2c57-113">The interface represents an I/O thread task or a completion port thread task.</span></span>|  
|`TT_THREADPOOL_TIMER`|<span data-ttu-id="a2c57-114">このインターフェイスは、タイマー スレッドのタスクを表します。</span><span class="sxs-lookup"><span data-stu-id="a2c57-114">The interface represents a timer thread task.</span></span>|  
|`TT_THREADPOOL_WAIT`|<span data-ttu-id="a2c57-115">このインターフェイスは、待機スレッドのタスクを表します。</span><span class="sxs-lookup"><span data-stu-id="a2c57-115">The interface represents a wait thread task.</span></span>|  
|`TT_THREADPOOL_WORKER`|<span data-ttu-id="a2c57-116">このインターフェイスは、ワーカー スレッドのタスクを表します。</span><span class="sxs-lookup"><span data-stu-id="a2c57-116">The interface represents a worker thread task.</span></span>|  
|`TT_UNKNOWN`|<span data-ttu-id="a2c57-117">タスクが不明です。</span><span class="sxs-lookup"><span data-stu-id="a2c57-117">The task is unknown.</span></span>|  
|`TT_USER`|<span data-ttu-id="a2c57-118">このインターフェイスは、ユーザーのタスクを表します。</span><span class="sxs-lookup"><span data-stu-id="a2c57-118">The interface represents a user task.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a2c57-119">必要条件</span><span class="sxs-lookup"><span data-stu-id="a2c57-119">Requirements</span></span>  
 <span data-ttu-id="a2c57-120">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a2c57-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a2c57-121">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a2c57-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a2c57-122">**ライブラリ:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a2c57-122">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a2c57-123">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a2c57-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2c57-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="a2c57-124">See also</span></span>

- [<span data-ttu-id="a2c57-125">ホスティングの列挙型</span><span class="sxs-lookup"><span data-stu-id="a2c57-125">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
