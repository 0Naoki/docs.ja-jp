---
title: F# を使用した Azure Table storage の概要します。
description: Azure Table storage または Azure Cosmos DB を使用してクラウドで構造化データを格納します。
author: sylvanc
ms.date: 03/26/2018
ms.openlocfilehash: 2d793ba8653833ff384f1824e303b08e05aba69b
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/02/2018
ms.locfileid: "43519536"
---
# <a name="get-started-with-azure-table-storage-and-the-azure-cosmos-db-table-api-using-f"></a><span data-ttu-id="44a67-103">Azure Table storage と F# を使用して Azure Cosmos DB Table API の概要します。</span><span class="sxs-lookup"><span data-stu-id="44a67-103">Get started with Azure Table storage and the Azure Cosmos DB Table API using F#</span></span> # 

<span data-ttu-id="44a67-104">Azure Table storage とは、クラウドで構造化 NoSQL データを格納するサービスです。</span><span class="sxs-lookup"><span data-stu-id="44a67-104">Azure Table storage is a service that stores structured NoSQL data in the cloud.</span></span> <span data-ttu-id="44a67-105">テーブル ストレージは、スキーマレス設計のキー/属性ストアです。</span><span class="sxs-lookup"><span data-stu-id="44a67-105">Table storage is a key/attribute store with a schemaless design.</span></span> <span data-ttu-id="44a67-106">Table storage は、スキーマなしであるために、簡単に、アプリケーションの進化のニーズに合わせてデータを調整できますが。</span><span class="sxs-lookup"><span data-stu-id="44a67-106">Because Table storage is schemaless, it's easy to adapt your data as the needs of your application evolve.</span></span> <span data-ttu-id="44a67-107">データへのアクセスとは、高速でコスト効率に優れたアプリケーションのすべての種類です。</span><span class="sxs-lookup"><span data-stu-id="44a67-107">Access to data is fast and cost-effective for all kinds of applications.</span></span> <span data-ttu-id="44a67-108">テーブル ストレージは、大幅に従来の SQL と同様、大量のデータよりも低コストでは通常です。</span><span class="sxs-lookup"><span data-stu-id="44a67-108">Table storage is typically significantly lower in cost than traditional SQL for similar volumes of data.</span></span>

<span data-ttu-id="44a67-109">Table storage を使用して、web アプリケーション、アドレス帳、デバイスについては、その他の種類のサービスに必要なメタデータ用のユーザー データなどの柔軟なデータセットを格納することができます。</span><span class="sxs-lookup"><span data-stu-id="44a67-109">You can use Table storage to store flexible datasets, such as user data for web applications, address books, device information, and any other type of metadata that your service requires.</span></span> <span data-ttu-id="44a67-110">テーブルのエンティティの任意の数を格納して、ストレージ アカウントは、ストレージ アカウントの容量の上限に達するまで、テーブルの任意の数を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="44a67-110">You can store any number of entities in a table, and a storage account may contain any number of tables, up to the capacity limit of the storage account.</span></span>

<span data-ttu-id="44a67-111">Azure Cosmos DB では、Azure Table storage に書き込まれなどのプレミアム機能を必要とするアプリケーションを Table API を提供します。</span><span class="sxs-lookup"><span data-stu-id="44a67-111">Azure Cosmos DB provides the Table API for applications that are written for Azure Table storage and that require premium capabilities such as:</span></span>

- <span data-ttu-id="44a67-112">ターンキー グローバル配信。</span><span class="sxs-lookup"><span data-stu-id="44a67-112">Turnkey global distribution.</span></span>
- <span data-ttu-id="44a67-113">世界中の専用スループット。</span><span class="sxs-lookup"><span data-stu-id="44a67-113">Dedicated throughput worldwide.</span></span>
- <span data-ttu-id="44a67-114">99 パーセン タイルで 1 桁ミリ秒の待機時間。</span><span class="sxs-lookup"><span data-stu-id="44a67-114">Single-digit millisecond latencies at the 99th percentile.</span></span>
- <span data-ttu-id="44a67-115">高可用性を保証します。</span><span class="sxs-lookup"><span data-stu-id="44a67-115">Guaranteed high availability.</span></span>
- <span data-ttu-id="44a67-116">自動セカンダリ インデックス作成。</span><span class="sxs-lookup"><span data-stu-id="44a67-116">Automatic secondary indexing.</span></span>

