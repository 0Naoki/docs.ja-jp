---
title: ICorProfilerInfo2::GetAppDomainStaticAddress メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetAppDomainStaticAddress
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetAppDomainStaticAddress
helpviewer_keywords:
- ICorProfilerInfo2::GetAppDomainStaticAddress method [.NET Framework profiling]
- GetAppDomainStaticAddress method [.NET Framework profiling]
ms.assetid: 2a9e0ea7-a9e2-4817-b1c4-fcf15b215ea9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f3c5e89057ef4c88d7c5e78120aca9841d731eda
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54524716"
---
# <a name="icorprofilerinfo2getappdomainstaticaddress-method"></a><span data-ttu-id="d34d6-102">ICorProfilerInfo2::GetAppDomainStaticAddress メソッド</span><span class="sxs-lookup"><span data-stu-id="d34d6-102">ICorProfilerInfo2::GetAppDomainStaticAddress Method</span></span>
<span data-ttu-id="d34d6-103">指定したアプリケーション ドメインのスコープ内の指定されたアプリケーション ドメインの静的フィールドのアドレスを取得します。</span><span class="sxs-lookup"><span data-stu-id="d34d6-103">Gets the address of the specified application domain-static field that is in the scope of the specified application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d34d6-104">構文</span><span class="sxs-lookup"><span data-stu-id="d34d6-104">Syntax</span></span>  
  
```  
RESULT GetAppDomainStaticAddress(  
    [in] ClassID classId,  
    [in] mdFieldDef fieldToken,  
    [in] AppDomainID appDomainId,  
    [out] void **ppAddress);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d34d6-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d34d6-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="d34d6-106">[in]要求されたアプリケーション ドメインの静的フィールドを格納するクラスのクラス ID。</span><span class="sxs-lookup"><span data-stu-id="d34d6-106">[in] The class ID of the class that contains the requested application domain-static field.</span></span>  
  
 `fieldToken`  
 <span data-ttu-id="d34d6-107">[in]要求されたアプリケーション ドメインの静的フィールドのメタデータ トークンです。</span><span class="sxs-lookup"><span data-stu-id="d34d6-107">[in] The metadata token for the requested application domain-static field.</span></span>  
  
 `appDomainId`  
 <span data-ttu-id="d34d6-108">[in]要求された静的フィールドのスコープとなっているアプリケーション ドメインの ID。</span><span class="sxs-lookup"><span data-stu-id="d34d6-108">[in] The ID of the application domain that is the scope for the requested static field.</span></span>  
  
 `ppAddress`  
 <span data-ttu-id="d34d6-109">[out]指定したアプリケーション ドメイン内にある静的フィールドのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="d34d6-109">[out] A pointer to the address of the static field that is within the specified application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d34d6-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="d34d6-110">Remarks</span></span>  
 <span data-ttu-id="d34d6-111">`GetAppDomainStaticAddress`メソッドは、次のいずれかを返す可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d34d6-111">The `GetAppDomainStaticAddress` method may return one of the following:</span></span>  
  
-   <span data-ttu-id="d34d6-112">指定された静的フィールドに指定したコンテキスト内のアドレスが割り当てられていない場合の CORPROF_E_DATAINCOMPLETE HRESULT。</span><span class="sxs-lookup"><span data-stu-id="d34d6-112">A CORPROF_E_DATAINCOMPLETE HRESULT if the given static field has not been assigned an address in the specified context.</span></span>  
  
-   <span data-ttu-id="d34d6-113">ガベージ コレクション ヒープで可能性のあるオブジェクトのアドレス。</span><span class="sxs-lookup"><span data-stu-id="d34d6-113">The addresses of objects that may be in the garbage collection heap.</span></span> <span data-ttu-id="d34d6-114">これらのアドレスは、ガベージ コレクション後にプロファイラーを想定しないでくださいが有効であるために、ガベージ コレクションの後無効になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d34d6-114">These addresses may become invalid after garbage collection, so after garbage collection, profilers should not assume that they are valid.</span></span>  
  
 <span data-ttu-id="d34d6-115">クラスのクラスのコンス トラクターが完了したら、前に`GetAppDomainStaticAddress`はいくつかの静的フィールドは既に初期化可能性がありますが、すべての静的フィールドの CORPROF_E_DATAINCOMPLETE を返し、ガベージ コレクション オブジェクトのルートします。</span><span class="sxs-lookup"><span data-stu-id="d34d6-115">Before a class’s class constructor is completed, `GetAppDomainStaticAddress` will return CORPROF_E_DATAINCOMPLETE for all its static fields, although some of the static fields may already be initialized and rooting garbage collection objects.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d34d6-116">必要条件</span><span class="sxs-lookup"><span data-stu-id="d34d6-116">Requirements</span></span>  
 <span data-ttu-id="d34d6-117">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d34d6-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d34d6-118">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d34d6-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d34d6-119">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d34d6-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d34d6-120">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d34d6-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d34d6-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="d34d6-121">See also</span></span>
- [<span data-ttu-id="d34d6-122">ICorProfilerInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d34d6-122">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="d34d6-123">ICorProfilerInfo2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d34d6-123">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
