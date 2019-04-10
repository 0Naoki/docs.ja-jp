---
title: COR_PRF_GC_GENERATION_RANGE 構造体
ms.date: 03/30/2017
api_name:
- COR_PRF_GC_GENERATION_RANGE
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_GC_GENERATION_RANGE
helpviewer_keywords:
- COR_PRF_GC_GENERATION_RANGE structure [.NET Framework profiling]
ms.assetid: e7e07273-8d10-4a68-807e-59634e3f8c5e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 646c4e37a7fab503a26557f9fdfc926b1186b17b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59216705"
---
# <a name="corprfgcgenerationrange-structure"></a><span data-ttu-id="558b8-102">COR_PRF_GC_GENERATION_RANGE 構造体</span><span class="sxs-lookup"><span data-stu-id="558b8-102">COR_PRF_GC_GENERATION_RANGE Structure</span></span>
<span data-ttu-id="558b8-103">ガーベッジ コレクションを実行中のメモリ範囲 (ブロック) を説明します。</span><span class="sxs-lookup"><span data-stu-id="558b8-103">Describes a range (that is, block) of memory that is undergoing garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="558b8-104">構文</span><span class="sxs-lookup"><span data-stu-id="558b8-104">Syntax</span></span>  
  
```  
typedef struct COR_PRF_GC_GENERATION_RANGE {  
    COR_PRF_GC_GENERATION generation;  
    ObjectID rangeStart;  
    UINT_PTR rangeLength;  
    UINT_PTR rangeLengthReserved;  
} COR_PRF_GC_GENERATION_RANGE;  
```  
  
## <a name="members"></a><span data-ttu-id="558b8-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="558b8-105">Members</span></span>  
  
|<span data-ttu-id="558b8-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="558b8-106">Member</span></span>|<span data-ttu-id="558b8-107">説明</span><span class="sxs-lookup"><span data-stu-id="558b8-107">Description</span></span>|  
|------------|-----------------|  
|`generation`|<span data-ttu-id="558b8-108">値、 [COR_PRF_GC_GENERATION](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-enumeration.md)メモリ ブロックを生成するように指定する列挙体が属しています。</span><span class="sxs-lookup"><span data-stu-id="558b8-108">A value of the [COR_PRF_GC_GENERATION](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-enumeration.md) enumeration that specifies the generation to which the block of memory belongs.</span></span>|  
|`rangeStart`|<span data-ttu-id="558b8-109">メモリ ブロックの開始位置を指定するオブジェクトの ID。</span><span class="sxs-lookup"><span data-stu-id="558b8-109">The ID of an object that specifies the starting location of the block of memory.</span></span>|  
|`rangeLength`|<span data-ttu-id="558b8-110">メモリ ブロック (つまり、ブロック内で使用されるメモリ量) の使用部分のサイズを指定する整数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="558b8-110">A pointer to an integer that specifies the size of the used portion of the memory block (that is, the amount of memory used within the block).</span></span>|  
|`rangeLengthReserved`|<span data-ttu-id="558b8-111">(つまり、ブロックのために予約されるメモリ量) メモリ ブロックのサイズを指定する整数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="558b8-111">A pointer to an integer that specifies the size of the memory block (that is, the amount of memory reserved for the block).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="558b8-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="558b8-112">Remarks</span></span>  
 <span data-ttu-id="558b8-113">`rangeLength`値は正確であることが保証場合にのみ[icorprofilerinfo 2::getgenerationbounds](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getgenerationbounds-method.md)または[icorprofilerinfo 2::getobjectgeneration](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getobjectgeneration-method.md)、使用するはどちらも、 `COR_PRF_GC_GENERATION_RANGE`構造体から呼び出される、 [icorprofilercallback 2::garbagecollectionstarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionstarted-method.md)または[icorprofilercallback 2::garbagecollectionfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="558b8-113">The `rangeLength` value is guaranteed to be accurate only if [ICorProfilerInfo2::GetGenerationBounds](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getgenerationbounds-method.md) or [ICorProfilerInfo2::GetObjectGeneration](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getobjectgeneration-method.md), both of which use the `COR_PRF_GC_GENERATION_RANGE` structure, is called from the [ICorProfilerCallback2::GarbageCollectionStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionstarted-method.md) or the [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="558b8-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="558b8-114">Requirements</span></span>  
 <span data-ttu-id="558b8-115">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="558b8-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="558b8-116">**ヘッダー:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="558b8-116">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="558b8-117">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="558b8-117">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="558b8-118">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="558b8-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="558b8-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="558b8-119">See also</span></span>

- [<span data-ttu-id="558b8-120">構造体のプロファイリング</span><span class="sxs-lookup"><span data-stu-id="558b8-120">Profiling Structures</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