<span data-ttu-id="44a67-117">Azure Table storage 用に記述されたアプリケーションでは、コードの変更を Table API を使用して、Azure Cosmos DB に移行でき、高度な機能を利用することができます。</span><span class="sxs-lookup"><span data-stu-id="44a67-117">Applications written for Azure Table storage can migrate to Azure Cosmos DB by using the Table API with no code changes and take advantage of premium capabilities.</span></span> <span data-ttu-id="44a67-118">Table API では、.NET、Java、Python、および Node.js の使用可能なクライアント Sdk があります。</span><span class="sxs-lookup"><span data-stu-id="44a67-118">The Table API has client SDKs available for .NET, Java, Python, and Node.js.</span></span>

<span data-ttu-id="44a67-119">詳細については、次を参照してください。 [Azure Cosmos DB Table API の概要](https://docs.microsoft.com/azure/cosmos-db/table-introduction)します。</span><span class="sxs-lookup"><span data-stu-id="44a67-119">For more information, see [Introduction to Azure Cosmos DB Table API](https://docs.microsoft.com/azure/cosmos-db/table-introduction).</span></span>

## <a name="about-this-tutorial"></a><span data-ttu-id="44a67-120">このチュートリアルについて</span><span class="sxs-lookup"><span data-stu-id="44a67-120">About this tutorial</span></span>

<span data-ttu-id="44a67-121">このチュートリアルでは、Azure Table storage またはなど、Azure Cosmos DB テーブル API、作成しテーブルの削除し挿入、更新、削除、およびテーブル データのクエリを使用していくつかの一般的なタスクを実行する F# コードを記述する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="44a67-121">This tutorial shows how to write F# code to do some common tasks using Azure Table storage or the Azure Cosmos DB Table API, including creating and deleting a table and inserting, updating, deleting, and querying table data.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="44a67-122">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="44a67-122">Prerequisites</span></span>

<span data-ttu-id="44a67-123">このガイドを使用するのにはまず[Azure ストレージ アカウントを作成](/azure/storage/storage-create-storage-account)または[Azure Cosmos DB アカウント](https://azure.microsoft.com/try/cosmosdb/)します。</span><span class="sxs-lookup"><span data-stu-id="44a67-123">To use this guide, you must first [create an Azure storage account](/azure/storage/storage-create-storage-account) or [Azure Cosmos DB account](https://azure.microsoft.com/try/cosmosdb/).</span></span>


## <a name="create-an-f-script-and-start-f-interactive"></a><span data-ttu-id="44a67-124">作成して、F# スクリプトと開始 F# 対話型</span><span class="sxs-lookup"><span data-stu-id="44a67-124">Create an F# Script and Start F# Interactive</span></span>

<span data-ttu-id="44a67-125">この記事のサンプルは、F# アプリケーションまたは F# スクリプトのいずれかで使用できます。</span><span class="sxs-lookup"><span data-stu-id="44a67-125">The samples in this article can be used in either an F# application or an F# script.</span></span> <span data-ttu-id="44a67-126">F# スクリプトを作成するには、ファイルを作成、`.fsx`拡張機能の例では、 `tables.fsx`、F# 開発環境にします。</span><span class="sxs-lookup"><span data-stu-id="44a67-126">To create an F# script, create a file with the `.fsx` extension, for example `tables.fsx`, in your F# development environment.</span></span>

<span data-ttu-id="44a67-127">次に、使用、[パッケージ マネージャー](package-management.md)など[パケット](https://fsprojects.github.io/Paket/)または[NuGet](https://www.nuget.org/)をインストールする、`WindowsAzure.Storage`パッケージと参照`WindowsAzure.Storage.dll`を使用して、スクリプトで`#r`ディレクティブ。</span><span class="sxs-lookup"><span data-stu-id="44a67-127">Next, use a [package manager](package-management.md) such as [Paket](https://fsprojects.github.io/Paket/) or [NuGet](https://www.nuget.org/) to install the `WindowsAzure.Storage` package and reference `WindowsAzure.Storage.dll` in your script using a `#r` directive.</span></span> <span data-ttu-id="44a67-128">用にもう一度やって`Microsoft.WindowsAzure.ConfigurationManager`Microsoft.Azure 名前空間を取得するためにします。</span><span class="sxs-lookup"><span data-stu-id="44a67-128">Do it again for `Microsoft.WindowsAzure.ConfigurationManager` in order to get the Microsoft.Azure namespace.</span></span>

### <a name="add-namespace-declarations"></a><span data-ttu-id="44a67-129">名前空間宣言を追加します。</span><span class="sxs-lookup"><span data-stu-id="44a67-129">Add namespace declarations</span></span>

<span data-ttu-id="44a67-130">次の追加`open`ステートメントの先頭に、`tables.fsx`ファイル。</span><span class="sxs-lookup"><span data-stu-id="44a67-130">Add the following `open` statements to the top of the `tables.fsx` file:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L1-L5)]

### <a name="get-your-azure-storage-connection-string"></a><span data-ttu-id="44a67-131">Azure Storage 接続文字列を取得します。</span><span class="sxs-lookup"><span data-stu-id="44a67-131">Get your Azure Storage connection string</span></span>

<span data-ttu-id="44a67-132">Azure Storage Table service に接続する場合は、このチュートリアルでは、接続文字列を必要があります。</span><span class="sxs-lookup"><span data-stu-id="44a67-132">If you're connecting to Azure Storage Table service, you'll need your connection string for this tutorial.</span></span> <span data-ttu-id="44a67-133">Azure portal から接続文字列をコピーすることができます。</span><span class="sxs-lookup"><span data-stu-id="44a67-133">You can copy your connection string from the Azure portal.</span></span> <span data-ttu-id="44a67-134">接続文字列の詳細については、次を参照してください。[ストレージ接続文字列を構成](/azure/storage/storage-configure-connection-string)します。</span><span class="sxs-lookup"><span data-stu-id="44a67-134">For more information about connection strings, see [Configure Storage Connection Strings](/azure/storage/storage-configure-connection-string).</span></span>

### <a name="get-your-azure-cosmos-db-connection-string"></a><span data-ttu-id="44a67-135">Azure Cosmos DB 接続文字列を取得します。</span><span class="sxs-lookup"><span data-stu-id="44a67-135">Get your Azure Cosmos DB connection string</span></span>

<span data-ttu-id="44a67-136">Azure Cosmos DB に接続する場合は、このチュートリアルでは、接続文字列を必要があります。</span><span class="sxs-lookup"><span data-stu-id="44a67-136">If you're connecting to Azure Cosmos DB, you'll need your connection string for this tutorial.</span></span> <span data-ttu-id="44a67-137">Azure portal から接続文字列をコピーすることができます。</span><span class="sxs-lookup"><span data-stu-id="44a67-137">You can copy your connection string from the Azure portal.</span></span> <span data-ttu-id="44a67-138">Cosmos DB アカウントに、Azure portal に移動**設定** > **接続文字列**、 をクリックし、**コピー**プライマリ接続をコピーする ボタン文字列。</span><span class="sxs-lookup"><span data-stu-id="44a67-138">In the Azure portal, in your Cosmos DB account, go to **Settings** > **Connection String**, and click the **Copy** button to copy your Primary Connection String.</span></span> 

<span data-ttu-id="44a67-139">このチュートリアルでは、次の例のように、スクリプトで、接続文字列を入力します。</span><span class="sxs-lookup"><span data-stu-id="44a67-139">For the tutorial, enter your connection string in your script, like the following example:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L11-L11)]

