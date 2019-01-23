---
title: '&lt;serviceHostingEnvironment&gt;'
ms.date: 03/30/2017
ms.assetid: 4f8a7c4f-e735-4987-979a-b74fcdae2652
ms.openlocfilehash: 47e683969a62541dd48a3c7211e1edf3bb7b4038
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54493847"
---
# <a name="ltservicehostingenvironmentgt"></a><span data-ttu-id="b3baf-102">&lt;serviceHostingEnvironment&gt;</span><span class="sxs-lookup"><span data-stu-id="b3baf-102">&lt;serviceHostingEnvironment&gt;</span></span>
<span data-ttu-id="b3baf-103">この要素は、環境をホストするサービスがインスタンス化する特定のトランスポートの型を定義します。</span><span class="sxs-lookup"><span data-stu-id="b3baf-103">This element defines the type the service hosting environment instantiates for a particular transport.</span></span> <span data-ttu-id="b3baf-104">この要素が空の場合は、既定の型が使用されます。</span><span class="sxs-lookup"><span data-stu-id="b3baf-104">If this element is empty, the default type is used.</span></span> <span data-ttu-id="b3baf-105">この要素は、アプリケーション レベルまたはコンピューター レベルの構成ファイルでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="b3baf-105">This element can only be used at the application or machine level configuration files.</span></span>  
  
 <span data-ttu-id="b3baf-106">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="b3baf-106">\<system.ServiceModel></span></span>  
<span data-ttu-id="b3baf-107">\<serviceHostingEnvironment ></span><span class="sxs-lookup"><span data-stu-id="b3baf-107">\<ServiceHostingEnvironment></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b3baf-108">構文</span><span class="sxs-lookup"><span data-stu-id="b3baf-108">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment aspNetCompatibilityEnabled="Boolean"
                           minFreeMemoryPercentageToActivateService="Integer"
                           multipleSiteBindingsEnabled="Boolean">
  <baseAddressPrefixFilters>
    <add prefix="string" />
  </baseAddressPrefixFilters>
  <serviceActivations>
    <add factory="String"
         service="String" />
  </serviceActivations>
  <transportConfigurationTypes>
    <add name="String"
         transportConfigurationType="String" />
  </transportConfigurationTypes>
</serviceHostingEnvironment>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b3baf-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="b3baf-109">Attributes and Elements</span></span>  
 <span data-ttu-id="b3baf-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="b3baf-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b3baf-111">属性</span><span class="sxs-lookup"><span data-stu-id="b3baf-111">Attributes</span></span>  
  
