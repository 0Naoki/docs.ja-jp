---
title: QualifierSet_EndEnumeration 関数 (アンマネージ API リファレンス)
description: QualifierSet_EndEnumeration 関数は、列挙を終了します。
ms.date: 11/06/2017
api_name:
- QualifierSet_EndEnumeration
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_EndEnumeration
helpviewer_keywords:
- QualifierSet_EndEnumeration function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: be2dfd6bb521dee14afd3728bdd9c446cb779e85
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59149228"
---
# <a name="qualifiersetendenumeration-function"></a><span data-ttu-id="8bc0b-103">QualifierSet_EndEnumeration 関数</span><span class="sxs-lookup"><span data-stu-id="8bc0b-103">QualifierSet_EndEnumeration function</span></span>
<span data-ttu-id="8bc0b-104">呼び出しで開始された列挙の終了、 [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md)関数。</span><span class="sxs-lookup"><span data-stu-id="8bc0b-104">Terminates the enumeration begun with a call to the [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md) function.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="8bc0b-105">構文</span><span class="sxs-lookup"><span data-stu-id="8bc0b-105">Syntax</span></span>  
  
```  
HRESULT QualifierSet_EndEnumeration (
   [in] int                  vFunc, 
   [in] IWbemQualifierSet*   ptr
); 
```  

## <a name="parameters"></a><span data-ttu-id="8bc0b-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="8bc0b-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="8bc0b-107">[in]このパラメーターは使用されません。</span><span class="sxs-lookup"><span data-stu-id="8bc0b-107">[in] This parameter is unused.</span></span>

`ptr`   
<span data-ttu-id="8bc0b-108">[in]ポインター、 [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset)インスタンス。</span><span class="sxs-lookup"><span data-stu-id="8bc0b-108">[in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

## <a name="return-value"></a><span data-ttu-id="8bc0b-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="8bc0b-109">Return value</span></span>

<span data-ttu-id="8bc0b-110">この関数によって返される次の値が定義されている、 *WbemCli.h*ヘッダー ファイルで定義できますを定数として、コード。</span><span class="sxs-lookup"><span data-stu-id="8bc0b-110">The following value returned by this function is defined in the *WbemCli.h* header file, or you can define it as a constant in your code:</span></span>

|<span data-ttu-id="8bc0b-111">定数</span><span class="sxs-lookup"><span data-stu-id="8bc0b-111">Constant</span></span>  |<span data-ttu-id="8bc0b-112">値</span><span class="sxs-lookup"><span data-stu-id="8bc0b-112">Value</span></span>  |<span data-ttu-id="8bc0b-113">説明</span><span class="sxs-lookup"><span data-stu-id="8bc0b-113">Description</span></span>  |
|---------|---------|---------|
|`WBEM_S_NO_ERROR` | <span data-ttu-id="8bc0b-114">0</span><span class="sxs-lookup"><span data-stu-id="8bc0b-114">0</span></span> | <span data-ttu-id="8bc0b-115">関数呼び出しに成功しました。</span><span class="sxs-lookup"><span data-stu-id="8bc0b-115">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="8bc0b-116">Remarks</span><span class="sxs-lookup"><span data-stu-id="8bc0b-116">Remarks</span></span>

<span data-ttu-id="8bc0b-117">この関数の呼び出しをラップする、 [IWbemQualifierSet::EndEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-endenumeration)メソッド。</span><span class="sxs-lookup"><span data-stu-id="8bc0b-117">This function wraps a call to the [IWbemQualifierSet::EndEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-endenumeration) method.</span></span>

<span data-ttu-id="8bc0b-118">この呼び出しは、お勧めしますが、必要ありません。</span><span class="sxs-lookup"><span data-stu-id="8bc0b-118">This call is recommended, but not required.</span></span> <span data-ttu-id="8bc0b-119">列挙体に関連付けられているリソースを直ちに解放します。</span><span class="sxs-lookup"><span data-stu-id="8bc0b-119">It immediately releases resources associated with the enumeration.</span></span>

## <a name="requirements"></a><span data-ttu-id="8bc0b-120">必要条件</span><span class="sxs-lookup"><span data-stu-id="8bc0b-120">Requirements</span></span>  

<span data-ttu-id="8bc0b-121">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8bc0b-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
<span data-ttu-id="8bc0b-122">**ヘッダー:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="8bc0b-122">**Header:** WMINet_Utils.idl</span></span>  
  
**<span data-ttu-id="8bc0b-123">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="8bc0b-123">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a><span data-ttu-id="8bc0b-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="8bc0b-124">See also</span></span>

- [<span data-ttu-id="8bc0b-125">WMI およびパフォーマンス カウンター (アンマネージド API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="8bc0b-125">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
