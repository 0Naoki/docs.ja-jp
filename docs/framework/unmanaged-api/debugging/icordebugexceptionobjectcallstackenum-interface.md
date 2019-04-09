---
title: ICorDebugExceptionObjectCallStackEnum インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugExceptionObjectCallStackEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugExceptionObjectCallStackEnum
helpviewer_keywords:
- ICorDebugExceptionObjectCallStackEnum interface [.NET Framework debugging]
ms.assetid: 39dffa18-c71b-48c4-b11d-e814631ab1e9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e7ed6c04a46a767ed122e54df0695429cf923b8a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59126205"
---
# <a name="icordebugexceptionobjectcallstackenum-interface"></a><span data-ttu-id="a3517-102">ICorDebugExceptionObjectCallStackEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a3517-102">ICorDebugExceptionObjectCallStackEnum Interface</span></span>
<span data-ttu-id="a3517-103">例外オブジェクトに埋め込まれているコール スタックの情報の列挙子を提供します。</span><span class="sxs-lookup"><span data-stu-id="a3517-103">Provides an enumerator for call stack information that is embedded in an exception object.</span></span> <span data-ttu-id="a3517-104">このインターフェイスは、ICorDebugEnum インターフェイスのサブクラスです。</span><span class="sxs-lookup"><span data-stu-id="a3517-104">This interface is a subclass of the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a3517-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="a3517-105">Methods</span></span>  
  
|<span data-ttu-id="a3517-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="a3517-106">Method</span></span>|<span data-ttu-id="a3517-107">説明</span><span class="sxs-lookup"><span data-stu-id="a3517-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a3517-108">Icordebugexceptionobjectcallstackenum::next</span><span class="sxs-lookup"><span data-stu-id="a3517-108">ICorDebugExceptionObjectCallStackEnum::Next</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-next-method.md)|<span data-ttu-id="a3517-109">指定した数を取得[CorDebugExceptionObjectStackFrame](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md)例外オブジェクトの呼び出し履歴に関する情報を含むオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="a3517-109">Gets a specified number of [CorDebugExceptionObjectStackFrame](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) objects that contain information about an exception object's call stack.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a3517-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="a3517-110">Remarks</span></span>  
 <span data-ttu-id="a3517-111">`ICorDebugExceptionObjectCallStackEnum` ICorDebugEnum インターフェイスを実装するインターフェイス。</span><span class="sxs-lookup"><span data-stu-id="a3517-111">The `ICorDebugExceptionObjectCallStackEnum` interface implements the ICorDebugEnum interface.</span></span>  
  
 <span data-ttu-id="a3517-112">`ICorDebugExceptionObjectCallStackEnum`インスタンスには、 [CorDebugExceptionObjectStackFrame](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md)オブジェクトを呼び出すことによって、 [icordebugexceptionobjectvalue::enumerateexceptioncallstack](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectvalue-enumerateexceptioncallstack-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="a3517-112">An `ICorDebugExceptionObjectCallStackEnum` instance is populated with [CorDebugExceptionObjectStackFrame](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) objects by calling the [ICorDebugExceptionObjectValue::EnumerateExceptionCallStack](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectvalue-enumerateexceptioncallstack-method.md) method.</span></span> <span data-ttu-id="a3517-113">呼び出すと、コレクション内の呼び出しスタックの項目を列挙できます、 [icordebugexceptionobjectcallstackenum::next](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-next-method.md)メソッド</span><span class="sxs-lookup"><span data-stu-id="a3517-113">The call stack items in the collection can be enumerated by calling the [ICorDebugExceptionObjectCallStackEnum::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-next-method.md) method</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a3517-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="a3517-114">Requirements</span></span>  
 <span data-ttu-id="a3517-115">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a3517-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a3517-116">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a3517-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a3517-117">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a3517-117">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="a3517-118">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="a3517-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a3517-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="a3517-119">See also</span></span>

- [<span data-ttu-id="a3517-120">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="a3517-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="a3517-121">デバッグ</span><span class="sxs-lookup"><span data-stu-id="a3517-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