<span data-ttu-id="44a67-140">ただし、これは**しないで**の実際のプロジェクト。</span><span class="sxs-lookup"><span data-stu-id="44a67-140">However, this is **not recommended** for real projects.</span></span> <span data-ttu-id="44a67-141">ストレージ アカウント キーは、ストレージ アカウントの root パスワードに似ています。</span><span class="sxs-lookup"><span data-stu-id="44a67-141">Your storage account key is similar to the root password for your storage account.</span></span> <span data-ttu-id="44a67-142">常に、ストレージ アカウント キーを保護するように注意します。</span><span class="sxs-lookup"><span data-stu-id="44a67-142">Always be careful to protect your storage account key.</span></span> <span data-ttu-id="44a67-143">ハード コーディング、または他のユーザーにアクセスできるプレーン テキスト ファイルに保存することは、他のユーザーに配布しないでください。</span><span class="sxs-lookup"><span data-stu-id="44a67-143">Avoid distributing it to other users, hard-coding it, or saving it in a plain-text file that is accessible to others.</span></span> <span data-ttu-id="44a67-144">侵害されていると思われる場合は、Azure Portal を使用して、キーを再生成することができます。</span><span class="sxs-lookup"><span data-stu-id="44a67-144">You can regenerate your key using the Azure Portal if you believe it may have been compromised.</span></span>

