---
title: 回復力の高い Entity Framework Core SQL 接続を実装する
description: コンテナー化された .NET アプリケーションの .NET マイクロサービス アーキテクチャ | 回復力の高い Entity Framework Core SQL 接続を実装する。 この手法は、クラウドで Azure SQL Database を使用する場合に特に重要です。
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 06/08/2018
ms.openlocfilehash: 59db9cdb894f76f54e77732be47dc6140a594121
ms.sourcegitcommit: 2350a091ef6459f0fcfd894301242400374d8558
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/21/2018
ms.locfileid: "46561514"
---
# <a name="implement-resilient-entity-framework-core-sql-connections"></a><span data-ttu-id="78ac6-104">回復力の高い Entity Framework Core SQL 接続を実装する</span><span class="sxs-lookup"><span data-stu-id="78ac6-104">Implement resilient Entity Framework Core SQL connections</span></span>

<span data-ttu-id="78ac6-105">Azure SQL DB の場合、Entity Framework Core に内部データベース接続の復元機能と再試行ロジックが既に用意されています。</span><span class="sxs-lookup"><span data-stu-id="78ac6-105">For Azure SQL DB, Entity Framework Core already provides internal database connection resiliency and retry logic.</span></span> <span data-ttu-id="78ac6-106">ただし、[回復力のある EF Core 接続](https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency)を使用する場合は、各 DbContext 接続に対して Entity Framework 実行戦略を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="78ac6-106">But you need to enable the Entity Framework execution strategy for each DbContext connection if you want to have [resilient EF Core connections](https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency).</span></span>

<span data-ttu-id="78ac6-107">たとえば、EF Core 接続レベルで次のコードを実行すると、接続が失敗した場合に再試行される回復力のある SQL 接続が有効になります。</span><span class="sxs-lookup"><span data-stu-id="78ac6-107">For instance, the following code at the EF Core connection level enables resilient SQL connections that are retried if the connection fails.</span></span>

```csharp
// Startup.cs from any ASP.NET Core Web API
public class Startup
{
    // Other code ...
    public IServiceProvider ConfigureServices(IServiceCollection services)
    {
        // ...
        services.AddDbContext<CatalogContext>(options =>
        {
            options.UseSqlServer(Configuration["ConnectionString"],
            sqlServerOptionsAction: sqlOptions =>
            {
                sqlOptions.EnableRetryOnFailure(
                maxRetryCount: 10,
                maxRetryDelay: TimeSpan.FromSeconds(30),
                errorNumbersToAdd: null);
            });
        });
    }
//...
}
```

## <a name="execution-strategies-and-explicit-transactions-using-begintransaction-and-multiple-dbcontexts"></a><span data-ttu-id="78ac6-108">BeginTransaction と複数の DbContext を使用した実行戦略と明示的なトランザクション</span><span class="sxs-lookup"><span data-stu-id="78ac6-108">Execution strategies and explicit transactions using BeginTransaction and multiple DbContexts</span></span>

<span data-ttu-id="78ac6-109">EF Core 接続で再試行を有効にすると、EF Core を使用して実行する各操作は、独自の再試行可能な操作になります。</span><span class="sxs-lookup"><span data-stu-id="78ac6-109">When retries are enabled in EF Core connections, each operation you perform using EF Core becomes its own retryable operation.</span></span> <span data-ttu-id="78ac6-110">一時的なエラーが発生した場合、SaveChanges への各クエリと各呼び出しは 1 つのユニットとして再試行されます。</span><span class="sxs-lookup"><span data-stu-id="78ac6-110">Each query and each call to SaveChanges will be retried as a unit if a transient failure occurs.</span></span>

<span data-ttu-id="78ac6-111">一方、BeginTransaction を使用してトランザクションを開始するコードの場合、1 ユニットとして扱う必要のある独自の操作グループを定義しています。エラーが発生した場合、トランザクション内のすべてがロールバックされます。</span><span class="sxs-lookup"><span data-stu-id="78ac6-111">However, if your code initiates a transaction using BeginTransaction, you are defining your own group of operations that need to be treated as a unit—everything inside the transaction has be rolled back if a failure occurs.</span></span> <span data-ttu-id="78ac6-112">EF 実行戦略 (再試行ポリシー) を使用し、複数の DbContext からの SaveChanges 呼び出しをいくつかトランザクションに含める場合、そのトランザクションを実行しようとすると、次のような例外が表示されます。</span><span class="sxs-lookup"><span data-stu-id="78ac6-112">You will see an exception like the following if you attempt to execute that transaction when using an EF execution strategy (retry policy) and you include several SaveChanges calls from multiple DbContexts in the transaction.</span></span>

> <span data-ttu-id="78ac6-113">System.InvalidOperationException: 構成された実行戦略 'SqlServerRetryingExecutionStrategy' は、ユーザーが開始したトランザクションをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="78ac6-113">System.InvalidOperationException: The configured execution strategy 'SqlServerRetryingExecutionStrategy' does not support user initiated transactions.</span></span> <span data-ttu-id="78ac6-114">'DbContext.Database.CreateExecutionStrategy()' から返された実行戦略を使用して、再試行可能なユニットとしてトランザクション内のすべての操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="78ac6-114">Use the execution strategy returned by 'DbContext.Database.CreateExecutionStrategy()' to execute all the operations in the transaction as a retriable unit.</span></span>

