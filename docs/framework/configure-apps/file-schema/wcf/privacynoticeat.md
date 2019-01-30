---
title: <privacyNoticeAt>
ms.date: 03/30/2017
ms.assetid: 4cc96942-4eb9-4241-b2fd-45aa239915e8
ms.openlocfilehash: b1de2a304a5dc4295497ea1f3b395240cb5ca9bc
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/30/2019
ms.locfileid: "55254914"
---
# <a name="privacynoticeat"></a><span data-ttu-id="18c6e-101">\<privacyNoticeAt></span><span class="sxs-lookup"><span data-stu-id="18c6e-101">\<privacyNoticeAt></span></span>
<span data-ttu-id="18c6e-102">`wsFederationHttp` バインディングで使用されるプライバシーに関する声明を指定する構成要素を表します。</span><span class="sxs-lookup"><span data-stu-id="18c6e-102">Represents a configuration element that specifies a privacy notice used in `wsFederationHttp` binding.</span></span>  
  
 <span data-ttu-id="18c6e-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="18c6e-103">\<system.serviceModel></span></span>  
<span data-ttu-id="18c6e-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="18c6e-104">\<bindings></span></span>  
<span data-ttu-id="18c6e-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="18c6e-105">\<customBinding></span></span>  
<span data-ttu-id="18c6e-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="18c6e-106">\<binding></span></span>  
<span data-ttu-id="18c6e-107">\<privacyNotice></span><span class="sxs-lookup"><span data-stu-id="18c6e-107">\<privacyNotice></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18c6e-108">構文</span><span class="sxs-lookup"><span data-stu-id="18c6e-108">Syntax</span></span>  
  
```xml  
<privacyNotice url="String"
               version="Integer" />
```  
  
## <a name="type"></a><span data-ttu-id="18c6e-109">型</span><span class="sxs-lookup"><span data-stu-id="18c6e-109">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="18c6e-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="18c6e-110">Attributes and Elements</span></span>  
 <span data-ttu-id="18c6e-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="18c6e-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="18c6e-112">属性</span><span class="sxs-lookup"><span data-stu-id="18c6e-112">Attributes</span></span>  
  
|<span data-ttu-id="18c6e-113">属性</span><span class="sxs-lookup"><span data-stu-id="18c6e-113">Attribute</span></span>|<span data-ttu-id="18c6e-114">説明</span><span class="sxs-lookup"><span data-stu-id="18c6e-114">Description</span></span>|  
|---------------|-----------------|  
|`url`|<span data-ttu-id="18c6e-115">プライバシーに関する声明の場所を示す URI を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="18c6e-115">A string that specifies the URI at which the privacy notice is located.</span></span>|  
|`version`|<span data-ttu-id="18c6e-116">このプライバシーに関する声明のバージョンを指定する整数。</span><span class="sxs-lookup"><span data-stu-id="18c6e-116">An integer that specifies the version of this privacy notice.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="18c6e-117">子要素</span><span class="sxs-lookup"><span data-stu-id="18c6e-117">Child Elements</span></span>  
 <span data-ttu-id="18c6e-118">なし。</span><span class="sxs-lookup"><span data-stu-id="18c6e-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="18c6e-119">親要素</span><span class="sxs-lookup"><span data-stu-id="18c6e-119">Parent Elements</span></span>  
  
|<span data-ttu-id="18c6e-120">要素</span><span class="sxs-lookup"><span data-stu-id="18c6e-120">Element</span></span>|<span data-ttu-id="18c6e-121">説明</span><span class="sxs-lookup"><span data-stu-id="18c6e-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="18c6e-122">\<binding></span><span class="sxs-lookup"><span data-stu-id="18c6e-122">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="18c6e-123">カスタム バインドのすべてのバインド機能を定義します。</span><span class="sxs-lookup"><span data-stu-id="18c6e-123">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="18c6e-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="18c6e-124">See also</span></span>
- <xref:System.ServiceModel.Configuration.PrivacyNoticeElement>
- <xref:System.ServiceModel.Channels.PrivacyNoticeBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="18c6e-125">バインディング</span><span class="sxs-lookup"><span data-stu-id="18c6e-125">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="18c6e-126">バインディングの拡張</span><span class="sxs-lookup"><span data-stu-id="18c6e-126">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="18c6e-127">カスタム バインディング</span><span class="sxs-lookup"><span data-stu-id="18c6e-127">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="18c6e-128">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="18c6e-128">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
