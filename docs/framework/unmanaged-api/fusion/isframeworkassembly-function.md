---
title: IsFrameworkAssembly 関数
ms.date: 03/30/2017
api_name:
- IsFrameworkAssembly
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IsFrameworkAssembly
helpviewer_keywords:
- IsFrameworkAssembly function [.NET Framework fusion]
ms.assetid: b0c6f19b-d4fd-4971-88f0-12ffb5793da3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d0fb4c98ff2c8b071f05b42aefed61485001e97f
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57480326"
---
# <a name="isframeworkassembly-function"></a><span data-ttu-id="12cec-102">IsFrameworkAssembly 関数</span><span class="sxs-lookup"><span data-stu-id="12cec-102">IsFrameworkAssembly Function</span></span>
<span data-ttu-id="12cec-103">指定したアセンブリが管理されているかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="12cec-103">Gets a value that indicates whether the specified assembly is managed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="12cec-104">構文</span><span class="sxs-lookup"><span data-stu-id="12cec-104">Syntax</span></span>  
  
```  
HRESULT IsFrameworkAssembly (  
    [in]  LPCWSTR pwzAssemblyReference,  
    [out] LPBOOL  pbIsFrameworkAssembly,  
    [in]  LPWSTR  pwzFrameworkAssemblyIdentity,  
    [in]  LPDWORD pccSize  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="12cec-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="12cec-105">Parameters</span></span>  
 `pwzAssemblyReference`  
 <span data-ttu-id="12cec-106">[in]チェック対象のアセンブリの名前。</span><span class="sxs-lookup"><span data-stu-id="12cec-106">[in] The name of the assembly to check.</span></span>  
  
 `pbIsFrameworkAssembly`  
 <span data-ttu-id="12cec-107">[out]アセンブリが管理されているかどうかを示すブール値。</span><span class="sxs-lookup"><span data-stu-id="12cec-107">[out] A Boolean value that indicates whether the assembly is managed.</span></span>  
  
 `pwzFrameworkAssemblyIdentity`  
 <span data-ttu-id="12cec-108">[in]アセンブリの一意の id を含む uncanonicalized 文字列。</span><span class="sxs-lookup"><span data-stu-id="12cec-108">[in] An uncanonicalized string that contains the unique identity of the assembly.</span></span>  
  
 `pccSize`  
 <span data-ttu-id="12cec-109">[入力] `pwzFrameworkAssemblyIdentity` のサイズ。</span><span class="sxs-lookup"><span data-stu-id="12cec-109">[in] The size of `pwzFrameworkAssemblyIdentity`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="12cec-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="12cec-110">Remarks</span></span>  
 <span data-ttu-id="12cec-111">`pwzAssemblyReference`パラメーターは、アセンブリの名前を含む文字列へのポインターです。</span><span class="sxs-lookup"><span data-stu-id="12cec-111">The `pwzAssemblyReference` parameter is a pointer to a character string that contains the name of an assembly.</span></span>  
  
 <span data-ttu-id="12cec-112">このアセンブリが、.NET Framework の一部である場合、`pbIsFrameworkAssembly`パラメーターはブール値を含む`true`します。</span><span class="sxs-lookup"><span data-stu-id="12cec-112">If this assembly is part of the .NET Framework, the `pbIsFrameworkAssembly` parameter will contain a Boolean value of `true`.</span></span>  
  
 <span data-ttu-id="12cec-113">名前付きのアセンブリ、.NET Framework の一部でない場合、または場合、`pwzAssemblyReference`パラメーターは、アセンブリを指定していない`pbIsFrameworkAssembly`のブール値を含む`false`します。</span><span class="sxs-lookup"><span data-stu-id="12cec-113">If the named assembly is not part of the .NET Framework, or if the `pwzAssemblyReference` parameter does not name an assembly, `pbIsFrameworkAssembly` will contain a Boolean value of `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="12cec-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="12cec-114">Requirements</span></span>  
 <span data-ttu-id="12cec-115">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="12cec-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12cec-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="12cec-116">See also</span></span>
- [<span data-ttu-id="12cec-117">Fusion グローバル静的関数</span><span class="sxs-lookup"><span data-stu-id="12cec-117">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
