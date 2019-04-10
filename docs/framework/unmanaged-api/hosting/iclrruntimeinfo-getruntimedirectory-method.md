---
title: ICLRRuntimeInfo::GetRuntimeDirectory メソッド
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.GetRuntimeDirectory
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::GetRuntimeDirectory
helpviewer_keywords:
- GetRuntimeDirectory method [.NET Framework hosting]
- ICLRRuntimeInfo::GetRuntimeDirectory method [.NET Framework hosting]
ms.assetid: 4401546e-4d48-453f-a1fb-b2ebda54df5c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5c09f57ad805b4ba17b4bdafd3ced533199277a0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59196685"
---
# <a name="iclrruntimeinfogetruntimedirectory-method"></a><span data-ttu-id="14792-102">ICLRRuntimeInfo::GetRuntimeDirectory メソッド</span><span class="sxs-lookup"><span data-stu-id="14792-102">ICLRRuntimeInfo::GetRuntimeDirectory Method</span></span>
<span data-ttu-id="14792-103">このインターフェイスに関連付けられている共通言語ランタイム (CLR) のインストール ディレクトリを取得します。</span><span class="sxs-lookup"><span data-stu-id="14792-103">Gets the installation directory of the common language runtime (CLR) associated with this interface.</span></span>  
  
 <span data-ttu-id="14792-104">このメソッドは、 [GetCORSystemDirectory](../../../../docs/framework/unmanaged-api/hosting/getcorsystemdirectory-function.md) .NET Framework バージョン 2.0、3.0、および 3.5 で提供される関数。</span><span class="sxs-lookup"><span data-stu-id="14792-104">This method supersedes the [GetCORSystemDirectory](../../../../docs/framework/unmanaged-api/hosting/getcorsystemdirectory-function.md) function provided in the .NET Framework versions 2.0, 3.0, and 3.5.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="14792-105">構文</span><span class="sxs-lookup"><span data-stu-id="14792-105">Syntax</span></span>  
  
```  
HRESULT GetRuntimeDirectory(  
[out, size_is(*pcchBuffer)] LPWSTR pwzBuffer,  
[in, out]  DWORD *pcchBuffer);  
```  
  
## <a name="parameters"></a><span data-ttu-id="14792-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="14792-106">Parameters</span></span>  
 `pwzBuffer`  
 <span data-ttu-id="14792-107">[out]CLR のインストール ディレクトリを返します。</span><span class="sxs-lookup"><span data-stu-id="14792-107">[out] Returns the CLR installation directory.</span></span> <span data-ttu-id="14792-108">インストール パスは、完全修飾;たとえば、"c:\windows\microsoft.net\framework\v1.0.3705\\"。</span><span class="sxs-lookup"><span data-stu-id="14792-108">The installation path is fully qualified; for example, "c:\windows\microsoft.net\framework\v1.0.3705\\".</span></span>  
  
 `pchBuffer`  
 <span data-ttu-id="14792-109">[入力、出力]サイズを示す`pwzBuffer`バッファー オーバーランを回避します。</span><span class="sxs-lookup"><span data-stu-id="14792-109">[in, out] Specifies the size of `pwzBuffer` to avoid buffer overruns.</span></span> <span data-ttu-id="14792-110">場合`pwzBuffer`が null、`pchBuffer`の必要なサイズを返します`pwzBuffer`します。</span><span class="sxs-lookup"><span data-stu-id="14792-110">If `pwzBuffer` is null, `pchBuffer` returns the required size of `pwzBuffer`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="14792-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="14792-111">Return Value</span></span>  
 <span data-ttu-id="14792-112">このメソッドは、次の特定の HRESULT と、メソッドの失敗を示す HRESULT エラーも返します。</span><span class="sxs-lookup"><span data-stu-id="14792-112">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="14792-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="14792-113">HRESULT</span></span>|<span data-ttu-id="14792-114">説明</span><span class="sxs-lookup"><span data-stu-id="14792-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="14792-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="14792-115">S_OK</span></span>|<span data-ttu-id="14792-116">メソッドは正常に完了しました。</span><span class="sxs-lookup"><span data-stu-id="14792-116">The method completed successfully.</span></span>|  
|<span data-ttu-id="14792-117">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="14792-117">E_POINTER</span></span>|`pwzBuffer` <span data-ttu-id="14792-118">または`pchBuffer`が null です。</span><span class="sxs-lookup"><span data-stu-id="14792-118">or `pchBuffer` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="14792-119">Remarks</span><span class="sxs-lookup"><span data-stu-id="14792-119">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="14792-120">必要条件</span><span class="sxs-lookup"><span data-stu-id="14792-120">Requirements</span></span>  
 <span data-ttu-id="14792-121">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="14792-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="14792-122">**ヘッダー:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="14792-122">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="14792-123">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="14792-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="14792-124">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="14792-124">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="14792-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="14792-125">See also</span></span>

- [<span data-ttu-id="14792-126">ICLRRuntimeInfo インターフェイス</span><span class="sxs-lookup"><span data-stu-id="14792-126">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [<span data-ttu-id="14792-127">ホスト</span><span class="sxs-lookup"><span data-stu-id="14792-127">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
