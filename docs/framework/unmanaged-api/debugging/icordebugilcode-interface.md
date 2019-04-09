---
title: ICorDebugILCode インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugILCode
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 51c4de0c-3813-4142-be25-a85bb84efb90
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 279a87039c4cbc12c7ec5f734928c851185280f0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59175722"
---
# <a name="icordebugilcode-interface"></a><span data-ttu-id="fa6c1-102">ICorDebugILCode インターフェイス</span><span class="sxs-lookup"><span data-stu-id="fa6c1-102">ICorDebugILCode Interface</span></span>
<span data-ttu-id="fa6c1-103">[.NET Framework 4.5.2 以降のバージョンでのみでサポート]</span><span class="sxs-lookup"><span data-stu-id="fa6c1-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="fa6c1-104">中間言語 (IL) コードのセグメントを表します。</span><span class="sxs-lookup"><span data-stu-id="fa6c1-104">Represents a segment of intermediate language (IL) code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="fa6c1-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="fa6c1-105">Methods</span></span>  
  
|<span data-ttu-id="fa6c1-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="fa6c1-106">Method</span></span>|<span data-ttu-id="fa6c1-107">説明</span><span class="sxs-lookup"><span data-stu-id="fa6c1-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="fa6c1-108">GetEHClauses メソッド</span><span class="sxs-lookup"><span data-stu-id="fa6c1-108">GetEHClauses Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-getehclauses-method.md)|<span data-ttu-id="fa6c1-109">この IL のために定義された例外処理 (EH) 句のリストへのポインターを返します。</span><span class="sxs-lookup"><span data-stu-id="fa6c1-109">Returns a pointer to a list of exception handling (EH) clauses that are defined for this IL.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="fa6c1-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="fa6c1-110">Requirements</span></span>  
 <span data-ttu-id="fa6c1-111">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="fa6c1-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fa6c1-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fa6c1-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fa6c1-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fa6c1-113">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="fa6c1-114">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="fa6c1-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="fa6c1-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="fa6c1-115">See also</span></span>

- [<span data-ttu-id="fa6c1-116">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="fa6c1-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="fa6c1-117">デバッグ</span><span class="sxs-lookup"><span data-stu-id="fa6c1-117">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
