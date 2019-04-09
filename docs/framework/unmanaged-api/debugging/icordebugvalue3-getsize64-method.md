---
title: ICorDebugValue3::GetSize64 メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugValue3::GetSize64
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue3::GetSize64
helpviewer_keywords:
- GetSize64 method, ICorDebugValue3 interface [.NET Framework debugging]
- ICorDebugValue3::GetSize64 method [.NET Framework debugging]
ms.assetid: fee56a29-3154-4192-958d-71da2ced3740
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7c0b45e08f7b88d9374023f95c6e3e22139c8949
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59144769"
---
# <a name="icordebugvalue3getsize64-method"></a><span data-ttu-id="979c1-102">ICorDebugValue3::GetSize64 メソッド</span><span class="sxs-lookup"><span data-stu-id="979c1-102">ICorDebugValue3::GetSize64 Method</span></span>
<span data-ttu-id="979c1-103">これのバイト単位のサイズを取得します。 [ICorDebugValue3](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md)オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="979c1-103">Gets the size, in bytes, of this [ICorDebugValue3](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="979c1-104">構文</span><span class="sxs-lookup"><span data-stu-id="979c1-104">Syntax</span></span>  
  
```  
HRESULT GetSize64(  
    [out] ULONG64 *pSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="979c1-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="979c1-105">Parameters</span></span>  
 <span data-ttu-id="979c1-106">pSize</span><span class="sxs-lookup"><span data-stu-id="979c1-106">pSize</span></span>  
 <span data-ttu-id="979c1-107">[out]このオブジェクトのバイト単位のサイズへのポインター。</span><span class="sxs-lookup"><span data-stu-id="979c1-107">[out] A pointer to the size, in bytes, of this object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="979c1-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="979c1-108">Remarks</span></span>  
 <span data-ttu-id="979c1-109">この値の型が参照型の場合は、このメソッドは、オブジェクトのサイズではなく、ポインターのサイズを返します。</span><span class="sxs-lookup"><span data-stu-id="979c1-109">If this value's type is a reference type, this method returns the size of the pointer rather than the size of the object.</span></span>  
  
 <span data-ttu-id="979c1-110">`ICorDebugValue3::GetSize`メソッドとは異なります、 [icordebugvalue::getsize](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getsize-method.md)出力パラメーターの型のメソッド。</span><span class="sxs-lookup"><span data-stu-id="979c1-110">The `ICorDebugValue3::GetSize` method differs from the [ICorDebugValue::GetSize](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getsize-method.md) method in the type of its output parameter.</span></span> <span data-ttu-id="979c1-111">[Icordebugvalue::getsize](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getsize-method.md)、出力パラメーターが、 `ULONG32`;`ICorDebugValue3::GetSize`は、`ULONG64`です。</span><span class="sxs-lookup"><span data-stu-id="979c1-111">In [ICorDebugValue::GetSize](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getsize-method.md), the output parameter is a `ULONG32`; in `ICorDebugValue3::GetSize`, it is a `ULONG64`.</span></span> <span data-ttu-id="979c1-112">これにより、 [ICorDebugValue3](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md) 2 GB を超える配列のサイズを報告するインターフェイス。</span><span class="sxs-lookup"><span data-stu-id="979c1-112">This enables the [ICorDebugValue3](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md) interface to report the size of arrays that exceed 2GB.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="979c1-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="979c1-113">Requirements</span></span>  
 <span data-ttu-id="979c1-114">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="979c1-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="979c1-115">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="979c1-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="979c1-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="979c1-116">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="979c1-117">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="979c1-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="979c1-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="979c1-118">See also</span></span>

- [<span data-ttu-id="979c1-119">ICorDebugValue3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="979c1-119">ICorDebugValue3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md)
- [<span data-ttu-id="979c1-120">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="979c1-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
