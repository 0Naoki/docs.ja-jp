---
title: ICorDebugModuleDebugEvent インターフェイス
ms.date: 03/30/2017
ms.assetid: 41950c52-1ac8-4212-b814-c77e20879f91
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 399f27db0a2d18e3bcd90b87f4470a77cb50595d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54646858"
---
# <a name="icordebugmoduledebugevent-interface"></a><span data-ttu-id="9a559-102">ICorDebugModuleDebugEvent インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9a559-102">ICorDebugModuleDebugEvent Interface</span></span>
<span data-ttu-id="9a559-103">拡張、 [ICorDebugDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md)モジュール レベルのイベントをサポートするインターフェイス。</span><span class="sxs-lookup"><span data-stu-id="9a559-103">Extends the [ICorDebugDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md) interface to support module-level events.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9a559-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="9a559-104">Methods</span></span>  
  
|<span data-ttu-id="9a559-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="9a559-105">Method</span></span>|<span data-ttu-id="9a559-106">説明</span><span class="sxs-lookup"><span data-stu-id="9a559-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9a559-107">GetModule メソッド</span><span class="sxs-lookup"><span data-stu-id="9a559-107">GetModule Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmoduledebugevent-getmodule-method.md)|<span data-ttu-id="9a559-108">ロードまたはアンロードされたばかりのマージ モジュールを取得します。</span><span class="sxs-lookup"><span data-stu-id="9a559-108">Gets the merged module that was just loaded or unloaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9a559-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="9a559-109">Remarks</span></span>  
 <span data-ttu-id="9a559-110">[MODULE_LOADED](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md)と[MODULE_UNLOADED](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md)イベントの種類は、このインターフェイスを実装します。</span><span class="sxs-lookup"><span data-stu-id="9a559-110">The [MODULE_LOADED](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md) and [MODULE_UNLOADED](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md) event types implement this interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9a559-111">このインターフェイスは .NET ネイティブでのみ使用可能です。</span><span class="sxs-lookup"><span data-stu-id="9a559-111">The interface is available with .NET Native only.</span></span> <span data-ttu-id="9a559-112">インターフェイス ポインターを取得するために `QueryInterface` を呼び出そうとすると、.NET ネイティブ外の ICorDebug シナリオに対して `E_NOINTERFACE` が返されます。</span><span class="sxs-lookup"><span data-stu-id="9a559-112">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9a559-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="9a559-113">Requirements</span></span>  
 <span data-ttu-id="9a559-114">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9a559-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9a559-115">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9a559-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9a559-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9a559-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9a559-117">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9a559-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a559-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="9a559-118">See also</span></span>
- [<span data-ttu-id="9a559-119">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9a559-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="9a559-120">デバッグ</span><span class="sxs-lookup"><span data-stu-id="9a559-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
