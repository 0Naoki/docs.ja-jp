---
title: PutClassWmi 関数 (アンマネージ API リファレンス)
description: PutClassWmi 関数では、新しいクラスを作成します。 または、既存のものを更新します。
ms.date: 11/06/2017
api_name:
- PutClassWmi
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- PutClassWmi
helpviewer_keywords:
- PutClassWmi function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: de08662a825a84f19a40863cf73481d89364ebd0
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/08/2018
ms.locfileid: "44210469"
---
# <a name="putclasswmi-function"></a><span data-ttu-id="0f70d-103">PutClassWmi 関数</span><span class="sxs-lookup"><span data-stu-id="0f70d-103">PutClassWmi function</span></span>
<span data-ttu-id="0f70d-104">新しいクラスが作成されるか、既存のクラスが更新されます。</span><span class="sxs-lookup"><span data-stu-id="0f70d-104">Creates a new class or updates an existing one.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="0f70d-105">構文</span><span class="sxs-lookup"><span data-stu-id="0f70d-105">Syntax</span></span>  
  
```  
HRESULT PutClassWmi (
   [in] IWbemClassObject*    pObject,
   [in] long                 lFlags,
   [in] IWbemContext*        pCtx,
   [out] IWbemCallResult**   ppCallResult
); 
```  

## <a name="parameters"></a><span data-ttu-id="0f70d-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0f70d-106">Parameters</span></span>

`pObject`    
<span data-ttu-id="0f70d-107">[in]有効なクラス定義へのポインター。</span><span class="sxs-lookup"><span data-stu-id="0f70d-107">[in] A pointer to a valid class definition.</span></span> <span data-ttu-id="0f70d-108">すべての必要なプロパティ値が正しく初期化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0f70d-108">It must be correctly initialized with all the required property values.</span></span>

`lFlags`   
<span data-ttu-id="0f70d-109">[in]この関数の動作に影響するフラグの組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="0f70d-109">[in] A combination of flags that affect the behavior of this function.</span></span> <span data-ttu-id="0f70d-110">次の値が定義されている、 *WbemCli.h*ヘッダー ファイル、またはすることができますに定数としてコードで定義します。</span><span class="sxs-lookup"><span data-stu-id="0f70d-110">The following values are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span> 

