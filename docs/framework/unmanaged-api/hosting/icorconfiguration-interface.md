---
title: ICorConfiguration インターフェイス
ms.date: 03/30/2017
api_name:
- ICorConfiguration
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorConfiguration
helpviewer_keywords:
- ICorConfiguration interface [.NET Framework hosting]
ms.assetid: aaf96116-372b-4538-afb1-9e0fcdac1f98
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b24e278b3449d0e17377495cef0f445c1ebed734
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59149813"
---
# <a name="icorconfiguration-interface"></a><span data-ttu-id="2a80d-102">ICorConfiguration インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2a80d-102">ICorConfiguration Interface</span></span>
<span data-ttu-id="2a80d-103">共通言語ランタイム (CLR) を構成するためのメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="2a80d-103">Provides methods for configuring the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2a80d-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="2a80d-104">Methods</span></span>  
  
|<span data-ttu-id="2a80d-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="2a80d-105">Method</span></span>|<span data-ttu-id="2a80d-106">説明</span><span class="sxs-lookup"><span data-stu-id="2a80d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2a80d-107">AddDebuggerSpecialThread メソッド</span><span class="sxs-lookup"><span data-stu-id="2a80d-107">AddDebuggerSpecialThread Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-adddebuggerspecialthread-method.md)|<span data-ttu-id="2a80d-108">デバッグ サービスを特定のスレッドがデバッガーがマネージまたはアンマネージ デバッグ シナリオ中に停止したアプリケーションの実行を続行できることを示します。</span><span class="sxs-lookup"><span data-stu-id="2a80d-108">Indicates to the debugging services that a particular thread should be allowed to continue executing while the debugger has an application stopped during managed or unmanaged debugging scenarios.</span></span>|  
|[<span data-ttu-id="2a80d-109">SetDebuggerThreadControl メソッド</span><span class="sxs-lookup"><span data-stu-id="2a80d-109">SetDebuggerThreadControl Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-setdebuggerthreadcontrol-method.md)|<span data-ttu-id="2a80d-110">デバッグ サービスは CLR のスレッドをブロックまたはブロック解除されたデバッグときに呼び出すコールバック インターフェイスを設定します。</span><span class="sxs-lookup"><span data-stu-id="2a80d-110">Sets the callback interface that the debugging services will call as CLR threads are blocked and unblocked for debugging.</span></span>|  
|[<span data-ttu-id="2a80d-111">SetGCHostControl メソッド</span><span class="sxs-lookup"><span data-stu-id="2a80d-111">SetGCHostControl Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-setgchostcontrol-method.md)|<span data-ttu-id="2a80d-112">仮想メモリの制限を変更するホストに要求、ガベージ コレクターで使用されるコールバック インターフェイスを設定します。</span><span class="sxs-lookup"><span data-stu-id="2a80d-112">Sets the callback interface to be used by the garbage collector to request the host to change the limits of virtual memory.</span></span>|  
|[<span data-ttu-id="2a80d-113">SetGCThreadControl メソッド</span><span class="sxs-lookup"><span data-stu-id="2a80d-113">SetGCThreadControl Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-setgcthreadcontrol-method.md)|<span data-ttu-id="2a80d-114">それ以外の場合、ガベージ コレクションのブロックされる非ランタイム タスクのスレッドをスケジュールするためのコールバック インターフェイスを設定します。</span><span class="sxs-lookup"><span data-stu-id="2a80d-114">Sets the callback interface for scheduling threads for non-runtime tasks that would otherwise be blocked for a garbage collection.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2a80d-115">必要条件</span><span class="sxs-lookup"><span data-stu-id="2a80d-115">Requirements</span></span>  
 <span data-ttu-id="2a80d-116">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2a80d-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2a80d-117">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2a80d-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2a80d-118">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="2a80d-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2a80d-119">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2a80d-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a80d-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="2a80d-120">See also</span></span>

- [<span data-ttu-id="2a80d-121">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2a80d-121">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="2a80d-122">CorRuntimeHost コクラス</span><span class="sxs-lookup"><span data-stu-id="2a80d-122">CorRuntimeHost Coclass</span></span>](../../../../docs/framework/unmanaged-api/hosting/corruntimehost-coclass.md)
