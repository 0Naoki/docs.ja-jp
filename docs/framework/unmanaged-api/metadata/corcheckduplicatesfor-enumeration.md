---
title: CorCheckDuplicatesFor 列挙型
ms.date: 03/30/2017
api_name:
- CorCheckDuplicatesFor
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorCheckDuplicatesFor
helpviewer_keywords:
- CorCheckDuplicatesFor enumeration [.NET Framework metadata]
ms.assetid: d8ec8d3c-70f7-4cc6-9957-68068fd8f49c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9c930b6fe81fdb7013e95a20d33ff0ba0148f88f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54658817"
---
# <a name="corcheckduplicatesfor-enumeration"></a><span data-ttu-id="fcb0b-102">CorCheckDuplicatesFor 列挙型</span><span class="sxs-lookup"><span data-stu-id="fcb0b-102">CorCheckDuplicatesFor Enumeration</span></span>
<span data-ttu-id="fcb0b-103">重複のチェックとメタデータ トークンを指定します。</span><span class="sxs-lookup"><span data-stu-id="fcb0b-103">Specifies the metadata tokens that will be checked for duplicates.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fcb0b-104">構文</span><span class="sxs-lookup"><span data-stu-id="fcb0b-104">Syntax</span></span>  
  
```  
typedef enum CorCheckDuplicatesFor {  
  
    MDDupAll                    = 0xffffffff,  
    MDDupENC                    = MDDupAll,  
    MDNoDupChecks               = 0x00000000,  
    MDDupTypeDef                = 0x00000001,  
    MDDupInterfaceImpl          = 0x00000002,  
    MDDupMethodDef              = 0x00000004,  
    MDDupTypeRef                = 0x00000008,  
    MDDupMemberRef              = 0x00000010,  
    MDDupCustomAttribute        = 0x00000020,  
    MDDupParamDef               = 0x00000040,  
    MDDupPermission             = 0x00000080,  
    MDDupProperty               = 0x00000100,  
    MDDupEvent                  = 0x00000200,  
    MDDupFieldDef               = 0x00000400,  
    MDDupSignature              = 0x00000800,  
    MDDupModuleRef              = 0x00001000,  
    MDDupTypeSpec               = 0x00002000,  
    MDDupImplMap                = 0x00004000,  
    MDDupAssemblyRef            = 0x00008000,  
    MDDupFile                   = 0x00010000,  
    MDDupExportedType           = 0x00020000,  
    MDDupManifestResource       = 0x00040000,  
    MDDupGenericParam           = 0x00080000,  
    MDDupMethodSpec             = 0x00100000,  
    MDDupGenericParamConstraint = 0x00200000,  
  
    MDDupAssembly               = 0x10000000,  
  
    MDDupDefault =   
        MDNoDupChecks | MDDupTypeRef | MDDupMemberRef |   
        MDDupSignature | MDDupTypeSpec | MDDupMethodSpec  
  
} CorCheckDuplicatesFor;  
```  
  
## <a name="members"></a><span data-ttu-id="fcb0b-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="fcb0b-105">Members</span></span>  
  
