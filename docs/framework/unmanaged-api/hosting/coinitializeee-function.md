---
title: CoInitializeEE 関数
ms.date: 03/30/2017
api_name:
- CoInitializeEE
api_location:
- mscoree.dll
- mscorsvr.dll
api_type:
- DLLExport
f1_keywords:
- CoInitializeEE
helpviewer_keywords:
- CoInitializeEE function [.NET Framework hosting]
ms.assetid: 7e42a928-5068-4ba6-b8c3-806551a01fa8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 18f1a4ede1a362860df1271835600e7b867eac00
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59127765"
---
# <a name="coinitializeee-function"></a><span data-ttu-id="94fcb-102">CoInitializeEE 関数</span><span class="sxs-lookup"><span data-stu-id="94fcb-102">CoInitializeEE Function</span></span>
<span data-ttu-id="94fcb-103">共通言語ランタイムの実行エンジンがプロセスに読み込まれているようにします。</span><span class="sxs-lookup"><span data-stu-id="94fcb-103">Ensures that the common language runtime execution engine is loaded into a process.</span></span> <span data-ttu-id="94fcb-104">この関数は非推奨、[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="94fcb-104">This function is deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span> <span data-ttu-id="94fcb-105">使用して、 [iclrruntimehost::start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md)メソッド代わりにします。</span><span class="sxs-lookup"><span data-stu-id="94fcb-105">Use the [ICLRRuntimeHost::Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94fcb-106">構文</span><span class="sxs-lookup"><span data-stu-id="94fcb-106">Syntax</span></span>  
  
```  
HRESULT CoInitializeEE (  
   [in] DWORD fFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="94fcb-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="94fcb-107">Parameters</span></span>  
 `fFlags`  
 <span data-ttu-id="94fcb-108">[in]1 つ、 [COINITIEE](../../../../docs/framework/unmanaged-api/metadata/coinitiee-enumeration.md)列挙定数。</span><span class="sxs-lookup"><span data-stu-id="94fcb-108">[in] One of the [COINITIEE](../../../../docs/framework/unmanaged-api/metadata/coinitiee-enumeration.md) enumeration constants.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="94fcb-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="94fcb-109">Return Value</span></span>  
 <span data-ttu-id="94fcb-110">このメソッドは、Winerror.h と、次の表の値で定義されている標準の COM エラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="94fcb-110">This method returns standard COM error codes as defined in Winerror.h, and the values in the following table.</span></span>  
  
|<span data-ttu-id="94fcb-111">リターン コード</span><span class="sxs-lookup"><span data-stu-id="94fcb-111">Return code</span></span>|<span data-ttu-id="94fcb-112">説明</span><span class="sxs-lookup"><span data-stu-id="94fcb-112">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="94fcb-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="94fcb-113">S_OK</span></span>|<span data-ttu-id="94fcb-114">実行エンジンは正常に読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="94fcb-114">The execution engine was loaded successfully.</span></span>|  
|<span data-ttu-id="94fcb-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="94fcb-115">S_FALSE</span></span>|<span data-ttu-id="94fcb-116">実行エンジンは既に読み込まれています。</span><span class="sxs-lookup"><span data-stu-id="94fcb-116">The execution engine is already loaded.</span></span>|  
|<span data-ttu-id="94fcb-117">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="94fcb-117">E_FAIL</span></span>|<span data-ttu-id="94fcb-118">実行エンジンを読み込むことができませんでした。</span><span class="sxs-lookup"><span data-stu-id="94fcb-118">The execution engine could not be loaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="94fcb-119">Remarks</span><span class="sxs-lookup"><span data-stu-id="94fcb-119">Remarks</span></span>  
 <span data-ttu-id="94fcb-120">このメソッドは、既に読み込まれていない場合に、実行エンジンを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="94fcb-120">This method loads the execution engine if it has not been previously loaded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="94fcb-121">必要条件</span><span class="sxs-lookup"><span data-stu-id="94fcb-121">Requirements</span></span>  
 <span data-ttu-id="94fcb-122">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="94fcb-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="94fcb-123">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="94fcb-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="94fcb-124">**ライブラリ:** MsCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="94fcb-124">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="94fcb-125">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="94fcb-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94fcb-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="94fcb-126">See also</span></span>

- [<span data-ttu-id="94fcb-127">メタデータ グローバル静的関数</span><span class="sxs-lookup"><span data-stu-id="94fcb-127">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
