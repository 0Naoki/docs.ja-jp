---
title: ICorDebugEval2::NewStringWithLength メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugEval2.NewStringWithLength
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval2::NewStringWithLength
helpviewer_keywords:
- NewStringWithLength method [.NET Framework debugging]
- ICorDebugEval2::NewStringWithLength method [.NET Framework debugging]
ms.assetid: d5f54a34-6335-4708-b407-a756ec70fab4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b84a2fad53feda2996515781035c0eaad5828d54
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57473436"
---
# <a name="icordebugeval2newstringwithlength-method"></a><span data-ttu-id="4dac7-102">ICorDebugEval2::NewStringWithLength メソッド</span><span class="sxs-lookup"><span data-stu-id="4dac7-102">ICorDebugEval2::NewStringWithLength Method</span></span>
<span data-ttu-id="4dac7-103">指定した内容を指定した長さの文字列を作成します。</span><span class="sxs-lookup"><span data-stu-id="4dac7-103">Creates a string of the specified length, with the specified contents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4dac7-104">構文</span><span class="sxs-lookup"><span data-stu-id="4dac7-104">Syntax</span></span>  
  
```  
HRESULT NewStringWithLength (  
    [in] LPCWSTR               string,  
    [in] UINT                  uiLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4dac7-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="4dac7-105">Parameters</span></span>  
 `string`  
 <span data-ttu-id="4dac7-106">[in]文字列値へのポインター。</span><span class="sxs-lookup"><span data-stu-id="4dac7-106">[in] A pointer to the string value.</span></span>  
  
 `uiLength`  
 <span data-ttu-id="4dac7-107">[in]文字列の長さ。</span><span class="sxs-lookup"><span data-stu-id="4dac7-107">[in] Length of the string.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4dac7-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="4dac7-108">Remarks</span></span>  
 <span data-ttu-id="4dac7-109">呼び出し元に、管理対象の文字列にする null 文字が必要です、文字列の末尾の場合、`NewStringWithLength`メソッドでは、文字列の長さが、末尾の null 文字が含まれることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4dac7-109">If the string's trailing null character is expected to be in the managed string, the caller of the `NewStringWithLength` method must ensure that the string length includes the trailing null character.</span></span>  
  
 <span data-ttu-id="4dac7-110">文字列が現在のスレッドが実行されているアプリケーション ドメインで常に作成されます。</span><span class="sxs-lookup"><span data-stu-id="4dac7-110">The string is always created in the application domain in which the thread is currently executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4dac7-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="4dac7-111">Requirements</span></span>  
 <span data-ttu-id="4dac7-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4dac7-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4dac7-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4dac7-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4dac7-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4dac7-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4dac7-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4dac7-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
