---
title: CorDebugIlToNativeMappingTypes 列挙型
ms.date: 03/30/2017
api_name:
- CorDebugIlToNativeMappingTypes
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugIlToNativeMappingTypes
helpviewer_keywords:
- CorDebugIIToNativeMappingTypes enumeration [.NET Framework debugging]
ms.assetid: c35e2919-42c3-4ba0-ae28-443c35f66f93
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 61b57d534770c6ab7cacbc2c084ac364dc31863f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54717611"
---
# <a name="cordebugiltonativemappingtypes-enumeration"></a><span data-ttu-id="8f3d0-102">CorDebugIlToNativeMappingTypes 列挙型</span><span class="sxs-lookup"><span data-stu-id="8f3d0-102">CorDebugIlToNativeMappingTypes Enumeration</span></span>
<span data-ttu-id="8f3d0-103">COR_DEBUG_IL_TO_NATIVE_MAP 構造体のインスタンスによって表されるネイティブの命令の特定の範囲が特別なコード領域に対応するかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="8f3d0-103">Indicates whether a particular range of native instructions, represented by an instance of the COR_DEBUG_IL_TO_NATIVE_MAP structure, corresponds to a special code region.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f3d0-104">構文</span><span class="sxs-lookup"><span data-stu-id="8f3d0-104">Syntax</span></span>  
  
```  
typedef enum CorDebugIlToNativeMappingTypes {  
    NO_MAPPING = -1,  
    PROLOG     = -2,  
    EPILOG     = -3  
} CorDebugIlToNativeMappingTypes;  
```  
  
## <a name="members"></a><span data-ttu-id="8f3d0-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="8f3d0-105">Members</span></span>  
  
|<span data-ttu-id="8f3d0-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="8f3d0-106">Member</span></span>|<span data-ttu-id="8f3d0-107">説明</span><span class="sxs-lookup"><span data-stu-id="8f3d0-107">Description</span></span>|  
|------------|-----------------|  
|`NO_MAPPING`|<span data-ttu-id="8f3d0-108">ネイティブ命令の範囲は、特別なコードの任意のリージョンに対応していません。</span><span class="sxs-lookup"><span data-stu-id="8f3d0-108">The range of native instructions does not correspond to any special code region.</span></span>|  
|`PROLOG`|<span data-ttu-id="8f3d0-109">ネイティブ命令の範囲は、プロローグに対応します。</span><span class="sxs-lookup"><span data-stu-id="8f3d0-109">The range of native instructions corresponds to the prolog.</span></span>|  
|`EPILOG`|<span data-ttu-id="8f3d0-110">ネイティブ命令の範囲は、エピローグに対応します。</span><span class="sxs-lookup"><span data-stu-id="8f3d0-110">The range of native instructions corresponds to the epilog.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8f3d0-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="8f3d0-111">Requirements</span></span>  
 <span data-ttu-id="8f3d0-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8f3d0-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8f3d0-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8f3d0-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8f3d0-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8f3d0-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8f3d0-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8f3d0-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f3d0-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="8f3d0-116">See also</span></span>
- [<span data-ttu-id="8f3d0-117">GetILToNativeMapping メソッド</span><span class="sxs-lookup"><span data-stu-id="8f3d0-117">GetILToNativeMapping Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getiltonativemapping-method.md)
- [<span data-ttu-id="8f3d0-118">列挙型のデバッグ</span><span class="sxs-lookup"><span data-stu-id="8f3d0-118">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