|<span data-ttu-id="0f70d-111">定数</span><span class="sxs-lookup"><span data-stu-id="0f70d-111">Constant</span></span>  |<span data-ttu-id="0f70d-112">値</span><span class="sxs-lookup"><span data-stu-id="0f70d-112">Value</span></span>  |<span data-ttu-id="0f70d-113">説明</span><span class="sxs-lookup"><span data-stu-id="0f70d-113">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_USE_AMENDED_QUALIFIERS` | <span data-ttu-id="0f70d-114">0x20000</span><span class="sxs-lookup"><span data-stu-id="0f70d-114">0x20000</span></span> | <span data-ttu-id="0f70d-115">場合設定、WMI では、修正済みのフレーバーで、修飾子は保存されません。</span><span class="sxs-lookup"><span data-stu-id="0f70d-115">If set, WMI does not store any qualifiers with the amended flavor.</span></span> </br> <span data-ttu-id="0f70d-116">このオブジェクトがローカライズされていないことと、すべての修飾子は storedwith こと前提は、セットされていない場合はこのインスタンス。</span><span class="sxs-lookup"><span data-stu-id="0f70d-116">If not set, it is assumed that this object is not localized, and all qualifiers are storedwith this instance.</span></span> |
| `WBEM_FLAG_CREATE_OR_UPDATE` | <span data-ttu-id="0f70d-117">0</span><span class="sxs-lookup"><span data-stu-id="0f70d-117">0</span></span> | <span data-ttu-id="0f70d-118">存在したり、既に存在する場合は、上書きしない場合は、クラスを作成します。</span><span class="sxs-lookup"><span data-stu-id="0f70d-118">Create the class if it does not exist, or overwrite it if it exists already.</span></span> |
| `WBEM_FLAG_UPDATE_ONLY` | <span data-ttu-id="0f70d-119">1</span><span class="sxs-lookup"><span data-stu-id="0f70d-119">1</span></span> | <span data-ttu-id="0f70d-120">クラスを更新します。</span><span class="sxs-lookup"><span data-stu-id="0f70d-120">Update the class.</span></span> <span data-ttu-id="0f70d-121">クラスは、呼び出しの成功に存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0f70d-121">The class must exist for the call to be successful.</span></span> |
| `WBEM_FLAG_CREATE_ONLY` | <span data-ttu-id="0f70d-122">2</span><span class="sxs-lookup"><span data-stu-id="0f70d-122">2</span></span> | <span data-ttu-id="0f70d-123">クラスを作成します。</span><span class="sxs-lookup"><span data-stu-id="0f70d-123">Create the class.</span></span> <span data-ttu-id="0f70d-124">クラスが既に存在する場合、呼び出しが失敗します。</span><span class="sxs-lookup"><span data-stu-id="0f70d-124">The call fails if the class already exists.</span></span> |
| `WBEM_FLAG_RETURN_IMMEDIATELY` | <span data-ttu-id="0f70d-125">0x10</span><span class="sxs-lookup"><span data-stu-id="0f70d-125">0x10</span></span> | <span data-ttu-id="0f70d-126">フラグには、半同期的メソッドの呼び出しが行わします。</span><span class="sxs-lookup"><span data-stu-id="0f70d-126">The flag causes a semisynchronous call.</span></span> |
| `WBEM_FLAG_OWNER_UPDATE` | <span data-ttu-id="0f70d-127">0x10000</span><span class="sxs-lookup"><span data-stu-id="0f70d-127">0x10000</span></span> | <span data-ttu-id="0f70d-128">呼び出すときに、プッシュのプロバイダーはこのフラグを指定する必要があります`PutClassWmi`をこのクラスが変更されたことを示します。</span><span class="sxs-lookup"><span data-stu-id="0f70d-128">Push providers must specify this flag when calling `PutClassWmi` to indicate that this class has changed.</span></span> |
| `WBEM_FLAG_UPDATE_COMPATIBLE` | <span data-ttu-id="0f70d-129">0</span><span class="sxs-lookup"><span data-stu-id="0f70d-129">0</span></span> | <span data-ttu-id="0f70d-130">クラスが派生クラスを持たないとそのクラスのインスタンスがない場合に更新するできるようにします。</span><span class="sxs-lookup"><span data-stu-id="0f70d-130">Allows a class to be updated if there are no derived classes and no instances of that class.</span></span> <span data-ttu-id="0f70d-131">説明の修飾子などの重要でない修飾子だけを変更した場合、更新プログラムは、すべてのケースでことも可能に。</span><span class="sxs-lookup"><span data-stu-id="0f70d-131">It also allows updates in all cases if the change is just to unimportant qualifiers, such as the Description qualifier.</span></span> <span data-ttu-id="0f70d-132">クラスのインスタンスには、または変更が重要な修飾子には、更新プログラムは失敗します。</span><span class="sxs-lookup"><span data-stu-id="0f70d-132">If the class has instances or changes are to important qualifiers, the update fails.</span></span> |
| `WBEM_FLAG_UPDATE_SAFE_MODE` | <span data-ttu-id="0f70d-133">0x20</span><span class="sxs-lookup"><span data-stu-id="0f70d-133">0x20</span></span> | <span data-ttu-id="0f70d-134">変更に子クラスを任意の競合が発生しない限り、子クラスがある場合でもクラスの更新が可能です。</span><span class="sxs-lookup"><span data-stu-id="0f70d-134">Allows updates of classes even if there are child classes as long as the change does not cause any conflicts with child classes.</span></span> <span data-ttu-id="0f70d-135">たとえば、このフラグは、子クラスのいずれかで記述されていない基底クラスに追加する新しいプロパティを使用できます。</span><span class="sxs-lookup"><span data-stu-id="0f70d-135">For example, this flag allows a new property to be added to the base class that was not previously mentioned in any of the child classes.</span></span> <span data-ttu-id="0f70d-136">クラスのインスタンスの場合、更新は失敗します。</span><span class="sxs-lookup"><span data-stu-id="0f70d-136">If the class has instances, the update fails.</span></span> |
| `WBEM_FLAG_UPDATE_FORCE_MODE` | <span data-ttu-id="0f70d-137">0x40</span><span class="sxs-lookup"><span data-stu-id="0f70d-137">0x40</span></span> | <span data-ttu-id="0f70d-138">競合する子クラスが存在する場合は、クラスの更新プログラムを強制的にします。</span><span class="sxs-lookup"><span data-stu-id="0f70d-138">forces updates of classes when conflicting child classes exist.</span></span> <span data-ttu-id="0f70d-139">たとえば、このフラグでは、クラス修飾子は、子クラスで定義され、基底クラスの既存の 1 つと競合する同じ修飾子を追加しようとする場合、更新プログラムが強制されます。</span><span class="sxs-lookup"><span data-stu-id="0f70d-139">For example, this flag forces an update if a class qualifier is defined in a child class, and the base class tries to add the same qualifier which conflicts with thte existing one.</span></span> <span data-ttu-id="0f70d-140">強制モードでは、子クラスに競合する修飾子を削除することによって tis 競合を解決します。</span><span class="sxs-lookup"><span data-stu-id="0f70d-140">In force mode, tis conflict is resolved by deleting the conflicting qualifier in the child class.</span></span> |

`pCtx`  
<span data-ttu-id="0f70d-141">[in]この値は、通常、`null`します。</span><span class="sxs-lookup"><span data-stu-id="0f70d-141">[in] Typically, this value is `null`.</span></span> <span data-ttu-id="0f70d-142">ポインターは、それ以外の場合、 [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext)インスタンスを要求されたクラスを提供しているプロバイダーによって使用されることができます。</span><span class="sxs-lookup"><span data-stu-id="0f70d-142">Otherwise, it is a pointer to an [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) instance that can be used by the provider that is providing the requested classes.</span></span> 

`ppCallResult`  
<span data-ttu-id="0f70d-143">[out]場合`null`、このパラメーターは使用されません。</span><span class="sxs-lookup"><span data-stu-id="0f70d-143">[out] If `null`, this parameter is unused.</span></span> <span data-ttu-id="0f70d-144">場合`lFlags`を含む`WBEM_FLAG_RETURN_IMMEDIATELY`、関数を直ちに返します`WBEM_S_NO_ERROR`します。</span><span class="sxs-lookup"><span data-stu-id="0f70d-144">If `lFlags` contains `WBEM_FLAG_RETURN_IMMEDIATELY`, the function returns immediately with `WBEM_S_NO_ERROR`.</span></span> <span data-ttu-id="0f70d-145">`ppCallResult`パラメーターは、新しいへのポインターを受け取ります[IWbemCallResult](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcallresult)オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="0f70d-145">The `ppCallResult` parameter receives a pointer to a new [IWbemCallResult](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcallresult) object.</span></span>

## <a name="return-value"></a><span data-ttu-id="0f70d-146">戻り値</span><span class="sxs-lookup"><span data-stu-id="0f70d-146">Return value</span></span>

<span data-ttu-id="0f70d-147">この関数によって返される次の値が定義されている、 *WbemCli.h*ヘッダー ファイル、またはすることができますに定数としてコードで定義します。</span><span class="sxs-lookup"><span data-stu-id="0f70d-147">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="0f70d-148">定数</span><span class="sxs-lookup"><span data-stu-id="0f70d-148">Constant</span></span>  |<span data-ttu-id="0f70d-149">値</span><span class="sxs-lookup"><span data-stu-id="0f70d-149">Value</span></span>  |<span data-ttu-id="0f70d-150">説明</span><span class="sxs-lookup"><span data-stu-id="0f70d-150">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | <span data-ttu-id="0f70d-151">0x80041003</span><span class="sxs-lookup"><span data-stu-id="0f70d-151">0x80041003</span></span> | <span data-ttu-id="0f70d-152">ユーザーには、作成またはクラスを変更するアクセス許可がありません。</span><span class="sxs-lookup"><span data-stu-id="0f70d-152">The user does not have permission to create or modify classes.</span></span> |
| `WBEM_E_FAILED` | <span data-ttu-id="0f70d-153">0x80041001</span><span class="sxs-lookup"><span data-stu-id="0f70d-153">0x80041001</span></span> | <span data-ttu-id="0f70d-154">不明なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="0f70d-154">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_CLASS` | <span data-ttu-id="0f70d-155">0x80041010</span><span class="sxs-lookup"><span data-stu-id="0f70d-155">0x80041010</span></span> | <span data-ttu-id="0f70d-156">指定したクラスが無効です。</span><span class="sxs-lookup"><span data-stu-id="0f70d-156">The specified class is not valid.</span></span> <span data-ttu-id="0f70d-157">通常、これが示す`pObject`インスタンス オブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="0f70d-157">Typically, this indicates that `pObject` specifies an instance object.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="0f70d-158">0x80041008</span><span class="sxs-lookup"><span data-stu-id="0f70d-158">0x80041008</span></span> | <span data-ttu-id="0f70d-159">パラメーターが無効です。</span><span class="sxs-lookup"><span data-stu-id="0f70d-159">A parameter is not valid.</span></span> |
| `WBEM_E_INVALID OPERATION` | <span data-ttu-id="0f70d-160">0x80041016</span><span class="sxs-lookup"><span data-stu-id="0f70d-160">0x80041016</span></span> | <span data-ttu-id="0f70d-161">指定されたクラス名が無効です。</span><span class="sxs-lookup"><span data-stu-id="0f70d-161">The specified class name is not valid.</span></span> |
| `WBEM_E_CLASS_HAS_CHILDREN` | <span data-ttu-id="0f70d-162">0x80041025</span><span class="sxs-lookup"><span data-stu-id="0f70d-162">0x80041025</span></span> | <span data-ttu-id="0f70d-163">サブクラスを無効にする変更が試行されました。</span><span class="sxs-lookup"><span data-stu-id="0f70d-163">An attempt was made to make a change that would invalidate a subclass.</span></span> |
| `WBEM_E_ALREADY_EXISTS` | <span data-ttu-id="0f70d-164">0x80041019</span><span class="sxs-lookup"><span data-stu-id="0f70d-164">0x80041019</span></span> | <span data-ttu-id="0f70d-165">`WBEM_FLAG_CREATE_ONLY`フラグが指定されましたが、クラスが既に存在します。</span><span class="sxs-lookup"><span data-stu-id="0f70d-165">The `WBEM_FLAG_CREATE_ONLY` flag was specified, but the class already exists.</span></span> |
| `WBEM_E_NOT_FOUND` | <span data-ttu-id="0f70d-166">0x80041002</span><span class="sxs-lookup"><span data-stu-id="0f70d-166">0x80041002</span></span> | <span data-ttu-id="0f70d-167">`WBEM_FLAG_UPDATE_ONLY` 指定された`lFlags`クラスが見つかりません。</span><span class="sxs-lookup"><span data-stu-id="0f70d-167">`WBEM_FLAG_UPDATE_ONLY` was specified in `lFlags`, and the class was not found.</span></span> |
| `WBEM_E_INCOMPLETE_CLASS` | <span data-ttu-id="0f70d-168">0x80041020</span><span class="sxs-lookup"><span data-stu-id="0f70d-168">0x80041020</span></span> | <span data-ttu-id="0f70d-169">クラスの必須プロパティがすべてではなく設定されています。</span><span class="sxs-lookup"><span data-stu-id="0f70d-169">The required properties for classes have not all been set.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="0f70d-170">0x80041006</span><span class="sxs-lookup"><span data-stu-id="0f70d-170">0x80041006</span></span> | <span data-ttu-id="0f70d-171">操作を完了するのに十分なメモリがあります。</span><span class="sxs-lookup"><span data-stu-id="0f70d-171">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_SHUTTING_DOWN` | <span data-ttu-id="0f70d-172">0x80041033</span><span class="sxs-lookup"><span data-stu-id="0f70d-172">0x80041033</span></span> | <span data-ttu-id="0f70d-173">WMI は、おそらく停止および再起動されました。</span><span class="sxs-lookup"><span data-stu-id="0f70d-173">WMI was probably stopped and restarting.</span></span> <span data-ttu-id="0f70d-174">呼び出す[ConnectServerWmi](connectserverwmi.md)もう一度です。</span><span class="sxs-lookup"><span data-stu-id="0f70d-174">Call [ConnectServerWmi](connectserverwmi.md) again.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="0f70d-175">0x80041015</span><span class="sxs-lookup"><span data-stu-id="0f70d-175">0x80041015</span></span> | <span data-ttu-id="0f70d-176">現在のプロセスと WMI のリモート プロシージャ コール (RPC) リンクに失敗しました。</span><span class="sxs-lookup"><span data-stu-id="0f70d-176">The remote procedure call (RPC) link between the current process and WMI has failed.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="0f70d-177">0</span><span class="sxs-lookup"><span data-stu-id="0f70d-177">0</span></span> | <span data-ttu-id="0f70d-178">関数呼び出しに成功しました。</span><span class="sxs-lookup"><span data-stu-id="0f70d-178">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="0f70d-179">Remarks</span><span class="sxs-lookup"><span data-stu-id="0f70d-179">Remarks</span></span>

<span data-ttu-id="0f70d-180">この関数の呼び出しをラップする、 [IWbemServices::PutClass](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-putclass)メソッド。</span><span class="sxs-lookup"><span data-stu-id="0f70d-180">This function wraps a call to the [IWbemServices::PutClass](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-putclass) method.</span></span>

<span data-ttu-id="0f70d-181">ユーザーは、アンダー スコア chacater で開始または終了する名前を持つクラスを作成できません。</span><span class="sxs-lookup"><span data-stu-id="0f70d-181">The user may not create classes with names that begin or end with an underscore chacater</span></span>

<span data-ttu-id="0f70d-182">呼び出すことによって追加のエラー情報を取得するには、関数呼び出しに失敗した場合、 [GetErrorInfo](geterrorinfo.md)関数。</span><span class="sxs-lookup"><span data-stu-id="0f70d-182">If the function call fails, you can obtain additional error information by calling the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="0f70d-183">要件</span><span class="sxs-lookup"><span data-stu-id="0f70d-183">Requirements</span></span>  
 <span data-ttu-id="0f70d-184">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0f70d-184">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0f70d-185">**ヘッダー:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="0f70d-185">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="0f70d-186">**.NET Framework のバージョン:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="0f70d-186">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f70d-187">関連項目</span><span class="sxs-lookup"><span data-stu-id="0f70d-187">See also</span></span>  
[<span data-ttu-id="0f70d-188">WMI およびパフォーマンス カウンター (アンマネージ API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="0f70d-188">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
