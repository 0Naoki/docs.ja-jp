---
title: SpawnInstance 関数 (アンマネージ API リファレンス)
description: SpawnInstance 関数は、クラスの新しいインスタンスを作成します。
ms.date: 11/06/2017
api_name:
- SpawnInstance
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- SpawnInstance
helpviewer_keywords:
- SpawnInstance function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fb187719ff502abe61ac5deb69c6427a4a64ab44
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/08/2018
ms.locfileid: "44198778"
---
# <a name="spawninstance-function"></a><span data-ttu-id="6ae37-103">SpawnInstance 関数</span><span class="sxs-lookup"><span data-stu-id="6ae37-103">SpawnInstance function</span></span>
<span data-ttu-id="6ae37-104">クラスの新しいインスタンスが作成されます。</span><span class="sxs-lookup"><span data-stu-id="6ae37-104">Creates a new instance of a class.</span></span>    
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="6ae37-105">構文</span><span class="sxs-lookup"><span data-stu-id="6ae37-105">Syntax</span></span>  
  
```  
HRESULT SpawnInstance (
   [in] int                  vFunc, 
   [in] IWbemClassObject*    ptr, 
   [in] LONG                 lFlags,
   [out] IWbemClassObject**  ppNewInstance); 
```  

## <a name="parameters"></a><span data-ttu-id="6ae37-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6ae37-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="6ae37-107">[in]このパラメーターは使用されません。</span><span class="sxs-lookup"><span data-stu-id="6ae37-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="6ae37-108">[in]ポインター、 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)インスタンス。</span><span class="sxs-lookup"><span data-stu-id="6ae37-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`lFlags`  
<span data-ttu-id="6ae37-109">[in]予約されています。</span><span class="sxs-lookup"><span data-stu-id="6ae37-109">[in] Reserved.</span></span> <span data-ttu-id="6ae37-110">このパラメーターは、0 を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ae37-110">This parameter must be 0.</span></span>

`ppNewInstance`  
<span data-ttu-id="6ae37-111">[out]クラスの新しいインスタンスへのポインターを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="6ae37-111">[out] Receives the pointer to the new instance of the class.</span></span> <span data-ttu-id="6ae37-112">新しいオブジェクトでないエラーが発生する場合、返されると`ppNewInstance`は左未変更の状態します。</span><span class="sxs-lookup"><span data-stu-id="6ae37-112">If an error occurs, a new object is not returned, and `ppNewInstance` is left unmodified.</span></span>

## <a name="return-value"></a><span data-ttu-id="6ae37-113">戻り値</span><span class="sxs-lookup"><span data-stu-id="6ae37-113">Return value</span></span>

