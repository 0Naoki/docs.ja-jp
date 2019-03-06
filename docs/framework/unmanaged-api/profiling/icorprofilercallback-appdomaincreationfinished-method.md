---
title: ICorProfilerCallback::AppDomainCreationFinished メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AppDomainCreationFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AppDomainCreationFinished
helpviewer_keywords:
- AppDomainCreationFinished method [.NET Framework profiling]
- ICorProfilerCallback::AppDomainCreationFinished method [.NET Framework profiling]
ms.assetid: dbab7d90-d515-4dc9-8195-294d5d04bab6
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a08a0ed8303804df1889973fe3ffab6db93249d5
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57481444"
---
# <a name="icorprofilercallbackappdomaincreationfinished-method"></a><span data-ttu-id="dc168-102">ICorProfilerCallback::AppDomainCreationFinished メソッド</span><span class="sxs-lookup"><span data-stu-id="dc168-102">ICorProfilerCallback::AppDomainCreationFinished Method</span></span>
<span data-ttu-id="dc168-103">アプリケーション ドメインが作成されたことをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="dc168-103">Notifies the profiler that an application domain has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc168-104">構文</span><span class="sxs-lookup"><span data-stu-id="dc168-104">Syntax</span></span>  
  
```  
HRESULT AppDomainCreationFinished(  
    [in] AppDomainID appDomainId,  
    [in] HRESULT     hrStatus);   
```  
  
## <a name="parameters"></a><span data-ttu-id="dc168-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="dc168-105">Parameters</span></span>  
 `appDomainId`  
 <span data-ttu-id="dc168-106">[in]作成されたドメインを識別します。</span><span class="sxs-lookup"><span data-stu-id="dc168-106">[in] Identifies the domain which has been created.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="dc168-107">[in]アプリケーション ドメインの作成が正常に完了したかどうかを示す HRESULT。</span><span class="sxs-lookup"><span data-stu-id="dc168-107">[in] An HRESULT that indicates whether creation of the application domain completed successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dc168-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="dc168-108">Remarks</span></span>  
 <span data-ttu-id="dc168-109">アプリケーション ID は、情報の要求まで無効です、`AppDomainCreationFinished`メソッドが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="dc168-109">The application ID is not valid for any information request until the `AppDomainCreationFinished` method is called.</span></span>  
  
 <span data-ttu-id="dc168-110">アプリケーション ドメインの読み込みの一部が後に続ける可能性があります、`AppDomainCreationFinished`コールバック。</span><span class="sxs-lookup"><span data-stu-id="dc168-110">Some parts of loading the application domain might continue after the `AppDomainCreationFinished` callback.</span></span> <span data-ttu-id="dc168-111">エラーの HRESULT で`hrStatus`失敗を示します。</span><span class="sxs-lookup"><span data-stu-id="dc168-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="dc168-112">ただし、成功 HRESULT で`hrStatus`のみにアプリケーション ドメインの作成の最初の部分が成功したことを示します。</span><span class="sxs-lookup"><span data-stu-id="dc168-112">However, a success HRESULT in `hrStatus` indicates only that the first part of creating the application domain has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dc168-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="dc168-113">Requirements</span></span>  
 <span data-ttu-id="dc168-114">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="dc168-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dc168-115">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="dc168-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="dc168-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dc168-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dc168-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dc168-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc168-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="dc168-118">See also</span></span>
- [<span data-ttu-id="dc168-119">ICorProfilerCallback インターフェイス</span><span class="sxs-lookup"><span data-stu-id="dc168-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
