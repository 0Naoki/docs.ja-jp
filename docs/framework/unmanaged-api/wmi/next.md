---
title: 次の関数 (アンマネージ API リファレンス)
description: 次のように関数 retireves 列挙体では、次のプロパティ。
ms.date: 11/06/2017
api_name:
- Next
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- Next
helpviewer_keywords:
- Next function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 15d470ccf9384695aa38a50c2c062c1b660fea96
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/01/2018
ms.locfileid: "43388615"
---
# <a name="next-function"></a><span data-ttu-id="c2882-103">次の関数</span><span class="sxs-lookup"><span data-stu-id="c2882-103">Next function</span></span>
<span data-ttu-id="c2882-104">呼び出しで開始する列挙体では、次のプロパティを取得します。 [BeginEnumeration](beginenumeration.md)します。</span><span class="sxs-lookup"><span data-stu-id="c2882-104">Retrieves the next property in an enumeration that begins with a call to [BeginEnumeration](beginenumeration.md).</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="c2882-105">構文</span><span class="sxs-lookup"><span data-stu-id="c2882-105">Syntax</span></span>  
  
```  
HRESULT Next (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LONG              lFlags,
   [out] BSTR*            pstrName,
   [out] VARIANT*         pVal,
   [out] CIMTYPE*         pvtType,
   [out] LONG*            plFlavor     
); 
```  

## <a name="parameters"></a><span data-ttu-id="c2882-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c2882-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="c2882-107">[in]このパラメーターは使用されません。</span><span class="sxs-lookup"><span data-stu-id="c2882-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="c2882-108">[in]ポインター、 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)インスタンス。</span><span class="sxs-lookup"><span data-stu-id="c2882-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`lFlags`  
<span data-ttu-id="c2882-109">[in]予約されています。</span><span class="sxs-lookup"><span data-stu-id="c2882-109">[in] Reserved.</span></span> <span data-ttu-id="c2882-110">このパラメーターは、0 を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c2882-110">This parameter must be 0.</span></span>

`pstrName`  
<span data-ttu-id="c2882-111">[out]新しい`BSTR`プロパティ名を格納しています。</span><span class="sxs-lookup"><span data-stu-id="c2882-111">[out] A new `BSTR` that contains the property name.</span></span> <span data-ttu-id="c2882-112">このパラメーターに設定することができます`null`名前が必要ない場合。</span><span class="sxs-lookup"><span data-stu-id="c2882-112">You can set this parameter to `null` if the name is not required.</span></span>

`pVal`  
<span data-ttu-id="c2882-113">[out]A`VARIANT`のプロパティの値が格納されます。</span><span class="sxs-lookup"><span data-stu-id="c2882-113">[out] A `VARIANT` filled with the value of the property.</span></span> <span data-ttu-id="c2882-114">このパラメーターに設定することができます`null`場合は、値は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="c2882-114">You can set this parameter to `null` if the value is not required.</span></span> <span data-ttu-id="c2882-115">関数は、エラー コードを返した場合、`VARIANT`に渡される`pVal`は左未変更の状態します。</span><span class="sxs-lookup"><span data-stu-id="c2882-115">If the function returns an error code, the `VARIANT` passed to `pVal` is left unmodified.</span></span> 

`pvtType`  
<span data-ttu-id="c2882-116">[out]ポインターを`CIMTYPE`変数 (、`LONG`にプロパティの型が配置されます)。</span><span class="sxs-lookup"><span data-stu-id="c2882-116">[out] A pointer to a `CIMTYPE` variable (a `LONG` into which the type of the property is placed).</span></span> <span data-ttu-id="c2882-117">このプロパティの値を指定できます、 `VT_NULL_VARIANT`、この場合は、プロパティの実際の型を決定するために必要です。</span><span class="sxs-lookup"><span data-stu-id="c2882-117">The value of this property can be a `VT_NULL_VARIANT`, in which case it is necessary to determine the actual type of the property.</span></span> <span data-ttu-id="c2882-118">このパラメーターは指定できますも`null`します。</span><span class="sxs-lookup"><span data-stu-id="c2882-118">This parameter can also be `null`.</span></span> 

