---
title: ICLRSyncManager インターフェイス
ms.date: 03/30/2017
api_name:
- ICLRSyncManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRSyncManager
helpviewer_keywords:
- ICLRSyncManager interface [.NET Framework hosting]
ms.assetid: a49f9d80-1c76-4ddd-8c49-34f913a5c596
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ede896cdb93217fcfba9d66ed7102bcc1ba762e9
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2018
ms.locfileid: "53129325"
---
# <a name="iclrsyncmanager-interface"></a><span data-ttu-id="dd634-102">ICLRSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="dd634-102">ICLRSyncManager Interface</span></span>
<span data-ttu-id="dd634-103">要求されたタスクに関する情報を取得し、その同期実装でデッドロックを検出するためにホストできるようにするメソッドを定義します。</span><span class="sxs-lookup"><span data-stu-id="dd634-103">Defines methods that allow the host to get information about requested tasks and to detect deadlocks in its synchronization implementation.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="dd634-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="dd634-104">Methods</span></span>  
  
|<span data-ttu-id="dd634-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="dd634-105">Method</span></span>|<span data-ttu-id="dd634-106">説明</span><span class="sxs-lookup"><span data-stu-id="dd634-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="dd634-107">CreateRWLockOwnerIterator メソッド</span><span class="sxs-lookup"><span data-stu-id="dd634-107">CreateRWLockOwnerIterator Method</span></span>](iclrsyncmanager-createrwlockowneriterator-method.md)|<span data-ttu-id="dd634-108">共通言語ランタイム (CLR) を使用して、リーダー/ライター ロックで待機しているタスクのセットを決定するホストの反復子を作成するように要求します。</span><span class="sxs-lookup"><span data-stu-id="dd634-108">Requests that the common language runtime (CLR) create an iterator for the host to use to determine the set of tasks waiting on a reader-writer lock.</span></span>|  
|[<span data-ttu-id="dd634-109">DeleteRWLockOwnerIterator メソッド</span><span class="sxs-lookup"><span data-stu-id="dd634-109">DeleteRWLockOwnerIterator Method</span></span>](iclrsyncmanager-deleterwlockowneriterator-method.md)|<span data-ttu-id="dd634-110">要求に CLR への呼び出しによって作成された反復子の破棄`CreateRWLockOwnerIterator`します。</span><span class="sxs-lookup"><span data-stu-id="dd634-110">Requests that the CLR destroy an iterator that was created by a call to `CreateRWLockOwnerIterator`.</span></span>|  
|[<span data-ttu-id="dd634-111">GetMonitorOwner メソッド</span><span class="sxs-lookup"><span data-stu-id="dd634-111">GetMonitorOwner Method</span></span>](iclrsyncmanager-getmonitorowner-method.md)|<span data-ttu-id="dd634-112">指定したモニターを所有するタスクを取得します。</span><span class="sxs-lookup"><span data-stu-id="dd634-112">Gets the task that owns the specified monitor.</span></span>|  
|[<span data-ttu-id="dd634-113">GetRWLockOwnerNext メソッド</span><span class="sxs-lookup"><span data-stu-id="dd634-113">GetRWLockOwnerNext Method</span></span>](iclrsyncmanager-getrwlockownernext-method.md)|<span data-ttu-id="dd634-114">現在のリーダー/ライター ロックを待機している次のタスクを取得します。</span><span class="sxs-lookup"><span data-stu-id="dd634-114">Gets the next task that is waiting on the current reader-writer lock.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="dd634-115">必要条件</span><span class="sxs-lookup"><span data-stu-id="dd634-115">Requirements</span></span>  
 <span data-ttu-id="dd634-116">**プラットフォーム:**[システム要件](../../get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="dd634-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dd634-117">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="dd634-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="dd634-118">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="dd634-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="dd634-119">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dd634-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd634-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="dd634-120">See Also</span></span>  
 <xref:System.Threading.Thread>  
 [<span data-ttu-id="dd634-121">IHostSyncManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="dd634-121">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)  
 <span data-ttu-id="dd634-122">[マネージ コードとアンマネージ スレッド処理](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/5s8ee185(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="dd634-122">[Managed and Unmanaged Threading](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/5s8ee185(v=vs.100))</span></span>  
 [<span data-ttu-id="dd634-123">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="dd634-123">Hosting Interfaces</span></span>](hosting-interfaces.md)
