---
title: ICorDebugVariableSymbol::GetSlotIndex メソッド
ms.date: 03/30/2017
ms.assetid: 09c19f5f-afc4-4e0c-bffe-cd7147bc7a43
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 09b50af49f8379539773d2000a6c1f8222fee875
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54563835"
---
# <a name="icordebugvariablesymbolgetslotindex-method"></a><span data-ttu-id="b0607-102">ICorDebugVariableSymbol::GetSlotIndex メソッド</span><span class="sxs-lookup"><span data-stu-id="b0607-102">ICorDebugVariableSymbol::GetSlotIndex Method</span></span>
<span data-ttu-id="b0607-103">ローカル変数のマネージド スロット インデックスを取得します。</span><span class="sxs-lookup"><span data-stu-id="b0607-103">Gets the managed slot index of a local variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0607-104">構文</span><span class="sxs-lookup"><span data-stu-id="b0607-104">Syntax</span></span>  
  
```  
HRESULT GetSlotIndex(  
   [out] ULONG32 *pSlotIndex  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b0607-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b0607-105">Parameters</span></span>  
 `pSlotIndex`  
 <span data-ttu-id="b0607-106">[out] ローカル変数のスロット インデックスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="b0607-106">[out] A pointer to the local variable's slot index.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b0607-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="b0607-107">Return Value</span></span>  
 <span data-ttu-id="b0607-108">正常終了した場合は、`S_OK`。</span><span class="sxs-lookup"><span data-stu-id="b0607-108">`S_OK` if successful.</span></span> <span data-ttu-id="b0607-109">変数が関数引数の場合は `E_FAIL`。</span><span class="sxs-lookup"><span data-stu-id="b0607-109">`E_FAIL` if the variable is a function argument.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b0607-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="b0607-110">Remarks</span></span>  
 <span data-ttu-id="b0607-111">ローカル変数のマネージド スロット インデックスを使用すると、変数のメタデータ情報を取得できます。</span><span class="sxs-lookup"><span data-stu-id="b0607-111">The managed slot index of a local variable can be used to retrieve the variable's metadata information</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b0607-112">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="b0607-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b0607-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="b0607-113">Requirements</span></span>  
 <span data-ttu-id="b0607-114">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b0607-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b0607-115">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b0607-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b0607-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b0607-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b0607-117">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b0607-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0607-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="b0607-118">See also</span></span>
- [<span data-ttu-id="b0607-119">ICorDebugVariableSymbol インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b0607-119">ICorDebugVariableSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md)
- [<span data-ttu-id="b0607-120">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b0607-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
