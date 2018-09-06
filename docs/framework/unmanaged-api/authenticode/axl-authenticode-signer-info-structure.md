---
title: AXL_AUTHENTICODE_SIGNER_INFO 構造体
ms.date: 03/30/2017
ms.assetid: 81c0f8b4-ce35-4716-8651-b642d40648a2
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4b9f54c7c57d122ac1214b9f31cc4e1d1cddd71c
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2018
ms.locfileid: "43773326"
---
# <a name="axlauthenticodesignerinfo-structure"></a><span data-ttu-id="5168e-102">AXL_AUTHENTICODE_SIGNER_INFO 構造体</span><span class="sxs-lookup"><span data-stu-id="5168e-102">AXL_AUTHENTICODE_SIGNER_INFO Structure</span></span>
<span data-ttu-id="5168e-103">Authenticode の署名者情報を定義します。</span><span class="sxs-lookup"><span data-stu-id="5168e-103">Defines the Authenticode signer information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5168e-104">構文</span><span class="sxs-lookup"><span data-stu-id="5168e-104">Syntax</span></span>  
  
```  
typedef struct _AXL_AUTHENTICODE_SIGNER_INFO {  
    DWORD cbSize;  
    HRESULT dwError;  
    ALG_ID algHash;  
    LPCWSTR pwszHash  
    LPCWSTR pwszDescription;  
    LPCWSTR pwszDescriptionUrl;  
    PCCERT_CHAIN_CONTEXT pChainContext  
} AXL_AUTHENTICODE_SIGNER_INFO, * PAXL_AUTHENTICODE_SIGNER_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="5168e-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="5168e-105">Members</span></span>  
  
|<span data-ttu-id="5168e-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="5168e-106">Member</span></span>|<span data-ttu-id="5168e-107">説明</span><span class="sxs-lookup"><span data-stu-id="5168e-107">Description</span></span>|  
|------------|-----------------|  
|`cbSize`|<span data-ttu-id="5168e-108">この構造のサイズ。</span><span class="sxs-lookup"><span data-stu-id="5168e-108">The size of this structure.</span></span>|  
|`dwError`|<span data-ttu-id="5168e-109">エラー コード。</span><span class="sxs-lookup"><span data-stu-id="5168e-109">The error code.</span></span>|  
|`algHash`|<span data-ttu-id="5168e-110">ハッシュアルゴリズム。</span><span class="sxs-lookup"><span data-stu-id="5168e-110">The hash algorithm.</span></span>|  
|`pwszHash`|<span data-ttu-id="5168e-111">ハッシュ。</span><span class="sxs-lookup"><span data-stu-id="5168e-111">The hash.</span></span>|  
|`pwszDescription`|<span data-ttu-id="5168e-112">説明。</span><span class="sxs-lookup"><span data-stu-id="5168e-112">The description.</span></span>|  
|`pwszDescriptionUrl`|<span data-ttu-id="5168e-113">説明の URL。</span><span class="sxs-lookup"><span data-stu-id="5168e-113">The URL of the description.</span></span>|  
|`pChainContext`|<span data-ttu-id="5168e-114">署名者のチェーン コンテキスト。</span><span class="sxs-lookup"><span data-stu-id="5168e-114">The chain context of the signer.</span></span> <span data-ttu-id="5168e-115">参照してください、 [CERT_CONTEXT](/windows/desktop/api/wincrypt/ns-wincrypt-_cert_context)構造体。</span><span class="sxs-lookup"><span data-stu-id="5168e-115">See the [CERT_CONTEXT](/windows/desktop/api/wincrypt/ns-wincrypt-_cert_context) structure.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5168e-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="5168e-116">See Also</span></span>  
 [<span data-ttu-id="5168e-117">Authenticode</span><span class="sxs-lookup"><span data-stu-id="5168e-117">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
