---
title: RUNTIME_INFO_FLAGS 列挙型
ms.date: 03/30/2017
api_name:
- RUNTIME_INFO_FLAGS
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- RUNTIME_INFO_FLAGS
helpviewer_keywords:
- RUNTIME_INFO_FLAGS enumeration [.NET Framework hosting]
ms.assetid: adba37be-f775-4cdb-8919-5746ce694f33
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 09bd32172bcad298eebc2921461fdc953e9c6d6e
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2018
ms.locfileid: "43866161"
---
# <a name="runtimeinfoflags-enumeration"></a><span data-ttu-id="6e6c1-102">RUNTIME_INFO_FLAGS 列挙型</span><span class="sxs-lookup"><span data-stu-id="6e6c1-102">RUNTIME_INFO_FLAGS Enumeration</span></span>
<span data-ttu-id="6e6c1-103">共通言語ランタイム (CLR) に関する情報を返す必要があるかを示す値が含まれています。</span><span class="sxs-lookup"><span data-stu-id="6e6c1-103">Contains values that indicate what information about the common language runtime (CLR) should be returned.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e6c1-104">構文</span><span class="sxs-lookup"><span data-stu-id="6e6c1-104">Syntax</span></span>  
  
```  
typedef enum {  
  
    RUNTIME_INFO_UPGRADE_VERSION             = 0x01,  
    RUNTIME_INFO_REQUEST_IA64                = 0x02,  
    RUNTIME_INFO_REQUEST_AMD64               = 0x04,  
    RUNTIME_INFO_REQUEST_X86                 = 0x08,  
    RUNTIME_INFO_DONT_RETURN_DIRECTORY       = 0x10,  
    RUNTIME_INFO_DONT_RETURN_VERSION         = 0x20,  
    RUNTIME_INFO_DONT_SHOW_ERROR_DIALOG      = 0x40,  
    RUNTIME_INFO_IGNORE_ERROR_MODE           = 0x1000  
  
} RUNTIME_INFO_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="6e6c1-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="6e6c1-105">Members</span></span>  
  
|<span data-ttu-id="6e6c1-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="6e6c1-106">Member</span></span>|<span data-ttu-id="6e6c1-107">説明</span><span class="sxs-lookup"><span data-stu-id="6e6c1-107">Description</span></span>|  
|------------|-----------------|  
|`RUNTIME_INFO_DONT_RETURN_DIRECTORY`|<span data-ttu-id="6e6c1-108">ディレクトリ情報を含める必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="6e6c1-108">Indicates that directory information should not be included.</span></span>|  
|`RUNTIME_INFO_DONT_RETURN_VERSION`|<span data-ttu-id="6e6c1-109">バージョン情報を含める必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="6e6c1-109">Indicates that version information should not be included.</span></span>|  
|`RUNTIME_INFO_DONT_SHOW_ERROR_DIALOG`|<span data-ttu-id="6e6c1-110">障害発生時にエラー ダイアログ ボックスを表示しないことを示します。</span><span class="sxs-lookup"><span data-stu-id="6e6c1-110">Indicates that an error dialog box should not be shown upon failure.</span></span>|  
|`RUNTIME_INFO_IGNORE_ERROR_MODE`|<span data-ttu-id="6e6c1-111">示します呼び出し元の効果、 [SetErrorMode](https://go.microsoft.com/fwlink/p/?LinkId=255242) SEM_FAILCRITICALERRORS フラグを使用して関数をオーバーライドする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e6c1-111">Indicates that the effects of calling the [SetErrorMode](https://go.microsoft.com/fwlink/p/?LinkId=255242) function with the SEM_FAILCRITICALERRORS flag should be overridden.</span></span> <span data-ttu-id="6e6c1-112">つまり、抑制されるのではなく、障害発生時にインストールのダイアログ ボックスを表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e6c1-112">That is, an installation dialog box should be shown upon failure, instead of being suppressed.</span></span>|  
|`RUNTIME_INFO_REQUEST_AMD64`|<span data-ttu-id="6e6c1-113">については、AMD 64 互換性のあるバージョンのランタイムの要求を示します。</span><span class="sxs-lookup"><span data-stu-id="6e6c1-113">Indicates a request for information about an AMD-64-compatible version of the runtime.</span></span>|  
|`RUNTIME_INFO_REQUEST_IA64`|<span data-ttu-id="6e6c1-114">IA 64 互換性のあるランタイムのバージョンに関する情報の要求を示します。</span><span class="sxs-lookup"><span data-stu-id="6e6c1-114">Indicates a request for information about an IA-64-compatible version of the runtime.</span></span>|  
|`RUNTIME_INFO_REQUEST_X86`|<span data-ttu-id="6e6c1-115">X86 と互換性のあるランタイムのバージョンに関する情報の要求を示します。</span><span class="sxs-lookup"><span data-stu-id="6e6c1-115">Indicates a request for information about an x86-compatible version of the runtime.</span></span>|  
|`RUNTIME_INFO_UPGRADE_VERSION`|<span data-ttu-id="6e6c1-116">バージョンのアップグレードについてを含める必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="6e6c1-116">Indicates that version upgrade information should be included.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6e6c1-117">Remarks</span><span class="sxs-lookup"><span data-stu-id="6e6c1-117">Remarks</span></span>  
 <span data-ttu-id="6e6c1-118">次のプラットフォーム アーキテクチャ フラグは、一度に 1 つのみ指定でき、組み合わせることはできません。</span><span class="sxs-lookup"><span data-stu-id="6e6c1-118">The following platform architecture flags can be specified only one at a time and cannot be combined:</span></span>  
  
-   <span data-ttu-id="6e6c1-119">RUNTIME_INFO_REQUEST_IA64</span><span class="sxs-lookup"><span data-stu-id="6e6c1-119">RUNTIME_INFO_REQUEST_IA64</span></span>  
  
-   <span data-ttu-id="6e6c1-120">RUNTIME_INFO_REQUEST_AMD64</span><span class="sxs-lookup"><span data-stu-id="6e6c1-120">RUNTIME_INFO_REQUEST_AMD64</span></span>  
  
-   <span data-ttu-id="6e6c1-121">RUNTIME_INFO_REQUEST_X86</span><span class="sxs-lookup"><span data-stu-id="6e6c1-121">RUNTIME_INFO_REQUEST_X86</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6e6c1-122">要件</span><span class="sxs-lookup"><span data-stu-id="6e6c1-122">Requirements</span></span>  
 <span data-ttu-id="6e6c1-123">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6e6c1-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6e6c1-124">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="6e6c1-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6e6c1-125">**ライブラリ:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6e6c1-125">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6e6c1-126">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6e6c1-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e6c1-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="6e6c1-127">See Also</span></span>  
 [<span data-ttu-id="6e6c1-128">ホスティングの列挙型</span><span class="sxs-lookup"><span data-stu-id="6e6c1-128">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
