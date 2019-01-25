---
title: CorUnmanagedCallingConvention 列挙型
ms.date: 03/30/2017
api_name:
- CorUnmanagedCallingConvention
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorUnmanagedCallingConvention
helpviewer_keywords:
- CorUnmanagedCallingConvention enumeration [.NET Framework metadata]
ms.assetid: 83058790-160b-4703-a5eb-74b66acbdfa9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c9a1ee9ab1649a832b6daefc96049d68850f3bc7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54555558"
---
# <a name="corunmanagedcallingconvention-enumeration"></a><span data-ttu-id="c8e4e-102">CorUnmanagedCallingConvention 列挙型</span><span class="sxs-lookup"><span data-stu-id="c8e4e-102">CorUnmanagedCallingConvention Enumeration</span></span>
<span data-ttu-id="c8e4e-103">アンマネージ コードの呼び出し規約を指定します。</span><span class="sxs-lookup"><span data-stu-id="c8e4e-103">Specifies the calling conventions for unmanaged code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8e4e-104">構文</span><span class="sxs-lookup"><span data-stu-id="c8e4e-104">Syntax</span></span>  
  
```  
typedef enum CorUnmanagedCallingConvention {  
  
    IMAGE_CEE_UNMANAGED_CALLCONV_C         = 0x1,  
    IMAGE_CEE_UNMANAGED_CALLCONV_STDCALL   = 0x2,  
    IMAGE_CEE_UNMANAGED_CALLCONV_THISCALL  = 0x3,  
    IMAGE_CEE_UNMANAGED_CALLCONV_FASTCALL  = 0x4,  
  
    IMAGE_CEE_CS_CALLCONV_C                = 0x1,  
    IMAGE_CEE_CS_CALLCONV_STDCALL          = 0x2,  
    IMAGE_CEE_CS_CALLCONV_THISCALL         = 0x3,  
    IMAGE_CEE_CS_CALLCONV_FASTCALL         = 0x4  
  
} CorUnmanagedCallingConvention;  
```  
  
## <a name="members"></a><span data-ttu-id="c8e4e-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="c8e4e-105">Members</span></span>  
  
|<span data-ttu-id="c8e4e-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="c8e4e-106">Member</span></span>|<span data-ttu-id="c8e4e-107">説明</span><span class="sxs-lookup"><span data-stu-id="c8e4e-107">Description</span></span>|  
|------------|-----------------|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_C`|<span data-ttu-id="c8e4e-108">C 言語の呼び出し規則。</span><span class="sxs-lookup"><span data-stu-id="c8e4e-108">The C language calling convention.</span></span>|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_STDCALL`|<span data-ttu-id="c8e4e-109">標準呼び出し規則。</span><span class="sxs-lookup"><span data-stu-id="c8e4e-109">The standard calling convention.</span></span>|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_THISCALL`|<span data-ttu-id="c8e4e-110">"This"呼び出し規約。</span><span class="sxs-lookup"><span data-stu-id="c8e4e-110">The "this" calling convention.</span></span>|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_FASTCALL`|<span data-ttu-id="c8e4e-111">「高速」の呼び出し規約。</span><span class="sxs-lookup"><span data-stu-id="c8e4e-111">The "fast" calling convention.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_C`|<span data-ttu-id="c8e4e-112">使用しません。</span><span class="sxs-lookup"><span data-stu-id="c8e4e-112">Not used.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_STDCALL`|<span data-ttu-id="c8e4e-113">使用しません。</span><span class="sxs-lookup"><span data-stu-id="c8e4e-113">Not used.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_THISCALL`|<span data-ttu-id="c8e4e-114">使用しません。</span><span class="sxs-lookup"><span data-stu-id="c8e4e-114">Not used.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_FASTCALL`|<span data-ttu-id="c8e4e-115">使用しません。</span><span class="sxs-lookup"><span data-stu-id="c8e4e-115">Not used.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c8e4e-116">Remarks</span><span class="sxs-lookup"><span data-stu-id="c8e4e-116">Remarks</span></span>  
 <span data-ttu-id="c8e4e-117">CLR は、.NET Framework version 1.0 での「高速」の呼び出し規約をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="c8e4e-117">The CLR does not support the "fast" calling convention in the .NET Framework version 1.0.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c8e4e-118">必要条件</span><span class="sxs-lookup"><span data-stu-id="c8e4e-118">Requirements</span></span>  
 <span data-ttu-id="c8e4e-119">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8e4e-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c8e4e-120">**ヘッダー:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="c8e4e-120">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="c8e4e-121">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c8e4e-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8e4e-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="c8e4e-122">See also</span></span>
- [<span data-ttu-id="c8e4e-123">メタデータ列挙型</span><span class="sxs-lookup"><span data-stu-id="c8e4e-123">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
