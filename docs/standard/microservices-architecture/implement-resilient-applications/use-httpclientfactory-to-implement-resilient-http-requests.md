---
title: HttpClientFactory を使用して回復力の高い HTTP 要求を実装する
description: HttpClientFactory は、自己主張性の強いファクトリであり、アプリケーションに使用する `HttpClient` インスタンスを作成するため、.NET Core 2.1 以降で使用できます。
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 07/03/2018
ms.openlocfilehash: 6fd30a9358ca9c07b2a6e2ec591e4c5d7db54ccb
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "43513214"
---
# <a name="use-httpclientfactory-to-implement-resilient-http-requests"></a><span data-ttu-id="33fb8-103">HttpClientFactory を使用して回復力の高い HTTP 要求を実装する</span><span class="sxs-lookup"><span data-stu-id="33fb8-103">Use HttpClientFactory to implement resilient HTTP requests</span></span>

<span data-ttu-id="33fb8-104">`HttpClientFactory` は、自己主張性の強いファクトリで、アプリケーションに使用する `HttpClient` インスタンスを作成するため、.NET Core 2.1 以降で使用できます。</span><span class="sxs-lookup"><span data-stu-id="33fb8-104">`HttpClientFactory` is an opinionated factory, available since .NET Core 2.1, for creating `HttpClient` instances to be used in your applications.</span></span> 

## <a name="issues-with-the-original-httpclient-class-available-in-net-core"></a><span data-ttu-id="33fb8-105">.NET Core で使用可能な元の HttpClient クラスに関する問題</span><span class="sxs-lookup"><span data-stu-id="33fb8-105">Issues with the original HttpClient class available in .NET Core</span></span>

