---
title: CorMarkThreadInThreadPool 関数
ms.date: 03/30/2017
api_name:
- CorMarkThreadInThreadPool
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- CorMarkThreadInThreadPool
helpviewer_keywords:
- CorMarkThreadInThreadPool function [.NET Framework hosting]
ms.assetid: 3f958d41-e82e-4ec3-ae6f-16c7b3b31e3e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a39b0f2546d84cf24a58d5367c87d0a862aead93
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59085078"
---
# <a name="cormarkthreadinthreadpool-function"></a><span data-ttu-id="9fa54-102">CorMarkThreadInThreadPool 関数</span><span class="sxs-lookup"><span data-stu-id="9fa54-102">CorMarkThreadInThreadPool Function</span></span>
<span data-ttu-id="9fa54-103">現在実行されているスレッド プールのスレッドに、マネージド コードの実行のマークを付けます。</span><span class="sxs-lookup"><span data-stu-id="9fa54-103">Marks the currently executing thread-pool thread for the execution of managed code.</span></span> <span data-ttu-id="9fa54-104">.NET Framework Version 2.0 以降では、この関数に効力はありません。</span><span class="sxs-lookup"><span data-stu-id="9fa54-104">Starting with the .NET Framework version 2.0, this function has no effect.</span></span> <span data-ttu-id="9fa54-105">必ずしも必要はありませんが、この関数はコードから削除できます。</span><span class="sxs-lookup"><span data-stu-id="9fa54-105">It is not required, and can be removed from your code.</span></span> <span data-ttu-id="9fa54-106">この関数は非推奨、[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="9fa54-106">This function is deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9fa54-107">構文</span><span class="sxs-lookup"><span data-stu-id="9fa54-107">Syntax</span></span>  
  
```  
void CorMarkThreadInThreadPool ();  
```  
  
## <a name="requirements"></a><span data-ttu-id="9fa54-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="9fa54-108">Requirements</span></span>  
 <span data-ttu-id="9fa54-109">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9fa54-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9fa54-110">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="9fa54-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9fa54-111">**ライブラリ:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9fa54-111">**Library:** MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="9fa54-112">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="9fa54-112">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="9fa54-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="9fa54-113">See also</span></span>

- [<span data-ttu-id="9fa54-114">非推奨の CLR ホスト関数</span><span class="sxs-lookup"><span data-stu-id="9fa54-114">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