|<span data-ttu-id="fcb0b-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="fcb0b-106">Member</span></span>|<span data-ttu-id="fcb0b-107">説明</span><span class="sxs-lookup"><span data-stu-id="fcb0b-107">Description</span></span>|  
|------------|-----------------|  
|`MDDupAll`|<span data-ttu-id="fcb0b-108">すべてのメタデータ トークンの重複を確認します。</span><span class="sxs-lookup"><span data-stu-id="fcb0b-108">Check all metadata tokens for duplicates.</span></span>|  
|`MDDupENC`|<span data-ttu-id="fcb0b-109">使用しません。</span><span class="sxs-lookup"><span data-stu-id="fcb0b-109">Not used.</span></span>|  
|`MDNoDupChecks`|<span data-ttu-id="fcb0b-110">メタデータ トークンの重複をチェックしません。</span><span class="sxs-lookup"><span data-stu-id="fcb0b-110">Do not check metadata tokens for duplicates.</span></span>|  
|`MDDupTypeDef`|<span data-ttu-id="fcb0b-111">重複をチェック`mdTypeDef`トークンです。</span><span class="sxs-lookup"><span data-stu-id="fcb0b-111">Check for duplicates of `mdTypeDef` tokens.</span></span>|  
|`MDDupInterfaceImpl`|<span data-ttu-id="fcb0b-112">重複をチェック`mdInterfaceImpl`トークンです。</span><span class="sxs-lookup"><span data-stu-id="fcb0b-112">Check for duplicates of `mdInterfaceImpl` tokens.</span></span>|  
|`MDDupMethodDef`|<span data-ttu-id="fcb0b-113">重複をチェック`mdMethodDef`トークンです。</span><span class="sxs-lookup"><span data-stu-id="fcb0b-113">Check for duplicates of `mdMethodDef` tokens.</span></span>|  
|`MDDupTypeRef`|<span data-ttu-id="fcb0b-114">重複をチェック`mdTypeRef`トークンです。</span><span class="sxs-lookup"><span data-stu-id="fcb0b-114">Check for duplicates of `mdTypeRef` tokens.</span></span>|  
|`MDDupMemberRef`|<span data-ttu-id="fcb0b-115">重複をチェック`mdMemberRef`トークンです。</span><span class="sxs-lookup"><span data-stu-id="fcb0b-115">Check for duplicates of `mdMemberRef` tokens.</span></span>|  
|`MDDupCustomAttribute`|<span data-ttu-id="fcb0b-116">重複をチェック`mdCustomAttribute`トークンです。</span><span class="sxs-lookup"><span data-stu-id="fcb0b-116">Check for duplicates of `mdCustomAttribute` tokens.</span></span>|  
|`MDDupParamDef`|<span data-ttu-id="fcb0b-117">重複をチェック`mdParamDef`トークンです。</span><span class="sxs-lookup"><span data-stu-id="fcb0b-117">Check for duplicates of `mdParamDef` tokens.</span></span>|  
|`MDDupPermission`|<span data-ttu-id="fcb0b-118">重複をチェック`mdPermission`トークンです。</span><span class="sxs-lookup"><span data-stu-id="fcb0b-118">Check for duplicates of `mdPermission` tokens.</span></span>|  
|`MDDupProperty`|<span data-ttu-id="fcb0b-119">重複をチェック`mdProperty`トークンです。</span><span class="sxs-lookup"><span data-stu-id="fcb0b-119">Check for duplicates of `mdProperty` tokens.</span></span>|  
|`MDDupEvent`|<span data-ttu-id="fcb0b-120">重複をチェック`mdEvent`トークンです。</span><span class="sxs-lookup"><span data-stu-id="fcb0b-120">Check for duplicates of `mdEvent` tokens.</span></span>|  
|`MDDupFieldDef`|<span data-ttu-id="fcb0b-121">重複をチェック`mdFieldDef`トークンです。</span><span class="sxs-lookup"><span data-stu-id="fcb0b-121">Check for duplicates of `mdFieldDef` tokens.</span></span>|  
|`MDDupSignature`|<span data-ttu-id="fcb0b-122">重複をチェック`mdSignature`トークンです。</span><span class="sxs-lookup"><span data-stu-id="fcb0b-122">Check for duplicates of `mdSignature` tokens.</span></span>|  
|`MDDupModuleRef`|<span data-ttu-id="fcb0b-123">重複をチェック`mdModuleRef`トークンです。</span><span class="sxs-lookup"><span data-stu-id="fcb0b-123">Check for duplicates of `mdModuleRef` tokens.</span></span>|  
|`MDDupTypeSpec`|<span data-ttu-id="fcb0b-124">重複をチェック`mdTypeSpec`トークンです。</span><span class="sxs-lookup"><span data-stu-id="fcb0b-124">Check for duplicates of `mdTypeSpec` tokens.</span></span>|  
|`MDDupImplMap`|<span data-ttu-id="fcb0b-125">重複をチェック`mdImplMap`トークンです。</span><span class="sxs-lookup"><span data-stu-id="fcb0b-125">Check for duplicates of `mdImplMap` tokens.</span></span>|  
|`MDDupAssemblyRef`|<span data-ttu-id="fcb0b-126">重複をチェック`mdAssemblyRef`トークンです。</span><span class="sxs-lookup"><span data-stu-id="fcb0b-126">Check for duplicates of `mdAssemblyRef` tokens.</span></span>|  
|`MDDupFile`|<span data-ttu-id="fcb0b-127">重複をチェック`mdFile`トークンです。</span><span class="sxs-lookup"><span data-stu-id="fcb0b-127">Check for duplicates of `mdFile` tokens.</span></span>|  
|`MDDupExportedType`|<span data-ttu-id="fcb0b-128">重複をチェック`mdExportedType`トークンです。</span><span class="sxs-lookup"><span data-stu-id="fcb0b-128">Check for duplicates of `mdExportedType` tokens.</span></span>|  
|`MDDupManifestResource`|<span data-ttu-id="fcb0b-129">重複をチェック`mdManifestResource`トークンです。</span><span class="sxs-lookup"><span data-stu-id="fcb0b-129">Check for duplicates of `mdManifestResource` tokens.</span></span>|  
|`MDDupGenericParam`|<span data-ttu-id="fcb0b-130">重複をチェック`mdGenericParam`トークンです。</span><span class="sxs-lookup"><span data-stu-id="fcb0b-130">Check for duplicates of `mdGenericParam` tokens.</span></span>|  
|`MDDupMethodSpec`|<span data-ttu-id="fcb0b-131">重複をチェック`mdMethodSpec`トークンです。</span><span class="sxs-lookup"><span data-stu-id="fcb0b-131">Check for duplicates of `mdMethodSpec` tokens.</span></span>|  
|`MDDupGenericParamConstraint`|<span data-ttu-id="fcb0b-132">重複をチェック`mdGenericParamConstraint`トークンです。</span><span class="sxs-lookup"><span data-stu-id="fcb0b-132">Check for duplicates of `mdGenericParamConstraint` tokens.</span></span>|  
|`MDDupAssembly`|<span data-ttu-id="fcb0b-133">重複をチェック`mdAssembly`トークンです。</span><span class="sxs-lookup"><span data-stu-id="fcb0b-133">Check for duplicates of `mdAssembly` tokens.</span></span>|  
|`MDDupDefault`|<span data-ttu-id="fcb0b-134">重複をチェック`mdMemberRef`、 `mdTypeRef`、 `mdSignature`、 `mdTypeSpec`、および`mdMethodSpec`トークンです。</span><span class="sxs-lookup"><span data-stu-id="fcb0b-134">Check for duplicates of `mdMemberRef`, `mdTypeRef`, `mdSignature`, `mdTypeSpec`, and `mdMethodSpec` tokens.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="fcb0b-135">必要条件</span><span class="sxs-lookup"><span data-stu-id="fcb0b-135">Requirements</span></span>  
 <span data-ttu-id="fcb0b-136">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="fcb0b-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fcb0b-137">**ヘッダー:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="fcb0b-137">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="fcb0b-138">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fcb0b-138">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fcb0b-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="fcb0b-139">See also</span></span>
- [<span data-ttu-id="fcb0b-140">メタデータ列挙型</span><span class="sxs-lookup"><span data-stu-id="fcb0b-140">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
