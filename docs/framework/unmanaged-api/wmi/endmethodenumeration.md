---
title: EndMethodEnumeration 関数 (アンマネージ API リファレンス)
description: EndMethodEnumeration 関数には、メソッドの列挙体シーケンスが終了します。
ms.date: 11/06/2017
api_name:
- EndMethodEnumeration
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- EndMethodEnumeration
helpviewer_keywords:
- EndMethodEnumeration function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a098afe1702e9559a2784ea0716a0a61216e9fd4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54535217"
---
# <a name="endmethodenumeration-function"></a><span data-ttu-id="4598b-103">EndMethodEnumeration 関数</span><span class="sxs-lookup"><span data-stu-id="4598b-103">EndMethodEnumeration function</span></span>
<span data-ttu-id="4598b-104">呼び出しで開始した、列挙体シーケンスの終了、 [BeginMethodEnumeration 関数](beginmethodenumeration.md)します。</span><span class="sxs-lookup"><span data-stu-id="4598b-104">Terminates an enumeration sequence started with a call to the [BeginMethodEnumeration function](beginmethodenumeration.md).</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="4598b-105">構文</span><span class="sxs-lookup"><span data-stu-id="4598b-105">Syntax</span></span>  
  
```  
HRESULT EndMethodEnumeration (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr 
); 
```  

## <a name="parameters"></a><span data-ttu-id="4598b-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="4598b-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="4598b-107">[in]このパラメーターは使用されません。</span><span class="sxs-lookup"><span data-stu-id="4598b-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="4598b-108">[in]ポインター、 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)インスタンス。</span><span class="sxs-lookup"><span data-stu-id="4598b-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

## <a name="return-value"></a><span data-ttu-id="4598b-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="4598b-109">Return value</span></span>

<span data-ttu-id="4598b-110">この関数によって返される次の値が定義されている、 *WbemCli.h*ヘッダー ファイル、またはすることができますに定数としてコードで定義します。</span><span class="sxs-lookup"><span data-stu-id="4598b-110">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="4598b-111">定数</span><span class="sxs-lookup"><span data-stu-id="4598b-111">Constant</span></span>  |<span data-ttu-id="4598b-112">値</span><span class="sxs-lookup"><span data-stu-id="4598b-112">Value</span></span>  |<span data-ttu-id="4598b-113">説明</span><span class="sxs-lookup"><span data-stu-id="4598b-113">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_UNEXPECTED` | <span data-ttu-id="4598b-114">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="4598b-114">0x8004101d</span></span> | <span data-ttu-id="4598b-115">内部エラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="4598b-115">An internal error occurred.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="4598b-116">0</span><span class="sxs-lookup"><span data-stu-id="4598b-116">0</span></span> | <span data-ttu-id="4598b-117">関数呼び出しに成功しました。</span><span class="sxs-lookup"><span data-stu-id="4598b-117">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="4598b-118">Remarks</span><span class="sxs-lookup"><span data-stu-id="4598b-118">Remarks</span></span>

<span data-ttu-id="4598b-119">この関数の呼び出しをラップする、 [IWbemClassObject::EndMethodEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-endmethodenumeration)メソッド。</span><span class="sxs-lookup"><span data-stu-id="4598b-119">This function wraps a call to the [IWbemClassObject::EndMethodEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-endmethodenumeration) method.</span></span>

<span data-ttu-id="4598b-120">呼び出し元が列挙体シーケンスの使用を開始[BeginMethodEnumeration 関数](beginmethodenumeration.md)、号餧ェヒェマル、 [NextMethod 関数](nextmethod.md )メソッドが戻るまで`WBEM_S_NO_MORE_DATA`します。</span><span class="sxs-lookup"><span data-stu-id="4598b-120">The caller begins the enumeration sequence using [BeginMethodEnumeration function](beginmethodenumeration.md), and then calls the [NextMethod function](nextmethod.md )until the method  returns `WBEM_S_NO_MORE_DATA`.</span></span> <span data-ttu-id="4598b-121">呼び出し元は、呼び出すことによって、シーケンスを完了する必要に応じて`EndMethodEnumeration`します。</span><span class="sxs-lookup"><span data-stu-id="4598b-121">The caller optionally finishes the sequence by calling `EndMethodEnumeration`.</span></span> <span data-ttu-id="4598b-122">呼び出し元が呼び出すことによって、列挙体を早期終了可能性があります`EndMethodEnumeration`いつでもできます。</span><span class="sxs-lookup"><span data-stu-id="4598b-122">The caller may terminate the enumeration early by calling `EndMethodEnumeration` at any time.</span></span>

## <a name="requirements"></a><span data-ttu-id="4598b-123">必要条件</span><span class="sxs-lookup"><span data-stu-id="4598b-123">Requirements</span></span>  
 <span data-ttu-id="4598b-124">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4598b-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4598b-125">**ヘッダー:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="4598b-125">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="4598b-126">**.NET Framework のバージョン:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="4598b-126">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4598b-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="4598b-127">See also</span></span>
- [<span data-ttu-id="4598b-128">WMI およびパフォーマンス カウンター (アンマネージ API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="4598b-128">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