<span data-ttu-id="44a67-145">実際のアプリケーションは、ストレージ接続文字列を維持するために最善の方法は、構成ファイルです。</span><span class="sxs-lookup"><span data-stu-id="44a67-145">For real applications, the best way to maintain your storage connection string is in a configuration file.</span></span> <span data-ttu-id="44a67-146">構成ファイルから接続文字列を取得するには、は、これを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="44a67-146">To fetch the connection string from a configuration file, you can do this:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L13-L15)]

<span data-ttu-id="44a67-147">Azure Configuration Manager の使用は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="44a67-147">Using Azure Configuration Manager is optional.</span></span> <span data-ttu-id="44a67-148">.NET Framework のなどの API を使用することもできます。`ConfigurationManager`型。</span><span class="sxs-lookup"><span data-stu-id="44a67-148">You can also use an API such as the .NET Framework's `ConfigurationManager` type.</span></span>

### <a name="parse-the-connection-string"></a><span data-ttu-id="44a67-149">接続文字列を解析します。</span><span class="sxs-lookup"><span data-stu-id="44a67-149">Parse the connection string</span></span>

<span data-ttu-id="44a67-150">接続文字列を解析するには、次のように使用します。</span><span class="sxs-lookup"><span data-stu-id="44a67-150">To parse the connection string, use:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L21-L22)]

<span data-ttu-id="44a67-151">これにより返されます、`CloudStorageAccount`します。</span><span class="sxs-lookup"><span data-stu-id="44a67-151">This returns a `CloudStorageAccount`.</span></span>

### <a name="create-the-table-service-client"></a><span data-ttu-id="44a67-152">Table service クライアントを作成します。</span><span class="sxs-lookup"><span data-stu-id="44a67-152">Create the Table service client</span></span>

<span data-ttu-id="44a67-153">`CloudTableClient`クラスでは、テーブルとテーブル ストレージ内のエンティティを取得することができます。</span><span class="sxs-lookup"><span data-stu-id="44a67-153">The `CloudTableClient` class enables you to retrieve tables and entities in Table storage.</span></span> <span data-ttu-id="44a67-154">サービス クライアントを作成する方法の 1 つを次に示します。</span><span class="sxs-lookup"><span data-stu-id="44a67-154">Here's one way to create the service client:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L28-L29)]

<span data-ttu-id="44a67-155">データを読み取るし、Table storage にデータを書き込むコードを記述する準備が整いました。</span><span class="sxs-lookup"><span data-stu-id="44a67-155">Now you are ready to write code that reads data from and writes data to Table storage.</span></span>

### <a name="create-a-table"></a><span data-ttu-id="44a67-156">テーブルの作成</span><span class="sxs-lookup"><span data-stu-id="44a67-156">Create a table</span></span>

<span data-ttu-id="44a67-157">この例では、存在しない場合は、テーブルを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="44a67-157">This example shows how to create a table if it does not already exist:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L35-L39)]

### <a name="add-an-entity-to-a-table"></a><span data-ttu-id="44a67-158">エンティティをテーブルに追加します。</span><span class="sxs-lookup"><span data-stu-id="44a67-158">Add an entity to a table</span></span>

