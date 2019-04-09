---
title: COR_PRF_SNAPSHOT_INFO 列挙型
ms.date: 03/30/2017
api_name:
- COR_PRF_SNAPSHOT_INFO
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_SNAPSHOT_INFO
helpviewer_keywords:
- COR_PRF_SNAPSHOT_INFO enumeration [.NET Framework profiling]
ms.assetid: a5906b2a-ad4a-4cc6-a421-2d7d8adf7468
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: fa85fb2cebb47ecbd7b0f091cb79f6ea0936b1cb
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59177841"
---
# <a name="corprfsnapshotinfo-enumeration"></a><span data-ttu-id="8c4fa-102">COR_PRF_SNAPSHOT_INFO 列挙型</span><span class="sxs-lookup"><span data-stu-id="8c4fa-102">COR_PRF_SNAPSHOT_INFO Enumeration</span></span>
<span data-ttu-id="8c4fa-103">プロファイラーの各呼び出しでスタック スナップショット バックアップに渡すデータ量を指定します。 [StackSnapshotCallback](../../../../docs/framework/unmanaged-api/profiling/stacksnapshotcallback-function.md)関数。</span><span class="sxs-lookup"><span data-stu-id="8c4fa-103">Specifies how much data to pass back with a stack snapshot in each call to the profiler's [StackSnapshotCallback](../../../../docs/framework/unmanaged-api/profiling/stacksnapshotcallback-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c4fa-104">構文</span><span class="sxs-lookup"><span data-stu-id="8c4fa-104">Syntax</span></span>  
  
```  
typedef enum _COR_PRF_SNAPSHOT_INFO {  
    COR_PRF_SNAPSHOT_DEFAULT = 0x0,  
    COR_PRF_SNAPSHOT_REGISTER_CONTEXT = 0x1,  
    COR_PRF_SNAPSHOT_X86_OPTIMIZED = 0X2  
} COR_PRF_SNAPSHOT_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="8c4fa-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="8c4fa-105">Members</span></span>  
  
|<span data-ttu-id="8c4fa-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="8c4fa-106">Members</span></span>|<span data-ttu-id="8c4fa-107">説明</span><span class="sxs-lookup"><span data-stu-id="8c4fa-107">Description</span></span>|  
|-------------|-----------------|  
|`COR_PRF_SNAPSHOT_DEFAULT`|<span data-ttu-id="8c4fa-108">すべての値を渡す必要があることを示します`StackSnapshotCallback`パラメーターを除く、`context`パラメーター。</span><span class="sxs-lookup"><span data-stu-id="8c4fa-108">Indicates that values must be passed for all `StackSnapshotCallback` parameters, except the `context` parameter.</span></span>|  
|`COR_PRF_SNAPSHOT_REGISTER_CONTEXT`|<span data-ttu-id="8c4fa-109">すべての値を渡す必要があることを示します`StackSnapshotCallback`などのパラメーター、`context`パラメーター。</span><span class="sxs-lookup"><span data-stu-id="8c4fa-109">Indicates that values must be passed for all `StackSnapshotCallback` parameters, including the `context` parameter.</span></span>|  
|`COR_PRF_SNAPSHOT_X86_OPTIMIZED`|<span data-ttu-id="8c4fa-110">単純化し、別のスタック ウォーク アルゴリズムが使用されることを示します。</span><span class="sxs-lookup"><span data-stu-id="8c4fa-110">Indicates that a simpler, alternative stack-walking algorithm will be used.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8c4fa-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="8c4fa-111">Remarks</span></span>  
 <span data-ttu-id="8c4fa-112">によって提供される値、`COR_PRF_SNAPSHOT_INFO`へのパラメーターとして渡される列挙型、 [DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="8c4fa-112">Values that are provided by the `COR_PRF_SNAPSHOT_INFO` enumeration are passed as parameters to the [DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8c4fa-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="8c4fa-113">Requirements</span></span>  
 <span data-ttu-id="8c4fa-114">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8c4fa-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8c4fa-115">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8c4fa-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8c4fa-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8c4fa-116">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="8c4fa-117">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="8c4fa-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="8c4fa-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="8c4fa-118">See also</span></span>

- [<span data-ttu-id="8c4fa-119">DoStackSnapshot メソッド</span><span class="sxs-lookup"><span data-stu-id="8c4fa-119">DoStackSnapshot Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md)
- [<span data-ttu-id="8c4fa-120">列挙体のプロファイリング</span><span class="sxs-lookup"><span data-stu-id="8c4fa-120">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
