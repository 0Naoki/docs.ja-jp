---
title: SQL Server の CLR 統合の概要
ms.date: 03/30/2017
ms.assetid: 551d2290-ed80-49be-b377-44b32444da1c
ms.openlocfilehash: 2f65e8690aa52f0442b4bee3b98bb1ea86e064a5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59110704"
---
# <a name="introduction-to-sql-server-clr-integration"></a><span data-ttu-id="14e26-102">SQL Server の CLR 統合の概要</span><span class="sxs-lookup"><span data-stu-id="14e26-102">Introduction to SQL Server CLR Integration</span></span>
<span data-ttu-id="14e26-103">共通言語ランタイム (CLR) は、Microsoft .NET Framework の中核であり、すべての .NET Framework コードの実行環境を提供します。</span><span class="sxs-lookup"><span data-stu-id="14e26-103">The common language runtime (CLR) is the heart of the Microsoft .NET Framework and provides the execution environment for all .NET Framework code.</span></span> <span data-ttu-id="14e26-104">CLR 内で実行されるコードを、マネージド コードと呼びます。</span><span class="sxs-lookup"><span data-stu-id="14e26-104">Code that runs within the CLR is referred to as managed code.</span></span> <span data-ttu-id="14e26-105">CLR は、ジャストインタイム (JIT) コンパイル、メモリの割り当てと管理、タイプ セーフの設定、例外処理、スレッド管理、セキュリティなど、プログラムの実行に必要なさまざまな機能やサービスを備えています。</span><span class="sxs-lookup"><span data-stu-id="14e26-105">The CLR provides various functions and services required for program execution, including just-in-time (JIT) compilation, allocating and managing memory, enforcing type safety, exception handling, thread management, and security.</span></span>  
  
 <span data-ttu-id="14e26-106">Microsoft SQL Server にホストされる CLR (CLR 統合と呼ばれる) を利用することで、ストアド プロシージャ、トリガー、ユーザー定義関数、ユーザー定義型、およびユーザー定義集計をマネージド コードで作成できます。</span><span class="sxs-lookup"><span data-stu-id="14e26-106">With the CLR hosted in Microsoft SQL Server (called CLR integration), you can author stored procedures, triggers, user-defined functions, user-defined types, and user-defined aggregates in managed code.</span></span> <span data-ttu-id="14e26-107">マネージド コードは実行前にネイティブ コードにコンパイルされるため、状況によっては、パフォーマンスが大幅に向上します。</span><span class="sxs-lookup"><span data-stu-id="14e26-107">Because managed code compiles to native code prior to execution, you can achieve significant performance increases in some scenarios.</span></span>  
  
 <span data-ttu-id="14e26-108">マネージド コードは、コード アクセス セキュリティ (CAS)、コード リンク、およびアプリケーション ドメインを使用して、アセンブリが特定の操作を実行することを防止します。</span><span class="sxs-lookup"><span data-stu-id="14e26-108">Managed code uses Code Access Security (CAS), code links, and application domains to prevent assemblies from performing certain operations.</span></span> <span data-ttu-id="14e26-109">SQL Server は、CAS を使用して、マネージド コードをセキュリティ保護し、オペレーティング システムやデータベース サーバーへの侵害を防止します。</span><span class="sxs-lookup"><span data-stu-id="14e26-109">SQL Server uses CAS to help secure the managed code and prevent compromise of the operating system or database server.</span></span>  
  
 <span data-ttu-id="14e26-110">このセクションは、SQL Server の CLR 統合を利用したプログラミングを始めるのに十分な情報を提供することを目的としており、包括的な情報の提供は目的としていません。</span><span class="sxs-lookup"><span data-stu-id="14e26-110">This section is meant to provide only enough information to get started programming with SQL Server CLR integration, and is not meant to be comprehensive.</span></span> <span data-ttu-id="14e26-111">詳細については、ご使用中の SQL Server のバージョンに対応するバージョンの SQL Server オンライン ブックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="14e26-111">For more detailed information, see the version of SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 **<span data-ttu-id="14e26-112">SQL Server オンライン ブック</span><span class="sxs-lookup"><span data-stu-id="14e26-112">SQL Server Books Online</span></span>**  
  