`plFlavor`  
<span data-ttu-id="c2882-119">[out]`null`、またはプロパティの原点の情報を受信する値。</span><span class="sxs-lookup"><span data-stu-id="c2882-119">[out] `null`, or a value that receives information on the origin of the property.</span></span> <span data-ttu-id="c2882-120">使用可能な値 [注釈] セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c2882-120">See the [Remarks] section for possible values.</span></span> 

## <a name="return-value"></a><span data-ttu-id="c2882-121">戻り値</span><span class="sxs-lookup"><span data-stu-id="c2882-121">Return value</span></span>

<span data-ttu-id="c2882-122">この関数によって返される次の値が定義されている、 *WbemCli.h*ヘッダー ファイル、またはすることができますに定数としてコードで定義します。</span><span class="sxs-lookup"><span data-stu-id="c2882-122">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="c2882-123">定数</span><span class="sxs-lookup"><span data-stu-id="c2882-123">Constant</span></span>  |<span data-ttu-id="c2882-124">値</span><span class="sxs-lookup"><span data-stu-id="c2882-124">Value</span></span>  |<span data-ttu-id="c2882-125">説明</span><span class="sxs-lookup"><span data-stu-id="c2882-125">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="c2882-126">0x80041001</span><span class="sxs-lookup"><span data-stu-id="c2882-126">0x80041001</span></span> | <span data-ttu-id="c2882-127">一般的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="c2882-127">There has been a general failure.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="c2882-128">0x80041008</span><span class="sxs-lookup"><span data-stu-id="c2882-128">0x80041008</span></span> | <span data-ttu-id="c2882-129">パラメーターが無効です。</span><span class="sxs-lookup"><span data-stu-id="c2882-129">A parameter is invalid.</span></span> |
| `WBEM_E_UNEXPECTED` | <span data-ttu-id="c2882-130">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="c2882-130">0x8004101d</span></span> | <span data-ttu-id="c2882-131">呼び出しがなかった、 [ `BeginEnumeration` ](beginenumeration.md)関数。</span><span class="sxs-lookup"><span data-stu-id="c2882-131">There was no call to the [`BeginEnumeration`](beginenumeration.md) function.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="c2882-132">0x80041006</span><span class="sxs-lookup"><span data-stu-id="c2882-132">0x80041006</span></span> | <span data-ttu-id="c2882-133">新しい列挙を開始するのに十分なメモリがあります。</span><span class="sxs-lookup"><span data-stu-id="c2882-133">Not enough memory is available to begin a new enumeration.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="c2882-134">0x80041015</span><span class="sxs-lookup"><span data-stu-id="c2882-134">0x80041015</span></span> | <span data-ttu-id="c2882-135">リモート プロシージャは、現在のプロセスと Windows の管理に失敗しました間を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="c2882-135">The remote procedure call betweeen the current process and Windows Management failed.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="c2882-136">0</span><span class="sxs-lookup"><span data-stu-id="c2882-136">0</span></span> | <span data-ttu-id="c2882-137">関数呼び出しに成功しました。</span><span class="sxs-lookup"><span data-stu-id="c2882-137">The function call was successful.</span></span>  |
| `WBEM_S_NO_MORE_DATA` | <span data-ttu-id="c2882-138">0x40005</span><span class="sxs-lookup"><span data-stu-id="c2882-138">0x40005</span></span> | <span data-ttu-id="c2882-139">列挙には、プロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="c2882-139">There are no more properties in the enumeration.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="c2882-140">Remarks</span><span class="sxs-lookup"><span data-stu-id="c2882-140">Remarks</span></span>

<span data-ttu-id="c2882-141">この関数の呼び出しをラップする、 [IWbemClassObject::Next](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-next)メソッド。</span><span class="sxs-lookup"><span data-stu-id="c2882-141">This function wraps a call to the [IWbemClassObject::Next](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-next) method.</span></span>

<span data-ttu-id="c2882-142">このメソッドは、システムのプロパティも返します。</span><span class="sxs-lookup"><span data-stu-id="c2882-142">This method also returns system properties.</span></span>

