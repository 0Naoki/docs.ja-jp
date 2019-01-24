---
title: ICLRDataTarget2 インターフェイス
ms.date: 03/30/2017
api_name:
- ICLRDataTarget2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget2
helpviewer_keywords:
- ICLRDataTarget2 interface [.NET Framework debugging]
ms.assetid: 94249397-861b-4294-a538-cf01466a66d3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 45f16fd50880b5d2482be365f3c55e1427cc6eaa
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54701002"
---
# <a name="iclrdatatarget2-interface"></a><span data-ttu-id="8fc48-102">ICLRDataTarget2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8fc48-102">ICLRDataTarget2 Interface</span></span>
<span data-ttu-id="8fc48-103">サブクラス[ICLRDataTarget](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)ターゲット プロセス内の仮想メモリ領域を操作するデータ アクセス サービス層で使用されます。</span><span class="sxs-lookup"><span data-stu-id="8fc48-103">A subclass of [ICLRDataTarget](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md) that is used by the data access services layer to manipulate virtual memory regions in the target process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8fc48-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="8fc48-104">Methods</span></span>  
  
|<span data-ttu-id="8fc48-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="8fc48-105">Method</span></span>|<span data-ttu-id="8fc48-106">説明</span><span class="sxs-lookup"><span data-stu-id="8fc48-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8fc48-107">AllocVirtual メソッド</span><span class="sxs-lookup"><span data-stu-id="8fc48-107">AllocVirtual Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-allocvirtual-method.md)|<span data-ttu-id="8fc48-108">ターゲット プロセスのアドレス空間内のメモリを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="8fc48-108">Allocates memory in the address space of the target process.</span></span>|  
|[<span data-ttu-id="8fc48-109">FreeVirtual メソッド</span><span class="sxs-lookup"><span data-stu-id="8fc48-109">FreeVirtual Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-freevirtual-method.md)|<span data-ttu-id="8fc48-110">ターゲット プロセスのアドレス空間に割り当てられていたメモリを解放します。</span><span class="sxs-lookup"><span data-stu-id="8fc48-110">Frees memory that was previously allocated in the address space of the target process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8fc48-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="8fc48-111">Remarks</span></span>  
 <span data-ttu-id="8fc48-112">API クライアント (つまりデバッガー) は、特定のターゲット プロセスに応じてこのインターフェイスを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8fc48-112">The API client (that is, the debugger) must implement this interface as appropriate for the particular target process.</span></span> <span data-ttu-id="8fc48-113">たとえば、ライブ プロセスの実装は、メモリ ダンプの実装とは異なります。</span><span class="sxs-lookup"><span data-stu-id="8fc48-113">For example, a live process would have an implementation different from that of a memory dump.</span></span> <span data-ttu-id="8fc48-114">ターゲットは、メモリ領域の変更をサポートしない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8fc48-114">The target may not support modification of its memory regions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8fc48-115">必要条件</span><span class="sxs-lookup"><span data-stu-id="8fc48-115">Requirements</span></span>  
 <span data-ttu-id="8fc48-116">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8fc48-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8fc48-117">**ヘッダー:** ClrData.idl、ClrData.h</span><span class="sxs-lookup"><span data-stu-id="8fc48-117">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="8fc48-118">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8fc48-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8fc48-119">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8fc48-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8fc48-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="8fc48-120">See also</span></span>
- [<span data-ttu-id="8fc48-121">ICLRDataTarget インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8fc48-121">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
- [<span data-ttu-id="8fc48-122">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8fc48-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
