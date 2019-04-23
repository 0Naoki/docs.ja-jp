---
title: <windowsStreamSecurity>
ms.date: 03/30/2017
ms.assetid: 926bea29-90c7-4a26-9cf0-fb4aa44f6f70
ms.openlocfilehash: 32e8ed6b70a23462fac3c53d1bc353167ff67560
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59113634"
---
# <a name="windowsstreamsecurity"></a><span data-ttu-id="78806-101">\<windowsStreamSecurity></span><span class="sxs-lookup"><span data-stu-id="78806-101">\<windowsStreamSecurity></span></span>
<span data-ttu-id="78806-102">カスタム バインディングの Windows ストリーム セキュリティ設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="78806-102">Specify Windows stream security settings of the custom binding.</span></span>  
  
 <span data-ttu-id="78806-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="78806-103">\<system.serviceModel></span></span>  
<span data-ttu-id="78806-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="78806-104">\<bindings></span></span>  
<span data-ttu-id="78806-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="78806-105">\<customBinding></span></span>  
<span data-ttu-id="78806-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="78806-106">\<binding></span></span>  
<span data-ttu-id="78806-107">\<windowsStreamSecurity></span><span class="sxs-lookup"><span data-stu-id="78806-107">\<windowsStreamSecurity></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78806-108">構文</span><span class="sxs-lookup"><span data-stu-id="78806-108">Syntax</span></span>  
  
```xml  
<windowsStreamSecurity protectionLevel="None/Sign/EncryptAndSign" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="78806-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="78806-109">Attributes and Elements</span></span>  
 <span data-ttu-id="78806-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="78806-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="78806-111">属性</span><span class="sxs-lookup"><span data-stu-id="78806-111">Attributes</span></span>  
  
|<span data-ttu-id="78806-112">属性</span><span class="sxs-lookup"><span data-stu-id="78806-112">Attribute</span></span>|<span data-ttu-id="78806-113">説明</span><span class="sxs-lookup"><span data-stu-id="78806-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="78806-114">protectionLevel</span><span class="sxs-lookup"><span data-stu-id="78806-114">protectionLevel</span></span>|<span data-ttu-id="78806-115">メッセージ レベルのセキュリティを定義します。</span><span class="sxs-lookup"><span data-stu-id="78806-115">Defines message-level security.</span></span> <span data-ttu-id="78806-116">メッセージに署名すると、転送中のメッセージが第三者によって改ざんされるリスクを軽減します。</span><span class="sxs-lookup"><span data-stu-id="78806-116">Signing messages mitigates the risk of a third party tampering with the message while it is being transferred.</span></span> <span data-ttu-id="78806-117">暗号化によって、トランスポート中にデータ レベルのプライバシーが提供されます。</span><span class="sxs-lookup"><span data-stu-id="78806-117">Encryption provides data-level privacy during transport.</span></span> <span data-ttu-id="78806-118">以下の値が有効です。</span><span class="sxs-lookup"><span data-stu-id="78806-118">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="78806-119">-None。保護されません。</span><span class="sxs-lookup"><span data-stu-id="78806-119">-   None: No protection.</span></span><br /><span data-ttu-id="78806-120">署名:メッセージは署名されます。</span><span class="sxs-lookup"><span data-stu-id="78806-120">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="78806-121">-EncryptAndSign:メッセージに署名および暗号化します。</span><span class="sxs-lookup"><span data-stu-id="78806-121">-   EncryptAndSign: Messages are signed and encrypted.</span></span><br /><br /> <span data-ttu-id="78806-122">既定値は EncryptAndSign です。</span><span class="sxs-lookup"><span data-stu-id="78806-122">The default is EncryptAndSign.</span></span><br /><br /> <span data-ttu-id="78806-123">この属性は <xref:System.Net.Security.ProtectionLevel> 型です。</span><span class="sxs-lookup"><span data-stu-id="78806-123">This attribute is of type <xref:System.Net.Security.ProtectionLevel>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="78806-124">子要素</span><span class="sxs-lookup"><span data-stu-id="78806-124">Child Elements</span></span>  
 <span data-ttu-id="78806-125">なし</span><span class="sxs-lookup"><span data-stu-id="78806-125">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="78806-126">親要素</span><span class="sxs-lookup"><span data-stu-id="78806-126">Parent Elements</span></span>  
  
|<span data-ttu-id="78806-127">要素</span><span class="sxs-lookup"><span data-stu-id="78806-127">Element</span></span>|<span data-ttu-id="78806-128">説明</span><span class="sxs-lookup"><span data-stu-id="78806-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="78806-129">\<binding></span><span class="sxs-lookup"><span data-stu-id="78806-129">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="78806-130">カスタム バインドのすべてのバインド機能を定義します。</span><span class="sxs-lookup"><span data-stu-id="78806-130">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="78806-131">Remarks</span><span class="sxs-lookup"><span data-stu-id="78806-131">Remarks</span></span>  
 <span data-ttu-id="78806-132">TCP などのストリーム指向プロトコルおよび名前付きパイプを使用するトランスポートは、ストリーム ベースのトランスポート アップグレードをサポートします。</span><span class="sxs-lookup"><span data-stu-id="78806-132">Transports that use a stream-oriented protocol such as TCP and named pipes support stream-based transport upgrades.</span></span> <span data-ttu-id="78806-133">特に、WCF にはセキュリティ アップグレードが用意されています。</span><span class="sxs-lookup"><span data-stu-id="78806-133">Specifically, WCF provides security upgrades.</span></span> <span data-ttu-id="78806-134">およびこのトランスポート セキュリティの構成がこの構成要素によってカプセル化[ \<sslStreamSecurity >](../../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md)、構成し、カスタム バインドに追加するには、この</span><span class="sxs-lookup"><span data-stu-id="78806-134">The configuration of this transport security is encapsulated by this configuration element  as well as by [\<sslStreamSecurity>](../../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md), which can be configured and added to a custom binding</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78806-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="78806-135">See also</span></span>

- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Configuration.WindowsStreamSecurityElement>
- <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement>
- [<span data-ttu-id="78806-136">バインディング</span><span class="sxs-lookup"><span data-stu-id="78806-136">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="78806-137">バインディングの拡張</span><span class="sxs-lookup"><span data-stu-id="78806-137">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="78806-138">カスタム バインディング</span><span class="sxs-lookup"><span data-stu-id="78806-138">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="78806-139">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="78806-139">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
