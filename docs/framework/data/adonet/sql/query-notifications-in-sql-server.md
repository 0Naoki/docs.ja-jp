---
title: SQL Server のクエリ通知
ms.date: 03/30/2017
ms.assetid: 0f0ba1a1-3180-4af8-87f7-c795dc8f8f55
ms.openlocfilehash: 87335b5c9ad626e998fdb7bf0e71cae2542386f5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54636691"
---
# <a name="query-notifications-in-sql-server"></a><span data-ttu-id="1e3c3-102">SQL Server のクエリ通知</span><span class="sxs-lookup"><span data-stu-id="1e3c3-102">Query Notifications in SQL Server</span></span>
<span data-ttu-id="1e3c3-103">クエリ通知は Service Broker インフラストラクチャに基づいて構築されており、データが変更されたときにクエリ通知を使用してアプリケーションに通知できます。</span><span class="sxs-lookup"><span data-stu-id="1e3c3-103">Built upon the Service Broker infrastructure, query notifications allow applications to be notified when data has changed.</span></span> <span data-ttu-id="1e3c3-104">この機能は、Web アプリケーションなど、データベースから情報のキャッシュを提供し、ソース データが変更された場合に通知を必要とするアプリケーションに特に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="1e3c3-104">This feature is particularly useful for applications that provide a cache of information from a database, such as a Web application, and need to be notified when the source data is changed.</span></span>  
  
 <span data-ttu-id="1e3c3-105">ADO.NET を使用してクエリ通知機能を実装する方法は 3 つあります。</span><span class="sxs-lookup"><span data-stu-id="1e3c3-105">There are three ways you can implement query notifications using ADO.NET:</span></span>  
  
1.  <span data-ttu-id="1e3c3-106">基本レベルの実装は、`SqlNotificationRequest` クラスによって行われます。これによってサーバー側の機能が公開され、通知要求を伴うコマンドを実行できます。</span><span class="sxs-lookup"><span data-stu-id="1e3c3-106">The low-level implementation is provided by the `SqlNotificationRequest` class that exposes server-side functionality, enabling you to execute a command with a notification request.</span></span>  
  
2.  <span data-ttu-id="1e3c3-107">高レベルの実装は、`SqlDependency` クラスによって行われます。このクラスでは、ソース アプリケーションと SQL Server 間の通知機能が高度に抽象化され、その依存関係を使用してサーバー内の変更を検出することができます。</span><span class="sxs-lookup"><span data-stu-id="1e3c3-107">The high-level implementation is provided by the `SqlDependency` class, which is a class that provides a high-level abstraction of notification functionality between the source application and SQL Server, enabling you to use a dependency to detect changes in the server.</span></span> <span data-ttu-id="1e3c3-108">マネージ クライアント アプリケーションが .NET Framework Data Provider for SQL Server を使用して SQL Server の通知機能を活用するには、ほとんどの場合、これが最も簡単かつ効果的な方法です。</span><span class="sxs-lookup"><span data-stu-id="1e3c3-108">In most cases, this is the simplest and most effective way to leverage SQL Server notifications capability by managed client applications using the .NET Framework Data Provider for SQL Server.</span></span>  
  
