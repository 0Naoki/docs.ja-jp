---
title: ICorDebugStepper2 インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugStepper2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper2
helpviewer_keywords:
- ICorDebugStepper2 interface [.NET Framework debugging]
ms.assetid: 7a191c2a-95ea-4d47-83b0-44de2b632d63
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 256f67d21a22ee4692d88311cc150736e61563a0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59073068"
---
# <a name="icordebugstepper2-interface"></a><span data-ttu-id="53f25-102">ICorDebugStepper2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="53f25-102">ICorDebugStepper2 Interface</span></span>
<span data-ttu-id="53f25-103">だけマイ コード (のみ JMC) デバッグのサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="53f25-103">Provides support for just my code (JMC) debugging.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="53f25-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="53f25-104">Methods</span></span>  
  
|<span data-ttu-id="53f25-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="53f25-105">Method</span></span>|<span data-ttu-id="53f25-106">説明</span><span class="sxs-lookup"><span data-stu-id="53f25-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="53f25-107">SetJMC メソッド</span><span class="sxs-lookup"><span data-stu-id="53f25-107">SetJMC Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper2-setjmc-method.md)|<span data-ttu-id="53f25-108">この ICorDebugStepper のステップは、アプリケーションの開発者が作成したコードからのみかどうかを指定する値を設定します。</span><span class="sxs-lookup"><span data-stu-id="53f25-108">Sets a value that specifies whether this ICorDebugStepper steps only through code that is authored by an application's developer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="53f25-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="53f25-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="53f25-110">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="53f25-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="53f25-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="53f25-111">Requirements</span></span>  
 <span data-ttu-id="53f25-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="53f25-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="53f25-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="53f25-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="53f25-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="53f25-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="53f25-115">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="53f25-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="53f25-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="53f25-116">See also</span></span>

- [<span data-ttu-id="53f25-117">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="53f25-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
