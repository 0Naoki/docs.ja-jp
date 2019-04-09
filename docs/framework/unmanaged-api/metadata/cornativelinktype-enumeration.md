---
title: CorNativeLinkType 列挙型
ms.date: 03/30/2017
api_name:
- CorNativeLinkType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorNativeLinkType
helpviewer_keywords:
- CorNativeLinkType enumeration [.NET Framework metadata]
ms.assetid: 4f86ff37-2dab-4e64-819a-76b3bfe828ff
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 66d650adb39a9c7dade0936ec671ae5a8b4aeecd
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59170073"
---
# <a name="cornativelinktype-enumeration"></a><span data-ttu-id="d23a1-102">CorNativeLinkType 列挙型</span><span class="sxs-lookup"><span data-stu-id="d23a1-102">CorNativeLinkType Enumeration</span></span>
<span data-ttu-id="d23a1-103">ネイティブ コード内のリンクの種類を示す値を提供します。</span><span class="sxs-lookup"><span data-stu-id="d23a1-103">Provides values that indicate the type linked in native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d23a1-104">構文</span><span class="sxs-lookup"><span data-stu-id="d23a1-104">Syntax</span></span>  
  
```  
typedef enum   
{  
    nltNone       = 1,  
    nltAnsi       = 2,  
    nltUnicode    = 3,  
    nltAuto       = 4,  
    nltOle        = 5,  
    nltMaxValue   = 7  
} CorNativeLinkType;  
```  
  
## <a name="members"></a><span data-ttu-id="d23a1-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="d23a1-105">Members</span></span>  
  
|<span data-ttu-id="d23a1-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="d23a1-106">Member</span></span>|<span data-ttu-id="d23a1-107">説明</span><span class="sxs-lookup"><span data-stu-id="d23a1-107">Description</span></span>|  
|------------|-----------------|  
|`nltNone`|<span data-ttu-id="d23a1-108">キーワードのいずれも指定されていることを示します。</span><span class="sxs-lookup"><span data-stu-id="d23a1-108">Indicates that none of the keywords are specified.</span></span>|  
|`nltAnsi`|<span data-ttu-id="d23a1-109">ANSI キーワードが指定されていることを示します。</span><span class="sxs-lookup"><span data-stu-id="d23a1-109">Indicates that an ANSI keyword is specified.</span></span>|  
|`nltUnicode`|<span data-ttu-id="d23a1-110">Unicode キーワードが指定されていることを示します。</span><span class="sxs-lookup"><span data-stu-id="d23a1-110">Indicates that a Unicode keyword is specified</span></span>|  
|`nltAuto`|<span data-ttu-id="d23a1-111">Auto キーワードが指定されていることを示します。</span><span class="sxs-lookup"><span data-stu-id="d23a1-111">Indicates that an auto keyword is specified.</span></span>|  
|`nltOle`|<span data-ttu-id="d23a1-112">OLE キーワードが指定されていることを示します。</span><span class="sxs-lookup"><span data-stu-id="d23a1-112">Indicates that an OLE keyword is specified.</span></span>|  
|`nltMaxValue`|<span data-ttu-id="d23a1-113">使用しません。</span><span class="sxs-lookup"><span data-stu-id="d23a1-113">Not used.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d23a1-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="d23a1-114">Requirements</span></span>  
 <span data-ttu-id="d23a1-115">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d23a1-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d23a1-116">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="d23a1-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d23a1-117">**ライブラリ:** MsCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="d23a1-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="d23a1-118">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="d23a1-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d23a1-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="d23a1-119">See also</span></span>

- [<span data-ttu-id="d23a1-120">メタデータ列挙体</span><span class="sxs-lookup"><span data-stu-id="d23a1-120">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
