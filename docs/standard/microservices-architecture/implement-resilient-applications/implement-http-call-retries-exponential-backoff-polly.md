---
title: Polly で指数バックオフを含む HTTP 呼び出しの再試行を実装する
description: HTTP エラーを Polly と HttpClientFactory で処理する方法について説明します
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 06/10/2018
ms.openlocfilehash: 78de1440721e83459e455f5c31d10e52a1d3b1b6
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2018
ms.locfileid: "53143988"
---
# <a name="implement-http-call-retries-with-exponential-backoff-with-httpclientfactory-and-polly-policies"></a><span data-ttu-id="6db08-103">HttpClientFactory ポリシーと Polly ポリシーで指数バックオフを含む HTTP 呼び出しの再試行を実装する</span><span class="sxs-lookup"><span data-stu-id="6db08-103">Implement HTTP call retries with exponential backoff with HttpClientFactory and Polly policies</span></span>

<span data-ttu-id="6db08-104">指数のバックオフでの再試行のためのアプローチとしては、オープン ソースである [Polly ライブラリ](https://github.com/App-vNext/Polly)のような高度な .NET ライブラリを利用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6db08-104">The recommended approach for retries with exponential backoff is to take advantage of more advanced .NET libraries like the open-source [Polly library](https://github.com/App-vNext/Polly).</span></span>

<span data-ttu-id="6db08-105">Polly とは、回復機能と一時的な障害処理の機能を提供する .NET ライブラリです。</span><span class="sxs-lookup"><span data-stu-id="6db08-105">Polly is a .NET library that provides resilience and transient-fault handling capabilities.</span></span> <span data-ttu-id="6db08-106">このような機能は、再試行、遮断器、バルクヘッド分離、タイムアウト、フォールバックなどの Polly ポリシーを適用することで実装できます。</span><span class="sxs-lookup"><span data-stu-id="6db08-106">You can implement those capabilities by applying Polly policies such as Retry, Circuit Breaker, Bulkhead Isolation, Timeout, and Fallback.</span></span> <span data-ttu-id="6db08-107">Polly は .NET 4.x および .NET Standard ライブラリ 1.0 (.NET Core をサポート) を対象にしています。</span><span class="sxs-lookup"><span data-stu-id="6db08-107">Polly targets .NET 4.x and the .NET Standard Library 1.0 (which supports .NET Core).</span></span>

<span data-ttu-id="6db08-108">ただし、HttpClient を含む独自のコードで Polly のライブラリを使用することは非常に複雑になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6db08-108">However, using Polly’s library with your own custom code with HttpClient can be significantly complex.</span></span> <span data-ttu-id="6db08-109">eShopOnContainers の最初のバージョンでは、[ResilientHttpClient ビルディングブロック](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/BuildingBlocks/Resilience/Resilience.Http/ResilientHttpClient.cs)が Polly を基盤としていました。</span><span class="sxs-lookup"><span data-stu-id="6db08-109">In the original version of eShopOnContainers, there was a [ResilientHttpClient building-block](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/BuildingBlocks/Resilience/Resilience.Http/ResilientHttpClient.cs) based on Polly.</span></span> <span data-ttu-id="6db08-110">しかしながら、HttpClientFactory が公開され、回復力のある HTTP 通信が簡単に実装できるようになり、eShopOnContainers ではビルディングブロックが非推奨になりました。</span><span class="sxs-lookup"><span data-stu-id="6db08-110">But with the release of HttpClientFactory, resilient Http communication has become much simpler to implement, so that building-block was deprecated from eShopOnContainers.</span></span> 

<span data-ttu-id="6db08-111">次の手順では、前のセクションで説明した、HttpClientFactory に統合された Polly で HTTP 再試行を使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="6db08-111">The following steps show how you can use Http retries with Polly integrated into HttpClientFactory, which is explained in the previous section.</span></span>

<span data-ttu-id="6db08-112">**ASP.NET Core 2.1 パッケージを参照する**</span><span class="sxs-lookup"><span data-stu-id="6db08-112">**Reference the ASP.NET Core 2.1 packages**</span></span>

<span data-ttu-id="6db08-113">プロジェクトで NuGet からの ASP.NET Core 2.1 を使用する必要がある場合、</span><span class="sxs-lookup"><span data-stu-id="6db08-113">Your project has to be using the ASP.NET Core 2.1 packages from NuGet.</span></span> <span data-ttu-id="6db08-114">通常、`AspNetCore` メタパッケージと拡張パッケージ `Microsoft.Extensions.Http.Polly` が必要になります。</span><span class="sxs-lookup"><span data-stu-id="6db08-114">You typically need the `AspNetCore` metapackage, and the extension package `Microsoft.Extensions.Http.Polly`.</span></span>

<span data-ttu-id="6db08-115">**Startup で、Polly の再試行ポリシーでクライアントを構成する**</span><span class="sxs-lookup"><span data-stu-id="6db08-115">**Configure a client with Polly’s Retry policy, in Startup**</span></span>

<span data-ttu-id="6db08-116">前のセクションで示したように、標準の Startup.ConfigureServices(...) メソッドで、名前または型が指定された HttpClient 構成を定義する必要がありますが、今後は以下のように、指数バックオフを含む HTTP 再試行のポリシーを指定し、増分コードを追加します。</span><span class="sxs-lookup"><span data-stu-id="6db08-116">As shown in previous sections, you need to define a named or typed client HttpClient configuration in your standard Startup.ConfigureServices(...) method, but now, you add incremental code specifying the policy for the Http retries with exponential backoff, as below:</span></span>

```csharp
//ConfigureServices()  - Startup.cs
services.AddHttpClient<IBasketService, BasketService>()
        .SetHandlerLifetime(TimeSpan.FromMinutes(5))  //Set lifetime to five minutes
        .AddPolicyHandler(GetRetryPolicy());
```

<span data-ttu-id="6db08-117">**AddPolicyHandler()** メソッドは、使用する `HttpClient` オブジェクトにポリシーを追加します。</span><span class="sxs-lookup"><span data-stu-id="6db08-117">The **AddPolicyHandler()** method is what adds policies to the `HttpClient` objects you will use.</span></span> <span data-ttu-id="6db08-118">この場合、指数バックオフを含む HTTP 再試行に対して Polly のポリシーが追加されます。</span><span class="sxs-lookup"><span data-stu-id="6db08-118">In this case, it is adding a Polly’s policy for Http Retries with exponential backoff.</span></span>

<span data-ttu-id="6db08-119">手法のモジュール性を高める目的で、次のコードのように、ConfigureServices() メソッド内の個別メソッドに HTTP 再試行ポリシーを定義できます。</span><span class="sxs-lookup"><span data-stu-id="6db08-119">In order to have a more modular approach, the Http Retry Policy can be defined in a separate method within the ConfigureServices() method, as the following code.</span></span>

```csharp
static IAsyncPolicy<HttpResponseMessage> GetRetryPolicy()
{
    return HttpPolicyExtensions
        .HandleTransientHttpError()
        .OrResult(msg => msg.StatusCode == System.Net.HttpStatusCode.NotFound)
        .WaitAndRetryAsync(6, retryAttempt => TimeSpan.FromSeconds(Math.Pow(2,
                                                                    retryAttempt)));
}
```

<span data-ttu-id="6db08-120">Polly では、再試行回数を指定した再試行ポリシー、指数バックオフの構成、HTTP 例外が発生した場合に実行するアクション (エラーの記録など) を定義できます。</span><span class="sxs-lookup"><span data-stu-id="6db08-120">With Polly, you can define a Retry policy with the number of retries, the exponential backoff configuration, and the actions to take when there is an HTTP exception, such as logging the error.</span></span> <span data-ttu-id="6db08-121">上記のコードでは、指数関数的再試行で (最初は 2 秒) 6 回試すようにポリシーが構成されています。</span><span class="sxs-lookup"><span data-stu-id="6db08-121">In this case, the policy is configured to try six times with an exponential retry, starting at two seconds.</span></span> 

<span data-ttu-id="6db08-122">つまり、6 回試すとき、再試行間の秒数が指数関数的に後退します (最初は 2 秒)。</span><span class="sxs-lookup"><span data-stu-id="6db08-122">so it will try six times and the seconds between each retry will be exponential, starting on two seconds.</span></span>

### <a name="adding-a-jitter-strategy-to-the-retry-policy"></a><span data-ttu-id="6db08-123">再試行ポリシーにジッタ方式を追加する</span><span class="sxs-lookup"><span data-stu-id="6db08-123">Adding a jitter strategy to the retry policy</span></span>

<span data-ttu-id="6db08-124">通常の再試行ポリシーは、コンカレンシーやスケーラビリティが高い場合や、高競合状態下でシステムに影響を及ぼすことがあります。</span><span class="sxs-lookup"><span data-stu-id="6db08-124">A regular Retry policy can impact your system in cases of high concurrency and scalability and under high contention.</span></span> <span data-ttu-id="6db08-125">部分的な停止の場合に多くのクライアントから来る同様の再試行のピークを乗り越えるための賢い回避策は、ジッタ方式を再試行アルゴリズムまたはポリシーに追加することです。</span><span class="sxs-lookup"><span data-stu-id="6db08-125">To overcome peaks of similar retries coming from many clients in case of partial outages, a good workaround is to add a jitter strategy to the retry algorithm/policy.</span></span> <span data-ttu-id="6db08-126">これにより、急増するバックオフにランダム性を加えることで、エンドツーエンド システム全体のパフォーマンスを向上できます。</span><span class="sxs-lookup"><span data-stu-id="6db08-126">This can improve the overall performance of the end-to-end system by adding randomness to the exponential backoff.</span></span> <span data-ttu-id="6db08-127">こうすれば、問題が発生した際のスパイクを分散できます。</span><span class="sxs-lookup"><span data-stu-id="6db08-127">This spreads out the spikes when issues arise.</span></span> <span data-ttu-id="6db08-128">平易な Polly ポリシーを使用する場合、ジッタを実装するコードは次の例のようになります。</span><span class="sxs-lookup"><span data-stu-id="6db08-128">When you use a plain Polly policy, code to implement jitter could look like the following example:</span></span>

```csharp
Random jitterer = new Random(); 
Policy
  .Handle<HttpResponseException>() // etc
  .WaitAndRetry(5,    // exponential back-off plus some jitter
      retryAttempt => TimeSpan.FromSeconds(Math.Pow(2, retryAttempt))  
                    + TimeSpan.FromMilliseconds(jitterer.Next(0, 100)) 
  );
```

## <a name="additional-resources"></a><span data-ttu-id="6db08-129">その他の技術情報</span><span class="sxs-lookup"><span data-stu-id="6db08-129">Additional resources</span></span>

-   <span data-ttu-id="6db08-130">**再試行パターン**
    [*https://docs.microsoft.com/azure/architecture/patterns/retry*](https://docs.microsoft.com/azure/architecture/patterns/retry)</span><span class="sxs-lookup"><span data-stu-id="6db08-130">**Retry pattern**
[*https://docs.microsoft.com/azure/architecture/patterns/retry*](https://docs.microsoft.com/azure/architecture/patterns/retry)</span></span>

-   <span data-ttu-id="6db08-131">**Polly と HttpClientFactory**
    [*https://github.com/App-vNext/Polly/wiki/Polly-and-HttpClientFactory*](https://github.com/App-vNext/Polly/wiki/Polly-and-HttpClientFactory)</span><span class="sxs-lookup"><span data-stu-id="6db08-131">**Polly and HttpClientFactory**
[*https://github.com/App-vNext/Polly/wiki/Polly-and-HttpClientFactory*](https://github.com/App-vNext/Polly/wiki/Polly-and-HttpClientFactory)</span></span>

-   <span data-ttu-id="6db08-132">**Polly (.NET の復元および一時的な障害処理ライブラリ)**</span><span class="sxs-lookup"><span data-stu-id="6db08-132">**Polly (.NET resilience and transient-fault-handling library)**</span></span>

    [*https://github.com/App-vNext/Polly*](https://github.com/App-vNext/Polly)

-   <span data-ttu-id="6db08-133">**Marc Brooker.ジッタ: ランダム性を使って状況を改善する**</span><span class="sxs-lookup"><span data-stu-id="6db08-133">**Marc Brooker. Jitter: Making Things Better With Randomness**</span></span>

    [*https://brooker.co.za/blog/2015/03/21/backoff.html*](https://brooker.co.za/blog/2015/03/21/backoff.html)

>[!div class="step-by-step"]
><span data-ttu-id="6db08-134">[前へ](explore-custom-http-call-retries-exponential-backoff.md)
>[次へ](implement-circuit-breaker-pattern.md)</span><span class="sxs-lookup"><span data-stu-id="6db08-134">[Previous](explore-custom-http-call-retries-exponential-backoff.md)
[Next](implement-circuit-breaker-pattern.md)</span></span>