<span data-ttu-id="44a67-159">継承する型を持つエンティティがある`TableEntity`します。</span><span class="sxs-lookup"><span data-stu-id="44a67-159">An entity has to have a type that inherits from `TableEntity`.</span></span> <span data-ttu-id="44a67-160">拡張する`TableEntity`、好きなように、型*する必要があります*パラメーターなしのコンス トラクターします。</span><span class="sxs-lookup"><span data-stu-id="44a67-160">You can extend `TableEntity` in any way you like, but your type *must* have a parameter-less constructor.</span></span> <span data-ttu-id="44a67-161">両方があるプロパティのみ`get`と`set`Azure テーブルに格納されます。</span><span class="sxs-lookup"><span data-stu-id="44a67-161">Only properties that have both `get` and `set` are stored in your Azure Table.</span></span>

<span data-ttu-id="44a67-162">エンティティのパーティション キーと行キーは、テーブル内のエンティティを一意に識別します。</span><span class="sxs-lookup"><span data-stu-id="44a67-162">An entity's partition and row key uniquely identify the entity in the table.</span></span> <span data-ttu-id="44a67-163">同じパーティション キーを持つエンティティは、別のパーティション キーを持つよりも迅速に照会できますが、並列操作のスケーラビリティが向上により、多様なパーティション キーを使用します。</span><span class="sxs-lookup"><span data-stu-id="44a67-163">Entities with the same partition key can be queried faster than those with different partition keys, but using diverse partition keys allows for greater scalability of parallel operations.</span></span>

<span data-ttu-id="44a67-164">次の例に示します、`Customer`を使用して、`lastName`パーティション キーとして、`firstName`行キーとして。</span><span class="sxs-lookup"><span data-stu-id="44a67-164">Here's an example of a `Customer` that uses the `lastName` as the partition key and the `firstName` as the row key.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L45-L52)]

<span data-ttu-id="44a67-165">ここで追加`Customer`テーブルにします。</span><span class="sxs-lookup"><span data-stu-id="44a67-165">Now add `Customer` to the table.</span></span> <span data-ttu-id="44a67-166">これを行うには、作成、`TableOperation`テーブルでを実行します。</span><span class="sxs-lookup"><span data-stu-id="44a67-166">To do so, create a `TableOperation` that executes on the table.</span></span> <span data-ttu-id="44a67-167">この場合、作成、`Insert`操作。</span><span class="sxs-lookup"><span data-stu-id="44a67-167">In this case, you create an `Insert` operation.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L54-L55)]

### <a name="insert-a-batch-of-entities"></a><span data-ttu-id="44a67-168">エンティティのバッチを挿入します。</span><span class="sxs-lookup"><span data-stu-id="44a67-168">Insert a batch of entities</span></span>

<span data-ttu-id="44a67-169">エンティティのバッチは、1 回の書き込み操作を使用してテーブルに挿入できます。</span><span class="sxs-lookup"><span data-stu-id="44a67-169">You can insert a batch of entities into a table using a single write operation.</span></span> <span data-ttu-id="44a67-170">バッチ操作は、操作を 1 回の実行にまとめることができますが、いくつかの制限。</span><span class="sxs-lookup"><span data-stu-id="44a67-170">Batch operations allow you to combine operations into a single execution, but they have some restrictions:</span></span>

- <span data-ttu-id="44a67-171">更新プログラムを実行する削除、および同じバッチ操作に挿入します。</span><span class="sxs-lookup"><span data-stu-id="44a67-171">You can perform updates, deletes, and inserts in the same batch operation.</span></span>
- <span data-ttu-id="44a67-172">バッチ操作では、最大 100 個のエンティティを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="44a67-172">A batch operation can include up to 100 entities.</span></span>
- <span data-ttu-id="44a67-173">すべてのエンティティをバッチ操作で同じパーティション キーが必要です。</span><span class="sxs-lookup"><span data-stu-id="44a67-173">All entities in a batch operation must have the same partition key.</span></span>
- <span data-ttu-id="44a67-174">バッチ操作でクエリを実行することはできますが、バッチ内の唯一の操作があります。</span><span class="sxs-lookup"><span data-stu-id="44a67-174">While it is possible to perform a query in a batch operation, it must be the only operation in the batch.</span></span>

