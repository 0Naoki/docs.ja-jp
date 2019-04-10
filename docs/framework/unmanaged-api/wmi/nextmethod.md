---
title: NextMethod 関数 (アンマネージ API リファレンス)
description: NextMethod 関数は、列挙体の次のメソッドを取得します。
ms.date: 11/06/2017
api_name:
- NextMethod
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- NextMethod
helpviewer_keywords:
- NextMethod function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2b3667f7371131a4c1394ba5ca619d1f605c89ce
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59190887"
---
# <a name="nextmethod-function"></a><span data-ttu-id="c69bf-103">NextMethod 関数</span><span class="sxs-lookup"><span data-stu-id="c69bf-103">NextMethod function</span></span>
<span data-ttu-id="c69bf-104">呼び出しで開始する列挙体の次のメソッドを取得します。 [BeginMethodEnumeration](beginmethodenumeration.md)します。</span><span class="sxs-lookup"><span data-stu-id="c69bf-104">Retrieves the next method in an enumeration that begins with a call to [BeginMethodEnumeration](beginmethodenumeration.md).</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="c69bf-105">構文</span><span class="sxs-lookup"><span data-stu-id="c69bf-105">Syntax</span></span>  
  
```  
HRESULT NextMethod (
   [in] int                 vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LONG                lFlags,
   [out] BSTR*              pName,
   [out] IWbemClassObject** ppInSignature,
   [out] IWbemClassObject** ppOutSignature   
); 
```  

## <a name="parameters"></a><span data-ttu-id="c69bf-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c69bf-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="c69bf-107">[in]このパラメーターは使用されません。</span><span class="sxs-lookup"><span data-stu-id="c69bf-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="c69bf-108">[in]ポインター、 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)インスタンス。</span><span class="sxs-lookup"><span data-stu-id="c69bf-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`lFlags`  
<span data-ttu-id="c69bf-109">[in] 予約されています。</span><span class="sxs-lookup"><span data-stu-id="c69bf-109">[in] Reserved.</span></span> <span data-ttu-id="c69bf-110">このパラメーターは、0 を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c69bf-110">This parameter must be 0.</span></span>

`pName`  
<span data-ttu-id="c69bf-111">[out]指すポインター`null`呼び出しの前にします。</span><span class="sxs-lookup"><span data-stu-id="c69bf-111">[out] A pointer that points to `null` prior to the call.</span></span> <span data-ttu-id="c69bf-112">ときに、関数からの新しいアドレス`BSTR`メソッド名を格納しています。</span><span class="sxs-lookup"><span data-stu-id="c69bf-112">When the function returns, the address of a new `BSTR` that contains the method name.</span></span> 

`ppSignatureIn`  
<span data-ttu-id="c69bf-113">[out]ポインターを受け取るポインター、 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)を格納している、`in`メソッドのパラメーター。</span><span class="sxs-lookup"><span data-stu-id="c69bf-113">[out] A pointer that receives a pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) that contains the `in` parameters for the method.</span></span> 

`ppSignatureOut`  
<span data-ttu-id="c69bf-114">[out]ポインターを受け取るポインター、 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)を格納している、`out`メソッドのパラメーター。</span><span class="sxs-lookup"><span data-stu-id="c69bf-114">[out] A pointer that receives a pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) that contains the `out` parameters for the method.</span></span> 

## <a name="return-value"></a><span data-ttu-id="c69bf-115">戻り値</span><span class="sxs-lookup"><span data-stu-id="c69bf-115">Return value</span></span>

