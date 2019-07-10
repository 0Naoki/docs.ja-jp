---
title: ICorDebugGuidToTypeEnum::Next メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugGuidToTypeEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGuidToTypeEnum::Next
helpviewer_keywords:
- ICorDebugGuidToTypeEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugGuidToTypeEnum interface [.NET Framework debugging]
ms.assetid: c9937666-8e18-484d-9fe0-b9ac95199530
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9f334b4a28b0573fa938c2fda340c0c03175ff18
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67756883"
---
# <a name="icordebugguidtotypeenumnext-method"></a><span data-ttu-id="ad07c-102">ICorDebugGuidToTypeEnum::Next メソッド</span><span class="sxs-lookup"><span data-stu-id="ad07c-102">ICorDebugGuidToTypeEnum::Next Method</span></span>
<span data-ttu-id="ad07c-103">指定した数を取得[CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md)インスタンス情報を入力する Guid にマップします。</span><span class="sxs-lookup"><span data-stu-id="ad07c-103">Gets the specified number of [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) instances that map GUIDs to type information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad07c-104">構文</span><span class="sxs-lookup"><span data-stu-id="ad07c-104">Syntax</span></span>  
  
```cpp  
HRESULT Next(  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched] CorDebugGuidToTypeMapping values[  ],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ad07c-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ad07c-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="ad07c-106">[in]取得する GUID 型への対応付けオブジェクトの数。</span><span class="sxs-lookup"><span data-stu-id="ad07c-106">[in] The number of GUID-to-type mapping objects to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="ad07c-107">[out]それぞれが指すポインターの配列を[CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) Windows ランタイムの GUID を対応する ICorDebugType オブジェクトにマップするオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="ad07c-107">[out] An array of pointers, each of which points to a [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) object that maps a Windows Runtime GUID to its corresponding ICorDebugType object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="ad07c-108">[out]数へのポインター [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md)で実際に返されるオブジェクト`values`します。</span><span class="sxs-lookup"><span data-stu-id="ad07c-108">[out] A pointer to the number of [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) objects actually returned in `values`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ad07c-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="ad07c-109">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ad07c-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="ad07c-110">Requirements</span></span>  
 <span data-ttu-id="ad07c-111">**プラットフォーム:** Windows ランタイム</span><span class="sxs-lookup"><span data-stu-id="ad07c-111">**Platforms:** Windows Runtime</span></span>  
  
 <span data-ttu-id="ad07c-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ad07c-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ad07c-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ad07c-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ad07c-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ad07c-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad07c-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="ad07c-115">See also</span></span>

- [<span data-ttu-id="ad07c-116">ICorDebugGuidToTypeEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ad07c-116">ICorDebugGuidToTypeEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-interface.md)
- [<span data-ttu-id="ad07c-117">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ad07c-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
