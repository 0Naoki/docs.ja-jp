---
title: ICorDebugEnum インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEnum
helpviewer_keywords:
- ICorDebugEnum interface [.NET Framework debugging]
ms.assetid: 80be7efe-2c32-4b9f-8c52-40c6f6268219
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9afaeebfdb98a404ea53b0b5ec147f8c8104e14d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59148812"
---
# <a name="icordebugenum-interface"></a><span data-ttu-id="2f520-102">ICorDebugEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2f520-102">ICorDebugEnum Interface</span></span>

<span data-ttu-id="2f520-103">デバッグ アプリケーションで使用される列挙子の抽象基底インターフェイスとして機能します。</span><span class="sxs-lookup"><span data-stu-id="2f520-103">Serves as the abstract base interface for the enumerators that are used by a debugging application.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2f520-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="2f520-104">Methods</span></span>  
  
|<span data-ttu-id="2f520-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="2f520-105">Method</span></span>|<span data-ttu-id="2f520-106">説明</span><span class="sxs-lookup"><span data-stu-id="2f520-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2f520-107">Clone メソッド</span><span class="sxs-lookup"><span data-stu-id="2f520-107">Clone Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-clone-method.md)|<span data-ttu-id="2f520-108">このコピーを作成します`ICorDebugEnum`オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="2f520-108">Creates a copy of this `ICorDebugEnum` object.</span></span>|  
|[<span data-ttu-id="2f520-109">GetCount メソッド</span><span class="sxs-lookup"><span data-stu-id="2f520-109">GetCount Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-getcount-method.md)|<span data-ttu-id="2f520-110">列挙に含まれる項目の数を取得します。</span><span class="sxs-lookup"><span data-stu-id="2f520-110">Gets the number of items in the enumeration.</span></span>|  
|[<span data-ttu-id="2f520-111">Reset メソッド</span><span class="sxs-lookup"><span data-stu-id="2f520-111">Reset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-reset-method.md)|<span data-ttu-id="2f520-112">列挙体の先頭にカーソルを移動します。</span><span class="sxs-lookup"><span data-stu-id="2f520-112">Moves the cursor to the beginning of the enumeration.</span></span>|  
|[<span data-ttu-id="2f520-113">Skip メソッド</span><span class="sxs-lookup"><span data-stu-id="2f520-113">Skip Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-skip-method.md)|<span data-ttu-id="2f520-114">指定数の項目では、列挙体にカーソルを移動します。</span><span class="sxs-lookup"><span data-stu-id="2f520-114">Moves the cursor forward in the enumeration by the specified number of items.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2f520-115">Remarks</span><span class="sxs-lookup"><span data-stu-id="2f520-115">Remarks</span></span>  
 <span data-ttu-id="2f520-116">次の列挙子から派生して`ICorDebugEnum`:</span><span class="sxs-lookup"><span data-stu-id="2f520-116">The following enumerators derive from `ICorDebugEnum`:</span></span>  
  
-   <span data-ttu-id="2f520-117">"ICorDebugAppDomainEnum"</span><span class="sxs-lookup"><span data-stu-id="2f520-117">"ICorDebugAppDomainEnum"</span></span>  
  
-   <span data-ttu-id="2f520-118">"ICorDebugAssemblyEnum"</span><span class="sxs-lookup"><span data-stu-id="2f520-118">"ICorDebugAssemblyEnum"</span></span>  
  
-   [<span data-ttu-id="2f520-119">ICorDebugBlockingObjectEnum</span><span class="sxs-lookup"><span data-stu-id="2f520-119">ICorDebugBlockingObjectEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugblockingobjectenum-interface.md)  
  
-   <span data-ttu-id="2f520-120">"ICorDebugBreakpointEnum"</span><span class="sxs-lookup"><span data-stu-id="2f520-120">"ICorDebugBreakpointEnum"</span></span>  
  
-   <span data-ttu-id="2f520-121">"ICorDebugChainEnum"</span><span class="sxs-lookup"><span data-stu-id="2f520-121">"ICorDebugChainEnum"</span></span>  
  
