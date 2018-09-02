---
title: BeginEnumeration 関数 (アンマネージ API リファレンス)
description: BeginEnumeration 関数が列挙体の先頭に列挙子をリセットします。
ms.date: 11/06/2017
api_name:
- BeginEnumeration
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- BeginEnumeration
helpviewer_keywords:
- BeginEnumeration function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 08406f7d93671b406b3c7cd8719a7a0e5e423184
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/01/2018
ms.locfileid: "43392358"
---
# <a name="beginenumeration-function"></a><span data-ttu-id="7491c-103">BeginEnumeration 関数</span><span class="sxs-lookup"><span data-stu-id="7491c-103">BeginEnumeration function</span></span>
<span data-ttu-id="7491c-104">列挙子を列挙体の先頭にリセットします。</span><span class="sxs-lookup"><span data-stu-id="7491c-104">Resets an enumerator back to the beginning of the enumeration.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="7491c-105">構文</span><span class="sxs-lookup"><span data-stu-id="7491c-105">Syntax</span></span>  
  
```  
HRESULT BeginEnumeration (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LONG              lEnumFlags
); 
```  

## <a name="parameters"></a><span data-ttu-id="7491c-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="7491c-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="7491c-107">[in]このパラメーターは使用されません。</span><span class="sxs-lookup"><span data-stu-id="7491c-107">[in] This parameter is unused.</span></span>

