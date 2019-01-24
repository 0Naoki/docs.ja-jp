---
title: CreateClassEnumWmi 関数 (アンマネージ API リファレンス)
description: CreateClassEnumWmi 関数は、指定した条件を満たすすべてのクラスの列挙子を返します。
ms.date: 11/06/2017
api_name:
- CreateClassEnumWmi
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- CreateClassEnumWmi
helpviewer_keywords:
- CreateClassEnumWmi function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2fc8b25465657ba41220d4a19e10aa06b0e30e86
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54733039"
---
# <a name="createclassenumwmi-function"></a><span data-ttu-id="22969-103">CreateClassEnumWmi 関数</span><span class="sxs-lookup"><span data-stu-id="22969-103">CreateClassEnumWmi function</span></span>
<span data-ttu-id="22969-104">指定した選択条件を満たしたすべてのクラスに対する列挙子が返されます。</span><span class="sxs-lookup"><span data-stu-id="22969-104">Returns an enumerator for all classes that satisfy the specified selection criteria.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="22969-105">構文</span><span class="sxs-lookup"><span data-stu-id="22969-105">Syntax</span></span>  
  
```  
HRESULT CreateClassEnumWmi (
   [in] BSTR                    strSuperclass,
   [in] long                    lFlags,
   [in] IWbemContext*           pCtx,
   [out] IEnumWbemClassObject** ppEnum,
   [in] DWORD                   authLevel,
   [in] DWORD                   impLevel,
   [in] IWbemServices*          pCurrentNamespace,
   [in] BSTR                    strUser,
   [in] BSTR                    strPassword,
   [in] BSTR                    strAuthority
); 
```  

## <a name="parameters"></a><span data-ttu-id="22969-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="22969-106">Parameters</span></span>

`strSuperclass`    
<span data-ttu-id="22969-107">[in]ない場合`null`空白または親クラスの名前を指定する、列挙子は、このクラスのサブクラスだけを返します。</span><span class="sxs-lookup"><span data-stu-id="22969-107">[in] If not `null` or blank, specifies the name of a parent class; the enumerator returns only subclasses of this class.</span></span> <span data-ttu-id="22969-108">場合は`null`または空白と`lFlags`WBEM_FLAG_SHALLOW 場合、最上位クラス (親クラスを持たないクラス) のみを返します。</span><span class="sxs-lookup"><span data-stu-id="22969-108">If it is `null` or blank and `lFlags` is WBEM_FLAG_SHALLOW, returns only top-level classes (classes with no parent class).</span></span> <span data-ttu-id="22969-109">場合は`null`または空白と`lFlags`は`WBEM_FLAG_DEEP`、名前空間内のすべてのクラスを返します。</span><span class="sxs-lookup"><span data-stu-id="22969-109">If it is `null` or blank and `lFlags` is `WBEM_FLAG_DEEP`, returns all classes in the namespace.</span></span>

`lFlags`   
<span data-ttu-id="22969-110">[in]この関数の動作に影響するフラグの組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="22969-110">[in] A combination of flags that affect the behavior of this function.</span></span> <span data-ttu-id="22969-111">次の値が定義されている、 *WbemCli.h*ヘッダー ファイル、またはすることができますに定数としてコードで定義します。</span><span class="sxs-lookup"><span data-stu-id="22969-111">The following values are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span> 

