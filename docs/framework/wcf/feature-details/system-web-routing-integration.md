---
title: System.Web.Routing 統合
ms.date: 03/30/2017
ms.assetid: 31fe2a4f-5c47-4e5d-8ee1-84c524609d41
ms.openlocfilehash: 540795838109b99111279bc693a765f58a1ff18e
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "43504845"
---
# <a name="systemwebrouting-integration"></a><span data-ttu-id="c31e3-102">System.Web.Routing 統合</span><span class="sxs-lookup"><span data-stu-id="c31e3-102">System.Web.Routing Integration</span></span>
<span data-ttu-id="c31e3-103">Windows Communication Foundation (WCF) サービスでは、インターネット インフォメーション サービス (IIS) をホストする場合は、仮想ディレクトリで、.svc ファイルを配置します。</span><span class="sxs-lookup"><span data-stu-id="c31e3-103">When hosting a Windows Communication Foundation (WCF) service in Internet Information Service (IIS) you place a .svc file in the virtual directory.</span></span> <span data-ttu-id="c31e3-104">この .svc ファイルは、使用するサービス ホスト ファクトリと、サービスを実装するクラスを指定します。</span><span class="sxs-lookup"><span data-stu-id="c31e3-104">This .svc file specifies the service host factory to use as well as the class that implements the service.</span></span> <span data-ttu-id="c31e3-105">たとえば、URI で .svc ファイルを指定する、サービスに要求を行うときに:http://contoso.com/EmployeeServce.svcします。</span><span class="sxs-lookup"><span data-stu-id="c31e3-105">When making requests to the service you specify the .svc file in the URI, for example: http://contoso.com/EmployeeServce.svc.</span></span> <span data-ttu-id="c31e3-106">REST サービスを記述するプログラマにとっては、この種類の URI は最適とは言えません。</span><span class="sxs-lookup"><span data-stu-id="c31e3-106">For programmers writing REST services this type of URI is not optimal.</span></span> <span data-ttu-id="c31e3-107">REST サービス用の URI は、特定のリソースを指定しており、拡張子がないのが普通です。</span><span class="sxs-lookup"><span data-stu-id="c31e3-107">URIs for REST services specify a specific resource and normally do not have any extensions.</span></span> <span data-ttu-id="c31e3-108"><xref:System.Web.Routing>統合機能では、拡張子のない Uri に応答する WCF REST サービスをホストすることができます。</span><span class="sxs-lookup"><span data-stu-id="c31e3-108">The <xref:System.Web.Routing> integration feature allows you to host a WCF REST service that responds to URIs without an extension.</span></span> <span data-ttu-id="c31e3-109">ルーティングの参照の詳細については[ASP.NET ルーティング](https://go.microsoft.com/fwlink/?LinkId=184660)と[AspNetRouteIntegration](../../../../docs/framework/wcf/samples/aspnetrouteintegration.md)サンプル。</span><span class="sxs-lookup"><span data-stu-id="c31e3-109">For more information about routing see [ASP.NET Routing](https://go.microsoft.com/fwlink/?LinkId=184660) and the [AspNetRouteIntegration](../../../../docs/framework/wcf/samples/aspnetrouteintegration.md) sample.</span></span>  
  
## <a name="using-systemwebrouting-integration"></a><span data-ttu-id="c31e3-110">System.Web.Routing 統合の使用</span><span class="sxs-lookup"><span data-stu-id="c31e3-110">Using System.Web.Routing Integration</span></span>  
 <span data-ttu-id="c31e3-111"><xref:System.Web.Routing> 統合機能を使用するには、<xref:System.ServiceModel.Activation.ServiceRoute> クラスを使用して 1 つ以上のルートを作成し、Global.asax ファイルでそれらを <xref:System.Web.Routing.RouteTable> に追加します。</span><span class="sxs-lookup"><span data-stu-id="c31e3-111">To use the <xref:System.Web.Routing> integration feature, you use the <xref:System.ServiceModel.Activation.ServiceRoute> class to create one or more routes and add them to the <xref:System.Web.Routing.RouteTable> in a Global.asax file.</span></span> <span data-ttu-id="c31e3-112">これらのルートは、サービスが応答する相対 URI を指定します。</span><span class="sxs-lookup"><span data-stu-id="c31e3-112">These routes specify the relative URIs that the service responds to.</span></span> <span data-ttu-id="c31e3-113">その方法を次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="c31e3-113">The following example shows how to do this.</span></span>  
  
