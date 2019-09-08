---
title: Initialize 関数 (アンマネージ API リファレンス)
description: Initialize 関数は、WMI の初期化を実行します。
ms.date: 11/06/2017
api_name:
- Initialize
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- Initialize
helpviewer_keywords:
- Initialize function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1bc3688b30180bdcde0a87027955a789de749f90
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798442"
---
# <a name="initialize-function"></a><span data-ttu-id="e0e6b-103">Initialize 関数</span><span class="sxs-lookup"><span data-stu-id="e0e6b-103">Initialize function</span></span>

<span data-ttu-id="e0e6b-104">WMI の初期化が実行されます。</span><span class="sxs-lookup"><span data-stu-id="e0e6b-104">Performs WMI initialization.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="e0e6b-105">構文</span><span class="sxs-lookup"><span data-stu-id="e0e6b-105">Syntax</span></span>

```cpp
HRESULT Initialize(
   [in] boolean bAllowIManagementObjectQI
);
```

## <a name="parameters"></a><span data-ttu-id="e0e6b-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e0e6b-106">Parameters</span></span>

`bAllowIManagementObjectQI`

<span data-ttu-id="e0e6b-107">から`true` WMI オブジェクトに対する QueryInterface の呼び出しが許可されていることを示す場合は。`false`それ以外の場合は。</span><span class="sxs-lookup"><span data-stu-id="e0e6b-107">[in] `true` to indicate that calls to QueryInterface on WMI objects are allowed; `false` otherwise.</span></span>

## <a name="return-value"></a><span data-ttu-id="e0e6b-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="e0e6b-108">Return value</span></span>

<span data-ttu-id="e0e6b-109">関数は常に`S_OK` (0) を返します。</span><span class="sxs-lookup"><span data-stu-id="e0e6b-109">The function always returns `S_OK` (0).</span></span>

## <a name="requirements"></a><span data-ttu-id="e0e6b-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="e0e6b-110">Requirements</span></span>

<span data-ttu-id="e0e6b-111">**・** [システム要件](../../get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e0e6b-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="e0e6b-112">**ヘッダー:** WMINet_Utils</span><span class="sxs-lookup"><span data-stu-id="e0e6b-112">**Header:** WMINet_Utils.def</span></span>

<span data-ttu-id="e0e6b-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="e0e6b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="e0e6b-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="e0e6b-114">See also</span></span>

- [<span data-ttu-id="e0e6b-115">WMI およびパフォーマンスカウンター (アンマネージ API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="e0e6b-115">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
