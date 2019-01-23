---
title: CorFieldAttr 列挙型
ms.date: 03/30/2017
api_name:
- CorFieldAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorFieldAttr
helpviewer_keywords:
- CorFieldAttr enumeration [.NET Framework metadata]
ms.assetid: 6ae2c4be-212c-4e74-9288-40a11dc26522
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7b07388b7f7385e93a6ca891e8ea98a2ce69763c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54576016"
---
# <a name="corfieldattr-enumeration"></a><span data-ttu-id="9e98d-102">CorFieldAttr 列挙型</span><span class="sxs-lookup"><span data-stu-id="9e98d-102">CorFieldAttr Enumeration</span></span>
<span data-ttu-id="9e98d-103">フィールドについてのメタデータを記述する値が格納されます。</span><span class="sxs-lookup"><span data-stu-id="9e98d-103">Contains values that describe metadata about a field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e98d-104">構文</span><span class="sxs-lookup"><span data-stu-id="9e98d-104">Syntax</span></span>  
  
```  
typedef enum CorFieldAttr {  
  
    fdFieldAccessMask           =   0x0007,  
    fdPrivateScope              =   0x0000,  
    fdPrivate                   =   0x0001,  
    fdFamANDAssem               =   0x0002,  
    fdAssembly                  =   0x0003,  
    fdFamily                    =   0x0004,  
    fdFamORAssem                =   0x0005,  
    fdPublic                    =   0x0006,  
  
    fdStatic                    =   0x0010,  
    fdInitOnly                  =   0x0020,  
    fdLiteral                   =   0x0040,  
    fdNotSerialized             =   0x0080,  
  
    fdSpecialName               =   0x0200,  
  
    fdPinvokeImpl               =   0x2000,  
  
    fdReservedMask              =   0x9500,  
    fdRTSpecialName             =   0x0400,  
    fdHasFieldMarshal           =   0x1000,  
    fdHasDefault                =   0x8000,  
    fdHasFieldRVA               =   0x0100  
  
} CorFieldAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="9e98d-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="9e98d-105">Members</span></span>  
  
|<span data-ttu-id="9e98d-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="9e98d-106">Member</span></span>|<span data-ttu-id="9e98d-107">説明</span><span class="sxs-lookup"><span data-stu-id="9e98d-107">Description</span></span>|  
|------------|-----------------|  
|`fdFieldAccessMask`|<span data-ttu-id="9e98d-108">アクセシビリティに関する情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="9e98d-108">Specifies accessibility information.</span></span>|  
|`fdPrivateScope`|<span data-ttu-id="9e98d-109">フィールドを参照できないことを指定します。</span><span class="sxs-lookup"><span data-stu-id="9e98d-109">Specifies that the field cannot be referenced.</span></span>|  
|`fdPrivate`|<span data-ttu-id="9e98d-110">フィールドが親の型からのみアクセスできることを指定します。</span><span class="sxs-lookup"><span data-stu-id="9e98d-110">Specifies that the field is accessible only by its parent type.</span></span>|  
|`fdFamANDAssem`|<span data-ttu-id="9e98d-111">フィールドにそのアセンブリの派生クラスからアクセスできることを指定します。</span><span class="sxs-lookup"><span data-stu-id="9e98d-111">Specifies that the field is accessible by derived classes in its assembly.</span></span>|  
|`fdAssembly`|<span data-ttu-id="9e98d-112">フィールドにそのアセンブリ内のすべての型からアクセスできることを指定します。</span><span class="sxs-lookup"><span data-stu-id="9e98d-112">Specifies that the field is accessible by all types in its assembly.</span></span>|  
|`fdFamily`|<span data-ttu-id="9e98d-113">フィールドの型によってのみアクセスできますが、派生クラスを指定します。</span><span class="sxs-lookup"><span data-stu-id="9e98d-113">Specifies that the field is accessible only by its type and derived classes.</span></span>|  
|`fdFamORAssem`|<span data-ttu-id="9e98d-114">フィールドにそのアセンブリ内のすべての型と派生クラスによってアクセスできることを指定します。</span><span class="sxs-lookup"><span data-stu-id="9e98d-114">Specifies that the field is accessible by derived classes and by all types in its assembly.</span></span>|  
|`fdPublic`|<span data-ttu-id="9e98d-115">フィールドがこのスコープの可視性を持つすべての種類でアクセスできることを指定します。</span><span class="sxs-lookup"><span data-stu-id="9e98d-115">Specifies that the field is accessible by all types with visibility of this scope.</span></span>|  
|`fdStatic`|<span data-ttu-id="9e98d-116">フィールドがインスタンス メンバーではなく、その型のメンバーであるを指定します。</span><span class="sxs-lookup"><span data-stu-id="9e98d-116">Specifies that the field is a member of its type rather than an instance member.</span></span>|  
|`fdInitOnly`|<span data-ttu-id="9e98d-117">初期化された後に、フィールドを変更できないことを指定します。</span><span class="sxs-lookup"><span data-stu-id="9e98d-117">Specifies that the field cannot be changed after it is initialized.</span></span>|  
|`fdLiteral`|<span data-ttu-id="9e98d-118">フィールド値がコンパイル時定数であることを指定します。</span><span class="sxs-lookup"><span data-stu-id="9e98d-118">Specifies that the field value is a compile-time constant.</span></span>|  
|`fdNotSerialized`|<span data-ttu-id="9e98d-119">その型は、リモート処理は実行時にフィールドはシリアルされないことを指定します。</span><span class="sxs-lookup"><span data-stu-id="9e98d-119">Specifies that the field is not serialized when its type is remoted.</span></span>|  
|`fdSpecialName`|<span data-ttu-id="9e98d-120">フィールドに、特別なことと、その名前を記述しているを指定しますか。</span><span class="sxs-lookup"><span data-stu-id="9e98d-120">Specifies that the field is special, and that its name describes how.</span></span>|  
|`fdPinvokeImpl`|<span data-ttu-id="9e98d-121">フィールドの実装が PInvoke 経由で転送されることを指定します。</span><span class="sxs-lookup"><span data-stu-id="9e98d-121">Specifies that the field implementation is forwarded through PInvoke.</span></span>|  
|`fdReservedMask`|<span data-ttu-id="9e98d-122">共通言語ランタイムでは、内部使用のため予約されています。</span><span class="sxs-lookup"><span data-stu-id="9e98d-122">Reserved for internal use by the common language runtime.</span></span>|  
|`fdRTSpecialName`|<span data-ttu-id="9e98d-123">共通言語ランタイム メタデータの内部 Api が名前のエンコーディングを確認する必要がありますように指定します。</span><span class="sxs-lookup"><span data-stu-id="9e98d-123">Specifies that the common language runtime metadata internal APIs should check the encoding of the name.</span></span>|  
|`fdHasFieldMarshal`|<span data-ttu-id="9e98d-124">フィールドにマーシャ リング情報が含まれることを指定します。</span><span class="sxs-lookup"><span data-stu-id="9e98d-124">Specifies that the field contains marshaling information.</span></span>|  
|`fdHasDefault`|<span data-ttu-id="9e98d-125">フィールドが既定値を持つことを指定します。</span><span class="sxs-lookup"><span data-stu-id="9e98d-125">Specifies that the field has a default value.</span></span>|  
|`fdHasFieldRVA`|<span data-ttu-id="9e98d-126">フィールドの相対仮想アドレスを持つことを指定します。</span><span class="sxs-lookup"><span data-stu-id="9e98d-126">Specifies that the field has a relative virtual address.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9e98d-127">必要条件</span><span class="sxs-lookup"><span data-stu-id="9e98d-127">Requirements</span></span>  
 <span data-ttu-id="9e98d-128">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9e98d-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9e98d-129">**ヘッダー:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="9e98d-129">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="9e98d-130">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9e98d-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e98d-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="9e98d-131">See also</span></span>
- [<span data-ttu-id="9e98d-132">メタデータ列挙型</span><span class="sxs-lookup"><span data-stu-id="9e98d-132">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