<span data-ttu-id="c69bf-116">この関数によって返される次の値が定義されている、 *WbemCli.h*ヘッダー ファイル、またはすることができますに定数としてコードで定義します。</span><span class="sxs-lookup"><span data-stu-id="c69bf-116">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="c69bf-117">定数</span><span class="sxs-lookup"><span data-stu-id="c69bf-117">Constant</span></span>  |<span data-ttu-id="c69bf-118">値</span><span class="sxs-lookup"><span data-stu-id="c69bf-118">Value</span></span>  |<span data-ttu-id="c69bf-119">説明</span><span class="sxs-lookup"><span data-stu-id="c69bf-119">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_UNEXPECTED` | <span data-ttu-id="c69bf-120">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="c69bf-120">0x8004101d</span></span> | <span data-ttu-id="c69bf-121">呼び出しがなかった、 [ `BeginEnumeration` ](beginenumeration.md)関数。</span><span class="sxs-lookup"><span data-stu-id="c69bf-121">There was no call to the [`BeginEnumeration`](beginenumeration.md) function.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="c69bf-122">0</span><span class="sxs-lookup"><span data-stu-id="c69bf-122">0</span></span> | <span data-ttu-id="c69bf-123">関数呼び出しに成功しました。</span><span class="sxs-lookup"><span data-stu-id="c69bf-123">The function call was successful.</span></span>  |
| `WBEM_S_NO_MORE_DATA` | <span data-ttu-id="c69bf-124">0x40005</span><span class="sxs-lookup"><span data-stu-id="c69bf-124">0x40005</span></span> | <span data-ttu-id="c69bf-125">列挙には、プロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="c69bf-125">There are no more properties in the enumeration.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="c69bf-126">Remarks</span><span class="sxs-lookup"><span data-stu-id="c69bf-126">Remarks</span></span>

<span data-ttu-id="c69bf-127">この関数の呼び出しをラップする、 [IWbemClassObject::NextMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-nextmethod)メソッド。</span><span class="sxs-lookup"><span data-stu-id="c69bf-127">This function wraps a call to the [IWbemClassObject::NextMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-nextmethod) method.</span></span>

<span data-ttu-id="c69bf-128">呼び出し元が呼び出すことによって列挙体シーケンスを開始、 [BeginMethodEnumeration](beginmethodenumeration.md)関数、および関数が戻るまで [NextMethod] 関数を呼び出して`WBEM_S_NO_MORE_DATA`します。</span><span class="sxs-lookup"><span data-stu-id="c69bf-128">The caller begins the enumeration sequence by calling the [BeginMethodEnumeration](beginmethodenumeration.md) function, and then calls the [NextMethod] function until the function returns `WBEM_S_NO_MORE_DATA`.</span></span> <span data-ttu-id="c69bf-129">呼び出し元が呼び出すことによって、シーケンスを完了する必要に応じて、 [EndMethodEnumeration](endmethodenumeration.md)します。</span><span class="sxs-lookup"><span data-stu-id="c69bf-129">Optionally, the caller finishes the sequence by calling [EndMethodEnumeration](endmethodenumeration.md).</span></span> <span data-ttu-id="c69bf-130">呼び出し元が呼び出すことによって、列挙体を早期終了可能性があります[EndMethodEnumeration](endmethodenumeration.md)いつでもできます。</span><span class="sxs-lookup"><span data-stu-id="c69bf-130">The caller may terminate the enumeration early by calling [EndMethodEnumeration](endmethodenumeration.md) at any time.</span></span>

## <a name="example"></a><span data-ttu-id="c69bf-131">例</span><span class="sxs-lookup"><span data-stu-id="c69bf-131">Example</span></span>

<span data-ttu-id="c69bf-132">C++ の例では、次を参照してください。、 [IWbemClassObject::NextMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-nextmethod)メソッド。</span><span class="sxs-lookup"><span data-stu-id="c69bf-132">For a C++ example, see the [IWbemClassObject::NextMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-nextmethod) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="c69bf-133">必要条件</span><span class="sxs-lookup"><span data-stu-id="c69bf-133">Requirements</span></span>  
 <span data-ttu-id="c69bf-134">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c69bf-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c69bf-135">**ヘッダー:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="c69bf-135">**Header:** WMINet_Utils.idl</span></span>  
  
 **<span data-ttu-id="c69bf-136">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="c69bf-136">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c69bf-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="c69bf-137">See also</span></span>

- [<span data-ttu-id="c69bf-138">WMI およびパフォーマンス カウンター (アンマネージド API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="c69bf-138">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