<span data-ttu-id="c2882-143">プロパティの基になる型がオブジェクトのパス、日付または時刻、または別の特殊な種類の場合は、し、返される型では十分な情報が含まれませんしません。</span><span class="sxs-lookup"><span data-stu-id="c2882-143">If the underlying type of the property is an object path, a date or time, or another special type, then the returned type does not contain enough information.</span></span> <span data-ttu-id="c2882-144">呼び出し元を確認する必要があります、`CIMTYPE`指定したプロパティ、プロパティがオブジェクト参照を日付または時刻、または別の特殊な種類を判断します。</span><span class="sxs-lookup"><span data-stu-id="c2882-144">The caller must examine the `CIMTYPE` for the specified property to determine if the property is an object reference, a date or time, or another special type.</span></span>

<span data-ttu-id="c2882-145">場合`plFlavor`は`null`、`LONG`値が次のように、プロパティの発生元に関する情報を受信します。</span><span class="sxs-lookup"><span data-stu-id="c2882-145">If `plFlavor` is not `null`, the `LONG` value receives information about the origin of the property, as follows:</span></span>

|<span data-ttu-id="c2882-146">定数</span><span class="sxs-lookup"><span data-stu-id="c2882-146">Constant</span></span>  |<span data-ttu-id="c2882-147">値</span><span class="sxs-lookup"><span data-stu-id="c2882-147">Value</span></span>  |<span data-ttu-id="c2882-148">説明</span><span class="sxs-lookup"><span data-stu-id="c2882-148">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAVOR_ORIGIN_SYSTEM` | <span data-ttu-id="c2882-149">0x40</span><span class="sxs-lookup"><span data-stu-id="c2882-149">0x40</span></span> | <span data-ttu-id="c2882-150">プロパティは、標準のシステム プロパティです。</span><span class="sxs-lookup"><span data-stu-id="c2882-150">The property is a standard system property.</span></span> |
| `WBEM_FLAVOR_ORIGIN_PROPAGATED` | <span data-ttu-id="c2882-151">0x20</span><span class="sxs-lookup"><span data-stu-id="c2882-151">0x20</span></span> | <span data-ttu-id="c2882-152">クラス: プロパティは、親クラスから継承されます。</span><span class="sxs-lookup"><span data-stu-id="c2882-152">For a class: The property is inherited from the parent class.</span></span> </br> <span data-ttu-id="c2882-153">インスタンス: プロパティを親クラスから継承中に変更されていないインスタンスによって。</span><span class="sxs-lookup"><span data-stu-id="c2882-153">For an instance: The property, while inherited from the parent class, has not been modified by the instance.</span></span>  |
| `WBEM_FLAVOR_ORIGIN_LOCAL` | <span data-ttu-id="c2882-154">0</span><span class="sxs-lookup"><span data-stu-id="c2882-154">0</span></span> | <span data-ttu-id="c2882-155">クラス: 派生クラスにプロパティが属しています。</span><span class="sxs-lookup"><span data-stu-id="c2882-155">For a class: The property belongs to the derived class.</span></span> </br> <span data-ttu-id="c2882-156">インスタンスのインスタンスでプロパティを変更。つまり、値が指定されましたまたは修飾子が追加または変更します。</span><span class="sxs-lookup"><span data-stu-id="c2882-156">For an instance: The property is modified by the instance; that is, a value was supplied, or a qualifier was added or modified.</span></span> |

## <a name="requirements"></a><span data-ttu-id="c2882-157">要件</span><span class="sxs-lookup"><span data-stu-id="c2882-157">Requirements</span></span>  
 <span data-ttu-id="c2882-158">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c2882-158">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c2882-159">**ヘッダー:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="c2882-159">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="c2882-160">**.NET Framework のバージョン:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="c2882-160">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2882-161">関連項目</span><span class="sxs-lookup"><span data-stu-id="c2882-161">See also</span></span>  
[<span data-ttu-id="c2882-162">WMI およびパフォーマンス カウンター (アンマネージ API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="c2882-162">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
