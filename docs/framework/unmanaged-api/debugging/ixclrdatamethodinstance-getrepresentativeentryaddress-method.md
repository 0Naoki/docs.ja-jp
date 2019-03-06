---
title: IXCLRDataMethodInstance::GetRepresentativeEntryAddress メソッド
ms.date: 02/01/2019
api.name:
- IXCLRDataMethodInstance::GetRepresentativeEntryAddress
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataMethodInstance::GetRepresentativeEntryAddress
helpviewer.keywords:
- IXCLRDataMethodInstance::GetRepresentativeEntryAddress Method [.NET Framework debugging]
topic_type:
- apiref
author: hoyosjs
ms.author: juhoyosa
ms.openlocfilehash: 6f204e2ed9cb1409d53432355467bb11946f8809
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57372452"
---
# <a name="ixclrdatamethodinstancegetrepresentativeentryaddress-method"></a><span data-ttu-id="5a90a-102">IXCLRDataMethodInstance::GetRepresentativeEntryAddress メソッド</span><span class="sxs-lookup"><span data-stu-id="5a90a-102">IXCLRDataMethodInstance::GetRepresentativeEntryAddress Method</span></span>

<span data-ttu-id="5a90a-103">メソッドのエントリ ポイントは、すべてのネイティブ コンパイルの最も代表的なエントリ ポイントのアドレスを取得します。</span><span class="sxs-lookup"><span data-stu-id="5a90a-103">Gets the most representative entry point address for the native compilation of all the possible entry points for a method.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="5a90a-104">構文</span><span class="sxs-lookup"><span data-stu-id="5a90a-104">Syntax</span></span>

```
HRESULT GetRepresentativeEntryAddress(
    [out] CLRDATA_ADDRESS* addr
);
```

## <a name="parameters"></a><span data-ttu-id="5a90a-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5a90a-105">Parameters</span></span>

`addr`\
<span data-ttu-id="5a90a-106">[out]メソッドの最も代表的なネイティブ エントリ ポイントのアドレス。</span><span class="sxs-lookup"><span data-stu-id="5a90a-106">[out] The address of the most representative native entry point for the method.</span></span>

## <a name="remarks"></a><span data-ttu-id="5a90a-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="5a90a-107">Remarks</span></span>

<span data-ttu-id="5a90a-108">指定されたメソッドは、 [ `IXCLRDataMethodInstance`インターフェイス](ixclrdatamethodinstance-interface.md)仮想メソッド テーブルの 19 のスロットに対応しています。</span><span class="sxs-lookup"><span data-stu-id="5a90a-108">The provided method is part of the [`IXCLRDataMethodInstance` interface](ixclrdatamethodinstance-interface.md) and corresponds to the 19th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="5a90a-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="5a90a-109">Requirements</span></span>

<span data-ttu-id="5a90a-110">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a90a-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="5a90a-111">**ヘッダー:** なし</span><span class="sxs-lookup"><span data-stu-id="5a90a-111">**Header:** None</span></span>  
<span data-ttu-id="5a90a-112">**ライブラリ:** なし</span><span class="sxs-lookup"><span data-stu-id="5a90a-112">**Library:** None</span></span>  
<span data-ttu-id="5a90a-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="5a90a-113">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="5a90a-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="5a90a-114">See also</span></span>

- [<span data-ttu-id="5a90a-115">デバッグ</span><span class="sxs-lookup"><span data-stu-id="5a90a-115">Debugging</span></span>](index.md)
- [<span data-ttu-id="5a90a-116">IXCLRDataMethodInstance インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5a90a-116">IXCLRDataMethodInstance Interface</span></span>](ixclrdatamethodinstance-interface.md)
