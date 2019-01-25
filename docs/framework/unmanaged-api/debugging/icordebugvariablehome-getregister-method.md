---
title: ICorDebugVariableHome::GetRegister メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetRegister
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetRegister
helpviewer_keywords:
- ICorDebugVariableHome::GetRegister method [.NET Framework debugging]
- GetRegister method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: a5eecd7b-b04c-4266-bff2-7c8771d519a8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7d678b6f52719287a1e8bbe88d178fa47b2893ca
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54563146"
---
# <a name="icordebugvariablehomegetregister-method"></a><span data-ttu-id="f6d47-102">ICorDebugVariableHome::GetRegister メソッド</span><span class="sxs-lookup"><span data-stu-id="f6d47-102">ICorDebugVariableHome::GetRegister Method</span></span>
<span data-ttu-id="f6d47-103">場所の種類を持つ変数を格納するレジスタを取得します。 `VLT_REGISTER`、を、基本の場所の型の変数を登録して`VLT_REGISTER_RELATIVE`します。</span><span class="sxs-lookup"><span data-stu-id="f6d47-103">Gets the register that contains a variable with a location type of `VLT_REGISTER`, and the base register for a variable with a location type of `VLT_REGISTER_RELATIVE`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6d47-104">構文</span><span class="sxs-lookup"><span data-stu-id="f6d47-104">Syntax</span></span>  
  
```  
HRESULT GetRegister(  
    [out] CorDebugRegister *pRegister  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f6d47-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f6d47-105">Parameters</span></span>  
 `pRegister`  
 <span data-ttu-id="f6d47-106">[out]CorDebugRegister 列挙の値の場所の種類を持つ変数のレジスタを示す`VLT_REGISTER`を基本の場所の型の変数を登録して`VLT_REGISTER_RELATIVE`します。</span><span class="sxs-lookup"><span data-stu-id="f6d47-106">[out] A CorDebugRegister enumeration value  that indicates the register for a variable with a location type of `VLT_REGISTER`, and the base register for a variable with a location type of `VLT_REGISTER_RELATIVE`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f6d47-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="f6d47-107">Return Value</span></span>  
 <span data-ttu-id="f6d47-108">メソッドは、次の値を返します。</span><span class="sxs-lookup"><span data-stu-id="f6d47-108">The method returns the following values:</span></span>  
  
|<span data-ttu-id="f6d47-109">[値]</span><span class="sxs-lookup"><span data-stu-id="f6d47-109">Value</span></span>|<span data-ttu-id="f6d47-110">説明</span><span class="sxs-lookup"><span data-stu-id="f6d47-110">Description</span></span>|  
|-----------|-----------------|  
|`S_OK`|<span data-ttu-id="f6d47-111">変数が、レジスタで示されるには、`pRegister`引数。</span><span class="sxs-lookup"><span data-stu-id="f6d47-111">The variable is in the register indicated by the `pRegister` argument.</span></span>|  
|`E_FAIL`|<span data-ttu-id="f6d47-112">変数は、レジスタまたはレジスタの相対位置ではありません。</span><span class="sxs-lookup"><span data-stu-id="f6d47-112">The variable is not in a register or a register-relative location.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f6d47-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="f6d47-113">Requirements</span></span>  
 <span data-ttu-id="f6d47-114">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f6d47-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f6d47-115">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f6d47-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f6d47-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f6d47-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f6d47-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f6d47-117">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6d47-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="f6d47-118">See also</span></span>
- [<span data-ttu-id="f6d47-119">VariableLocationType 列挙型</span><span class="sxs-lookup"><span data-stu-id="f6d47-119">VariableLocationType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/variablelocationtype-enumeration.md)
- [<span data-ttu-id="f6d47-120">ICorDebugVariableHome インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f6d47-120">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
