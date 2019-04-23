---
title: IValidator インターフェイス
ms.date: 03/30/2017
api_name:
- IValidator
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IValidator
helpviewer_keywords:
- IValidator interface [.NET Framework hosting]
ms.assetid: b297e3b0-20f9-478f-b707-5e2eecb2b5b2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2f516bf1f19e4d4a77e2d6af834a1c3d4e34c327
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59121915"
---
# <a name="ivalidator-interface"></a><span data-ttu-id="cea62-102">IValidator インターフェイス</span><span class="sxs-lookup"><span data-stu-id="cea62-102">IValidator Interface</span></span>
<span data-ttu-id="cea62-103">ポータブル実行可能 (PE) イメージを検証し、検証エラーを報告するためのメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="cea62-103">Provides methods for validating portable executable (PE) images and reporting validation errors.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="cea62-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="cea62-104">Methods</span></span>  
  
|<span data-ttu-id="cea62-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="cea62-105">Method</span></span>|<span data-ttu-id="cea62-106">説明</span><span class="sxs-lookup"><span data-stu-id="cea62-106">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="cea62-107">検証</span><span class="sxs-lookup"><span data-stu-id="cea62-107">Validate</span></span>|<span data-ttu-id="cea62-108">指定された PE または Microsoft intermediate language (MSIL) ファイルを検証します。</span><span class="sxs-lookup"><span data-stu-id="cea62-108">Validates the specified PE or Microsoft intermediate language (MSIL) file.</span></span>|  
|<span data-ttu-id="cea62-109">FormatEventInfo</span><span class="sxs-lookup"><span data-stu-id="cea62-109">FormatEventInfo</span></span>|<span data-ttu-id="cea62-110">指定した検証エラーに対応するエラー メッセージを取得します。</span><span class="sxs-lookup"><span data-stu-id="cea62-110">Gets the error message corresponding to the specified validation error.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="cea62-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="cea62-111">Requirements</span></span>  
 <span data-ttu-id="cea62-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cea62-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cea62-113">**ヘッダー:** IValidator.idl, IValidator.h</span><span class="sxs-lookup"><span data-stu-id="cea62-113">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="cea62-114">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="cea62-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cea62-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cea62-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cea62-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="cea62-116">See also</span></span>

- [<span data-ttu-id="cea62-117">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="cea62-117">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="cea62-118">CorRuntimeHost コクラス</span><span class="sxs-lookup"><span data-stu-id="cea62-118">CorRuntimeHost Coclass</span></span>](../../../../docs/framework/unmanaged-api/hosting/corruntimehost-coclass.md)
