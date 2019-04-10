---
title: CorTokenType 列挙型
ms.date: 03/30/2017
api_name:
- CorTokenType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorTokenType
helpviewer_keywords:
- CorTokenType enumeration [.NET Framework metadata]
ms.assetid: 93c9a369-225f-4eff-9b78-3fbee4902cf1
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1b33b50e53c454f2b62253d12943ea044240d8cc
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59230513"
---
# <a name="cortokentype-enumeration"></a><span data-ttu-id="231db-102">CorTokenType 列挙型</span><span class="sxs-lookup"><span data-stu-id="231db-102">CorTokenType Enumeration</span></span>
<span data-ttu-id="231db-103">メタデータ トークンの種類を示します。</span><span class="sxs-lookup"><span data-stu-id="231db-103">Indicates the type of a metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="231db-104">構文</span><span class="sxs-lookup"><span data-stu-id="231db-104">Syntax</span></span>  
  
```  
typedef enum CorTokenType {  
  
    mdtModule                       = 0x00000000,  
    mdtTypeRef                      = 0x01000000,  
    mdtTypeDef                      = 0x02000000,  
    mdtFieldDef                     = 0x04000000,  
    mdtMethodDef                    = 0x06000000,  
    mdtParamDef                     = 0x08000000,  
    mdtInterfaceImpl                = 0x09000000,  
    mdtMemberRef                    = 0x0a000000,  
    mdtCustomAttribute              = 0x0c000000,  
    mdtPermission                   = 0x0e000000,  
    mdtSignature                    = 0x11000000,  
    mdtEvent                        = 0x14000000,  
    mdtProperty                     = 0x17000000,  
    mdtModuleRef                    = 0x1a000000,  
    mdtTypeSpec                     = 0x1b000000,  
    mdtAssembly                     = 0x20000000,  
    mdtAssemblyRef                  = 0x23000000,  
    mdtFile                         = 0x26000000,  
    mdtExportedType                 = 0x27000000,  
    mdtManifestResource             = 0x28000000,  
    mdtGenericParam                 = 0x2a000000,  
    mdtMethodSpec                   = 0x2b000000,  
    mdtGenericParamConstraint       = 0x2c000000,  
    mdtString                       = 0x70000000,  
    mdtName                         = 0x71000000,  
    mdtBaseType                     = 0x72000000  
  
} CorTokenType;  
```  
  
## <a name="members"></a><span data-ttu-id="231db-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="231db-105">Members</span></span>  
  
