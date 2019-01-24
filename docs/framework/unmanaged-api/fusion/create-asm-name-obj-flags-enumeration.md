---
title: CREATE_ASM_NAME_OBJ_FLAGS 列挙型
ms.date: 03/30/2017
api_name:
- CREATE_ASM_NAME_OBJ_FLAGS
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- CREATE_ASM_NAME_OBJ_FLAGS
helpviewer_keywords:
- CREATE_ASM_NAME_OBJ_FLAGS enumeration [.NET Framework fusion]
ms.assetid: a5ed2fd0-c7d2-4603-aaca-5d0caad92675
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e4da0e064f507e2330aac27fc5c8bcd56b9d3c1b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54716233"
---
# <a name="createasmnameobjflags-enumeration"></a><span data-ttu-id="1f11c-102">CREATE_ASM_NAME_OBJ_FLAGS 列挙型</span><span class="sxs-lookup"><span data-stu-id="1f11c-102">CREATE_ASM_NAME_OBJ_FLAGS Enumeration</span></span>
<span data-ttu-id="1f11c-103">属性を指定します、 [IAssemblyName インターフェイス](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)オブジェクトは、によって作成時に、 [CreateAssemblyNameObject](../../../../docs/framework/unmanaged-api/fusion/createassemblynameobject-function.md)関数。</span><span class="sxs-lookup"><span data-stu-id="1f11c-103">Specifies the attributes of an [IAssemblyName Interface](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) object when it is constructed by the [CreateAssemblyNameObject](../../../../docs/framework/unmanaged-api/fusion/createassemblynameobject-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1f11c-104">構文</span><span class="sxs-lookup"><span data-stu-id="1f11c-104">Syntax</span></span>  
  
```  
typedef enum {  
  
    CANOF_PARSE_DISPLAY_NAME            = 0x1,  
    CANOF_SET_DEFAULT_VALUES            = 0x2,  
    CANOF_VERIFY_FRIEND_ASSEMBLYNAME    = 0x4,  
    CANOF_PARSE_FRIEND_DISPLAY_NAME     =   
        CANOF_PARSE_DISPLAY_NAME | CANOF_VERIFY_FRIEND_ASSEMBLYNAME  
  
} CREATE_ASM_NAME_OBJ_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="1f11c-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="1f11c-105">Members</span></span>  
  
|<span data-ttu-id="1f11c-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="1f11c-106">Member</span></span>|<span data-ttu-id="1f11c-107">説明</span><span class="sxs-lookup"><span data-stu-id="1f11c-107">Description</span></span>|  
|------------|-----------------|  
|`CANOF_PARSE_DISPLAY_NAME`|<span data-ttu-id="1f11c-108">渡されたパラメーターが、テキスト id であることを示します。</span><span class="sxs-lookup"><span data-stu-id="1f11c-108">Indicates that the parameter passed is a textual identity.</span></span>|  
|`CANOF_SET_DEFAULT_VALUES`|<span data-ttu-id="1f11c-109">いくつかの既定値を設定します。</span><span class="sxs-lookup"><span data-stu-id="1f11c-109">Sets a few default values.</span></span>|  
|`CANOF_VERIFY_FRIEND_ASSEMBLYNAME`|<span data-ttu-id="1f11c-110">フレンド アセンブリのルール (名前と公開キーのみ) を確認します。</span><span class="sxs-lookup"><span data-stu-id="1f11c-110">Verifies the friend assembly rule (only name and public key).</span></span> <span data-ttu-id="1f11c-111">このメンバーは、内部使用のみです。</span><span class="sxs-lookup"><span data-stu-id="1f11c-111">This member is for internal use only.</span></span>|  
|`CANOF_PARSE_FRIEND_DISPLAY_NAME`|<span data-ttu-id="1f11c-112">組み合わせ、`CANOF_PARSE_DISPLAY_NAME`と`CANOF_VERIFY_FRIEND_ASSEMBLYNAME`フラグ。</span><span class="sxs-lookup"><span data-stu-id="1f11c-112">A combination of the `CANOF_PARSE_DISPLAY_NAME` and `CANOF_VERIFY_FRIEND_ASSEMBLYNAME` flags.</span></span> <span data-ttu-id="1f11c-113">このメンバーは、内部使用のみです。</span><span class="sxs-lookup"><span data-stu-id="1f11c-113">This member is for internal use only.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1f11c-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="1f11c-114">Requirements</span></span>  
 <span data-ttu-id="1f11c-115">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1f11c-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1f11c-116">**ヘッダー:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="1f11c-116">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="1f11c-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1f11c-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f11c-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="1f11c-118">See also</span></span>
- [<span data-ttu-id="1f11c-119">IAssemblyName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1f11c-119">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
- [<span data-ttu-id="1f11c-120">CreateAssemblyNameObject 関数</span><span class="sxs-lookup"><span data-stu-id="1f11c-120">CreateAssemblyNameObject Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/createassemblynameobject-function.md)
- [<span data-ttu-id="1f11c-121">Fusion 列挙型</span><span class="sxs-lookup"><span data-stu-id="1f11c-121">Fusion Enumerations</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-enumerations.md)
