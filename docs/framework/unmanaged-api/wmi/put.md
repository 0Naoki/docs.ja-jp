---
title: Put 関数 (アンマネージ API リファレンス)
description: Put 関数は、名前付きプロパティに新しい値を割り当てます。
ms.date: 11/06/2017
api_name:
- Put
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- Put
helpviewer_keywords:
- Put function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 02c8ab3aa7fcc603b76fb4b1d09e7e73d04494be
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57369196"
---
# <a name="put-function"></a><span data-ttu-id="71e62-103">Put 関数</span><span class="sxs-lookup"><span data-stu-id="71e62-103">Put function</span></span>

<span data-ttu-id="71e62-104">名前付きプロパティが新しい値に設定されます。</span><span class="sxs-lookup"><span data-stu-id="71e62-104">Sets a named property to a new value.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="71e62-105">構文</span><span class="sxs-lookup"><span data-stu-id="71e62-105">Syntax</span></span>

```cpp
HRESULT Put (
   [in] int               vFunc,
   [in] IWbemClassObject* ptr,
   [in] LPCWSTR           wszName,
   [in] LONG              lFlags,
   [in] VARIANT*          pVal,
   [in] CIMTYPE           vtType
);
```

## <a name="parameters"></a><span data-ttu-id="71e62-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="71e62-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="71e62-107">[in]このパラメーターは使用されません。</span><span class="sxs-lookup"><span data-stu-id="71e62-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="71e62-108">[in]ポインター、 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)インスタンス。</span><span class="sxs-lookup"><span data-stu-id="71e62-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszName`\
<span data-ttu-id="71e62-109">[in]プロパティの名前。</span><span class="sxs-lookup"><span data-stu-id="71e62-109">[in] The name of the property.</span></span> <span data-ttu-id="71e62-110">このパラメーターを `null` とすることはできません。</span><span class="sxs-lookup"><span data-stu-id="71e62-110">This parameter cannot be `null`.</span></span>

`lFlags`\
<span data-ttu-id="71e62-111">[in] 予約されています。</span><span class="sxs-lookup"><span data-stu-id="71e62-111">[in] Reserved.</span></span> <span data-ttu-id="71e62-112">このパラメーターは、0 を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="71e62-112">This parameter must be 0.</span></span>

`pVal`\
<span data-ttu-id="71e62-113">[in]有効なへのポインター`VARIANT`新しいプロパティ値になります。</span><span class="sxs-lookup"><span data-stu-id="71e62-113">[in] A pointer to a valid `VARIANT` that becomes the new property value.</span></span> <span data-ttu-id="71e62-114">場合`pVal`は`null`を指す、または、`VARIANT`型の`VT_NULL`に設定されて`null`します。</span><span class="sxs-lookup"><span data-stu-id="71e62-114">If `pVal` is `null` or points to a `VARIANT` of type `VT_NULL`, the property is set to `null`.</span></span>

