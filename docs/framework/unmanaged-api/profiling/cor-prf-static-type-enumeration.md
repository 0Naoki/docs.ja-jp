---
title: COR_PRF_STATIC_TYPE 列挙型
ms.date: 03/30/2017
api_name:
- COR_PRF_STATIC_TYPE
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_STATIC_TYPE
helpviewer_keywords:
- COR_PRF_STATIC_TYPE enumeration [.NET Framework profiling]
ms.assetid: 441d7809-5b65-41a5-ba64-2910a8008315
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 34a2ca5b505c504115af47402c3d92a05ec0676f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54737634"
---
# <a name="corprfstatictype-enumeration"></a><span data-ttu-id="ad963-102">COR_PRF_STATIC_TYPE 列挙型</span><span class="sxs-lookup"><span data-stu-id="ad963-102">COR_PRF_STATIC_TYPE Enumeration</span></span>
<span data-ttu-id="ad963-103">フィールドが静的であるかどうかを示し、静的な場合は、フィールドに適用される静的なクオリティを示します。</span><span class="sxs-lookup"><span data-stu-id="ad963-103">Indicates whether a field is static and, if so, the static quality that applies to the field.</span></span> <span data-ttu-id="ad963-104">フィールドを複数持つことを示すビットごとの OR 演算を使用してこれらの値を結合できる別の静的品質。</span><span class="sxs-lookup"><span data-stu-id="ad963-104">These values can be combined using the bitwise OR operation to indicate that the field has multiple, different static qualities.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad963-105">構文</span><span class="sxs-lookup"><span data-stu-id="ad963-105">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PRF_FIELD_NOT_A_STATIC = 0x0,  
    COR_PRF_FIELD_APP_DOMAIN_STATIC = 0x1,  
    COR_PRF_FIELD_THREAD_STATIC = 0x2,  
    COR_PRF_FIELD_CONTEXT_STATIC = 0x4,  
    COR_PRF_FIELD_RVA_STATIC = 0x8  
} COR_PRF_STATIC_TYPE;  
```  
  
## <a name="members"></a><span data-ttu-id="ad963-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="ad963-106">Members</span></span>  
  
|<span data-ttu-id="ad963-107">メンバー</span><span class="sxs-lookup"><span data-stu-id="ad963-107">Member</span></span>|<span data-ttu-id="ad963-108">説明</span><span class="sxs-lookup"><span data-stu-id="ad963-108">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_FIELD_NOT_A_STATIC`|<span data-ttu-id="ad963-109">フィールドは静的でありません。</span><span class="sxs-lookup"><span data-stu-id="ad963-109">The field is not static.</span></span>|  
|`COR_PRF_FIELD_APP_DOMAIN_STATIC`|<span data-ttu-id="ad963-110">フィールドには、アプリケーション ドメインの静的です。</span><span class="sxs-lookup"><span data-stu-id="ad963-110">The field is application domain-static.</span></span>|  
|`COR_PRF_FIELD_THREAD_STATIC`|<span data-ttu-id="ad963-111">フィールドでは、スレッドの静的です。</span><span class="sxs-lookup"><span data-stu-id="ad963-111">The field is thread-static.</span></span>|  
|`COR_PRF_FIELD_CONTEXT_STATIC`|<span data-ttu-id="ad963-112">フィールドでは、コンテキストの静的です。</span><span class="sxs-lookup"><span data-stu-id="ad963-112">The field is context-static.</span></span>|  
|`COR_PRF_FIELD_RVA_STATIC`|<span data-ttu-id="ad963-113">フィールドが相対仮想アドレス (RVA)-静的です。</span><span class="sxs-lookup"><span data-stu-id="ad963-113">The field is relative virtual address (RVA)-static.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ad963-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="ad963-114">Requirements</span></span>  
 <span data-ttu-id="ad963-115">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ad963-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ad963-116">**ヘッダー:** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ad963-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ad963-117">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ad963-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ad963-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ad963-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad963-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="ad963-119">See also</span></span>
- [<span data-ttu-id="ad963-120">列挙型のプロファイリング</span><span class="sxs-lookup"><span data-stu-id="ad963-120">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
