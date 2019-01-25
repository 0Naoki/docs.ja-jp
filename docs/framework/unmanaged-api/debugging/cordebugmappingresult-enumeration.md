---
title: CorDebugMappingResult 列挙型
ms.date: 03/30/2017
api_name:
- CorDebugMappingResult
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugMappingResult
helpviewer_keywords:
- CorDebugMappingResult enumeration [.NET Framework debugging]
ms.assetid: 701281dd-2936-45c8-a1f0-3bf7332b093b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 16c4e03667d4af3ab5cc8b653d77f15eaef25843
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54691828"
---
# <a name="cordebugmappingresult-enumeration"></a><span data-ttu-id="e45a2-102">CorDebugMappingResult 列挙型</span><span class="sxs-lookup"><span data-stu-id="e45a2-102">CorDebugMappingResult Enumeration</span></span>
<span data-ttu-id="e45a2-103">命令ポインター (IP) の値が得られた方法の詳細を提供します。</span><span class="sxs-lookup"><span data-stu-id="e45a2-103">Provides the details of how the value of the instruction pointer (IP) was obtained.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e45a2-104">構文</span><span class="sxs-lookup"><span data-stu-id="e45a2-104">Syntax</span></span>  
  
```  
typedef enum CorDebugMappingResult {  
    MAPPING_PROLOG              = 0x1,  
    MAPPING_EPILOG              = 0x2,  
    MAPPING_NO_INFO             = 0x4,  
    MAPPING_UNMAPPED_ADDRESS    = 0x8,  
    MAPPING_EXACT               = 0x10,  
    MAPPING_APPROXIMATE         = 0x20,  
} CorDebugMappingResult;  
```  
  
## <a name="members"></a><span data-ttu-id="e45a2-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="e45a2-105">Members</span></span>  
  
|<span data-ttu-id="e45a2-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="e45a2-106">Member</span></span>|<span data-ttu-id="e45a2-107">説明</span><span class="sxs-lookup"><span data-stu-id="e45a2-107">Description</span></span>|  
|------------|-----------------|  
|`MAPPING_PROLOG`|<span data-ttu-id="e45a2-108">Ip アドレスの値は 0 は、プロローグでネイティブ コードです。</span><span class="sxs-lookup"><span data-stu-id="e45a2-108">The native code is in the prolog, so the value of the IP is 0.</span></span>|  
|`MAPPING_EPILOG`|<span data-ttu-id="e45a2-109">Ip アドレスの値は、メソッドの最後の命令のアドレスは、エピローグでネイティブ コード。</span><span class="sxs-lookup"><span data-stu-id="e45a2-109">The native code is in an epilog, so the value of the IP is the address of the last instruction of the method.</span></span>|  
|`MAPPING_NO_INFO`|<span data-ttu-id="e45a2-110">マッピング情報がない、メソッドの使用可能なため、IP の値は 0 です。</span><span class="sxs-lookup"><span data-stu-id="e45a2-110">No mapping information is available for the method, so the value of the IP is 0.</span></span>|  
|`MAPPING_UNMAPPED_ADDRESS`|<span data-ttu-id="e45a2-111">メソッドのマッピング情報が、現在のアドレスは、Microsoft intermediate language (MSIL) コードにマップできません。</span><span class="sxs-lookup"><span data-stu-id="e45a2-111">Although there is mapping information for the method, the current address cannot be mapped to Microsoft intermediate language (MSIL) code.</span></span> <span data-ttu-id="e45a2-112">Ip アドレスの値は 0 です。</span><span class="sxs-lookup"><span data-stu-id="e45a2-112">The value of the IP is 0.</span></span>|  
|`MAPPING_EXACT`|<span data-ttu-id="e45a2-113">メソッドの MSIL コードに正確にマップまたはフレームが解釈されているので、ip アドレスの値は正確です。</span><span class="sxs-lookup"><span data-stu-id="e45a2-113">Either the method maps exactly to MSIL code or the frame has been interpreted, so the value of the IP is accurate.</span></span>|  
|`MAPPING_APPROXIMATE`|<span data-ttu-id="e45a2-114">メソッドが正常にマップされましたが、ip アドレスの値は概数である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e45a2-114">The method was successfully mapped, but the value of the IP may be approximate.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e45a2-115">Remarks</span><span class="sxs-lookup"><span data-stu-id="e45a2-115">Remarks</span></span>  
 <span data-ttu-id="e45a2-116">使用することができます、 [icordebugilframe::getip](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getip-method.md)命令ポインターの値を取得します。</span><span class="sxs-lookup"><span data-stu-id="e45a2-116">You can use the [ICorDebugILFrame::GetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getip-method.md) method to obtain the value of the instruction pointer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e45a2-117">必要条件</span><span class="sxs-lookup"><span data-stu-id="e45a2-117">Requirements</span></span>  
 <span data-ttu-id="e45a2-118">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e45a2-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e45a2-119">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e45a2-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e45a2-120">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e45a2-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e45a2-121">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e45a2-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e45a2-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="e45a2-122">See also</span></span>
- [<span data-ttu-id="e45a2-123">列挙型のデバッグ</span><span class="sxs-lookup"><span data-stu-id="e45a2-123">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
