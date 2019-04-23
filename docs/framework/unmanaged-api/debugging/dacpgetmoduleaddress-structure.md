---
title: DacpGetModuleAddress 構造体
ms.date: 01/16/2019
api.name:
- DacpGetModuleAddress Structure
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- DacpGetModuleAddress Structure
helpviewer.keywords:
- DacpGetModuleAddress Structure [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: cbea6c0562c68ae5d18247dc97bc53eb9dfbfd7e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59104111"
---
# <a name="dacpgetmoduleaddress-structure"></a><span data-ttu-id="37a1c-102">DacpGetModuleAddress 構造体</span><span class="sxs-lookup"><span data-stu-id="37a1c-102">DacpGetModuleAddress Structure</span></span>

<span data-ttu-id="37a1c-103">モジュールのアドレスの要求のコンテナーを定義します。</span><span class="sxs-lookup"><span data-stu-id="37a1c-103">Defines the container for a module address request.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="37a1c-104">構文</span><span class="sxs-lookup"><span data-stu-id="37a1c-104">Syntax</span></span>

```
struct DacpGetModuleAddress
{
    CLRDATA_ADDRESS ModulePtr;
};
```

## <a name="members"></a><span data-ttu-id="37a1c-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="37a1c-105">Members</span></span>

| <span data-ttu-id="37a1c-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="37a1c-106">Member</span></span>      | <span data-ttu-id="37a1c-107">説明</span><span class="sxs-lookup"><span data-stu-id="37a1c-107">Description</span></span>                |
| ----------- | -------------------------- |
| `ModulePtr` | <span data-ttu-id="37a1c-108">モジュールへのポインター。</span><span class="sxs-lookup"><span data-stu-id="37a1c-108">The pointer to the module.</span></span> |

## <a name="methods"></a><span data-ttu-id="37a1c-109">メソッド</span><span class="sxs-lookup"><span data-stu-id="37a1c-109">Methods</span></span>

| <span data-ttu-id="37a1c-110">メソッド</span><span class="sxs-lookup"><span data-stu-id="37a1c-110">Method</span></span>                                                                                               | <span data-ttu-id="37a1c-111">説明</span><span class="sxs-lookup"><span data-stu-id="37a1c-111">Description</span></span>                                                                    |
| ---------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------ |
| [<span data-ttu-id="37a1c-112">要求</span><span class="sxs-lookup"><span data-stu-id="37a1c-112">Request</span></span>](../../../../docs/framework/unmanaged-api/debugging/dacpgetmoduleaddress-request-method.md) | <span data-ttu-id="37a1c-113">指定したランタイムの構造体から構造の作成要求を実行します。</span><span class="sxs-lookup"><span data-stu-id="37a1c-113">Performs a request to populate the structure from the given runtime structure.</span></span> |

## <a name="remarks"></a><span data-ttu-id="37a1c-114">Remarks</span><span class="sxs-lookup"><span data-stu-id="37a1c-114">Remarks</span></span>

<span data-ttu-id="37a1c-115">この構造は、ランタイム内に収めるし、任意のヘッダーまたはライブラリ ファイルでは公開されません。</span><span class="sxs-lookup"><span data-stu-id="37a1c-115">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="37a1c-116">これを使用する構造を定義、上で指定した場所`CLRDATA_ADDRESS`は 64 ビット符号なし整数。</span><span class="sxs-lookup"><span data-stu-id="37a1c-116">To use it, define the structure as specified above, where `CLRDATA_ADDRESS` is a 64-bit unsigned integer.</span></span>

## <a name="requirements"></a><span data-ttu-id="37a1c-117">必要条件</span><span class="sxs-lookup"><span data-stu-id="37a1c-117">Requirements</span></span>
<span data-ttu-id="37a1c-118">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="37a1c-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="37a1c-119">**ヘッダー:** なし</span><span class="sxs-lookup"><span data-stu-id="37a1c-119">**Header:** None</span></span>  
<span data-ttu-id="37a1c-120">**ライブラリ:** なし</span><span class="sxs-lookup"><span data-stu-id="37a1c-120">**Library:** None</span></span>  
<span data-ttu-id="37a1c-121">**.NET Framework のバージョン:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="37a1c-121">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="37a1c-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="37a1c-122">See also</span></span>

- [<span data-ttu-id="37a1c-123">デバッグ</span><span class="sxs-lookup"><span data-stu-id="37a1c-123">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="37a1c-124">デバッグ構造体</span><span class="sxs-lookup"><span data-stu-id="37a1c-124">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
