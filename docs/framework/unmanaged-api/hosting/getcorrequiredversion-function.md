---
title: GetCORRequiredVersion 関数
ms.date: 03/30/2017
api_name:
- GetCORRequiredVersion
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetCORRequiredVersion
helpviewer_keywords:
- GetCORRequiredVersion function [.NET Framework hosting]
ms.assetid: 1588fe7b-c378-4f4b-9c4b-48647f1119cc
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b5786444c36fcfc9547be1db0006757b0a9376c6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59175189"
---
# <a name="getcorrequiredversion-function"></a><span data-ttu-id="104cb-102">GetCORRequiredVersion 関数</span><span class="sxs-lookup"><span data-stu-id="104cb-102">GetCORRequiredVersion Function</span></span>
<span data-ttu-id="104cb-103">必要な共通言語ランタイム (CLR) バージョン番号を取得します。</span><span class="sxs-lookup"><span data-stu-id="104cb-103">Gets the required common language runtime (CLR) version number.</span></span>  
  
 <span data-ttu-id="104cb-104">この関数は、[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] では非推奨とされました。</span><span class="sxs-lookup"><span data-stu-id="104cb-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="104cb-105">構文</span><span class="sxs-lookup"><span data-stu-id="104cb-105">Syntax</span></span>  
  
```  
HRESULT GetCORRequiredVersion (  
    [out] LPWSTR   pbuffer,  
    [in]  DWORD    cchBuffer,  
    [out] DWORD   *dwLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="104cb-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="104cb-106">Parameters</span></span>  
 `pbuffer`  
 <span data-ttu-id="104cb-107">[out]バージョン番号を指定する文字列を格納するバッファー。</span><span class="sxs-lookup"><span data-stu-id="104cb-107">[out] A buffer containing a string that specifies the version number.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="104cb-108">[in]バッファーのバイト単位のサイズ。</span><span class="sxs-lookup"><span data-stu-id="104cb-108">[in] The size, in bytes, of the buffer.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="104cb-109">[out]バッファー内のバイト数が返されます。</span><span class="sxs-lookup"><span data-stu-id="104cb-109">[out] The number of bytes returned in the buffer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="104cb-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="104cb-110">Requirements</span></span>  
 <span data-ttu-id="104cb-111">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="104cb-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="104cb-112">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="104cb-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="104cb-113">**ライブラリ:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="104cb-113">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="104cb-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="104cb-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="104cb-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="104cb-115">See also</span></span>

- [<span data-ttu-id="104cb-116">非推奨の CLR ホスト関数</span><span class="sxs-lookup"><span data-stu-id="104cb-116">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