<span data-ttu-id="44a67-175">2 つの挿入をバッチ操作に結合したいくつかのコードを次に示します。</span><span class="sxs-lookup"><span data-stu-id="44a67-175">Here's some code that combines two inserts into a batch operation:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L62-L71)]

### <a name="retrieve-all-entities-in-a-partition"></a><span data-ttu-id="44a67-176">パーティション内のすべてのエンティティを取得します。</span><span class="sxs-lookup"><span data-stu-id="44a67-176">Retrieve all entities in a partition</span></span>

<span data-ttu-id="44a67-177">テーブルに対してパーティション内のすべてのエンティティを照会するを使用して、`TableQuery`オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="44a67-177">To query a table for all entities in a partition, use a `TableQuery` object.</span></span> <span data-ttu-id="44a67-178">ここでは、フィルター処理するエンティティをパーティション キーは、"Smith"。</span><span class="sxs-lookup"><span data-stu-id="44a67-178">Here, you filter for entities where "Smith" is the partition key.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L77-L82)]

<span data-ttu-id="44a67-179">結果を印刷するようになりました。</span><span class="sxs-lookup"><span data-stu-id="44a67-179">You now print the results:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L84-L85)]


### <a name="retrieve-a-range-of-entities-in-a-partition"></a><span data-ttu-id="44a67-180">パーティション内のエンティティの範囲を取得します。</span><span class="sxs-lookup"><span data-stu-id="44a67-180">Retrieve a range of entities in a partition</span></span>

<span data-ttu-id="44a67-181">パーティション内のすべてのエンティティのクエリを実行しない場合は、パーティション キー フィルターと行キー フィルターを組み合わせることで、範囲を指定できます。</span><span class="sxs-lookup"><span data-stu-id="44a67-181">If you don't want to query all the entities in a partition, you can specify a range by combining the partition key filter with a row key filter.</span></span> <span data-ttu-id="44a67-182">ここでは、フィルターを使用する 2 つ、"Smith"パーティション内のすべてのエンティティを取得するのに、行キー (名) 文字から始まり、アルファベットの"M"よりも前。</span><span class="sxs-lookup"><span data-stu-id="44a67-182">Here, you use two filters to get all entities in the "Smith" partition where the row key (first name) starts with a letter earlier than "M" in the alphabet.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L91-L100)]

<span data-ttu-id="44a67-183">結果を印刷するようになりました。</span><span class="sxs-lookup"><span data-stu-id="44a67-183">You now print the results:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L102-L103)]

### <a name="retrieve-a-single-entity"></a><span data-ttu-id="44a67-184">1 つのエンティティを取得します。</span><span class="sxs-lookup"><span data-stu-id="44a67-184">Retrieve a single entity</span></span>

<span data-ttu-id="44a67-185">1 つの特定のエンティティを取得するクエリを記述することができます。</span><span class="sxs-lookup"><span data-stu-id="44a67-185">You can write a query to retrieve a single, specific entity.</span></span> <span data-ttu-id="44a67-186">ここを使用する、 `TableOperation` "Ben Smith"というユーザーを指定します。</span><span class="sxs-lookup"><span data-stu-id="44a67-186">Here, you use a `TableOperation` to specify the customer "Ben Smith".</span></span> <span data-ttu-id="44a67-187">コレクションではなく、得られる、`Customer`します。</span><span class="sxs-lookup"><span data-stu-id="44a67-187">Instead of a collection, you get back a `Customer`.</span></span> <span data-ttu-id="44a67-188">Table service から単一のエンティティを取得する最も簡単な方法は、クエリでパーティション キーと行キーの両方を指定します。</span><span class="sxs-lookup"><span data-stu-id="44a67-188">Specifying both the partition key and the row key in a query is the fastest way to retrieve a single entity from the Table service.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L109-L111)]

<span data-ttu-id="44a67-189">結果を印刷するようになりました。</span><span class="sxs-lookup"><span data-stu-id="44a67-189">You now print the results:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L113-L115)]


### <a name="replace-an-entity"></a><span data-ttu-id="44a67-190">エンティティを置換します。</span><span class="sxs-lookup"><span data-stu-id="44a67-190">Replace an entity</span></span>

