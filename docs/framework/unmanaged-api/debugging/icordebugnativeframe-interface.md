---
title: ICorDebugNativeFrame Interface1
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame
helpviewer_keywords:
- ICorDebugNativeFrame interface [.NET Framework debugging]
ms.assetid: 04819c58-7246-4b32-befb-680cf1dbc436
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c923b54f791cd8ff794538d4687ca0329e62c87e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54547028"
---
# <a name="icordebugnativeframe-interface1"></a><span data-ttu-id="34b3d-102">ICorDebugNativeFrame Interface1</span><span class="sxs-lookup"><span data-stu-id="34b3d-102">ICorDebugNativeFrame Interface1</span></span>
<span data-ttu-id="34b3d-103">ネイティブ フレームで使用される ICorDebugFrame の特殊な実装です。</span><span class="sxs-lookup"><span data-stu-id="34b3d-103">A specialized implementation of ICorDebugFrame used for native frames.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="34b3d-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="34b3d-104">Methods</span></span>  
  
|<span data-ttu-id="34b3d-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="34b3d-105">Method</span></span>|<span data-ttu-id="34b3d-106">説明</span><span class="sxs-lookup"><span data-stu-id="34b3d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="34b3d-107">CanSetIP メソッド</span><span class="sxs-lookup"><span data-stu-id="34b3d-107">CanSetIP Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-cansetip-method.md)|<span data-ttu-id="34b3d-108">命令ポインターをネイティブ コードで指定されたオフセット位置に設定しても安全であるかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="34b3d-108">Gets a value that indicates whether it is safe to set the instruction pointer to the specified offset location in native code.</span></span>|  
|[<span data-ttu-id="34b3d-109">GetIP メソッド</span><span class="sxs-lookup"><span data-stu-id="34b3d-109">GetIP Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getip-method.md)|<span data-ttu-id="34b3d-110">ネイティブ コードには、スタック フレームのオフセットを取得します。</span><span class="sxs-lookup"><span data-stu-id="34b3d-110">Gets the stack frame's offset into native code.</span></span>|  
|[<span data-ttu-id="34b3d-111">GetLocalDoubleRegisterValue メソッド</span><span class="sxs-lookup"><span data-stu-id="34b3d-111">GetLocalDoubleRegisterValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocaldoubleregistervalue-method.md)|<span data-ttu-id="34b3d-112">引数またはネイティブ フレームの 2 つのメモリ レジスタに格納されているローカル変数の値を表す ICorDebugValue へのポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="34b3d-112">Gets a pointer to an ICorDebugValue that represents the value of an argument or local variable stored in two memory registers of a native frame.</span></span>|  
|[<span data-ttu-id="34b3d-113">GetLocalMemoryRegisterValue メソッド</span><span class="sxs-lookup"><span data-stu-id="34b3d-113">GetLocalMemoryRegisterValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocalmemoryregistervalue-method.md)|<span data-ttu-id="34b3d-114">ポインターを取得、`ICorDebugValue`うち下位ビットが指定されたレジスタに格納されている、上位ビットが指定されたメモリ アドレスに格納されている、ローカル変数の値を表します。</span><span class="sxs-lookup"><span data-stu-id="34b3d-114">Gets a pointer to an `ICorDebugValue` that represents the value of a local variable, of which the low bits are stored in the specified register and the high bits are stored at the specified memory address.</span></span>|  
|[<span data-ttu-id="34b3d-115">GetLocalMemoryValue メソッド</span><span class="sxs-lookup"><span data-stu-id="34b3d-115">GetLocalMemoryValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocalmemoryvalue-method.md)|<span data-ttu-id="34b3d-116">ポインターを取得、`ICorDebugValue`を表す、指定されたメモリ アドレスに格納されているローカル変数の値。</span><span class="sxs-lookup"><span data-stu-id="34b3d-116">Gets a pointer to an `ICorDebugValue` that represents the value of a local variable stored at the specified memory address.</span></span>|  
|[<span data-ttu-id="34b3d-117">GetLocalRegisterMemoryValue メソッド</span><span class="sxs-lookup"><span data-stu-id="34b3d-117">GetLocalRegisterMemoryValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocalregistermemoryvalue-method.md)|<span data-ttu-id="34b3d-118">ポインターを取得、`ICorDebugValue`うち上位ビットが指定されたレジスタに格納されているし、指定されたメモリ アドレスの下位ビットが格納されている、ローカル変数の値を表す</span><span class="sxs-lookup"><span data-stu-id="34b3d-118">Gets a pointer to an `ICorDebugValue` that represents the value of a local variable, of which the high bits are stored in the specified register and the low bits are stored at the specified memory address</span></span>|  
|[<span data-ttu-id="34b3d-119">GetLocalRegisterValue メソッド</span><span class="sxs-lookup"><span data-stu-id="34b3d-119">GetLocalRegisterValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocalregistervalue-method.md)|<span data-ttu-id="34b3d-120">ポインターを取得、`ICorDebugValue`引数または指定されたネイティブ レジスタに格納されているローカル変数の値を表します。</span><span class="sxs-lookup"><span data-stu-id="34b3d-120">Gets a pointer to an `ICorDebugValue` that represents the value of an argument or a local variable stored in the specified native register.</span></span>|  
|[<span data-ttu-id="34b3d-121">GetRegisterSet メソッド</span><span class="sxs-lookup"><span data-stu-id="34b3d-121">GetRegisterSet Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getregisterset-method.md)|<span data-ttu-id="34b3d-122">ポインターを取得、 [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)これのレジスタ セットを表す`ICorDebugNativeFrame`します。</span><span class="sxs-lookup"><span data-stu-id="34b3d-122">Gets a pointer to an [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) that represents the register set for this `ICorDebugNativeFrame`.</span></span>|  
|[<span data-ttu-id="34b3d-123">SetIP メソッド</span><span class="sxs-lookup"><span data-stu-id="34b3d-123">SetIP Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-setip-method.md)|<span data-ttu-id="34b3d-124">命令ポインターをネイティブ コードで指定されたオフセット位置に設定します。</span><span class="sxs-lookup"><span data-stu-id="34b3d-124">Sets the instruction pointer to the specified offset location in native code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="34b3d-125">Remarks</span><span class="sxs-lookup"><span data-stu-id="34b3d-125">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="34b3d-126">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="34b3d-126">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="34b3d-127">必要条件</span><span class="sxs-lookup"><span data-stu-id="34b3d-127">Requirements</span></span>  
 <span data-ttu-id="34b3d-128">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="34b3d-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="34b3d-129">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="34b3d-129">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="34b3d-130">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="34b3d-130">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="34b3d-131">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="34b3d-131">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34b3d-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="34b3d-132">See also</span></span>
- [<span data-ttu-id="34b3d-133">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="34b3d-133">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
