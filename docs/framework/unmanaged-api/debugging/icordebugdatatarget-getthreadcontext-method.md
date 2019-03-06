---
title: ICorDebugDataTarget::GetThreadContext メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugDataTarget.GetThreadContext Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugDataTarget::GetThreadContext
helpviewer_keywords:
- ICorDebugDataTarget::GetThreadContext method [.NET Framework debugging]
- GetThreadContext method, ICorDebugDataTarget interface [.NET Framework debugging]
ms.assetid: c8954268-1821-4b23-b665-dbb55f2af31b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c0d579ffe6bf0722365e789ba3a43ce1dce06fac
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57502996"
---
# <a name="icordebugdatatargetgetthreadcontext-method"></a><span data-ttu-id="45843-102">ICorDebugDataTarget::GetThreadContext メソッド</span><span class="sxs-lookup"><span data-stu-id="45843-102">ICorDebugDataTarget::GetThreadContext Method</span></span>
<span data-ttu-id="45843-103">指定したスレッドの現在のスレッド コンテキストを返します。</span><span class="sxs-lookup"><span data-stu-id="45843-103">Returns the current thread context for the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45843-104">構文</span><span class="sxs-lookup"><span data-stu-id="45843-104">Syntax</span></span>  
  
```  
HRESULT GetThreadContext(  
       [in] DWORD dwThreadID,  
       [in] ULONG32 contextFlags,  
       [in] ULONG32 contextSize,  
       [out, size_is(contextSize)] BYTE * pContext);  
```  
  
## <a name="parameters"></a><span data-ttu-id="45843-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="45843-105">Parameters</span></span>  
 `dwThreadID`  
 <span data-ttu-id="45843-106">[in]コンテキストが取得されるスレッドの識別子。</span><span class="sxs-lookup"><span data-stu-id="45843-106">[in] The identifier of the thread whose context is to be retrieved.</span></span> <span data-ttu-id="45843-107">識別子は、オペレーティング システムによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="45843-107">The identifier is defined by the operating system.</span></span>  
  
 `contextFlags`  
 <span data-ttu-id="45843-108">[in]コンテキストのどの部分を示すプラットフォームに依存するフラグのビットごとの組み合わせをお読みください。</span><span class="sxs-lookup"><span data-stu-id="45843-108">[in] A bitwise combination of platform-dependent flags that indicate which portions of the context should be read.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="45843-109">[入力] `pContext` のサイズ。</span><span class="sxs-lookup"><span data-stu-id="45843-109">[in] The size of `pContext`.</span></span>  
  
 `pContext`  
 <span data-ttu-id="45843-110">[out]スレッド コンテキストを格納するバッファー。</span><span class="sxs-lookup"><span data-stu-id="45843-110">[out] The buffer where the thread context will be stored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="45843-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="45843-111">Remarks</span></span>  
 <span data-ttu-id="45843-112">Windows のプラットフォームで`pContext`必要があります、`CONTEXT`構造 (WinNT.h で定義されている) で指定されたコンピューターの種類に適した、 [icordebugdatatarget::getplatform](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="45843-112">On Windows platforms, `pContext` must be a `CONTEXT` structure (defined in WinNT.h) that is appropriate for the machine type specified by the [ICorDebugDataTarget::GetPlatform](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md) method.</span></span> <span data-ttu-id="45843-113">`contextFlags` として値が同じである必要があります、`ContextFlags`のフィールド、`CONTEXT`構造体。</span><span class="sxs-lookup"><span data-stu-id="45843-113">`contextFlags` must have the same values as the `ContextFlags` field of the `CONTEXT` structure.</span></span> <span data-ttu-id="45843-114">`CONTEXT`構造は、プロセッサ固有。 詳細については、WinNT.h でファイルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="45843-114">The `CONTEXT` structure is processor-specific; refer to the WinNT.h file for details.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="45843-115">必要条件</span><span class="sxs-lookup"><span data-stu-id="45843-115">Requirements</span></span>  
 <span data-ttu-id="45843-116">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="45843-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="45843-117">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="45843-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="45843-118">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="45843-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="45843-119">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="45843-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45843-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="45843-120">See also</span></span>
- [<span data-ttu-id="45843-121">ICorDebugDataTarget インターフェイス</span><span class="sxs-lookup"><span data-stu-id="45843-121">ICorDebugDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)
- [<span data-ttu-id="45843-122">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="45843-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="45843-123">デバッグ</span><span class="sxs-lookup"><span data-stu-id="45843-123">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
