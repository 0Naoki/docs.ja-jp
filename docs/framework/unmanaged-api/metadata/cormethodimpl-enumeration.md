---
title: CorMethodImpl 列挙型
ms.date: 03/30/2017
api_name:
- CorMethodImpl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorMethodImpl
helpviewer_keywords:
- CorMethodImpl enumeration [.NET Framework metadata]
ms.assetid: ffbb3caf-20da-4a4b-8983-77376e72b990
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8ef293daea1a768c26adf05d14107a42889226e0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54491286"
---
# <a name="cormethodimpl-enumeration"></a><span data-ttu-id="dae19-102">CorMethodImpl 列挙型</span><span class="sxs-lookup"><span data-stu-id="dae19-102">CorMethodImpl Enumeration</span></span>
<span data-ttu-id="dae19-103">メソッド実装の機能を記述する値が格納されます。</span><span class="sxs-lookup"><span data-stu-id="dae19-103">Contains values that describe method implementation features.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dae19-104">構文</span><span class="sxs-lookup"><span data-stu-id="dae19-104">Syntax</span></span>  
  
```  
typedef enum CorMethodImpl {  
  
    miCodeTypeMask      =   0x0003,  
    miIL                =   0x0000,  
    miNative            =   0x0001,  
    miOPTIL             =   0x0002,  
    miRuntime           =   0x0003,  
  
    miManagedMask       =   0x0004,  
    miUnmanaged         =   0x0004,  
    miManaged           =   0x0000,  
  
    miForwardRef        =   0x0010,  
    miPreserveSig       =   0x0080,  
  
    miInternalCall      =   0x1000,  
    miSynchronized      =   0x0020,  
    miNoInlining        =   0x0008,  
    miAggressiveInlining =  0x0100,  
    miNoOptimization     =  0x0040,  
    miMaxMethodImplVal  =   0xffff  
  
} CorMethodImpl;  
```  
  
## <a name="members"></a><span data-ttu-id="dae19-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="dae19-105">Members</span></span>  
  
|<span data-ttu-id="dae19-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="dae19-106">Member</span></span>|<span data-ttu-id="dae19-107">説明</span><span class="sxs-lookup"><span data-stu-id="dae19-107">Description</span></span>|  
|------------|-----------------|  
|`miCodeTypeMask`|<span data-ttu-id="dae19-108">コードの種類を記述するフラグ。</span><span class="sxs-lookup"><span data-stu-id="dae19-108">Flags that describe code type.</span></span>|  
|`miIL`|<span data-ttu-id="dae19-109">メソッドの実装が Microsoft intermediate language (MSIL) であることを指定します。</span><span class="sxs-lookup"><span data-stu-id="dae19-109">Specifies that the method implementation is Microsoft intermediate language (MSIL).</span></span>|  
|`miNative`|<span data-ttu-id="dae19-110">メソッド実装がネイティブであることを指定します。</span><span class="sxs-lookup"><span data-stu-id="dae19-110">Specifies that the method implementation is native.</span></span>|  
|`miOPTIL`|<span data-ttu-id="dae19-111">メソッドの実装が OPTIL であることを指定します。</span><span class="sxs-lookup"><span data-stu-id="dae19-111">Specifies that the method implementation is OPTIL.</span></span>|  
|`miRuntime`|<span data-ttu-id="dae19-112">メソッドの実装が、共通言語ランタイムによって提供されることを指定します。</span><span class="sxs-lookup"><span data-stu-id="dae19-112">Specifies that the method implementation is provided by the common language runtime.</span></span>|  
|`miManagedMask`|<span data-ttu-id="dae19-113">コードがマネージかアンマネージかどうかを示すフラグです。</span><span class="sxs-lookup"><span data-stu-id="dae19-113">Flags that indicate whether the code is managed or unmanaged.</span></span>|  
|`miUnmanaged`|<span data-ttu-id="dae19-114">メソッドの実装が管理されていないことを指定します。</span><span class="sxs-lookup"><span data-stu-id="dae19-114">Specifies that the method implementation is unmanaged.</span></span>|  
|`miManaged`|<span data-ttu-id="dae19-115">メソッドの実装が管理されていることを指定します。</span><span class="sxs-lookup"><span data-stu-id="dae19-115">Specifies that the method implementation is managed.</span></span>|  
|`miForwardRef`|<span data-ttu-id="dae19-116">メソッドが定義されていることを指定します。</span><span class="sxs-lookup"><span data-stu-id="dae19-116">Specifies that the method is defined.</span></span> <span data-ttu-id="dae19-117">このフラグは、マージのシナリオで主に使用されます。</span><span class="sxs-lookup"><span data-stu-id="dae19-117">This flag is used primarily in merge scenarios.</span></span>|  
|`miPreserveSig`|<span data-ttu-id="dae19-118">メソッドのシグネチャは、その HRESULT 変換では変形ことはできませんを指定します。</span><span class="sxs-lookup"><span data-stu-id="dae19-118">Specifies that the method signature cannot be mangled for an HRESULT conversion.</span></span>|  
|`miInternalCall`|<span data-ttu-id="dae19-119">共通言語ランタイムでは、内部使用のため予約されています。</span><span class="sxs-lookup"><span data-stu-id="dae19-119">Reserved for internal use by the common language runtime.</span></span>|  
|`miSynchronized`|<span data-ttu-id="dae19-120">メソッドがその内部から、シングル スレッドであるを指定します。</span><span class="sxs-lookup"><span data-stu-id="dae19-120">Specifies that the method is single-threaded through its body.</span></span>|  
|`miNoInlining`|<span data-ttu-id="dae19-121">メソッドがインライン化できないことを指定します。</span><span class="sxs-lookup"><span data-stu-id="dae19-121">Specifies that the method cannot be inlined.</span></span>|  
|`miAggressiveInlining`|<span data-ttu-id="dae19-122">メソッドがインライン化できません可能な場合を指定します。</span><span class="sxs-lookup"><span data-stu-id="dae19-122">Specifies that the method should be inlined if possible.</span></span>|  
|`miNoOptimization`|<span data-ttu-id="dae19-123">メソッドを最適化されていないことを指定します。</span><span class="sxs-lookup"><span data-stu-id="dae19-123">Specifies that the method should not be optimized.</span></span>|  
|`miMaxMethodImplVal`|<span data-ttu-id="dae19-124">最大有効値、`CorMethodImpl`します。</span><span class="sxs-lookup"><span data-stu-id="dae19-124">The maximum valid value for a `CorMethodImpl`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="dae19-125">必要条件</span><span class="sxs-lookup"><span data-stu-id="dae19-125">Requirements</span></span>  
 <span data-ttu-id="dae19-126">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="dae19-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dae19-127">**ヘッダー:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="dae19-127">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="dae19-128">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dae19-128">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dae19-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="dae19-129">See also</span></span>
- [<span data-ttu-id="dae19-130">メタデータ列挙型</span><span class="sxs-lookup"><span data-stu-id="dae19-130">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
