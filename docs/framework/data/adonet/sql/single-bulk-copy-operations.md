---
title: バルク コピー操作の単一実行
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5e7ff0be-3f23-4996-a92c-bd54d65c3836
ms.openlocfilehash: 274a6e87b272002a567fd92605c4e690c03b6e26
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2018
ms.locfileid: "44271011"
---
# <a name="single-bulk-copy-operations"></a><span data-ttu-id="34fc2-102">バルク コピー操作の単一実行</span><span class="sxs-lookup"><span data-stu-id="34fc2-102">Single Bulk Copy Operations</span></span>
<span data-ttu-id="34fc2-103">SQL Server のバルク コピー操作を実行する簡単な方法は、データベースに対して単一操作を実行することです。</span><span class="sxs-lookup"><span data-stu-id="34fc2-103">The simplest approach to performing a SQL Server bulk copy operation is to perform a single operation against a database.</span></span> <span data-ttu-id="34fc2-104">既定では、バルク コピー操作は分離された操作として実行されます。このコピー操作は非トランザクション方式で処理され、ロールバックできません。</span><span class="sxs-lookup"><span data-stu-id="34fc2-104">By default, a bulk copy operation is performed as an isolated operation: the copy operation occurs in a non-transacted way, with no opportunity for rolling it back.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="34fc2-105">エラーの発生時に、バルク コピー処理の全部または一部をロールバックする必要がある場合は、<xref:System.Data.SqlClient.SqlBulkCopy> が管理するトランザクションを使用するか、または既存のトランザクション内でバルク コピー操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="34fc2-105">If you need to roll back all or part of the bulk copy when an error occurs, you can either use a <xref:System.Data.SqlClient.SqlBulkCopy>-managed transaction, or perform the bulk copy operation within an existing transaction.</span></span> <span data-ttu-id="34fc2-106">**SqlBulkCopy**はでも動作<xref:System.Transactions>かどうか、接続が参加している (暗黙的または明示的に) に、 **System.Transactions**トランザクション。</span><span class="sxs-lookup"><span data-stu-id="34fc2-106">**SqlBulkCopy** will also work with <xref:System.Transactions> if the connection is enlisted (implicitly or explicitly) into a **System.Transactions** transaction.</span></span>  
>   
>  <span data-ttu-id="34fc2-107">詳細については、次を参照してください。[トランザクションとバルク コピー操作](../../../../../docs/framework/data/adonet/sql/transaction-and-bulk-copy-operations.md)します。</span><span class="sxs-lookup"><span data-stu-id="34fc2-107">For more information, see [Transaction and Bulk Copy Operations](../../../../../docs/framework/data/adonet/sql/transaction-and-bulk-copy-operations.md).</span></span>  
  
 <span data-ttu-id="34fc2-108">通常、バルク コピー操作の実行手順は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="34fc2-108">The general steps for performing a bulk copy operation are as follows:</span></span>  
  
1.  <span data-ttu-id="34fc2-109">コピー元のサーバーに接続し、コピーするデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="34fc2-109">Connect to the source server and obtain the data to be copied.</span></span> <span data-ttu-id="34fc2-110"><xref:System.Data.IDataReader> オブジェクトまたは <xref:System.Data.DataTable> オブジェクトからデータを取得できる場合は、他のソースからデータを取得して利用することもできます。</span><span class="sxs-lookup"><span data-stu-id="34fc2-110">Data can also come from other sources, if it can be retrieved from an <xref:System.Data.IDataReader> or <xref:System.Data.DataTable> object.</span></span>  
  
2.  <span data-ttu-id="34fc2-111">移行先サーバーに接続 (する場合を除き、 **SqlBulkCopy**の接続を確立するために)。</span><span class="sxs-lookup"><span data-stu-id="34fc2-111">Connect to the destination server (unless you want **SqlBulkCopy** to establish a connection for you).</span></span>  
  
