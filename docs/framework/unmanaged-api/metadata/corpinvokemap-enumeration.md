---
title: CorPinvokeMap 列挙型
ms.date: 03/30/2017
api_name:
- CorPinvokeMap
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorPinvokeMap
helpviewer_keywords:
- CorPinvokeMap enumeration [.NET Framework metadata]
ms.assetid: f14f986e-f6ce-42bc-aa23-18150c46d28c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 951941092f67f66c5b17c8ae592569c2a8e6a675
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59079631"
---
# <a name="corpinvokemap-enumeration"></a><span data-ttu-id="7d9de-102">CorPinvokeMap 列挙型</span><span class="sxs-lookup"><span data-stu-id="7d9de-102">CorPinvokeMap Enumeration</span></span>
<span data-ttu-id="7d9de-103">PInvoke 呼び出しのオプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="7d9de-103">Specifies options for a PInvoke call.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d9de-104">構文</span><span class="sxs-lookup"><span data-stu-id="7d9de-104">Syntax</span></span>  
  
```  
typedef enum  CorPinvokeMap {  
  
    pmNoMangle          = 0x0001,  
  
    pmCharSetMask       = 0x0006,  
    pmCharSetNotSpec    = 0x0000,  
    pmCharSetAnsi       = 0x0002,  
    pmCharSetUnicode    = 0x0004,  
    pmCharSetAuto       = 0x0006,  
  
    pmBestFitUseAssem   = 0x0000,  
    pmBestFitEnabled    = 0x0010,  
    pmBestFitDisabled   = 0x0020,  
    pmBestFitMask       = 0x0030,  
  
    pmThrowOnUnmappableCharUseAssem   = 0x0000,  
    pmThrowOnUnmappableCharEnabled    = 0x1000,  
    pmThrowOnUnmappableCharDisabled   = 0x2000,  
    pmThrowOnUnmappableCharMask       = 0x3000,  
  
    pmSupportsLastError = 0x0040,   
  
    pmCallConvMask      = 0x0700,  
    pmCallConvWinapi    = 0x0100,  
    pmCallConvCdecl     = 0x0200,  
    pmCallConvStdcall   = 0x0300,  
    pmCallConvThiscall  = 0x0400,  
    pmCallConvFastcall  = 0x0500,  
  
    pmMaxValue          = 0xFFFF  
  
} CorPinvokeMap;  
```  
  
## <a name="members"></a><span data-ttu-id="7d9de-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="7d9de-105">Members</span></span>  
  