<span data-ttu-id="7491c-108">`ptr` [in]ポインター、 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)インスタンス。</span><span class="sxs-lookup"><span data-stu-id="7491c-108">`ptr` [in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`lEnumFlags`  
<span data-ttu-id="7491c-109">[in]フラグまたはで説明されている値のビットごとの組み合わせ、[解説](#remarks)列挙体に含まれるプロパティを制御するセクション。</span><span class="sxs-lookup"><span data-stu-id="7491c-109">[in] A bitwise combination of the flags or values described in the [Remarks](#remarks) section that controls the properties included in the enumeration.</span></span>

## <a name="return-value"></a><span data-ttu-id="7491c-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="7491c-110">Return value</span></span>

<span data-ttu-id="7491c-111">この関数によって返される次の値が定義されている、 *WbemCli.h*ヘッダー ファイル、またはすることができますに定数としてコードで定義します。</span><span class="sxs-lookup"><span data-stu-id="7491c-111">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="7491c-112">定数</span><span class="sxs-lookup"><span data-stu-id="7491c-112">Constant</span></span>  |<span data-ttu-id="7491c-113">値</span><span class="sxs-lookup"><span data-stu-id="7491c-113">Value</span></span>  |<span data-ttu-id="7491c-114">説明</span><span class="sxs-lookup"><span data-stu-id="7491c-114">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="7491c-115">0x80041008</span><span class="sxs-lookup"><span data-stu-id="7491c-115">0x80041008</span></span> | <span data-ttu-id="7491c-116">フラグの組み合わせ`lEnumFlags`が無効か、無効な引数が指定されました。</span><span class="sxs-lookup"><span data-stu-id="7491c-116">The combination of flags in `lEnumFlags` is invalid, or an invalid argument was specified.</span></span> |
|`WBEM_E_UNEXPECTED` | <span data-ttu-id="7491c-117">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="7491c-117">0x8004101d</span></span> | <span data-ttu-id="7491c-118">2 番目の呼び出し`BeginEnumeration`せずに、中間の呼び出しが行われた[ `EndEnumeration`](endenumeration.md)します。</span><span class="sxs-lookup"><span data-stu-id="7491c-118">A second call to `BeginEnumeration` was made without an intervening call to [`EndEnumeration`](endenumeration.md).</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="7491c-119">0x80041006</span><span class="sxs-lookup"><span data-stu-id="7491c-119">0x80041006</span></span> | <span data-ttu-id="7491c-120">新しい列挙を開始するのに十分なメモリがあります。</span><span class="sxs-lookup"><span data-stu-id="7491c-120">Not enough memory is available to begin a new enumeration.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="7491c-121">0</span><span class="sxs-lookup"><span data-stu-id="7491c-121">0</span></span> | <span data-ttu-id="7491c-122">関数呼び出しに成功しました。</span><span class="sxs-lookup"><span data-stu-id="7491c-122">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="7491c-123">Remarks</span><span class="sxs-lookup"><span data-stu-id="7491c-123">Remarks</span></span>

<span data-ttu-id="7491c-124">この関数の呼び出しをラップする、 [IWbemClassObject::BeginEnumeration](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)メソッド。</span><span class="sxs-lookup"><span data-stu-id="7491c-124">This function wraps a call to the [IWbemClassObject::BeginEnumeration](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) method.</span></span>

<span data-ttu-id="7491c-125">フラグとして渡すことができる、`lEnumFlags`で引数が定義されている、 *WbemCli.h*ヘッダー ファイル、またはすることができますに定数としてコードで定義します。</span><span class="sxs-lookup"><span data-stu-id="7491c-125">The flags that can be passed as the `lEnumFlags` argument are defined in the *WbemCli.h* header file, or you can define them as constants in your code.</span></span>  <span data-ttu-id="7491c-126">その他のグループからのすべてのフラグでは、各グループから 1 つのフラグを組み合わせることができます。</span><span class="sxs-lookup"><span data-stu-id="7491c-126">You can combine one flag from each group with any flag from any other group.</span></span> <span data-ttu-id="7491c-127">ただし、同じグループからのフラグは、相互に排他的です。</span><span class="sxs-lookup"><span data-stu-id="7491c-127">However, flags from the same group are mutually exclusive.</span></span> 

<span data-ttu-id="7491c-128">**グループ 1**</span><span class="sxs-lookup"><span data-stu-id="7491c-128">**Group 1**</span></span>

|<span data-ttu-id="7491c-129">定数</span><span class="sxs-lookup"><span data-stu-id="7491c-129">Constant</span></span>  |<span data-ttu-id="7491c-130">値</span><span class="sxs-lookup"><span data-stu-id="7491c-130">Value</span></span>  |<span data-ttu-id="7491c-131">説明</span><span class="sxs-lookup"><span data-stu-id="7491c-131">Description</span></span>  |
|---------|---------|---------|
|`WBEM_FLAG_KEYS_ONLY` | <span data-ttu-id="7491c-132">0x4</span><span class="sxs-lookup"><span data-stu-id="7491c-132">0x4</span></span> | <span data-ttu-id="7491c-133">キーのみを構成するプロパティが含まれます。</span><span class="sxs-lookup"><span data-stu-id="7491c-133">Include properties that constitute the key only.</span></span> |
|`WBEM_FLAG_REFS_ONLY` | <span data-ttu-id="7491c-134">0x8</span><span class="sxs-lookup"><span data-stu-id="7491c-134">0x8</span></span> | <span data-ttu-id="7491c-135">オブジェクト参照のみであるプロパティが含まれます。</span><span class="sxs-lookup"><span data-stu-id="7491c-135">Include properties that are object references only.</span></span> |

<span data-ttu-id="7491c-136">**グループ 2**</span><span class="sxs-lookup"><span data-stu-id="7491c-136">**Group 2**</span></span>

<span data-ttu-id="7491c-137">定数</span><span class="sxs-lookup"><span data-stu-id="7491c-137">Constant</span></span>  |<span data-ttu-id="7491c-138">値</span><span class="sxs-lookup"><span data-stu-id="7491c-138">Value</span></span>  |<span data-ttu-id="7491c-139">説明</span><span class="sxs-lookup"><span data-stu-id="7491c-139">Description</span></span>  |
|---------|---------|---------|
|`WBEM_FLAG_SYSTEM_ONLY` | <span data-ttu-id="7491c-140">0x30</span><span class="sxs-lookup"><span data-stu-id="7491c-140">0x30</span></span> | <span data-ttu-id="7491c-141">システムのプロパティのみを列挙型を制限します。</span><span class="sxs-lookup"><span data-stu-id="7491c-141">Limit the enumeration to system properties only.</span></span> |
|`WBEM_FLAG_NONSYSTEM_ONLY` | <span data-ttu-id="7491c-142">0x40</span><span class="sxs-lookup"><span data-stu-id="7491c-142">0x40</span></span> | <span data-ttu-id="7491c-143">ローカルおよび伝達されたプロパティが含まれますが、列挙体からシステムのプロパティを除外します。</span><span class="sxs-lookup"><span data-stu-id="7491c-143">Include local and propagated properties but exclude system properties from the enumeration.</span></span> |

<span data-ttu-id="7491c-144">クラス。</span><span class="sxs-lookup"><span data-stu-id="7491c-144">For classes:</span></span>

<span data-ttu-id="7491c-145">定数</span><span class="sxs-lookup"><span data-stu-id="7491c-145">Constant</span></span>  |<span data-ttu-id="7491c-146">値</span><span class="sxs-lookup"><span data-stu-id="7491c-146">Value</span></span>  |<span data-ttu-id="7491c-147">説明</span><span class="sxs-lookup"><span data-stu-id="7491c-147">Description</span></span>  |
|---------|---------|---------|
|`WBEM_FLAG_CLASS_OVERRIDES_ONLY` | <span data-ttu-id="7491c-148">0x100</span><span class="sxs-lookup"><span data-stu-id="7491c-148">0x100</span></span> | <span data-ttu-id="7491c-149">クラス定義でオーバーライドされたプロパティを列挙型を制限します。</span><span class="sxs-lookup"><span data-stu-id="7491c-149">Limit the enumeration to properties overridden in the class definition.</span></span> |
|`WBEM_FLAG_CLASS_LOCAL_AND_OVERRIDES` | <span data-ttu-id="7491c-150">0x100</span><span class="sxs-lookup"><span data-stu-id="7491c-150">0x100</span></span> | <span data-ttu-id="7491c-151">現在のクラス定義でオーバーライドされたプロパティには、クラスで定義されている新しいプロパティを列挙型を制限します。</span><span class="sxs-lookup"><span data-stu-id="7491c-151">Limit the enumeration to properties overridden in the current class definition and to new properties defined in the class.</span></span> |
| `WBEM_MASK_CLASS_CONDITION` | <span data-ttu-id="7491c-152">0x300</span><span class="sxs-lookup"><span data-stu-id="7491c-152">0x300</span></span> | <span data-ttu-id="7491c-153">A がに対して適用するマスク (フラグ) ではなく、`lEnumFlags`いずれかを確認する値`WBEM_FLAG_CLASS_OVERRIDES_ONLY`または`WBEM_FLAG_CLASS_LOCAL_AND_OVERRIDES`設定されています。</span><span class="sxs-lookup"><span data-stu-id="7491c-153">A mask (rather than a flag) to apply against a `lEnumFlags` value to check if either `WBEM_FLAG_CLASS_OVERRIDES_ONLY` or `WBEM_FLAG_CLASS_LOCAL_AND_OVERRIDES` is set.</span></span> |
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="7491c-154">0x10</span><span class="sxs-lookup"><span data-stu-id="7491c-154">0x10</span></span> | <span data-ttu-id="7491c-155">定義またはクラス自体で変更されるプロパティを列挙型を制限します。</span><span class="sxs-lookup"><span data-stu-id="7491c-155">Limit the enumeration to properties that are defined or modified in the class itself.</span></span> |
| `WBEM_FLAG_PROPAGATED_ONLY` |  <span data-ttu-id="7491c-156">0x20</span><span class="sxs-lookup"><span data-stu-id="7491c-156">0x20</span></span> | <span data-ttu-id="7491c-157">基底クラスから継承されるプロパティを列挙型を制限します。</span><span class="sxs-lookup"><span data-stu-id="7491c-157">Limit the enumeration to properties that are inherited from base classes.</span></span> |

<span data-ttu-id="7491c-158">インスタンス。</span><span class="sxs-lookup"><span data-stu-id="7491c-158">For instances:</span></span>

<span data-ttu-id="7491c-159">定数</span><span class="sxs-lookup"><span data-stu-id="7491c-159">Constant</span></span>  |<span data-ttu-id="7491c-160">値</span><span class="sxs-lookup"><span data-stu-id="7491c-160">Value</span></span>  |<span data-ttu-id="7491c-161">説明</span><span class="sxs-lookup"><span data-stu-id="7491c-161">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="7491c-162">0x10</span><span class="sxs-lookup"><span data-stu-id="7491c-162">0x10</span></span> | <span data-ttu-id="7491c-163">定義またはクラス自体で変更されるプロパティを列挙型を制限します。</span><span class="sxs-lookup"><span data-stu-id="7491c-163">Limit the enumeration to properties that are defined or modified in the class itself.</span></span> |
| `WBEM_FLAG_PROPAGATED_ONLY` |  <span data-ttu-id="7491c-164">0x20</span><span class="sxs-lookup"><span data-stu-id="7491c-164">0x20</span></span> | <span data-ttu-id="7491c-165">基底クラスから継承されるプロパティを列挙型を制限します。</span><span class="sxs-lookup"><span data-stu-id="7491c-165">Limit the enumeration to properties that are inherited from base classes.</span></span> |


## <a name="requirements"></a><span data-ttu-id="7491c-166">要件</span><span class="sxs-lookup"><span data-stu-id="7491c-166">Requirements</span></span>  
 <span data-ttu-id="7491c-167">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7491c-167">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7491c-168">**ヘッダー:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="7491c-168">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="7491c-169">**.NET Framework のバージョン:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="7491c-169">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7491c-170">関連項目</span><span class="sxs-lookup"><span data-stu-id="7491c-170">See also</span></span>  
[<span data-ttu-id="7491c-171">WMI およびパフォーマンス カウンター (アンマネージ API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="7491c-171">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
