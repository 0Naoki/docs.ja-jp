---
title: ICorDebugStackWalk::GetContext メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugStackWalk.GetContext Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStackWalk::GetContext
helpviewer_keywords:
- GetContext method, ICorDebugStackWalk interface [.NET Framework debugging]
- ICorDebugStackWalk::GetContext method [.NET Framework debugging]
ms.assetid: 081d1c95-152b-4797-8552-18453eb7b14b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bba1e6c113fb4caa0db8963e238d3eceba0cc8ce
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59224859"
---
# <a name="icordebugstackwalkgetcontext-method"></a><span data-ttu-id="dbc94-102">ICorDebugStackWalk::GetContext メソッド</span><span class="sxs-lookup"><span data-stu-id="dbc94-102">ICorDebugStackWalk::GetContext Method</span></span>
<span data-ttu-id="dbc94-103">現在のフレームのコンテキストを返します、 [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md)オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="dbc94-103">Returns the context for the current frame in the [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dbc94-104">構文</span><span class="sxs-lookup"><span data-stu-id="dbc94-104">Syntax</span></span>  
  
```  
HRESULT GetContext([in]  ULONG32 contextFlags,  
                   [in]  ULONG32 contextBufSize,  
                   [out] ULONG32* contextSize,  
                   [out, size_is(contextBufSize)] BYTE contextBuf[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dbc94-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="dbc94-105">Parameters</span></span>  
 `contextFlags`  
 <span data-ttu-id="dbc94-106">[in]要求された (WinNT.h で定義されている) コンテキスト バッファーの内容を示すフラグです。</span><span class="sxs-lookup"><span data-stu-id="dbc94-106">[in] Flags that indicate the requested contents of the context buffer (defined in WinNT.h).</span></span>  
  
 `contextBufSize`  
 <span data-ttu-id="dbc94-107">[in]コンテキスト バッファーの割り当てサイズ。</span><span class="sxs-lookup"><span data-stu-id="dbc94-107">[in] The allocated size of the context buffer.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="dbc94-108">[out]コンテキストの実際のサイズ。</span><span class="sxs-lookup"><span data-stu-id="dbc94-108">[out] The actual size of the context.</span></span> <span data-ttu-id="dbc94-109">この値は、コンテキスト バッファーのサイズ以下である必要があります。</span><span class="sxs-lookup"><span data-stu-id="dbc94-109">This value must be less than or equal to the size of the context buffer.</span></span>  
  
 `contextBuf`  
 <span data-ttu-id="dbc94-110">[out]コンテキストのバッファー。</span><span class="sxs-lookup"><span data-stu-id="dbc94-110">[out] The context buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="dbc94-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="dbc94-111">Return Value</span></span>  
 <span data-ttu-id="dbc94-112">このメソッドは、次の特定の HRESULT と、メソッドの失敗を示す HRESULT エラーも返します。</span><span class="sxs-lookup"><span data-stu-id="dbc94-112">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="dbc94-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="dbc94-113">HRESULT</span></span>|<span data-ttu-id="dbc94-114">説明</span><span class="sxs-lookup"><span data-stu-id="dbc94-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="dbc94-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="dbc94-115">S_OK</span></span>|<span data-ttu-id="dbc94-116">現在のフレームのコンテキストが正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="dbc94-116">The context for the current frame was successfully returned.</span></span>|  
|<span data-ttu-id="dbc94-117">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="dbc94-117">E_FAIL</span></span>|<span data-ttu-id="dbc94-118">コンテキストは返されませんでした。</span><span class="sxs-lookup"><span data-stu-id="dbc94-118">The context could not be returned.</span></span>|  
|<span data-ttu-id="dbc94-119">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT BUFFER)</span><span class="sxs-lookup"><span data-stu-id="dbc94-119">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT BUFFER)</span></span>|<span data-ttu-id="dbc94-120">コンテキスト バッファーが小さすぎます。</span><span class="sxs-lookup"><span data-stu-id="dbc94-120">The context buffer is too small.</span></span>|  
|<span data-ttu-id="dbc94-121">CORDBG_E_PAST_END_OF_STACK</span><span class="sxs-lookup"><span data-stu-id="dbc94-121">CORDBG_E_PAST_END_OF_STACK</span></span>|<span data-ttu-id="dbc94-122">フレーム ポインターがスタックの末尾に達してそのため、追加のフレームにはアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="dbc94-122">The frame pointer is already at the end of the stack; therefore, no additional frames can be accessed.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="dbc94-123">例外</span><span class="sxs-lookup"><span data-stu-id="dbc94-123">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dbc94-124">Remarks</span><span class="sxs-lookup"><span data-stu-id="dbc94-124">Remarks</span></span>  
 <span data-ttu-id="dbc94-125">アンワインド非 volatile レジスタなどのレジスタのサブセットのみが復元されるため、コンテキストの呼び出しの時点でレジスタの状態が一致も一致しないです。</span><span class="sxs-lookup"><span data-stu-id="dbc94-125">Because unwinding restores only a subset of the registers, such as non-volatile registers, the context may not exactly match the register state at the time of the call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dbc94-126">必要条件</span><span class="sxs-lookup"><span data-stu-id="dbc94-126">Requirements</span></span>  
 <span data-ttu-id="dbc94-127">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="dbc94-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dbc94-128">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dbc94-128">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dbc94-129">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dbc94-129">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="dbc94-130">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="dbc94-130">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="dbc94-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="dbc94-131">See also</span></span>

- [<span data-ttu-id="dbc94-132">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="dbc94-132">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="dbc94-133">デバッグ</span><span class="sxs-lookup"><span data-stu-id="dbc94-133">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