<span data-ttu-id="78ac6-115">この解決策では、実行する必要があるすべてを表すデリゲートを使用して EF 実行戦略を手動で呼び出します。</span><span class="sxs-lookup"><span data-stu-id="78ac6-115">The solution is to manually invoke the EF execution strategy with a delegate representing everything that needs to be executed.</span></span> <span data-ttu-id="78ac6-116">一時的なエラーが発生した場合、実行戦略によってデリゲートが再び呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="78ac6-116">If a transient failure occurs, the execution strategy will invoke the delegate again.</span></span> <span data-ttu-id="78ac6-117">たとえば、次のコードは、製品を更新し、別の DbContext を使用する必要がある ProductPriceChangedIntegrationEvent オブジェクトを保存するときに、2 つの DbContext (\_catalogContext と IntegrationEventLogContext) を使用して eShopOnContainers で実装する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="78ac6-117">For example, the following code show how it is implemented in eShopOnContainers with two multiple DbContexts (\_catalogContext and the IntegrationEventLogContext) when updating a product and then saving the ProductPriceChangedIntegrationEvent object, which needs to use a different DbContext.</span></span>

```csharp
public async Task<IActionResult> UpdateProduct([FromBody]CatalogItem
    productToUpdate)
{
    // Other code ...
    // Update current product
    catalogItem = productToUpdate;

    // Use of an EF Core resiliency strategy when using multiple DbContexts
    // within an explicit transaction
    // See:
    // https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency
    var strategy = _catalogContext.Database.CreateExecutionStrategy();
    await strategy.ExecuteAsync(async () =>
    {
        // Achieving atomicity between original Catalog database operation and the
        // IntegrationEventLog thanks to a local transaction
        using (var transaction = _catalogContext.Database.BeginTransaction())
        {
            _catalogContext.CatalogItems.Update(catalogItem);
            await _catalogContext.SaveChangesAsync();
            // Save to EventLog only if product price changed
            if (raiseProductPriceChangedEvent)
            await _integrationEventLogService.SaveEventAsync(priceChangedEvent);
            transaction.Commit();
        }
    });
}
```

<span data-ttu-id="78ac6-118">最初の DbContext は \_catalogContext で、2 つ目の DbContext\_ は integrationEventLogService オブジェクト内にあります。</span><span class="sxs-lookup"><span data-stu-id="78ac6-118">The first DbContext is \_catalogContext and the second DbContext is within the \_integrationEventLogService object.</span></span> <span data-ttu-id="78ac6-119">Commit アクションは、EF 実行戦略を使用して複数の DbContext 全体で実行されます。</span><span class="sxs-lookup"><span data-stu-id="78ac6-119">The Commit action is performed across multiple DbContexts using an EF execution strategy.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="78ac6-120">その他の技術情報</span><span class="sxs-lookup"><span data-stu-id="78ac6-120">Additional resources</span></span>

-   <span data-ttu-id="78ac6-121">**EF 接続の回復性** (Entity Framework Core) [*https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency*](https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency)</span><span class="sxs-lookup"><span data-stu-id="78ac6-121">**EF Connection Resiliency** (Entity Framework Core) [*https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency*](https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency)</span></span>

-   <span data-ttu-id="78ac6-122">**Entity Framework での接続回復性とコマンド傍受**
    [*https://docs.microsoft.com/azure/architecture/patterns/category/resiliency*](https://docs.microsoft.com/azure/architecture/patterns/category/resiliency)</span><span class="sxs-lookup"><span data-stu-id="78ac6-122">**Connection Resiliency and Command Interception with the Entity Framework**
[*https://docs.microsoft.com/azure/architecture/patterns/category/resiliency*](https://docs.microsoft.com/azure/architecture/patterns/category/resiliency)</span></span>

-   <span data-ttu-id="78ac6-123">**Cesar de la Torre。回復力の高い Entity Framework Core SQL 接続とトランザクションの使用**
    <https://blogs.msdn.microsoft.com/cesardelatorre/2017/03/26/using-resilient-entity-framework-core-sql-connections-and-transactions-retries-with-exponential-backoff/></span><span class="sxs-lookup"><span data-stu-id="78ac6-123">**Cesar de la Torre. Using Resilient Entity Framework Core Sql Connections and Transactions**
<https://blogs.msdn.microsoft.com/cesardelatorre/2017/03/26/using-resilient-entity-framework-core-sql-connections-and-transactions-retries-with-exponential-backoff/></span></span>

>[!div class="step-by-step"]
<span data-ttu-id="78ac6-124">[前へ](implement-retries-exponential-backoff.md)
[次へ](explore-custom-http-call-retries-exponential-backoff.md)</span><span class="sxs-lookup"><span data-stu-id="78ac6-124">[Previous](implement-retries-exponential-backoff.md)
[Next](explore-custom-http-call-retries-exponential-backoff.md)</span></span>