-   <span data-ttu-id="2f520-122">"ICorDebugCodeEnum"</span><span class="sxs-lookup"><span data-stu-id="2f520-122">"ICorDebugCodeEnum"</span></span>  
  
-   <span data-ttu-id="2f520-123">"ICorDebugErrorInfoEnum"</span><span class="sxs-lookup"><span data-stu-id="2f520-123">"ICorDebugErrorInfoEnum"</span></span>  
  
-   [<span data-ttu-id="2f520-124">ICorDebugExceptionObjectCallStackEnum</span><span class="sxs-lookup"><span data-stu-id="2f520-124">ICorDebugExceptionObjectCallStackEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md)  
  
-   <span data-ttu-id="2f520-125">"ICorDebugFrameEnum"</span><span class="sxs-lookup"><span data-stu-id="2f520-125">"ICorDebugFrameEnum"</span></span>  
  
-   [<span data-ttu-id="2f520-126">ICorDebugGCReferenceEnum</span><span class="sxs-lookup"><span data-stu-id="2f520-126">ICorDebugGCReferenceEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md)  
  
-   [<span data-ttu-id="2f520-127">ICorDebugGuidToTypeEnum</span><span class="sxs-lookup"><span data-stu-id="2f520-127">ICorDebugGuidToTypeEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-interface.md)  
  
-   [<span data-ttu-id="2f520-128">ICorDebugHeapEnum</span><span class="sxs-lookup"><span data-stu-id="2f520-128">ICorDebugHeapEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md)  
  
-   [<span data-ttu-id="2f520-129">ICorDebugHeapSegmentEnum</span><span class="sxs-lookup"><span data-stu-id="2f520-129">ICorDebugHeapSegmentEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md)  
  
-   <span data-ttu-id="2f520-130">"ICorDebugModuleEnum"</span><span class="sxs-lookup"><span data-stu-id="2f520-130">"ICorDebugModuleEnum"</span></span>  
  
-   <span data-ttu-id="2f520-131">"ICorDebugObjectEnum"</span><span class="sxs-lookup"><span data-stu-id="2f520-131">"ICorDebugObjectEnum"</span></span>  
  
-   <span data-ttu-id="2f520-132">"ICorDebugProcessEnum"</span><span class="sxs-lookup"><span data-stu-id="2f520-132">"ICorDebugProcessEnum"</span></span>  
  
-   <span data-ttu-id="2f520-133">"ICorDebugStepperEnum"</span><span class="sxs-lookup"><span data-stu-id="2f520-133">"ICorDebugStepperEnum"</span></span>  
  
-   <span data-ttu-id="2f520-134">"ICorDebugThreadEnum"</span><span class="sxs-lookup"><span data-stu-id="2f520-134">"ICorDebugThreadEnum"</span></span>  
  
-   <span data-ttu-id="2f520-135">"ICorDebugTypeEnum"</span><span class="sxs-lookup"><span data-stu-id="2f520-135">"ICorDebugTypeEnum"</span></span>  
  
-   <span data-ttu-id="2f520-136">"ICorDebugValueEnum"</span><span class="sxs-lookup"><span data-stu-id="2f520-136">"ICorDebugValueEnum"</span></span>  
  
-   [<span data-ttu-id="2f520-137">ICorDebugVariableHomeEnum</span><span class="sxs-lookup"><span data-stu-id="2f520-137">ICorDebugVariableHomeEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md)  
  
> [!NOTE]
>  <span data-ttu-id="2f520-138">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="2f520-138">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2f520-139">必要条件</span><span class="sxs-lookup"><span data-stu-id="2f520-139">Requirements</span></span>  
 <span data-ttu-id="2f520-140">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2f520-140">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2f520-141">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2f520-141">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2f520-142">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2f520-142">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="2f520-143">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="2f520-143">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="2f520-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="2f520-144">See also</span></span>

- [<span data-ttu-id="2f520-145">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="2f520-145">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
