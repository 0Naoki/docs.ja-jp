---
title: ICorDebugVariableHome::GetSlotIndex メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetSlotIndex
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetSlotIndex
helpviewer_keywords:
- ICorDebugVariableHome::GetSlotIndex method [.NET Framework debugging]
- GetSlotIndex method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: 966da50d-5665-4fff-bf7b-1c72bbadd9a4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b819f1f02870a8a85a531d7d341cbaf488a1ccd6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59093755"
---
# <a name="icordebugvariablehomegetslotindex-method"></a><span data-ttu-id="d0b57-102">ICorDebugVariableHome::GetSlotIndex メソッド</span><span class="sxs-lookup"><span data-stu-id="d0b57-102">ICorDebugVariableHome::GetSlotIndex Method</span></span>
<span data-ttu-id="d0b57-103">ローカル変数のマネージ スロット インデックスを取得します。</span><span class="sxs-lookup"><span data-stu-id="d0b57-103">Gets the managed slot-index of a local variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0b57-104">構文</span><span class="sxs-lookup"><span data-stu-id="d0b57-104">Syntax</span></span>  
  
```  
HRESULT GetSlotIndex(  
    [out] ULONG32 *pSlotIndex  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d0b57-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d0b57-105">Parameters</span></span>  
 `pSlotIndex`  
 <span data-ttu-id="d0b57-106">[out]ローカル変数のスロット インデックスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="d0b57-106">[out] A pointer to the slot-index of a local variable.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d0b57-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="d0b57-107">Return Value</span></span>  
 <span data-ttu-id="d0b57-108">メソッドは、次の値を返します。</span><span class="sxs-lookup"><span data-stu-id="d0b57-108">The method returns the following values.</span></span>  
  
|<span data-ttu-id="d0b57-109">[値]</span><span class="sxs-lookup"><span data-stu-id="d0b57-109">Value</span></span>|<span data-ttu-id="d0b57-110">説明</span><span class="sxs-lookup"><span data-stu-id="d0b57-110">Description</span></span>|  
|-----------|-----------------|  
|`S_OK`|<span data-ttu-id="d0b57-111">メソッドの呼び出しでのスロット インデックス値が返されました`pSlotIndex`します。</span><span class="sxs-lookup"><span data-stu-id="d0b57-111">The method call returned a slot-index value in `pSlotIndex`.</span></span>|  
|`E_FAIL`|<span data-ttu-id="d0b57-112">現在[ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)インスタンスは、関数の引数を表します。</span><span class="sxs-lookup"><span data-stu-id="d0b57-112">The current [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) instance represents a function argument.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d0b57-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="d0b57-113">Remarks</span></span>  
 <span data-ttu-id="d0b57-114">スロット インデックスは、このローカル変数のメタデータの取得に使用できます。</span><span class="sxs-lookup"><span data-stu-id="d0b57-114">The slot-index can be used to retrieve the metadata for this local variable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d0b57-115">必要条件</span><span class="sxs-lookup"><span data-stu-id="d0b57-115">Requirements</span></span>  
 <span data-ttu-id="d0b57-116">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0b57-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d0b57-117">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d0b57-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d0b57-118">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d0b57-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d0b57-119">**.NET Framework のバージョン:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d0b57-119">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0b57-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="d0b57-120">See also</span></span>

- [<span data-ttu-id="d0b57-121">ICorDebugVariableHome インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d0b57-121">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
