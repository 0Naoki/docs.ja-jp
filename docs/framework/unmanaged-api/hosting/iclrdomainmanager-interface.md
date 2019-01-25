---
title: ICLRDomainManager インターフェイス
ms.date: 03/30/2017
api_name:
- ICLRDomainManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDomainManager
helpviewer_keywords:
- ICLRDomainManager interface [.NET Framework hosting]
ms.assetid: f08b2390-d872-4521-a815-e9c237c4c45d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 797b6031449672e8b610b2a53e77497e5835ea6a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54657429"
---
# <a name="iclrdomainmanager-interface"></a><span data-ttu-id="84551-102">ICLRDomainManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="84551-102">ICLRDomainManager Interface</span></span>
<span data-ttu-id="84551-103">初期化プロパティを指定して、既定のアプリケーション ドメインを初期化するために使用されるアプリケーション ドメイン マネージャーを指定するホストを有効にします。</span><span class="sxs-lookup"><span data-stu-id="84551-103">Enables the host to specify the application domain manager that will be used to initialize the default application domain, and to specify initialization properties.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="84551-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="84551-104">Methods</span></span>  
  
|<span data-ttu-id="84551-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="84551-105">Method</span></span>|<span data-ttu-id="84551-106">説明</span><span class="sxs-lookup"><span data-stu-id="84551-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="84551-107">SetAppDomainManagerType メソッド</span><span class="sxs-lookup"><span data-stu-id="84551-107">SetAppDomainManagerType Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-setappdomainmanagertype-method.md)|<span data-ttu-id="84551-108">派生した、型を指定します、<xref:System.AppDomainManager?displayProperty=nameWithType>の既定のアプリケーション ドメインを初期化するために使用されるアプリケーション ドメイン マネージャーのクラス。</span><span class="sxs-lookup"><span data-stu-id="84551-108">Specifies the type, derived from the <xref:System.AppDomainManager?displayProperty=nameWithType> class, of the application domain manager that will be used to initialize the default application domain.</span></span>|  
|[<span data-ttu-id="84551-109">SetPropertiesForDefaultAppDomain メソッド</span><span class="sxs-lookup"><span data-stu-id="84551-109">SetPropertiesForDefaultAppDomain Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-setpropertiesfordefaultappdomain-method.md)|<span data-ttu-id="84551-110">既定のアプリケーション ドメインを初期化するために使用されるプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="84551-110">Sets properties that will be used to initialize the default application domain.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="84551-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="84551-111">Remarks</span></span>  
 <span data-ttu-id="84551-112">このインターフェイスのインスタンスを取得する、 [iclrcontrol::getclrmanager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) IID マネージャーの種類を持つメソッド`IID_ICLRDomainManager`します。</span><span class="sxs-lookup"><span data-stu-id="84551-112">To get an instance of this interface, call the [ICLRControl::GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) method with the manager type IID `IID_ICLRDomainManager`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="84551-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="84551-113">Requirements</span></span>  
 <span data-ttu-id="84551-114">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="84551-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="84551-115">**ヘッダー:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="84551-115">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="84551-116">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="84551-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="84551-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="84551-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84551-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="84551-118">See also</span></span>
- [<span data-ttu-id="84551-119">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="84551-119">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="84551-120">ホスティング</span><span class="sxs-lookup"><span data-stu-id="84551-120">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
