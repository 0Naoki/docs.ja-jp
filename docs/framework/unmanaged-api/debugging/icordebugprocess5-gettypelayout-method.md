---
title: ICorDebugProcess5::GetTypeLayout メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.GetTypeLayout
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::GetTypeLayout
helpviewer_keywords:
- ICorDebugProcess5::GetTypeLayout method [.NET Framework debugging]
- GetTypeLayout method, ICorDebugProcess5 interface [.NET Framework debugging]
ms.assetid: bd62f5d1-e874-41f1-81e5-a29a7572c15d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b05ff331520e0afc24b02fa7262045612c6344c1
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59162764"
---
# <a name="icordebugprocess5gettypelayout-method"></a><span data-ttu-id="af4f1-102">ICorDebugProcess5::GetTypeLayout メソッド</span><span class="sxs-lookup"><span data-stu-id="af4f1-102">ICorDebugProcess5::GetTypeLayout Method</span></span>
<span data-ttu-id="af4f1-103">その型の識別子に基づくメモリ内のオブジェクトのレイアウトに関する情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="af4f1-103">Gets information about the layout of an object in memory based on its type identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af4f1-104">構文</span><span class="sxs-lookup"><span data-stu-id="af4f1-104">Syntax</span></span>  
  
```  
HRESULT GetTypeLayout(    [in] COR_TYPEID id,     [out] COR_TYPE_LAYOUT *pLayout);  
```  
  
## <a name="parameters"></a><span data-ttu-id="af4f1-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="af4f1-105">Parameters</span></span>  
 `id`  
 <span data-ttu-id="af4f1-106">[in]A [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md)レイアウトを持つが必要な型を示すトークン。</span><span class="sxs-lookup"><span data-stu-id="af4f1-106">[in] A [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) token that specifies the type whose layout is desired.</span></span>  
  
 `pLayout`  
 <span data-ttu-id="af4f1-107">[out]ポインターを[COR_TYPE_LAYOUT](../../../../docs/framework/unmanaged-api/debugging/cor-type-layout-structure.md)メモリ内のオブジェクトのレイアウトに関する情報を含む構造体。</span><span class="sxs-lookup"><span data-stu-id="af4f1-107">[out] A pointer to a [COR_TYPE_LAYOUT](../../../../docs/framework/unmanaged-api/debugging/cor-type-layout-structure.md) structure that contains information about the layout of the object in memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="af4f1-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="af4f1-108">Remarks</span></span>  
 <span data-ttu-id="af4f1-109">`ICorDebugProcess5::GetTypeLayout`メソッドに基づくオブジェクトに関する情報を提供するその[COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md)、他の数値から返される[ICorDebugProcess5](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="af4f1-109">The `ICorDebugProcess5::GetTypeLayout` method provides information about an object based on its [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md), which is returned by a number of other [ICorDebugProcess5](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md) methods.</span></span> <span data-ttu-id="af4f1-110">によって、情報が提供される、 [COR_TYPE_LAYOUT](../../../../docs/framework/unmanaged-api/debugging/cor-type-layout-structure.md)メソッドによって設定される構造体。</span><span class="sxs-lookup"><span data-stu-id="af4f1-110">The information is provided by a [COR_TYPE_LAYOUT](../../../../docs/framework/unmanaged-api/debugging/cor-type-layout-structure.md) structure that is populated by the method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="af4f1-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="af4f1-111">Requirements</span></span>  
 <span data-ttu-id="af4f1-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="af4f1-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="af4f1-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="af4f1-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="af4f1-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="af4f1-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="af4f1-115">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="af4f1-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="af4f1-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="af4f1-116">See also</span></span>

- [<span data-ttu-id="af4f1-117">COR_TYPE_LAYOUT 構造体</span><span class="sxs-lookup"><span data-stu-id="af4f1-117">COR_TYPE_LAYOUT Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/cor-type-layout-structure.md)
- [<span data-ttu-id="af4f1-118">ICorDebugProcess5 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="af4f1-118">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [<span data-ttu-id="af4f1-119">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="af4f1-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
