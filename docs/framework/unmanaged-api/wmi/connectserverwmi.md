---
title: ConnectServerWmi 関数 (アンマネージ API リファレンス)
description: ConnectServerWmi 関数では、DCOM を使用して、WMI 名前空間への接続を作成します。
ms.date: 11/06/2017
api_name:
- ConnectServerWmi
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- ConnectServerWmi
helpviewer_keywords:
- ConnectServerWmi function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 163e61eef8a753b5b6470285e5e3ce63789e25a4
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/16/2018
ms.locfileid: "45675757"
---
# <a name="connectserverwmi-function"></a><span data-ttu-id="42a9c-103">ConnectServerWmi 関数</span><span class="sxs-lookup"><span data-stu-id="42a9c-103">ConnectServerWmi function</span></span>
<span data-ttu-id="42a9c-104">指定したコンピューターにある WMI 名前空間との接続が DCOM 経由で作成されます。</span><span class="sxs-lookup"><span data-stu-id="42a9c-104">Creates a connection through DCOM to a WMI namespace on a specified computer.</span></span>  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="42a9c-105">構文</span><span class="sxs-lookup"><span data-stu-id="42a9c-105">Syntax</span></span>  
  
```  
HRESULT ConnectServerWmi (
   [in] BSTR               strNetworkResource,
   [in] BSTR               strUser,
   [in] BSTR               strPassword,
   [in] BSTR               strLocale,
   [in] long               lSecurityFlags,
   [in] BSTR               strAuthority,
   [in] IWbemContext*      pCtx,
   [out] IWbemServices**   ppNamespace,
   [in] DWORD              impLevel, 
   [in] DWORD              authLevel
);
```  
## <a name="parameters"></a><span data-ttu-id="42a9c-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="42a9c-106">Parameters</span></span>

