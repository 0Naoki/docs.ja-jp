---
title: <baseAddressPrefixFilters>
ms.date: 03/30/2017
ms.assetid: 8cab2a9a-c51f-4283-bb60-2ad0c274fd46
ms.openlocfilehash: 378db238d647be2248c0303f45aece42f7ea5b31
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59227627"
---
# <a name="baseaddressprefixfilters"></a><span data-ttu-id="f05e4-101">\<baseAddressPrefixFilters></span><span class="sxs-lookup"><span data-stu-id="f05e4-101">\<baseAddressPrefixFilters></span></span>
<span data-ttu-id="f05e4-102">構成フィルター、IIS で Windows Communication Foundation (WCF) アプリケーションをホストする場合に、適切なインターネット インフォメーション サービス (IIS) のバインドを選択するためのメカニズムを提供するパススルーを指定する要素のコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="f05e4-102">Represents a collection of configuration elements that specify pass through filters, which provide a mechanism to pick the appropriate Internet Information Services (IIS) bindings when hosting the Windows Communication Foundation (WCF) application in IIS.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="f05e4-103">\<baseAddressPrefixFilters > は"localhost"を認識ではなくコンピューターの完全修飾名を代わりに使用します。</span><span class="sxs-lookup"><span data-stu-id="f05e4-103">\<baseAddressPrefixFilters> does not recognize "localhost", use the fully qualified machine name instead.</span></span>  
  
 <span data-ttu-id="f05e4-104">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="f05e4-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="f05e4-105">\<serviceHostingEnvironment ></span><span class="sxs-lookup"><span data-stu-id="f05e4-105">\<ServiceHostingEnvironment></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f05e4-106">構文</span><span class="sxs-lookup"><span data-stu-id="f05e4-106">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>
  <baseAddressPrefixFilters>
    <add prefix="String" />
   </baseAddressPrefixFilters>
</serviceHostingEnvironment>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f05e4-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="f05e4-107">Attributes and Elements</span></span>  
 <span data-ttu-id="f05e4-108">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="f05e4-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f05e4-109">属性</span><span class="sxs-lookup"><span data-stu-id="f05e4-109">Attributes</span></span>  
 <span data-ttu-id="f05e4-110">なし。</span><span class="sxs-lookup"><span data-stu-id="f05e4-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="f05e4-111">子要素</span><span class="sxs-lookup"><span data-stu-id="f05e4-111">Child Elements</span></span>  
  
|<span data-ttu-id="f05e4-112">要素</span><span class="sxs-lookup"><span data-stu-id="f05e4-112">Element</span></span>|<span data-ttu-id="f05e4-113">説明</span><span class="sxs-lookup"><span data-stu-id="f05e4-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f05e4-114">\<add></span><span class="sxs-lookup"><span data-stu-id="f05e4-114">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-baseaddressprefixfilter.md)|<span data-ttu-id="f05e4-115">サービス ホストによって使用されるベース アドレスのプレフィックス フィルターを指定する構成要素を追加します。</span><span class="sxs-lookup"><span data-stu-id="f05e4-115">Adds a configuration element that specifies a prefix filter for the base addresses used by the service host.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f05e4-116">親要素</span><span class="sxs-lookup"><span data-stu-id="f05e4-116">Parent Elements</span></span>  
  
