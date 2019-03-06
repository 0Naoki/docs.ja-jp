---
title: IXCLRDataMethodInstance::GetILAddressMap メソッド
ms.date: 01/16/2019
api.name:
- IXCLRDataMethodInstance::GetILAddressMap Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataMethodInstance::GetILAddressMap Method
helpviewer.keywords:
- IXCLRDataMethodInstance::GetILAddressMap Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: e88897342bf18111ebd4914948ab45085c35ea08
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57484122"
---
# <a name="ixclrdatamethodinstancegetiladdressmap-method"></a><span data-ttu-id="e4d12-102">IXCLRDataMethodInstance::GetILAddressMap メソッド</span><span class="sxs-lookup"><span data-stu-id="e4d12-102">IXCLRDataMethodInstance::GetILAddressMap Method</span></span>

<span data-ttu-id="e4d12-103">アドレスのマッピング情報の IL を取得します。</span><span class="sxs-lookup"><span data-stu-id="e4d12-103">Gets the IL to address mapping information.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="e4d12-104">構文</span><span class="sxs-lookup"><span data-stu-id="e4d12-104">Syntax</span></span>

```
HRESULT GetILAddressMap(
    [in] ULONG32                                   mapLen,
    [out] ULONG32                                 *mapNeeded,
    [out, size_is(mapLen)] CLRDATA_IL_ADDRESS_MAP  maps[]
);
```

## <a name="parameters"></a><span data-ttu-id="e4d12-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e4d12-105">Parameters</span></span>

`mapLen`\
<span data-ttu-id="e4d12-106">[in]マップの指定された配列の長さ。</span><span class="sxs-lookup"><span data-stu-id="e4d12-106">[in] The length of the provided maps array.</span></span>

`mapNeeded`\
<span data-ttu-id="e4d12-107">[out]メソッドが必要なマップ エントリの数。</span><span class="sxs-lookup"><span data-stu-id="e4d12-107">[out] The number of map entries that the method needs.</span></span>

`maps`\
<span data-ttu-id="e4d12-108">[out, size_is(mapLen)]マップ エントリを格納する配列。</span><span class="sxs-lookup"><span data-stu-id="e4d12-108">[out, size_is(mapLen)] The array for storing the map entries.</span></span>

## <a name="remarks"></a><span data-ttu-id="e4d12-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="e4d12-109">Remarks</span></span>

<span data-ttu-id="e4d12-110">指定されたメソッドは、`IXCLRDataMethodInstance`インターフェイスし、仮想メソッド テーブルの 14 のスロットに対応しています。</span><span class="sxs-lookup"><span data-stu-id="e4d12-110">The provided method is part of the `IXCLRDataMethodInstance` interface and corresponds to the 14th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="e4d12-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="e4d12-111">Requirements</span></span>

<span data-ttu-id="e4d12-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e4d12-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="e4d12-113">**ヘッダー:** なし</span><span class="sxs-lookup"><span data-stu-id="e4d12-113">**Header:** None</span></span>  
<span data-ttu-id="e4d12-114">**ライブラリ:** なし</span><span class="sxs-lookup"><span data-stu-id="e4d12-114">**Library:** None</span></span>  
<span data-ttu-id="e4d12-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="e4d12-115">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="e4d12-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="e4d12-116">See also</span></span>

- [<span data-ttu-id="e4d12-117">デバッグ</span><span class="sxs-lookup"><span data-stu-id="e4d12-117">Debugging</span></span>](index.md)
- [<span data-ttu-id="e4d12-118">IXCLRDataMethodInstance インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e4d12-118">IXCLRDataMethodInstance Interface</span></span>](ixclrdatamethodinstance-interface.md)
