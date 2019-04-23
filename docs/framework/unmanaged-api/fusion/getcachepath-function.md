---
title: GetCachePath 関数
ms.date: 03/30/2017
api_name:
- GetCachePath
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- GetCachePath
helpviewer_keywords:
- GetCachePath function [.NET Framework fusion]
ms.assetid: d977ad29-6619-42e1-b0be-bc25ea950e80
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cf23a8f1893aa0f992d554d3c7533c3dc42f4e95
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59150983"
---
# <a name="getcachepath-function"></a><span data-ttu-id="1f341-102">GetCachePath 関数</span><span class="sxs-lookup"><span data-stu-id="1f341-102">GetCachePath Function</span></span>
<span data-ttu-id="1f341-103">指定したフラグを使用して、キャッシュされたアセンブリへのパスを取得します。</span><span class="sxs-lookup"><span data-stu-id="1f341-103">Gets the path to the cached assembly, using the specified flags.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1f341-104">構文</span><span class="sxs-lookup"><span data-stu-id="1f341-104">Syntax</span></span>  
  
```  
HRESULT GetCachePath (  
    [in]      ASM_CACHE_FLAGS  dwCacheFlags,  
    [in]      LPWSTR           pwzCachePath,  
    [in, out] PDWORD           pcchPath  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="1f341-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1f341-105">Parameters</span></span>  
 `dwCacheFlags`  
 <span data-ttu-id="1f341-106">[in][ASM_CACHE_FLAGS](../../../../docs/framework/unmanaged-api/fusion/asm-cache-flags-enumeration.md)キャッシュされたアセンブリのソースを示す値。</span><span class="sxs-lookup"><span data-stu-id="1f341-106">[in] An [ASM_CACHE_FLAGS](../../../../docs/framework/unmanaged-api/fusion/asm-cache-flags-enumeration.md) value that indicates the source of the cached assembly.</span></span>  
  
 `pwzCachePath`  
 <span data-ttu-id="1f341-107">[out]パスに返されるポインター。</span><span class="sxs-lookup"><span data-stu-id="1f341-107">[out] The returned pointer to the path.</span></span>  
  
 `pcchPath`  
 <span data-ttu-id="1f341-108">[入力、出力]要求の最大長の`pwzCachePath`、関数が戻るとき、実際の長さと`pwzCachePath`します。</span><span class="sxs-lookup"><span data-stu-id="1f341-108">[in, out] The requested maximum length of `pwzCachePath`, and upon return, the actual length of `pwzCachePath`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1f341-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="1f341-109">Requirements</span></span>  
 <span data-ttu-id="1f341-110">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1f341-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1f341-111">**ヘッダー:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="1f341-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="1f341-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1f341-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f341-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="1f341-113">See also</span></span>

- [<span data-ttu-id="1f341-114">ASM_CACHE_FLAGS 列挙型</span><span class="sxs-lookup"><span data-stu-id="1f341-114">ASM_CACHE_FLAGS Enumeration</span></span>](../../../../docs/framework/unmanaged-api/fusion/asm-cache-flags-enumeration.md)
- [<span data-ttu-id="1f341-115">Fusion グローバル静的関数</span><span class="sxs-lookup"><span data-stu-id="1f341-115">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