3.  <span data-ttu-id="34fc2-112"><xref:System.Data.SqlClient.SqlBulkCopy> オブジェクトを作成し、必要なプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="34fc2-112">Create a <xref:System.Data.SqlClient.SqlBulkCopy> object, setting any necessary properties.</span></span>  
  
4.  <span data-ttu-id="34fc2-113">設定、 **DestinationTableName**を一括の対象テーブルを示すプロパティが操作を挿入します。</span><span class="sxs-lookup"><span data-stu-id="34fc2-113">Set the **DestinationTableName** property to indicate the target table for the bulk insert operation.</span></span>  
  
5.  <span data-ttu-id="34fc2-114">1 つを呼び出して、 **WriteToServer**メソッド。</span><span class="sxs-lookup"><span data-stu-id="34fc2-114">Call one of the **WriteToServer** methods.</span></span>  
  
6.  <span data-ttu-id="34fc2-115">プロパティと呼び出しを必要に応じて、更新**WriteToServer**必要に応じて、もう一度です。</span><span class="sxs-lookup"><span data-stu-id="34fc2-115">Optionally, update properties and call **WriteToServer** again as necessary.</span></span>  
  
7.  <span data-ttu-id="34fc2-116"><xref:System.Data.SqlClient.SqlBulkCopy.Close%2A> を呼び出すか、または `Using` ステートメント内にバルク コピー操作をラップします。</span><span class="sxs-lookup"><span data-stu-id="34fc2-116">Call <xref:System.Data.SqlClient.SqlBulkCopy.Close%2A>, or wrap the bulk copy operations within a `Using` statement.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="34fc2-117">コピー元とコピー先の列のデータ型を一致させることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="34fc2-117">We recommend that the source and target column data types match.</span></span> <span data-ttu-id="34fc2-118">データ型が一致しない場合**SqlBulkCopy**で採用されている規則を使用して、対象のデータ型への各ソース値の変換を試みます<xref:System.Data.SqlClient.SqlParameter.Value%2A>します。</span><span class="sxs-lookup"><span data-stu-id="34fc2-118">If the data types do not match, **SqlBulkCopy** attempts to convert each source value to the target data type, using the rules employed by <xref:System.Data.SqlClient.SqlParameter.Value%2A>.</span></span> <span data-ttu-id="34fc2-119">この変換はパフォーマンスに影響を及ぼし、予期しないエラーが発生することもあります。</span><span class="sxs-lookup"><span data-stu-id="34fc2-119">Conversions can affect performance, and also can result in unexpected errors.</span></span> <span data-ttu-id="34fc2-120">たとえば、`Double` データ型は、多くの場合 `Decimal` データ型に変換されますが、常にというわけではありません。</span><span class="sxs-lookup"><span data-stu-id="34fc2-120">For example, a `Double` data type can be converted to a `Decimal` data type most of the time, but not always.</span></span>  
  