-   [<span data-ttu-id="14e26-113">共通言語ランタイム (CLR) 統合の概要</span><span class="sxs-lookup"><span data-stu-id="14e26-113">Common Language Runtime (CLR) Integration Overview</span></span>](https://go.microsoft.com/fwlink/?LinkId=115242)  
  
## <a name="enabling-clr-integration"></a><span data-ttu-id="14e26-114">CLR 統合の有効化</span><span class="sxs-lookup"><span data-stu-id="14e26-114">Enabling CLR Integration</span></span>  
 <span data-ttu-id="14e26-115">Microsoft SQL Server では共通言語ランタイム (CLR) 統合機能が既定でオフになっているため、CLR 統合を利用して実装されるオブジェクトを使用するには、CLR 統合機能を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="14e26-115">The common language runtime (CLR) integration feature is off by default in Microsoft SQL Server, and must be enabled in order to use objects that are implemented using CLR integration.</span></span> <span data-ttu-id="14e26-116">Transact-SQL を使用して CLR 統合を有効にするには、次に示すように、`clr enabled` ストアド プロシージャの `sp_configure` オプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="14e26-116">To enable CLR integration using Transact-SQL, use the `clr enabled` option of the `sp_configure` stored procedure as shown:</span></span>  
  
```  
sp_configure 'clr enabled', 1  
GO  
RECONFIGURE  
GO  
```  
  
 <span data-ttu-id="14e26-117">`clr enabled` オプションを 0 に設定することにより、CLR 統合を無効にできます。</span><span class="sxs-lookup"><span data-stu-id="14e26-117">You can disable CLR integration by setting the `clr enabled` option to 0.</span></span> <span data-ttu-id="14e26-118">CLR 統合を無効にすると、SQL Server ではすべての CLR ルーチンの実行が停止され、すべてのアプリケーション ドメインがアンロードされます。</span><span class="sxs-lookup"><span data-stu-id="14e26-118">When you disable CLR integration, SQL Server stops executing all CLR routines and unloads all application domains.</span></span>  
  
 <span data-ttu-id="14e26-119">詳細については、ご使用中の SQL Server のバージョンに対応するバージョンの SQL Server オンライン ブックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="14e26-119">For more detailed information, see the version of SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 **<span data-ttu-id="14e26-120">SQL Server オンライン ブック</span><span class="sxs-lookup"><span data-stu-id="14e26-120">SQL Server Books Online</span></span>**  
  
-   [<span data-ttu-id="14e26-121">CLR 統合の有効化</span><span class="sxs-lookup"><span data-stu-id="14e26-121">Enabling CLR Integration</span></span>](https://go.microsoft.com/fwlink/?LinkId=115230)  
  
## <a name="deploying-a-clr-assembly"></a><span data-ttu-id="14e26-122">CLR アセンブリの配置</span><span class="sxs-lookup"><span data-stu-id="14e26-122">Deploying a CLR Assembly</span></span>  
 <span data-ttu-id="14e26-123">CLR メソッドをテスト サーバーでテストおよび検証すると、配置スクリプトを使用してこれらを実稼働サーバーに配布できます。</span><span class="sxs-lookup"><span data-stu-id="14e26-123">Once the CLR methods have been tested and verified on the test server, they can be distributed to production servers using a deployment script.</span></span> <span data-ttu-id="14e26-124">配置スクリプトは手動で生成するか、SQL Server Management Studio を使用して生成することができます。</span><span class="sxs-lookup"><span data-stu-id="14e26-124">The deployment script can be generated manually, or by using SQL Server Management Studio.</span></span> <span data-ttu-id="14e26-125">詳細については、ご使用中の SQL Server のバージョンに対応するバージョンの SQL Server オンライン ブックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="14e26-125">For more detailed information, see the version of SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 **<span data-ttu-id="14e26-126">SQL Server オンライン ブック</span><span class="sxs-lookup"><span data-stu-id="14e26-126">SQL Server Books Online</span></span>**  
  
1.  [<span data-ttu-id="14e26-127">CLR データベース オブジェクトの配置</span><span class="sxs-lookup"><span data-stu-id="14e26-127">Deploying CLR Database Objects</span></span>](https://go.microsoft.com/fwlink/?LinkId=115232)  
  
## <a name="clr-integration-security"></a><span data-ttu-id="14e26-128">CLR 統合セキュリティ</span><span class="sxs-lookup"><span data-stu-id="14e26-128">CLR Integration Security</span></span>  
 <span data-ttu-id="14e26-129">Microsoft SQL Server と Microsoft .NET Framework 共通言語ランタイム (CLR) との統合のセキュリティ モデルは、SQL Server 内部で実行されるさまざまなタイプの CLR オブジェクトおよび非 CLR オブジェクトの間のアクセスを管理し、セキュリティで保護します。</span><span class="sxs-lookup"><span data-stu-id="14e26-129">The security model of the Microsoft SQL Server integration with the Microsoft .NET Framework common language runtime (CLR) manages and secures access between different types of CLR and non-CLR objects running within SQL Server.</span></span> <span data-ttu-id="14e26-130">これらのオブジェクトは、Transact-SQL ステートメントまたはサーバーで実行される別の CLR オブジェクトから呼び出される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="14e26-130">These objects may be called by a Transact-SQL statement or another CLR object running in the server.</span></span>  
  
 <span data-ttu-id="14e26-131">詳細については、ご使用中の SQL Server のバージョンに対応するバージョンの SQL Server オンライン ブックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="14e26-131">For more detailed information, see the version of SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 **<span data-ttu-id="14e26-132">SQL Server オンライン ブック</span><span class="sxs-lookup"><span data-stu-id="14e26-132">SQL Server Books Online</span></span>**  
  
-   [<span data-ttu-id="14e26-133">CLR 統合セキュリティ</span><span class="sxs-lookup"><span data-stu-id="14e26-133">CLR Integration Security</span></span>](https://go.microsoft.com/fwlink/?LinkId=115234)  
  
## <a name="debugging-a-clr-assembly"></a><span data-ttu-id="14e26-134">CLR アセンブリのデバッグ</span><span class="sxs-lookup"><span data-stu-id="14e26-134">Debugging a CLR Assembly</span></span>  
 <span data-ttu-id="14e26-135">Microsoft SQL Server は、データベース内の Transact-SQL オブジェクトおよび共通言語ランタイム (CLR) オブジェクトのデバッグをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="14e26-135">Microsoft SQL Server provides support for debugging Transact-SQL and common language runtime (CLR) objects in the database.</span></span> <span data-ttu-id="14e26-136">デバッグは言語をまたがって機能します。ユーザーは、Transact-SQL から CLR オブジェクトへ、または CLR オブジェクトから Transact-SQL へシームレスにデバッグできます。</span><span class="sxs-lookup"><span data-stu-id="14e26-136">Debugging works across languages: users can step seamlessly into CLR objects from Transact-SQL, and vice versa.</span></span>  
  
 <span data-ttu-id="14e26-137">詳細については、ご使用中の SQL Server のバージョンに対応するバージョンの SQL Server オンライン ブックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="14e26-137">For more detailed information, see the version of SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 **<span data-ttu-id="14e26-138">SQL Server オンライン ブック</span><span class="sxs-lookup"><span data-stu-id="14e26-138">SQL Server Books Online</span></span>**  
  
-   [<span data-ttu-id="14e26-139">CLR データベース オブジェクトのデバッグ</span><span class="sxs-lookup"><span data-stu-id="14e26-139">Debugging CLR Database Objects</span></span>](https://go.microsoft.com/fwlink/?LinkId=115236)  
  
## <a name="see-also"></a><span data-ttu-id="14e26-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="14e26-140">See also</span></span>

- [<span data-ttu-id="14e26-141">コード アクセス セキュリティと ADO.NET</span><span class="sxs-lookup"><span data-stu-id="14e26-141">Code Access Security and ADO.NET</span></span>](../../../../../docs/framework/data/adonet/code-access-security.md)
- [<span data-ttu-id="14e26-142">ADO.NET のマネージド プロバイダーと DataSet デベロッパー センター</span><span class="sxs-lookup"><span data-stu-id="14e26-142">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
