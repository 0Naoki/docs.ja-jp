---
title: ICorDebugVariableHome::GetLocationType メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetLocationType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetLocationType
helpviewer_keywords:
- ICorDebugVariableHome::GetLocationType method [.NET Framework debugging]
- GetLocationType method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: 88027c55-8ec6-4f1e-a55b-7eefdbbc3515
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: af879cbbf8edfd05e79d9b77b0c1fb71b2c835c3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59224300"
---
# <a name="icordebugvariablehomegetlocationtype-method"></a><span data-ttu-id="18187-102">ICorDebugVariableHome::GetLocationType メソッド</span><span class="sxs-lookup"><span data-stu-id="18187-102">ICorDebugVariableHome::GetLocationType Method</span></span>
<span data-ttu-id="18187-103">変数のネイティブの場所の種類を取得します。</span><span class="sxs-lookup"><span data-stu-id="18187-103">Gets the type of the variable's native location.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18187-104">構文</span><span class="sxs-lookup"><span data-stu-id="18187-104">Syntax</span></span>  
  
```  
HRESULT GetLocationType(  
    [out] VariableLocationType *pLocationType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="18187-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="18187-105">Parameters</span></span>  
 `pLocationType`  
 <span data-ttu-id="18187-106">[out]変数のネイティブの場所の種類へのポインター。</span><span class="sxs-lookup"><span data-stu-id="18187-106">[out] A pointer to the type of the variable's native location.</span></span>  <span data-ttu-id="18187-107">参照してください、 [VariableLocationType](../../../../docs/framework/unmanaged-api/debugging/variablelocationtype-enumeration.md)詳細情報を列挙します。</span><span class="sxs-lookup"><span data-stu-id="18187-107">See the [VariableLocationType](../../../../docs/framework/unmanaged-api/debugging/variablelocationtype-enumeration.md) enumeration for more information.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="18187-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="18187-108">Requirements</span></span>  
 <span data-ttu-id="18187-109">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="18187-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="18187-110">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="18187-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="18187-111">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="18187-111">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="18187-112">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="18187-112">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="18187-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="18187-113">See also</span></span>

- [<span data-ttu-id="18187-114">ICorDebugVariableHome インターフェイス</span><span class="sxs-lookup"><span data-stu-id="18187-114">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
- [<span data-ttu-id="18187-115">VariableLocationType 列挙型</span><span class="sxs-lookup"><span data-stu-id="18187-115">VariableLocationType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/variablelocationtype-enumeration.md)