<span data-ttu-id="42a9c-107">`strNetworkResource` [in]有効なポインター`BSTR`正しい WMI 名前空間のオブジェクトのパスを格納しています。</span><span class="sxs-lookup"><span data-stu-id="42a9c-107">`strNetworkResource` [in] Pointer to a valid `BSTR` that contains the object path of the correct WMI namespace.</span></span> <span data-ttu-id="42a9c-108">参照してください、[解説](#remarks)詳細についてはします。</span><span class="sxs-lookup"><span data-stu-id="42a9c-108">See the [Remarks](#remarks) section for more information.</span></span>

<span data-ttu-id="42a9c-109">`strUser` [in]有効なへのポインター`BSTR`ユーザー名を格納しています。</span><span class="sxs-lookup"><span data-stu-id="42a9c-109">`strUser` [in] A pointer to a valid `BSTR` that contains the user name.</span></span> <span data-ttu-id="42a9c-110">A`null`値が現在のセキュリティ コンテキストを示します。</span><span class="sxs-lookup"><span data-stu-id="42a9c-110">A `null` value indicates the current security context.</span></span> <span data-ttu-id="42a9c-111">場合、ユーザーは、現在の 1 つの異なるドメインから`strUser`円記号で区切られたドメインとユーザー名を含めることもできます。</span><span class="sxs-lookup"><span data-stu-id="42a9c-111">If the user is from a different domain than the current one, `strUser` can also contain the domain and user name separated by a backslash.</span></span> <span data-ttu-id="42a9c-112">`strUser` ユーザー プリンシパル名 (UPN) 書式指定もできます、として suhc  *userName@domainName*します。</span><span class="sxs-lookup"><span data-stu-id="42a9c-112">`strUser` can also be in user principal name (UPN) format, suhc as *userName@domainName*.</span></span> <span data-ttu-id="42a9c-113">参照してください、[解説](#remarks)詳細についてはします。</span><span class="sxs-lookup"><span data-stu-id="42a9c-113">See the [Remarks](#remarks) section for more information.</span></span>

<span data-ttu-id="42a9c-114">`strPassword` [in]有効なへのポインター`BSTR`パスワードを格納しています。</span><span class="sxs-lookup"><span data-stu-id="42a9c-114">`strPassword` [in] A pointer to a valid `BSTR` that contains the password.</span></span> <span data-ttu-id="42a9c-115">A`null`現在のセキュリティ コンテキストを示します。</span><span class="sxs-lookup"><span data-stu-id="42a9c-115">A `null` indicates the current security context.</span></span> <span data-ttu-id="42a9c-116">空の文字列 ("")、有効な長さ 0 のパスワードを示します。</span><span class="sxs-lookup"><span data-stu-id="42a9c-116">An empty string ("") indicates a valid zero-length password.</span></span>

<span data-ttu-id="42a9c-117">`strLocale` [in]有効なへのポインター`BSTR`情報の取得を適切なロケールを示します。</span><span class="sxs-lookup"><span data-stu-id="42a9c-117">`strLocale` [in] A pointer to a valid `BSTR` that indicates the correct locale for information retrieval.</span></span> <span data-ttu-id="42a9c-118">マイクロソフト ロケールの識別子、文字列の形式は"MS\_*xxx*"ここで、 *xxx*文字列がロケール識別子 (LCID) を示す 16 進数形式です。</span><span class="sxs-lookup"><span data-stu-id="42a9c-118">For Microsoft locale identifiers, the format of the string is "MS\_*xxx*", where *xxx* is a string in hexadecimal form that indicates the locale identifier (LCID).</span></span> <span data-ttu-id="42a9c-119">無効なロケールが指定されているかどうか、メソッドを返します`WBEM_E_INVALID_PARAMETER`Windows 7、サーバーの既定のロケールが代わりに使用される場合は除きます。</span><span class="sxs-lookup"><span data-stu-id="42a9c-119">If an invalid locale is specified, the method returns `WBEM_E_INVALID_PARAMETER` except on Windows 7, where the default locale of the server is used instead.</span></span> <span data-ttu-id="42a9c-120">場合 ' null 1、現在のロケールを使用します。</span><span class="sxs-lookup"><span data-stu-id="42a9c-120">If \`null1, the current locale is used.</span></span> 
 
<span data-ttu-id="42a9c-121">`lSecurityFlags` [in]渡すフラグ、`ConnectServerWmi`メソッド。</span><span class="sxs-lookup"><span data-stu-id="42a9c-121">`lSecurityFlags` [in] Flags to pass to the `ConnectServerWmi` method.</span></span> <span data-ttu-id="42a9c-122">このパラメーターにゼロ (0) の値の結果への呼び出しで`ConnectServerWmi`サーバーへの接続が確立された後にのみを返します。</span><span class="sxs-lookup"><span data-stu-id="42a9c-122">A value of zero (0) for this parameter results in the call to `ConnectServerWmi` returning only after a connection to the server is established.</span></span> <span data-ttu-id="42a9c-123">これは、結果、応答していない無期限に、サーバーが切断されたかどうか、アプリケーション。</span><span class="sxs-lookup"><span data-stu-id="42a9c-123">This could result in an application not responding indefinitely if the server is broken.</span></span> <span data-ttu-id="42a9c-124">その他の有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="42a9c-124">The other valid values are:</span></span>

| <span data-ttu-id="42a9c-125">定数</span><span class="sxs-lookup"><span data-stu-id="42a9c-125">Constant</span></span>  | <span data-ttu-id="42a9c-126">値</span><span class="sxs-lookup"><span data-stu-id="42a9c-126">Value</span></span>  | <span data-ttu-id="42a9c-127">説明</span><span class="sxs-lookup"><span data-stu-id="42a9c-127">Description</span></span>  |
|---------|---------|---------|
| `CONNECT_REPOSITORY_ONLY` | <span data-ttu-id="42a9c-128">0x40</span><span class="sxs-lookup"><span data-stu-id="42a9c-128">0x40</span></span> | <span data-ttu-id="42a9c-129">内部使用のために予約されています。</span><span class="sxs-lookup"><span data-stu-id="42a9c-129">Reserved for internal use.</span></span> <span data-ttu-id="42a9c-130">使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="42a9c-130">Do not use.</span></span> |
| `WBEM_FLAG_CONNECT_USE_MAX_WAIT` | <span data-ttu-id="42a9c-131">0x80</span><span class="sxs-lookup"><span data-stu-id="42a9c-131">0x80</span></span> | <span data-ttu-id="42a9c-132">`ConnectServerWmi` 2 分以内に返されます。</span><span class="sxs-lookup"><span data-stu-id="42a9c-132">`ConnectServerWmi` returns in two minutes or less.</span></span> |

<span data-ttu-id="42a9c-133">`strAuthority` [in]ユーザーのドメイン名。</span><span class="sxs-lookup"><span data-stu-id="42a9c-133">`strAuthority` [in] The domain name of the user.</span></span> <span data-ttu-id="42a9c-134">次の値のいずれかを取ります。</span><span class="sxs-lookup"><span data-stu-id="42a9c-134">It can have the following values:</span></span>

| <span data-ttu-id="42a9c-135">[値]</span><span class="sxs-lookup"><span data-stu-id="42a9c-135">Value</span></span> | <span data-ttu-id="42a9c-136">説明</span><span class="sxs-lookup"><span data-stu-id="42a9c-136">Description</span></span> |
|---------|---------|
| <span data-ttu-id="42a9c-137">空白</span><span class="sxs-lookup"><span data-stu-id="42a9c-137">blank</span></span> | <span data-ttu-id="42a9c-138">NTLM 認証を使用して、現在のユーザーの NTLM ドメインが使用されます。</span><span class="sxs-lookup"><span data-stu-id="42a9c-138">NTLM authentication is used, and the NTLM domain of the current user is used.</span></span> <span data-ttu-id="42a9c-139">場合`strUser`ドメイン (推奨される場所) を指定します。 ここで指定しない必要がありますに。</span><span class="sxs-lookup"><span data-stu-id="42a9c-139">If `strUser` specifies the domain (the recommended location), it must not be specified here.</span></span> <span data-ttu-id="42a9c-140">関数を返します`WBEM_E_INVALID_PARAMETER`両方のパラメーターでドメインを指定する場合。</span><span class="sxs-lookup"><span data-stu-id="42a9c-140">The function returns `WBEM_E_INVALID_PARAMETER` if you specify the domain in both parameters.</span></span> |
| <span data-ttu-id="42a9c-141">Kerberos:*プリンシパル名*</span><span class="sxs-lookup"><span data-stu-id="42a9c-141">Kerberos:*principal name*</span></span> | <span data-ttu-id="42a9c-142">Kerberos 認証を使用して、このパラメーターには、Kerberos プリンシパル名が含まれています。</span><span class="sxs-lookup"><span data-stu-id="42a9c-142">Kerberos authentication is used, and this parameter contains a Kerberos principal name.</span></span> |
| <span data-ttu-id="42a9c-143">NTLMDOMAIN:*ドメイン名*</span><span class="sxs-lookup"><span data-stu-id="42a9c-143">NTLMDOMAIN:*domain name*</span></span> | <span data-ttu-id="42a9c-144">NT LAN Manager 認証を使用して、このパラメーターには、NTLM ドメイン名が含まれています。</span><span class="sxs-lookup"><span data-stu-id="42a9c-144">NT LAN Manager authentication is used, and this parameter contains an NTLM domain name.</span></span> |

`pCtx`   
<span data-ttu-id="42a9c-145">[in]このパラメーターは、通常、`null`します。</span><span class="sxs-lookup"><span data-stu-id="42a9c-145">[in] Typically, this parameter is is `null`.</span></span> <span data-ttu-id="42a9c-146">ポインターは、それ以外の場合、 [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext)オブジェクトが 1 つまたは複数の動的クラス プロバイダーが必要です。</span><span class="sxs-lookup"><span data-stu-id="42a9c-146">Otherwise, it is a pointer to an [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) object required by one or more dynamic class providers.</span></span> 

`ppNamespace`  
<span data-ttu-id="42a9c-147">[out]ポインターを受け取る関数が戻るとき、 [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices)オブジェクトを指定した名前空間にバインドします。</span><span class="sxs-lookup"><span data-stu-id="42a9c-147">[out] When the function returns, receives a pointer to an [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) object bound to the specified namespace.</span></span> <span data-ttu-id="42a9c-148">をポイントに設定されている`null`エラーがあるとします。</span><span class="sxs-lookup"><span data-stu-id="42a9c-148">It is set to point to `null` when there is an error.</span></span>

`impLevel`  
<span data-ttu-id="42a9c-149">[in]偽装レベル。</span><span class="sxs-lookup"><span data-stu-id="42a9c-149">[in] The impersonation level.</span></span>

`authLevel`  
<span data-ttu-id="42a9c-150">[in]承認レベル。</span><span class="sxs-lookup"><span data-stu-id="42a9c-150">[in] The authorization level.</span></span>

## <a name="return-value"></a><span data-ttu-id="42a9c-151">戻り値</span><span class="sxs-lookup"><span data-stu-id="42a9c-151">Return value</span></span>

<span data-ttu-id="42a9c-152">この関数によって返される次の値が定義されている、 *WbemCli.h*ヘッダー ファイル、またはすることができますに定数としてコードで定義します。</span><span class="sxs-lookup"><span data-stu-id="42a9c-152">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="42a9c-153">定数</span><span class="sxs-lookup"><span data-stu-id="42a9c-153">Constant</span></span>  |<span data-ttu-id="42a9c-154">値</span><span class="sxs-lookup"><span data-stu-id="42a9c-154">Value</span></span>  |<span data-ttu-id="42a9c-155">説明</span><span class="sxs-lookup"><span data-stu-id="42a9c-155">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="42a9c-156">0x80041001</span><span class="sxs-lookup"><span data-stu-id="42a9c-156">0x80041001</span></span> | <span data-ttu-id="42a9c-157">一般的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="42a9c-157">There has been a general failure.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="42a9c-158">0x80041008</span><span class="sxs-lookup"><span data-stu-id="42a9c-158">0x80041008</span></span> | <span data-ttu-id="42a9c-159">パラメーターが無効です。</span><span class="sxs-lookup"><span data-stu-id="42a9c-159">A parameter is not valid.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="42a9c-160">0x80041006</span><span class="sxs-lookup"><span data-stu-id="42a9c-160">0x80041006</span></span> | <span data-ttu-id="42a9c-161">操作を完了するのに十分なメモリがあります。</span><span class="sxs-lookup"><span data-stu-id="42a9c-161">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="42a9c-162">0</span><span class="sxs-lookup"><span data-stu-id="42a9c-162">0</span></span> | <span data-ttu-id="42a9c-163">関数呼び出しに成功しました。</span><span class="sxs-lookup"><span data-stu-id="42a9c-163">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="42a9c-164">Remarks</span><span class="sxs-lookup"><span data-stu-id="42a9c-164">Remarks</span></span>

<span data-ttu-id="42a9c-165">この関数の呼び出しをラップする、 [IWbemLocator::ConnectServer](https://msdn.microsoft.com/libraryaa391769%28v=vs.85%29.aspx)メソッド。</span><span class="sxs-lookup"><span data-stu-id="42a9c-165">This function wraps a call to the [IWbemLocator::ConnectServer](https://msdn.microsoft.com/libraryaa391769%28v=vs.85%29.aspx) method.</span></span>

 <span data-ttu-id="42a9c-166">既定の名前空間へのローカル アクセスの`strNetworkResource`簡単なオブジェクト パスを指定することができます。"root \default"または"\\.\root\default"。</span><span class="sxs-lookup"><span data-stu-id="42a9c-166">For local access to the default namespace, `strNetworkResource` can be a simple object path: "root\default" or "\\.\root\default".</span></span> <span data-ttu-id="42a9c-167">リモート コンピューター上の既定の名前空間にアクセスするため、COM や Microsoft と互換性のあるネットワークを使用して、コンピューター名を含める:"\\myserver\root\default"。</span><span class="sxs-lookup"><span data-stu-id="42a9c-167">For access to the default namespace on a remote computer using COM or Microsoft-compatible networking, include the computer name: "\\myserver\root\default".</span></span> <span data-ttu-id="42a9c-168">コンピューター名は、DNS 名または IP アドレスを使用することも。</span><span class="sxs-lookup"><span data-stu-id="42a9c-168">The computer name also can be a DNS name or IP address.</span></span> <span data-ttu-id="42a9c-169">`ConnectServerWmi`関数は IPv6 を実行しているコンピューターにも接続できる IPv6 アドレスを使用します。</span><span class="sxs-lookup"><span data-stu-id="42a9c-169">The `ConnectServerWmi` function can also connect with computers running IPv6 using an IPv6 address.</span></span>

<span data-ttu-id="42a9c-170">`strUser` 空の文字列にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="42a9c-170">`strUser` cannot be an empty string.</span></span> <span data-ttu-id="42a9c-171">ドメインがで指定されている場合`strAuthority`、いないも含める必要がありますで`strUser`、関数を返しますまたは`WBEM_E_INVALID_PARAMETER`します。</span><span class="sxs-lookup"><span data-stu-id="42a9c-171">If the domain is specified in `strAuthority`, it must not also be included in `strUser`, or the function returns `WBEM_E_INVALID_PARAMETER`.</span></span>


## <a name="requirements"></a><span data-ttu-id="42a9c-172">要件</span><span class="sxs-lookup"><span data-stu-id="42a9c-172">Requirements</span></span>  
 <span data-ttu-id="42a9c-173">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="42a9c-173">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="42a9c-174">**ヘッダー:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="42a9c-174">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="42a9c-175">**.NET Framework のバージョン:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="42a9c-175">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42a9c-176">関連項目</span><span class="sxs-lookup"><span data-stu-id="42a9c-176">See also</span></span>  
[<span data-ttu-id="42a9c-177">WMI およびパフォーマンス カウンター (アンマネージ API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="42a9c-177">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
