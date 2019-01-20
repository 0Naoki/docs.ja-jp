---
title: IXCLRDataMethodDefinition::StartEnumInstances メソッド
ms.date: 01/16/2019
api.name:
- IXCLRDataMethodDefinition::StartEnumInstances Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataMethodDefinition::StartEnumInstances Method
helpviewer.keywords:
- IXCLRDataMethodDefinition::StartEnumInstances Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 208d6c46f18834b23e642efa82df0a365013a410
ms.sourcegitcommit: b56d59ad42140d277f2acbd003b74d655fdbc9f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/19/2019
ms.locfileid: "54416569"
---
# <a name="ixclrdatamethoddefinitionstartenuminstances-method"></a><span data-ttu-id="180eb-102">IXCLRDataMethodDefinition::StartEnumInstances メソッド</span><span class="sxs-lookup"><span data-stu-id="180eb-102">IXCLRDataMethodDefinition::StartEnumInstances Method</span></span>

<span data-ttu-id="180eb-103">メソッド インスタンスの列挙体のハンドルを提供する、指定された`IXCLRDataAppDomain`します。</span><span class="sxs-lookup"><span data-stu-id="180eb-103">Provides a handle for the enumeration of method instances for a given `IXCLRDataAppDomain`.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="180eb-104">構文</span><span class="sxs-lookup"><span data-stu-id="180eb-104">Syntax</span></span>

```
HRESULT StartEnumInstances(
    [in] IXCLRDataAppDomain* appDomain,
    [out] CLRDATA_ENUM *handle
);
```

### <a name="parameters"></a><span data-ttu-id="180eb-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="180eb-105">Parameters</span></span>

<span data-ttu-id="180eb-106">`appDomain` [in]列挙には、アプリケーション ドメイン。</span><span class="sxs-lookup"><span data-stu-id="180eb-106">`appDomain` [in] An AppDomain for the enumeration.</span></span>

<span data-ttu-id="180eb-107">`handle` [out]インスタンスを列挙するためのハンドル。</span><span class="sxs-lookup"><span data-stu-id="180eb-107">`handle` [out] A handle for enumerating the instances.</span></span>

## <a name="remarks"></a><span data-ttu-id="180eb-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="180eb-108">Remarks</span></span>

<span data-ttu-id="180eb-109">指定されたメソッドは、`IXCLRDataMethodDefinition`インターフェイスし、仮想メソッド テーブルの 3 番目のスロットに対応しています。</span><span class="sxs-lookup"><span data-stu-id="180eb-109">The provided method is part of the `IXCLRDataMethodDefinition` interface and corresponds to the third slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="180eb-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="180eb-110">Requirements</span></span>

<span data-ttu-id="180eb-111">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="180eb-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="180eb-112">**ヘッダー:** なし</span><span class="sxs-lookup"><span data-stu-id="180eb-112">**Header:** None</span></span>  
<span data-ttu-id="180eb-113">**ライブラリ:** なし</span><span class="sxs-lookup"><span data-stu-id="180eb-113">**Library:** None</span></span>  
<span data-ttu-id="180eb-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="180eb-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="180eb-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="180eb-115">See Also</span></span>

- [<span data-ttu-id="180eb-116">CLRDataSourceType 列挙型</span><span class="sxs-lookup"><span data-stu-id="180eb-116">CLRDataSourceType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="180eb-117">デバッグ</span><span class="sxs-lookup"><span data-stu-id="180eb-117">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="180eb-118">IXCLRDataMethodDefinition インターフェイス</span><span class="sxs-lookup"><span data-stu-id="180eb-118">IXCLRDataMethodDefinition Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamethoddefinition-interface.md)
