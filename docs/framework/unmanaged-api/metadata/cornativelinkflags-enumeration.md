---
title: CorNativeLinkFlags 列挙型
ms.date: 03/30/2017
api_name:
- CorNativeLinkFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorNativeLinkFlags
helpviewer_keywords:
- CorNativeLinkFlags enumeration [.NET Framework metadata]
ms.assetid: 8027df7c-cfad-4724-bda0-7538d9519070
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7e6eb2a30dd6722309fd80c1611ad9200ab14ae5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59151997"
---
# <a name="cornativelinkflags-enumeration"></a><span data-ttu-id="96524-102">CorNativeLinkFlags 列挙型</span><span class="sxs-lookup"><span data-stu-id="96524-102">CorNativeLinkFlags Enumeration</span></span>
<span data-ttu-id="96524-103">ネイティブ コードをリンクするときに、リンカーが使用するフラグ値を提供します。</span><span class="sxs-lookup"><span data-stu-id="96524-103">Provides flag values used by the linker when linking native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96524-104">構文</span><span class="sxs-lookup"><span data-stu-id="96524-104">Syntax</span></span>  
  
```  
typedef enum  
{  
    nlfNone         = 0x00,  
    nlfLastError    = 0x01,  
    nlfNoMangle     = 0x02,  
    nlfMaxValue     = 0x03  
} CorNativeLinkFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="96524-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="96524-105">Members</span></span>  
  
|<span data-ttu-id="96524-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="96524-106">Member</span></span>|<span data-ttu-id="96524-107">説明</span><span class="sxs-lookup"><span data-stu-id="96524-107">Description</span></span>|  
|------------|-----------------|  
|`nlfNone`|<span data-ttu-id="96524-108">フラグがないことを示します。</span><span class="sxs-lookup"><span data-stu-id="96524-108">Indicates no flags.</span></span>|  
|`nlfLastError`|<span data-ttu-id="96524-109">示す、`setLastError`キーワード。</span><span class="sxs-lookup"><span data-stu-id="96524-109">Indicates a `setLastError` keyword.</span></span>|  
|`nlfNoMangle`|<span data-ttu-id="96524-110">示す、`nomangle`キーワード。</span><span class="sxs-lookup"><span data-stu-id="96524-110">Indicates a `nomangle` keyword.</span></span>|  
|`nlfMaxValue`|<span data-ttu-id="96524-111">使用しません。</span><span class="sxs-lookup"><span data-stu-id="96524-111">Not used.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="96524-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="96524-112">Requirements</span></span>  
 <span data-ttu-id="96524-113">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="96524-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="96524-114">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="96524-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="96524-115">**ライブラリ:** MsCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="96524-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="96524-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="96524-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96524-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="96524-117">See also</span></span>

- [<span data-ttu-id="96524-118">メタデータ列挙型</span><span class="sxs-lookup"><span data-stu-id="96524-118">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
