---
title: IXCLRDataProcess::StartEnumMethodInstancesByAddress メソッド
ms.date: 01/16/2019
api.name:
- IXCLRDataProcess::StartEnumMethodInstancesByAddress Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess::StartEnumMethodInstancesByAddress Method
helpviewer.keywords:
- IXCLRDataProcess::StartEnumMethodInstancesByAddress Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 8d0494e53705493de814ed4d4caa869e1e8a700f
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57374571"
---
# <a name="ixclrdataprocessstartenummethodinstancesbyaddress-method"></a><span data-ttu-id="b6fe3-102">IXCLRDataProcess::StartEnumMethodInstancesByAddress メソッド</span><span class="sxs-lookup"><span data-stu-id="b6fe3-102">IXCLRDataProcess::StartEnumMethodInstancesByAddress Method</span></span>

<span data-ttu-id="b6fe3-103">メソッドのインスタンスを列挙ハンドルを提供します`AppDomain`特定のアドレスで開始します。</span><span class="sxs-lookup"><span data-stu-id="b6fe3-103">Provides a handle to enumerate the method instances of `AppDomain` starting at a given address.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="b6fe3-104">構文</span><span class="sxs-lookup"><span data-stu-id="b6fe3-104">Syntax</span></span>

```
HRESULT StartEnumMethodInstancesByAddress(
    [in] CLRDATA_ADDRESS     address,
    [in] IXCLRDataAppDomain *appDomain,
    [out] CLRDATA_ENUM      *handle
);
```

### <a name="parameters"></a><span data-ttu-id="b6fe3-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b6fe3-105">Parameters</span></span>

`address`\
<span data-ttu-id="b6fe3-106">[in]メソッドの最初のインスタンスのアドレス。</span><span class="sxs-lookup"><span data-stu-id="b6fe3-106">[in] The address of the first method instance.</span></span>

`appDomain`\
<span data-ttu-id="b6fe3-107">[in]メソッド インスタンスのアプリケーション ドメイン。</span><span class="sxs-lookup"><span data-stu-id="b6fe3-107">[in] The AppDomain of the method instances.</span></span>

`handle`\
<span data-ttu-id="b6fe3-108">[out]メソッド インスタンスを列挙するためのハンドル。</span><span class="sxs-lookup"><span data-stu-id="b6fe3-108">[out] A handle for enumerating the method instances.</span></span>

## <a name="remarks"></a><span data-ttu-id="b6fe3-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="b6fe3-109">Remarks</span></span>

<span data-ttu-id="b6fe3-110">指定されたメソッドは、`IXCLRDataProcess`インターフェイスし、仮想メソッド テーブルの 27 のスロットに対応しています。</span><span class="sxs-lookup"><span data-stu-id="b6fe3-110">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 27th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="b6fe3-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="b6fe3-111">Requirements</span></span>

<span data-ttu-id="b6fe3-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b6fe3-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="b6fe3-113">**ヘッダー:** なし</span><span class="sxs-lookup"><span data-stu-id="b6fe3-113">**Header:** None</span></span>  
<span data-ttu-id="b6fe3-114">**ライブラリ:** なし</span><span class="sxs-lookup"><span data-stu-id="b6fe3-114">**Library:** None</span></span>  
<span data-ttu-id="b6fe3-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="b6fe3-115">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="b6fe3-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="b6fe3-116">See also</span></span>

- [<span data-ttu-id="b6fe3-117">CLRDataSourceType 列挙型</span><span class="sxs-lookup"><span data-stu-id="b6fe3-117">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="b6fe3-118">デバッグ</span><span class="sxs-lookup"><span data-stu-id="b6fe3-118">Debugging</span></span>](index.md)
- [<span data-ttu-id="b6fe3-119">IXCLRDataProcess インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b6fe3-119">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)
