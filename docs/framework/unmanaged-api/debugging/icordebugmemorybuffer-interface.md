---
title: ICorDebugMemoryBuffer インターフェイス
ms.date: 03/30/2017
ms.assetid: 85dc2d65-3657-4b93-9f23-9feaa95d37ff
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 77fa6b1a8c7a559b9d88c0173e389ec11a75ec8b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69914787"
---
# <a name="icordebugmemorybuffer-interface"></a><span data-ttu-id="991d5-102">ICorDebugMemoryBuffer インターフェイス</span><span class="sxs-lookup"><span data-stu-id="991d5-102">ICorDebugMemoryBuffer Interface</span></span>
<span data-ttu-id="991d5-103">メモリ内のバッファーを表します。</span><span class="sxs-lookup"><span data-stu-id="991d5-103">Represents an in-memory buffer.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="991d5-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="991d5-104">Methods</span></span>  
  
|<span data-ttu-id="991d5-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="991d5-105">Method</span></span>|<span data-ttu-id="991d5-106">説明</span><span class="sxs-lookup"><span data-stu-id="991d5-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="991d5-107">GetSize メソッド</span><span class="sxs-lookup"><span data-stu-id="991d5-107">GetSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-getsize-method.md)|<span data-ttu-id="991d5-108">メモリ バッファーのサイズ (バイト単位) を取得します。</span><span class="sxs-lookup"><span data-stu-id="991d5-108">Gets the size of the memory buffer in bytes.</span></span>|  
|[<span data-ttu-id="991d5-109">GetStartAddress メソッド</span><span class="sxs-lookup"><span data-stu-id="991d5-109">GetStartAddress Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-getstartaddress-method.md)|<span data-ttu-id="991d5-110">メモリ バッファーの開始アドレスを取得します。</span><span class="sxs-lookup"><span data-stu-id="991d5-110">Gets the starting address of the memory buffer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="991d5-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="991d5-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="991d5-112">このインターフェイスは .NET ネイティブでのみ使用可能です。</span><span class="sxs-lookup"><span data-stu-id="991d5-112">This interface is available with .NET Native only.</span></span> <span data-ttu-id="991d5-113">.NET ネイティブの外部で ICorDebug シナリオについてこのインターフェイスを実装する場合は、共通言語ランタイムはこのインターフェイスを無視します。</span><span class="sxs-lookup"><span data-stu-id="991d5-113">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="991d5-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="991d5-114">Requirements</span></span>  
 <span data-ttu-id="991d5-115">**・** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="991d5-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="991d5-116">**ヘッダー:** CorDebug .idl、CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="991d5-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="991d5-117">**ライブラリ**CorGuids .lib</span><span class="sxs-lookup"><span data-stu-id="991d5-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="991d5-118">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="991d5-118">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="991d5-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="991d5-119">See also</span></span>

- [<span data-ttu-id="991d5-120">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="991d5-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="991d5-121">デバッグ</span><span class="sxs-lookup"><span data-stu-id="991d5-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
