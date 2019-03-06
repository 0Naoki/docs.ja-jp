---
title: ICorDebugModule::GetFunctionFromToken メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetFunctionFromToken
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetFunctionFromToken
helpviewer_keywords:
- GetFunctionFromToken method, ICorDebugModule interface [.NET Framework debugging]
- ICorDebugModule::GetFunctionFromToken method [.NET Framework debugging]
ms.assetid: 6fe12194-4ef7-43c1-9570-ade35ccf127a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c1af0f8f792c856c0b27b4d3d9ff557bcc5fce82
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57500071"
---
# <a name="icordebugmodulegetfunctionfromtoken-method"></a><span data-ttu-id="d43f0-102">ICorDebugModule::GetFunctionFromToken メソッド</span><span class="sxs-lookup"><span data-stu-id="d43f0-102">ICorDebugModule::GetFunctionFromToken Method</span></span>
<span data-ttu-id="d43f0-103">メタデータ トークンで指定されている関数を取得します。</span><span class="sxs-lookup"><span data-stu-id="d43f0-103">Gets the function that is specified by the metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d43f0-104">構文</span><span class="sxs-lookup"><span data-stu-id="d43f0-104">Syntax</span></span>  
  
```  
HRESULT GetFunctionFromToken(  
    [in] mdMethodDef methodDef,  
    [out] ICorDebugFunction **ppFunction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d43f0-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d43f0-105">Parameters</span></span>  
 `methodDef`  
 <span data-ttu-id="d43f0-106">[in]A`mdMethodDef`関数のメタデータを参照するメタデータ トークン。</span><span class="sxs-lookup"><span data-stu-id="d43f0-106">[in] A `mdMethodDef` metadata token that references the function's metadata.</span></span>  
  
 `ppFunction`  
 <span data-ttu-id="d43f0-107">[out]関数を表す ICorDebugFunction インターフェイス オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="d43f0-107">[out] A pointer to the address of a ICorDebugFunction interface object that represents the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d43f0-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="d43f0-108">Remarks</span></span>  
 <span data-ttu-id="d43f0-109">`GetFunctionFromToken`値が渡された場合、メソッドは CORDBG_E_FUNCTION_NOT_IL HRESULT を返します`methodDef`Microsoft intermediate language (MSIL) のメソッドは参照しません。</span><span class="sxs-lookup"><span data-stu-id="d43f0-109">The `GetFunctionFromToken` method returns a CORDBG_E_FUNCTION_NOT_IL HRESULT if the value passed in `methodDef` does not refer to a Microsoft intermediate language (MSIL) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d43f0-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="d43f0-110">Requirements</span></span>  
 <span data-ttu-id="d43f0-111">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d43f0-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d43f0-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d43f0-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d43f0-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d43f0-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d43f0-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d43f0-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
