---
title: AssemblyAttributesGoHereSM
ms.date: 03/30/2017
api_name:
- AssemblyAttributesGoHereSM
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- AssemblyAttributesGoHereSM
helpviewer_keywords:
- AssemblyAttributesGoHereSM type
- Alink API, AssemblyAttributesGoHereSM type
ms.assetid: 4cf9bf39-1527-49e0-a0e9-55e7a018bf66
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6d47ca3a9134266d1c40447cea6eb8aaf2cc9eb9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54706298"
---
# <a name="assemblyattributesgoheresm"></a><span data-ttu-id="c8176-102">AssemblyAttributesGoHereSM</span><span class="sxs-lookup"><span data-stu-id="c8176-102">AssemblyAttributesGoHereSM</span></span>
<span data-ttu-id="c8176-103">ALink でプレースホルダーとして使用し、カスタム属性に関する情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="c8176-103">Used by ALink as a placeholder to store information about custom attributes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8176-104">構文</span><span class="sxs-lookup"><span data-stu-id="c8176-104">Syntax</span></span>  
  
```  
AssemblyAttributeGoHereSM  
```  
  
## <a name="remarks"></a><span data-ttu-id="c8176-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="c8176-105">Remarks</span></span>  
 <span data-ttu-id="c8176-106">この型への参照は、ソースにアセンブリのカスタム属性が含まれている netmodule 内部に埋め込まれていることがあります。</span><span class="sxs-lookup"><span data-stu-id="c8176-106">References to this type might be embedded inside netmodules whose sources contain assembly custom attributes.</span></span> <span data-ttu-id="c8176-107">これらの型への参照が含まれる 1 つまたは複数の  netmodule からアセンブリ マニフェストを作成すると、ALink はこれらの参照にアタッチされた情報を使用して、実際のカスタム属性を生成します。</span><span class="sxs-lookup"><span data-stu-id="c8176-107">When building an assembly manifest from one or more netmodules that contain references to these types, ALink uses information attached to these references to emit real custom attributes.</span></span> <span data-ttu-id="c8176-108">このため、この型がインスタンス化されることはなく、その型への参照はビルド処理の一部としてのみ使用され、最終的なアセンブリでは使用されません。</span><span class="sxs-lookup"><span data-stu-id="c8176-108">As such, this type is never instantiated, and references to it are used only as part of the build process and serve no purpose in the final assembly.</span></span>  
  
 <span data-ttu-id="c8176-109">この型への参照は、セキュリティに関連して複数の用途を持つカスタム属性を示します。</span><span class="sxs-lookup"><span data-stu-id="c8176-109">References to this type indicate custom attributes that are security related and multiple-use.</span></span>  
  
 <span data-ttu-id="c8176-110">これらの型は .NET Framework 内で "内部的" とマーク付けされ、<xref:System.Runtime.CompilerServices> にあります。</span><span class="sxs-lookup"><span data-stu-id="c8176-110">These types are marked "internal" within the .NET Framework, and are located in <xref:System.Runtime.CompilerServices>.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c8176-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="c8176-111">Requirements</span></span>  
 <span data-ttu-id="c8176-112">mscorlib.dll</span><span class="sxs-lookup"><span data-stu-id="c8176-112">mscorlib.dll</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8176-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="c8176-113">See also</span></span>
- [<span data-ttu-id="c8176-114">AssemblyAttributesGoHere</span><span class="sxs-lookup"><span data-stu-id="c8176-114">AssemblyAttributesGoHere</span></span>](../../../../docs/framework/unmanaged-api/alink/assemblyattributesgohere.md)
- [<span data-ttu-id="c8176-115">AssemblyAttributesGoHereM</span><span class="sxs-lookup"><span data-stu-id="c8176-115">AssemblyAttributesGoHereM</span></span>](../../../../docs/framework/unmanaged-api/alink/assemblyattributesgoherem.md)
- [<span data-ttu-id="c8176-116">AssemblyAttributesGoHereS</span><span class="sxs-lookup"><span data-stu-id="c8176-116">AssemblyAttributesGoHereS</span></span>](../../../../docs/framework/unmanaged-api/alink/assemblyattributesgoheres.md)
