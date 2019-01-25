---
title: ICLRMetaHost::QueryLegacyV2RuntimeBinding メソッド
ms.date: 03/30/2017
api_name:
- ICLRMetaHost.RequestRuntimeLoadedNotification
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost::QueryLegacyV2RuntimeBinding
helpviewer_keywords:
- QueryLegacyV2RuntimeBinding method [.NET Framework hosting]
- ICLRMetaHost::QueryLegacyV2RuntimeBinding method [.NET Framework hosting]
ms.assetid: 9929817e-acc9-40b7-960c-598664e04b60
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dd58d38e92f492522008745384459045e007c3ae
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54646842"
---
# <a name="iclrmetahostquerylegacyv2runtimebinding-method"></a><span data-ttu-id="12fd2-102">ICLRMetaHost::QueryLegacyV2RuntimeBinding メソッド</span><span class="sxs-lookup"><span data-stu-id="12fd2-102">ICLRMetaHost::QueryLegacyV2RuntimeBinding Method</span></span>
<span data-ttu-id="12fd2-103">レガシ アクティブ化ポリシーが関連付けられてなどを使用してランタイムを表すインターフェイスを返します、`useLegacyV2RuntimeActivationPolicy`属性を[ \<startup > 要素](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)ダイレクトを使用して、構成ファイルのエントリレガシ アクティブ化 Api、または呼び出すことによって、 [iclrruntimeinfo::bindaslegacyv2runtime](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-bindaslegacyv2runtime-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="12fd2-103">Returns an interface that represents a runtime to which legacy activation policy has been bound, for example, by using the `useLegacyV2RuntimeActivationPolicy` attribute on the [\<startup> element](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) configuration file entry, by direct use of the legacy activation APIs, or by calling the [ICLRRuntimeInfo::BindAsLegacyV2Runtime](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-bindaslegacyv2runtime-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="12fd2-104">構文</span><span class="sxs-lookup"><span data-stu-id="12fd2-104">Syntax</span></span>  
  
```  
HRESULT QueryLegacyV2RuntimeBinding (  
    [in] REFIID riid,  
    [out, iid_is(riid), retval] LPVOID *ppUnk);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="12fd2-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="12fd2-105">Parameters</span></span>  
 `riid`  
 <span data-ttu-id="12fd2-106">[in]このパラメーターの唯一の有効な値は Required.Currently`IID_ICLRRuntimeInfo`します。</span><span class="sxs-lookup"><span data-stu-id="12fd2-106">[in] Required.Currently the only valid value for this parameter is `IID_ICLRRuntimeInfo`.</span></span>  
  
 `ppUnk`  
 <span data-ttu-id="12fd2-107">[out] 必須。</span><span class="sxs-lookup"><span data-stu-id="12fd2-107">[out] Required.</span></span> <span data-ttu-id="12fd2-108">このメソッドから制御が戻るときにへのポインターを格納、 [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)レガシ アクティブ化ポリシーにバインドされているランタイムを表すインターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="12fd2-108">When this method returns, contains a pointer to the [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface that represents a runtime that has been bound to legacy activation policy.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="12fd2-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="12fd2-109">Return Value</span></span>  
 <span data-ttu-id="12fd2-110">このメソッドは、次の特定の HRESULT と、メソッドの失敗を示す HRESULT エラーも返します。</span><span class="sxs-lookup"><span data-stu-id="12fd2-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="12fd2-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="12fd2-111">HRESULT</span></span>|<span data-ttu-id="12fd2-112">説明</span><span class="sxs-lookup"><span data-stu-id="12fd2-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="12fd2-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="12fd2-113">S_OK</span></span>|<span data-ttu-id="12fd2-114">メソッドは正常に完了し、レガシ アクティブ化ポリシーにバインドされているランタイムが返されました。</span><span class="sxs-lookup"><span data-stu-id="12fd2-114">The method completed successfully and returned a runtime that was bound to legacy activation policy.</span></span>|  
|<span data-ttu-id="12fd2-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="12fd2-115">S_FALSE</span></span>|<span data-ttu-id="12fd2-116">メソッドは正常に完了しましたが、レガシ ランタイムはまだバインドされていません。</span><span class="sxs-lookup"><span data-stu-id="12fd2-116">The method completed successfully, but a legacy runtime has not yet been bound.</span></span>|  
|<span data-ttu-id="12fd2-117">E_NOINTERFACE</span><span class="sxs-lookup"><span data-stu-id="12fd2-117">E_NOINTERFACE</span></span>|<span data-ttu-id="12fd2-118">メソッドで、レガシ アクティブ化ポリシーにバインドされているランタイムが見つかりましたが、`riid` はそのランタイムでサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="12fd2-118">The method found a runtime that was bound to legacy activation policy, but `riid` is not supported by that runtime.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="12fd2-119">Remarks</span><span class="sxs-lookup"><span data-stu-id="12fd2-119">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="12fd2-120">必要条件</span><span class="sxs-lookup"><span data-stu-id="12fd2-120">Requirements</span></span>  
 <span data-ttu-id="12fd2-121">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="12fd2-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="12fd2-122">**ヘッダー:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="12fd2-122">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="12fd2-123">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="12fd2-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="12fd2-124">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="12fd2-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12fd2-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="12fd2-125">See also</span></span>
- [<span data-ttu-id="12fd2-126">ICLRMetaHost インターフェイス</span><span class="sxs-lookup"><span data-stu-id="12fd2-126">ICLRMetaHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)
- [<span data-ttu-id="12fd2-127">ホスティング</span><span class="sxs-lookup"><span data-stu-id="12fd2-127">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
