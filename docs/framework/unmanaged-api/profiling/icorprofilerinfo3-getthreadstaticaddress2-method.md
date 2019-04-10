---
title: ICorProfilerInfo3::GetThreadStaticAddress2 メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.GetThreadStaticAddress2 Method
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::GetThreadStaticAddress2
helpviewer_keywords:
- ICorProfilerInfo3::GetThreadStaticAddress2 method [.NET Framework profiling]
- GetThreadStaticAddress2 method [.NET Framework profiling]
ms.assetid: a9608861-ae64-4467-8a73-be05ad34beac
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f62dadf4f21022f8f425596cf5957891ed39effe
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59189184"
---
# <a name="icorprofilerinfo3getthreadstaticaddress2-method"></a><span data-ttu-id="67f58-102">ICorProfilerInfo3::GetThreadStaticAddress2 メソッド</span><span class="sxs-lookup"><span data-stu-id="67f58-102">ICorProfilerInfo3::GetThreadStaticAddress2 Method</span></span>
<span data-ttu-id="67f58-103">指定したスレッドおよびアプリケーション ドメインのスコープ内にある、指定したスレッド内静的フィールドのアドレスを取得します。</span><span class="sxs-lookup"><span data-stu-id="67f58-103">Gets the address of the specified thread-static field that is in the scope of the specified thread and application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67f58-104">構文</span><span class="sxs-lookup"><span data-stu-id="67f58-104">Syntax</span></span>  
  
```  
HRESULT GetThreadStaticAddress2(  
                [in] ClassID classId,  
                [in] mdFieldDef fieldToken,  
                [in] AppDomainID appDomainId,  
                [in] ThreadID threadId,  
                [out] void **ppAddress);  
```  
  
## <a name="parameters"></a><span data-ttu-id="67f58-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="67f58-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="67f58-106">[in]要求されたスレッド内静的フィールドを含むクラスの ID。</span><span class="sxs-lookup"><span data-stu-id="67f58-106">[in] The ID of the class that contains the requested thread-static field.</span></span>  
  
 `fieldToken`  
 <span data-ttu-id="67f58-107">[in]要求されたスレッド内静的フィールドのメタデータ トークン。</span><span class="sxs-lookup"><span data-stu-id="67f58-107">[in] The metadata token for the requested thread-static field.</span></span>  
  
 `appDomainId`  
 <span data-ttu-id="67f58-108">[in] アプリケーション ドメインの ID。</span><span class="sxs-lookup"><span data-stu-id="67f58-108">[in] The ID of the application domain.</span></span>  
  
 `threadId`  
 <span data-ttu-id="67f58-109">[in]要求された静的フィールドのスコープにあるスレッドの ID。</span><span class="sxs-lookup"><span data-stu-id="67f58-109">[in] The ID of the thread that is the scope for the requested static field.</span></span>  
  
 `ppAddress`  
 <span data-ttu-id="67f58-110">[out]指定したスレッド内の静的フィールドのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="67f58-110">[out] A pointer to the address of the static field that is within the specified thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="67f58-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="67f58-111">Remarks</span></span>  
 <span data-ttu-id="67f58-112">`GetThreadStaticAddress2`メソッドは、次のいずれかを返す可能性があります。</span><span class="sxs-lookup"><span data-stu-id="67f58-112">The `GetThreadStaticAddress2` method may return one of the following:</span></span>  
  
-   <span data-ttu-id="67f58-113">指定された静的フィールドに指定したコンテキスト内のアドレスが割り当てられていない場合の CORPROF_E_DATAINCOMPLETE HRESULT。</span><span class="sxs-lookup"><span data-stu-id="67f58-113">A CORPROF_E_DATAINCOMPLETE HRESULT if the given static field has not been assigned an address in the specified context.</span></span>  
  
-   <span data-ttu-id="67f58-114">ガベージ コレクション ヒープで可能性のあるオブジェクトのアドレス。</span><span class="sxs-lookup"><span data-stu-id="67f58-114">The addresses of objects that may be in the garbage collection heap.</span></span> <span data-ttu-id="67f58-115">これらのアドレスは、ガベージ コレクション後にプロファイラーを想定しないでくださいが有効であるために、ガベージ コレクションの後無効になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="67f58-115">These addresses may become invalid after garbage collection, so after garbage collection, profilers should not assume that they are valid.</span></span>  
  
 <span data-ttu-id="67f58-116">クラスのクラスのコンス トラクターが完了したら、前に`GetThreadStaticAddress2`はいくつかの静的フィールドは既に初期化可能性がありますが、すべての静的フィールドの CORPROF_E_DATAINCOMPLETE を返し、ガベージ コレクション オブジェクトのルートします。</span><span class="sxs-lookup"><span data-stu-id="67f58-116">Before a class’s class constructor is completed, `GetThreadStaticAddress2` will return CORPROF_E_DATAINCOMPLETE for all its static fields, although some of the static fields may already be initialized and rooting garbage collection objects.</span></span>  
  
 <span data-ttu-id="67f58-117">[Icorprofilerinfo 2::getthreadstaticaddress](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getthreadstaticaddress-method.md)メソッドは、`GetThreadStaticAddress2`メソッドがアプリケーション ドメインの引数は受け付けません。</span><span class="sxs-lookup"><span data-stu-id="67f58-117">The [ICorProfilerInfo2::GetThreadStaticAddress](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getthreadstaticaddress-method.md) method is similar to the `GetThreadStaticAddress2` method, but does not accept an application domain argument.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="67f58-118">必要条件</span><span class="sxs-lookup"><span data-stu-id="67f58-118">Requirements</span></span>  
 <span data-ttu-id="67f58-119">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="67f58-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="67f58-120">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="67f58-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="67f58-121">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="67f58-121">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="67f58-122">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="67f58-122">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="67f58-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="67f58-123">See also</span></span>

- [<span data-ttu-id="67f58-124">ICorProfilerInfo3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="67f58-124">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [<span data-ttu-id="67f58-125">プロファイリングのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="67f58-125">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="67f58-126">プロファイル</span><span class="sxs-lookup"><span data-stu-id="67f58-126">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