3.  <span data-ttu-id="1e3c3-109">さらに、ASP.NET 2.0 以降を使用して構築された Web アプリケーションでは、`SqlCacheDependency` ヘルパー クラスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="1e3c3-109">In addition, Web applications built using ASP.NET 2.0 or later can use the `SqlCacheDependency` helper classes.</span></span>  
  
 <span data-ttu-id="1e3c3-110">クエリ通知は、基になるデータの変更に応じて表示またはキャッシュを更新する必要があるアプリケーションで使用されます。</span><span class="sxs-lookup"><span data-stu-id="1e3c3-110">Query notifications are used for applications that need to refresh displays or caches in response to changes in underlying data.</span></span> <span data-ttu-id="1e3c3-111">Microsoft SQL Server では、最初に取得したものと異なる結果セットが同じコマンドで得られた場合には、.NET Framework アプリケーションから SQL Server にコマンドを送信して通知を要求することができます。</span><span class="sxs-lookup"><span data-stu-id="1e3c3-111">Microsoft SQL Server allows .NET Framework applications to send a command to SQL Server and request notification if executing the same command would produce result sets different from those initially retrieved.</span></span> <span data-ttu-id="1e3c3-112">サーバーで生成された通知は、キューを通じて送信された後に処理されます。</span><span class="sxs-lookup"><span data-stu-id="1e3c3-112">Notifications generated at the server are sent through queues to be processed later.</span></span>  
  
 <span data-ttu-id="1e3c3-113">通知は SELECT ステートメントおよび EXECUTE ステートメントに対して設定できます。</span><span class="sxs-lookup"><span data-stu-id="1e3c3-113">You can set up notifications for SELECT and EXECUTE statements.</span></span> <span data-ttu-id="1e3c3-114">EXECUTE ステートメントを使用した場合、SQL Server では、EXECUTE ステートメント自体ではなく、EXECUTE ステートメントで実行されたコマンドに対する通知が登録されます。</span><span class="sxs-lookup"><span data-stu-id="1e3c3-114">When using an EXECUTE statement, SQL Server registers a notification for the command executed rather than the EXECUTE statement itself.</span></span> <span data-ttu-id="1e3c3-115">コマンドは、SELECT ステートメントの要件と制限を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="1e3c3-115">The command must meet the requirements and limitations for a SELECT statement.</span></span> <span data-ttu-id="1e3c3-116">通知を登録するコマンドに複数のステートメントが含まれている場合、データベース エンジンによりバッチ内のステートメントごとに通知が作成されます。</span><span class="sxs-lookup"><span data-stu-id="1e3c3-116">When a command that registers a notification contains more than one statement, the Database Engine creates a notification for each statement in the batch.</span></span>  
  
 <span data-ttu-id="1e3c3-117">セクションを参照してデータが変更されたときに、信頼できる即時の通知が必要なアプリケーションを開発している場合、**効率的なクエリ通知戦略の計画**と**クエリに代わる方法通知**で、[通知の計画](https://go.microsoft.com/fwlink/?LinkId=211984)SQL Server オンライン ブックのトピックです。</span><span class="sxs-lookup"><span data-stu-id="1e3c3-117">If you are developing an application where you need reliable sub-second notifications when data changes, review the sections **Planning an Efficient Query Notifications Strategy** and **Alternatives to Query Notifications** in the [Planning for Notifications](https://go.microsoft.com/fwlink/?LinkId=211984) topic in SQL Server Books Online.</span></span> <span data-ttu-id="1e3c3-118">クエリ通知と SQL Server Service Broker の詳細については、次の SQL Server オンライン ブックのトピックへのリンクを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1e3c3-118">For more information about Query Notifications and SQL Server Service Broker, see the following links to topics in SQL Server Books Online.</span></span>  
  
 <span data-ttu-id="1e3c3-119">**SQL Server オンライン ブック**</span><span class="sxs-lookup"><span data-stu-id="1e3c3-119">**SQL Server Books Online**</span></span>  
  
-   [<span data-ttu-id="1e3c3-120">クエリ通知の使用</span><span class="sxs-lookup"><span data-stu-id="1e3c3-120">Using Query Notifications</span></span>](https://msdn.microsoft.com/library/ms175110.aspx)  
  
-   [<span data-ttu-id="1e3c3-121">通知のクエリを作成します。</span><span class="sxs-lookup"><span data-stu-id="1e3c3-121">Creating a Query for Notification</span></span>](https://msdn.microsoft.com/library/ms181122.aspx)  
  
-   [<span data-ttu-id="1e3c3-122">Service Broker</span><span class="sxs-lookup"><span data-stu-id="1e3c3-122">Service Broker</span></span>](https://msdn.microsoft.com/library/bb522889.aspx)  
  
-   [<span data-ttu-id="1e3c3-123">Service Broker 開発者向けの情報</span><span class="sxs-lookup"><span data-stu-id="1e3c3-123">Service Broker Developer InfoCenter</span></span>](https://msdn.microsoft.com/library/ms166100.aspx)  
  
-   [<span data-ttu-id="1e3c3-124">開発 (Service Broker)</span><span class="sxs-lookup"><span data-stu-id="1e3c3-124">Development (Service Broker)</span></span>](https://msdn.microsoft.com/library/bb522908.aspx)  
  
## <a name="in-this-section"></a><span data-ttu-id="1e3c3-125">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="1e3c3-125">In This Section</span></span>  
 [<span data-ttu-id="1e3c3-126">クエリ通知の有効化</span><span class="sxs-lookup"><span data-stu-id="1e3c3-126">Enabling Query Notifications</span></span>](../../../../../docs/framework/data/adonet/sql/enabling-query-notifications.md)  
 <span data-ttu-id="1e3c3-127">クエリ通知を有効にするための要件を含め、クエリ通知の使用方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="1e3c3-127">Discusses how to use query notifications, including the requirements for enabling and using them.</span></span>  
  
 [<span data-ttu-id="1e3c3-128">ASP.NET アプリケーションでの SqlDependency</span><span class="sxs-lookup"><span data-stu-id="1e3c3-128">SqlDependency in an ASP.NET Application</span></span>](../../../../../docs/framework/data/adonet/sql/sqldependency-in-an-aspnet-app.md)  
 <span data-ttu-id="1e3c3-129">ASP.NET アプリケーションからクエリ通知を使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="1e3c3-129">Demonstrates how to use query notifications from an ASP.NET application.</span></span>  
  
 [<span data-ttu-id="1e3c3-130">SqlDependency を使用した変更の検出</span><span class="sxs-lookup"><span data-stu-id="1e3c3-130">Detecting Changes with SqlDependency</span></span>](../../../../../docs/framework/data/adonet/sql/detecting-changes-with-sqldependency.md)  
 <span data-ttu-id="1e3c3-131">最初に取得された結果と異なるクエリ結果を検出する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="1e3c3-131">Demonstrates how to detect when query results will be different from those originally received.</span></span>  
  
 [<span data-ttu-id="1e3c3-132">SqlCommand の実行と SqlNotificationRequest</span><span class="sxs-lookup"><span data-stu-id="1e3c3-132">SqlCommand Execution with a SqlNotificationRequest</span></span>](../../../../../docs/framework/data/adonet/sql/sqlcommand-execution-with-a-sqlnotificationrequest.md)  
 <span data-ttu-id="1e3c3-133">クエリ通知を使用する <xref:System.Data.SqlClient.SqlCommand> オブジェクトの構成例を示します。</span><span class="sxs-lookup"><span data-stu-id="1e3c3-133">Demonstrates configuring a <xref:System.Data.SqlClient.SqlCommand> object to work with a query notification.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="1e3c3-134">参照</span><span class="sxs-lookup"><span data-stu-id="1e3c3-134">Reference</span></span>  
 <xref:System.Data.Sql.SqlNotificationRequest>  
 <span data-ttu-id="1e3c3-135"><xref:System.Data.Sql.SqlNotificationRequest> クラスおよびそのすべてのメンバーについて説明します。</span><span class="sxs-lookup"><span data-stu-id="1e3c3-135">Describes the <xref:System.Data.Sql.SqlNotificationRequest> class and all of its members.</span></span>  
  
 <xref:System.Data.SqlClient.SqlDependency>  
 <span data-ttu-id="1e3c3-136"><xref:System.Data.SqlClient.SqlDependency> クラスおよびそのすべてのメンバーについて説明します。</span><span class="sxs-lookup"><span data-stu-id="1e3c3-136">Describes the <xref:System.Data.SqlClient.SqlDependency> class and all of its members.</span></span>  
  
 <xref:System.Web.Caching.SqlCacheDependency>  
 <span data-ttu-id="1e3c3-137"><xref:System.Web.Caching.SqlCacheDependency> クラスおよびそのすべてのメンバーについて説明します。</span><span class="sxs-lookup"><span data-stu-id="1e3c3-137">Describes the <xref:System.Web.Caching.SqlCacheDependency> class and all of its members.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e3c3-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="1e3c3-138">See also</span></span>
- [<span data-ttu-id="1e3c3-139">SQL Server と ADO.NET</span><span class="sxs-lookup"><span data-stu-id="1e3c3-139">SQL Server and ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/index.md)
- [<span data-ttu-id="1e3c3-140">ADO.NET のマネージド プロバイダーと DataSet デベロッパー センター</span><span class="sxs-lookup"><span data-stu-id="1e3c3-140">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
