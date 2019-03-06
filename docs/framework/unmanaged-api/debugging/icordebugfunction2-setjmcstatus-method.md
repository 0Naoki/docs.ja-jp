---
title: ICorDebugFunction2::SetJMCStatus メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugFunction2.SetJMCStatus
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction2::SetJMCStatus
helpviewer_keywords:
- ICorDebugFunction2::SetJMCStatus method [.NET Framework debugging]
- SetJMCStatus method, ICorDebugFunction2 interface [.NET Framework debugging]
ms.assetid: 22c27b01-2869-4214-b840-5921f7c874fc
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 49ced1b4be888c7550c3927d1b319ab2f0bef086
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57501007"
---
# <a name="icordebugfunction2setjmcstatus-method"></a><span data-ttu-id="5e870-102">ICorDebugFunction2::SetJMCStatus メソッド</span><span class="sxs-lookup"><span data-stu-id="5e870-102">ICorDebugFunction2::SetJMCStatus Method</span></span>
<span data-ttu-id="5e870-103">マイ コードのみのこの ICorDebugFunction2 によって表される関数をマーク ステップ実行します。</span><span class="sxs-lookup"><span data-stu-id="5e870-103">Marks the function represented by this ICorDebugFunction2 for Just My Code stepping.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5e870-104">構文</span><span class="sxs-lookup"><span data-stu-id="5e870-104">Syntax</span></span>  
  
```  
HRESULT SetJMCStatus (  
    [in] BOOL   bIsJustMyCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5e870-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5e870-105">Parameters</span></span>  
 `bIsJustMyCode`  
 <span data-ttu-id="5e870-106">[in]設定`true`ユーザー コードとして関数をマークする場合は、`false`します。</span><span class="sxs-lookup"><span data-stu-id="5e870-106">[in] Set to `true` to mark the function as user code; otherwise, set to `false`.</span></span>  
  
## <a name="return-values"></a><span data-ttu-id="5e870-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="5e870-107">Return Values</span></span>  
  
|<span data-ttu-id="5e870-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5e870-108">HRESULT</span></span>|<span data-ttu-id="5e870-109">説明</span><span class="sxs-lookup"><span data-stu-id="5e870-109">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="5e870-110">関数は正しく設定されました。</span><span class="sxs-lookup"><span data-stu-id="5e870-110">The function was successfully marked.</span></span>|  
|`CORDBG_E_FUNCTION_NOT_DEBUGGABLE`|<span data-ttu-id="5e870-111">デバッグすることはできませんので、関数をユーザー コードとしてマークされませんでした。</span><span class="sxs-lookup"><span data-stu-id="5e870-111">The function could not be marked as user code because it cannot be debugged.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5e870-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="5e870-112">Remarks</span></span>  
 <span data-ttu-id="5e870-113">マイ コードのみステッパでは、非ユーザー コードをスキップします。</span><span class="sxs-lookup"><span data-stu-id="5e870-113">A Just My Code stepper will skip non-user code.</span></span> <span data-ttu-id="5e870-114">ユーザー コードは、デバッグできるコードのサブセットである必要があります。</span><span class="sxs-lookup"><span data-stu-id="5e870-114">User code must be a subset of debuggable code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5e870-115">必要条件</span><span class="sxs-lookup"><span data-stu-id="5e870-115">Requirements</span></span>  
 <span data-ttu-id="5e870-116">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5e870-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5e870-117">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5e870-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5e870-118">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5e870-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5e870-119">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5e870-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
