---
title: ICorDebugHeapSegmentEnum インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugHealRegionEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapSegmentEnum
helpviewer_keywords:
- ICorDebugHeapSegmentEnum interface [.NET Framework debugging]
ms.assetid: 20fc1b9d-e228-4107-bd76-53934c1724b9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6e5c29952fd300da1d7fb6b87a3287b34e76f863
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54716249"
---
# <a name="icordebugheapsegmentenum-interface"></a><span data-ttu-id="23a08-102">ICorDebugHeapSegmentEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="23a08-102">ICorDebugHeapSegmentEnum Interface</span></span>
<span data-ttu-id="23a08-103">マネージド ヒープのメモリ領域の列挙子を提供します。</span><span class="sxs-lookup"><span data-stu-id="23a08-103">Provides an enumerator for the memory regions of the managed heap.</span></span> <span data-ttu-id="23a08-104">このインターフェイスは、ICorDebugEnum インターフェイスのサブクラスです。</span><span class="sxs-lookup"><span data-stu-id="23a08-104">This interface is a subclass of the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="23a08-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="23a08-105">Methods</span></span>  
  
|<span data-ttu-id="23a08-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="23a08-106">Method</span></span>|<span data-ttu-id="23a08-107">説明</span><span class="sxs-lookup"><span data-stu-id="23a08-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="23a08-108">Next メソッド</span><span class="sxs-lookup"><span data-stu-id="23a08-108">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-next-method.md)|<span data-ttu-id="23a08-109">指定した数を取得[COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md)マネージ ヒープの領域に関する情報が含まれているインスタンス。</span><span class="sxs-lookup"><span data-stu-id="23a08-109">Gets the specified number of [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) instances that contain information about regions of the managed heap.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="23a08-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="23a08-110">Remarks</span></span>  
 <span data-ttu-id="23a08-111">`ICorDebugHeapSegmentEnum` ICorDebugEnum インターフェイスを実装するインターフェイス。</span><span class="sxs-lookup"><span data-stu-id="23a08-111">The `ICorDebugHeapSegmentEnum` interface implements the ICorDebugEnum interface.</span></span>  
  
 <span data-ttu-id="23a08-112">`ICorDebugHeapSegmentEnum`インスタンスには、 [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md)インスタンスを呼び出すことによって、 [icordebugprocess 5::enumerateheapregions](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheapregions-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="23a08-112">An `ICorDebugHeapSegmentEnum` instance is populated with [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) instances by calling the [ICorDebugProcess5::EnumerateHeapRegions](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheapregions-method.md) method.</span></span> <span data-ttu-id="23a08-113">[COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md)呼び出すことによって、コレクション内のオブジェクトを列挙することができます、 [icordebugheapsegmentenum::next](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-next-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="23a08-113">The [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) objects in the collection can be enumerated by calling the [ICorDebugHeapSegmentEnum::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-next-method.md) method.</span></span>  
  
 <span data-ttu-id="23a08-114">`ICorDebugHeapSegmentEnum`コレクション オブジェクトがマネージ オブジェクトを含む可能性のあるすべてのメモリ領域を列挙しますが、管理対象のオブジェクトが実際にそれらのリージョン内にあることは保証されません。</span><span class="sxs-lookup"><span data-stu-id="23a08-114">An `ICorDebugHeapSegmentEnum` collection object enumerates all memory regions that may contain managed objects, but it does not guarantee that managed objects actually reside in those regions.</span></span> <span data-ttu-id="23a08-115">これには、空または予約済みのメモリ領域に関する情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="23a08-115">It may include information about empty or reserved memory regions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="23a08-116">必要条件</span><span class="sxs-lookup"><span data-stu-id="23a08-116">Requirements</span></span>  
 <span data-ttu-id="23a08-117">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="23a08-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="23a08-118">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="23a08-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="23a08-119">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="23a08-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="23a08-120">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="23a08-120">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23a08-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="23a08-121">See also</span></span>
- [<span data-ttu-id="23a08-122">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="23a08-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
