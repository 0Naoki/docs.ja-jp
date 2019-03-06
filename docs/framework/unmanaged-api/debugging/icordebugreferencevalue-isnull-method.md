---
title: ICorDebugReferenceValue::IsNull メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugReferenceValue.IsNull
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugReferenceValue::IsNull
helpviewer_keywords:
- IsNull method, ICorDebugReferenceValue interface [.NET Framework debugging]
- ICorDebugReferenceValue::IsNull method [.NET Framework debugging]
ms.assetid: 99e8c8d7-a1c0-47c8-9dbd-03e0b2bcb4d5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 972df4613255dc1b71801e02d387a735dfc632c0
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57477258"
---
# <a name="icordebugreferencevalueisnull-method"></a><span data-ttu-id="61b1d-102">ICorDebugReferenceValue::IsNull メソッド</span><span class="sxs-lookup"><span data-stu-id="61b1d-102">ICorDebugReferenceValue::IsNull Method</span></span>
<span data-ttu-id="61b1d-103">この ICorDebugReferenceValue が null の値を後者がかどうかを示す値を取得、`ICorDebugReferenceValue`がオブジェクトを指していません。</span><span class="sxs-lookup"><span data-stu-id="61b1d-103">Gets a value that indicates whether this ICorDebugReferenceValue is a null value, in which case the `ICorDebugReferenceValue` does not point to an object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61b1d-104">構文</span><span class="sxs-lookup"><span data-stu-id="61b1d-104">Syntax</span></span>  
  
```  
HRESULT IsNull (  
    [out] BOOL   *pbNull  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="61b1d-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="61b1d-105">Parameters</span></span>  
 `pbNull`  
 <span data-ttu-id="61b1d-106">[out]ブール値へのポインター`true`場合は、この`ICorDebugReferenceValue`オブジェクトは null。 それ以外の場合、`pbNull`は`false`します。</span><span class="sxs-lookup"><span data-stu-id="61b1d-106">[out] A pointer to a Boolean value that is `true` if this `ICorDebugReferenceValue` object is null; otherwise, `pbNull` is `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="61b1d-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="61b1d-107">Requirements</span></span>  
 <span data-ttu-id="61b1d-108">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="61b1d-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="61b1d-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="61b1d-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="61b1d-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="61b1d-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="61b1d-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="61b1d-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
