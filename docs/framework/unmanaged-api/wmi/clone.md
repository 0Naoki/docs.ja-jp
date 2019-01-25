---
title: Clone 関数 (アンマネージ API リファレンス)
description: クローン関数は、現在の完全な複製である新しいオブジェクトを返します。
ms.date: 11/06/2017
api_name:
- Clone
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- Clone
helpviewer_keywords:
- Clone function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b027d26292b5d810d91932bac4ec8dee4b77661d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54643287"
---
# <a name="clone-function"></a><span data-ttu-id="d96af-103">Clone 関数</span><span class="sxs-lookup"><span data-stu-id="d96af-103">Clone function</span></span>
<span data-ttu-id="d96af-104">現在のオブジェクトの完全な複製である新しいオブジェクトが返されます。</span><span class="sxs-lookup"><span data-stu-id="d96af-104">Returns a new object that is a complete clone of the current object.</span></span>   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="d96af-105">構文</span><span class="sxs-lookup"><span data-stu-id="d96af-105">Syntax</span></span>  
  
```  
HRESULT Clone (
   [in] int                  vFunc, 
   [in] IWbemClassObject*    ptr, 
   [out] IWbemClassObject**  ppCopy
); 
```  

## <a name="parameters"></a><span data-ttu-id="d96af-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d96af-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="d96af-107">[in]このパラメーターは使用されません。</span><span class="sxs-lookup"><span data-stu-id="d96af-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="d96af-108">[in]ポインター、 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)インスタンス。</span><span class="sxs-lookup"><span data-stu-id="d96af-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`ppCopy`  
<span data-ttu-id="d96af-109">[out]完全なである新しいオブジェクトの唯一`ptr`します。</span><span class="sxs-lookup"><span data-stu-id="d96af-109">[out] A new object that is a complete lone of `ptr`.</span></span> <span data-ttu-id="d96af-110">この引数にすることはできません`null`現在のオブジェクトのコピーを受信した場合。</span><span class="sxs-lookup"><span data-stu-id="d96af-110">This argument cannot be `null` if it receives the copy of the current object.</span></span>

## <a name="return-value"></a><span data-ttu-id="d96af-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="d96af-111">Return value</span></span>

<span data-ttu-id="d96af-112">この関数によって返される次の値が定義されている、 *WbemCli.h*ヘッダー ファイル、またはすることができますに定数としてコードで定義します。</span><span class="sxs-lookup"><span data-stu-id="d96af-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="d96af-113">定数</span><span class="sxs-lookup"><span data-stu-id="d96af-113">Constant</span></span>  |<span data-ttu-id="d96af-114">値</span><span class="sxs-lookup"><span data-stu-id="d96af-114">Value</span></span>  |<span data-ttu-id="d96af-115">説明</span><span class="sxs-lookup"><span data-stu-id="d96af-115">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="d96af-116">0x80041001</span><span class="sxs-lookup"><span data-stu-id="d96af-116">0x80041001</span></span> | <span data-ttu-id="d96af-117">一般的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="d96af-117">There has been a general failure.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="d96af-118">0x80041008</span><span class="sxs-lookup"><span data-stu-id="d96af-118">0x80041008</span></span> | <span data-ttu-id="d96af-119">`null` パラメーターとして指定されたこの使用法ではありません。</span><span class="sxs-lookup"><span data-stu-id="d96af-119">`null` was specified as a parameter, and it is not legal in this usage.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="d96af-120">0x80041006</span><span class="sxs-lookup"><span data-stu-id="d96af-120">0x80041006</span></span> | <span data-ttu-id="d96af-121">十分なメモリがオブジェクトを複製します。</span><span class="sxs-lookup"><span data-stu-id="d96af-121">Not enough memory is available to clone the object.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="d96af-122">0</span><span class="sxs-lookup"><span data-stu-id="d96af-122">0</span></span> | <span data-ttu-id="d96af-123">関数呼び出しに成功しました。</span><span class="sxs-lookup"><span data-stu-id="d96af-123">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="d96af-124">Remarks</span><span class="sxs-lookup"><span data-stu-id="d96af-124">Remarks</span></span>

<span data-ttu-id="d96af-125">この関数の呼び出しをラップする、 [IWbemClassObject::Clone](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-clone)メソッド。</span><span class="sxs-lookup"><span data-stu-id="d96af-125">This function wraps a call to the [IWbemClassObject::Clone](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-clone) method.</span></span>

<span data-ttu-id="d96af-126">複製されたオブジェクトは、1 の参照カウントを含む COM オブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="d96af-126">The cloned object is a COM object that has a reference count of 1.</span></span>

## <a name="requirements"></a><span data-ttu-id="d96af-127">必要条件</span><span class="sxs-lookup"><span data-stu-id="d96af-127">Requirements</span></span>  
 <span data-ttu-id="d96af-128">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d96af-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d96af-129">**ヘッダー:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="d96af-129">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="d96af-130">**.NET Framework のバージョン:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="d96af-130">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d96af-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="d96af-131">See also</span></span>
- [<span data-ttu-id="d96af-132">WMI およびパフォーマンス カウンター (アンマネージ API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="d96af-132">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