|<span data-ttu-id="22969-112">定数</span><span class="sxs-lookup"><span data-stu-id="22969-112">Constant</span></span>  |<span data-ttu-id="22969-113">値</span><span class="sxs-lookup"><span data-stu-id="22969-113">Value</span></span>  |<span data-ttu-id="22969-114">説明</span><span class="sxs-lookup"><span data-stu-id="22969-114">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_USE_AMENDED_QUALIFIERS` | <span data-ttu-id="22969-115">0x20000</span><span class="sxs-lookup"><span data-stu-id="22969-115">0x20000</span></span> | <span data-ttu-id="22969-116">セット、関数は、現在の接続のロケールのローカライズされた名前空間に格納されている修正済みの修飾子を取得します。 場合、</span><span class="sxs-lookup"><span data-stu-id="22969-116">If set, the function retrieves the amended qualifiers stored in the localized namespace of the current connection's locale.</span></span> <br/> <span data-ttu-id="22969-117">指定しない場合、セット、関数は、即時の名前空間に格納されている修飾子のみを取得します。</span><span class="sxs-lookup"><span data-stu-id="22969-117">If not set, the function retrieves only the qualifiers stored in the immediate namespace.</span></span> |
| `WBEM_FLAG_DEEP` | <span data-ttu-id="22969-118">0</span><span class="sxs-lookup"><span data-stu-id="22969-118">0</span></span> | <span data-ttu-id="22969-119">列挙には、このクラスではなく、階層ですべてのサブクラスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="22969-119">The enumeration includes all subclasses in the hierarchy, but not this class.</span></span> |
| `WBEM_FLAG_SHALLOW` | <span data-ttu-id="22969-120">1</span><span class="sxs-lookup"><span data-stu-id="22969-120">1</span></span> | <span data-ttu-id="22969-121">列挙体は、このクラスの純粋なインスタンスのみが含まれていますおよび、このクラスにないプロパティが指定のサブクラスのすべてのインスタンスを除外します。</span><span class="sxs-lookup"><span data-stu-id="22969-121">The enumeration includes only pure instances of this class and excludes all instances of subclasses that supply properties not found in this class.</span></span> |
| `WBEM_FLAG_RETURN_IMMEDIATELY` | <span data-ttu-id="22969-122">0x10</span><span class="sxs-lookup"><span data-stu-id="22969-122">0x10</span></span> | <span data-ttu-id="22969-123">フラグには、半同期的メソッドの呼び出しが行わします。</span><span class="sxs-lookup"><span data-stu-id="22969-123">The flag causes a semisynchronous call.</span></span> |
| `WBEM_FLAG_FORWARD_ONLY` | <span data-ttu-id="22969-124">0x20</span><span class="sxs-lookup"><span data-stu-id="22969-124">0x20</span></span> | <span data-ttu-id="22969-125">関数は、順方向専用の列挙子を返します。</span><span class="sxs-lookup"><span data-stu-id="22969-125">The function returns a forward-only enumerator.</span></span> <span data-ttu-id="22969-126">呼び出しは許可されませんが、通常、順方向専用の列挙子は、高速と従来の列挙子より少ないメモリを使用して、[複製](clone.md)します。</span><span class="sxs-lookup"><span data-stu-id="22969-126">Typically, forward-only enumerators are faster and use less memory than conventional enumerators, but they do not allow calls to [Clone](clone.md).</span></span> |
| `WBEM_FLAG_BIDIRECTIONAL` | <span data-ttu-id="22969-127">0</span><span class="sxs-lookup"><span data-stu-id="22969-127">0</span></span> | <span data-ttu-id="22969-128">WMI は、リリースされるまで、enumration 内のオブジェクトへのポインターを保持します。</span><span class="sxs-lookup"><span data-stu-id="22969-128">WMI retains pointers to objects in the enumration until they are released.</span></span> | 

<span data-ttu-id="22969-129">推奨されるフラグは`WBEM_FLAG_RETURN_IMMEDIATELY`と`WBEM_FLAG_FORWARD_ONLY`最適なパフォーマンス。</span><span class="sxs-lookup"><span data-stu-id="22969-129">The recommended flags are `WBEM_FLAG_RETURN_IMMEDIATELY` and `WBEM_FLAG_FORWARD_ONLY` for best performance.</span></span>

`pCtx`  
<span data-ttu-id="22969-130">[in]この値は、通常、`null`します。</span><span class="sxs-lookup"><span data-stu-id="22969-130">[in] Typically, this value is `null`.</span></span> <span data-ttu-id="22969-131">ポインターは、それ以外の場合、 [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext)インスタンスを要求されたクラスを提供しているプロバイダーによって使用されることができます。</span><span class="sxs-lookup"><span data-stu-id="22969-131">Otherwise, it is a pointer to an [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) instance that can be used by the provider that is providing the requested classes.</span></span> 

`ppEnum`  
<span data-ttu-id="22969-132">[out]列挙子へのポインターを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="22969-132">[out] Receives the pointer to the enumerator.</span></span>

`authLevel`  
<span data-ttu-id="22969-133">[in]承認レベル。</span><span class="sxs-lookup"><span data-stu-id="22969-133">[in] The authorization level.</span></span>

<span data-ttu-id="22969-134">`impLevel` [in]偽装レベル。</span><span class="sxs-lookup"><span data-stu-id="22969-134">`impLevel` [in] The impersonation level.</span></span>

`pCurrentNamespace`   
<span data-ttu-id="22969-135">[in]ポインター、 [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices)現在の名前空間を表すオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="22969-135">[in] A pointer to an [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) object that represents the current namespace.</span></span>

`strUser`   
<span data-ttu-id="22969-136">[in]ユーザー名。</span><span class="sxs-lookup"><span data-stu-id="22969-136">[in] The user name.</span></span> <span data-ttu-id="22969-137">参照してください、 [ConnectServerWmi](connectserverwmi.md)関数の詳細についてはします。</span><span class="sxs-lookup"><span data-stu-id="22969-137">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strPassword`   
<span data-ttu-id="22969-138">[in]パスワードです。</span><span class="sxs-lookup"><span data-stu-id="22969-138">[in] The password.</span></span> <span data-ttu-id="22969-139">参照してください、 [ConnectServerWmi](connectserverwmi.md)関数の詳細についてはします。</span><span class="sxs-lookup"><span data-stu-id="22969-139">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strAuthority`   
<span data-ttu-id="22969-140">[in]ユーザーのドメイン名。</span><span class="sxs-lookup"><span data-stu-id="22969-140">[in] The domain name of the user.</span></span> <span data-ttu-id="22969-141">参照してください、 [ConnectServerWmi](connectserverwmi.md)関数の詳細についてはします。</span><span class="sxs-lookup"><span data-stu-id="22969-141">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

## <a name="return-value"></a><span data-ttu-id="22969-142">戻り値</span><span class="sxs-lookup"><span data-stu-id="22969-142">Return value</span></span>

<span data-ttu-id="22969-143">この関数によって返される次の値が定義されている、 *WbemCli.h*ヘッダー ファイル、またはすることができますに定数としてコードで定義します。</span><span class="sxs-lookup"><span data-stu-id="22969-143">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="22969-144">定数</span><span class="sxs-lookup"><span data-stu-id="22969-144">Constant</span></span>  |<span data-ttu-id="22969-145">値</span><span class="sxs-lookup"><span data-stu-id="22969-145">Value</span></span>  |<span data-ttu-id="22969-146">説明</span><span class="sxs-lookup"><span data-stu-id="22969-146">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | <span data-ttu-id="22969-147">0x80041003</span><span class="sxs-lookup"><span data-stu-id="22969-147">0x80041003</span></span> | <span data-ttu-id="22969-148">ユーザーには、1 つ以上の関数が返すことができるクラスを表示するアクセス許可がありません。</span><span class="sxs-lookup"><span data-stu-id="22969-148">The user does not have permission to view one or more of the classes that the function can return.</span></span> |
| `WBEM_E_FAILED` | <span data-ttu-id="22969-149">0x80041001</span><span class="sxs-lookup"><span data-stu-id="22969-149">0x80041001</span></span> | <span data-ttu-id="22969-150">不明なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="22969-150">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_CLASS` | <span data-ttu-id="22969-151">0x80041010</span><span class="sxs-lookup"><span data-stu-id="22969-151">0x80041010</span></span> | <span data-ttu-id="22969-152">`strSuperClass` は存在しません。</span><span class="sxs-lookup"><span data-stu-id="22969-152">`strSuperClass` does not exist.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="22969-153">0x80041008</span><span class="sxs-lookup"><span data-stu-id="22969-153">0x80041008</span></span> | <span data-ttu-id="22969-154">パラメーターが無効です。</span><span class="sxs-lookup"><span data-stu-id="22969-154">A parameter is not valid.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="22969-155">0x80041006</span><span class="sxs-lookup"><span data-stu-id="22969-155">0x80041006</span></span> | <span data-ttu-id="22969-156">操作を完了するのに十分なメモリがあります。</span><span class="sxs-lookup"><span data-stu-id="22969-156">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_SHUTTING_DOWN` | <span data-ttu-id="22969-157">0x80041033</span><span class="sxs-lookup"><span data-stu-id="22969-157">0x80041033</span></span> | <span data-ttu-id="22969-158">WMI は、おそらく停止および再起動されました。</span><span class="sxs-lookup"><span data-stu-id="22969-158">WMI was probably stopped and restarting.</span></span> <span data-ttu-id="22969-159">呼び出す[ConnectServerWmi](connectserverwmi.md)もう一度です。</span><span class="sxs-lookup"><span data-stu-id="22969-159">Call [ConnectServerWmi](connectserverwmi.md) again.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="22969-160">0x80041015</span><span class="sxs-lookup"><span data-stu-id="22969-160">0x80041015</span></span> | <span data-ttu-id="22969-161">現在のプロセスと WMI のリモート プロシージャ コール (RPC) リンクに失敗しました。</span><span class="sxs-lookup"><span data-stu-id="22969-161">The remote procedure call (RPC) link between the current process and WMI has failed.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="22969-162">0</span><span class="sxs-lookup"><span data-stu-id="22969-162">0</span></span> | <span data-ttu-id="22969-163">関数呼び出しに成功しました。</span><span class="sxs-lookup"><span data-stu-id="22969-163">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="22969-164">Remarks</span><span class="sxs-lookup"><span data-stu-id="22969-164">Remarks</span></span>

<span data-ttu-id="22969-165">この関数の呼び出しをラップする、 [iwbemservices::createclassenum](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-createclassenum)メソッド。</span><span class="sxs-lookup"><span data-stu-id="22969-165">This function wraps a call to the [IWbemServices::CreateClassEnum](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-createclassenum) method.</span></span>

<span data-ttu-id="22969-166">呼び出すことによって追加のエラー情報を取得するには、関数呼び出しに失敗した場合、 [GetErrorInfo](geterrorinfo.md)関数。</span><span class="sxs-lookup"><span data-stu-id="22969-166">If the function call fails, you can obtain additional error information by calling the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="22969-167">必要条件</span><span class="sxs-lookup"><span data-stu-id="22969-167">Requirements</span></span>  
 <span data-ttu-id="22969-168">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="22969-168">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="22969-169">**ヘッダー:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="22969-169">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="22969-170">**.NET Framework のバージョン:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="22969-170">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22969-171">関連項目</span><span class="sxs-lookup"><span data-stu-id="22969-171">See also</span></span>
- [<span data-ttu-id="22969-172">WMI およびパフォーマンス カウンター (アンマネージ API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="22969-172">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
