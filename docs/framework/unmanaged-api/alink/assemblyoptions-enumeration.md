---
title: AssemblyOptions 列挙体
ms.date: 03/30/2017
api_name:
- AssemblyOptions
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- AssemblyOptions
helpviewer_keywords:
- Alink API, AssemblyOptions enumeration
- AssemblyOptions enumeration
ms.assetid: 84f83921-64cb-49e3-ac8b-22a0b77b18a8
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 293787d7798768ff2b4e2fb8fec9ed201fdb85ff
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59085416"
---
# <a name="assemblyoptions-enumeration"></a><span data-ttu-id="b8f60-102">AssemblyOptions 列挙体</span><span class="sxs-lookup"><span data-stu-id="b8f60-102">AssemblyOptions Enumeration</span></span>
<span data-ttu-id="b8f60-103">アセンブリ オプションを列挙します。</span><span class="sxs-lookup"><span data-stu-id="b8f60-103">Enumerates the assembly options.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8f60-104">構文</span><span class="sxs-lookup"><span data-stu-id="b8f60-104">Syntax</span></span>  
  
```  
typedef enum _AssemblyOptions {  
    optAssemTitle = 0,  
    optAssemDescription,  
    optAssemConfig,  
    optAssemOS,  
    optAssemProcessor,  
    optAssemLocale,  
    optAssemVersion,  
    optAssemCompany,  
    optAssemProduct,  
    optAssemProductVersion,  
    optAssemCopyright,  
    optAssemTrademark,  
    optAssemKeyFile,  
    optAssemKeyName,  
    optAssemAlgID,  
    optAssemFlags,  
    optAssemHalfSign,  
    optAssemFileVersion,  
    optAssemSatelliteVer,  
    optLastAssemOption  
}   AssemblyOptions;  
```  
  
## <a name="fields"></a><span data-ttu-id="b8f60-105">フィールド</span><span class="sxs-lookup"><span data-stu-id="b8f60-105">Fields</span></span>  
  
