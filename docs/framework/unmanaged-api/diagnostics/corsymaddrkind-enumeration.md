---
title: CorSymAddrKind 列挙体
ms.date: 03/30/2017
api_name:
- CorSymAddrKind
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorSymAddrKind
helpviewer_keywords:
- CorSymAddrKind enumeration [.NET Framework debugging]
ms.assetid: 3ef841c2-cade-42ee-ba34-2ef91d6d0879
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 389cf2e77728002ce1078f63df3d741d1847c105
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54744974"
---
# <a name="corsymaddrkind-enumeration"></a><span data-ttu-id="8c717-102">CorSymAddrKind 列挙体</span><span class="sxs-lookup"><span data-stu-id="8c717-102">CorSymAddrKind Enumeration</span></span>
<span data-ttu-id="8c717-103">メモリ アドレスの種類を示します。</span><span class="sxs-lookup"><span data-stu-id="8c717-103">Indicates the type of memory address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c717-104">構文</span><span class="sxs-lookup"><span data-stu-id="8c717-104">Syntax</span></span>  
  
```  
typedef enum CorSymAddrKind  
{  
    ADDR_IL_OFFSET          = 1,  
    ADDR_NATIVE_RVA         = 2,  
    ADDR_NATIVE_REGISTER    = 3,  
    ADDR_NATIVE_REGREL      = 4,  
    ADDR_NATIVE_OFFSET      = 5,  
    ADDR_NATIVE_REGREG      = 6,  
    ADDR_NATIVE_REGSTK      = 7,  
    ADDR_NATIVE_STKREG      = 8,  
    ADDR_BITFIELD           = 9,  
    ADDR_NATIVE_ISECTOFFSET = 10  
} CorSymAddrKind;  
```  
  
## <a name="members"></a><span data-ttu-id="8c717-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="8c717-105">Members</span></span>  
  
|<span data-ttu-id="8c717-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="8c717-106">Member</span></span>|<span data-ttu-id="8c717-107">説明</span><span class="sxs-lookup"><span data-stu-id="8c717-107">Description</span></span>|  
|------------|-----------------|  
|`ADDR_IL_OFFSET`|<span data-ttu-id="8c717-108">Microsoft intermediate language (MSIL) ローカル変数またはパラメーター インデックスを示します。</span><span class="sxs-lookup"><span data-stu-id="8c717-108">Indicates a Microsoft intermediate language (MSIL) local variable or parameter index.</span></span>|  
|`ADDR_NATIVE_RVA`|<span data-ttu-id="8c717-109">モジュールへの相対仮想アドレスを示します。</span><span class="sxs-lookup"><span data-stu-id="8c717-109">Indicates a relative virtual address into a module.</span></span>|  
|`ADDR_NATIVE_REGISTER`|<span data-ttu-id="8c717-110">CPU レジスタを示します。</span><span class="sxs-lookup"><span data-stu-id="8c717-110">Indicates a CPU register.</span></span>|  
|`ADDR_NATIVE_REGREL`|<span data-ttu-id="8c717-111">最初のアドレスは、レジスタと 2 番目のアドレスは、オフセットを示します。</span><span class="sxs-lookup"><span data-stu-id="8c717-111">Indicates that the first address is a register and the second address is an offset.</span></span>|  
|`ADDR_NATIVE_OFFSET`|<span data-ttu-id="8c717-112">ベース アドレスからのオフセットを示します。</span><span class="sxs-lookup"><span data-stu-id="8c717-112">Indicates an offset from a base address.</span></span>|  
|`ADDR_NATIVE_REGREG`|<span data-ttu-id="8c717-113">最初のアドレスは、レジスタの下位部、2 つ目は高い部分を示します。</span><span class="sxs-lookup"><span data-stu-id="8c717-113">Indicates that the first address is the low portion of a register, and the second address is the high portion.</span></span>|  
|`ADDR_NATIVE_REGSTK`|<span data-ttu-id="8c717-114">最初のアドレスは、レジスタの下位部、2 つ目は、高の部分では、および 3 番目のオフセットは、ことを示します。</span><span class="sxs-lookup"><span data-stu-id="8c717-114">Indicates that the first address is the low portion of a register, the second is the high portion, and the third is an offset.</span></span>|  
|`ADDR_NATIVE_STKREG`|<span data-ttu-id="8c717-115">最初のアドレスは、レジスタこと、2 つ目は、オフセット、および 3 番目はレジスタの高い部分を示します。</span><span class="sxs-lookup"><span data-stu-id="8c717-115">Indicates that the first address is a register, the second is an offset, and the third is the high portion of the register.</span></span>|  
|`ADDR_BITFIELD`|<span data-ttu-id="8c717-116">最初のアドレスは、フィールドの最初と 2 番目のアドレスは、フィールド長のことを示します。</span><span class="sxs-lookup"><span data-stu-id="8c717-116">Indicates that the first address is the start of a field and the second address is the field length.</span></span>|  
|`ADDR_NATIVE_ISECTOFFSET`|<span data-ttu-id="8c717-117">最初のアドレスは、セクションと 2 番目のアドレスは、オフセットを示します。</span><span class="sxs-lookup"><span data-stu-id="8c717-117">Indicates that the first address is the section and the second address is an offset.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8c717-118">必要条件</span><span class="sxs-lookup"><span data-stu-id="8c717-118">Requirements</span></span>  
 <span data-ttu-id="8c717-119">**ヘッダー:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="8c717-119">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c717-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="8c717-120">See also</span></span>
- [<span data-ttu-id="8c717-121">シンボル ストア診断列挙型</span><span class="sxs-lookup"><span data-stu-id="8c717-121">Diagnostics Symbol Store Enumerations</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)
