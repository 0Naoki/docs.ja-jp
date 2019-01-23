---
title: ICorDebugMetaDataLocator インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugMetaDataLocator
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugMetaDataLocator
helpviewer_keywords:
- ICorDebugMetaDataLocator interface [.NET Framework debugging]
ms.assetid: 287f5ecd-863f-4090-a615-077859f0257b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c1ee52e993859963984f7468e41a5daf3a77ba26
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54621670"
---
# <a name="icordebugmetadatalocator-interface"></a><span data-ttu-id="5cbbf-102">ICorDebugMetaDataLocator インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5cbbf-102">ICorDebugMetaDataLocator Interface</span></span>
<span data-ttu-id="5cbbf-103">デバッガーにメタデータ情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="5cbbf-103">Provides metadata information to the debugger.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5cbbf-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="5cbbf-104">Methods</span></span>  
  
|<span data-ttu-id="5cbbf-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="5cbbf-105">Method</span></span>|<span data-ttu-id="5cbbf-106">説明</span><span class="sxs-lookup"><span data-stu-id="5cbbf-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5cbbf-107">GetMetadata メソッド</span><span class="sxs-lookup"><span data-stu-id="5cbbf-107">GetMetaData Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmetadatalocator-getmetadata-method.md)|<span data-ttu-id="5cbbf-108">デバッガーが要求した操作を完了するために必要となるメタデータが含まれているモジュールの完全パスを返すように、デバッガーに求めます。</span><span class="sxs-lookup"><span data-stu-id="5cbbf-108">Asks the debugger to return the full path to a module whose metadata is needed to complete an operation the debugger requested.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5cbbf-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="5cbbf-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5cbbf-110">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="5cbbf-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5cbbf-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="5cbbf-111">Requirements</span></span>  
 <span data-ttu-id="5cbbf-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5cbbf-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5cbbf-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5cbbf-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5cbbf-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5cbbf-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5cbbf-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5cbbf-115">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5cbbf-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="5cbbf-116">See also</span></span>
- [<span data-ttu-id="5cbbf-117">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5cbbf-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="5cbbf-118">デバッグ</span><span class="sxs-lookup"><span data-stu-id="5cbbf-118">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