<span data-ttu-id="33fb8-106">よく知られている元の [HttpClient](https://docs.microsoft.com/dotnet/api/system.net.http.httpclient?view=netstandard-2.0) クラスは、簡単に使用できますが、多くの開発者によって適切に使用されていない場合もあります。</span><span class="sxs-lookup"><span data-stu-id="33fb8-106">The original and well-know [HttpClient](https://docs.microsoft.com/dotnet/api/system.net.http.httpclient?view=netstandard-2.0) class can be easily used, but in some cases, it is not being properly used by many developers.</span></span> 

<span data-ttu-id="33fb8-107">1 つ目の問題は、このクラスは破棄可能ですが、`HttpClient` オブジェクトを破棄しても、基になるソケットがすぐに解放されず、'ソケットの枯渇' という重大な問題が発生する場合があるため、`using` ステートメントで使用するのは最適な選択ではないということです。</span><span class="sxs-lookup"><span data-stu-id="33fb8-107">As a first issue, while this class is disposable, using it with the `using` statement is not the best choice because even when you dispose `HttpClient` object, the underlying socket is not immediately released and can cause a serious issue named ‘sockets exhaustion’.</span></span> <span data-ttu-id="33fb8-108">この問題の詳細については、ブログ記事「[You're using HttpClient wrong and it is destabilizing your software](https://aspnetmonsters.com/2016/08/2016-08-27-httpclientwrong/)」 (HttpClient の誤った使い方がソフトウェアを不安定にする) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="33fb8-108">For more information about this issue, see [You're using HttpClient wrong and it is destabilizing your software](https://aspnetmonsters.com/2016/08/2016-08-27-httpclientwrong/) blog post.</span></span>

<span data-ttu-id="33fb8-109">そのため、`HttpClient` は一度インスタンス化されたら、アプリケーションの有効期間にわたって再利用されることを目的としています。</span><span class="sxs-lookup"><span data-stu-id="33fb8-109">Therefore, `HttpClient` is intended to be instantiated once and reused throughout the life of an application.</span></span> <span data-ttu-id="33fb8-110">すべての要求に対して `HttpClient` クラスをインスタンス化すると、高負荷の下で使用可能なソケットの数が枯渇してしまいます。</span><span class="sxs-lookup"><span data-stu-id="33fb8-110">Instantiating an `HttpClient` class for every request will exhaust the number of sockets available under heavy loads.</span></span> <span data-ttu-id="33fb8-111">この問題により、`SocketException` エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="33fb8-111">That issue will result in `SocketException` errors.</span></span> <span data-ttu-id="33fb8-112">この問題を解決するために可能なアプローチは、HttpClient クライアントの使用に関するこの [Microsoft の記事](https://docs.microsoft.com/en-us/dotnet/csharp/tutorials/console-webapiclient)で説明されているように、`HttpClient` オブジェクトをシングルトンまたは静的として作成することに基づいています。</span><span class="sxs-lookup"><span data-stu-id="33fb8-112">Possible approaches to solve that problem are based on the creation of the `HttpClient` object as singleton or static, as explained in this [Microsoft article on HttpClient usage](https://docs.microsoft.com/en-us/dotnet/csharp/tutorials/console-webapiclient).</span></span> 

<span data-ttu-id="33fb8-113">しかし、`HttpClient` には、シングルトンまたは静的オブジェクトとして使用した場合に発生する可能性がある 2 つ目の問題があります。</span><span class="sxs-lookup"><span data-stu-id="33fb8-113">But there’s a second issue with `HttpClient` that you can have when you use it as singleton or static object.</span></span> <span data-ttu-id="33fb8-114">この場合、[.NET Core GitHub リポジトリでこの問題](https://github.com/dotnet/corefx/issues/11224)について説明されているように、シングルトンまたは静的 `HttpClient` は、DNS の変更を尊重しません。</span><span class="sxs-lookup"><span data-stu-id="33fb8-114">In this case, a singleton or static `HttpClient` doesn't respect DNS changes, as explained in this [issue at the .NET Core GitHub repo](https://github.com/dotnet/corefx/issues/11224).</span></span> 

<span data-ttu-id="33fb8-115">これらの問題に対処し、`HttpClient` インスタンスの管理を容易にするため、.NET Core 2.1 では、新しい `HttpClientFactory` が提供されています。これは、Polly を統合することで、回復力のある HTTP 呼び出しを実装するためにも使用できます。</span><span class="sxs-lookup"><span data-stu-id="33fb8-115">To address those mentioned issues and make the management of `HttpClient` instances easier, .NET Core 2.1 offers a new `HttpClientFactory` that can also be used to implement resilient HTTP calls by integrating Polly with it.</span></span>   

## <a name="what-is-httpclientfactory"></a><span data-ttu-id="33fb8-116">HttpClientFactory とは</span><span class="sxs-lookup"><span data-stu-id="33fb8-116">What is HttpClientFactory</span></span>

<span data-ttu-id="33fb8-117">`HttpClientFactory` は次の目的のために設計されています。</span><span class="sxs-lookup"><span data-stu-id="33fb8-117">`HttpClientFactory` is designed to:</span></span>

- <span data-ttu-id="33fb8-118">論理 HttpClients の名前付けと構成を一元化します。</span><span class="sxs-lookup"><span data-stu-id="33fb8-118">Provide a central location for naming and configuring logical HttpClients.</span></span> <span data-ttu-id="33fb8-119">たとえば、特定のマイクロサービスにアクセスするために事前に構成されているクライアント (サービス エージェント) を構成できます。</span><span class="sxs-lookup"><span data-stu-id="33fb8-119">For example, you may configure a client (Service Agent) that is pre-configured to access a specific microservice.</span></span>
- <span data-ttu-id="33fb8-120">`HttpClient` でのハンドラーのデリゲートにより送信ミドルウェアの概念を体系化し、Polly ベースのミドルウェアを実装して、回復性のための Polly のポリシーを利用します。</span><span class="sxs-lookup"><span data-stu-id="33fb8-120">Codify the concept of outgoing middleware via delegating handlers in `HttpClient` and implementing Polly-based middleware to take advantage of Polly’s policies for resiliency.</span></span>
- <span data-ttu-id="33fb8-121">`HttpClient` は既に、送信 HTTP 要求用にリンクできるハンドラーのデリゲートの概念を備えています。</span><span class="sxs-lookup"><span data-stu-id="33fb8-121">`HttpClient` already has the concept of delegating handlers that could be linked together for outgoing HTTP requests.</span></span> <span data-ttu-id="33fb8-122">ファクトリに http クライアントを登録できるほか、再試行、サーキット ブレーカーなどに Polly ポリシーが使えるようになる Polly ハンドラーを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="33fb8-122">You register http clients into the factory plus you can use a Polly handler that allows Polly policies to be used for Retry, CircuitBreakers, etc.</span></span>
- <span data-ttu-id="33fb8-123">HttpClientMessageHandler の有効期間を管理して、`HttpClient` の有効期間を自分で管理する際に発生する可能性がある上記の問題を回避します。</span><span class="sxs-lookup"><span data-stu-id="33fb8-123">Manage the lifetime of HttpClientMessageHandlers to avoid the mentioned problems/issues that can occur when managing `HttpClient` lifetimes yourself.</span></span> 

## <a name="multiple-ways-to-use-httpclientfactory"></a><span data-ttu-id="33fb8-124">HttpClientFactory を使用する複数の方法</span><span class="sxs-lookup"><span data-stu-id="33fb8-124">Multiple ways to use HttpClientFactory</span></span>

<span data-ttu-id="33fb8-125">アプリケーションで `HttpClientFactory` を使用するには、複数の方法があります。</span><span class="sxs-lookup"><span data-stu-id="33fb8-125">There are several ways that you can use `HttpClientFactory` in your application:</span></span>

- <span data-ttu-id="33fb8-126">`HttpClientFactory` を直接使用する</span><span class="sxs-lookup"><span data-stu-id="33fb8-126">Use `HttpClientFactory` Directly</span></span>
- <span data-ttu-id="33fb8-127">名前付きクライアントを使用する</span><span class="sxs-lookup"><span data-stu-id="33fb8-127">Use Named Clients</span></span>
- <span data-ttu-id="33fb8-128">型指定されたクライアントを使用する</span><span class="sxs-lookup"><span data-stu-id="33fb8-128">Use Typed Clients</span></span>
- <span data-ttu-id="33fb8-129">生成されたクライアントを使用する</span><span class="sxs-lookup"><span data-stu-id="33fb8-129">Use Generated Clients</span></span>

<span data-ttu-id="33fb8-130">説明を簡潔にするため、このガイダンスでは、型指定されたクライアント (サービス エージェント パターン) を使用するための `HttpClientFactory` を使用する最も体系化されている方法を示します。ただし、すべてのオプションは文書化されており、現在、[HttpClientFactory の使用方法を説明しているこの記事](https://docs.microsoft.com/aspnet/core/fundamentals/http-requests?#consumption-patterns)に一覧があります。</span><span class="sxs-lookup"><span data-stu-id="33fb8-130">For the sake of brevity, this guidance shows the most structured way to use `HttpClientFactory` that is to use Typed Clients (Service Agent pattern), but all options are documented and are currently listed in this [article covering HttpClientFactory usage](https://docs.microsoft.com/aspnet/core/fundamentals/http-requests?#consumption-patterns).</span></span>  

## <a name="how-to-use-typed-clients-with-httpclientfactory"></a><span data-ttu-id="33fb8-131">HttpClientFactory で型指定されたクライアントを使用する方法</span><span class="sxs-lookup"><span data-stu-id="33fb8-131">How to use Typed Clients with HttpClientFactory</span></span>

<span data-ttu-id="33fb8-132">次の図は、HttpClientFactory で型指定されたクライアントを使用する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="33fb8-132">The following diagram shows how Typed Clients are used with HttpClientFactory.</span></span>

![挿入された ClientService を使用する MVC コントローラーが記された図。HttpClientFactory と Polly のポリシーにより構成された HttpClient を内部的に使用しています。](./media/image3.5.png)

<span data-ttu-id="33fb8-134">**図 10-4**.</span><span class="sxs-lookup"><span data-stu-id="33fb8-134">**Figure 10-4**.</span></span> <span data-ttu-id="33fb8-135">型指定されたクライアント クラスで `HttpClientFactory` を使用する</span><span class="sxs-lookup"><span data-stu-id="33fb8-135">Using `HttpClientFactory`with Typed Client classes.</span></span>

<span data-ttu-id="33fb8-136">最初に、アプリケーションで `HttpClientFactory` をセットアップします。</span><span class="sxs-lookup"><span data-stu-id="33fb8-136">First, setup `HttpClientFactory` in your application.</span></span> <span data-ttu-id="33fb8-137">`IServiceCollection` の `AddHttpClient()` 拡張メソッドが含まれる `Microsoft.Extensions.Http` に参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="33fb8-137">Add a reference to the `Microsoft.Extensions.Http` package which includes the `AddHttpClient()` extension method for `IServiceCollection`.</span></span> <span data-ttu-id="33fb8-138">この拡張メソッドは、インターフェイス `IHttpClientFactory` のシングルトンとして使用される `DefaultHttpClientFactory` を登録します。</span><span class="sxs-lookup"><span data-stu-id="33fb8-138">This extension method registers the `DefaultHttpClientFactory` to be used as a singleton for the interface `IHttpClientFactory`.</span></span> <span data-ttu-id="33fb8-139">これは `HttpMessageHandlerBuilder` の一時的な構成を定義します。</span><span class="sxs-lookup"><span data-stu-id="33fb8-139">It defines a transient configuration for the `HttpMessageHandlerBuilder`.</span></span> <span data-ttu-id="33fb8-140">プールから取得されたこのメッセージ ハンドラー (`HttpMessageHandler` オブジェクト) は、ファクトリから返された `HttpClient` によって使用されます。</span><span class="sxs-lookup"><span data-stu-id="33fb8-140">This message handler (`HttpMessageHandler` object), taken from a pool, is used by the `HttpClient` returned from the factory.</span></span>

<span data-ttu-id="33fb8-141">次のコードで、`AddHttpClient()` を使用して、`HttpClient` を使用する必要がある型指定されたクライアント (エージェント サービス) を登録する方法を確認できます。</span><span class="sxs-lookup"><span data-stu-id="33fb8-141">In the next code, you can see how `AddHttpClient()` can be used to register Typed Clients (Service Agents) that need to use `HttpClient`.</span></span>

```csharp
// Startup.cs
//Add http client services at ConfigureServices(IServiceCollection services) 
services.AddHttpClient<ICatalogService, CatalogService>();
services.AddHttpClient<IBasketService, BasketService>();
services.AddHttpClient<IOrderingService, OrderingService>();
```

<span data-ttu-id="33fb8-142">AddHttpClient() を使用して型指定されたクライアント クラスを追加するだけで、そのコンストラクターを通じてクラスに挿入される `HttpClient` オブジェクトを使用する場合には常に、その `HttpClient` オブジェクトで提供されたすべての構成とポリシーが使用されるようになります。</span><span class="sxs-lookup"><span data-stu-id="33fb8-142">Just by adding your typed client classes with AddHttpClient(), whenever you use the `HttpClient` object that will be injected to your class through its constructor, that `HttpClient` object will be using all the configuration and policies provided.</span></span> <span data-ttu-id="33fb8-143">以降のセクションでは、Polly の再試行またはサーキット ブレーカーのような、これらのポリシーを確認します。</span><span class="sxs-lookup"><span data-stu-id="33fb8-143">In the next sections, you will see those policies like Polly’s retries or circuit-breakers.</span></span>

### <a name="httpclient-lifetimes"></a><span data-ttu-id="33fb8-144">HttpClient の有効期間</span><span class="sxs-lookup"><span data-stu-id="33fb8-144">HttpClient lifetimes</span></span>

<span data-ttu-id="33fb8-145">IHttpClientFactory から `HttpClient` オブジェクトを取得するたび、`HttpClient` の新しいインスタンスが返されます。</span><span class="sxs-lookup"><span data-stu-id="33fb8-145">Each time you get an `HttpClient` object from IHttpClientFactory, a new instance of an `HttpClient` is returned.</span></span> <span data-ttu-id="33fb8-146">型指定されたクライアントの名前ごとに HttpMessageHandler\*\* があります。</span><span class="sxs-lookup"><span data-stu-id="33fb8-146">There will be an HttpMessageHandler\*\* per named of typed client.</span></span> <span data-ttu-id="33fb8-147">`HttpClientFactory` は、リソースの消費量を減らすためにファクトリによって作成された HttpMessageHandler インスタンスをプールします。</span><span class="sxs-lookup"><span data-stu-id="33fb8-147">I`HttpClientFactory` will pool the HttpMessageHandler instances created by the factory to reduce resource consumption.</span></span> <span data-ttu-id="33fb8-148">新しい `HttpClient` インスタンスを作成するとき、プールの HttpMessageHandler インスタンスの有効期間が切れていない場合はそれを再利用できます。</span><span class="sxs-lookup"><span data-stu-id="33fb8-148">An HttpMessageHandler instance may be reused from the pool when creating a new `HttpClient` instance if its lifetime hasn't expired.</span></span>

<span data-ttu-id="33fb8-149">通常各ハンドラーは基になる HTTP 接続を独自に管理しており、必要以上に多くのハンドラーを作成すると接続が遅延する可能性があるため、ハンドラーをプールするのは望ましい方法です。</span><span class="sxs-lookup"><span data-stu-id="33fb8-149">Pooling of handlers is desirable as each handler typically manages its own underlying HTTP connections; creating more handlers than necessary can result in connection delays.</span></span> <span data-ttu-id="33fb8-150">また、一部のハンドラーは接続を無期限に開いており、DNS の変更にハンドラーが対応できないことがあります。</span><span class="sxs-lookup"><span data-stu-id="33fb8-150">Some handlers also keep connections open indefinitely, which can prevent the handler from reacting to DNS changes.</span></span>

<span data-ttu-id="33fb8-151">プール内の HttpMessageHandler オブジェクトには、有効期間があります。この有効期間は、プール内の HttpMessageHandler インスタンスを再利用できる期間です。</span><span class="sxs-lookup"><span data-stu-id="33fb8-151">The HttpMessageHandler objects in the pool have a lifetime that is the length of time that an HttpMessageHandler instance in the pool can be reused.</span></span> <span data-ttu-id="33fb8-152">既定値は 2 分ですが、名前付きクライアントまたは型指定されたクライアントごとにオーバーライドできます。</span><span class="sxs-lookup"><span data-stu-id="33fb8-152">The default value is two minutes, but it can be overridden per named or typed client basis.</span></span> <span data-ttu-id="33fb8-153">オーバーライドするには、次のコードに示すように、クライアントを作成するときに返される IHttpClientBuilder で SetHandlerLifetime() を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="33fb8-153">To override it, call SetHandlerLifetime() on the IHttpClientBuilder that is returned when creating the client, as shown in the following code.</span></span>

```csharp
//Set 5 min as the lifetime for the HttpMessageHandler objects in the pool used for the Catalog Typed Client 
services.AddHttpClient<ICatalogService, CatalogService>()
                 .SetHandlerLifetime(TimeSpan.FromMinutes(5));  
```

<span data-ttu-id="33fb8-154">型指定されたクライアントまたは名前付きクライアントには、それぞれ独自の構成済みハンドラーの有効期間の値を設定できます。</span><span class="sxs-lookup"><span data-stu-id="33fb8-154">Each typed client or named client can have its own configured handler lifetime value.</span></span> <span data-ttu-id="33fb8-155">ハンドラーの有効期限を無効にするには、有効期間を InfiniteTimeSpan に設定します。</span><span class="sxs-lookup"><span data-stu-id="33fb8-155">Set the lifetime to InfiniteTimeSpan to disable handler expiry.</span></span>

### <a name="implement-your-typed-client-classes-that-use-the-injected-and-configured-httpclient"></a><span data-ttu-id="33fb8-156">挿入された構成済みの HttpClient を使用する、型指定されたクライアント クラスを実装する</span><span class="sxs-lookup"><span data-stu-id="33fb8-156">Implement your Typed Client classes that use the injected and configured HttpClient</span></span>

<span data-ttu-id="33fb8-157">前の手順では、型指定されたクライアント クラス (サンプル コードにある、‘BasketService’、‘CatalogService’、‘OrderingService’ のようなクラスなど) が定義されている必要がありました。型指定されたクライアントは、(そのコンストラクターを通じて挿入された) `HttpClient` オブジェクトを受け取り、それを使用していくつかのリモート HTTP サービスを呼び出すクラスです。</span><span class="sxs-lookup"><span data-stu-id="33fb8-157">As a previous step, you need to have your Typed Client classes defined, such as the classes in the sample code, like ‘BasketService’, ‘CatalogService’, ‘OrderingService’, etc. – A typed client is a class that accepts an `HttpClient` object (injected through its constructor) and uses it to call some remote HTTP service.</span></span> <span data-ttu-id="33fb8-158">例:</span><span class="sxs-lookup"><span data-stu-id="33fb8-158">For example:</span></span>

```csharp
public class CatalogService : ICatalogService
{
    private readonly HttpClient _httpClient;
    private readonly string _remoteServiceBaseUrl;

    public CatalogService(HttpClient httpClient)
    {
        _httpClient = httpClient;
    }

    public async Task<Catalog> GetCatalogItems(int page, int take, 
                                               int? brand, int? type)
    {
        var uri = API.Catalog.GetAllCatalogItems(_remoteServiceBaseUrl, 
                                                 page, take, brand, type);

        var responseString = await _httpClient.GetStringAsync(uri);

        var catalog = JsonConvert.DeserializeObject<Catalog>(responseString);
        return catalog;
    }
}
```

<span data-ttu-id="33fb8-159">型指定されたクライアント (この例では CatalogService) は、依存関係の挿入 (DI) によってアクティブ化されます。つまり HttpClient だけでなく、そのコンストラクター内に登録されている任意のサービスを受け取ることができます。</span><span class="sxs-lookup"><span data-stu-id="33fb8-159">The typed client (CatalogService in the example) is activated by DI (Dependency Injection), meaning that it can accept any registered service in its constructor, in addition to HttpClient.</span></span>

<span data-ttu-id="33fb8-160">型指定されたクライアントは、実際には、一時的なオブジェクトです。つまり、新しいインスタンスは必要になるたびに作成され、新しい `HttpClient` インスタンスが構築されるたびにそれを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="33fb8-160">A typed client is, effectively, a transient object, meaning that a new instance is created each time one is needed and it will receive a new `HttpClient` instance each time it is constructed.</span></span> <span data-ttu-id="33fb8-161">ただし、プール内の HttpMessageHandler オブジェクトは、複数の Http 要求で再利用されるオブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="33fb8-161">However, the HttpMessageHandler objects in the pool are the objects that are reused by multiple Http requests.</span></span>

### <a name="use-your-typed-client-classes"></a><span data-ttu-id="33fb8-162">型指定されたクライアント クラスを使用する</span><span class="sxs-lookup"><span data-stu-id="33fb8-162">Use your Typed Client classes</span></span>

<span data-ttu-id="33fb8-163">最後に、型クラスを実装し、それを AddHttpClient() に登録すると、DI によって挿入されたサービスがある任意の場所でそれを使用できます。たとえば、次の eShopOnContainers のコードのように、任意の Razor ページ コードや、MVC Web アプリの任意のコントローラーで使用できます。</span><span class="sxs-lookup"><span data-stu-id="33fb8-163">Finally, once you have your type classes implemented and have them registered with AddHttpClient(), you can use it anywhere you can have services injected by DI, for example in any Razor page code or any controller of an MVC web app, like in the following code from eShopOnContainers.</span></span>

```csharp
namespace Microsoft.eShopOnContainers.WebMVC.Controllers
{
    public class CatalogController : Controller
    {
        private ICatalogService _catalogSvc;

        public CatalogController(ICatalogService catalogSvc) => 
                                                           _catalogSvc = catalogSvc;

        public async Task<IActionResult> Index(int? BrandFilterApplied, 
                                               int? TypesFilterApplied, 
                                               int? page, 
                                               [FromQuery]string errorMsg)
        {
            var itemsPage = 10;
            var catalog = await _catalogSvc.GetCatalogItems(page ?? 0, 
                                                            itemsPage, 
                                                            BrandFilterApplied, 
                                                            TypesFilterApplied);
            //… Additional code
        }

        }
}
```

<span data-ttu-id="33fb8-164">この時点までは、示されているコードは、通常の Http 要求を実行するだけですが、次のセクションでは、不思議なことが起こります。ポリシーを追加して、ハンドラーを登録済みの型指定されているクライアントにデリゲートするだけで、`HttpClient` によって実行されるすべての Http 要求が、指数バックオフを含む再試行、サーキット ブレーカー、またはその他の任意のカスタム デリゲート ハンドラーなど、回復力のあるポリシーを考慮して、追加のセキュリティ機能 (認証トークンの使用など) やその他のカスタム機能を実装するようになります。</span><span class="sxs-lookup"><span data-stu-id="33fb8-164">Until this point, the code shown is just performing regular Http requests, but the ‘magic’ comes in the following sections where, just by adding policies and delegating handlers to your registered typed clients, all the Http requests to be done by `HttpClient` will behave taking into account resilient policies such as retries with exponential backoff, circuit breakers, or any other custom delegating handler to implement additional security features, like using auth tokens, or any other custom feature.</span></span> 


## <a name="additional-resources"></a><span data-ttu-id="33fb8-165">その他の技術情報</span><span class="sxs-lookup"><span data-stu-id="33fb8-165">Additional resources</span></span>

-   <span data-ttu-id="33fb8-166">**.NET Core 2.1 で HttpClientFactory を使用する**
    [*https://docs.microsoft.com/en-us/aspnet/core/fundamentals/http-requests?view=aspnetcore-2.1*](https://docs.microsoft.com/en-us/aspnet/core/fundamentals/http-requests?view=aspnetcore-2.1)</span><span class="sxs-lookup"><span data-stu-id="33fb8-166">**Using HttpClientFactory in .NET Core 2.1**
[*https://docs.microsoft.com/en-us/aspnet/core/fundamentals/http-requests?view=aspnetcore-2.1*](https://docs.microsoft.com/en-us/aspnet/core/fundamentals/http-requests?view=aspnetcore-2.1)</span></span>


-   <span data-ttu-id="33fb8-167">**HttpClientFactory GitHub リポジトリ**</span><span class="sxs-lookup"><span data-stu-id="33fb8-167">**HttpClientFactory GitHub repo**</span></span>

    [*https://github.com/aspnet/HttpClientFactory*](https://github.com/aspnet/HttpClientFactory)



>[!div class="step-by-step"]
<span data-ttu-id="33fb8-168">[前へ] (explore-custom-http-call-retries-exponential-backoff.md) [次へ] (implement-http-call-retries-exponential-backoff-polly.md)</span><span class="sxs-lookup"><span data-stu-id="33fb8-168">[Previous] (explore-custom-http-call-retries-exponential-backoff.md) [Next] (implement-http-call-retries-exponential-backoff-polly.md)</span></span>
