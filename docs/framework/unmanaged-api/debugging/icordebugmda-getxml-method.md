---
title: ICorDebugMDA::GetXML メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugMDA.GetXML
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugMDA::GetXML
helpviewer_keywords:
- ICorDebugMDA::GetXML method [.NET Framework debugging]
- GetXML method [.NET Framework debugging]
ms.assetid: 29746b24-3766-4255-8813-0426c45e73e5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 06eaa77ab655d57ad2cc0a3c5613c05444afd903
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54660633"
---
# <a name="icordebugmdagetxml-method"></a><span data-ttu-id="b14b2-102">ICorDebugMDA::GetXML メソッド</span><span class="sxs-lookup"><span data-stu-id="b14b2-102">ICorDebugMDA::GetXML Method</span></span>
<span data-ttu-id="b14b2-103">によって表されるマネージ デバッグ アシスタント (MDA) に関連付けられている完全な XML ストリームを取得して[ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md)します。</span><span class="sxs-lookup"><span data-stu-id="b14b2-103">Gets the full XML stream associated with the managed debugging assistant (MDA) represented by [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b14b2-104">構文</span><span class="sxs-lookup"><span data-stu-id="b14b2-104">Syntax</span></span>  
  
```  
HRESULT GetXML (  
    [in] ULONG32   cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]  
        WCHAR      szName[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b14b2-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b14b2-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="b14b2-106">[in] `szName` 配列のサイズ。</span><span class="sxs-lookup"><span data-stu-id="b14b2-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="b14b2-107">[out]XML ストリームの長さへのポインター。</span><span class="sxs-lookup"><span data-stu-id="b14b2-107">[out] A pointer to the length of the XML stream.</span></span>  
  
 `szName`  
 <span data-ttu-id="b14b2-108">[out]XML ストリームを格納する配列。</span><span class="sxs-lookup"><span data-stu-id="b14b2-108">[out] An array in which to store the XML stream.</span></span> <span data-ttu-id="b14b2-109">配列は空にすることがあります。</span><span class="sxs-lookup"><span data-stu-id="b14b2-109">The array may be empty.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b14b2-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="b14b2-110">Remarks</span></span>  
 <span data-ttu-id="b14b2-111">`GetXML`メソッドできます関連付けられている XML ストリームのサイズによっては、パフォーマンスに影響する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b14b2-111">The `GetXML` method can potentially affect performance, depending on the size of the associated XML stream.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b14b2-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="b14b2-112">Requirements</span></span>  
 <span data-ttu-id="b14b2-113">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b14b2-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b14b2-114">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b14b2-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b14b2-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b14b2-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b14b2-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b14b2-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b14b2-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="b14b2-117">See also</span></span>
- [<span data-ttu-id="b14b2-118">ICorDebugMDA インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b14b2-118">ICorDebugMDA Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md)
- [<span data-ttu-id="b14b2-119">マネージド デバッグ アシスタントによるエラーの診断</span><span class="sxs-lookup"><span data-stu-id="b14b2-119">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
