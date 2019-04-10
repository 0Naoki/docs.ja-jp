---
title: <sslStreamSecurity>
ms.date: 03/30/2017
ms.assetid: 430a378b-a742-4858-8a12-9f9b235fd627
ms.openlocfilehash: 67ec30b2bf3c322b949700789ce942e4281b77a4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59204446"
---
# <a name="sslstreamsecurity"></a><span data-ttu-id="f7412-101">\<sslStreamSecurity></span><span class="sxs-lookup"><span data-stu-id="f7412-101">\<sslStreamSecurity></span></span>
<span data-ttu-id="f7412-102">SSL ストリームを使用するチャネル セキュリティをサポートするカスタム バインディング要素を表します。</span><span class="sxs-lookup"><span data-stu-id="f7412-102">Represents a custom binding element that supports channel security using an SSL stream.</span></span>  
  
 <span data-ttu-id="f7412-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="f7412-103">\<system.serviceModel></span></span>  
<span data-ttu-id="f7412-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="f7412-104">\<bindings></span></span>  
<span data-ttu-id="f7412-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="f7412-105">\<customBinding></span></span>  
<span data-ttu-id="f7412-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="f7412-106">\<binding></span></span>  
<span data-ttu-id="f7412-107">\<sslStreamSecurity></span><span class="sxs-lookup"><span data-stu-id="f7412-107">\<sslStreamSecurity></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7412-108">構文</span><span class="sxs-lookup"><span data-stu-id="f7412-108">Syntax</span></span>  
  
```xml  
<sslStreamSecurity requireClientCertificate="Boolean"
                   sslProtocols="Ssl3|Tls|Tls11|Tls12" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f7412-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="f7412-109">Attributes and Elements</span></span>  
 <span data-ttu-id="f7412-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="f7412-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f7412-111">属性</span><span class="sxs-lookup"><span data-stu-id="f7412-111">Attributes</span></span>  
  
|<span data-ttu-id="f7412-112">属性</span><span class="sxs-lookup"><span data-stu-id="f7412-112">Attribute</span></span>|<span data-ttu-id="f7412-113">説明</span><span class="sxs-lookup"><span data-stu-id="f7412-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f7412-114">requireClientCertificate</span><span class="sxs-lookup"><span data-stu-id="f7412-114">requireClientCertificate</span></span>|<span data-ttu-id="f7412-115">クライアント証明書がこのバインディングに必要かどうかを指定するブール値。</span><span class="sxs-lookup"><span data-stu-id="f7412-115">A Boolean value that specifies if a client certificate is required for this binding.</span></span> <span data-ttu-id="f7412-116">既定値は `false` です。</span><span class="sxs-lookup"><span data-stu-id="f7412-116">The default is `false`.</span></span>|  
|<span data-ttu-id="f7412-117">sslProtocols</span><span class="sxs-lookup"><span data-stu-id="f7412-117">sslProtocols</span></span>|<span data-ttu-id="f7412-118">どの SslProtocols がサポートされているのかを指定する SslProtocols 列挙型フラグの値。</span><span class="sxs-lookup"><span data-stu-id="f7412-118">A SslProtocols enum flag value that specifies which SslProtocols are supported.</span></span> <span data-ttu-id="f7412-119">既定値は Ssl3&#124;Tls&#124;Tls11&#124;tls12 です。</span><span class="sxs-lookup"><span data-stu-id="f7412-119">The default is Ssl3&#124;Tls&#124;Tls11&#124;Tls12.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f7412-120">子要素</span><span class="sxs-lookup"><span data-stu-id="f7412-120">Child Elements</span></span>  
 <span data-ttu-id="f7412-121">なし。</span><span class="sxs-lookup"><span data-stu-id="f7412-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f7412-122">親要素</span><span class="sxs-lookup"><span data-stu-id="f7412-122">Parent Elements</span></span>  
  
|<span data-ttu-id="f7412-123">要素</span><span class="sxs-lookup"><span data-stu-id="f7412-123">Element</span></span>|<span data-ttu-id="f7412-124">説明</span><span class="sxs-lookup"><span data-stu-id="f7412-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f7412-125">\<binding></span><span class="sxs-lookup"><span data-stu-id="f7412-125">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="f7412-126">カスタム バインドのすべてのバインド機能を定義します。</span><span class="sxs-lookup"><span data-stu-id="f7412-126">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f7412-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="f7412-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.SslStreamSecurityElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement>
- [<span data-ttu-id="f7412-128">バインディング</span><span class="sxs-lookup"><span data-stu-id="f7412-128">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="f7412-129">バインディングの拡張</span><span class="sxs-lookup"><span data-stu-id="f7412-129">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="f7412-130">カスタム バインディング</span><span class="sxs-lookup"><span data-stu-id="f7412-130">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="f7412-131">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="f7412-131">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
