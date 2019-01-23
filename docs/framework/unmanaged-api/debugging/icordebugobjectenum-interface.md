---
title: ICorDebugObjectEnum Interface1
ms.date: 03/30/2017
api_name:
- ICorDebugObjectEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugObjectEnum
helpviewer_keywords:
- ICorDebugObjectEnum interface [.NET Framework debugging]
ms.assetid: 9ffb4498-7719-49d3-8890-df2c22248a0c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3a9f10301db488e4ca68ce5fdaf0ba767053d7d4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54547002"
---
# <a name="icordebugobjectenum-interface1"></a><span data-ttu-id="a204d-102">ICorDebugObjectEnum Interface1</span><span class="sxs-lookup"><span data-stu-id="a204d-102">ICorDebugObjectEnum Interface1</span></span>
<span data-ttu-id="a204d-103">ICorDebugEnum のメソッドを実装し、相対仮想アドレス (Rva) でオブジェクトの配列を列挙します。</span><span class="sxs-lookup"><span data-stu-id="a204d-103">Implements ICorDebugEnum methods, and enumerates arrays of objects by their relative virtual addresses (RVAs).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a204d-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="a204d-104">Methods</span></span>  
  
|<span data-ttu-id="a204d-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="a204d-105">Method</span></span>|<span data-ttu-id="a204d-106">説明</span><span class="sxs-lookup"><span data-stu-id="a204d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a204d-107">Next メソッド</span><span class="sxs-lookup"><span data-stu-id="a204d-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectenum-next-method.md)|<span data-ttu-id="a204d-108">列挙体の現在位置から指定した数のオブジェクトの Rva を取得します。</span><span class="sxs-lookup"><span data-stu-id="a204d-108">Gets the RVAs of the specified number of objects from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a204d-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="a204d-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a204d-110">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="a204d-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a204d-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="a204d-111">Requirements</span></span>  
 <span data-ttu-id="a204d-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a204d-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a204d-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a204d-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a204d-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a204d-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a204d-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a204d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a204d-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="a204d-116">See also</span></span>
- [<span data-ttu-id="a204d-117">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a204d-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
