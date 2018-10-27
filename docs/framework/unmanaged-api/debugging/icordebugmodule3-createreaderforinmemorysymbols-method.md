---
title: ICorDebugModule3::CreateReaderForInMemorySymbols メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugModule3.CreateReaderForInMemorySymbols
api_location:
- CorDebug.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule3::CreateReaderForInMemorySymbols
helpviewer_keywords:
- CreateReaderForInMemorySymbols method, ICorDebugModule3 interface [.NET Framework debugging]
- ICorDebugModule3::CreateReaderForInMemorySymbols method [.NET Framework debugging]
ms.assetid: af317171-d66d-4114-89eb-063554c74940
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e404228cbc6efb81ed90c135358b1832ddcd8954
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2018
ms.locfileid: "50185366"
---
# <a name="icordebugmodule3createreaderforinmemorysymbols-method"></a><span data-ttu-id="58407-102">ICorDebugModule3::CreateReaderForInMemorySymbols メソッド</span><span class="sxs-lookup"><span data-stu-id="58407-102">ICorDebugModule3::CreateReaderForInMemorySymbols Method</span></span>
<span data-ttu-id="58407-103">動的モジュールのデバッグのシンボル リーダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="58407-103">Creates a debug symbol reader for a dynamic module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58407-104">構文</span><span class="sxs-lookup"><span data-stu-id="58407-104">Syntax</span></span>  
  
```  
HRESULT CreateReaderForInMemorySymbols (  
      [in] REFIID riid,  
      [out][iid_is(riid)] void **    ppObj  
```  
  
#### <a name="parameters"></a><span data-ttu-id="58407-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="58407-105">Parameters</span></span>  
 <span data-ttu-id="58407-106">riid</span><span class="sxs-lookup"><span data-stu-id="58407-106">riid</span></span>  
 <span data-ttu-id="58407-107">[in]返す COM インターフェイスの IID。</span><span class="sxs-lookup"><span data-stu-id="58407-107">[in] The IID of the COM interface to return.</span></span> <span data-ttu-id="58407-108">通常、これは、 [ISymUnmanagedReader インターフェイス](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)します。</span><span class="sxs-lookup"><span data-stu-id="58407-108">Typically, this is an [ISymUnmanagedReader Interface](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md).</span></span>  
  
 <span data-ttu-id="58407-109">ppObj</span><span class="sxs-lookup"><span data-stu-id="58407-109">ppObj</span></span>  
 <span data-ttu-id="58407-110">[out]返されるインターフェイスへのポインターへのポインター。</span><span class="sxs-lookup"><span data-stu-id="58407-110">[out] Pointer to a pointer to the returned interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="58407-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="58407-111">Return Value</span></span>  
 <span data-ttu-id="58407-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="58407-112">S_OK</span></span>  
 <span data-ttu-id="58407-113">リーダーが正常に作成します。</span><span class="sxs-lookup"><span data-stu-id="58407-113">Successfully created the reader.</span></span>  
  
 <span data-ttu-id="58407-114">CORDBG_E_MODULE_LOADED_FROM_DISK</span><span class="sxs-lookup"><span data-stu-id="58407-114">CORDBG_E_MODULE_LOADED_FROM_DISK</span></span>  
 <span data-ttu-id="58407-115">モジュールは、メモリ内または動的モジュールではありません。</span><span class="sxs-lookup"><span data-stu-id="58407-115">The module is not an in-memory or dynamic module.</span></span>  
  
 <span data-ttu-id="58407-116">CORDBG_E_SYMBOLS_NOT_AVAILABLE</span><span class="sxs-lookup"><span data-stu-id="58407-116">CORDBG_E_SYMBOLS_NOT_AVAILABLE</span></span>  
 <span data-ttu-id="58407-117">シンボルは、アプリケーションで指定されていないまたはまだ提供されていません。</span><span class="sxs-lookup"><span data-stu-id="58407-117">Symbols have not been supplied by the application or are not yet available.</span></span>  
  
 <span data-ttu-id="58407-118">E_FAIL (またはその他の E_ リターン コード)</span><span class="sxs-lookup"><span data-stu-id="58407-118">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="58407-119">リーダーを作成できません。</span><span class="sxs-lookup"><span data-stu-id="58407-119">Unable to create the reader.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="58407-120">Remarks</span><span class="sxs-lookup"><span data-stu-id="58407-120">Remarks</span></span>  
 <span data-ttu-id="58407-121">このメソッドも、メモリ内の (非動的) モジュールのシンボル リーダー オブジェクトを作成するために使用のみするシンボルが利用可能に最初 (で示される、 [UpdateModuleSymbols メソッド](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-updatemodulesymbols-method.md)コールバック)。</span><span class="sxs-lookup"><span data-stu-id="58407-121">This method can also be used to create a symbol reader object for in-memory (non-dynamic) modules, but only after the symbols are first available (indicated by the [UpdateModuleSymbols Method](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-updatemodulesymbols-method.md) callback).</span></span>  
  
 <span data-ttu-id="58407-122">このメソッドが呼び出されるたびに、新しいリーダーのインスタンスを返します (など[CComPtrBase::CoCreateInstance](/cpp/atl/reference/ccomptrbase-class#cocreateinstance))。</span><span class="sxs-lookup"><span data-stu-id="58407-122">This method returns a new reader instance every time it is called (like [CComPtrBase::CoCreateInstance](/cpp/atl/reference/ccomptrbase-class#cocreateinstance)).</span></span> <span data-ttu-id="58407-123">そのため、デバッガーが結果をキャッシュして、基になるデータが変更されたときにのみ、新しいインスタンスを要求する必要があります (つまりとき、 [LoadClass メソッド](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md)コールバックを受信した)。</span><span class="sxs-lookup"><span data-stu-id="58407-123">Therefore, the debugger should cache the result and request a new instance only when the underlying data may have changed (that is, when a [LoadClass Method](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) callback is received).</span></span>  
  
 <span data-ttu-id="58407-124">最初の型が読み込まれるまで動的モジュールは使用可能なすべてのシンボルはありません (で示されている、 [LoadClass メソッド](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md)コールバック)。</span><span class="sxs-lookup"><span data-stu-id="58407-124">Dynamic modules do not have any symbols available until the first type has been loaded (as indicated by the [LoadClass Method](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) callback).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="58407-125">必要条件</span><span class="sxs-lookup"><span data-stu-id="58407-125">Requirements</span></span>  
 <span data-ttu-id="58407-126">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="58407-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="58407-127">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="58407-127">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="58407-128">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="58407-128">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="58407-129">**.NET framework のバージョン:** 4.5、4、3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="58407-129">**.NET Framework Versions:** 4.5, 4, 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58407-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="58407-130">See Also</span></span>  
 [<span data-ttu-id="58407-131">ICorDebugRemoteTarget インターフェイス</span><span class="sxs-lookup"><span data-stu-id="58407-131">ICorDebugRemoteTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md)  
 [<span data-ttu-id="58407-132">ICorDebug インターフェイス</span><span class="sxs-lookup"><span data-stu-id="58407-132">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)  
    
 [<span data-ttu-id="58407-133">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="58407-133">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