|<span data-ttu-id="b8f60-106">フィールド</span><span class="sxs-lookup"><span data-stu-id="b8f60-106">Field</span></span>|<span data-ttu-id="b8f60-107">説明</span><span class="sxs-lookup"><span data-stu-id="b8f60-107">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="b8f60-108">optAssemTitle</span><span class="sxs-lookup"><span data-stu-id="b8f60-108">optAssemTitle</span></span>|<span data-ttu-id="b8f60-109">文字列 - アセンブリのタイトルを表します。</span><span class="sxs-lookup"><span data-stu-id="b8f60-109">String - Represents the assembly title.</span></span>|  
|<span data-ttu-id="b8f60-110">optAssemDescription</span><span class="sxs-lookup"><span data-stu-id="b8f60-110">optAssemDescription</span></span>|<span data-ttu-id="b8f60-111">文字列 - アセンブリの説明が含まれています。</span><span class="sxs-lookup"><span data-stu-id="b8f60-111">String - Contains the assembly description.</span></span>|  
|<span data-ttu-id="b8f60-112">optAssemConfig</span><span class="sxs-lookup"><span data-stu-id="b8f60-112">optAssemConfig</span></span>|<span data-ttu-id="b8f60-113">文字列 - アセンブリの構成が含まれています。</span><span class="sxs-lookup"><span data-stu-id="b8f60-113">String - Contains the assembly configuration.</span></span>|  
|<span data-ttu-id="b8f60-114">optAssemOS</span><span class="sxs-lookup"><span data-stu-id="b8f60-114">optAssemOS</span></span>|<span data-ttu-id="b8f60-115">-エンコードされた文字列:"dwOSPlatformId.dwOSMajorVersion.dwOSMinorVersion"。</span><span class="sxs-lookup"><span data-stu-id="b8f60-115">String - Encoded as: "dwOSPlatformId.dwOSMajorVersion.dwOSMinorVersion".</span></span>|  
|<span data-ttu-id="b8f60-116">optAssemProcessor</span><span class="sxs-lookup"><span data-stu-id="b8f60-116">optAssemProcessor</span></span>|<span data-ttu-id="b8f60-117">ULONG</span><span class="sxs-lookup"><span data-stu-id="b8f60-117">ULONG</span></span>|  
|<span data-ttu-id="b8f60-118">optAssemLocale</span><span class="sxs-lookup"><span data-stu-id="b8f60-118">optAssemLocale</span></span>|<span data-ttu-id="b8f60-119">文字列 - アセンブリのロケールが含まれています。</span><span class="sxs-lookup"><span data-stu-id="b8f60-119">String - Contains the assembly locale.</span></span>|  
|<span data-ttu-id="b8f60-120">optAssemVersion</span><span class="sxs-lookup"><span data-stu-id="b8f60-120">optAssemVersion</span></span>|<span data-ttu-id="b8f60-121">文字列 - としてエンコードされます。"Major.Minor.Build.Revision"。</span><span class="sxs-lookup"><span data-stu-id="b8f60-121">String - Encoded as: "Major.Minor.Build.Revision".</span></span>|  
|<span data-ttu-id="b8f60-122">optAssemCompany</span><span class="sxs-lookup"><span data-stu-id="b8f60-122">optAssemCompany</span></span>|<span data-ttu-id="b8f60-123">文字列 - 会社が含まれています。</span><span class="sxs-lookup"><span data-stu-id="b8f60-123">String - Contains the company.</span></span>|  
|<span data-ttu-id="b8f60-124">optAssemProduct</span><span class="sxs-lookup"><span data-stu-id="b8f60-124">optAssemProduct</span></span>|<span data-ttu-id="b8f60-125">文字列 - 製品名が含まれています。</span><span class="sxs-lookup"><span data-stu-id="b8f60-125">String - Contains the product name.</span></span>|  
|<span data-ttu-id="b8f60-126">optAssemProductVersion</span><span class="sxs-lookup"><span data-stu-id="b8f60-126">optAssemProductVersion</span></span>|<span data-ttu-id="b8f60-127">文字列 (InformationalVersion とも呼ばれます)。</span><span class="sxs-lookup"><span data-stu-id="b8f60-127">String (also known as InformationalVersion).</span></span>|  
|<span data-ttu-id="b8f60-128">optAssemCopyright</span><span class="sxs-lookup"><span data-stu-id="b8f60-128">optAssemCopyright</span></span>|<span data-ttu-id="b8f60-129">文字列 - 著作権情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="b8f60-129">String - Contains the copyright information.</span></span>|  
|<span data-ttu-id="b8f60-130">optAssemTrademark</span><span class="sxs-lookup"><span data-stu-id="b8f60-130">optAssemTrademark</span></span>|<span data-ttu-id="b8f60-131">文字列 - 商標に関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="b8f60-131">String - Contains the trademark information.</span></span>|  
|<span data-ttu-id="b8f60-132">optAssemKeyFile</span><span class="sxs-lookup"><span data-stu-id="b8f60-132">optAssemKeyFile</span></span>|<span data-ttu-id="b8f60-133">String (ファイル名)。</span><span class="sxs-lookup"><span data-stu-id="b8f60-133">String (file name).</span></span>|  
|<span data-ttu-id="b8f60-134">optAssemKeyName</span><span class="sxs-lookup"><span data-stu-id="b8f60-134">optAssemKeyName</span></span>|<span data-ttu-id="b8f60-135">文字列 (キー名)。</span><span class="sxs-lookup"><span data-stu-id="b8f60-135">String (The key name).</span></span>|  
|<span data-ttu-id="b8f60-136">optAssemAlgID</span><span class="sxs-lookup"><span data-stu-id="b8f60-136">optAssemAlgID</span></span>|<span data-ttu-id="b8f60-137">ULONG</span><span class="sxs-lookup"><span data-stu-id="b8f60-137">ULONG</span></span>|  
|<span data-ttu-id="b8f60-138">optAssemFlags</span><span class="sxs-lookup"><span data-stu-id="b8f60-138">optAssemFlags</span></span>|<span data-ttu-id="b8f60-139">ULONG</span><span class="sxs-lookup"><span data-stu-id="b8f60-139">ULONG</span></span>|  
|<span data-ttu-id="b8f60-140">optAssemHalfSign</span><span class="sxs-lookup"><span data-stu-id="b8f60-140">optAssemHalfSign</span></span>|<span data-ttu-id="b8f60-141">Bool (DelaySign とも呼ばれます)。</span><span class="sxs-lookup"><span data-stu-id="b8f60-141">Bool (Also known as DelaySign).</span></span>|  
|<span data-ttu-id="b8f60-142">optAssemFileVersion</span><span class="sxs-lookup"><span data-stu-id="b8f60-142">optAssemFileVersion</span></span>|<span data-ttu-id="b8f60-143">文字列 -"Major.Minor.Build.Revision"--ProductVersion と同じようにエンコードします。</span><span class="sxs-lookup"><span data-stu-id="b8f60-143">String - Encoded as "Major.Minor.Build.Revision"--same as ProductVersion.</span></span>|  
|<span data-ttu-id="b8f60-144">optAssemSatelliteVer</span><span class="sxs-lookup"><span data-stu-id="b8f60-144">optAssemSatelliteVer</span></span>|<span data-ttu-id="b8f60-145">文字列の"Major.Minor.Build.Revision"としてエンコードされます。</span><span class="sxs-lookup"><span data-stu-id="b8f60-145">String - Encoded as "Major.Minor.Build.Revision".</span></span>|  
|<span data-ttu-id="b8f60-146">optLastAssemOption</span><span class="sxs-lookup"><span data-stu-id="b8f60-146">optLastAssemOption</span></span>|<span data-ttu-id="b8f60-147">要素の数のカウンター。</span><span class="sxs-lookup"><span data-stu-id="b8f60-147">A counter of the number of elements.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b8f60-148">必要条件</span><span class="sxs-lookup"><span data-stu-id="b8f60-148">Requirements</span></span>  
 <span data-ttu-id="b8f60-149">**ヘッダー:** alink.h</span><span class="sxs-lookup"><span data-stu-id="b8f60-149">**Header:** alink.h</span></span>  
  
 <span data-ttu-id="b8f60-150">**ライブラリ**: alink.dll</span><span class="sxs-lookup"><span data-stu-id="b8f60-150">**Library**: alink.dll</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8f60-151">関連項目</span><span class="sxs-lookup"><span data-stu-id="b8f60-151">See also</span></span>

- [<span data-ttu-id="b8f60-152">Al.exe (アセンブリ リンカー)</span><span class="sxs-lookup"><span data-stu-id="b8f60-152">Al.exe (Assembly Linker)</span></span>](../../../../docs/framework/tools/al-exe-assembly-linker.md)