`vtType`\
<span data-ttu-id="71e62-115">[in]型`VARIANT`によって示される`pVal`します。</span><span class="sxs-lookup"><span data-stu-id="71e62-115">[in] The type of `VARIANT` pointed to by `pVal`.</span></span> <span data-ttu-id="71e62-116">参照してください、[解説](#remarks)詳細についてはします。</span><span class="sxs-lookup"><span data-stu-id="71e62-116">See the [Remarks](#remarks) section for more information.</span></span>

## <a name="return-value"></a><span data-ttu-id="71e62-117">戻り値</span><span class="sxs-lookup"><span data-stu-id="71e62-117">Return value</span></span>

<span data-ttu-id="71e62-118">この関数によって返される次の値が定義されている、 *WbemCli.h*ヘッダー ファイル、またはすることができますに定数としてコードで定義します。</span><span class="sxs-lookup"><span data-stu-id="71e62-118">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="71e62-119">定数</span><span class="sxs-lookup"><span data-stu-id="71e62-119">Constant</span></span>  |<span data-ttu-id="71e62-120">値</span><span class="sxs-lookup"><span data-stu-id="71e62-120">Value</span></span>  |<span data-ttu-id="71e62-121">説明</span><span class="sxs-lookup"><span data-stu-id="71e62-121">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="71e62-122">0x80041001</span><span class="sxs-lookup"><span data-stu-id="71e62-122">0x80041001</span></span> | <span data-ttu-id="71e62-123">一般的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="71e62-123">There has been a general failure.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="71e62-124">0x80041008</span><span class="sxs-lookup"><span data-stu-id="71e62-124">0x80041008</span></span> | <span data-ttu-id="71e62-125">1 つまたは複数のパラメーターが無効です。</span><span class="sxs-lookup"><span data-stu-id="71e62-125">One or more parameters are not valid.</span></span> |
|`WBEM_E_INVALID_PROPERTY_TYPE` | <span data-ttu-id="71e62-126">0x8004102a</span><span class="sxs-lookup"><span data-stu-id="71e62-126">0x8004102a</span></span> | <span data-ttu-id="71e62-127">プロパティの型は認識されません。</span><span class="sxs-lookup"><span data-stu-id="71e62-127">The property type is not recognized.</span></span> <span data-ttu-id="71e62-128">クラスが既に存在する場合は、クラスのインスタンスを作成するときに、この値が返されます。</span><span class="sxs-lookup"><span data-stu-id="71e62-128">This value is returned when creating class instances if the class already exists.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="71e62-129">0x80041006</span><span class="sxs-lookup"><span data-stu-id="71e62-129">0x80041006</span></span> | <span data-ttu-id="71e62-130">操作を完了するのに十分なメモリがあります。</span><span class="sxs-lookup"><span data-stu-id="71e62-130">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_TYPE_MISMATCH` | <span data-ttu-id="71e62-131">0x80041005</span><span class="sxs-lookup"><span data-stu-id="71e62-131">0x80041005</span></span> | <span data-ttu-id="71e62-132">インスタンス。示します`pVal`を指す、`VARIANT`プロパティの型が正しくないのです。</span><span class="sxs-lookup"><span data-stu-id="71e62-132">For instances: Indicates that `pVal` points to a `VARIANT` of an incorrect type for the property.</span></span> <br/> <span data-ttu-id="71e62-133">クラス定義。親クラスのプロパティが既に存在し、新しい COM 型が古い COM 型と異なる。</span><span class="sxs-lookup"><span data-stu-id="71e62-133">For class definitions: The property already exists in the parent class, and the new COM type is different from the old COM type.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="71e62-134">0</span><span class="sxs-lookup"><span data-stu-id="71e62-134">0</span></span> | <span data-ttu-id="71e62-135">関数呼び出しに成功しました。</span><span class="sxs-lookup"><span data-stu-id="71e62-135">The function call was successful.</span></span> |

## <a name="remarks"></a><span data-ttu-id="71e62-136">Remarks</span><span class="sxs-lookup"><span data-stu-id="71e62-136">Remarks</span></span>

<span data-ttu-id="71e62-137">この関数の呼び出しをラップする、 [IWbemClassObject::Put](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-put)メソッド。</span><span class="sxs-lookup"><span data-stu-id="71e62-137">This function wraps a call to the [IWbemClassObject::Put](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-put) method.</span></span>

<span data-ttu-id="71e62-138">この関数は常を新しい現在のプロパティ値を上書きします。</span><span class="sxs-lookup"><span data-stu-id="71e62-138">This function always overwrites the current property value with a new one.</span></span> <span data-ttu-id="71e62-139">場合、 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)クラスの定義を指す`Put`を作成またはプロパティの値を更新します。</span><span class="sxs-lookup"><span data-stu-id="71e62-139">If the [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) points to a class definition, `Put` creates or updates the property value.</span></span> <span data-ttu-id="71e62-140">ときに[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) CIM のインスタンスを指す`Put`更新プログラムのプロパティの値だけです。`Put`プロパティ値を作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="71e62-140">When [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) points to a CIM instance, `Put` updates the property value only; `Put` cannot create a property value.</span></span>

<span data-ttu-id="71e62-141">`__CLASS`システム プロパティは書き込み可能なクラスの作成時に場合にのみこれが空白にできません。</span><span class="sxs-lookup"><span data-stu-id="71e62-141">The `__CLASS` system property is only writable during class creation, when it may not be left blank.</span></span> <span data-ttu-id="71e62-142">その他のすべてのシステム プロパティとは、読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="71e62-142">All other system properties are read-only.</span></span>

<span data-ttu-id="71e62-143">ユーザーは、アンダー スコア (_) で開始または終了する名前を持つプロパティを作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="71e62-143">A user cannot create properties with names that begin or end with an underscore ("_").</span></span> <span data-ttu-id="71e62-144">これはシステム クラスとプロパティの予約されています。</span><span class="sxs-lookup"><span data-stu-id="71e62-144">This is reserved for system classes and properties.</span></span>

<span data-ttu-id="71e62-145">プロパティで設定した場合、`Put`親クラスの関数が存在する、プロパティの既定値が変わらない限り、プロパティの型が、親クラスの型と一致しません。</span><span class="sxs-lookup"><span data-stu-id="71e62-145">If the property set by the `Put` function exists in the parent class, the default value of the property is changed unless the property type does not match the parent class type.</span></span> <span data-ttu-id="71e62-146">プロパティが存在しない型の不一致がない場合は、プロパティが作成されます。</span><span class="sxs-lookup"><span data-stu-id="71e62-146">If the property does not exist and it is not a type mismatch, the property is created.</span></span>

<span data-ttu-id="71e62-147">使用して、 `vtType` CIM クラスの定義で新しいプロパティを作成する場合にのみ、パラメーターと`pVal`は`null`を指す、または、`VARIANT`型の`VT_NULL`します。</span><span class="sxs-lookup"><span data-stu-id="71e62-147">Use the `vtType` parameter only when creating new properties in a CIM class definition and `pVal` is `null` or points to a `VARIANT` of type `VT_NULL`.</span></span> <span data-ttu-id="71e62-148">ここで、`vType`パラメーター プロパティの CIM 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="71e62-148">In this case, the `vType` parameter specifies the CIM type of the property.</span></span> <span data-ttu-id="71e62-149">その他のすべてのケースで`vtType`0 にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="71e62-149">In every other case, `vtType` must be 0.</span></span> <span data-ttu-id="71e62-150">`vtType` 基になるオブジェクトがインスタンスの場合も、0 をある必要があります (場合でも`Val`は`null`) ため、プロパティの型は固定され変更できません。</span><span class="sxs-lookup"><span data-stu-id="71e62-150">`vtType` must also be 0 if the underlying object is an instance (even if `Val` is `null`) because the type of the property is fixed and cannot be changed.</span></span>

## <a name="example"></a><span data-ttu-id="71e62-151">例</span><span class="sxs-lookup"><span data-stu-id="71e62-151">Example</span></span>

<span data-ttu-id="71e62-152">例については、次を参照してください。、 [IWbemClassObject::Put](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-put)メソッド。</span><span class="sxs-lookup"><span data-stu-id="71e62-152">For an example, see the [IWbemClassObject::Put](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-put) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="71e62-153">必要条件</span><span class="sxs-lookup"><span data-stu-id="71e62-153">Requirements</span></span>

<span data-ttu-id="71e62-154">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="71e62-154">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="71e62-155">**ヘッダー:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="71e62-155">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="71e62-156">**.NET Framework のバージョン:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="71e62-156">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="71e62-157">関連項目</span><span class="sxs-lookup"><span data-stu-id="71e62-157">See also</span></span>

- [<span data-ttu-id="71e62-158">WMI およびパフォーマンス カウンター (アンマネージ API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="71e62-158">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)