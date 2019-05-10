---
title: GetRequestedRuntimeInfo 関数
ms.date: 03/30/2017
api_name:
- GetRequestedRuntimeInfo
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- GetRequestedRuntimeInfo
helpviewer_keywords:
- GetRequestedRuntimeInfo function [.NET Framework hosting]
ms.assetid: 0dfd7cdc-c116-4e25-b56a-ac7b0378c942
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a440cef9de12c420e7b49b794ed0bcba39e756e8
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64665072"
---
# <a name="getrequestedruntimeinfo-function"></a><span data-ttu-id="a9bef-102">GetRequestedRuntimeInfo 関数</span><span class="sxs-lookup"><span data-stu-id="a9bef-102">GetRequestedRuntimeInfo Function</span></span>
<span data-ttu-id="a9bef-103">アプリケーションによって要求された共通言語ランタイム (CLR) のバージョンとディレクトリ情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="a9bef-103">Gets version and directory information about the common language runtime (CLR) requested by an application.</span></span>  
  
 <span data-ttu-id="a9bef-104">この関数は、[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] では非推奨とされました。</span><span class="sxs-lookup"><span data-stu-id="a9bef-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9bef-105">構文</span><span class="sxs-lookup"><span data-stu-id="a9bef-105">Syntax</span></span>  
  