<span data-ttu-id="44a67-191">エンティティを更新するには、テーブル サービスから取得し、エンティティ オブジェクトを変更および変更を保存して、サービスを使用してテーブルに、`Replace`操作。</span><span class="sxs-lookup"><span data-stu-id="44a67-191">To update an entity, retrieve it from the Table service, modify the entity object, and then save the changes back to the Table service using a `Replace` operation.</span></span> <span data-ttu-id="44a67-192">これにより、操作に失敗する場合、取得した後、サーバー上のエンティティを変更しない限り、サーバーが完全に置換するエンティティ。</span><span class="sxs-lookup"><span data-stu-id="44a67-192">This causes the entity to be fully replaced on the server, unless the entity on the server has changed since it was retrieved, in which case the operation fails.</span></span> <span data-ttu-id="44a67-193">このエラーは、アプリケーションが他のソースからの変更を誤って上書きを防止します。</span><span class="sxs-lookup"><span data-stu-id="44a67-193">This failure is to prevent your application from inadvertently overwriting changes from other sources.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L121-L128)]

### <a name="insert-or-replace-an-entity"></a><span data-ttu-id="44a67-194">エンティティを挿入または置換</span><span class="sxs-lookup"><span data-stu-id="44a67-194">Insert-or-replace an entity</span></span>

<span data-ttu-id="44a67-195">場合によっては、テーブルにエンティティが存在するかどうかがわからない。</span><span class="sxs-lookup"><span data-stu-id="44a67-195">Sometimes, you don't know whether an entity exists in the table.</span></span> <span data-ttu-id="44a67-196">それに格納されている現在の値が不要になった場合は、します。</span><span class="sxs-lookup"><span data-stu-id="44a67-196">And if it does, the current values stored in it are no longer needed.</span></span> <span data-ttu-id="44a67-197">使用することができます`InsertOrReplace`に、エンティティを作成するか、その状態に関係なく、ユーザーが存在する場合に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="44a67-197">You can use `InsertOrReplace` to create the entity, or replace it if it exists, regardless of its state.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L134-L141)]

### <a name="query-a-subset-of-entity-properties"></a><span data-ttu-id="44a67-198">エンティティのプロパティのサブセットを照会します。</span><span class="sxs-lookup"><span data-stu-id="44a67-198">Query a subset of entity properties</span></span>

<span data-ttu-id="44a67-199">テーブル クエリでは、それらのすべてではなく、エンティティからプロパティをいくつかを取得できます。</span><span class="sxs-lookup"><span data-stu-id="44a67-199">A table query can retrieve just a few properties from an entity instead of all of them.</span></span> <span data-ttu-id="44a67-200">この手法は、プロジェクションと呼ばれるには、特に大規模なエンティティの場合のクエリ パフォーマンスを向上できます。</span><span class="sxs-lookup"><span data-stu-id="44a67-200">This technique, called projection, can improve query performance, especially for large entities.</span></span> <span data-ttu-id="44a67-201">ここを使用して電子メールにのみのアドレスを返す`DynamicTableEntity`と`EntityResolver`します。</span><span class="sxs-lookup"><span data-stu-id="44a67-201">Here, you return only email addresses using `DynamicTableEntity` and `EntityResolver`.</span></span> <span data-ttu-id="44a67-202">Table service でアカウントを使用している場合にのみ、このコードが実行されるように、プロジェクションは、ローカル ストレージ エミュレーターでサポートされないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="44a67-202">Note that projection is not supported on the local storage emulator, so this code runs only when you're using an account on the Table service.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L147-L158)]

### <a name="retrieve-entities-in-pages-asynchronously"></a><span data-ttu-id="44a67-203">ページ内のエンティティを非同期的に取得します。</span><span class="sxs-lookup"><span data-stu-id="44a67-203">Retrieve entities in pages asynchronously</span></span>

<span data-ttu-id="44a67-204">多数のエンティティを読み取るし、それらすべてで返されるを待機しているのではなく、取得されるようにそれらを処理する場合は、セグメント化されたクエリを使用できます。</span><span class="sxs-lookup"><span data-stu-id="44a67-204">If you are reading a large number of entities, and you want to process them as they are retrieved rather than waiting for them all to return, you can use a segmented query.</span></span> <span data-ttu-id="44a67-205">ここでは、結果は、返される結果の大規模なセットを待っている間に実行がブロックされないように、非同期ワークフローを使用してにページに返します。</span><span class="sxs-lookup"><span data-stu-id="44a67-205">Here, you return results in pages by using an async workflow so that execution is not blocked while you're waiting for a large set of results to return.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L163-L178)]