|<span data-ttu-id="b3baf-112">属性</span><span class="sxs-lookup"><span data-stu-id="b3baf-112">Attribute</span></span>|<span data-ttu-id="b3baf-113">説明</span><span class="sxs-lookup"><span data-stu-id="b3baf-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b3baf-114">aspNetCompatibilityEnabled</span><span class="sxs-lookup"><span data-stu-id="b3baf-114">aspNetCompatibilityEnabled</span></span>|<span data-ttu-id="b3baf-115">ASP.NET の互換モードが現在のアプリケーションに対して有効になっているかどうかを示すブール値。</span><span class="sxs-lookup"><span data-stu-id="b3baf-115">A Boolean value indicating whether the ASP.NET compatibility mode has been turned on for the current application.</span></span> <span data-ttu-id="b3baf-116">既定値は `false` です。</span><span class="sxs-lookup"><span data-stu-id="b3baf-116">The default is `false`.</span></span><br /><br /> <span data-ttu-id="b3baf-117">この属性を設定すると`true`、Windows Communication Foundation (WCF) サービスへの要求を ASP.NET HTTP パイプラインを通過し、非 HTTP プロトコルを介した通信は禁止されています。</span><span class="sxs-lookup"><span data-stu-id="b3baf-117">When this attribute is set to `true`, requests to Windows Communication Foundation (WCF) services flow through the ASP.NET HTTP pipeline, and communication over non-HTTP protocols is prohibited.</span></span> <span data-ttu-id="b3baf-118">詳細については、次を参照してください。 [WCF サービスと ASP.NET](../../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md)します。</span><span class="sxs-lookup"><span data-stu-id="b3baf-118">For more information, see [WCF Services and ASP.NET](../../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md).</span></span>|  
|<span data-ttu-id="b3baf-119">minFreeMemoryPercentageToActivateService</span><span class="sxs-lookup"><span data-stu-id="b3baf-119">minFreeMemoryPercentageToActivateService</span></span>|<span data-ttu-id="b3baf-120">WCF サービスをアクティブにする前に、システムに利用できるように、空きメモリの最小量を指定する整数。</span><span class="sxs-lookup"><span data-stu-id="b3baf-120">An integer that specifies the minimum amount of free memory that should be available to the system, before a WCF service can be activated.</span></span> <span data-ttu-id="b3baf-121">**注意:** WCF サービスの web.config ファイルで部分信頼と共にこの属性を指定するが、<xref:System.Security.SecurityException>サービスを実行するとします。</span><span class="sxs-lookup"><span data-stu-id="b3baf-121">**Caution:**  Specifying this attribute along with partial trust in the web.config file of a WCF service will result in a <xref:System.Security.SecurityException> when the service is run.</span></span>|  
|<span data-ttu-id="b3baf-122">multipleSiteBindingsEnabled</span><span class="sxs-lookup"><span data-stu-id="b3baf-122">multipleSiteBindingsEnabled</span></span>|<span data-ttu-id="b3baf-123">1 つのサイトで複数の IIS バインディングが有効になっているかどうかを指定するブール値。</span><span class="sxs-lookup"><span data-stu-id="b3baf-123">A Boolean value that specifies whether multiple IIS bindings per site is enabled.</span></span><br /><br /> <span data-ttu-id="b3baf-124">IIS は、仮想ディレクトリを含む仮想アプリケーションのコンテナーとしての Web サイトで構成されています。</span><span class="sxs-lookup"><span data-stu-id="b3baf-124">IIS consists of web sites, which are containers for virtual applications containing virtual directories.</span></span> <span data-ttu-id="b3baf-125">サイト内のアプリケーションに、1 つ以上の IIS バインディングからアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="b3baf-125">The application in a site can be accessed through one or more IIS binding.</span></span> <span data-ttu-id="b3baf-126">IIS バインディングは、バインディング プロトコルとバインディング情報という 2 つの情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="b3baf-126">An IIS binding provides two pieces of information: a binding protocol and binding information.</span></span> <span data-ttu-id="b3baf-127">バインディング プロトコルは通信を行うスキームを定義するもので、バインディング情報はサイトにアクセスするために使用する情報です。</span><span class="sxs-lookup"><span data-stu-id="b3baf-127">Binding protocol defines the scheme over which communication occurs, and binding information is the information used to access the site.</span></span> <span data-ttu-id="b3baf-128">バインディング プロトコルの例には HTTP があり、一方、バインディング情報には IP アドレス、ポート、ホスト ヘッダーなどを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="b3baf-128">An example of a binding protocol can be HTTP, whereas binding information can contain an IP address, Port, host header, etc.</span></span><br /><br /> <span data-ttu-id="b3baf-129">IIS ではサイトごとに複数の IIS バインディングを指定でき、これによりスキームごとに複数のベース アドレスをサポートできます。</span><span class="sxs-lookup"><span data-stu-id="b3baf-129">IIS supports specifying multiple IIS bindings per site, which results in multiple base addresses per scheme.</span></span> <span data-ttu-id="b3baf-130">ただし、サイトでホストされている Windows Communication Foundation (WCF) サービスは、スキームごとの 1 つのみの baseAddress へのバインドを許可します。</span><span class="sxs-lookup"><span data-stu-id="b3baf-130">However, a Windows Communication Foundation (WCF) service hosted under a site allows binding to only one baseAddress per scheme.</span></span><br /><br /> <span data-ttu-id="b3baf-131">Windows Communication Foundation (WCF) サービスの 1 つのサイトの複数の IIS バインディングを有効にするのにはこの属性設定`true`します。</span><span class="sxs-lookup"><span data-stu-id="b3baf-131">To enable multiple IIS bindings per site for a Windows Communication Foundation (WCF) service, set this attribute to `true`.</span></span> <span data-ttu-id="b3baf-132">複数のサイト バインディングは HTTP プロトコルに対してのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="b3baf-132">Notice that multiple site binding is supported only for the HTTP protocol.</span></span> <span data-ttu-id="b3baf-133">構成ファイル内のエンドポイントのアドレスには完全な URI を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b3baf-133">The address of endpoints in the configuration file needs to be a complete URI.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b3baf-134">子要素</span><span class="sxs-lookup"><span data-stu-id="b3baf-134">Child Elements</span></span>  
  
