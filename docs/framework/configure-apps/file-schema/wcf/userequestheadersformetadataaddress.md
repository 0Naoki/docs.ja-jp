---
title: <useRequestHeadersForMetadataAddress>
ms.date: 03/30/2017
ms.assetid: 679f0eae-f353-44d1-b42d-a9e247509774
ms.openlocfilehash: 969461d0e5bdc9f8c49b7a019a6000af5af77eec
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59121187"
---
# <a name="userequestheadersformetadataaddress"></a><span data-ttu-id="bc38b-101">\<useRequestHeadersForMetadataAddress ></span><span class="sxs-lookup"><span data-stu-id="bc38b-101">\<useRequestHeadersForMetadataAddress></span></span>
<span data-ttu-id="bc38b-102">メタデータのアドレス情報を要求メッセージ ヘッダーから取得できるようにします。</span><span class="sxs-lookup"><span data-stu-id="bc38b-102">Enables the retrieval of metadata address information from the request message headers.</span></span>  
  
<span data-ttu-id="bc38b-103">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="bc38b-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="bc38b-104">\<<behaviors></span><span class="sxs-lookup"><span data-stu-id="bc38b-104">\<behaviors></span></span>  
<span data-ttu-id="bc38b-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="bc38b-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="bc38b-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="bc38b-106">\<behavior></span></span>  
<span data-ttu-id="bc38b-107">\<useRequestHeadersForMetadataAddress ></span><span class="sxs-lookup"><span data-stu-id="bc38b-107">\<useRequestHeadersForMetadataAddress></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bc38b-108">構文</span><span class="sxs-lookup"><span data-stu-id="bc38b-108">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add scheme="http"
         port="integer" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bc38b-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="bc38b-109">Attributes and Elements</span></span>  
 <span data-ttu-id="bc38b-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="bc38b-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bc38b-111">属性</span><span class="sxs-lookup"><span data-stu-id="bc38b-111">Attributes</span></span>  
 <span data-ttu-id="bc38b-112">なし。</span><span class="sxs-lookup"><span data-stu-id="bc38b-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="bc38b-113">子要素</span><span class="sxs-lookup"><span data-stu-id="bc38b-113">Child Elements</span></span>  
  
|<span data-ttu-id="bc38b-114">要素</span><span class="sxs-lookup"><span data-stu-id="bc38b-114">Element</span></span>|<span data-ttu-id="bc38b-115">説明</span><span class="sxs-lookup"><span data-stu-id="bc38b-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bc38b-116">\<defaultPorts></span><span class="sxs-lookup"><span data-stu-id="bc38b-116">\<defaultPorts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/defaultports.md)|<span data-ttu-id="bc38b-117">クライアント アプリケーションがリッスンする既定の通信エンドポイントの一覧を表示する既定のポートのコレクション。</span><span class="sxs-lookup"><span data-stu-id="bc38b-117">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="bc38b-118">親要素</span><span class="sxs-lookup"><span data-stu-id="bc38b-118">Parent Elements</span></span>  
  
|<span data-ttu-id="bc38b-119">要素</span><span class="sxs-lookup"><span data-stu-id="bc38b-119">Element</span></span>|<span data-ttu-id="bc38b-120">説明</span><span class="sxs-lookup"><span data-stu-id="bc38b-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bc38b-121">\<behavior></span><span class="sxs-lookup"><span data-stu-id="bc38b-121">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="bc38b-122">動作の要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="bc38b-122">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bc38b-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="bc38b-123">See also</span></span>

- <xref:System.ServiceModel.Configuration.UseRequestHeadersForMetadataAddressElement>
