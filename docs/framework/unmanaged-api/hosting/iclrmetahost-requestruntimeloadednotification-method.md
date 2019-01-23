---
title: ICLRMetaHost::RequestRuntimeLoadedNotification メソッド
ms.date: 03/30/2017
api_name:
- ICLRMetaHost.RequestRuntimeLoadedNotification
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost::RequestRuntimeLoadedNotification
helpviewer_keywords:
- RequestRuntimeLoadedNotification method [.NET Framework hosting]
- ICLRMetaHost::RequestRuntimeLoadedNotification method [.NET Framework hosting]
ms.assetid: 0d5ccc4d-0193-41f5-af54-45d7b70d5321
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0f3ac053f12cb4bc37ab0bd16036fb561f8f176c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54519126"
---
# <a name="iclrmetahostrequestruntimeloadednotification-method"></a><span data-ttu-id="5123c-102">ICLRMetaHost::RequestRuntimeLoadedNotification メソッド</span><span class="sxs-lookup"><span data-stu-id="5123c-102">ICLRMetaHost::RequestRuntimeLoadedNotification Method</span></span>
<span data-ttu-id="5123c-103">共通言語ランタイム (CLR) バージョンが初めて読み込まれるが、開始していないときに呼び出されることが保証されるコールバック関数を提供します。</span><span class="sxs-lookup"><span data-stu-id="5123c-103">Provides a callback function that is guaranteed to be called when a common language runtime (CLR) version is first loaded, but not yet started.</span></span> <span data-ttu-id="5123c-104">このメソッドは、 [LockClrVersion](../../../../docs/framework/unmanaged-api/hosting/lockclrversion-function.md)関数。</span><span class="sxs-lookup"><span data-stu-id="5123c-104">This method supersedes the [LockClrVersion](../../../../docs/framework/unmanaged-api/hosting/lockclrversion-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5123c-105">構文</span><span class="sxs-lookup"><span data-stu-id="5123c-105">Syntax</span></span>  
  
```  
HRESULT RequestRuntimeLoadedNotification (  
    [in] RuntimeLoadedCallbackFnPtr pCallbackFunction);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5123c-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5123c-106">Parameters</span></span>  
 `pCallbackFunction`  
 <span data-ttu-id="5123c-107">[in]新しいランタイムが読み込まれたときに呼び出されるコールバック関数。</span><span class="sxs-lookup"><span data-stu-id="5123c-107">[in] The callback function that is invoked when a new runtime has been loaded.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5123c-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="5123c-108">Return Value</span></span>  
 <span data-ttu-id="5123c-109">このメソッドは、次の特定の HRESULT と、メソッドの失敗を示す HRESULT エラーも返します。</span><span class="sxs-lookup"><span data-stu-id="5123c-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="5123c-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5123c-110">HRESULT</span></span>|<span data-ttu-id="5123c-111">説明</span><span class="sxs-lookup"><span data-stu-id="5123c-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5123c-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="5123c-112">S_OK</span></span>|<span data-ttu-id="5123c-113">メソッドは正常に完了しました。</span><span class="sxs-lookup"><span data-stu-id="5123c-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="5123c-114">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="5123c-114">E_POINTER</span></span>|<span data-ttu-id="5123c-115">`pCallbackFunction` が null です。</span><span class="sxs-lookup"><span data-stu-id="5123c-115">`pCallbackFunction` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5123c-116">Remarks</span><span class="sxs-lookup"><span data-stu-id="5123c-116">Remarks</span></span>  
 <span data-ttu-id="5123c-117">コールバックは、次のように動作します。</span><span class="sxs-lookup"><span data-stu-id="5123c-117">The callback works in the following way:</span></span>  
  
-   <span data-ttu-id="5123c-118">最初に、ランタイムが読み込まれる場合にのみ、コールバックが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="5123c-118">The callback is invoked only when a runtime is loaded for the first time.</span></span>  
  
-   <span data-ttu-id="5123c-119">同じランタイムの再入可能な負荷、コールバックは呼び出されません。</span><span class="sxs-lookup"><span data-stu-id="5123c-119">The callback is not invoked for reentrant loads of the same runtime.</span></span>  
  
-   <span data-ttu-id="5123c-120">再入不可能なランタイムの読み込み、コールバック関数の呼び出しがシリアル化します。</span><span class="sxs-lookup"><span data-stu-id="5123c-120">For non-reentrant runtime loads, calls to the callback function are serialized.</span></span>  
  
 <span data-ttu-id="5123c-121">コールバック関数では、次のプロトタイプを持ちます。</span><span class="sxs-lookup"><span data-stu-id="5123c-121">The callback function has the following prototype:</span></span>  
  
```  
typedef void (__stdcall *RuntimeLoadedCallbackFnPtr)(  
                     ICLRRuntimeInfo *pRuntimeInfo,  
                     CallbackThreadSetFnPtr pfnCallbackThreadSet,  
                     CallbackThreadUnsetFnPtr pfnCallbackThreadUnset);  
```  
  
 <span data-ttu-id="5123c-122">コールバック関数のプロトタイプは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="5123c-122">The callback function prototypes are as follows:</span></span>  
  
-   <span data-ttu-id="5123c-123">`pfnCallbackThreadSet`:</span><span class="sxs-lookup"><span data-stu-id="5123c-123">`pfnCallbackThreadSet`:</span></span>  
  
    ```  
    typedef HRESULT (__stdcall *CallbackThreadSetFnPtr)();  
    ```  
  
-   <span data-ttu-id="5123c-124">`pfnCallbackThreadUnset`:</span><span class="sxs-lookup"><span data-stu-id="5123c-124">`pfnCallbackThreadUnset`:</span></span>  
  
    ```  
    typedef HRESULT (__stdcall *CallbackThreadUnsetFnPtr)();  
    ```  
  
 <span data-ttu-id="5123c-125">ホストが読み込みまたは再入可能の方法で読み込まれる別のランタイムが発生する場合、`pfnCallbackThreadSet`と`pfnCallbackThreadUnset`コールバック内で次のように関数を使用する必要がありますに用意されているパラメーター。</span><span class="sxs-lookup"><span data-stu-id="5123c-125">If the host intends to load or cause another runtime to be loaded in a reentrant manner, the `pfnCallbackThreadSet` and `pfnCallbackThreadUnset` parameters that are provided in the callback function must be used in the following way:</span></span>  
  
-   <span data-ttu-id="5123c-126">`pfnCallbackThreadSet` このような負荷が試みられる前に、実行時の負荷を引き起こす可能性のあるスレッドから呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="5123c-126">`pfnCallbackThreadSet` must be called by the thread that might cause a runtime load before such a load is attempted.</span></span>  
  
-   <span data-ttu-id="5123c-127">`pfnCallbackThreadUnset` スレッドは実行時の負荷が発生しない場合 (および初期コールバックから戻る前に) 呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="5123c-127">`pfnCallbackThreadUnset` must be called when the thread will no longer cause such a runtime load (and before returning from the initial callback).</span></span>  
  
-   <span data-ttu-id="5123c-128">`pfnCallbackThreadSet` `pfnCallbackThreadUnset`はどちらも再入不可能な。</span><span class="sxs-lookup"><span data-stu-id="5123c-128">`pfnCallbackThreadSet` and `pfnCallbackThreadUnset` are both non-reentrant.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5123c-129">ホスト アプリケーションを呼び出してはならない`pfnCallbackThreadSet`と`pfnCallbackThreadUnset`の範囲外の`pCallbackFunction`パラメーター。</span><span class="sxs-lookup"><span data-stu-id="5123c-129">Host applications must not call `pfnCallbackThreadSet` and `pfnCallbackThreadUnset` outside the scope of the `pCallbackFunction` parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5123c-130">必要条件</span><span class="sxs-lookup"><span data-stu-id="5123c-130">Requirements</span></span>  
 <span data-ttu-id="5123c-131">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5123c-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5123c-132">**ヘッダー:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="5123c-132">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="5123c-133">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="5123c-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5123c-134">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5123c-134">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5123c-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="5123c-135">See also</span></span>
- [<span data-ttu-id="5123c-136">ICLRMetaHost インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5123c-136">ICLRMetaHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)
- [<span data-ttu-id="5123c-137">ホスティング</span><span class="sxs-lookup"><span data-stu-id="5123c-137">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