<span data-ttu-id="44a67-206">今すぐ実行するこの計算に同期的に。</span><span class="sxs-lookup"><span data-stu-id="44a67-206">You now execute this computation synchronously:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L180-L180)]

### <a name="delete-an-entity"></a><span data-ttu-id="44a67-207">エンティティを削除します。</span><span class="sxs-lookup"><span data-stu-id="44a67-207">Delete an entity</span></span>

<span data-ttu-id="44a67-208">取得した後は、エンティティを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="44a67-208">You can delete an entity after you have retrieved it.</span></span> <span data-ttu-id="44a67-209">エンティティを更新する場合と同様には取得した後にエンティティが変更される場合が失敗しました。</span><span class="sxs-lookup"><span data-stu-id="44a67-209">As with updating an entity, this fails if the entity has changed since you retrieved it.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L186-L187)]

### <a name="delete-a-table"></a><span data-ttu-id="44a67-210">テーブルを削除します。</span><span class="sxs-lookup"><span data-stu-id="44a67-210">Delete a table</span></span>

<span data-ttu-id="44a67-211">ストレージ アカウントからテーブルを削除できます。</span><span class="sxs-lookup"><span data-stu-id="44a67-211">You can delete a table from a storage account.</span></span> <span data-ttu-id="44a67-212">削除されたテーブルは、削除を後の一定期間の再作成するできなくなります。</span><span class="sxs-lookup"><span data-stu-id="44a67-212">A table that has been deleted will be unavailable to be re-created for a period of time following the deletion.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L193-L193)]

## <a name="next-steps"></a><span data-ttu-id="44a67-213">次の手順</span><span class="sxs-lookup"><span data-stu-id="44a67-213">Next steps</span></span>

<span data-ttu-id="44a67-214">これで、Table storage の基本を学習する次のリンクより複雑なストレージ タスクと、Azure Cosmos DB Table API について説明します。</span><span class="sxs-lookup"><span data-stu-id="44a67-214">Now that you've learned the basics of Table storage, follow these links to learn about more complex storage tasks and the Azure Cosmos DB Table API.</span></span>

- [<span data-ttu-id="44a67-215">Azure Cosmos DB Table API の概要</span><span class="sxs-lookup"><span data-stu-id="44a67-215">Introduction to Azure Cosmos DB Table API</span></span>](https://docs.microsoft.com/azure/cosmos-db/table-introduction)
- [<span data-ttu-id="44a67-216">.NET リファレンス用ストレージ クライアント ライブラリ</span><span class="sxs-lookup"><span data-stu-id="44a67-216">Storage Client Library for .NET reference</span></span>](https://docs.microsoft.com/dotnet/api/overview/azure/storage?view=azure-dotnet)
- [<span data-ttu-id="44a67-217">Azure Storage 型プロバイダー</span><span class="sxs-lookup"><span data-stu-id="44a67-217">Azure Storage Type Provider</span></span>](http://fsprojects.github.io/AzureStorageTypeProvider/)
- [<span data-ttu-id="44a67-218">Azure Storage チーム ブログ</span><span class="sxs-lookup"><span data-stu-id="44a67-218">Azure Storage Team Blog</span></span>](https://blogs.msdn.com/b/windowsazurestorage/)
- [<span data-ttu-id="44a67-219">接続文字列の構成</span><span class="sxs-lookup"><span data-stu-id="44a67-219">Configuring Connection Strings</span></span>](https://docs.microsoft.com/azure/storage/common/storage-configure-connection-string)
- [<span data-ttu-id="44a67-220">.NET で Azure Table Storage の概要</span><span class="sxs-lookup"><span data-stu-id="44a67-220">Getting Started with Azure Table Storage in .NET</span></span>](https://azure.microsoft.com/resources/samples/storage-table-dotnet-getting-started/)
