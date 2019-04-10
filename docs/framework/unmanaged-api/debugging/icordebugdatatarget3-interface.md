---
title: ICorDebugDataTarget3 インターフェイス
ms.date: 03/30/2017
ms.assetid: f477af85-994f-4df0-ae78-404ed252bf49
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c3b0d67d390931cc92c0b6a1320f66545517cde3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59223044"
---
# <a name="icordebugdatatarget3-interface"></a><span data-ttu-id="a81ba-102">ICorDebugDataTarget3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a81ba-102">ICorDebugDataTarget3 Interface</span></span>
<span data-ttu-id="a81ba-103">論理的に拡張し、 [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)インターフェイスが読み込まれたモジュールに関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="a81ba-103">Logically extends the [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) interface to provide information about loaded modules.</span></span>  
  
## <a name="method"></a><span data-ttu-id="a81ba-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="a81ba-104">Method</span></span>  
  
|<span data-ttu-id="a81ba-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="a81ba-105">Method</span></span>|<span data-ttu-id="a81ba-106">説明</span><span class="sxs-lookup"><span data-stu-id="a81ba-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a81ba-107">GetLoadedModules メソッド</span><span class="sxs-lookup"><span data-stu-id="a81ba-107">GetLoadedModules Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget3-getloadedmodules-method.md)|<span data-ttu-id="a81ba-108">これまでに読み込まれたモジュールの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="a81ba-108">Gets a list of the modules that have been loaded so far.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a81ba-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="a81ba-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a81ba-110">このインターフェイスは .NET ネイティブでのみ使用可能です。</span><span class="sxs-lookup"><span data-stu-id="a81ba-110">This interface is available with .NET Native only.</span></span> <span data-ttu-id="a81ba-111">.NET ネイティブの外部で ICorDebug シナリオについてこのインターフェイスを実装する場合は、共通言語ランタイムはこのインターフェイスを無視します。</span><span class="sxs-lookup"><span data-stu-id="a81ba-111">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a81ba-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="a81ba-112">Requirements</span></span>  
 <span data-ttu-id="a81ba-113">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a81ba-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a81ba-114">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a81ba-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a81ba-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a81ba-115">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="a81ba-116">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="a81ba-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a81ba-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="a81ba-117">See also</span></span>

- [<span data-ttu-id="a81ba-118">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="a81ba-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="a81ba-119">デバッグ</span><span class="sxs-lookup"><span data-stu-id="a81ba-119">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
