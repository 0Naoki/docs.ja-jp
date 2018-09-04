---
title: ADO.NET のコード例
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c119657a-9ce6-4940-91e4-ac1d5f0d9584
ms.openlocfilehash: 93cc0cf34d2bba23ff0938c8c13d7343d665192d
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "43552968"
---
# <a name="adonet-code-examples"></a><span data-ttu-id="57fc0-102">ADO.NET のコード例</span><span class="sxs-lookup"><span data-stu-id="57fc0-102">ADO.NET code examples</span></span>
<span data-ttu-id="57fc0-103">このトピックにリストされたコードは、次の ADO.NET テクノロジを使用してデータベースからデータを取得する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="57fc0-103">The code listings in this topic demonstrate how to retrieve data from a database by using the following ADO.NET technologies:</span></span>

- <span data-ttu-id="57fc0-104">ADO.NET データ プロバイダー: </span><span class="sxs-lookup"><span data-stu-id="57fc0-104">ADO.NET data providers:</span></span>

  - <span data-ttu-id="57fc0-105">[SqlClient](#sqlclient) (`System.Data.SqlClient`)</span><span class="sxs-lookup"><span data-stu-id="57fc0-105">[SqlClient](#sqlclient) (`System.Data.SqlClient`)</span></span>

  - <span data-ttu-id="57fc0-106">[OleDb](#oledb) (`System.Data.OleDb`)</span><span class="sxs-lookup"><span data-stu-id="57fc0-106">[OleDb](#oledb) (`System.Data.OleDb`)</span></span>

  - <span data-ttu-id="57fc0-107">[Odbc](#odbc) (`System.Data.Odbc`)</span><span class="sxs-lookup"><span data-stu-id="57fc0-107">[Odbc](#odbc) (`System.Data.Odbc`)</span></span>

  - <span data-ttu-id="57fc0-108">[OracleClient](#oracleclient) (`System.Data.OracleClient`)</span><span class="sxs-lookup"><span data-stu-id="57fc0-108">[OracleClient](#oracleclient) (`System.Data.OracleClient`)</span></span>

- <span data-ttu-id="57fc0-109">ADO.NET Entity Framework:</span><span class="sxs-lookup"><span data-stu-id="57fc0-109">ADO.NET Entity Framework:</span></span>

  - [<span data-ttu-id="57fc0-110">LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="57fc0-110">LINQ to Entities</span></span>](#linq-to-entities)

  - [<span data-ttu-id="57fc0-111">型指定された ObjectQuery</span><span class="sxs-lookup"><span data-stu-id="57fc0-111">Typed ObjectQuery</span></span>](#typed-objectquery)

  - <span data-ttu-id="57fc0-112">[EntityClient](#entityclient) (`System.Data.EntityClient`)</span><span class="sxs-lookup"><span data-stu-id="57fc0-112">[EntityClient](#entityclient) (`System.Data.EntityClient`)</span></span>

- [<span data-ttu-id="57fc0-113">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="57fc0-113">LINQ to SQL</span></span>](#linq-to-sql)

## <a name="adonet-data-provider-examples"></a><span data-ttu-id="57fc0-114">ADO.NET データ プロバイダーの例</span><span class="sxs-lookup"><span data-stu-id="57fc0-114">ADO.NET data provider examples</span></span>
<span data-ttu-id="57fc0-115">以下に示した各コードは、ADO.NET データ プロバイダーを使用してデータベースからデータを取得する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="57fc0-115">The following code listings demonstrate how to retrieve data from a database using ADO.NET data providers.</span></span> <span data-ttu-id="57fc0-116">データは `DataReader` で返されます。</span><span class="sxs-lookup"><span data-stu-id="57fc0-116">The data is returned in a `DataReader`.</span></span> <span data-ttu-id="57fc0-117">詳細については、次を参照してください。 [DataReader によるデータの取得](../../../../docs/framework/data/adonet/retrieving-data-using-a-datareader.md)します。</span><span class="sxs-lookup"><span data-stu-id="57fc0-117">For more information, see [Retrieving Data Using a DataReader](../../../../docs/framework/data/adonet/retrieving-data-using-a-datareader.md).</span></span>

### <a name="sqlclient"></a><span data-ttu-id="57fc0-118">SqlClient</span><span class="sxs-lookup"><span data-stu-id="57fc0-118">SqlClient</span></span>
<span data-ttu-id="57fc0-119">この例では、コードに接続できることを前提としています、 `Northwind` Microsoft SQL Server のサンプル データベース。</span><span class="sxs-lookup"><span data-stu-id="57fc0-119">The code in this example assumes that you can connect to the `Northwind` sample database on Microsoft SQL Server.</span></span> <span data-ttu-id="57fc0-120">このコードは <xref:System.Data.SqlClient.SqlCommand> を作成してProducts テーブルから行を選択し、<xref:System.Data.SqlClient.SqlParameter> を追加して、結果を指定したパラメーター値 (この場合は 5) よりも大きな UnitPrice を持つ行に制限します。</span><span class="sxs-lookup"><span data-stu-id="57fc0-120">The code creates a <xref:System.Data.SqlClient.SqlCommand> to select rows from the Products table, adding a <xref:System.Data.SqlClient.SqlParameter> to restrict the results to rows with a UnitPrice greater than the specified parameter value, in this case 5.</span></span> <span data-ttu-id="57fc0-121"><xref:System.Data.SqlClient.SqlConnection>内部で開かれた、`using`によってリソースが閉じられ、コードが終了すると破棄は、ブロックします。</span><span class="sxs-lookup"><span data-stu-id="57fc0-121">The <xref:System.Data.SqlClient.SqlConnection> is opened inside a `using` block, which ensures that resources are closed and disposed when the code exits.</span></span> <span data-ttu-id="57fc0-122">コードは <xref:System.Data.SqlClient.SqlDataReader> を使用してコマンドを実行し、コンソール ウィンドウに結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="57fc0-122">The code executes the command by using a <xref:System.Data.SqlClient.SqlDataReader>, and displays the results in the console window.</span></span>

 [!code-csharp[DataWorks SampleApp.SqlClient#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SampleApp.SqlClient/CS/source.cs#1)]
 [!code-vb[DataWorks SampleApp.SqlClient#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SampleApp.SqlClient/VB/source.vb#1)]

### <a name="oledb"></a><span data-ttu-id="57fc0-123">OleDb</span><span class="sxs-lookup"><span data-stu-id="57fc0-123">OleDb</span></span>
<span data-ttu-id="57fc0-124">このコード例は、Microsoft Access の Northwind サンプル データベースに接続できることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="57fc0-124">The code in this example assumes that you can connect to the Microsoft Access Northwind sample database.</span></span> <span data-ttu-id="57fc0-125">このコードは <xref:System.Data.OleDb.OleDbCommand> を作成してProducts テーブルから行を選択し、<xref:System.Data.OleDb.OleDbParameter> を追加して、結果を指定したパラメーター値 (この場合は 5) よりも大きな UnitPrice を持つ行に制限します。</span><span class="sxs-lookup"><span data-stu-id="57fc0-125">The code creates a <xref:System.Data.OleDb.OleDbCommand> to select rows from the Products table, adding a <xref:System.Data.OleDb.OleDbParameter> to restrict the results to rows with a UnitPrice greater than the specified parameter value, in this case 5.</span></span> <span data-ttu-id="57fc0-126"><xref:System.Data.OleDb.OleDbConnection> は `using` ブロック内に開かれ、これによってコードが終了したときにリソースが閉じられ破棄されます。</span><span class="sxs-lookup"><span data-stu-id="57fc0-126">The <xref:System.Data.OleDb.OleDbConnection> is opened inside of a `using` block, which ensures that resources are closed and disposed when the code exits.</span></span> <span data-ttu-id="57fc0-127">コードは <xref:System.Data.OleDb.OleDbDataReader> を使用してコマンドを実行し、コンソール ウィンドウに結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="57fc0-127">The code executes the command by using a <xref:System.Data.OleDb.OleDbDataReader>, and displays the results in the console window.</span></span>

 [!code-csharp[DataWorks SampleApp.OleDb#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SampleApp.OleDb/CS/source.cs#1)]
 [!code-vb[DataWorks SampleApp.OleDb#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SampleApp.OleDb/VB/source.vb#1)]

### <a name="odbc"></a><span data-ttu-id="57fc0-128">Odbc</span><span class="sxs-lookup"><span data-stu-id="57fc0-128">Odbc</span></span>
<span data-ttu-id="57fc0-129">このコード例は、Microsoft Access の Northwind サンプル データベースに接続できることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="57fc0-129">The code in this example assumes that you can connect to the Microsoft Access Northwind sample database.</span></span> <span data-ttu-id="57fc0-130">このコードは <xref:System.Data.Odbc.OdbcCommand> を作成してProducts テーブルから行を選択し、<xref:System.Data.Odbc.OdbcParameter> を追加して、結果を指定したパラメーター値 (この場合は 5) よりも大きな UnitPrice を持つ行に制限します。</span><span class="sxs-lookup"><span data-stu-id="57fc0-130">The code creates a <xref:System.Data.Odbc.OdbcCommand> to select rows from the Products table, adding a <xref:System.Data.Odbc.OdbcParameter> to restrict the results to rows with a UnitPrice greater than the specified parameter value, in this case 5.</span></span> <span data-ttu-id="57fc0-131"><xref:System.Data.Odbc.OdbcConnection>内部で開かれた、`using`によってリソースが閉じられ、コードが終了すると破棄は、ブロックします。</span><span class="sxs-lookup"><span data-stu-id="57fc0-131">The <xref:System.Data.Odbc.OdbcConnection> is opened inside a `using` block, which ensures that resources are closed and disposed when the code exits.</span></span> <span data-ttu-id="57fc0-132">コードは <xref:System.Data.Odbc.OdbcDataReader> を使用してコマンドを実行し、コンソール ウィンドウに結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="57fc0-132">The code executes the command by using a <xref:System.Data.Odbc.OdbcDataReader>, and displays the results in the console window.</span></span>

[!code-csharp[DataWorks SampleApp.Odbc#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SampleApp.Odbc/CS/source.cs#1)] 
[!code-vb[DataWorks SampleApp.Odbc#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SampleApp.Odbc/VB/source.vb#1)] 

### <a name="oracleclient"></a><span data-ttu-id="57fc0-133">OracleClient</span><span class="sxs-lookup"><span data-stu-id="57fc0-133">OracleClient</span></span>
<span data-ttu-id="57fc0-134">このコード例では、Oracle サーバー上の DEMO.CUSTOMER との接続を前提としています。</span><span class="sxs-lookup"><span data-stu-id="57fc0-134">The code in this example assumes a connection to DEMO.CUSTOMER on an Oracle server.</span></span> <span data-ttu-id="57fc0-135">また、System.Data.OracleClient.dll への参照を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="57fc0-135">You must also add a reference to the System.Data.OracleClient.dll.</span></span> <span data-ttu-id="57fc0-136">このコードは、データを <xref:System.Data.OracleClient.OracleDataReader> で返します。</span><span class="sxs-lookup"><span data-stu-id="57fc0-136">The code returns the data in an <xref:System.Data.OracleClient.OracleDataReader>.</span></span>

 [!code-csharp[DataWorks SampleApp.Oracle#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SampleApp.Oracle/CS/source.cs#1)]
 [!code-vb[DataWorks SampleApp.Oracle#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SampleApp.Oracle/VB/source.vb#1)]

## <a name="entity-framework-examples"></a><span data-ttu-id="57fc0-137">Entity Framework の例</span><span class="sxs-lookup"><span data-stu-id="57fc0-137">Entity Framework examples</span></span>
<span data-ttu-id="57fc0-138">以下に示した各コードは、エンティティ データ モデル (EDM) のエンティティを照会して、データ ソースからデータを取得する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="57fc0-138">The following code listings demonstrate how to retrieve data from a data source by querying entities in an Entity Data Model (EDM).</span></span> <span data-ttu-id="57fc0-139">これらの例を使用して、 [Northwind モデル](https://msdn.microsoft.com/74521f8c-e974-48cb-8858-c08deff52638)します。</span><span class="sxs-lookup"><span data-stu-id="57fc0-139">These examples use the [Northwind model](https://msdn.microsoft.com/74521f8c-e974-48cb-8858-c08deff52638).</span></span> <span data-ttu-id="57fc0-140">詳細については、次を参照してください。 [Entity Framework の概要](../../../../docs/framework/data/adonet/ef/overview.md)します。</span><span class="sxs-lookup"><span data-stu-id="57fc0-140">For more information, see [Entity Framework Overview](../../../../docs/framework/data/adonet/ef/overview.md).</span></span>

### <a name="linq-to-entities"></a><span data-ttu-id="57fc0-141">LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="57fc0-141">LINQ to Entities</span></span>
<span data-ttu-id="57fc0-142">この例のコードは LINQ クエリを使用してデータをカテゴリ オブジェクトとして返します。これは、CategoryID および CategoryName プロパティのみを含んでいる匿名型として射影されます。</span><span class="sxs-lookup"><span data-stu-id="57fc0-142">The code in this example uses a LINQ query to return data as Categories objects, which are projected as an anonymous type that contains only the CategoryID and CategoryName properties.</span></span> <span data-ttu-id="57fc0-143">詳細については、次を参照してください。 [LINQ to Entities の概要](https://msdn.microsoft.com/86d87a27-c17a-45ac-b28d-72c8500333c6)します。</span><span class="sxs-lookup"><span data-stu-id="57fc0-143">For more information, see [LINQ to Entities Overview](https://msdn.microsoft.com/86d87a27-c17a-45ac-b28d-72c8500333c6).</span></span>

```csharp
using System;
using System.Linq;
using System.Data.Objects;
using NorthwindModel;

class LinqSample
{
    public static void ExecuteQuery()
    {
        using (NorthwindEntities context = new NorthwindEntities())
        {
            try
            {
                var query = from category in context.Categories
                            select new
                            {
                                categoryID = category.CategoryID,
                                categoryName = category.CategoryName
                            };

                foreach (var categoryInfo in query)
                {
                    Console.WriteLine("\t{0}\t{1}",
                        categoryInfo.categoryID, categoryInfo.categoryName);
                }
            }
            catch (Exception ex)
            {
                Console.WriteLine(ex.Message);
            }
        }
    }
}
```

```vb
Option Explicit On
Option Strict On

Imports System
Imports System.Linq
Imports System.Data.Objects
Imports NorthwindModel

Class LinqSample
    Public Shared Sub ExecuteQuery()
        Using context As NorthwindEntities = New NorthwindEntities()
            Try
                Dim query = From category In context.Categories _
                            Select New With _
                            { _
                                .categoryID = category.CategoryID, _
                                .categoryName = category.CategoryName _
                            }

                For Each categoryInfo In query
                    Console.WriteLine(vbTab & "{0}" & vbTab & "{1}", _
                        categoryInfo.categoryID, categoryInfo.categoryName)
                Next
            Catch ex As Exception
                Console.WriteLine(ex.Message)
            End Try
        End Using
    End Sub
End Class
```

### <a name="typed-objectquery"></a><span data-ttu-id="57fc0-144">型指定された ObjectQuery</span><span class="sxs-lookup"><span data-stu-id="57fc0-144">Typed ObjectQuery</span></span>
<span data-ttu-id="57fc0-145">この例のコードは <xref:System.Data.Objects.ObjectQuery%601> を使用し、カテゴリ オブジェクトとしてデータを返します。</span><span class="sxs-lookup"><span data-stu-id="57fc0-145">The code in this example uses an <xref:System.Data.Objects.ObjectQuery%601> to return data as Categories objects.</span></span> <span data-ttu-id="57fc0-146">詳細については、次を参照してください。[オブジェクト クエリ](https://msdn.microsoft.com/0768033c-876f-471d-85d5-264884349276)します。</span><span class="sxs-lookup"><span data-stu-id="57fc0-146">For more information, see [Object Queries](https://msdn.microsoft.com/0768033c-876f-471d-85d5-264884349276).</span></span>

```csharp
using System;
using System.Data.Objects;
using NorthwindModel;

class ObjectQuerySample
{
    public static void ExecuteQuery()
    {
        using (NorthwindEntities context = new NorthwindEntities())
        {
            ObjectQuery<Categories> categoryQuery = context.Categories;

            foreach (Categories category in 
                categoryQuery.Execute(MergeOption.AppendOnly))
            {
                Console.WriteLine("\t{0}\t{1}",
                    category.CategoryID, category.CategoryName);
            }
        }
    }
}
```

```vb
Option Explicit On
Option Strict On

Imports System
Imports System.Data.Objects
Imports NorthwindModel

Class ObjectQuerySample
    Public Shared Sub ExecuteQuery()
        Using context As NorthwindEntities = New NorthwindEntities()
            Dim categoryQuery As ObjectQuery(Of Categories) = context.Categories

            For Each category As Categories In _
                categoryQuery.Execute(MergeOption.AppendOnly)
                Console.WriteLine(vbTab & "{0}" & vbTab & "{1}", _
                    category.CategoryID, category.CategoryName)
            Next
        End Using
    End Sub
End Class
```

### <a name="entityclient"></a><span data-ttu-id="57fc0-147">EntityClient</span><span class="sxs-lookup"><span data-stu-id="57fc0-147">EntityClient</span></span>
<span data-ttu-id="57fc0-148">この例のコードは <xref:System.Data.EntityClient.EntityCommand> を使用し、Entity SQL クエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="57fc0-148">The code in this example uses an <xref:System.Data.EntityClient.EntityCommand> to execute an Entity SQL query.</span></span> <span data-ttu-id="57fc0-149">このクエリは、カテゴリ エンティティ型のインスタンスを示すレコードのリストを返します。</span><span class="sxs-lookup"><span data-stu-id="57fc0-149">This query returns a list of records that represent instances of the Categories entity type.</span></span> <span data-ttu-id="57fc0-150"><xref:System.Data.EntityClient.EntityDataReader> を使用して、結果セットのデータ レコードにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="57fc0-150">An <xref:System.Data.EntityClient.EntityDataReader> is used to access data records in the result set.</span></span> <span data-ttu-id="57fc0-151">詳細については、次を参照してください。 [Entity Framework 用の EntityClient プロバイダー](../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md)します。</span><span class="sxs-lookup"><span data-stu-id="57fc0-151">For more information, see [EntityClient Provider for the Entity Framework](../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md).</span></span>

```csharp
using System;
using System.Data;
using System.Data.Common;
using System.Data.EntityClient;
using NorthwindModel;

class EntityClientSample
{
    public static void ExecuteQuery()
    {
        string queryString =
            @"SELECT c.CategoryID, c.CategoryName 
                FROM NorthwindEntities.Categories AS c";

        using (EntityConnection conn =
            new EntityConnection("name=NorthwindEntities"))
        {
            try
            {
                conn.Open();
                using (EntityCommand query = new EntityCommand(queryString, conn))
                {
                    using (DbDataReader rdr = 
                        query.ExecuteReader(CommandBehavior.SequentialAccess))
                    {
                        while (rdr.Read())
                        {
                            Console.WriteLine("\t{0}\t{1}", rdr[0], rdr[1]);
                        }
                    }
                }
            }
            catch (Exception ex)
            {
                Console.WriteLine(ex.Message);
            }
        }
    }
}
```

```vb
Option Explicit On
Option Strict On

Imports System
Imports System.Data
Imports System.Data.Common
Imports System.Data.EntityClient
Imports NorthwindModel

Class EntityClientSample
    Public Shared Sub ExecuteQuery()
        Dim queryString As String = _
            "SELECT c.CategoryID, c.CategoryName " & _
                "FROM NorthwindEntities.Categories AS c"

        Using conn As EntityConnection = _
            New EntityConnection("name=NorthwindEntities")

            Try
                conn.Open()
                Using query As EntityCommand = _
                New EntityCommand(queryString, conn)
                    Using rdr As DbDataReader = _
                        query.ExecuteReader(CommandBehavior.SequentialAccess)
                        While rdr.Read()
                            Console.WriteLine(vbTab & "{0}" & vbTab & "{1}", _
                                              rdr(0), rdr(1))
                        End While
                    End Using
                End Using
            Catch ex As Exception
                Console.WriteLine(ex.Message)
            End Try
        End Using 
    End Sub
End Class
```

## <a name="linq-to-sql"></a><span data-ttu-id="57fc0-152">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="57fc0-152">LINQ to SQL</span></span>
<span data-ttu-id="57fc0-153">この例のコードは LINQ クエリを使用してデータをカテゴリ オブジェクトとして返します。これは、CategoryID および CategoryName プロパティのみを含んでいる匿名型として射影されます。</span><span class="sxs-lookup"><span data-stu-id="57fc0-153">The code in this example uses a LINQ query to return data as Categories objects, which are projected as an anonymous type that contains only the CategoryID and CategoryName properties.</span></span> <span data-ttu-id="57fc0-154">この例は Northwind データ コンテキストを基にしています。</span><span class="sxs-lookup"><span data-stu-id="57fc0-154">This example is based on the Northwind data context.</span></span> <span data-ttu-id="57fc0-155">詳細については、[概要](../../../../docs/framework/data/adonet/sql/linq/getting-started.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="57fc0-155">For more information, see [Getting Started](../../../../docs/framework/data/adonet/sql/linq/getting-started.md).</span></span>

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using Northwind;

    class LinqSqlSample
    {
        public static void ExecuteQuery()
        {
            using (NorthwindDataContext db = new NorthwindDataContext())
            {
                try
                {
                    var query = from category in db.Categories
                                select new
                                {
                                    categoryID = category.CategoryID,
                                    categoryName = category.CategoryName
                                };

                    foreach (var categoryInfo in query)
                    {
                        Console.WriteLine("vbTab {0} vbTab {1}",
                            categoryInfo.categoryID, categoryInfo.categoryName);
                    }
                }
                catch (Exception ex)
                {
                    Console.WriteLine(ex.Message);
                }
            }
        }
    }
```

```vb
Option Explicit On
Option Strict On

Imports System
Imports System.Collections.Generic
Imports System.Linq
Imports System.Text
Imports Northwind

Class LinqSqlSample
    Public Shared Sub ExecuteQuery()
        Using db As NorthwindDataContext = New NorthwindDataContext()
            Try
                Dim query = From category In db.Categories _
                                Select New With _
                                { _
                                    .categoryID = category.CategoryID, _
                                    .categoryName = category.CategoryName _
                                }

                For Each categoryInfo In query
                    Console.WriteLine(vbTab & "{0}" & vbTab & "{1}", _
                            categoryInfo.categoryID, categoryInfo.categoryName)
                Next
            Catch ex As Exception
                Console.WriteLine(ex.Message)
            End Try
            End Using 
    End Sub
End Class
```

## <a name="see-also"></a><span data-ttu-id="57fc0-156">関連項目</span><span class="sxs-lookup"><span data-stu-id="57fc0-156">See also</span></span>
 [<span data-ttu-id="57fc0-157">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="57fc0-157">ADO.NET Overview</span></span>](../../../../docs/framework/data/adonet/ado-net-overview.md)  
 [<span data-ttu-id="57fc0-158">ADO.NET でのデータの取得および変更</span><span class="sxs-lookup"><span data-stu-id="57fc0-158">Retrieving and Modifying Data in ADO.NET</span></span>](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [<span data-ttu-id="57fc0-159">データ アプリケーションの作成</span><span class="sxs-lookup"><span data-stu-id="57fc0-159">Creating Data Applications</span></span>](https://msdn.microsoft.com/library/ab334d5f-4f49-4346-bce0-3325d6130b3e)  
 [<span data-ttu-id="57fc0-160">Entity Data Model (Entity Framework Tasks) のクエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="57fc0-160">Querying an Entity Data Model (Entity Framework Tasks)</span></span>](https://msdn.microsoft.com/187f1caa-e4d3-4e31-bd99-5d5c2b329c77)  
 [<span data-ttu-id="57fc0-161">方法: 匿名型オブジェクトを返すクエリの実行</span><span class="sxs-lookup"><span data-stu-id="57fc0-161">How to: Execute a Query that Returns Anonymous Type Objects</span></span>](https://msdn.microsoft.com/3b264025-e911-4d73-90ce-992d2b9d189d)  
 [<span data-ttu-id="57fc0-162">ADO.NET のマネージド プロバイダーと DataSet デベロッパー センター</span><span class="sxs-lookup"><span data-stu-id="57fc0-162">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)  
