---
title: ASSEMBLY_INFO 構造体
ms.date: 03/30/2017
api_name:
- ASSEMBLY_INFO
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- ASSEMBLY_INFO
helpviewer_keywords:
- ASSEMBLY_INFO structure [.NET Framework fusion]
ms.assetid: b3cbb47c-457f-4083-8895-49562ca99ab8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bae19ec18c54eccc7aa54d2d3a006f36ba8ab762
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59110878"
---
# <a name="assemblyinfo-structure"></a><span data-ttu-id="59f71-102">ASSEMBLY_INFO 構造体</span><span class="sxs-lookup"><span data-stu-id="59f71-102">ASSEMBLY_INFO Structure</span></span>
<span data-ttu-id="59f71-103">グローバル アセンブリ キャッシュに登録されているアセンブリに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="59f71-103">Contains information about an assembly that is registered in the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59f71-104">構文</span><span class="sxs-lookup"><span data-stu-id="59f71-104">Syntax</span></span>  
  
```  
typedef struct _ASSEMBLY_INFO {  
    ULONG           cbAssemblyInfo;  
    DWORD           dwAssemblyFlags;  
    ULARGE_INTEGER  uliAssemblySizeInKB;  
    LPWSTR          pszCurrentAssemblyPathBuf;  
    ULONG           cchBuf;  
} ASSEMBLY_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="59f71-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="59f71-105">Members</span></span>  
  
|<span data-ttu-id="59f71-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="59f71-106">Member</span></span>|<span data-ttu-id="59f71-107">説明</span><span class="sxs-lookup"><span data-stu-id="59f71-107">Description</span></span>|  
|------------|-----------------|  
|`cbAssemblyInfo`|<span data-ttu-id="59f71-108">構造体のバイト単位のサイズ。</span><span class="sxs-lookup"><span data-stu-id="59f71-108">The size, in bytes, of the structure.</span></span> <span data-ttu-id="59f71-109">このフィールドは、将来の機能拡張予約されています。</span><span class="sxs-lookup"><span data-stu-id="59f71-109">This field is reserved for future extensibility.</span></span>|  
|`dwAssemblyFlags`|<span data-ttu-id="59f71-110">アセンブリのインストールの詳細を示すフラグです。</span><span class="sxs-lookup"><span data-stu-id="59f71-110">Flags that indicate installation details about the assembly.</span></span> <span data-ttu-id="59f71-111">次の値がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="59f71-111">The following values are supported:</span></span><br /><br /> <span data-ttu-id="59f71-112">-ASSEMBLYINFO_FLAG_INSTALLED 値、アセンブリがインストールされていることを示します。</span><span class="sxs-lookup"><span data-stu-id="59f71-112">-   The ASSEMBLYINFO_FLAG_INSTALLED value, which indicates that the assembly is installed.</span></span> <span data-ttu-id="59f71-113">.NET Framework の現在のバージョンが常に設定`dwAssemblyFlags`この値にします。</span><span class="sxs-lookup"><span data-stu-id="59f71-113">The current version of the .NET Framework always sets `dwAssemblyFlags` to this value.</span></span><br /><span data-ttu-id="59f71-114">-ASSEMBLYINFO_FLAG_PAYLOADRESIDENT 値、アセンブリが常駐ペイロードであることを示します。</span><span class="sxs-lookup"><span data-stu-id="59f71-114">-   The ASSEMBLYINFO_FLAG_PAYLOADRESIDENT value, which indicates that the assembly is a payload resident.</span></span> <span data-ttu-id="59f71-115">.NET Framework の現在のバージョンを設定しません`dwAssemblyFlags`この値にします。</span><span class="sxs-lookup"><span data-stu-id="59f71-115">The current version of the .NET Framework never sets `dwAssemblyFlags` to this value.</span></span>|  
|`uliAssemblySizeInKB`|<span data-ttu-id="59f71-116">アセンブリに含まれるファイルの合計サイズ。</span><span class="sxs-lookup"><span data-stu-id="59f71-116">The total size, in kilobytes, of the files that the assembly contains.</span></span>|  
|`pszCurrentAssemblyPathBuf`|<span data-ttu-id="59f71-117">マニフェスト ファイルに、現在のパスを保持する文字列バッファーへのポインター。</span><span class="sxs-lookup"><span data-stu-id="59f71-117">A pointer to a string buffer that holds the current path to the manifest file.</span></span> <span data-ttu-id="59f71-118">パスの末尾に null 文字を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="59f71-118">The path must end with a null character.</span></span>|  
|`cchBuf`|<span data-ttu-id="59f71-119">Null の終端文字を含め、ワイド文字の数を`pszCurrentAssemblyPathBuf`が含まれています。</span><span class="sxs-lookup"><span data-stu-id="59f71-119">The number of wide characters, including the null terminator, that `pszCurrentAssemblyPathBuf` contains.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="59f71-120">必要条件</span><span class="sxs-lookup"><span data-stu-id="59f71-120">Requirements</span></span>  
 <span data-ttu-id="59f71-121">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="59f71-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="59f71-122">**ヘッダー:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="59f71-122">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="59f71-123">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="59f71-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59f71-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="59f71-124">See also</span></span>

- [<span data-ttu-id="59f71-125">Fusion 構造体</span><span class="sxs-lookup"><span data-stu-id="59f71-125">Fusion Structures</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-structures.md)
- [<span data-ttu-id="59f71-126">グローバル アセンブリ キャッシュ</span><span class="sxs-lookup"><span data-stu-id="59f71-126">Global Assembly Cache</span></span>](../../../../docs/framework/app-domains/gac.md)
