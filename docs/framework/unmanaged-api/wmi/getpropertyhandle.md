---
title: GetPropertyHandle 関数 (アンマネージ API リファレンス)
description: GetPropertyHandle 関数では、プロパティの識別子を管理する一意のハンドルを返します。
ms.date: 11/06/2017
api_name:
- GetPropertyHandle
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetPropertyHandle
helpviewer_keywords:
- GetPropertyHandle function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 94171b0708c97eb7510e916e451ed03645d706f3
ms.sourcegitcommit: a1e35d4e94edab384a63406c0a5438306873031b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/21/2018
ms.locfileid: "42754591"
---
# <a name="getpropertyhandle-function"></a><span data-ttu-id="78c54-103">GetPropertyHandle 関数</span><span class="sxs-lookup"><span data-stu-id="78c54-103">GetPropertyHandle function</span></span>
<span data-ttu-id="78c54-104">プロパティを識別する一意のハンドルを返します。</span><span class="sxs-lookup"><span data-stu-id="78c54-104">Returns a unique handle that identifies a property.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="78c54-105">構文</span><span class="sxs-lookup"><span data-stu-id="78c54-105">Syntax</span></span>  
  
```  
HRESULT GetPropertyHandle (
   [in] int                  vFunc, 
   [in] IWbemObjectAccess*   ptr, 
   [in] LPCWSTR              wszPropertyName,
   [out] CIMTYPE*            pType,
   [out] long*               pHandle
); 
```  

## <a name="parameters"></a><span data-ttu-id="78c54-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="78c54-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="78c54-107">[in]このパラメーターは使用されません。</span><span class="sxs-lookup"><span data-stu-id="78c54-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="78c54-108">[in]ポインター、 [IWbemObjectAccess](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectaccess)インスタンス。</span><span class="sxs-lookup"><span data-stu-id="78c54-108">[in] A pointer to an [IWbemObjectAccess](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectaccess) instance.</span></span>

`wszPropertyName`  
<span data-ttu-id="78c54-109">[in]プロパティ名を含む UTF16 でエンコードされた characaters の null で終わる文字列。</span><span class="sxs-lookup"><span data-stu-id="78c54-109">[in] A null-terminated string of UTF16-encoded characaters that contains the property name.</span></span>   

`pType`  
<span data-ttu-id="78c54-110">[out]ポインターを[ `CIMTYPE` ](https://msdn.microsoft.com/library/aa386309(v=vs.85).aspx)プロパティの CIM 型を表す列挙型メンバー。</span><span class="sxs-lookup"><span data-stu-id="78c54-110">[out] A pointer to a [`CIMTYPE`](https://msdn.microsoft.com/library/aa386309(v=vs.85).aspx) enumeration member that represents the CIM type of the property.</span></span>

`pHandle`   
<span data-ttu-id="78c54-111">[out]プロパティのハンドルを格納する整数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="78c54-111">[out] A pointer to an integer that contains the property handle.</span></span>

## <a name="return-value"></a><span data-ttu-id="78c54-112">戻り値</span><span class="sxs-lookup"><span data-stu-id="78c54-112">Return value</span></span>

<span data-ttu-id="78c54-113">この関数によって返される次の値が定義されている、 *WbemCli.h*ヘッダー ファイル、またはすることができますに定数としてコードで定義します。</span><span class="sxs-lookup"><span data-stu-id="78c54-113">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="78c54-114">定数</span><span class="sxs-lookup"><span data-stu-id="78c54-114">Constant</span></span>  |<span data-ttu-id="78c54-115">値</span><span class="sxs-lookup"><span data-stu-id="78c54-115">Value</span></span>  |<span data-ttu-id="78c54-116">説明</span><span class="sxs-lookup"><span data-stu-id="78c54-116">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="78c54-117">0x80041002</span><span class="sxs-lookup"><span data-stu-id="78c54-117">0x80041002</span></span> | <span data-ttu-id="78c54-118">指定したプロパティ名が見つかりませんでした。</span><span class="sxs-lookup"><span data-stu-id="78c54-118">The specified property name was not found.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="78c54-119">0x80041008</span><span class="sxs-lookup"><span data-stu-id="78c54-119">0x80041008</span></span> | <span data-ttu-id="78c54-120">パラメーターが無効です。</span><span class="sxs-lookup"><span data-stu-id="78c54-120">A parameter is not valid.</span></span> |
|`WBEM_E_NOT_SUPPORTED` | <span data-ttu-id="78c54-121">0x8004100c</span><span class="sxs-lookup"><span data-stu-id="78c54-121">0x8004100c</span></span> | <span data-ttu-id="78c54-122">要求されたプロパティの型は、`CIM_OBJECT`または`CIM_ARRAY`します。</span><span class="sxs-lookup"><span data-stu-id="78c54-122">The requested property is of type are `CIM_OBJECT` or `CIM_ARRAY`.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="78c54-123">0</span><span class="sxs-lookup"><span data-stu-id="78c54-123">0</span></span> | <span data-ttu-id="78c54-124">関数呼び出しに成功しました。</span><span class="sxs-lookup"><span data-stu-id="78c54-124">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="78c54-125">Remarks</span><span class="sxs-lookup"><span data-stu-id="78c54-125">Remarks</span></span>

<span data-ttu-id="78c54-126">この関数の呼び出しをラップする、 [IWbemClassObject::GetPropertyHandle](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemobjectaccess-getpropertyhandle)メソッド。</span><span class="sxs-lookup"><span data-stu-id="78c54-126">This function wraps a call to the [IWbemClassObject::GetPropertyHandle](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemobjectaccess-getpropertyhandle) method.</span></span>

<span data-ttu-id="78c54-127">使用する場合は、プロパティを識別するために、このハンドルを使用することができます[IWbemObjectAccess](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectaccess)読み取りまたは書き込みのプロパティの値をメソッド。</span><span class="sxs-lookup"><span data-stu-id="78c54-127">You can use this handle to identify properties when using  [IWbemObjectAccess](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectaccess) methods to read or write property values.</span></span>

<span data-ttu-id="78c54-128">ハンドルを以外のすべてのデータ型のプロパティを取得できる`CIM_OBJECT`と`CIM_ARRAY`します。</span><span class="sxs-lookup"><span data-stu-id="78c54-128">Handles can be retrieved for properties of all data types other than `CIM_OBJECT` and `CIM_ARRAY`.</span></span> <span data-ttu-id="78c54-129">クラスのすべてのインスタンス ハンドルの作業が返されます。</span><span class="sxs-lookup"><span data-stu-id="78c54-129">Returned handles work across all instances of a class.</span></span>

## <a name="requirements"></a><span data-ttu-id="78c54-130">要件</span><span class="sxs-lookup"><span data-stu-id="78c54-130">Requirements</span></span>  
<span data-ttu-id="78c54-131">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="78c54-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="78c54-132">**ヘッダー:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="78c54-132">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="78c54-133">**.NET Framework のバージョン:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="78c54-133">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78c54-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="78c54-134">See also</span></span>  
[<span data-ttu-id="78c54-135">WMI およびパフォーマンス カウンター (アンマネージ API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="78c54-135">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
