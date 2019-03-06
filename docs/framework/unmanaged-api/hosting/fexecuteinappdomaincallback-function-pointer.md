---
title: FExecuteInAppDomainCallback 関数ポインター
ms.date: 03/30/2017
api_name:
- FExecuteInAppDomainCallback
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- FExecuteInAppDomainCallback
helpviewer_keywords:
- FExecuteInAppDomainCallback function pointer [.NET Framework hosting]
ms.assetid: 2709f18f-3eee-497f-bc33-3ab7a485599b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 16608980505ffc03ef8ecc19cacddabaefaba6ca
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57471746"
---
# <a name="fexecuteinappdomaincallback-function-pointer"></a><span data-ttu-id="4c23d-102">FExecuteInAppDomainCallback 関数ポインター</span><span class="sxs-lookup"><span data-stu-id="4c23d-102">FExecuteInAppDomainCallback Function Pointer</span></span>
<span data-ttu-id="4c23d-103">マネージ コードを実行する共通言語ランタイム (CLR) によって呼び出される関数を指します。</span><span class="sxs-lookup"><span data-stu-id="4c23d-103">Points to a function that is called by the common language runtime (CLR) to execute managed code.</span></span>  
  
 <span data-ttu-id="4c23d-104">この関数のポインターが非推奨とされた、[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="4c23d-104">This function pointer has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4c23d-105">構文</span><span class="sxs-lookup"><span data-stu-id="4c23d-105">Syntax</span></span>  
  
```  
typedef HRESULT (__stdcall *FExecuteInAppDomainCallback) (  
    [in] void  *cookie  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4c23d-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="4c23d-106">Parameters</span></span>  
 `cookie`  
 <span data-ttu-id="4c23d-107">[in]実行されるマネージ コードを含む非透過の呼び出し元が割り当てたメモリへのポインター。</span><span class="sxs-lookup"><span data-stu-id="4c23d-107">[in] A pointer to opaque caller-allocated memory that contains the managed code to be executed.</span></span>  
  
 <span data-ttu-id="4c23d-108">割り当てとメモリの有効期間は、呼び出し元の (つまり、CLR) によって制御されます。</span><span class="sxs-lookup"><span data-stu-id="4c23d-108">The allocation and lifetime of this memory are controlled by the caller (that is, the CLR).</span></span> <span data-ttu-id="4c23d-109">これは、CLR のマネージ ヒープ メモリではありません。</span><span class="sxs-lookup"><span data-stu-id="4c23d-109">This is not CLR managed-heap memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4c23d-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="4c23d-110">Requirements</span></span>  
 <span data-ttu-id="4c23d-111">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4c23d-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4c23d-112">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="4c23d-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4c23d-113">**ライブラリ:** MSCorWks.dll</span><span class="sxs-lookup"><span data-stu-id="4c23d-113">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="4c23d-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4c23d-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c23d-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="4c23d-115">See also</span></span>
- [<span data-ttu-id="4c23d-116">非推奨の CLR ホスト関数</span><span class="sxs-lookup"><span data-stu-id="4c23d-116">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
