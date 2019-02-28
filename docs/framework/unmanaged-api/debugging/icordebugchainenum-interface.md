---
title: ICorDebugChainEnum インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugChainEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChainEnum
helpviewer_keywords:
- ICorDebugChainEnum interface [.NET Framework debugging]
ms.assetid: 6639335c-48e1-4e74-a4f3-70a6a0f54af1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 57a36f1d15ad251781b4d9843086a966fa2d4585
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2019
ms.locfileid: "56982129"
---
# <a name="icordebugchainenum-interface"></a><span data-ttu-id="3fd9b-102">ICorDebugChainEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3fd9b-102">ICorDebugChainEnum Interface</span></span>

<span data-ttu-id="3fd9b-103">ICorDebugEnum のメソッドを実装し、ICorDebugChain 配列を列挙します。</span><span class="sxs-lookup"><span data-stu-id="3fd9b-103">Implements ICorDebugEnum methods, and enumerates ICorDebugChain arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3fd9b-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="3fd9b-104">Methods</span></span>  
  
|<span data-ttu-id="3fd9b-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="3fd9b-105">Method</span></span>|<span data-ttu-id="3fd9b-106">説明</span><span class="sxs-lookup"><span data-stu-id="3fd9b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3fd9b-107">Next メソッド</span><span class="sxs-lookup"><span data-stu-id="3fd9b-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchainenum-next-method.md)|<span data-ttu-id="3fd9b-108">指定した数を取得`ICorDebugChain`列挙体の現在位置からのインスタンス。</span><span class="sxs-lookup"><span data-stu-id="3fd9b-108">Gets the specified number of `ICorDebugChain` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3fd9b-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="3fd9b-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3fd9b-110">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="3fd9b-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3fd9b-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="3fd9b-111">Requirements</span></span>  
 <span data-ttu-id="3fd9b-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3fd9b-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3fd9b-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3fd9b-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3fd9b-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3fd9b-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3fd9b-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3fd9b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3fd9b-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="3fd9b-116">See also</span></span>
- [<span data-ttu-id="3fd9b-117">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3fd9b-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
