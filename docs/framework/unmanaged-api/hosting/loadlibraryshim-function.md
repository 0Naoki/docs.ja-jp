---
title: LoadLibraryShim 関数
ms.date: 03/30/2017
api_name:
- LoadLibraryShim
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- LoadLibraryShim
helpviewer_keywords:
- LoadLibraryShim function [.NET Framework hosting]
ms.assetid: 30931874-4d0e-4df1-b3d1-e425b50655d1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5fe1ba15f8a9f8ee79582158209049c1e502a61d
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/25/2018
ms.locfileid: "47108729"
---
# <a name="loadlibraryshim-function"></a><span data-ttu-id="cf648-102">LoadLibraryShim 関数</span><span class="sxs-lookup"><span data-stu-id="cf648-102">LoadLibraryShim Function</span></span>
<span data-ttu-id="cf648-103">指定したバージョンの .NET Framework 再頒布可能パッケージに含まれている DLL を読み込みます。</span><span class="sxs-lookup"><span data-stu-id="cf648-103">Loads a specified version of a DLL that is included in the .NET Framework redistributable package.</span></span>  
  
 <span data-ttu-id="cf648-104">この関数は、[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] では非推奨とされました。</span><span class="sxs-lookup"><span data-stu-id="cf648-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span> <span data-ttu-id="cf648-105">使用して、 [iclrruntimeinfo::loadlibrary](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-loadlibrary-method.md)メソッド代わりにします。</span><span class="sxs-lookup"><span data-stu-id="cf648-105">Use the [ICLRRuntimeInfo::LoadLibrary](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-loadlibrary-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf648-106">構文</span><span class="sxs-lookup"><span data-stu-id="cf648-106">Syntax</span></span>  
  
```  
HRESULT LoadLibraryShim (  
    [in]  LPCWSTR  szDllName,  
    [in]  LPCWSTR  szVersion,  
          LPVOID   pvReserved,  
    [out] HMODULE *phModDll  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cf648-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="cf648-107">Parameters</span></span>  
 `szDllName`  
 <span data-ttu-id="cf648-108">[in].NET Framework ライブラリから読み込まれる DLL の名前を表す、0 で終わる文字列。</span><span class="sxs-lookup"><span data-stu-id="cf648-108">[in] A zero-terminated string that represents the name of the DLL to be loaded from the .NET Framework library.</span></span>  
  
 `szVersion`  
 <span data-ttu-id="cf648-109">[in]読み込まれる DLL のバージョンを表す、0 で終わる文字列。</span><span class="sxs-lookup"><span data-stu-id="cf648-109">[in] A zero-terminated string that represents the version of the DLL to be loaded.</span></span> <span data-ttu-id="cf648-110">場合`szVersion`読み込みはバージョン 4 未満である指定された DLL の最新バージョンを選択したバージョンは null です。</span><span class="sxs-lookup"><span data-stu-id="cf648-110">If `szVersion` is null, the version selected for loading is the latest version of the specified DLL that is less than version 4.</span></span> <span data-ttu-id="cf648-111">場合は、バージョン 4 以上のすべてのバージョンは無視されます`szVersion`が null の場合と、version 4 より前のバージョンがインストールされていない場合、DLL の読み込みに失敗します。</span><span class="sxs-lookup"><span data-stu-id="cf648-111">That is, all versions equal to or greater than version 4 are ignored if `szVersion` is null, and if no version less than version 4 is installed, the DLL fails to load.</span></span> <span data-ttu-id="cf648-112">インストールを確認します。 これは、[!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]の既存のアプリケーションやコンポーネントには影響しません。</span><span class="sxs-lookup"><span data-stu-id="cf648-112">This is to ensure that installation of the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] does not affect pre-existing applications or components.</span></span> <span data-ttu-id="cf648-113">エントリを参照してください。[インプロセス SxS と移行のクイック スタート](https://go.microsoft.com/fwlink/?LinkId=200329)CLR チームのブログにします。</span><span class="sxs-lookup"><span data-stu-id="cf648-113">See the entry [In-Proc SxS and Migration Quick Start](https://go.microsoft.com/fwlink/?LinkId=200329) in the CLR team blog.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="cf648-114">将来使用するために予約されています。</span><span class="sxs-lookup"><span data-stu-id="cf648-114">Reserved for future use.</span></span>  
  
 `phModDll`  
 <span data-ttu-id="cf648-115">[out]モジュールのハンドルへのポインター。</span><span class="sxs-lookup"><span data-stu-id="cf648-115">[out] A pointer to the handle of the module.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cf648-116">戻り値</span><span class="sxs-lookup"><span data-stu-id="cf648-116">Return Value</span></span>  
 <span data-ttu-id="cf648-117">このメソッドは、次の値だけでなく、WinError.h で定義されている標準のコンポーネント オブジェクト モデル (COM) エラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="cf648-117">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="cf648-118">リターン コード</span><span class="sxs-lookup"><span data-stu-id="cf648-118">Return code</span></span>|<span data-ttu-id="cf648-119">説明</span><span class="sxs-lookup"><span data-stu-id="cf648-119">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="cf648-120">S_OK</span><span class="sxs-lookup"><span data-stu-id="cf648-120">S_OK</span></span>|<span data-ttu-id="cf648-121">メソッドは正常に完了しました。</span><span class="sxs-lookup"><span data-stu-id="cf648-121">The method completed successfully.</span></span>|  
|<span data-ttu-id="cf648-122">CLR_E_SHIM_RUNTIMELOAD</span><span class="sxs-lookup"><span data-stu-id="cf648-122">CLR_E_SHIM_RUNTIMELOAD</span></span>|<span data-ttu-id="cf648-123">読み込み`szDllName`共通言語ランタイム (CLR) と必要なバージョンの CLR を読み込めません。 読み込む必要があります。</span><span class="sxs-lookup"><span data-stu-id="cf648-123">Loading `szDllName` requires loading the common language runtime (CLR), and the necessary version of the CLR cannot be loaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cf648-124">Remarks</span><span class="sxs-lookup"><span data-stu-id="cf648-124">Remarks</span></span>  
 <span data-ttu-id="cf648-125">この関数は、.NET Framework 再頒布可能パッケージに含まれている Dll の読み込みに使用されます。</span><span class="sxs-lookup"><span data-stu-id="cf648-125">This function is used to load DLLs that are included in the .NET Framework redistributable package.</span></span> <span data-ttu-id="cf648-126">ユーザーが生成した Dll は読み込まれません。</span><span class="sxs-lookup"><span data-stu-id="cf648-126">It does not load user-generated DLLs.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cf648-127">以降、.NET Framework version 2.0 と、読み込まれる CLR Fusion.dll を読み込むとします。</span><span class="sxs-lookup"><span data-stu-id="cf648-127">Beginning with the .NET Framework version 2.0, loading Fusion.dll causes the CLR to be loaded.</span></span> <span data-ttu-id="cf648-128">Fusion.dll で関数が、ラッパーが、この実装は、ランタイムによって提供されるためです。</span><span class="sxs-lookup"><span data-stu-id="cf648-128">This is because the functions in Fusion.dll are now wrappers whose implementations are provided by the runtime.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cf648-129">要件</span><span class="sxs-lookup"><span data-stu-id="cf648-129">Requirements</span></span>  
 <span data-ttu-id="cf648-130">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cf648-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cf648-131">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="cf648-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="cf648-132">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cf648-132">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf648-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="cf648-133">See Also</span></span>  
 [<span data-ttu-id="cf648-134">非推奨の CLR ホスト関数</span><span class="sxs-lookup"><span data-stu-id="cf648-134">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