|<span data-ttu-id="231db-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="231db-106">Member</span></span>|<span data-ttu-id="231db-107">説明</span><span class="sxs-lookup"><span data-stu-id="231db-107">Description</span></span>|  
|------------|-----------------|  
|`mdtModule`|<span data-ttu-id="231db-108">`mdModule`トークンです。</span><span class="sxs-lookup"><span data-stu-id="231db-108">An `mdModule` token.</span></span>|  
|`mdtTypeRef`|<span data-ttu-id="231db-109">`mdTypeRef`トークンです。</span><span class="sxs-lookup"><span data-stu-id="231db-109">An `mdTypeRef` token.</span></span>|  
|`mdtTypeDef`|<span data-ttu-id="231db-110">`mdTypeDef`トークンです。</span><span class="sxs-lookup"><span data-stu-id="231db-110">An `mdTypeDef` token.</span></span>|  
|`mdtFieldDef`|<span data-ttu-id="231db-111">`mdFieldDef`トークンです。</span><span class="sxs-lookup"><span data-stu-id="231db-111">An `mdFieldDef` token.</span></span>|  
|`mdtMethodDef`|<span data-ttu-id="231db-112">`mdMethodDef`トークンです。</span><span class="sxs-lookup"><span data-stu-id="231db-112">An `mdMethodDef` token.</span></span>|  
|`mdtParamDef`|<span data-ttu-id="231db-113">`mdParamDef`トークンです。</span><span class="sxs-lookup"><span data-stu-id="231db-113">An `mdParamDef` token.</span></span>|  
|`mdtInterfaceImpl`|<span data-ttu-id="231db-114">`mdInterfaceImpl`トークンです。</span><span class="sxs-lookup"><span data-stu-id="231db-114">An `mdInterfaceImpl` token.</span></span>|  
|`mdtMemberRef`|<span data-ttu-id="231db-115">`mdMemberRef`トークンです。</span><span class="sxs-lookup"><span data-stu-id="231db-115">An `mdMemberRef` token.</span></span>|  
|`mdtCustomAttribute`|<span data-ttu-id="231db-116">`mdCustomAttribute`トークンです。</span><span class="sxs-lookup"><span data-stu-id="231db-116">An `mdCustomAttribute` token.</span></span>|  
|`mdtPermission`|<span data-ttu-id="231db-117">`mdPermission`トークンです。</span><span class="sxs-lookup"><span data-stu-id="231db-117">An `mdPermission` token.</span></span>|  
|`mdtSignature`|<span data-ttu-id="231db-118">`mdSignature`トークンです。</span><span class="sxs-lookup"><span data-stu-id="231db-118">An `mdSignature` token.</span></span>|  
|`mdtEvent`|<span data-ttu-id="231db-119">`mdEvent`トークンです。</span><span class="sxs-lookup"><span data-stu-id="231db-119">An `mdEvent` token.</span></span>|  
|`mdtProperty`|<span data-ttu-id="231db-120">`mdProperty`トークンです。</span><span class="sxs-lookup"><span data-stu-id="231db-120">An `mdProperty` token.</span></span>|  
|`mdtModuleRef`|<span data-ttu-id="231db-121">`mdModuleRef`トークンです。</span><span class="sxs-lookup"><span data-stu-id="231db-121">An `mdModuleRef` token.</span></span>|  
|`mdtTypeSpec`|<span data-ttu-id="231db-122">`mdTypeSpec`トークンです。</span><span class="sxs-lookup"><span data-stu-id="231db-122">An `mdTypeSpec` token.</span></span>|  
|`mdtAssembly`|<span data-ttu-id="231db-123">`mdAssembly`トークンです。</span><span class="sxs-lookup"><span data-stu-id="231db-123">An `mdAssembly` token.</span></span>|  
|`mdtAssemblyRef`|<span data-ttu-id="231db-124">`mdAssemblyRef`トークンです。</span><span class="sxs-lookup"><span data-stu-id="231db-124">An `mdAssemblyRef` token.</span></span>|  
|`mdtFile`|<span data-ttu-id="231db-125">`mdFile`トークンです。</span><span class="sxs-lookup"><span data-stu-id="231db-125">An `mdFile` token.</span></span>|  
|`mdtExportedType`|<span data-ttu-id="231db-126">`mdExportedType`トークンです。</span><span class="sxs-lookup"><span data-stu-id="231db-126">An `mdExportedType` token.</span></span>|  
|`mdtManifestResource`|<span data-ttu-id="231db-127">`mdManifestResource`トークンです。</span><span class="sxs-lookup"><span data-stu-id="231db-127">An `mdManifestResource` token.</span></span>|  
|`mdtGenericParam`|<span data-ttu-id="231db-128">`mdGenericParam`トークンです。</span><span class="sxs-lookup"><span data-stu-id="231db-128">An `mdGenericParam` token.</span></span>|  
|`mdtMethodSpec`|<span data-ttu-id="231db-129">`mdMethodSpec`トークンです。</span><span class="sxs-lookup"><span data-stu-id="231db-129">An `mdMethodSpec` token.</span></span>|  
|`mdtGenericParamConstraint`|<span data-ttu-id="231db-130">`mdGenericParamConstraint`トークンです。</span><span class="sxs-lookup"><span data-stu-id="231db-130">An `mdGenericParamConstraint` token.</span></span>|  
|`mdtString`|<span data-ttu-id="231db-131">`mdString`トークンです。</span><span class="sxs-lookup"><span data-stu-id="231db-131">An `mdString` token.</span></span>|  
|`mdtName`|<span data-ttu-id="231db-132">`mdName`トークンです。</span><span class="sxs-lookup"><span data-stu-id="231db-132">An `mdName` token.</span></span>|  
|`mdtBaseType`|<span data-ttu-id="231db-133">使用しません。</span><span class="sxs-lookup"><span data-stu-id="231db-133">Not used.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="231db-134">Remarks</span><span class="sxs-lookup"><span data-stu-id="231db-134">Remarks</span></span>  
 <span data-ttu-id="231db-135">各値は、対応するメタデータ トークン内の最上位バイトの値と同じです。</span><span class="sxs-lookup"><span data-stu-id="231db-135">Each value is equal to the value of the top byte in the corresponding metadata token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="231db-136">必要条件</span><span class="sxs-lookup"><span data-stu-id="231db-136">Requirements</span></span>  
 <span data-ttu-id="231db-137">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="231db-137">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="231db-138">**ヘッダー:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="231db-138">**Header:** CorHdr.h</span></span>  
  
 **<span data-ttu-id="231db-139">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="231db-139">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="231db-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="231db-140">See also</span></span>

- [<span data-ttu-id="231db-141">メタデータ列挙体</span><span class="sxs-lookup"><span data-stu-id="231db-141">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
