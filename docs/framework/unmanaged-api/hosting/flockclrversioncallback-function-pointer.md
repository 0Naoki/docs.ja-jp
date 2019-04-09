---
title: FLockClrVersionCallback 関数ポインター
ms.date: 03/30/2017
api_name:
- FLockClrVersionCallback
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- FLockClrVersionCallback
helpviewer_keywords:
- FLockClrVersionCallback function pointer [.NET Framework hosting]
ms.assetid: 98a4762d-9ad2-45bd-9d03-39064a028b44
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8062ab151efc6175aa68cb0563cd2ad042ee9cd8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59189054"
---
# <a name="flockclrversioncallback-function-pointer"></a><span data-ttu-id="981f5-102">FLockClrVersionCallback 関数ポインター</span><span class="sxs-lookup"><span data-stu-id="981f5-102">FLockClrVersionCallback Function Pointer</span></span>
<span data-ttu-id="981f5-103">その初期化を示すために、共通言語ランタイム (CLR) 呼び出しが開始または完了する関数を指します。</span><span class="sxs-lookup"><span data-stu-id="981f5-103">Points to a function that the common language runtime (CLR) calls to indicate that initialization has either started or completed.</span></span>  
  
 <span data-ttu-id="981f5-104">この関数のポインターが非推奨とされた、[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="981f5-104">This function pointer has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="981f5-105">構文</span><span class="sxs-lookup"><span data-stu-id="981f5-105">Syntax</span></span>  
  
```  
typedef HRESULT (__stdcall *FLockClrVersionCallback) ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="981f5-106">Remarks</span><span class="sxs-lookup"><span data-stu-id="981f5-106">Remarks</span></span>  
 <span data-ttu-id="981f5-107">この関数は、ホストによって実装されます。</span><span class="sxs-lookup"><span data-stu-id="981f5-107">This function is implemented by the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="981f5-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="981f5-108">Requirements</span></span>  
 <span data-ttu-id="981f5-109">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="981f5-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="981f5-110">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="981f5-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="981f5-111">**ライブラリ:** MSCorWks.dll</span><span class="sxs-lookup"><span data-stu-id="981f5-111">**Library:** MSCorWks.dll</span></span>  
  
 **<span data-ttu-id="981f5-112">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="981f5-112">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="981f5-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="981f5-113">See also</span></span>

- [<span data-ttu-id="981f5-114">LockClrVersion 関数</span><span class="sxs-lookup"><span data-stu-id="981f5-114">LockClrVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/lockclrversion-function.md)
- [<span data-ttu-id="981f5-115">非推奨の CLR ホスト関数</span><span class="sxs-lookup"><span data-stu-id="981f5-115">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
