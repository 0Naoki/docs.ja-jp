---
title: CertFreeAuthenticodeTimestamperInfo 関数
ms.date: 03/30/2017
api_name:
- CertFreeAuthenticodeTimestamperInfo
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: 3eb14c49-68c2-4516-ac89-e5bd7473831c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 27c16cb5d85ddffc1646bee893c5644682812025
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54560582"
---
# <a name="certfreeauthenticodetimestamperinfo-function"></a><span data-ttu-id="7abc0-102">CertFreeAuthenticodeTimestamperInfo 関数</span><span class="sxs-lookup"><span data-stu-id="7abc0-102">CertFreeAuthenticodeTimestamperInfo Function</span></span>
<span data-ttu-id="7abc0-103">割り当てられているリソース、 [AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md)構造体。</span><span class="sxs-lookup"><span data-stu-id="7abc0-103">Frees resources allocated for the [AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md) structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7abc0-104">構文</span><span class="sxs-lookup"><span data-stu-id="7abc0-104">Syntax</span></span>  
  
```  
HRESULT CertFreeAuthenticodeTimestamperInfo (  
    [in, out]  PAXL_AUTHENTICODE_TIMESTAMPER_INFO   pTimestamperInfo  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7abc0-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="7abc0-105">Parameters</span></span>  
 `pTimestamperInfo`  
 <span data-ttu-id="7abc0-106">[入力、出力] 解放されるタイム スタンパー情報。</span><span class="sxs-lookup"><span data-stu-id="7abc0-106">[in, out] The time stamper information to be released.</span></span> <span data-ttu-id="7abc0-107">参照してください、 [AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md)構造体。</span><span class="sxs-lookup"><span data-stu-id="7abc0-107">See the [AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md) structure.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7abc0-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="7abc0-108">Return Value</span></span>  
 <span data-ttu-id="7abc0-109">関数が成功した場合は `S_OK`。</span><span class="sxs-lookup"><span data-stu-id="7abc0-109">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="7abc0-110">それ以外の場合はエラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="7abc0-110">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7abc0-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="7abc0-111">See also</span></span>
- [<span data-ttu-id="7abc0-112">Authenticode</span><span class="sxs-lookup"><span data-stu-id="7abc0-112">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
