---
title: ICorDebugThread4::HadUnhandledException メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugThread4.HadUnhandledException Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread4::HadUnhandledException
helpviewer_keywords:
- ICorDebugThread4::HadUnhandledException method [.NET Framework debugging]
- HadUnhandledException method [.NET Framework debugging]
ms.assetid: 05558daa-39e2-4c38-aeaf-e2aec4a09468
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 12433786f353212c1ffbd57e9bf526c3ecc60e9a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59163632"
---
# <a name="icordebugthread4hadunhandledexception-method"></a><span data-ttu-id="03900-102">ICorDebugThread4::HadUnhandledException メソッド</span><span class="sxs-lookup"><span data-stu-id="03900-102">ICorDebugThread4::HadUnhandledException Method</span></span>
<span data-ttu-id="03900-103">スレッドが未処理の例外をしたかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="03900-103">Indicates whether the thread has ever had an unhandled exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="03900-104">構文</span><span class="sxs-lookup"><span data-stu-id="03900-104">Syntax</span></span>  
  
```  
HRESULT GetBlockingObjects (  
    [out] ICorDebugBlockingObjectEnum **ppBlockingObjectEnum  
    );  
```  
  
## <a name="parameters"></a><span data-ttu-id="03900-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="03900-105">Parameters</span></span>  
 `ppBlockingObjectEnum`  
 <span data-ttu-id="03900-106">[out]順序付けされた列挙体のアドレスへのポインター [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md)構造体。</span><span class="sxs-lookup"><span data-stu-id="03900-106">[out] A pointer to the address of an ordered enumeration of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structures.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="03900-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="03900-107">Return Value</span></span>  
 <span data-ttu-id="03900-108">このメソッドは、次の特定の HRESULT と、メソッドの失敗を示す HRESULT エラーも返します。</span><span class="sxs-lookup"><span data-stu-id="03900-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="03900-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="03900-109">HRESULT</span></span>|<span data-ttu-id="03900-110">説明</span><span class="sxs-lookup"><span data-stu-id="03900-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="03900-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="03900-111">S_OK</span></span>|<span data-ttu-id="03900-112">スレッドは、未処理の例外の作成後にしました。</span><span class="sxs-lookup"><span data-stu-id="03900-112">The thread has had an unhandled exception since its creation.</span></span>|  
|<span data-ttu-id="03900-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="03900-113">S_FALSE</span></span>|<span data-ttu-id="03900-114">スレッドのハンドルされない例外がなかった。</span><span class="sxs-lookup"><span data-stu-id="03900-114">The thread has never had an unhandled exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="03900-115">Remarks</span><span class="sxs-lookup"><span data-stu-id="03900-115">Remarks</span></span>  
 <span data-ttu-id="03900-116">このメソッドは、スレッドが未処理の例外をしたかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="03900-116">This method indicates whether the thread has ever had an unhandled exception.</span></span> <span data-ttu-id="03900-117">ハンドルされない例外コールバックがトリガーされた時点でまたはネイティブの JIT アタッチが開始されると、このメソッドは S_OK を返す保証されます。</span><span class="sxs-lookup"><span data-stu-id="03900-117">By the time the unhandled exception callback is triggered or native JIT-attach is initiated, this method is guaranteed to return S_OK.</span></span> <span data-ttu-id="03900-118">保証はありませんが、 [ICorDebugThread.GetCurrentException](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getcurrentexception-method.md)メソッドは、未処理の例外を返しますただし、場合、プロセスが続行されていない未処理の例外コールバックを取得した後、または時には。ネイティブ JIT アタッチします。</span><span class="sxs-lookup"><span data-stu-id="03900-118">There is no guarantee that the [ICorDebugThread.GetCurrentException](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getcurrentexception-method.md) method will return the unhandled exception; however, it will if the process has not yet been continued after getting the unhandled exception callback or upon native JIT-attach.</span></span> <span data-ttu-id="03900-119">さらに、ことができます (ただし、可能性は低い) にネイティブ JIT アタッチがトリガーされた時点でハンドルされない例外では、複数のスレッドがあります。</span><span class="sxs-lookup"><span data-stu-id="03900-119">Furthermore, it is possible (although unlikely) to have more than one thread with an unhandled exception at the time native JIT-attach is triggered.</span></span> <span data-ttu-id="03900-120">このような場合は、JIT アタッチする例外がトリガーされるかを判断する方法はありません。</span><span class="sxs-lookup"><span data-stu-id="03900-120">In such a case there is no way to determine which exception triggered the JIT-attach.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="03900-121">必要条件</span><span class="sxs-lookup"><span data-stu-id="03900-121">Requirements</span></span>  
 <span data-ttu-id="03900-122">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="03900-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="03900-123">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="03900-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="03900-124">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="03900-124">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="03900-125">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="03900-125">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="03900-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="03900-126">See also</span></span>

- [<span data-ttu-id="03900-127">ICorDebugThread4 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="03900-127">ICorDebugThread4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-interface.md)
- [<span data-ttu-id="03900-128">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="03900-128">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="03900-129">デバッグ</span><span class="sxs-lookup"><span data-stu-id="03900-129">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
