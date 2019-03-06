---
title: ICorDebugVariableHome::GetArgumentIndex メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetArgumentIndex
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetArgumentIndex
helpviewer_keywords:
- ICorDebugVariableHome::GetArgumentIndex method [.NET Framework debugging]
- GetArgumentIndex method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: e86fcc72-388d-4009-ab21-8f9c3323e9a3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2457dff3063e47f1fb9d040caac1bc08441e1739
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57366830"
---
# <a name="icordebugvariablehomegetargumentindex-method"></a><span data-ttu-id="25e8b-102">ICorDebugVariableHome::GetArgumentIndex メソッド</span><span class="sxs-lookup"><span data-stu-id="25e8b-102">ICorDebugVariableHome::GetArgumentIndex Method</span></span>

<span data-ttu-id="25e8b-103">関数の引数のインデックスを取得します。</span><span class="sxs-lookup"><span data-stu-id="25e8b-103">Gets the index of a function argument.</span></span>

## <a name="syntax"></a><span data-ttu-id="25e8b-104">構文</span><span class="sxs-lookup"><span data-stu-id="25e8b-104">Syntax</span></span>

```cpp
HRESULT GetArgumentIndex(
    [out] ULONG32* pArgumentIndex
);
```

## <a name="parameters"></a><span data-ttu-id="25e8b-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="25e8b-105">Parameters</span></span>

`pArgumentIndex`\
<span data-ttu-id="25e8b-106">[out]引数のインデックスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="25e8b-106">[out] A pointer to the argument index.</span></span>

## <a name="return-value"></a><span data-ttu-id="25e8b-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="25e8b-107">Return Value</span></span>

<span data-ttu-id="25e8b-108">メソッドは、次の値を返します。</span><span class="sxs-lookup"><span data-stu-id="25e8b-108">The method returns the following values.</span></span>

|<span data-ttu-id="25e8b-109">[値]</span><span class="sxs-lookup"><span data-stu-id="25e8b-109">Value</span></span>|<span data-ttu-id="25e8b-110">説明</span><span class="sxs-lookup"><span data-stu-id="25e8b-110">Description</span></span>|
|-----------|-----------------|
|`S_OK`|<span data-ttu-id="25e8b-111">メソッドの呼び出しには、有効な引数のインデックスが返されます。</span><span class="sxs-lookup"><span data-stu-id="25e8b-111">The method call returned a valid argument index.</span></span>|
|`E_FAIL`|<span data-ttu-id="25e8b-112">現在[ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)インスタンスがローカル変数を表します。</span><span class="sxs-lookup"><span data-stu-id="25e8b-112">The current [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) instance represents a local variable.</span></span>|

## <a name="remarks"></a><span data-ttu-id="25e8b-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="25e8b-113">Remarks</span></span>

<span data-ttu-id="25e8b-114">この引数のメタデータを取得する引数のインデックスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="25e8b-114">The argument index can be used to retrieve metadata for this argument.</span></span>

## <a name="requirements"></a><span data-ttu-id="25e8b-115">必要条件</span><span class="sxs-lookup"><span data-stu-id="25e8b-115">Requirements</span></span>

<span data-ttu-id="25e8b-116">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="25e8b-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="25e8b-117">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="25e8b-117">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="25e8b-118">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="25e8b-118">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="25e8b-119">**.NET Framework のバージョン:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="25e8b-119">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="25e8b-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="25e8b-120">See also</span></span>

- [<span data-ttu-id="25e8b-121">ICorDebugVariableHome インターフェイス</span><span class="sxs-lookup"><span data-stu-id="25e8b-121">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