<span data-ttu-id="6ae37-114">この関数によって返される次の値が定義されている、 *WbemCli.h*ヘッダー ファイル、またはすることができますに定数としてコードで定義します。</span><span class="sxs-lookup"><span data-stu-id="6ae37-114">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="6ae37-115">定数</span><span class="sxs-lookup"><span data-stu-id="6ae37-115">Constant</span></span>  |<span data-ttu-id="6ae37-116">値</span><span class="sxs-lookup"><span data-stu-id="6ae37-116">Value</span></span>  |<span data-ttu-id="6ae37-117">説明</span><span class="sxs-lookup"><span data-stu-id="6ae37-117">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_INCOMPLETE_CLASS` | <span data-ttu-id="6ae37-118">0x80041020</span><span class="sxs-lookup"><span data-stu-id="6ae37-118">0x80041020</span></span> | <span data-ttu-id="6ae37-119">`ptr` 有効なクラス定義ではないと、新しいインスタンスを生成することはできません。</span><span class="sxs-lookup"><span data-stu-id="6ae37-119">`ptr` is not a valid class definition and cannot spawn new instances.</span></span> <span data-ttu-id="6ae37-120">完了しないか、それが登録されていない Windows の管理を呼び出すことによって[PutClassWmi](putclasswmi.md)します。</span><span class="sxs-lookup"><span data-stu-id="6ae37-120">Either it is incomplete or it has not been registered with Windows Management by calling [PutClassWmi](putclasswmi.md).</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="6ae37-121">0x80041006</span><span class="sxs-lookup"><span data-stu-id="6ae37-121">0x80041006</span></span> | <span data-ttu-id="6ae37-122">操作を完了するのに十分なメモリがあります。</span><span class="sxs-lookup"><span data-stu-id="6ae37-122">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="6ae37-123">0x80041008</span><span class="sxs-lookup"><span data-stu-id="6ae37-123">0x80041008</span></span> | <span data-ttu-id="6ae37-124">`ppNewClass` は `null` です。</span><span class="sxs-lookup"><span data-stu-id="6ae37-124">`ppNewClass` is `null`.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="6ae37-125">0</span><span class="sxs-lookup"><span data-stu-id="6ae37-125">0</span></span> | <span data-ttu-id="6ae37-126">関数呼び出しに成功しました。</span><span class="sxs-lookup"><span data-stu-id="6ae37-126">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="6ae37-127">Remarks</span><span class="sxs-lookup"><span data-stu-id="6ae37-127">Remarks</span></span>

<span data-ttu-id="6ae37-128">この関数の呼び出しをラップする、 [IWbemClassObject::SpawnInstance](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-spawninstance)メソッド。</span><span class="sxs-lookup"><span data-stu-id="6ae37-128">This function wraps a call to the [IWbemClassObject::SpawnInstance](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-spawninstance) method.</span></span>

<span data-ttu-id="6ae37-129">`ptr` 取得する必要があるクラス定義から Windows の管理。</span><span class="sxs-lookup"><span data-stu-id="6ae37-129">`ptr` must be a class definition obtained from Windows Management.</span></span> <span data-ttu-id="6ae37-130">(インスタンスからインスタンスの生成がサポートされていることに注意してください。 ただし、返されたインスタンスが空)。このクラスの定義を使用するには、新しいインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="6ae37-130">(Note that spawning an instance from an instance is supported but the returned instance is empty.) You then use this class definition to create new instances.</span></span> <span data-ttu-id="6ae37-131">呼び出し、 [PutInstanceWmi](putinstancewmi.md) Windows 管理インスタンスを作成する場合は、関数が必要です。</span><span class="sxs-lookup"><span data-stu-id="6ae37-131">A call to the [PutInstanceWmi](putinstancewmi.md) function is required if you intend to write the instance to Windows Management.</span></span>




<span data-ttu-id="6ae37-132">返される新しいオブジェクト`ppNewClass`自動的に現在のオブジェクトのサブクラスになります。</span><span class="sxs-lookup"><span data-stu-id="6ae37-132">The new object returned in `ppNewClass` automatically becomes a subclass of the current object.</span></span> <span data-ttu-id="6ae37-133">この動作を上書きすることはできません。</span><span class="sxs-lookup"><span data-stu-id="6ae37-133">This behavior cannot be overridden.</span></span> <span data-ttu-id="6ae37-134">サブクラス (派生クラス) を作成できる他の方法はありません。</span><span class="sxs-lookup"><span data-stu-id="6ae37-134">There is no other method by which subclasses (derived classes) can be created.</span></span>

## <a name="requirements"></a><span data-ttu-id="6ae37-135">要件</span><span class="sxs-lookup"><span data-stu-id="6ae37-135">Requirements</span></span>  
 <span data-ttu-id="6ae37-136">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6ae37-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6ae37-137">**ヘッダー:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="6ae37-137">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="6ae37-138">**.NET Framework のバージョン:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="6ae37-138">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ae37-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="6ae37-139">See also</span></span>  
[<span data-ttu-id="6ae37-140">WMI およびパフォーマンス カウンター (アンマネージ API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="6ae37-140">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