```  
<%@ Application Language="C#" %>  
<%@ Import Namespace="System.Web.Routing" %>  
<%@ Import Namespace="System.ServiceModel.Activation" %>  
<%@ Import Namespace="System.ServiceModel.Web " %>  
  
<script RunAt="server">  
    void Application_Start(object sender, EventArgs e)  
    {  
        RegisterRoutes(RouteTable.Routes);  
    }  
  
    private void RegisterRoutes(RouteCollection routes)  
    {  
        routes.Add(new ServiceRoute("Customers", new WebServiceHostFactory(), typeof(Service)));   
   }  
</script>  
```  
  
 <span data-ttu-id="c31e3-114">これは、Customers で始まる相対 URI が指定されたすべての要求を `Service` サービスにルーティングします。</span><span class="sxs-lookup"><span data-stu-id="c31e3-114">This routes all requests with a relative URI that begins with Customers to the `Service` service.</span></span>  
  
 <span data-ttu-id="c31e3-115">Web.config ファイルでは、次の例に示すように、`System.Web.Routing.UrlRoutingModule` モジュールを追加し、`runAllManagedModulesForAllRequests` 属性を `true` に設定し、`UrlRoutingHandler` ハンドラーを `<system.webServer>` 要素に追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c31e3-115">In your Web.config file you must add the `System.Web.Routing.UrlRoutingModule` module, set the `runAllManagedModulesForAllRequests` attribute to `true`, and add the `UrlRoutingHandler` handler to the `<system.webServer>` element as shown in the following example.</span></span>  
  
```xml  
<system.webServer>  
      <modules runAllManagedModulesForAllRequests="true">  
        <add name="UrlRoutingModule" type="System.Web.Routing.UrlRoutingModule, System.Web, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a" />  
      </modules>  
      <handlers>  
        <add name="UrlRoutingHandler" preCondition="integratedMode" verb="*" path="UrlRouting.axd"/>  
      </handlers>  
    </system.webServer>  
```  
  
 <span data-ttu-id="c31e3-116">これで、ルーティングに必要なモジュールとハンドラーが読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="c31e3-116">This loads a module and handler required for routing.</span></span> <span data-ttu-id="c31e3-117">詳細については、[ルーティング](../../../../docs/framework/wcf/feature-details/routing.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c31e3-117">For more information, see [Routing](../../../../docs/framework/wcf/feature-details/routing.md).</span></span> <span data-ttu-id="c31e3-118">また、次の例に示すように、`aspNetCompatibilityEnabled` 要素で `true` 属性を `<serviceHostingEnvironment>` に設定する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="c31e3-118">You must also set the `aspNetCompatibilityEnabled` attribute to `true` in the `<serviceHostingEnvironment>` element as shown in the following example.</span></span>  
  
```xml  
<system.serviceModel>  
    <serviceHostingEnvironment aspNetCompatibilityEnabled="true"/>  
        <!-- ... -->  
    </system.serviceModel>  
```  
  
 <span data-ttu-id="c31e3-119">次の例に示すように、このサービスを実装するクラスでは、ASP.NET 互換要件を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c31e3-119">The class that implements the service must enable ASP.NET compatibility requirements as shown in the following example.</span></span>  
  
```  
[ServiceContract]  
[AspNetCompatibilityRequirements(RequirementsMode=AspNetCompatibilityRequirementsMode.Allowed)]  
    public class Service  
    {  
        // ...  
    }  
```  
  
## <a name="see-also"></a><span data-ttu-id="c31e3-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="c31e3-120">See Also</span></span>  
 [<span data-ttu-id="c31e3-121">WCF Web HTTP プログラミング モデル</span><span class="sxs-lookup"><span data-stu-id="c31e3-121">WCF Web HTTP Programming Model</span></span>](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)  
 [<span data-ttu-id="c31e3-122">ASP.NET ルーティング</span><span class="sxs-lookup"><span data-stu-id="c31e3-122">ASP.NET Routing</span></span>](https://go.microsoft.com/fwlink/?LinkId=184660)