|<span data-ttu-id="7d9de-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="7d9de-106">Member</span></span>|<span data-ttu-id="7d9de-107">説明</span><span class="sxs-lookup"><span data-stu-id="7d9de-107">Description</span></span>|  
|------------|-----------------|  
|`pmNoMangle`|<span data-ttu-id="7d9de-108">指定された各メンバー名を使用します。</span><span class="sxs-lookup"><span data-stu-id="7d9de-108">Use each member name as specified.</span></span>|  
|`pmCharSetMask`|<span data-ttu-id="7d9de-109">予約済み。</span><span class="sxs-lookup"><span data-stu-id="7d9de-109">Reserved.</span></span>|  
|`pmCharSetNotSpec`|<span data-ttu-id="7d9de-110">予約済み。</span><span class="sxs-lookup"><span data-stu-id="7d9de-110">Reserved.</span></span>|  
|`pmCharSetAnsi`|<span data-ttu-id="7d9de-111">マルチ バイト文字の文字列として文字列をマーシャ リングします。</span><span class="sxs-lookup"><span data-stu-id="7d9de-111">Marshal strings as multiple-byte character strings.</span></span>|  
|`pmCharSetUnicode`|<span data-ttu-id="7d9de-112">Unicode 2 バイト文字の文字列をマーシャ リングします。</span><span class="sxs-lookup"><span data-stu-id="7d9de-112">Marshal strings as Unicode 2-byte characters.</span></span>|  
|`pmCharSetAuto`|<span data-ttu-id="7d9de-113">自動的に対象のオペレーティング システムを適切に文字列をマーシャ リングします。</span><span class="sxs-lookup"><span data-stu-id="7d9de-113">Automatically marshal strings appropriately for the target operating system.</span></span> <span data-ttu-id="7d9de-114">既定値は Unicode では、Windows NT、Windows 2000、Windows XP、および Windows Server 2003 ファミリです。既定値はし、Windows 98 および Windows me では ANSI</span><span class="sxs-lookup"><span data-stu-id="7d9de-114">The default is Unicode on Windows NT, Windows 2000, Windows XP, and the Windows Server 2003 family; the default is ANSI on Windows 98 and Windows Me.</span></span>|  
|`pmBestFitUseAssem`|<span data-ttu-id="7d9de-115">予約済み。</span><span class="sxs-lookup"><span data-stu-id="7d9de-115">Reserved.</span></span>|  
|`pmBestFitEnabled`|<span data-ttu-id="7d9de-116">ANSI 文字セットで一致がない Unicode 文字の最適なマッピングを実行します。</span><span class="sxs-lookup"><span data-stu-id="7d9de-116">Perform best-fit mapping of Unicode characters that lack an exact match in the ANSI character set.</span></span>|  
|`pmBestFitDisabled`|<span data-ttu-id="7d9de-117">Unicode 文字の最適なマッピングを実行しません。</span><span class="sxs-lookup"><span data-stu-id="7d9de-117">Do not perform best-fit mapping of Unicode characters.</span></span> <span data-ttu-id="7d9de-118">この場合、すべてのマップできない文字に置き換えられます、'?' です。</span><span class="sxs-lookup"><span data-stu-id="7d9de-118">In this case, all unmappable characters will be replaced by a ‘?’.</span></span>|  
|`pmBestFitMask`|<span data-ttu-id="7d9de-119">予約済み。</span><span class="sxs-lookup"><span data-stu-id="7d9de-119">Reserved.</span></span>|  
|`pmThrowOnUnmappableCharUseAssem`|<span data-ttu-id="7d9de-120">予約済み。</span><span class="sxs-lookup"><span data-stu-id="7d9de-120">Reserved.</span></span>|  
|`pmThrowOnUnmappableCharEnabled`|<span data-ttu-id="7d9de-121">相互運用マーシャラーは、マップできない文字を検出した場合は、例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="7d9de-121">Throw an exception when the interop marshaler encounters an unmappable character.</span></span>|  
|`pmThrowOnUnmappableCharDisabled`|<span data-ttu-id="7d9de-122">相互運用マーシャラーは、マップできない文字を検出したときに例外をスローしません。</span><span class="sxs-lookup"><span data-stu-id="7d9de-122">Do not throw an exception when the interop marshaler encounters an unmappable character.</span></span>|  
|`pmThrowOnUnmappableCharMask`|<span data-ttu-id="7d9de-123">予約されています。</span><span class="sxs-lookup"><span data-stu-id="7d9de-123">Reserved</span></span>|  
|`pmSupportsLastError`|<span data-ttu-id="7d9de-124">呼び出す、Win32 呼び出しを許可する`SetLastError`属性付きメソッドから戻る前に関数。</span><span class="sxs-lookup"><span data-stu-id="7d9de-124">Allow the callee to call the Win32 `SetLastError` function before returning from the attributed method.</span></span>|  
|`pmCallConvMask`|<span data-ttu-id="7d9de-125">予約されています。</span><span class="sxs-lookup"><span data-stu-id="7d9de-125">Reserved</span></span>|  
|`pmCallConvWinapi`|<span data-ttu-id="7d9de-126">既定のプラットフォーム呼び出し規約を使用します。</span><span class="sxs-lookup"><span data-stu-id="7d9de-126">Use the default platform calling convention.</span></span> <span data-ttu-id="7d9de-127">たとえば、Windows の既定値は`StdCall`とは、Windows CE .NET`Cdecl`します。</span><span class="sxs-lookup"><span data-stu-id="7d9de-127">For example, on Windows the default is `StdCall` and on Windows CE .NET it is `Cdecl`.</span></span>|  
|`pmCallConvCdecl`|<span data-ttu-id="7d9de-128">使用して、`Cdecl`呼び出し規約。</span><span class="sxs-lookup"><span data-stu-id="7d9de-128">Use the `Cdecl` calling convention.</span></span> <span data-ttu-id="7d9de-129">この場合、呼び出し元がスタックを消去します。</span><span class="sxs-lookup"><span data-stu-id="7d9de-129">In this case, the caller cleans the stack.</span></span> <span data-ttu-id="7d9de-130">これにより、関数を呼び出す`varargs`(可変個のパラメーターを受け入れる関数)。</span><span class="sxs-lookup"><span data-stu-id="7d9de-130">This enables calling functions with `varargs` (that is, functions that accept a variable number of parameters).</span></span>|  
|`pmCallConvStdcall`|<span data-ttu-id="7d9de-131">使用して、`StdCall`呼び出し規約。</span><span class="sxs-lookup"><span data-stu-id="7d9de-131">Use the `StdCall` calling convention.</span></span> <span data-ttu-id="7d9de-132">この場合、呼び出し先がスタックを消去します。</span><span class="sxs-lookup"><span data-stu-id="7d9de-132">In this case, the callee cleans the stack.</span></span> <span data-ttu-id="7d9de-133">これは、アンマネージ関数を呼び出すプラットフォーム呼び出しの既定の規則です。</span><span class="sxs-lookup"><span data-stu-id="7d9de-133">This is the default convention for calling unmanaged functions with platform invoke.</span></span>|  
|`pmCallConvThiscall`|<span data-ttu-id="7d9de-134">使用して、`ThisCall`呼び出し規約。</span><span class="sxs-lookup"><span data-stu-id="7d9de-134">Use the `ThisCall` calling convention.</span></span> <span data-ttu-id="7d9de-135">この場合は、最初のパラメーターは、`this`ポインター レジスタ ECX に格納されます。</span><span class="sxs-lookup"><span data-stu-id="7d9de-135">In this case, the first parameter is the `this` pointer and is stored in register ECX.</span></span> <span data-ttu-id="7d9de-136">その他のパラメーターは、スタックにプッシュされます。</span><span class="sxs-lookup"><span data-stu-id="7d9de-136">Other parameters are pushed on the stack.</span></span> <span data-ttu-id="7d9de-137">`ThisCall`アンマネージ DLL からエクスポートしたクラスのメソッドの呼び出しに使用呼び出し規約。</span><span class="sxs-lookup"><span data-stu-id="7d9de-137">The `ThisCall` calling convention is used to call methods on classes exported from an unmanaged DLL.</span></span>|  
|`pmCallConvFastcall`|<span data-ttu-id="7d9de-138">予約済み。</span><span class="sxs-lookup"><span data-stu-id="7d9de-138">Reserved.</span></span>|  
|`pmMaxValue`|<span data-ttu-id="7d9de-139">予約済み。</span><span class="sxs-lookup"><span data-stu-id="7d9de-139">Reserved.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7d9de-140">必要条件</span><span class="sxs-lookup"><span data-stu-id="7d9de-140">Requirements</span></span>  
 <span data-ttu-id="7d9de-141">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7d9de-141">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7d9de-142">**ヘッダー:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="7d9de-142">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="7d9de-143">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7d9de-143">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d9de-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="7d9de-144">See also</span></span>

- [<span data-ttu-id="7d9de-145">メタデータ列挙型</span><span class="sxs-lookup"><span data-stu-id="7d9de-145">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
