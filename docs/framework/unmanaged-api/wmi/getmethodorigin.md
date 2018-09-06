---
title: GetMethodOrigin 関数 (アンマネージ API リファレンス)
description: GetMethodOrigin 関数は、メソッドが宣言されているクラスを決定します。
ms.date: 11/06/2017
api_name:
- GetMethodOrigin
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetMethodOrigin
helpviewer_keywords:
- GetMethodOrigin function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d1cc754fcf7d1defa815bb0a74b7c2b4a6909478
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2018
ms.locfileid: "43877899"
---
# <a name="getmethodorigin-function"></a><span data-ttu-id="cde2c-103">GetMethodOrigin 関数</span><span class="sxs-lookup"><span data-stu-id="cde2c-103">GetMethodOrigin function</span></span>
<span data-ttu-id="cde2c-104">メソッドを宣言しているクラスが特定されます。</span><span class="sxs-lookup"><span data-stu-id="cde2c-104">Determines the class in which a method is declared.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="cde2c-105">構文</span><span class="sxs-lookup"><span data-stu-id="cde2c-105">Syntax</span></span>  
  
```  
HRESULT GetMethodOrigin (
   [in] int                 vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LPCWSTR             wszMethodName,
   [out] BSTR*              pstrClassName
); 
```  

## <a name="parameters"></a><span data-ttu-id="cde2c-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="cde2c-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="cde2c-107">[in]このパラメーターは使用されません。</span><span class="sxs-lookup"><span data-stu-id="cde2c-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="cde2c-108">[in]ポインター、 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)インスタンス。</span><span class="sxs-lookup"><span data-stu-id="cde2c-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszMethodName`  
<span data-ttu-id="cde2c-109">[in]所有しているクラスが要求されているオブジェクトのメソッドの名前。</span><span class="sxs-lookup"><span data-stu-id="cde2c-109">[in] The name of the method for the object whose owning class is being requested.</span></span> 

`pstrClassName`  
<span data-ttu-id="cde2c-110">[out]メソッドを所有しているクラスの名前を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="cde2c-110">[out] Receives the name of the class that owns the method.</span></span>

## <a name="return-value"></a><span data-ttu-id="cde2c-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="cde2c-111">Return value</span></span>

<span data-ttu-id="cde2c-112">この関数によって返される次の値が定義されている、 *WbemCli.h*ヘッダー ファイル、またはすることができますに定数としてコードで定義します。</span><span class="sxs-lookup"><span data-stu-id="cde2c-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="cde2c-113">定数</span><span class="sxs-lookup"><span data-stu-id="cde2c-113">Constant</span></span>  |<span data-ttu-id="cde2c-114">値</span><span class="sxs-lookup"><span data-stu-id="cde2c-114">Value</span></span>  |<span data-ttu-id="cde2c-115">説明</span><span class="sxs-lookup"><span data-stu-id="cde2c-115">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="cde2c-116">0x80041002</span><span class="sxs-lookup"><span data-stu-id="cde2c-116">0x80041002</span></span> | <span data-ttu-id="cde2c-117">指定されたメソッドが見つかりませんでした。</span><span class="sxs-lookup"><span data-stu-id="cde2c-117">The specified method was not found.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="cde2c-118">0x80041008</span><span class="sxs-lookup"><span data-stu-id="cde2c-118">0x80041008</span></span> | <span data-ttu-id="cde2c-119">1 つまたは複数のパラメーターが無効です。</span><span class="sxs-lookup"><span data-stu-id="cde2c-119">One or more parameters are not valid.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="cde2c-120">0</span><span class="sxs-lookup"><span data-stu-id="cde2c-120">0</span></span> | <span data-ttu-id="cde2c-121">関数呼び出しに成功しました。</span><span class="sxs-lookup"><span data-stu-id="cde2c-121">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="cde2c-122">Remarks</span><span class="sxs-lookup"><span data-stu-id="cde2c-122">Remarks</span></span>

<span data-ttu-id="cde2c-123">この関数の呼び出しをラップする、 [IWbemClassObject::GetMethodOrigin](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethod)メソッド。</span><span class="sxs-lookup"><span data-stu-id="cde2c-123">This function wraps a call to the [IWbemClassObject::GetMethodOrigin](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethod) method.</span></span>

<span data-ttu-id="cde2c-124">クラスは、1 つまたは複数の基底クラスからメソッドを継承することができます、ため開発者は多くの場合に特定のメソッドが定義されているクラスを判別するとします。</span><span class="sxs-lookup"><span data-stu-id="cde2c-124">Because a class can inherit methods from one or more base classes, developers often want to determine the class in which a given method is defined.</span></span>

<span data-ttu-id="cde2c-125">`pstrClassName`パラメーターが有効なをポイントする必要がありますいない`BSTR`ため、これは、関数が呼び出される前に、`out`パラメーター。 この関数によって返された後に、ポインターが割り当て解除されません。</span><span class="sxs-lookup"><span data-stu-id="cde2c-125">The `pstrClassName` parameter must not point to a valid `BSTR` before the function is called because this is an `out` parameter; this pointer is not deallocated after the function returns.</span></span>

## <a name="requirements"></a><span data-ttu-id="cde2c-126">要件</span><span class="sxs-lookup"><span data-stu-id="cde2c-126">Requirements</span></span>  
<span data-ttu-id="cde2c-127">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cde2c-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cde2c-128">**ヘッダー:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="cde2c-128">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="cde2c-129">**.NET Framework のバージョン:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="cde2c-129">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cde2c-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="cde2c-130">See also</span></span>  
[<span data-ttu-id="cde2c-131">WMI およびパフォーマンス カウンター (アンマネージ API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="cde2c-131">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
