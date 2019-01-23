---
title: ICorDebugVirtualUnwinder::Next メソッド
ms.date: 03/30/2017
ms.assetid: 790e0426-e5cd-49fd-a792-f8c8635d72fe
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b6b6b7078db058150ec39bcf82e6984a1949e7cd
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54507136"
---
# <a name="icordebugvirtualunwindernext-method"></a><span data-ttu-id="f6b8b-102">ICorDebugVirtualUnwinder::Next メソッド</span><span class="sxs-lookup"><span data-stu-id="f6b8b-102">ICorDebugVirtualUnwinder::Next Method</span></span>
<span data-ttu-id="f6b8b-103">呼び出し元のコンテキストに進みます。</span><span class="sxs-lookup"><span data-stu-id="f6b8b-103">Advances to the caller's context.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6b8b-104">構文</span><span class="sxs-lookup"><span data-stu-id="f6b8b-104">Syntax</span></span>  
  
```  
HRESULT Next();  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f6b8b-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f6b8b-105">Parameters</span></span>  
 <span data-ttu-id="f6b8b-106">なし。</span><span class="sxs-lookup"><span data-stu-id="f6b8b-106">None.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f6b8b-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="f6b8b-107">Return Value</span></span>  
 <span data-ttu-id="f6b8b-108">アンワインドが正常に発生した場合は `S_OK`、フレームがないためにアンワインドが完了できなかった場合は `CORDBG_S_AT_END_OF_STACK`。</span><span class="sxs-lookup"><span data-stu-id="f6b8b-108">`S_OK` if the unwind occurred successfully, or `CORDBG_S_AT_END_OF_STACK` if the unwind cannot be completed because there are no more frames.</span></span>  
  
 <span data-ttu-id="f6b8b-109">失敗を示す HRESULT が返される場合、ICorDebug API は `CORDBG_E_DATA_TARGET_ERROR` を返します。</span><span class="sxs-lookup"><span data-stu-id="f6b8b-109">If a failing HRESULT is returned, ICorDebug APIs will return `CORDBG_E_DATA_TARGET_ERROR`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f6b8b-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="f6b8b-110">Remarks</span></span>  
 <span data-ttu-id="f6b8b-111">スタック ウォーカーにより、前へ進んでいることが確認されます。これにより、最終的に `Next` の呼び出しによって、失敗を示す HRESULT または `CORDBG_S_AT_END_OF_STACK` が返されます。</span><span class="sxs-lookup"><span data-stu-id="f6b8b-111">The stack walker should ensure that it makes forward progress, so that eventually a call to `Next` will return a failing HRESULT or `CORDBG_S_AT_END_OF_STACK`.</span></span> <span data-ttu-id="f6b8b-112">返す`S_OK`無期限に無限ループが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f6b8b-112">Returning `S_OK` indefinitely may cause an infinite loop.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f6b8b-113">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="f6b8b-113">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f6b8b-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="f6b8b-114">Requirements</span></span>  
 <span data-ttu-id="f6b8b-115">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f6b8b-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f6b8b-116">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f6b8b-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f6b8b-117">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f6b8b-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f6b8b-118">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f6b8b-118">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6b8b-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="f6b8b-119">See also</span></span>
- [<span data-ttu-id="f6b8b-120">ICorDebugMemoryBuffer インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f6b8b-120">ICorDebugMemoryBuffer Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md)
- [<span data-ttu-id="f6b8b-121">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f6b8b-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
