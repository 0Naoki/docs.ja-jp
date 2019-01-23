---
title: ICLRValidator インターフェイス
ms.date: 03/30/2017
api_name:
- ICLRValidator
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRValidator
helpviewer_keywords:
- ICLRValidator interface [.NET Framework hosting]
ms.assetid: 2edd0a10-77fb-4173-91eb-f2970cc364d0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6f34a9aac31fe50974a6f88416d0a00cd72aca8e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54511931"
---
# <a name="iclrvalidator-interface"></a><span data-ttu-id="087ff-102">ICLRValidator インターフェイス</span><span class="sxs-lookup"><span data-stu-id="087ff-102">ICLRValidator Interface</span></span>
<span data-ttu-id="087ff-103">ポータブル実行可能 (PE) イメージを検証し、検証エラーを報告するためのメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="087ff-103">Provides methods for validating portable executable (PE) images and reporting validation errors.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="087ff-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="087ff-104">Methods</span></span>  
  
|<span data-ttu-id="087ff-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="087ff-105">Method</span></span>|<span data-ttu-id="087ff-106">説明</span><span class="sxs-lookup"><span data-stu-id="087ff-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="087ff-107">FormatEventInfo メソッド</span><span class="sxs-lookup"><span data-stu-id="087ff-107">FormatEventInfo Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-formateventinfo-method.md)|<span data-ttu-id="087ff-108">指定した検証エラーに関する詳細なメッセージを取得します。</span><span class="sxs-lookup"><span data-stu-id="087ff-108">Gets a detailed message about the specified validation error.</span></span>|  
|[<span data-ttu-id="087ff-109">Validate メソッド</span><span class="sxs-lookup"><span data-stu-id="087ff-109">Validate Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-validate-method.md)|<span data-ttu-id="087ff-110">ポータブル実行可能ファイルまたは Microsoft intermediate language (MSIL) で指定されたファイルを検証します。</span><span class="sxs-lookup"><span data-stu-id="087ff-110">Validates the portable executable or Microsoft intermediate language (MSIL) in the specified file.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="087ff-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="087ff-111">Requirements</span></span>  
 <span data-ttu-id="087ff-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="087ff-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="087ff-113">**ヘッダー:** IValidator.idl, IValidator.h</span><span class="sxs-lookup"><span data-stu-id="087ff-113">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="087ff-114">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="087ff-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="087ff-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="087ff-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="087ff-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="087ff-116">See also</span></span>
- [<span data-ttu-id="087ff-117">ICLRErrorReportingManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="087ff-117">ICLRErrorReportingManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)
- [<span data-ttu-id="087ff-118">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="087ff-118">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="087ff-119">CLRRuntimeHost コクラス</span><span class="sxs-lookup"><span data-stu-id="087ff-119">CLRRuntimeHost Coclass</span></span>](../../../../docs/framework/unmanaged-api/hosting/clrruntimehost-coclass.md)