```  
HRESULT GetRequestedRuntimeInfo (  
    [in]  LPCWSTR  pExe,   
    [in]  LPCWSTR  pwszVersion,   
    [in]  LPCWSTR  pConfigurationFile,   
    [in]  DWORD    startupFlags,   
    [in]  DWORD    runtimeInfoFlags,   
    [out] LPWSTR   pDirectory,   
    [in]  DWORD    dwDirectory,   
    [out] DWORD   *dwDirectoryLength,   
    [out] LPWSTR   pVersion,   
    [in]  DWORD    cchBuffer,   
    [out] DWORD   *dwlength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a9bef-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a9bef-106">Parameters</span></span>  
 `pExe`  
 <span data-ttu-id="a9bef-107">[in]アプリケーションの名前。</span><span class="sxs-lookup"><span data-stu-id="a9bef-107">[in] The name of the application.</span></span>  
  
 `pwszVersion`  
 <span data-ttu-id="a9bef-108">[in]ランタイムのバージョン番号を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="a9bef-108">[in] A string specifying the version number of the runtime.</span></span>  
  
 `pConfigurationFile`  
 <span data-ttu-id="a9bef-109">[in]関連付けられている構成ファイルの名前`pExe`します。</span><span class="sxs-lookup"><span data-stu-id="a9bef-109">[in] The name of the configuration file that is associated with `pExe`.</span></span>  
  
 `startupFlags`  
 <span data-ttu-id="a9bef-110">[in]1 つ以上の[STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md)列挙値。</span><span class="sxs-lookup"><span data-stu-id="a9bef-110">[in] One or more of the [STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) enumeration values.</span></span>  
  
 `runtimeInfoFlags`  
 <span data-ttu-id="a9bef-111">[in]1 つ以上の[RUNTIME_INFO_FLAGS](../../../../docs/framework/unmanaged-api/hosting/runtime-info-flags-enumeration.md)列挙値。</span><span class="sxs-lookup"><span data-stu-id="a9bef-111">[in] One or more of the [RUNTIME_INFO_FLAGS](../../../../docs/framework/unmanaged-api/hosting/runtime-info-flags-enumeration.md) enumeration values.</span></span>  
  
 `pDirectory`  
 <span data-ttu-id="a9bef-112">[out]正常完了時にランタイムのディレクトリ パスを格納するバッファー。</span><span class="sxs-lookup"><span data-stu-id="a9bef-112">[out] A buffer that contains the directory path to the runtime upon successful completion.</span></span>  
  
 `dwDirectory`  
 <span data-ttu-id="a9bef-113">[in]ディレクトリのバッファーの長さ。</span><span class="sxs-lookup"><span data-stu-id="a9bef-113">[in] The length of the directory buffer.</span></span>  
  
 `dwDirectoryLength`  
 <span data-ttu-id="a9bef-114">[out]ディレクトリのパス文字列の長さへのポインター。</span><span class="sxs-lookup"><span data-stu-id="a9bef-114">[out] A pointer to the length of the directory path string.</span></span>  
  
 `pVersion`  
 <span data-ttu-id="a9bef-115">[out]正常完了時にランタイムのバージョン番号を格納するバッファー。</span><span class="sxs-lookup"><span data-stu-id="a9bef-115">[out] A buffer that contains the version number of the runtime upon successful completion.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="a9bef-116">[in]バージョンの文字列バッファーの長さ。</span><span class="sxs-lookup"><span data-stu-id="a9bef-116">[in] The length of the version string buffer.</span></span>  
  
 `dwlength`  
 <span data-ttu-id="a9bef-117">[out]バージョン文字列の長さへのポインター。</span><span class="sxs-lookup"><span data-stu-id="a9bef-117">[out] A pointer to the length of the version string.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a9bef-118">戻り値</span><span class="sxs-lookup"><span data-stu-id="a9bef-118">Return Value</span></span>  
 <span data-ttu-id="a9bef-119">このメソッドは、次の値だけでなく、WinError.h で定義されている標準のコンポーネント オブジェクト モデル (COM) エラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="a9bef-119">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="a9bef-120">リターン コード</span><span class="sxs-lookup"><span data-stu-id="a9bef-120">Return code</span></span>|<span data-ttu-id="a9bef-121">説明</span><span class="sxs-lookup"><span data-stu-id="a9bef-121">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="a9bef-122">S_OK</span><span class="sxs-lookup"><span data-stu-id="a9bef-122">S_OK</span></span>|<span data-ttu-id="a9bef-123">メソッドは正常に完了しました。</span><span class="sxs-lookup"><span data-stu-id="a9bef-123">The method completed successfully.</span></span>|  
|<span data-ttu-id="a9bef-124">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="a9bef-124">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="a9bef-125">ディレクトリ バッファーは、ディレクトリ パスを格納するのに十分な大きさではありません。</span><span class="sxs-lookup"><span data-stu-id="a9bef-125">The directory buffer is not large enough to store the directory path.</span></span><br /><br /> <span data-ttu-id="a9bef-126">または</span><span class="sxs-lookup"><span data-stu-id="a9bef-126">- or -</span></span><br /><br /> <span data-ttu-id="a9bef-127">バージョン バッファーは、バージョン文字列を格納するのに十分な大きさではありません。</span><span class="sxs-lookup"><span data-stu-id="a9bef-127">The version buffer is not large enough to store the version string.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a9bef-128">Remarks</span><span class="sxs-lookup"><span data-stu-id="a9bef-128">Remarks</span></span>  
 <span data-ttu-id="a9bef-129">`GetRequestedRuntimeInfo`メソッドは必ずしもコンピューターにインストールされている最新バージョンではないと、プロセスに読み込まれたバージョンに関する実行時の情報を返します。</span><span class="sxs-lookup"><span data-stu-id="a9bef-129">The `GetRequestedRuntimeInfo` method returns run-time information about the version loaded into the process, which is not necessarily the latest version installed on the computer.</span></span>  
  
 <span data-ttu-id="a9bef-130">.NET Framework version 2.0 を使用している最新のバージョンに関する情報を取得できます、`GetRequestedRuntimeInfo`メソッドとして、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="a9bef-130">In the .NET Framework version 2.0, you can get information about the latest installed version by using the `GetRequestedRuntimeInfo` method as follows:</span></span>  
  
- <span data-ttu-id="a9bef-131">指定、 `pExe`、 `pwszVersion`、および`pConfigurationFile`パラメーターを null として。</span><span class="sxs-lookup"><span data-stu-id="a9bef-131">Specify the `pExe`, `pwszVersion`, and `pConfigurationFile` parameters as null.</span></span>  
  
- <span data-ttu-id="a9bef-132">RUNTIME_INFO_UPGRADE_VERSION フラグを指定、`RUNTIME_INFO_FLAGS`の列挙体、`runtimeInfoFlags`パラメーター。</span><span class="sxs-lookup"><span data-stu-id="a9bef-132">Specify the RUNTIME_INFO_UPGRADE_VERSION flag in the `RUNTIME_INFO_FLAGS` enumerations for the `runtimeInfoFlags` parameter.</span></span>  
  
 <span data-ttu-id="a9bef-133">`GetRequestedRuntimeInfo`メソッドでは、次の状況では、最新の CLR バージョンは返しません。</span><span class="sxs-lookup"><span data-stu-id="a9bef-133">The `GetRequestedRuntimeInfo` method does not return the latest CLR version in the following circumstances:</span></span>  
  
- <span data-ttu-id="a9bef-134">特定の CLR バージョンの読み込みを指定するアプリケーション構成ファイルが存在します。</span><span class="sxs-lookup"><span data-stu-id="a9bef-134">An application configuration file that specifies loading a particular CLR version exists.</span></span> <span data-ttu-id="a9bef-135">Null を指定した場合でも、.NET Framework は構成ファイルを使用ことに注意してください、`pConfigurationFile`パラメーター。</span><span class="sxs-lookup"><span data-stu-id="a9bef-135">Note that the .NET Framework will use the configuration file even if you specify null for the `pConfigurationFile` parameter.</span></span>  
  
- <span data-ttu-id="a9bef-136">[CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) CLR の以前のバージョンを指定するメソッドが呼び出されました。</span><span class="sxs-lookup"><span data-stu-id="a9bef-136">The [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) method was called specifying an earlier CLR version.</span></span>  
  
- <span data-ttu-id="a9bef-137">CLR の以前のバージョン用にコンパイルされたアプリケーションは現在実行中です。</span><span class="sxs-lookup"><span data-stu-id="a9bef-137">An application that was compiled for an earlier CLR version is currently running.</span></span>  
  
 <span data-ttu-id="a9bef-138">`runtimeInfoFlags`パラメーターを指定できますアーキテクチャの定数の 1 つだけ、`RUNTIME_INFO_FLAGS`一度に列挙体。</span><span class="sxs-lookup"><span data-stu-id="a9bef-138">For the `runtimeInfoFlags` parameter, you can specify only one of the architecture constants of the `RUNTIME_INFO_FLAGS` enumeration at a time:</span></span>  
  
- <span data-ttu-id="a9bef-139">RUNTIME_INFO_REQUEST_IA64</span><span class="sxs-lookup"><span data-stu-id="a9bef-139">RUNTIME_INFO_REQUEST_IA64</span></span>  
  
- <span data-ttu-id="a9bef-140">RUNTIME_INFO_REQUEST_AMD64</span><span class="sxs-lookup"><span data-stu-id="a9bef-140">RUNTIME_INFO_REQUEST_AMD64</span></span>  
  
- <span data-ttu-id="a9bef-141">RUNTIME_INFO_REQUEST_X86</span><span class="sxs-lookup"><span data-stu-id="a9bef-141">RUNTIME_INFO_REQUEST_X86</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a9bef-142">必要条件</span><span class="sxs-lookup"><span data-stu-id="a9bef-142">Requirements</span></span>  
 <span data-ttu-id="a9bef-143">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a9bef-143">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a9bef-144">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a9bef-144">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a9bef-145">**ライブラリ:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a9bef-145">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a9bef-146">**.NET Framework のバージョン:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a9bef-146">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9bef-147">関連項目</span><span class="sxs-lookup"><span data-stu-id="a9bef-147">See also</span></span>

- [<span data-ttu-id="a9bef-148">GetRequestedRuntimeVersion 関数</span><span class="sxs-lookup"><span data-stu-id="a9bef-148">GetRequestedRuntimeVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md)
- [<span data-ttu-id="a9bef-149">GetVersionFromProcess 関数</span><span class="sxs-lookup"><span data-stu-id="a9bef-149">GetVersionFromProcess Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md)
- [<span data-ttu-id="a9bef-150">非推奨の CLR ホスト関数</span><span class="sxs-lookup"><span data-stu-id="a9bef-150">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