|<span data-ttu-id="b3baf-135">要素</span><span class="sxs-lookup"><span data-stu-id="b3baf-135">Element</span></span>|<span data-ttu-id="b3baf-136">説明</span><span class="sxs-lookup"><span data-stu-id="b3baf-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b3baf-137">\<baseAddressPrefixFilters></span><span class="sxs-lookup"><span data-stu-id="b3baf-137">\<baseAddressPrefixFilters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/baseaddressprefixfilters.md)|<span data-ttu-id="b3baf-138">サービス ホストによって使用されるベース アドレスのプレフィックス フィルターを指定する構成要素のコレクション。</span><span class="sxs-lookup"><span data-stu-id="b3baf-138">A collection of configuration elements that specify prefix filters for the base addresses used by the service host.</span></span>|  
|[<span data-ttu-id="b3baf-139">\<serviceActivations></span><span class="sxs-lookup"><span data-stu-id="b3baf-139">\<serviceActivations></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/serviceactivations.md)|<span data-ttu-id="b3baf-140">アクティベーション設定を記述する構成セクション。</span><span class="sxs-lookup"><span data-stu-id="b3baf-140">A configuration section that describes activation settings.</span></span>|  
|[<span data-ttu-id="b3baf-141">\<transportConfigurationTypes></span><span class="sxs-lookup"><span data-stu-id="b3baf-141">\<transportConfigurationTypes></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transportconfigurationtypes.md)|<span data-ttu-id="b3baf-142">特定のトランスポートの型を識別する構成要素のコレクション。</span><span class="sxs-lookup"><span data-stu-id="b3baf-142">A collection of configuration elements that identify the type of a particular transport.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b3baf-143">親要素</span><span class="sxs-lookup"><span data-stu-id="b3baf-143">Parent Elements</span></span>  
  
|<span data-ttu-id="b3baf-144">要素</span><span class="sxs-lookup"><span data-stu-id="b3baf-144">Element</span></span>|<span data-ttu-id="b3baf-145">説明</span><span class="sxs-lookup"><span data-stu-id="b3baf-145">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b3baf-146">serviceModel</span><span class="sxs-lookup"><span data-stu-id="b3baf-146">serviceModel</span></span>|<span data-ttu-id="b3baf-147">すべての Windows Communication Foundation (WCF) 構成要素のルート要素です。</span><span class="sxs-lookup"><span data-stu-id="b3baf-147">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b3baf-148">Remarks</span><span class="sxs-lookup"><span data-stu-id="b3baf-148">Remarks</span></span>  
 <span data-ttu-id="b3baf-149">既定では、WCF サービスは、ホストされるアプリケーション ドメイン (AppDomain) で ASP.NET と並行で実行します。</span><span class="sxs-lookup"><span data-stu-id="b3baf-149">By default, WCF services run side-by-side with ASP.NET in hosted Application Domains (AppDomain).</span></span> <span data-ttu-id="b3baf-150">WCF と ASP.NET が同じ AppDomain で共存できても、既定では WCF 要求は ASP.NET HTTP パイプラインでは処理されません。</span><span class="sxs-lookup"><span data-stu-id="b3baf-150">Even though WCF and ASP.NET can coexist in the same AppDomain, WCF requests are not processed by the ASP.NET HTTP Pipeline by default.</span></span> <span data-ttu-id="b3baf-151">結果として、ASP.NET アプリケーション プラットフォームのいくつかの要素は、WCF サービスでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="b3baf-151">As a result, several elements of the ASP.NET application platform are not available to WCF services.</span></span> <span data-ttu-id="b3baf-152">これらの要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="b3baf-152">These include</span></span>  
  
-   <span data-ttu-id="b3baf-153">ASP.NET ファイル/URL 承認</span><span class="sxs-lookup"><span data-stu-id="b3baf-153">ASP.NET File/URL Authorization</span></span>  
  
-   <span data-ttu-id="b3baf-154">ASP.NET の偽装</span><span class="sxs-lookup"><span data-stu-id="b3baf-154">ASP.NET Impersonation</span></span>  
  
-   <span data-ttu-id="b3baf-155">クッキー ベースのセッションの状態</span><span class="sxs-lookup"><span data-stu-id="b3baf-155">Cookie-based Session State</span></span>  
  
-   <span data-ttu-id="b3baf-156">HttpContext.Current</span><span class="sxs-lookup"><span data-stu-id="b3baf-156">HttpContext.Current</span></span>  
  
