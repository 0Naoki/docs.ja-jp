---
title: CorPEKind 列挙型
ms.date: 03/30/2017
api_name:
- CorPEKind
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorPEKind
helpviewer_keywords:
- CorPEKind enumeration [.NET Framework metadata]
ms.assetid: 22dc6dea-b1b9-4982-a730-a022d586b117
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d8f830ca7e273b65dc9ec77566a02df6c32cd464
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59202392"
---
# <a name="corpekind-enumeration"></a><span data-ttu-id="8822e-102">CorPEKind 列挙型</span><span class="sxs-lookup"><span data-stu-id="8822e-102">CorPEKind Enumeration</span></span>
<span data-ttu-id="8822e-103">呼び出しから返される、ポータブル実行可能 (PE) ファイルを記述する値を含む[imetadataimport 2::getpekind](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getpekind-method.md)します。</span><span class="sxs-lookup"><span data-stu-id="8822e-103">Contains values that describe a portable executable (PE) file, as returned from a call to [IMetaDataImport2::GetPEKind](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getpekind-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8822e-104">構文</span><span class="sxs-lookup"><span data-stu-id="8822e-104">Syntax</span></span>  
  
```  
typedef enum CorPEKind {  
  
    peNot           = 0x00000000,  
    peILonly        = 0x00000001,  
    pe32BitRequired = 0x00000002,  
    pe32Plus        = 0x00000004,  
    pe32Unmanaged   = 0x00000008,  
    pe32BitPreferred= 0x00000010  
  
} CorPEKind;  
```  
  
## <a name="members"></a><span data-ttu-id="8822e-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="8822e-105">Members</span></span>  
  
|<span data-ttu-id="8822e-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="8822e-106">Member</span></span>|<span data-ttu-id="8822e-107">説明</span><span class="sxs-lookup"><span data-stu-id="8822e-107">Description</span></span>|  
|------------|-----------------|  
|`peNot`|<span data-ttu-id="8822e-108">PE ファイルではないことを示します。</span><span class="sxs-lookup"><span data-stu-id="8822e-108">Indicates that this is not a PE file.</span></span>|  
|`peILOnly`|<span data-ttu-id="8822e-109">この PE ファイルには、マネージ コードだけが含まれていることを示します。</span><span class="sxs-lookup"><span data-stu-id="8822e-109">Indicates that this PE file contains only managed code.</span></span>|  
|`pe32BitRequired`|<span data-ttu-id="8822e-110">この PE ファイルが Win32 呼び出しを行うことを示します。</span><span class="sxs-lookup"><span data-stu-id="8822e-110">Indicates that this PE file makes Win32 calls.</span></span>|  
|`pe32Plus`|<span data-ttu-id="8822e-111">64 ビット プラットフォームでこの PE ファイルを実行することを示します。</span><span class="sxs-lookup"><span data-stu-id="8822e-111">Indicates that this PE file runs on a 64-bit platform.</span></span>|  
|`pe32Unmanaged`|<span data-ttu-id="8822e-112">この PE ファイルがネイティブ コードであることを示します。</span><span class="sxs-lookup"><span data-stu-id="8822e-112">Indicates that this PE file is native code.</span></span>|  
|<span data-ttu-id="8822e-113">pe32BitPreferred</span><span class="sxs-lookup"><span data-stu-id="8822e-113">pe32BitPreferred</span></span>|<span data-ttu-id="8822e-114">この PE ファイルが 32 ビット環境に読み込むことが推奨プラットフォームに依存しないことを示します。</span><span class="sxs-lookup"><span data-stu-id="8822e-114">Indicates that this PE file is platform-neutral and prefers to be loaded in a 32-bit environment.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8822e-115">Remarks</span><span class="sxs-lookup"><span data-stu-id="8822e-115">Remarks</span></span>  
 <span data-ttu-id="8822e-116">これらの値は、ビットごとの組み合わせで使用できます。</span><span class="sxs-lookup"><span data-stu-id="8822e-116">These values can be used in bitwise combinations.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8822e-117">必要条件</span><span class="sxs-lookup"><span data-stu-id="8822e-117">Requirements</span></span>  
 <span data-ttu-id="8822e-118">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8822e-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8822e-119">**ヘッダー:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="8822e-119">**Header:** CorHdr.h</span></span>  
  
 **<span data-ttu-id="8822e-120">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="8822e-120">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="8822e-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="8822e-121">See also</span></span>

- [<span data-ttu-id="8822e-122">メタデータ列挙体</span><span class="sxs-lookup"><span data-stu-id="8822e-122">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