## <a name="example"></a><span data-ttu-id="34fc2-121">例</span><span class="sxs-lookup"><span data-stu-id="34fc2-121">Example</span></span>  
 <span data-ttu-id="34fc2-122">次のコンソール アプリケーションでは、<xref:System.Data.SqlClient.SqlBulkCopy> クラスを使用してデータを読み込む方法について示しています。</span><span class="sxs-lookup"><span data-stu-id="34fc2-122">The following console application demonstrates how to load data using the <xref:System.Data.SqlClient.SqlBulkCopy> class.</span></span> <span data-ttu-id="34fc2-123">この例で、<xref:System.Data.SqlClient.SqlDataReader>からデータをコピーするために使用、 **Production.Product** SQL Server のテーブル**AdventureWorks**データベースを同じデータベース内の同等のテーブル。</span><span class="sxs-lookup"><span data-stu-id="34fc2-123">In this example, a <xref:System.Data.SqlClient.SqlDataReader> is used to copy data from the **Production.Product** table in the SQL Server**AdventureWorks** database to a similar table in the same database.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="34fc2-124">このサンプルでは」の説明に従って、作業テーブルを作成していない限りは実行されません[バルク コピー サンプルのセットアップ](../../../../../docs/framework/data/adonet/sql/bulk-copy-example-setup.md)します。</span><span class="sxs-lookup"><span data-stu-id="34fc2-124">This sample will not run unless you have created the work tables as described in [Bulk Copy Example Setup](../../../../../docs/framework/data/adonet/sql/bulk-copy-example-setup.md).</span></span> <span data-ttu-id="34fc2-125">使用する構文を示すためにこのコードが提供される**SqlBulkCopy**のみです。</span><span class="sxs-lookup"><span data-stu-id="34fc2-125">This code is provided to demonstrate the syntax for using **SqlBulkCopy** only.</span></span> <span data-ttu-id="34fc2-126">コピー元およびコピー先のテーブルが同一の SQL Server インスタンス内に存在する場合、Transact-SQL `INSERT … SELECT` ステートメントを使用すれば簡単かつ高速にデータをコピーすることができます。</span><span class="sxs-lookup"><span data-stu-id="34fc2-126">If the source and destination tables are located in the same SQL Server instance, it is easier and faster to use a Transact-SQL `INSERT … SELECT` statement to copy the data.</span></span>  
  
 [!code-csharp[DataWorks BulkCopy.Single#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks BulkCopy.Single/CS/source.cs#1)]
 [!code-vb[DataWorks BulkCopy.Single#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks BulkCopy.Single/VB/source.vb#1)]  
  
## <a name="performing-a-bulk-copy-operation-using-transact-sql-and-the-command-class"></a><span data-ttu-id="34fc2-127">Transact-SQL および Command クラスを使用したバルク コピー操作の実行</span><span class="sxs-lookup"><span data-stu-id="34fc2-127">Performing a Bulk Copy Operation Using Transact-SQL and the Command Class</span></span>  
 <span data-ttu-id="34fc2-128">次の例では、BULK INSERT ステートメントを実行する <xref:System.Data.SqlClient.SqlCommand.ExecuteNonQuery%2A> メソッドの使用方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="34fc2-128">The following example illustrates how to use the <xref:System.Data.SqlClient.SqlCommand.ExecuteNonQuery%2A> method to execute the BULK INSERT statement.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="34fc2-129">データ ソースのファイル パスはサーバーに対する相対パスです。</span><span class="sxs-lookup"><span data-stu-id="34fc2-129">The file path for the data source is relative to the server.</span></span> <span data-ttu-id="34fc2-130">サーバー プロセスがこのパスにアクセスできないと、バルク コピー操作は失敗します。</span><span class="sxs-lookup"><span data-stu-id="34fc2-130">The server process must have access to that path in order for the bulk copy operation to succeed.</span></span>  
  
```vb  
Using connection As SqlConnection = New SqlConnection(connectionString)  
Dim queryString As String = _  
    "BULK INSERT Northwind.dbo.[Order Details] FROM " & _  
    "'f:\mydata\data.tbl' WITH (FORMATFILE='f:\mydata\data.fmt' )"  
connection.Open()  
SqlCommand command = New SqlCommand(queryString, connection);  
  
command.ExecuteNonQuery()  
End Using  
```  
  
```csharp  
using (SqlConnection connection = New SqlConnection(connectionString))  
{  
string queryString =  "BULK INSERT Northwind.dbo.[Order Details] " +  
    "FROM 'f:\mydata\data.tbl' " +  
    "WITH ( FORMATFILE='f:\mydata\data.fmt' )";  
connection.Open();  
SqlCommand command = new SqlCommand(queryString, connection);  
  
command.ExecuteNonQuery();  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="34fc2-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="34fc2-131">See Also</span></span>  
 [<span data-ttu-id="34fc2-132">SQL Server でのバルク コピー操作</span><span class="sxs-lookup"><span data-stu-id="34fc2-132">Bulk Copy Operations in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/bulk-copy-operations-in-sql-server.md)  
 [<span data-ttu-id="34fc2-133">ADO.NET のマネージド プロバイダーと DataSet デベロッパー センター</span><span class="sxs-lookup"><span data-stu-id="34fc2-133">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
