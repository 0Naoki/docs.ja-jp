---
title: ISOSDacInterface::GetMethodDescPtrFromIP メソッド
ms.date: 02/01/2019
api.name:
- ISOSDacInterface::GetMethodDescPtrFromIP Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- ISOSDacInterface::GetMethodDescPtrFromIP Method
helpviewer.keywords:
- ISOSDacInterface::GetMethodDescPtrFromIP Method [.NET Framework debugging]
topic_type:
- apiref
author: hoyosjs
ms.author: juhoyosa
ms.openlocfilehash: 82c4531ac16e8b4bf7ac45bc01eb7128b9507ab5
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57358536"
---
# <a name="isosdacinterfacegetmethoddescptrfromip-method"></a><span data-ttu-id="2b056-102">ISOSDacInterface::GetMethodDescPtrFromIP メソッド</span><span class="sxs-lookup"><span data-stu-id="2b056-102">ISOSDacInterface::GetMethodDescPtrFromIP Method</span></span>

<span data-ttu-id="2b056-103">指定されたネイティブ命令のアドレスを含むメソッドに対応する MethodDesc ポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="2b056-103">Retrieves the pointer of the MethodDesc corresponding the method containing the given native instruction address.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="2b056-104">構文</span><span class="sxs-lookup"><span data-stu-id="2b056-104">Syntax</span></span>

```
HRESULT GetMethodDescPtrFromIP(
    CLRDATA_ADDRESS ip,
    CLRDATA_ADDRESS * ppMD
);
```

## <a name="parameters"></a><span data-ttu-id="2b056-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2b056-105">Parameters</span></span>

`ip`\
<span data-ttu-id="2b056-106">[in]実行時に、メソッド内のアドレス。</span><span class="sxs-lookup"><span data-stu-id="2b056-106">[in] An address within the method at runtime.</span></span>

`ppMD`\
<span data-ttu-id="2b056-107">[out]アドレス、`MethodDesc`の特定のメソッド。</span><span class="sxs-lookup"><span data-stu-id="2b056-107">[out] The address of the `MethodDesc` for the particular method.</span></span>

## <a name="remarks"></a><span data-ttu-id="2b056-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="2b056-108">Remarks</span></span>

<span data-ttu-id="2b056-109">指定されたメソッドは、 [ `ISOSDacInterface`インターフェイス](isosdacinterface-interface.md)21 のスロットの仮想メソッド テーブルに対応しています。</span><span class="sxs-lookup"><span data-stu-id="2b056-109">The provided method is part of the [`ISOSDacInterface` interface](isosdacinterface-interface.md) and corresponds to the 21st slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="2b056-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="2b056-110">Requirements</span></span>

<span data-ttu-id="2b056-111">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2b056-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="2b056-112">**ヘッダー:** なし</span><span class="sxs-lookup"><span data-stu-id="2b056-112">**Header:** None</span></span>  
<span data-ttu-id="2b056-113">**ライブラリ:** なし</span><span class="sxs-lookup"><span data-stu-id="2b056-113">**Library:** None</span></span>  
<span data-ttu-id="2b056-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="2b056-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="2b056-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="2b056-115">See also</span></span>

- [<span data-ttu-id="2b056-116">デバッグ</span><span class="sxs-lookup"><span data-stu-id="2b056-116">Debugging</span></span>](index.md)
- [<span data-ttu-id="2b056-117">ISOSDacInterface インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2b056-117">ISOSDacInterface Interface</span></span>](isosdacinterface-interface.md)