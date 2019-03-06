---
title: ICorDebugHeapValue3::GetThreadOwningMonitorLock メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugHeapValue3.GetThreadOwningMonitorLock
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapValue3::GetThreadOwningMonitorLock
helpviewer_keywords:
- GetThreadOwningMonitorLock method [.NET Framework debugging]
- ICorDebugHeapValue3::GetThreadOwningMonitorLock method [.NET Framework debugging]
ms.assetid: e06fc19d-2cf4-4cad-81a3-137a68af8969
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 361cc3b897b4c85297b597f80aaffc2a2760f88e
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57468482"
---
# <a name="icordebugheapvalue3getthreadowningmonitorlock-method"></a><span data-ttu-id="ef523-102">ICorDebugHeapValue3::GetThreadOwningMonitorLock メソッド</span><span class="sxs-lookup"><span data-stu-id="ef523-102">ICorDebugHeapValue3::GetThreadOwningMonitorLock Method</span></span>
<span data-ttu-id="ef523-103">このオブジェクトのモニター ロックを所有しているマネージ スレッドを返します。</span><span class="sxs-lookup"><span data-stu-id="ef523-103">Returns the managed thread that owns the monitor lock on this object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef523-104">構文</span><span class="sxs-lookup"><span data-stu-id="ef523-104">Syntax</span></span>  
  
```  
HRESULT GetThreadOwningMonitorLock (  
    [out] ICorDebugThread   **ppThread,  
    [out] DWORD              *pAcquisitionCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ef523-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ef523-105">Parameters</span></span>  
 `ppThread`  
 <span data-ttu-id="ef523-106">[out]このオブジェクトのモニター ロックを所有しているマネージ スレッド。</span><span class="sxs-lookup"><span data-stu-id="ef523-106">[out] The managed thread that owns the monitor lock on this object.</span></span>  
  
 `pAcquisitionCount`  
 <span data-ttu-id="ef523-107">[out]このスレッドが所有されているに返す前に、ロックを解放する必要があります回数。</span><span class="sxs-lookup"><span data-stu-id="ef523-107">[out] The number of times this thread would have to release the lock before it returns to being unowned.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ef523-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="ef523-108">Return Value</span></span>  
 <span data-ttu-id="ef523-109">このメソッドは、次の特定の HRESULT と、メソッドの失敗を示す HRESULT エラーも返します。</span><span class="sxs-lookup"><span data-stu-id="ef523-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="ef523-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ef523-110">HRESULT</span></span>|<span data-ttu-id="ef523-111">説明</span><span class="sxs-lookup"><span data-stu-id="ef523-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ef523-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="ef523-112">S_OK</span></span>|<span data-ttu-id="ef523-113">メソッドは正常に完了しました。</span><span class="sxs-lookup"><span data-stu-id="ef523-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="ef523-114">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="ef523-114">S_FALSE</span></span>|<span data-ttu-id="ef523-115">マネージ スレッドでは、このオブジェクトのモニター ロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="ef523-115">No managed thread owns the monitor lock on this object.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="ef523-116">例外</span><span class="sxs-lookup"><span data-stu-id="ef523-116">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ef523-117">Remarks</span><span class="sxs-lookup"><span data-stu-id="ef523-117">Remarks</span></span>  
 <span data-ttu-id="ef523-118">マネージ スレッドは、このオブジェクトのモニター ロックを所有している: 場合</span><span class="sxs-lookup"><span data-stu-id="ef523-118">If a managed thread owns the monitor lock on this object:</span></span>  
  
-   <span data-ttu-id="ef523-119">メソッドは、S_OK を返します。</span><span class="sxs-lookup"><span data-stu-id="ef523-119">The method returns S_OK.</span></span>  
  
-   <span data-ttu-id="ef523-120">スレッド オブジェクトは、スレッドが終了するまで有効です。</span><span class="sxs-lookup"><span data-stu-id="ef523-120">The thread object is valid until the thread exits.</span></span>  
  
 <span data-ttu-id="ef523-121">マネージ スレッドが、このオブジェクトのモニター ロックを所有していない場合`ppThread`と`pAcquisitionCount`は変更されず、およびメソッドは S_FALSE を返します。</span><span class="sxs-lookup"><span data-stu-id="ef523-121">If no managed thread owns the monitor lock on this object, `ppThread` and `pAcquisitionCount` are unchanged, and the method returns S_FALSE.</span></span>  
  
 <span data-ttu-id="ef523-122">場合`ppThread`または`pAcquisitionCount`有効なポインターでない、結果は未定義です。</span><span class="sxs-lookup"><span data-stu-id="ef523-122">If `ppThread` or `pAcquisitionCount` is not a valid pointer, the result is undefined.</span></span>  
  
 <span data-ttu-id="ef523-123">スレッドが、このオブジェクトのモニター ロックを所有している場合は、これを特定できないように、エラーが発生した場合、メソッドは失敗を示す HRESULT を返します。</span><span class="sxs-lookup"><span data-stu-id="ef523-123">If an error occurs such that it cannot be determined which, if any, thread owns the monitor lock on this object, the method returns an HRESULT that indicates failure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ef523-124">必要条件</span><span class="sxs-lookup"><span data-stu-id="ef523-124">Requirements</span></span>  
 <span data-ttu-id="ef523-125">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ef523-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ef523-126">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ef523-126">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ef523-127">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ef523-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ef523-128">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ef523-128">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef523-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="ef523-129">See also</span></span>
- [<span data-ttu-id="ef523-130">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ef523-130">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="ef523-131">デバッグ</span><span class="sxs-lookup"><span data-stu-id="ef523-131">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
