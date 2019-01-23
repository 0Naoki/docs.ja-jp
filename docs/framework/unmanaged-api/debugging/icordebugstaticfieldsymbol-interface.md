---
title: ICorDebugStaticFieldSymbol インターフェイス
ms.date: 03/30/2017
ms.assetid: c0b93609-631e-4b15-878a-189ede922631
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0415e622ebba76d0af7d58fc3b59c4bdb47e0043
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54619890"
---
# <a name="icordebugstaticfieldsymbol-interface"></a><span data-ttu-id="c9618-102">ICorDebugStaticFieldSymbol インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c9618-102">ICorDebugStaticFieldSymbol Interface</span></span>
<span data-ttu-id="c9618-103">静的フィールドのデバッグ シンボル情報を表します。</span><span class="sxs-lookup"><span data-stu-id="c9618-103">Represents the debug symbol information for a static field.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c9618-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="c9618-104">Methods</span></span>  
  
|<span data-ttu-id="c9618-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="c9618-105">Method</span></span>|<span data-ttu-id="c9618-106">説明</span><span class="sxs-lookup"><span data-stu-id="c9618-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c9618-107">GetAddress メソッド</span><span class="sxs-lookup"><span data-stu-id="c9618-107">GetAddress Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-getaddress-method.md)|<span data-ttu-id="c9618-108">静的フィールドのアドレスを取得します。</span><span class="sxs-lookup"><span data-stu-id="c9618-108">Gets the address of the static field.</span></span>|  
|[<span data-ttu-id="c9618-109">GetName メソッド</span><span class="sxs-lookup"><span data-stu-id="c9618-109">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-getname-method.md)|<span data-ttu-id="c9618-110">静的フィールドの名前を取得します。</span><span class="sxs-lookup"><span data-stu-id="c9618-110">Gets the name of the static field.</span></span>|  
|[<span data-ttu-id="c9618-111">GetSize メソッド</span><span class="sxs-lookup"><span data-stu-id="c9618-111">GetSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-getsize-method.md)|<span data-ttu-id="c9618-112">静的フィールドのサイズ (バイト単位) を取得します。</span><span class="sxs-lookup"><span data-stu-id="c9618-112">Gets the size in bytes of the static field.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c9618-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="c9618-113">Remarks</span></span>  
 <span data-ttu-id="c9618-114">`ICorDebugStaticFieldSymbol` インターフェイスは、静的フィールドのデバッグ シンボル情報を取得するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="c9618-114">The `ICorDebugStaticFieldSymbol` interface is used to retrieve the debug symbol information for a static field.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c9618-115">このインターフェイスは .NET ネイティブでのみ使用可能です。</span><span class="sxs-lookup"><span data-stu-id="c9618-115">This interface is available with .NET Native only.</span></span> <span data-ttu-id="c9618-116">.NET ネイティブの外部で ICorDebug シナリオについてこのインターフェイスを実装する場合は、共通言語ランタイムはこのインターフェイスを無視します。</span><span class="sxs-lookup"><span data-stu-id="c9618-116">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c9618-117">必要条件</span><span class="sxs-lookup"><span data-stu-id="c9618-117">Requirements</span></span>  
 <span data-ttu-id="c9618-118">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c9618-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c9618-119">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c9618-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c9618-120">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c9618-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c9618-121">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c9618-121">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9618-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="c9618-122">See also</span></span>
- [<span data-ttu-id="c9618-123">ICorDebugInstanceFieldSymbol インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c9618-123">ICorDebugInstanceFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-interface.md)
- [<span data-ttu-id="c9618-124">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c9618-124">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="c9618-125">デバッグ</span><span class="sxs-lookup"><span data-stu-id="c9618-125">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
