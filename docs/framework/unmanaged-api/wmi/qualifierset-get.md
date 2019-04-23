---
title: QualifierSet_Get 関数 (アンマネージ API リファレンス)
description: QualifierSet_Get 関数は、名前付き修飾子を取得します。
ms.date: 11/06/2017
api_name:
- QualifierSet_Get
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_Get
helpviewer_keywords:
- QualifierSet_Get function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b0dc76a2732bf9c1e4f3a26fa2d045bfbcd837ec
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59181091"
---
# <a name="qualifiersetget-function"></a><span data-ttu-id="f5c77-103">QualifierSet_Get 関数</span><span class="sxs-lookup"><span data-stu-id="f5c77-103">QualifierSet_Get function</span></span>
<span data-ttu-id="f5c77-104">指定した名前付き修飾子が取得されます。</span><span class="sxs-lookup"><span data-stu-id="f5c77-104">Gets the specified named qualifier.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="f5c77-105">構文</span><span class="sxs-lookup"><span data-stu-id="f5c77-105">Syntax</span></span>  
  
```  
HRESULT QualifierSet_Get (
   [in] int                  vFunc, 
   [in] IWbemQualifierSet*   ptr, 
   [in] LPCWSTR              wszName,
   [in] LONG                 lFlags,
   [out] VARIANT*            pVal,
   [out] LONG*               plFlavor                 
); 
```  

## <a name="parameters"></a><span data-ttu-id="f5c77-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f5c77-106">Parameters</span></span>

`vFunc`   
<span data-ttu-id="f5c77-107">[in]このパラメーターは使用されません。</span><span class="sxs-lookup"><span data-stu-id="f5c77-107">[in] This parameter is unused.</span></span>

`ptr`   
<span data-ttu-id="f5c77-108">[in]ポインター、 [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset)インスタンス。</span><span class="sxs-lookup"><span data-stu-id="f5c77-108">[in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

`wszName`   
<span data-ttu-id="f5c77-109">[in]値が要求された修飾子の名前。</span><span class="sxs-lookup"><span data-stu-id="f5c77-109">[in] The name of the qualifier whose value is requested.</span></span>

`lFlags`   
<span data-ttu-id="f5c77-110">[in] 予約されています。</span><span class="sxs-lookup"><span data-stu-id="f5c77-110">[in] Reserved.</span></span> <span data-ttu-id="f5c77-111">このパラメーターは、0 を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f5c77-111">This parameter must be 0.</span></span>

`pVal`   
<span data-ttu-id="f5c77-112">[out]成功した場合、正しい型および修飾子の値。</span><span class="sxs-lookup"><span data-stu-id="f5c77-112">[out] When successful, the correct type and value for the qualifier.</span></span> <span data-ttu-id="f5c77-113">関数が失敗した場合、`VARIANT`によって示される`pVal`は変更されません。</span><span class="sxs-lookup"><span data-stu-id="f5c77-113">If the function fails, the `VARIANT` pointed to by `pVal` is not modified.</span></span> <span data-ttu-id="f5c77-114">このパラメーターが場合`null`パラメーターは無視されます。</span><span class="sxs-lookup"><span data-stu-id="f5c77-114">If this parameter is `null`, the parameter is ignored.</span></span>

`plFlavor`   
<span data-ttu-id="f5c77-115">[out]要求された修飾子の修飾子のフレーバー ビットを受け取る LONG へのポインター。</span><span class="sxs-lookup"><span data-stu-id="f5c77-115">[out] A pointer to a LONG that receives the qualifier flavor bits for the requested qualifier.</span></span> <span data-ttu-id="f5c77-116">このパラメーターを指定できますフレーバー情報が望ましくない場合`null`します。</span><span class="sxs-lookup"><span data-stu-id="f5c77-116">If flavor information is not desired, this parameter can be `null`.</span></span> 

## <a name="return-value"></a><span data-ttu-id="f5c77-117">戻り値</span><span class="sxs-lookup"><span data-stu-id="f5c77-117">Return value</span></span>

<span data-ttu-id="f5c77-118">この関数によって返される次の値が定義されている、 *WbemCli.h*ヘッダー ファイル、またはすることができますに定数としてコードで定義します。</span><span class="sxs-lookup"><span data-stu-id="f5c77-118">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="f5c77-119">定数</span><span class="sxs-lookup"><span data-stu-id="f5c77-119">Constant</span></span>  |<span data-ttu-id="f5c77-120">値</span><span class="sxs-lookup"><span data-stu-id="f5c77-120">Value</span></span>  |<span data-ttu-id="f5c77-121">説明</span><span class="sxs-lookup"><span data-stu-id="f5c77-121">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="f5c77-122">0x80041008</span><span class="sxs-lookup"><span data-stu-id="f5c77-122">0x80041008</span></span> | <span data-ttu-id="f5c77-123">パラメーターが無効です。</span><span class="sxs-lookup"><span data-stu-id="f5c77-123">A parameter is not valid.</span></span> |
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="f5c77-124">0x80041002</span><span class="sxs-lookup"><span data-stu-id="f5c77-124">0x80041002</span></span> | <span data-ttu-id="f5c77-125">指定した修飾子が存在しません。</span><span class="sxs-lookup"><span data-stu-id="f5c77-125">The specified qualifier does not exist.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="f5c77-126">0</span><span class="sxs-lookup"><span data-stu-id="f5c77-126">0</span></span> | <span data-ttu-id="f5c77-127">関数呼び出しに成功しました。</span><span class="sxs-lookup"><span data-stu-id="f5c77-127">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="f5c77-128">Remarks</span><span class="sxs-lookup"><span data-stu-id="f5c77-128">Remarks</span></span>

<span data-ttu-id="f5c77-129">この関数の呼び出しをラップする、 [IWbemQualifierSet::Get](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-get)メソッド。</span><span class="sxs-lookup"><span data-stu-id="f5c77-129">This function wraps a call to the [IWbemQualifierSet::Get](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-get) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="f5c77-130">必要条件</span><span class="sxs-lookup"><span data-stu-id="f5c77-130">Requirements</span></span>  
 <span data-ttu-id="f5c77-131">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f5c77-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f5c77-132">**ヘッダー:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="f5c77-132">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="f5c77-133">**.NET Framework のバージョン:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="f5c77-133">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5c77-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="f5c77-134">See also</span></span>

- [<span data-ttu-id="f5c77-135">WMI およびパフォーマンス カウンター (アンマネージ API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="f5c77-135">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
