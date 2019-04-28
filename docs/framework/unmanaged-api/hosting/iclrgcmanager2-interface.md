---
title: ICLRGCManager2 インターフェイス
ms.date: 03/30/2017
api_name:
- ICLRGCManager2
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRGCManager2
helpviewer_keywords:
- ICLRGCManager2 interface [.NET Framework hosting]
ms.assetid: 4b5ffd7b-9ad7-41cd-9bba-34030ae3da7e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a89a7ef34418163d790fd055de681c1cdf989e57
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61700430"
---
# <a name="iclrgcmanager2-interface"></a><span data-ttu-id="9cc20-102">ICLRGCManager2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9cc20-102">ICLRGCManager2 Interface</span></span>
<span data-ttu-id="9cc20-103">ホストが共通言語ランタイムのガベージ コレクション システムと対話できるようにするメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="9cc20-103">Provides methods that allow a host to interact with the common language runtime's garbage collection system.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9cc20-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="9cc20-104">Methods</span></span>  
  
|<span data-ttu-id="9cc20-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="9cc20-105">Method</span></span>|<span data-ttu-id="9cc20-106">説明</span><span class="sxs-lookup"><span data-stu-id="9cc20-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9cc20-107">SetGCStartupLimitsEx メソッド</span><span class="sxs-lookup"><span data-stu-id="9cc20-107">SetGCStartupLimitsEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md)|<span data-ttu-id="9cc20-108">ガベージ コレクション セグメントのサイズと、ガベージ コレクション システムのジェネレーション 0 の最大サイズを設定します。</span><span class="sxs-lookup"><span data-stu-id="9cc20-108">Sets the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0.</span></span> <span data-ttu-id="9cc20-109">により、ジェネレーション 0 およびセグメントのサイズを超える`DWORD`します。</span><span class="sxs-lookup"><span data-stu-id="9cc20-109">Enables generation 0 and segment sizes larger than `DWORD`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9cc20-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="9cc20-110">Remarks</span></span>  
 <span data-ttu-id="9cc20-111">このインターフェイスから継承、 [ICLRGCManager インターフェイス](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md)します。</span><span class="sxs-lookup"><span data-stu-id="9cc20-111">This interface inherits from the [ICLRGCManager Interface](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md).</span></span>  
  
 <span data-ttu-id="9cc20-112">共通言語ランタイム (CLR) で、管理対象のガベージ コレクションのメカニズムを実装する<xref:System.GC>型。</span><span class="sxs-lookup"><span data-stu-id="9cc20-112">The common language runtime (CLR) implements its garbage collection mechanism with the managed <xref:System.GC> type.</span></span> <span data-ttu-id="9cc20-113">ガベージ コレクションのシステムの詳細については、次を参照してください。[ガベージ コレクション](../../../../docs/standard/garbage-collection/index.md)します。</span><span class="sxs-lookup"><span data-stu-id="9cc20-113">For more information about the garbage collection system, see [Garbage Collection](../../../../docs/standard/garbage-collection/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9cc20-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="9cc20-114">Requirements</span></span>  
 <span data-ttu-id="9cc20-115">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9cc20-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9cc20-116">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="9cc20-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9cc20-117">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="9cc20-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9cc20-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9cc20-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9cc20-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="9cc20-119">See also</span></span>

- [<span data-ttu-id="9cc20-120">自動メモリ管理</span><span class="sxs-lookup"><span data-stu-id="9cc20-120">Automatic Memory Management</span></span>](../../../../docs/standard/automatic-memory-management.md)
- [<span data-ttu-id="9cc20-121">COR_GC_STATS 構造体</span><span class="sxs-lookup"><span data-stu-id="9cc20-121">COR_GC_STATS Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)
- [<span data-ttu-id="9cc20-122">ICLRControl インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9cc20-122">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="9cc20-123">.NET Framework 4 および 4.5 で追加された CLR ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9cc20-123">CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)
- [<span data-ttu-id="9cc20-124">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9cc20-124">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="9cc20-125">ホスティング</span><span class="sxs-lookup"><span data-stu-id="9cc20-125">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
