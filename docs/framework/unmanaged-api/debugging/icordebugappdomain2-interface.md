---
title: ICorDebugAppDomain2 インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain2
helpviewer_keywords:
- ICorDebugAppDomain2 interface [.NET Framework debugging]
ms.assetid: 314d29f3-feb0-4a92-9530-b569c280cc31
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5c6ef901f43cd6568f17657ed8e58bc2cc2cc0a1
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59186057"
---
# <a name="icordebugappdomain2-interface"></a><span data-ttu-id="0900f-102">ICorDebugAppDomain2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0900f-102">ICorDebugAppDomain2 Interface</span></span>

<span data-ttu-id="0900f-103">配列、ポインター、関数ポインター、および参照型を使用するメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="0900f-103">Provides methods to work with arrays, pointers, function pointers, and reference types.</span></span> <span data-ttu-id="0900f-104">このインターフェイスは、ICorDebugAppDomain インターフェイスの拡張機能です。</span><span class="sxs-lookup"><span data-stu-id="0900f-104">This interface is an extension of the ICorDebugAppDomain interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0900f-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="0900f-105">Methods</span></span>  
  
|<span data-ttu-id="0900f-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="0900f-106">Method</span></span>|<span data-ttu-id="0900f-107">説明</span><span class="sxs-lookup"><span data-stu-id="0900f-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0900f-108">GetArrayOrPointerType メソッド</span><span class="sxs-lookup"><span data-stu-id="0900f-108">GetArrayOrPointerType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain2-getarrayorpointertype-method.md)|<span data-ttu-id="0900f-109">指定した型、ポインター、または指定した型への参照の配列を取得します。</span><span class="sxs-lookup"><span data-stu-id="0900f-109">Gets an array of the specified type, or a pointer or reference to the specified type.</span></span>|  
|[<span data-ttu-id="0900f-110">GetFunctionPointerType</span><span class="sxs-lookup"><span data-stu-id="0900f-110">GetFunctionPointerType</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain2-getfunctionpointertype-method.md)|<span data-ttu-id="0900f-111">指定されたシグネチャを持つ関数へのポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="0900f-111">Gets a pointer to a function that has a given signature.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0900f-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="0900f-112">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0900f-113">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="0900f-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0900f-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="0900f-114">Requirements</span></span>  
 <span data-ttu-id="0900f-115">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0900f-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0900f-116">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0900f-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0900f-117">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0900f-117">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="0900f-118">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="0900f-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="0900f-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="0900f-119">See also</span></span>

- [<span data-ttu-id="0900f-120">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="0900f-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
