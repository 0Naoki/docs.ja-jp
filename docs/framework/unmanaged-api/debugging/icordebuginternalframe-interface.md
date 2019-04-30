---
title: ICorDebugInternalFrame インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugInternalFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugInternalFrame
helpviewer_keywords:
- ICorDebugInternalFrame interface [.NET Framework debugging]
ms.assetid: bb4772ca-0d54-4185-b738-7a6ffe9ea85a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2f16b4628215bee2410708edeb337b41fbdc0311
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61946381"
---
# <a name="icordebuginternalframe-interface"></a><span data-ttu-id="71d2d-102">ICorDebugInternalFrame インターフェイス</span><span class="sxs-lookup"><span data-stu-id="71d2d-102">ICorDebugInternalFrame Interface</span></span>

<span data-ttu-id="71d2d-103">ランタイム内部スタックにフレームを表します。</span><span class="sxs-lookup"><span data-stu-id="71d2d-103">Represents a runtime-internal frame on the stack.</span></span> <span data-ttu-id="71d2d-104">このインターフェイスは、ICorDebugFrame インターフェイスのサブクラスです。</span><span class="sxs-lookup"><span data-stu-id="71d2d-104">This interface is a subclass of the ICorDebugFrame interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="71d2d-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="71d2d-105">Methods</span></span>  
  
|<span data-ttu-id="71d2d-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="71d2d-106">Method</span></span>|<span data-ttu-id="71d2d-107">説明</span><span class="sxs-lookup"><span data-stu-id="71d2d-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="71d2d-108">GetFrameType メソッド</span><span class="sxs-lookup"><span data-stu-id="71d2d-108">GetFrameType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe-getframetype-method.md)|<span data-ttu-id="71d2d-109">この内部フレームの種類を取得します。</span><span class="sxs-lookup"><span data-stu-id="71d2d-109">Gets the type of this internal frame.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="71d2d-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="71d2d-110">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="71d2d-111">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="71d2d-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="71d2d-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="71d2d-112">Requirements</span></span>  
 <span data-ttu-id="71d2d-113">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="71d2d-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="71d2d-114">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="71d2d-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="71d2d-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="71d2d-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="71d2d-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="71d2d-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71d2d-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="71d2d-117">See also</span></span>

- [<span data-ttu-id="71d2d-118">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="71d2d-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
