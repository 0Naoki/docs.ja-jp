---
title: ICorProfilerInfo::GetILFunctionBodyAllocator メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetILFunctionBodyAllocator
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetILFunctionBodyAllocator
helpviewer_keywords:
- GetILFunctionBodyAllocator method [.NET Framework profiling]
- ICorProfilerInfo::GetILFunctionBodyAllocator method [.NET Framework profiling]
ms.assetid: 5da1bf3d-dddf-4892-b266-578ee54d570b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2cd66a895f99d62e8deaa45afab12d963aee2901
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59109123"
---
# <a name="icorprofilerinfogetilfunctionbodyallocator-method"></a><span data-ttu-id="ecc06-102">ICorProfilerInfo::GetILFunctionBodyAllocator メソッド</span><span class="sxs-lookup"><span data-stu-id="ecc06-102">ICorProfilerInfo::GetILFunctionBodyAllocator Method</span></span>
<span data-ttu-id="ecc06-103">Microsoft intermediate language (MSIL) コード内のメソッドの本文をスワップするために使用されるメモリを割り当てるメソッドを提供するインターフェイスを取得します。</span><span class="sxs-lookup"><span data-stu-id="ecc06-103">Gets an interface that provides a method to allocate memory to be used for swapping out the body of a method in Microsoft intermediate language (MSIL) code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ecc06-104">構文</span><span class="sxs-lookup"><span data-stu-id="ecc06-104">Syntax</span></span>  
  
```  
HRESULT GetILFunctionBodyAllocator(  
    [in]  ModuleID      moduleId,  
    [out] IMethodMalloc **ppMalloc);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ecc06-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ecc06-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="ecc06-106">[in]メソッドが存在するモジュールの ID。</span><span class="sxs-lookup"><span data-stu-id="ecc06-106">[in] The ID of the module in which the method resides.</span></span>  
  
 `ppMalloc`  
 <span data-ttu-id="ecc06-107">[out]ポインター、 [IMethodMalloc](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-interface.md)メモリを割り当てるメソッドを提供するインターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="ecc06-107">[out] A pointer to an [IMethodMalloc](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-interface.md) interface that provides a method to allocate the memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ecc06-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="ecc06-108">Remarks</span></span>  
 <span data-ttu-id="ecc06-109">メソッドの本体の MSIL コードでは、4 GB 内のモジュールに従っていることを意味、読み込まれたモジュールの基準とした相対仮想アドレス (RVA) として配置である必要があります。</span><span class="sxs-lookup"><span data-stu-id="ecc06-109">A method body in MSIL code must be located as a relative virtual address (RVA), relative to the loaded module, which means that it follows the module within 4 GB.</span></span> <span data-ttu-id="ecc06-110">メソッドの本体のスワップ アウトするためのツールを容易にできるように、`GetILFunctionBodyAllocator`メソッドにより、メモリがその範囲内で割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="ecc06-110">To make it easier for a tool to swap out the body of a method, the `GetILFunctionBodyAllocator` method ensures that memory is allocated within that range.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ecc06-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="ecc06-111">Requirements</span></span>  
 <span data-ttu-id="ecc06-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ecc06-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ecc06-113">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ecc06-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ecc06-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ecc06-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ecc06-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ecc06-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ecc06-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="ecc06-116">See also</span></span>

- [<span data-ttu-id="ecc06-117">ICorProfilerInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ecc06-117">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
