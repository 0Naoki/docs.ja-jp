---
title: IcorDebugVariableHome::GetLiveRange メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetLiveRange
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetLiveRange
helpviewer_keywords:
- ICorDebugVariableHome::GetLiveRange method [.NET Framework debugging]
- GetLiveRange method, ICorDebugVariableFrame interface [.NET Framework debugging]
ms.assetid: 87277e1a-1595-4729-9e25-d1c3ac18ce5f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 06c8ae378c10eda986740dfb73f3bf60ea8647a6
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57468846"
---
# <a name="icordebugvariablehomegetliverange-method"></a><span data-ttu-id="c076e-102">IcorDebugVariableHome::GetLiveRange メソッド</span><span class="sxs-lookup"><span data-stu-id="c076e-102">IcorDebugVariableHome::GetLiveRange Method</span></span>
<span data-ttu-id="c076e-103">この変数はライブのネイティブの範囲を取得します。</span><span class="sxs-lookup"><span data-stu-id="c076e-103">Gets the native range over which this variable is live.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c076e-104">構文</span><span class="sxs-lookup"><span data-stu-id="c076e-104">Syntax</span></span>  
  
```  
HRESULT GetLiveRange(  
    [out] ULONG32* pStartOffset,  
    [out] ULONG32 *pEndOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c076e-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c076e-105">Parameters</span></span>  
 `pStartOffset`  
 <span data-ttu-id="c076e-106">[out]これで、変数が最初ライブ論理オフセット。</span><span class="sxs-lookup"><span data-stu-id="c076e-106">[out] The logical offset at which the variable is first live.</span></span>  
  
 `pEndOffset`  
 <span data-ttu-id="c076e-107">[out]位置、変数が最後ライブ後すぐに論理オフセット。</span><span class="sxs-lookup"><span data-stu-id="c076e-107">[out] The logical offset immediately after the point at which the variable is last live.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c076e-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="c076e-108">Requirements</span></span>  
 <span data-ttu-id="c076e-109">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c076e-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c076e-110">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c076e-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c076e-111">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c076e-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c076e-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c076e-112">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c076e-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="c076e-113">See also</span></span>
- [<span data-ttu-id="c076e-114">ICorDebugVariableHome インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c076e-114">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
