---
title: ICorDebugThread3::CreateStackWalk メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugThread3.CreateStackWalk Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread3::CreateStackWalk
helpviewer_keywords:
- CreateStackWalk method [.NET Framework debugging]
- ICorDebugThread3::CreateStackWalk method [.NET Framework debugging]
ms.assetid: c55e35d9-f9aa-4268-94b5-dce44c61acf2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7969d8482970b13951938203262f6ce8f9bf574a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59229304"
---
# <a name="icordebugthread3createstackwalk-method"></a><span data-ttu-id="41563-102">ICorDebugThread3::CreateStackWalk メソッド</span><span class="sxs-lookup"><span data-stu-id="41563-102">ICorDebugThread3::CreateStackWalk Method</span></span>
<span data-ttu-id="41563-103">作成、 [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md)がスタックをアンワインドするスレッドのオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="41563-103">Creates an [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) object for the thread whose stack you want to unwind.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41563-104">構文</span><span class="sxs-lookup"><span data-stu-id="41563-104">Syntax</span></span>  
  
```  
HRESULT CreateStackWalk([out] ICorDebugStackWalk **ppStackWalk);  
```  
  
## <a name="parameters"></a><span data-ttu-id="41563-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="41563-105">Parameters</span></span>  
 `ppStackWalk`  
 <span data-ttu-id="41563-106">[out]アドレスへのポインター、 [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md)がスタックをアンワインドするスレッドのオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="41563-106">[out] A pointer to address of the [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) object for the thread whose stack you want to unwind.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="41563-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="41563-107">Return Value</span></span>  
 <span data-ttu-id="41563-108">このメソッドは、次の特定の HRESULT と、メソッドの失敗を示す HRESULT エラーも返します。</span><span class="sxs-lookup"><span data-stu-id="41563-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="41563-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="41563-109">HRESULT</span></span>|<span data-ttu-id="41563-110">説明</span><span class="sxs-lookup"><span data-stu-id="41563-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="41563-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="41563-111">S_OK</span></span>|<span data-ttu-id="41563-112">`ICorDebugStackWalk`オブジェクトが正常に作成します。</span><span class="sxs-lookup"><span data-stu-id="41563-112">The `ICorDebugStackWalk` object was successfully created.</span></span>|  
|<span data-ttu-id="41563-113">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="41563-113">E_FAIL</span></span>|<span data-ttu-id="41563-114">`ICorDebugStackWalk`オブジェクトは作成されませんでした。</span><span class="sxs-lookup"><span data-stu-id="41563-114">The `ICorDebugStackWalk` object was not created.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="41563-115">例外</span><span class="sxs-lookup"><span data-stu-id="41563-115">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="41563-116">Remarks</span><span class="sxs-lookup"><span data-stu-id="41563-116">Remarks</span></span>  
 <span data-ttu-id="41563-117">場合、`CreateStackWalk`メソッドが成功すると、返された`ICorDebugStackWalk`オブジェクトのコンテキストが、スレッドの現在のコンテキストに設定します。</span><span class="sxs-lookup"><span data-stu-id="41563-117">If the `CreateStackWalk` method succeeds, the returned `ICorDebugStackWalk` object's context is set to the thread's current context.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="41563-118">必要条件</span><span class="sxs-lookup"><span data-stu-id="41563-118">Requirements</span></span>  
 <span data-ttu-id="41563-119">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="41563-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="41563-120">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="41563-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="41563-121">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="41563-121">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="41563-122">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="41563-122">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="41563-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="41563-123">See also</span></span>

- [<span data-ttu-id="41563-124">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="41563-124">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="41563-125">デバッグ</span><span class="sxs-lookup"><span data-stu-id="41563-125">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
