---
title: QualifierSet_Delete 関数 (アンマネージ API リファレンス)
description: QualifierSet_Delete 関数は、名前、修飾子を削除します。
ms.date: 11/06/2017
api_name:
- QualifierSet_Delete
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_Delete
helpviewer_keywords:
- QualifierSet_Delete function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7ca4cc9fb65d1a4bd8713f969bbda5551ce5a2e2
ms.sourcegitcommit: 8c28ab17c26bf08abbd004cc37651985c68841b8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/08/2018
ms.locfileid: "48850623"
---
# <a name="qualifiersetdelete-function"></a><span data-ttu-id="7a8a2-103">QualifierSet_Delete 関数</span><span class="sxs-lookup"><span data-stu-id="7a8a2-103">QualifierSet_Delete function</span></span>
<span data-ttu-id="7a8a2-104">名前によって指定した修飾子が削除されます。</span><span class="sxs-lookup"><span data-stu-id="7a8a2-104">Deletes a specified qualifier by name.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="7a8a2-105">構文</span><span class="sxs-lookup"><span data-stu-id="7a8a2-105">Syntax</span></span>  
  
```  
HRESULT QualifierSet_Delete (
   [in] int                  vFunc, 
   [in] IWbemQualifierSet*   ptr, 
   [in] LPCWSTR              wszName
); 
```  

## <a name="parameters"></a><span data-ttu-id="7a8a2-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="7a8a2-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="7a8a2-107">[in]このパラメーターは使用されません。</span><span class="sxs-lookup"><span data-stu-id="7a8a2-107">[in] This parameter is unused.</span></span>

`ptr`   
<span data-ttu-id="7a8a2-108">[in]ポインター、 [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset)インスタンス。</span><span class="sxs-lookup"><span data-stu-id="7a8a2-108">[in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

`wszName`   
<span data-ttu-id="7a8a2-109">[in]削除する修飾子の名前。</span><span class="sxs-lookup"><span data-stu-id="7a8a2-109">[in] The name of the qualifier to delete.</span></span>

## <a name="return-value"></a><span data-ttu-id="7a8a2-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="7a8a2-110">Return value</span></span>

<span data-ttu-id="7a8a2-111">この関数によって返される次の値が定義されている、 *WbemCli.h*ヘッダー ファイル、またはすることができますに定数としてコードで定義します。</span><span class="sxs-lookup"><span data-stu-id="7a8a2-111">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="7a8a2-112">定数</span><span class="sxs-lookup"><span data-stu-id="7a8a2-112">Constant</span></span>  |<span data-ttu-id="7a8a2-113">値</span><span class="sxs-lookup"><span data-stu-id="7a8a2-113">Value</span></span>  |<span data-ttu-id="7a8a2-114">説明</span><span class="sxs-lookup"><span data-stu-id="7a8a2-114">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="7a8a2-115">0x80041008</span><span class="sxs-lookup"><span data-stu-id="7a8a2-115">0x80041008</span></span> | <span data-ttu-id="7a8a2-116">`wszName`パラメーターが無効です。</span><span class="sxs-lookup"><span data-stu-id="7a8a2-116">The `wszName` parameter is not valid.</span></span> |
|`WBEM_E_INVALID_OPERATION` | <span data-ttu-id="7a8a2-117">0x80041016</span><span class="sxs-lookup"><span data-stu-id="7a8a2-117">0x80041016</span></span> | <span data-ttu-id="7a8a2-118">この修飾子を削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="7a8a2-118">Deleting this qualifier is illegal.</span></span> |
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="7a8a2-119">0x80041002</span><span class="sxs-lookup"><span data-stu-id="7a8a2-119">0x80041002</span></span> | <span data-ttu-id="7a8a2-120">指定した修飾子が見つかりませんでした。</span><span class="sxs-lookup"><span data-stu-id="7a8a2-120">The specified qualifier was not found.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="7a8a2-121">0</span><span class="sxs-lookup"><span data-stu-id="7a8a2-121">0</span></span> | <span data-ttu-id="7a8a2-122">関数呼び出しに成功しました。</span><span class="sxs-lookup"><span data-stu-id="7a8a2-122">The function call was successful.</span></span>  |
| `WBEM_S_RESET_TO_DEFAULT` | <span data-ttu-id="7a8a2-123">0x40002</span><span class="sxs-lookup"><span data-stu-id="7a8a2-123">0x40002</span></span> | <span data-ttu-id="7a8a2-124">ローカルのオーバーライドが削除され、親オブジェクトから元の修飾子がスコープを再開します。</span><span class="sxs-lookup"><span data-stu-id="7a8a2-124">The local override was deleted and the original qualifier from the parent object has resumed scope.</span></span> |

## <a name="remarks"></a><span data-ttu-id="7a8a2-125">Remarks</span><span class="sxs-lookup"><span data-stu-id="7a8a2-125">Remarks</span></span>

<span data-ttu-id="7a8a2-126">この関数の呼び出しをラップする、 [IWbemQualifierSet::Delete](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-delete)メソッド。</span><span class="sxs-lookup"><span data-stu-id="7a8a2-126">This function wraps a call to the [IWbemQualifierSet::Delete](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-delete) method.</span></span>

<span data-ttu-id="7a8a2-127">修飾子の伝達の規則により、特定の修飾子可能性があります別のオブジェクトから継承されだけでは、現在のクラスまたはインスタンスでオーバーライドされます。</span><span class="sxs-lookup"><span data-stu-id="7a8a2-127">Due to qualifier propagation rules, a particular qualifier may have been inherited from another object and merely overridden in the current class or instance.</span></span> <span data-ttu-id="7a8a2-128">ここで、`QualifierSet_Delete`メソッドは、元の継承された値に、修飾子をリセットします。</span><span class="sxs-lookup"><span data-stu-id="7a8a2-128">In this case, the `QualifierSet_Delete` method resets the qualifier to its original inherited value.</span></span> <span data-ttu-id="7a8a2-129">関数は、この場合、状態コードを返します`WBEM_S_RESET_TO_DEFAULT`します。</span><span class="sxs-lookup"><span data-stu-id="7a8a2-129">The function in this case returns the status code `WBEM_S_RESET_TO_DEFAULT`.</span></span>

## <a name="requirements"></a><span data-ttu-id="7a8a2-130">要件</span><span class="sxs-lookup"><span data-stu-id="7a8a2-130">Requirements</span></span>  
 <span data-ttu-id="7a8a2-131">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7a8a2-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7a8a2-132">**ヘッダー:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="7a8a2-132">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="7a8a2-133">**.NET Framework のバージョン:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="7a8a2-133">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a8a2-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="7a8a2-134">See also</span></span>  
[<span data-ttu-id="7a8a2-135">WMI およびパフォーマンス カウンター (アンマネージ API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="7a8a2-135">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
