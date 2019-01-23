---
title: ICorProfilerThreadEnum::Clone メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerThreadEnum.Clone
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerThreadEnum::Clone
helpviewer_keywords:
- Clone method, ICorProfilerThreadEnum interface [.NET Framework profiling]
- ICorProfilerThreadEnum::Clone method [.NET Framework profiling]
ms.assetid: 5a278bc9-88e2-4c69-b035-9d550dd77081
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5b9d3224370dac0f8a52affef9201e5cbec43de0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54547437"
---
# <a name="icorprofilerthreadenumclone-method"></a><span data-ttu-id="6e062-102">ICorProfilerThreadEnum::Clone メソッド</span><span class="sxs-lookup"><span data-stu-id="6e062-102">ICorProfilerThreadEnum::Clone Method</span></span>
<span data-ttu-id="6e062-103">このコピーにインターフェイス ポインターを取得[ICorProfilerThreadEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md)インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="6e062-103">Gets an interface pointer to a copy of this [ICorProfilerThreadEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e062-104">構文</span><span class="sxs-lookup"><span data-stu-id="6e062-104">Syntax</span></span>  
  
```  
HRESULT Clone (    [out] ICorProfilerThreadEnum **ppEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6e062-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6e062-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="6e062-106">[out]さらに、このコピーを指しますインターフェイス ポインターへのポインター [ICorProfilerThreadEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md)インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="6e062-106">[out] A pointer to the interface pointer, which, in turn, points to the copy of this [ICorProfilerThreadEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md) interface.</span></span> <span data-ttu-id="6e062-107">列挙子のコピーでは、この列挙子から個別に独自の列挙状態を保持します。</span><span class="sxs-lookup"><span data-stu-id="6e062-107">The copy of the enumerator maintains its own enumeration state separately from this enumerator.</span></span> <span data-ttu-id="6e062-108">ただし、コピーの最初のカーソル位置では、この列挙子の現在のカーソル位置の場合と同じです。</span><span class="sxs-lookup"><span data-stu-id="6e062-108">However, the initial cursor position of the copy is the same as this current cursor position of the enumerator.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6e062-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="6e062-109">Requirements</span></span>  
 <span data-ttu-id="6e062-110">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6e062-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6e062-111">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6e062-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="6e062-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6e062-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6e062-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6e062-113">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e062-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="6e062-114">See also</span></span>
- [<span data-ttu-id="6e062-115">ICorProfilerThreadEnum</span><span class="sxs-lookup"><span data-stu-id="6e062-115">ICorProfilerThreadEnum</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md)
- [<span data-ttu-id="6e062-116">プロファイリングのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="6e062-116">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
