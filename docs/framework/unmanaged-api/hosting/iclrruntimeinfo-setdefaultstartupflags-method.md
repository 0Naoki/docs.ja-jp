---
title: ICLRRuntimeInfo::SetDefaultStartupFlags メソッド
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.SetDefaultStartupFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::SetDefaultStartupFlags
helpviewer_keywords:
- ICLRRuntimeInfo::SetDefaultStartupFlags method [.NET Framework hosting]
- SetDefaultStartupFlags method [.NET Framework hosting]
ms.assetid: 98ae174f-bff0-48f1-9e05-6cb63b451824
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 440f2f7c542c697b3d817c988211303c60073979
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57492362"
---
# <a name="iclrruntimeinfosetdefaultstartupflags-method"></a><span data-ttu-id="7c0f4-102">ICLRRuntimeInfo::SetDefaultStartupFlags メソッド</span><span class="sxs-lookup"><span data-stu-id="7c0f4-102">ICLRRuntimeInfo::SetDefaultStartupFlags Method</span></span>
<span data-ttu-id="7c0f4-103">スタートアップ フラグとランタイムの起動に使用されるホストの構成ファイルを設定します。</span><span class="sxs-lookup"><span data-stu-id="7c0f4-103">Sets the startup flags and the host configuration file that will be used to start the runtime.</span></span> <span data-ttu-id="7c0f4-104">このメソッドの使用よりも優先されます、`startupFlags`パラメーター、 [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)と[CorBindToRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md)関数。</span><span class="sxs-lookup"><span data-stu-id="7c0f4-104">This method supersedes the use of the `startupFlags` parameter in the [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) and [CorBindToRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md) functions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c0f4-105">構文</span><span class="sxs-lookup"><span data-stu-id="7c0f4-105">Syntax</span></span>  
  
```  
HRESULT SetDefaultStartupFlags(  
           [in]  DWORD dwStartupFlags,  
           [in]  LPCWSTR pwzHostConfigFile);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7c0f4-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="7c0f4-106">Parameters</span></span>  
 `dwStartupFlags`  
 <span data-ttu-id="7c0f4-107">[in]設定するホストのスタートアップ フラグ。</span><span class="sxs-lookup"><span data-stu-id="7c0f4-107">[in] The host startup flags to set.</span></span> <span data-ttu-id="7c0f4-108">使用したのと同じフラグを使用して、 [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)と[CorBindToRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md)関数。</span><span class="sxs-lookup"><span data-stu-id="7c0f4-108">Use the same flags as with the [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) and [CorBindToRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md) functions.</span></span>  
  
 `pwzHostConfigFile`  
 <span data-ttu-id="7c0f4-109">[in]設定するホストの構成ファイルのディレクトリ パス。</span><span class="sxs-lookup"><span data-stu-id="7c0f4-109">[in] The directory path of the host configuration file to set.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7c0f4-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="7c0f4-110">Return Value</span></span>  
 <span data-ttu-id="7c0f4-111">このメソッドは、次の特定の HRESULT を返します。 メソッドの失敗を示す HRESULT エラーとします。</span><span class="sxs-lookup"><span data-stu-id="7c0f4-111">This method returns the following specific HRESULT as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="7c0f4-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7c0f4-112">HRESULT</span></span>|<span data-ttu-id="7c0f4-113">説明</span><span class="sxs-lookup"><span data-stu-id="7c0f4-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7c0f4-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="7c0f4-114">S_OK</span></span>|<span data-ttu-id="7c0f4-115">メソッドは正常に完了しました。</span><span class="sxs-lookup"><span data-stu-id="7c0f4-115">The method completed successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7c0f4-116">Remarks</span><span class="sxs-lookup"><span data-stu-id="7c0f4-116">Remarks</span></span>  
 <span data-ttu-id="7c0f4-117">マルチ スレッドのホストには、このメソッドの呼び出しを同期する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7c0f4-117">A multithreaded host should synchronize calls to this method.</span></span> <span data-ttu-id="7c0f4-118">それ以外の場合、スレッド A が呼び出すことができます、`SetStartupFlags`スレッド B への呼び出しの完了後に、`SetStartupFlags`スレッド B が、ランタイムを開始する前にします。</span><span class="sxs-lookup"><span data-stu-id="7c0f4-118">Otherwise, thread A might call the `SetStartupFlags` method after thread B completes a call to `SetStartupFlags` and before thread B starts the runtime.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7c0f4-119">必要条件</span><span class="sxs-lookup"><span data-stu-id="7c0f4-119">Requirements</span></span>  
 <span data-ttu-id="7c0f4-120">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7c0f4-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7c0f4-121">**ヘッダー:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="7c0f4-121">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="7c0f4-122">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="7c0f4-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7c0f4-123">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c0f4-123">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c0f4-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="7c0f4-124">See also</span></span>
- [<span data-ttu-id="7c0f4-125">ICLRRuntimeInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7c0f4-125">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [<span data-ttu-id="7c0f4-126">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7c0f4-126">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="7c0f4-127">ホスティング</span><span class="sxs-lookup"><span data-stu-id="7c0f4-127">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