-   <span data-ttu-id="b3baf-157">カスタム HttpModule を経由するパイプライン拡張</span><span class="sxs-lookup"><span data-stu-id="b3baf-157">Pipeline Extensibility via custom HttpModule</span></span>  
  
 <span data-ttu-id="b3baf-158">WCF サービスが ASP.NET のコンテキストで機能し、HTTP 経由でのみ通信する必要がある場合は、WCF の ASP.NET 互換モードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="b3baf-158">If your WCF services need to function in the ASP.NET context, and communicate only over HTTP, you can use WCF’s ASP.NET compatibility mode.</span></span> <span data-ttu-id="b3baf-159">このモードは、`aspNetCompatibilityEnabled` 属性がアプリケーション レベルで `true` に設定されている場合に有効です。</span><span class="sxs-lookup"><span data-stu-id="b3baf-159">This mode is turned on when the `aspNetCompatibilityEnabled` attribute is set to `true` at the application level.</span></span> <span data-ttu-id="b3baf-160">サービス実装では、<xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute> クラスを使用して互換モードで実行できる機能を宣言する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b3baf-160">Service implementations must declare their ability to run in compatibility mode using the <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute> class.</span></span> <span data-ttu-id="b3baf-161">互換モードが有効な場合、</span><span class="sxs-lookup"><span data-stu-id="b3baf-161">When the compatibility mode is enabled,</span></span>  
  
-   <span data-ttu-id="b3baf-162">ASP.NET ファイル/URL 承認が、WCF 承認の前に強制的に実行されます。</span><span class="sxs-lookup"><span data-stu-id="b3baf-162">ASP.NET File/URL Authorization is enforced prior to WCF authorization.</span></span> <span data-ttu-id="b3baf-163">承認決定は、要求のトランスポート レベルの ID に基づいています。</span><span class="sxs-lookup"><span data-stu-id="b3baf-163">An authorization decision is based on the transport-level identity of the request.</span></span> <span data-ttu-id="b3baf-164">メッセージ レベルでの ID は、無視されます。</span><span class="sxs-lookup"><span data-stu-id="b3baf-164">Identities at the message level are ignored.</span></span>  
  
-   <span data-ttu-id="b3baf-165">WCF サービス操作は、ASP.NET の偽装コンテキストで実行を開始します。</span><span class="sxs-lookup"><span data-stu-id="b3baf-165">WCF service operations start to execute in the ASP.NET impersonation context.</span></span> <span data-ttu-id="b3baf-166">ASP.NET の偽装と WCF の偽装の両方が特定のサービスで有効な場合は、WCF の偽装コンテキストが適用されます。</span><span class="sxs-lookup"><span data-stu-id="b3baf-166">If both ASP.NET impersonation and WCF impersonation are enabled for a specific service, the WCF impersonation context applies.</span></span>  
  
-   <span data-ttu-id="b3baf-167">HttpContext.Current を WCF サービス コードから使用できるため、サービスは非 HTTP エンドポイントを公開しません。</span><span class="sxs-lookup"><span data-stu-id="b3baf-167">HttpContext.Current can be used from WCF service code, and services are prevented from exposing non-HTTP endpoints.</span></span>  
  
-   <span data-ttu-id="b3baf-168">WCF 要求は、ASP.NET パイプラインによって処理されます。</span><span class="sxs-lookup"><span data-stu-id="b3baf-168">WCF requests are processed by the ASP.NET pipeline.</span></span> <span data-ttu-id="b3baf-169">受信要求を処理するように構成された HttpModules は、WCF 要求も処理できます。</span><span class="sxs-lookup"><span data-stu-id="b3baf-169">HttpModules that have been configured to act on incoming requests can also process WCF requests.</span></span> <span data-ttu-id="b3baf-170">これらには、ASP.NET プラットフォーム コンポーネント (<xref:System.Web.SessionState.SessionStateModule> など) とカスタム サードパーティ モジュールが含まれます。</span><span class="sxs-lookup"><span data-stu-id="b3baf-170">These can include ASP.NET platform components (e.g., <xref:System.Web.SessionState.SessionStateModule>), as well as custom third party modules.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b3baf-171">例</span><span class="sxs-lookup"><span data-stu-id="b3baf-171">Example</span></span>  
 <span data-ttu-id="b3baf-172">次のコード サンプルは、ASP 互換モードを有効にする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="b3baf-172">The following code sample shows how to enable ASP Compatibility Mode.</span></span>  
  
## <a name="code"></a><span data-ttu-id="b3baf-173">コード</span><span class="sxs-lookup"><span data-stu-id="b3baf-173">Code</span></span>  
  
```xml  
<serviceHostingEnvironment aspNetCompatibilityEnabled="true"/>
```  
  
## <a name="see-also"></a><span data-ttu-id="b3baf-174">関連項目</span><span class="sxs-lookup"><span data-stu-id="b3baf-174">See also</span></span>
- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
- [<span data-ttu-id="b3baf-175">ホスティング</span><span class="sxs-lookup"><span data-stu-id="b3baf-175">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
- [<span data-ttu-id="b3baf-176">WCF サービスと ASP.NET</span><span class="sxs-lookup"><span data-stu-id="b3baf-176">WCF Services and ASP.NET</span></span>](../../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md)