|<span data-ttu-id="f05e4-117">要素</span><span class="sxs-lookup"><span data-stu-id="f05e4-117">Element</span></span>|<span data-ttu-id="f05e4-118">説明</span><span class="sxs-lookup"><span data-stu-id="f05e4-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f05e4-119">\<serviceHostingEnvironment></span><span class="sxs-lookup"><span data-stu-id="f05e4-119">\<serviceHostingEnvironment></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md)|<span data-ttu-id="f05e4-120">環境をホストするサービスがインスタンス化する特定のトランスポートの型を定義します。</span><span class="sxs-lookup"><span data-stu-id="f05e4-120">Defines the type the service hosting environment instantiates for a particular transport.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f05e4-121">Remarks</span><span class="sxs-lookup"><span data-stu-id="f05e4-121">Remarks</span></span>  
 <span data-ttu-id="f05e4-122">プレフィックス フィルターは、サービスによって使用される URI を、共有ホスティング プロバイダーが指定できるようにする手段を提供します。</span><span class="sxs-lookup"><span data-stu-id="f05e4-122">A prefix filter provides a way for shared hosting providers to specify which URIs are to be used by the service.</span></span> <span data-ttu-id="f05e4-123">これにより、共有ホストは、同じサイト上の同じスキームに対して、別々のベース アドレスを使用して複数のアプリケーションをホストできるようになります。</span><span class="sxs-lookup"><span data-stu-id="f05e4-123">It enables shared hosts to host multiple applications with different base addresses for the same scheme on the same site.</span></span>  
  
 <span data-ttu-id="f05e4-124">IIS Web サイトは、仮想ディレクトリを含む仮想アプリケーションのコンテナーです。</span><span class="sxs-lookup"><span data-stu-id="f05e4-124">IIS Web sites are containers for virtual applications which contain virtual directories.</span></span> <span data-ttu-id="f05e4-125">サイト内のアプリケーションには、1 つ以上の IIS バインディングからアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="f05e4-125">The application in a site can be accessed through one or more IIS bindings.</span></span> <span data-ttu-id="f05e4-126">IIS バインディングは、バインディング プロトコルとバインディング情報という 2 つの情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="f05e4-126">IIS bindings provide two pieces of information: binding protocol and binding information.</span></span> <span data-ttu-id="f05e4-127">バインディング プロトコル (HTTP など) は通信を行うスキームを定義し、バインディング情報 (IP アドレス、ポート、ホスト ヘッダーなど) にはサイトにアクセスするために使用するデータが含まれます。</span><span class="sxs-lookup"><span data-stu-id="f05e4-127">Binding protocol (for example, HTTP) defines the scheme over which communication occurs, and binding information (for example, IP Address, Port, Hostheader) contains data used to access the site.</span></span>  
  
 <span data-ttu-id="f05e4-128">IIS では、サイトごとに複数の IIS バインディングを指定できるので、各スキームに複数のベース アドレスが定義されることがあります。</span><span class="sxs-lookup"><span data-stu-id="f05e4-128">IIS supports specifying multiple IIS bindings for each site, which results in multiple base addresses for each scheme.</span></span> <span data-ttu-id="f05e4-129">サイトでホストされている WCF サービスにスキームごとに 1 つだけのベース アドレスにバインドが使用できるため、ホステッド サービスの必要なベース アドレスを選択、プレフィックス フィルター機能を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="f05e4-129">Because a WCF service hosted under a site allows binding to only one base address for each scheme, you can use the prefix filter feature to pick the required base address of the hosted service.</span></span> <span data-ttu-id="f05e4-130">IIS によって指定される受信ベース アドレスは、オプションのプレフィックス リスト フィルターに基づいてフィルター処理されます。</span><span class="sxs-lookup"><span data-stu-id="f05e4-130">The incoming base addresses, supplied by IIS, are filtered based on the optional prefix list filter.</span></span>  
  
 <span data-ttu-id="f05e4-131">たとえば、サイトに次のベース アドレスが含まれているとします。</span><span class="sxs-lookup"><span data-stu-id="f05e4-131">For example, your site can contain the following base addresses.</span></span>  
  
```  
http://testl.fabrikam.com/Service.svc  
http://test2.fabrikam.com/Service.svc  
```  
  
 <span data-ttu-id="f05e4-132">次の構成ファイルを使用して、appdomain レベルでプレフィックス フィルターを指定できます。</span><span class="sxs-lookup"><span data-stu-id="f05e4-132">You can use the following configuration file to specify a prefix filter at the appdomain level.</span></span>  
  
```xml  
<system.serviceModel>
  <serviceHostingEnvironment>
    <baseAddressPrefixFilters>
      <add prefix="net.tcp://test1.fabrikam.com:8000" />
      <add prefix="http://test2.fabrikam.com:9000" />
    </baseAddressPrefixFilters>
  </serviceHostingEnvironment>
</system.serviceModel>
```  
  
 <span data-ttu-id="f05e4-133">この例では、`net.tcp://test1.fabrikam.com:8000` と `http://test2.fabrikam.com:9000` が、対応するスキームに渡される唯一のベース アドレスです。</span><span class="sxs-lookup"><span data-stu-id="f05e4-133">In this example, `net.tcp://test1.fabrikam.com:8000` and `http://test2.fabrikam.com:9000` are the only base addresses for their respective schemes, which are allowed to be passed through.</span></span>  
  
 <span data-ttu-id="f05e4-134">既定では、プレフィックスを指定しない場合、すべてのアドレスが渡されます。</span><span class="sxs-lookup"><span data-stu-id="f05e4-134">By default, when prefix is not specified, all addresses are passed through.</span></span> <span data-ttu-id="f05e4-135">プレフィックスだけを指定すると、そのスキームに一致するベース アドレスを渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="f05e4-135">Specifying the prefix only allows the matching base address for that scheme to be passed through.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f05e4-136">フィルターでワイルドカードはサポートされません。</span><span class="sxs-lookup"><span data-stu-id="f05e4-136">The filter does not support any wildcards.</span></span> <span data-ttu-id="f05e4-137">また、IIS が提供する baseAddresses には、`baseAddressPrefixFilters` リストに存在しない他のスキームにバインドされたアドレスが指定される場合があります。</span><span class="sxs-lookup"><span data-stu-id="f05e4-137">In addition, the baseAddresses supplied by IIS may have addresses bound to other schemes not present in the `baseAddressPrefixFilters` list.</span></span> <span data-ttu-id="f05e4-138">これらのアドレスはフィルターで除外されません。</span><span class="sxs-lookup"><span data-stu-id="f05e4-138">These addresses are not filtered out.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f05e4-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="f05e4-139">See also</span></span>

- <xref:System.ServiceModel.Configuration.BaseAddressPrefixFilterElementCollection>
- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
- [<span data-ttu-id="f05e4-140">ホスト</span><span class="sxs-lookup"><span data-stu-id="f05e4-140">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
