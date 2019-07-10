---
title: ICorProfilerInfo::GetClassIDInfo メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetClassIDInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetClassIDInfo
helpviewer_keywords:
- GetClassIDInfo method [.NET Framework profiling]
- ICorProfilerInfo::GetClassIDInfo method [.NET Framework profiling]
ms.assetid: 9e93b99e-5aca-415c-8e37-7f33753b612d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 232b5f4560fd62113a93d279683f3236e755e076
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67780182"
---
# <a name="icorprofilerinfogetclassidinfo-method"></a><span data-ttu-id="dde9b-102">ICorProfilerInfo::GetClassIDInfo メソッド</span><span class="sxs-lookup"><span data-stu-id="dde9b-102">ICorProfilerInfo::GetClassIDInfo Method</span></span>
<span data-ttu-id="dde9b-103">指定したクラスの親モジュールとメタデータ トークンを取得します。</span><span class="sxs-lookup"><span data-stu-id="dde9b-103">Gets the parent module and the metadata token for the specified class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dde9b-104">構文</span><span class="sxs-lookup"><span data-stu-id="dde9b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetClassIDInfo(  
    [in]  ClassID   classId,  
    [out] ModuleID  *pModuleId,  
    [out] mdTypeDef *pTypeDefToken);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dde9b-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="dde9b-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="dde9b-106">[in]情報を取得する対象のクラスの ID。</span><span class="sxs-lookup"><span data-stu-id="dde9b-106">[in] The ID of the class for which to get the information.</span></span>  
  
 `pModuleId`  
 <span data-ttu-id="dde9b-107">[out]クラスの親モジュールの ID へのポインター。</span><span class="sxs-lookup"><span data-stu-id="dde9b-107">[out] A pointer to the ID of the parent module of the class.</span></span>  
  
 `pTypeDefToken`  
 <span data-ttu-id="dde9b-108">[out]クラスのメタデータ トークンへのポインター。</span><span class="sxs-lookup"><span data-stu-id="dde9b-108">[out] A pointer to the metadata token for the class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dde9b-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="dde9b-109">Remarks</span></span>  
 <span data-ttu-id="dde9b-110">プロファイラー コードを呼び出すことができます[icorprofilerinfo::getmodulemetadata](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmodulemetadata-method.md)指定したモジュールのメタデータ インターフェイスを取得します。</span><span class="sxs-lookup"><span data-stu-id="dde9b-110">The profiler code can call [ICorProfilerInfo::GetModuleMetaData](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmodulemetadata-method.md) to obtain a metadata interface for a given module.</span></span> <span data-ttu-id="dde9b-111">`pTypeDefToken` によって参照される場所に返されるメタデータ トークンを使用すると、クラスのメタデータにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="dde9b-111">The metadata token that is returned to the location referenced by `pTypeDefToken` can then be used to access the metadata for the class.</span></span>  
  
 <span data-ttu-id="dde9b-112">ジェネリック型の詳細情報を表示するには使用[icorprofilerinfo 2::getclassidinfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassidinfo2-method.md)します。</span><span class="sxs-lookup"><span data-stu-id="dde9b-112">To get more information for generic types, use [ICorProfilerInfo2::GetClassIDInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassidinfo2-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dde9b-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="dde9b-113">Requirements</span></span>  
 <span data-ttu-id="dde9b-114">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="dde9b-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dde9b-115">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="dde9b-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="dde9b-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dde9b-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dde9b-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dde9b-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dde9b-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="dde9b-118">See also</span></span>

- [<span data-ttu-id="dde9b-119">ICorProfilerInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="dde9b-119">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
