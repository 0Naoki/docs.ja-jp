---
title: ICorProfilerInfo4::GetObjectSize2 メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4.GetObjectSize2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::GetObjectSize2
helpviewer_keywords:
- GetObjectSize2 method, ICorProfilerInfo4 interface [.NET Framework profiling]
- ICorProfilerInfo4::GetObjectSize2 method [.NET Framework profiling]
ms.assetid: 4a3e43ed-3ee3-4395-ab14-f78b903be13e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 15829e08a755b91ff91ca939b92a5a87bd377e8b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59176294"
---
# <a name="icorprofilerinfo4getobjectsize2-method"></a><span data-ttu-id="8b114-102">ICorProfilerInfo4::GetObjectSize2 メソッド</span><span class="sxs-lookup"><span data-stu-id="8b114-102">ICorProfilerInfo4::GetObjectSize2 Method</span></span>
<span data-ttu-id="8b114-103">指定したオブジェクトのサイズを返します。</span><span class="sxs-lookup"><span data-stu-id="8b114-103">Returns the size of a specified object.</span></span> <span data-ttu-id="8b114-104">置換、 [icorprofilerinfo::getobjectsize](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getobjectsize-method.md)メソッドで表現できる内容よりも大きいオブジェクトのサイズを報告することによって、`ULONG`します。</span><span class="sxs-lookup"><span data-stu-id="8b114-104">Replaces the [ICorProfilerInfo::GetObjectSize](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getobjectsize-method.md) method by reporting sizes of objects that are larger than what can be expressed in a `ULONG`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b114-105">構文</span><span class="sxs-lookup"><span data-stu-id="8b114-105">Syntax</span></span>  
  
```  
HRESULT GetObjectSize2(  
    [in]  ObjectID objectId,  
    [out] SIZE_T *pcSize);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8b114-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="8b114-106">Parameters</span></span>  
 `objectId`  
 <span data-ttu-id="8b114-107">[in]オブジェクトの ID。</span><span class="sxs-lookup"><span data-stu-id="8b114-107">[in] The ID of the object.</span></span>  
  
 `pcSize`  
 <span data-ttu-id="8b114-108">[out]オブジェクトのサイズ (バイト) へのポインター。</span><span class="sxs-lookup"><span data-stu-id="8b114-108">[out] A pointer to the object's size, in bytes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8b114-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="8b114-109">Remarks</span></span>  
 <span data-ttu-id="8b114-110">多くの場合、同じ種類の異なるオブジェクトと同じサイズである場合します。</span><span class="sxs-lookup"><span data-stu-id="8b114-110">Different objects of the same types often have the same size.</span></span> <span data-ttu-id="8b114-111">ただし、配列や文字列など、一部の種類には、オブジェクトごとに別のサイズがあります。</span><span class="sxs-lookup"><span data-stu-id="8b114-111">However, some types, such as arrays or strings, may have a different size for each object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8b114-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="8b114-112">Requirements</span></span>  
 <span data-ttu-id="8b114-113">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8b114-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8b114-114">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8b114-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8b114-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8b114-115">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="8b114-116">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="8b114-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="8b114-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="8b114-117">See also</span></span>

- [<span data-ttu-id="8b114-118">ICorProfilerInfo4 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8b114-118">ICorProfilerInfo4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)
