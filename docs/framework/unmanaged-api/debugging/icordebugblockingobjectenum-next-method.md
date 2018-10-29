---
title: ICorDebugBlockingObjectEnum::Next メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugBlockingObjectEnum.Next Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBlockingObjectEnum::Next
helpviewer_keywords:
- Next method, ICorDebugBlockingObjectEnum interface [.NET Framework debugging]
- ICorDebugBlockingObjectEnum::Next method [.NET Framework debugging]
ms.assetid: 0121753f-ebea-48d0-aeb2-ed7fda76dc60
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 04b28dec0f016d44692665fb0ce95a7e496f103c
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/28/2018
ms.locfileid: "50200523"
---
# <a name="icordebugblockingobjectenumnext-method"></a><span data-ttu-id="9035b-102">ICorDebugBlockingObjectEnum::Next メソッド</span><span class="sxs-lookup"><span data-stu-id="9035b-102">ICorDebugBlockingObjectEnum::Next Method</span></span>
<span data-ttu-id="9035b-103">指定した数を取得[CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md)列挙体の現在位置からのオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="9035b-103">Gets the specified number of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) objects from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9035b-104">構文</span><span class="sxs-lookup"><span data-stu-id="9035b-104">Syntax</span></span>  
  
```  
HRESULT Next([in] ULONG  celt,  
             [out, size_is(celt), length_is(*pceltFetched)]  
                           CorDebugBlockingObject values[],  
             [out] ULONG *pceltFetched;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9035b-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="9035b-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="9035b-106">[in]取得するオブジェクトの数。</span><span class="sxs-lookup"><span data-stu-id="9035b-106">[in] The number of objects to retrieve.</span></span>  
  
 `values`  
 <span data-ttu-id="9035b-107">[out]ポインターの配列[CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md)オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="9035b-107">[out] An array of pointers to [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) objects.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="9035b-108">[out]取得されたオブジェクトの数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="9035b-108">[out] A pointer to the number of objects that were retrieved.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9035b-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="9035b-109">Return Value</span></span>  
 <span data-ttu-id="9035b-110">このメソッドは、次の特定の HRESULT を返します。</span><span class="sxs-lookup"><span data-stu-id="9035b-110">This method returns the following specific HRESULTs.</span></span>  
  
|<span data-ttu-id="9035b-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9035b-111">HRESULT</span></span>|<span data-ttu-id="9035b-112">説明</span><span class="sxs-lookup"><span data-stu-id="9035b-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9035b-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="9035b-113">S_OK</span></span>|<span data-ttu-id="9035b-114">メソッドは正常に完了しました。</span><span class="sxs-lookup"><span data-stu-id="9035b-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="9035b-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="9035b-115">S_FALSE</span></span>|<span data-ttu-id="9035b-116">`pceltFetched` は `celt` と一致しません。</span><span class="sxs-lookup"><span data-stu-id="9035b-116">`pceltFetched` does not equal `celt`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9035b-117">Remarks</span><span class="sxs-lookup"><span data-stu-id="9035b-117">Remarks</span></span>  
 <span data-ttu-id="9035b-118">このメソッドが機能などの一般的な COM の列挙子。</span><span class="sxs-lookup"><span data-stu-id="9035b-118">This method functions like a typical COM enumerator.</span></span>  
  
 <span data-ttu-id="9035b-119">入力配列の値は以上である必要がありますサイズの`celt`します。</span><span class="sxs-lookup"><span data-stu-id="9035b-119">The input array values must be at least of size `celt`.</span></span> <span data-ttu-id="9035b-120">配列で塗りつぶされますか、[次へ]`celt`値よりも少ない場合は列挙体で、または残りのすべての値を持つ`celt`ままにします。</span><span class="sxs-lookup"><span data-stu-id="9035b-120">The array will be filled with either the next `celt` values in the enumeration or with all remaining values if fewer than `celt` remain.</span></span> <span data-ttu-id="9035b-121">このメソッドが戻るとき`pceltFetched`取得された値の数で塗りつぶされます。</span><span class="sxs-lookup"><span data-stu-id="9035b-121">When this method returns, `pceltFetched` will be filled with the number of values that were retrieved.</span></span> <span data-ttu-id="9035b-122">場合`values`無効なポインターが格納または未満であるバッファーを指す`celt`、または`pceltFetched`無効なポインターが、結果は未定義です。</span><span class="sxs-lookup"><span data-stu-id="9035b-122">If `values` contains invalid pointers or points to a buffer that is smaller than `celt`, or if `pceltFetched` is an invalid pointer, the result is undefined.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9035b-123">ただし、 [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md)構造体を解放する必要はありません、その内部に"ICorDebugValue"インターフェイスが解放する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9035b-123">Although the [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structure does not need to be released, the "ICorDebugValue" interface inside of it does need to be released.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9035b-124">必要条件</span><span class="sxs-lookup"><span data-stu-id="9035b-124">Requirements</span></span>  
 <span data-ttu-id="9035b-125">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9035b-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9035b-126">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9035b-126">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9035b-127">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9035b-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9035b-128">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9035b-128">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9035b-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="9035b-129">See Also</span></span>  
 [<span data-ttu-id="9035b-130">ICorDebugDataTarget インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9035b-130">ICorDebugDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)  
 [<span data-ttu-id="9035b-131">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9035b-131">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="9035b-132">デバッグ</span><span class="sxs-lookup"><span data-stu-id="9035b-132">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
