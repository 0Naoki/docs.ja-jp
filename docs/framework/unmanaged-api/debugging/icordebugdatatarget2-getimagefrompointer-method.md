---
title: ICorDebugDataTarget2::GetImageFromPointer メソッド
ms.date: 03/30/2017
ms.assetid: 939cabe1-b647-4090-b662-eeec23c6c58d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 64affd9b262934316fc904b10f1a9c4a7e7657bb
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54539975"
---
# <a name="icordebugdatatarget2getimagefrompointer-method"></a><span data-ttu-id="2d33e-102">ICorDebugDataTarget2::GetImageFromPointer メソッド</span><span class="sxs-lookup"><span data-stu-id="2d33e-102">ICorDebugDataTarget2::GetImageFromPointer Method</span></span>
<span data-ttu-id="2d33e-103">モジュールのアドレスから、そのモジュールのベース アドレスとサイズを返します。</span><span class="sxs-lookup"><span data-stu-id="2d33e-103">Returns the module base address and size from an address in that module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d33e-104">構文</span><span class="sxs-lookup"><span data-stu-id="2d33e-104">Syntax</span></span>  
  
```  
HRESULT GetImageFromPointer(  
   [in] CORDB_ADDRESS addr,   
   [out] CORDB_ADDRESS *pImageBase,   
   [out] ULONG32 *pSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2d33e-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2d33e-105">Parameters</span></span>  
 `addr`  
 <span data-ttu-id="2d33e-106">A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md)モジュール内のアドレスを表す値です。</span><span class="sxs-lookup"><span data-stu-id="2d33e-106">A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) value that represents an address in a module.</span></span>  
  
 `pImageBase`  
 <span data-ttu-id="2d33e-107">[out]A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md)モジュールのベース アドレスを表す値です。</span><span class="sxs-lookup"><span data-stu-id="2d33e-107">[out] A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) value that represents the module's base address.</span></span>  
  
 `pSize`  
 <span data-ttu-id="2d33e-108">モジュールのサイズへのポインター。</span><span class="sxs-lookup"><span data-stu-id="2d33e-108">A pointer to the module size.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2d33e-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="2d33e-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2d33e-110">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="2d33e-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2d33e-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="2d33e-111">Requirements</span></span>  
 <span data-ttu-id="2d33e-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2d33e-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2d33e-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2d33e-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2d33e-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2d33e-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2d33e-115">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2d33e-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d33e-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="2d33e-116">See also</span></span>
- [<span data-ttu-id="2d33e-117">ICorDebugDataTarget2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2d33e-117">ICorDebugDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-interface.md)
- [<span data-ttu-id="2d33e-118">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2d33e-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
