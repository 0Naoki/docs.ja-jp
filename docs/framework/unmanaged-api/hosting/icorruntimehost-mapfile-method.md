---
title: ICorRuntimeHost::MapFile メソッド
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.MapFile
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::MapFile
helpviewer_keywords:
- ICorRuntimeHost::MapFile method [.NET Framework hosting]
- MapFile method [.NET Framework hosting]
ms.assetid: 45ae0502-0a31-4342-b7e3-f36e1cf738f3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 814073b766d5d562b414a566ae3f92abd664ce35
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54707844"
---
# <a name="icorruntimehostmapfile-method"></a><span data-ttu-id="fb1e0-102">ICorRuntimeHost::MapFile メソッド</span><span class="sxs-lookup"><span data-stu-id="fb1e0-102">ICorRuntimeHost::MapFile Method</span></span>
<span data-ttu-id="fb1e0-103">指定したファイルをメモリにマップします。</span><span class="sxs-lookup"><span data-stu-id="fb1e0-103">Maps the specified file into memory.</span></span> <span data-ttu-id="fb1e0-104">このメソッドは、互換性のために残されています。</span><span class="sxs-lookup"><span data-stu-id="fb1e0-104">This method is obsolete.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb1e0-105">構文</span><span class="sxs-lookup"><span data-stu-id="fb1e0-105">Syntax</span></span>  
  
```  
HRESULT MapFile(  
    [in]  HANDLE    hFile,  
    [out] HMODULE*  hMapAddress  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fb1e0-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="fb1e0-106">Parameters</span></span>  
 `hFile`  
 <span data-ttu-id="fb1e0-107">[in]マップするファイルのハンドル。</span><span class="sxs-lookup"><span data-stu-id="fb1e0-107">[in] The handle of the file to be mapped.</span></span>  
  
 `hMapAddress`  
 <span data-ttu-id="fb1e0-108">[out]ファイルのマッピングを開始する位置の開始メモリ アドレス。</span><span class="sxs-lookup"><span data-stu-id="fb1e0-108">[out] The starting memory address at which to begin mapping the file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fb1e0-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="fb1e0-109">Requirements</span></span>  
 <span data-ttu-id="fb1e0-110">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="fb1e0-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fb1e0-111">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="fb1e0-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fb1e0-112">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="fb1e0-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fb1e0-113">**.NET framework のバージョン:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="fb1e0-113">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb1e0-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="fb1e0-114">See also</span></span>
- [<span data-ttu-id="fb1e0-115">ICorRuntimeHost インターフェイス</span><span class="sxs-lookup"><span data-stu-id="fb1e0-115">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
