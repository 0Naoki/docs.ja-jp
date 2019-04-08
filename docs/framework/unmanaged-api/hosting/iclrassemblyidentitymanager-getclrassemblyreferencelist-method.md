---
title: ICLRAssemblyIdentityManager::GetCLRAssemblyReferenceList メソッド
ms.date: 03/30/2017
api_name:
- ICLRAssemblyIdentityManager.GetCLRAssemblyReferenceList
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyIdentityManager::GetCLRAssemblyReferenceList
helpviewer_keywords:
- GetClrAssemblyReferenceList method [.NET Framework hosting]
- ICLRAssemblyIdentityManager::GetCLRAssemblyReferenceList method [.NET Framework hosting]
ms.assetid: cb5ffae5-287b-4a87-9ca8-7ce3ae0601b7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: de166a22350e49197ff6a5b5d6dc956cdcc2d1ac
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59089511"
---
# <a name="iclrassemblyidentitymanagergetclrassemblyreferencelist-method"></a><span data-ttu-id="95250-102">ICLRAssemblyIdentityManager::GetCLRAssemblyReferenceList メソッド</span><span class="sxs-lookup"><span data-stu-id="95250-102">ICLRAssemblyIdentityManager::GetCLRAssemblyReferenceList Method</span></span>
<span data-ttu-id="95250-103">インターフェイス ポインターを取得、 [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)部分的なアセンブリ id の指定されたリストからのインスタンス。</span><span class="sxs-lookup"><span data-stu-id="95250-103">Gets an interface pointer to an [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) instance from the supplied list of partial assembly identities.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95250-104">構文</span><span class="sxs-lookup"><span data-stu-id="95250-104">Syntax</span></span>  
  
```  
HRESULT  GetCLRAssemblyReferenceList (  
    [in] LPCWSTR *ppwzAssemblyReferences,  
    [in] DWORD    dwNumOfReferences,  
    [out] ICLRAssemblyReferenceList **ppReferenceList  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="95250-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="95250-105">Parameters</span></span>  
 `ppwzAssemblyReferences`  
 <span data-ttu-id="95250-106">[in]フォームでの null で終わる文字列の配列"プロパティの名前 = value…"部分的なアセンブリ id の一覧を指定するとします。</span><span class="sxs-lookup"><span data-stu-id="95250-106">[in] An array of null-terminated strings in the form "name, property=value..." that specify a list of partial assembly identities.</span></span>  
  
 `dwNumOfReferences`  
 <span data-ttu-id="95250-107">[in]内の項目数`ppwzAssemblyReferences`します。</span><span class="sxs-lookup"><span data-stu-id="95250-107">[in] The number of items in `ppwzAssemblyReferences`.</span></span>  
  
 `ppReferenceList`  
 <span data-ttu-id="95250-108">[out]インターフェイス ポインターを`ICLRAssemblyReferenceList`で指定されたアセンブリの一覧については、アセンブリの id データを格納しているオブジェクト`ppwzAssemblyReferences`します。</span><span class="sxs-lookup"><span data-stu-id="95250-108">[out] An interface pointer to an `ICLRAssemblyReferenceList` object that contains the assembly identity data for the list of assemblies specified in `ppwzAssemblyReferences`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="95250-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="95250-109">Return Value</span></span>  
  
|<span data-ttu-id="95250-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="95250-110">HRESULT</span></span>|<span data-ttu-id="95250-111">説明</span><span class="sxs-lookup"><span data-stu-id="95250-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="95250-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="95250-112">S_OK</span></span>|<span data-ttu-id="95250-113">メソッドが正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="95250-113">The method returned successfully.</span></span>|  
|<span data-ttu-id="95250-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="95250-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="95250-115">共通言語ランタイム (CLR) は、プロセスに読み込まれていないか、CLR は状態をマネージ コードを実行または呼び出しを正常に処理ができません。</span><span class="sxs-lookup"><span data-stu-id="95250-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="95250-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="95250-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="95250-117">呼び出しがタイムアウトになりました。</span><span class="sxs-lookup"><span data-stu-id="95250-117">The call timed out.</span></span>|  
|<span data-ttu-id="95250-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="95250-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="95250-119">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="95250-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="95250-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="95250-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="95250-121">イベントがキャンセルされましたブロックされたスレッドまたはファイバーが待機しています。</span><span class="sxs-lookup"><span data-stu-id="95250-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="95250-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="95250-122">E_FAIL</span></span>|<span data-ttu-id="95250-123">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="95250-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="95250-124">メソッドから E_FAIL が返された場合、CLR は、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="95250-124">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="95250-125">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="95250-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="95250-126">必要条件</span><span class="sxs-lookup"><span data-stu-id="95250-126">Requirements</span></span>  
 <span data-ttu-id="95250-127">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="95250-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="95250-128">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="95250-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="95250-129">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="95250-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="95250-130">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="95250-130">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="95250-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="95250-131">See also</span></span>

- [<span data-ttu-id="95250-132">ICLRAssemblyIdentityManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="95250-132">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="95250-133">ICLRAssemblyReferenceList インターフェイス</span><span class="sxs-lookup"><span data-stu-id="95250-133">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
