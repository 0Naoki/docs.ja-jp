---
title: FILESTREAM データ
ms.date: 03/30/2017
ms.assetid: bd8b845c-0f09-4295-b466-97ef106eefa8
ms.openlocfilehash: eef03d171d288cb2bc62c3aaa477a95a5ce718c3
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "44130605"
---
# <a name="filestream-data"></a><span data-ttu-id="f8a7e-102">FILESTREAM データ</span><span class="sxs-lookup"><span data-stu-id="f8a7e-102">FILESTREAM Data</span></span>
<span data-ttu-id="f8a7e-103">FILESTREAM ストレージ属性は、varbinary(max) 列に格納されるバイナリ (BLOB) データに対応しています。</span><span class="sxs-lookup"><span data-stu-id="f8a7e-103">The FILESTREAM storage attribute is for binary (BLOB) data stored in a varbinary(max) column.</span></span> <span data-ttu-id="f8a7e-104">FILESTREAM の導入前は、バイナリ データの格納するために特別な処理が必要でした。</span><span class="sxs-lookup"><span data-stu-id="f8a7e-104">Before FILESTREAM, storing binary data required special handling.</span></span> <span data-ttu-id="f8a7e-105">テキスト ドキュメント、イメージ、ビデオなどの非構造化データはデータベース外に保存されることが多く、そのために管理が困難でした。</span><span class="sxs-lookup"><span data-stu-id="f8a7e-105">Unstructured data, such as text documents, images and video, is often stored outside of the database, making it difficult to manage.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f8a7e-106">SqlClient を使用して FILESTREAM データを操作するには、.NET Framework 3.5 SP1 以降をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f8a7e-106">You must install the .NET Framework 3.5 SP1 (or later) to work with FILESTREAM data using SqlClient.</span></span>  
  
 <span data-ttu-id="f8a7e-107">varbinary(max) 列に FILESTREAM 属性を指定すると、SQL Server ではデータはデータベース ファイルではなくローカルの NTFS ファイル システムに保存されます。</span><span class="sxs-lookup"><span data-stu-id="f8a7e-107">Specifying the FILESTREAM attribute on a varbinary(max) column causes SQL Server to store the data on the local NTFS file system instead of in the database file.</span></span> <span data-ttu-id="f8a7e-108">データは個別に保存されますが、データベースに保存されている varbinary(max) データの操作のためにサポートされているのと同じ [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] ステートメントを使用できます。</span><span class="sxs-lookup"><span data-stu-id="f8a7e-108">Although it is stored separately, you can use the same [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] statements that are supported for working with varbinary(max) data that is stored in the database.</span></span>  
  
## <a name="sqlclient-support-for-filestream"></a><span data-ttu-id="f8a7e-109">FILESTREAM の SqlClient サポート</span><span class="sxs-lookup"><span data-stu-id="f8a7e-109">SqlClient Support for FILESTREAM</span></span>  
 <span data-ttu-id="f8a7e-110">[!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] Data Provider for SQL Server、 <xref:System.Data.SqlClient>、読み取りと書き込みを使用して FILESTREAM データをサポートしています、<xref:System.Data.SqlTypes.SqlFileStream>クラスで定義されている、<xref:System.Data.SqlTypes>名前空間。</span><span class="sxs-lookup"><span data-stu-id="f8a7e-110">The [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] Data Provider for SQL Server, <xref:System.Data.SqlClient>, supports reading and writing to FILESTREAM data using the <xref:System.Data.SqlTypes.SqlFileStream> class defined in the <xref:System.Data.SqlTypes> namespace.</span></span> <span data-ttu-id="f8a7e-111">`SqlFileStream` は <xref:System.IO.Stream> クラスを継承します。このクラスは、データのストリームへの読み込みと書き込みを行うためのメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="f8a7e-111">`SqlFileStream` inherits from the <xref:System.IO.Stream> class, which provides methods for reading and writing to streams of data.</span></span> <span data-ttu-id="f8a7e-112">ストリームからデータを読み取ると、データはストリームからバイトの配列などのデータ構造に転送されます。</span><span class="sxs-lookup"><span data-stu-id="f8a7e-112">Reading from a stream transfers data from the stream into a data structure, such as an array of bytes.</span></span> <span data-ttu-id="f8a7e-113">書き込みを行うと、データはデータ構造からストリームに転送されます。</span><span class="sxs-lookup"><span data-stu-id="f8a7e-113">Writing transfers the data from the data structure into a stream.</span></span>  
  
### <a name="creating-the-sql-server-table"></a><span data-ttu-id="f8a7e-114">SQL Server テーブルの作成</span><span class="sxs-lookup"><span data-stu-id="f8a7e-114">Creating the SQL Server Table</span></span>  
 <span data-ttu-id="f8a7e-115">次の [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] ステートメントでは、従業員の名前の付いたテーブルを作成し、データ行を挿入します。</span><span class="sxs-lookup"><span data-stu-id="f8a7e-115">The following [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] statements creates a table named employees and inserts a row of data.</span></span> <span data-ttu-id="f8a7e-116">FILESTREAM ストレージを有効にすると、このテーブルを次のようなコード例と共に使用できます。</span><span class="sxs-lookup"><span data-stu-id="f8a7e-116">Once you have enabled FILESTREAM storage, you can use this table in conjunction with the code examples that follow.</span></span> <span data-ttu-id="f8a7e-117">SQL Server オンライン ブックのリソースへのリンクは、このトピックの最後にあります。</span><span class="sxs-lookup"><span data-stu-id="f8a7e-117">The links to resources in SQL Server Books Online are located at the end of this topic.</span></span>  
  
```  
CREATE TABLE employees  
(  
  EmployeeId INT  NOT NULL  PRIMARY KEY,  
  Photo VARBINARY(MAX) FILESTREAM  NULL,  
  RowGuid UNIQUEIDENTIFIER  NOT NULL  ROWGUIDCOL  
  UNIQUE DEFAULT NEWID()  
)  
GO  
Insert into employees  
Values(1, 0x00, default)  
GO  
```  
  
### <a name="example-reading-overwriting-and-inserting-filestream-data"></a><span data-ttu-id="f8a7e-118">例: FILESTREAM データの読み取り、上書き、および挿入</span><span class="sxs-lookup"><span data-stu-id="f8a7e-118">Example: Reading, Overwriting, and Inserting FILESTREAM Data</span></span>  
 <span data-ttu-id="f8a7e-119">次のサンプルでは、FILESTREAM からデータを読み取る方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f8a7e-119">The following sample demonstrates how to read data from a FILESTREAM.</span></span> <span data-ttu-id="f8a7e-120">コードはファイルへの論理パスを取得し、`FileAccess` を `Read` に、`FileOptions` を `SequentialScan` に設定します。</span><span class="sxs-lookup"><span data-stu-id="f8a7e-120">The code gets the logical path to the file, setting the `FileAccess` to `Read` and the `FileOptions` to `SequentialScan`.</span></span> <span data-ttu-id="f8a7e-121">次に、コードは SqlFileStream からバイトをバッファーに読み取ります。</span><span class="sxs-lookup"><span data-stu-id="f8a7e-121">The code then reads the bytes from the SqlFileStream into the buffer.</span></span> <span data-ttu-id="f8a7e-122">バイトはコンソール ウィンドウに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="f8a7e-122">The bytes are then written to the console window.</span></span>  
  
 <span data-ttu-id="f8a7e-123">また、このサンプルでは、すべての既存のデータを上書きする FILESTREAM にデータを書き込む方法も示します。</span><span class="sxs-lookup"><span data-stu-id="f8a7e-123">The sample also demonstrates how to write data to a FILESTREAM in which all existing data is overwritten.</span></span> <span data-ttu-id="f8a7e-124">コードはファイルへの論理パスを取得し、`SqlFileStream` を作成し、`FileAccess` を `Write` に、`FileOptions` を `SequentialScan` に設定します。</span><span class="sxs-lookup"><span data-stu-id="f8a7e-124">The code gets the logical path to the file and creates the `SqlFileStream`, setting the `FileAccess` to `Write` and the `FileOptions` to `SequentialScan`.</span></span> <span data-ttu-id="f8a7e-125">1 バイトが `SqlFileStream` に書き込まれ、ファイルのデータは置換されます。</span><span class="sxs-lookup"><span data-stu-id="f8a7e-125">A single byte is written to the `SqlFileStream`, replacing any data in the file.</span></span>  
  
 <span data-ttu-id="f8a7e-126">このサンプルでは、Seek メソッドを使用してファイルの末尾にデータを追加することによって、データを FILESTREAM に書き込む方法も示します。</span><span class="sxs-lookup"><span data-stu-id="f8a7e-126">The sample also demonstrates how to write data to a FILESTREAM by using the Seek method to append data to the end of the file.</span></span> <span data-ttu-id="f8a7e-127">コードはファイルへの論理パスを取得し、`SqlFileStream` を作成し、`FileAccess` を `ReadWrite` に、`FileOptions` を `SequentialScan` に設定します。</span><span class="sxs-lookup"><span data-stu-id="f8a7e-127">The code gets the logical path to the file and creates the `SqlFileStream`, setting the `FileAccess` to `ReadWrite` and the `FileOptions` to `SequentialScan`.</span></span> <span data-ttu-id="f8a7e-128">コードは Seek メソッドを使用してファイルの末尾をシークし、1 バイトを既存のファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="f8a7e-128">The code uses the Seek method to seek to the end of the file, appending a single byte to the existing file.</span></span>  
  
```csharp  
using System;  
using System.Data.SqlClient;  
using System.Data.SqlTypes;  
using System.Data;  
using System.IO;  
  
namespace FileStreamTest  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            SqlConnectionStringBuilder builder = new SqlConnectionStringBuilder("server=(local);integrated security=true;database=myDB");  
            ReadFilestream(builder);  
            OverwriteFilestream(builder);  
            InsertFilestream(builder);  
  
            Console.WriteLine("Done");  
        }  
  
        private static void ReadFilestream(SqlConnectionStringBuilder connStringBuilder)  
        {  
            using (SqlConnection connection = new SqlConnection(connStringBuilder.ToString()))  
            {  
                connection.Open();  
                SqlCommand command = new SqlCommand("SELECT TOP(1) Photo.PathName(), GET_FILESTREAM_TRANSACTION_CONTEXT() FROM employees", connection);  
  
                SqlTransaction tran = connection.BeginTransaction(IsolationLevel.ReadCommitted);  
                command.Transaction = tran;  
  
                using (SqlDataReader reader = command.ExecuteReader())  
                {  
                    while (reader.Read())  
                    {  
                        // Get the pointer for the file  
                        string path = reader.GetString(0);  
                        byte[] transactionContext = reader.GetSqlBytes(1).Buffer;  
  
                        // Create the SqlFileStream  
                        using (Stream fileStream = new SqlFileStream(path, transactionContext, FileAccess.Read, FileOptions.SequentialScan, allocationSize: 0))  
                        {  
                            // Read the contents as bytes and write them to the console  
                            for (long index = 0; index < fileStream.Length; index++)  
                            {  
                                Console.WriteLine(fileStream.ReadByte());  
                            }  
                        }  
                    }  
                }  
                tran.Commit();  
            }  
        }  
  
        private static void OverwriteFilestream(SqlConnectionStringBuilder connStringBuilder)  
        {  
            using (SqlConnection connection = new SqlConnection(connStringBuilder.ToString()))  
            {  
                connection.Open();  
  
                SqlCommand command = new SqlCommand("SELECT TOP(1) Photo.PathName(), GET_FILESTREAM_TRANSACTION_CONTEXT() FROM employees", connection);  
  
                SqlTransaction tran = connection.BeginTransaction(IsolationLevel.ReadCommitted);  
                command.Transaction = tran;  
  
                using (SqlDataReader reader = command.ExecuteReader())  
                {  
                    while (reader.Read())  
                    {  
                        // Get the pointer for file   
                        string path = reader.GetString(0);  
                        byte[] transactionContext = reader.GetSqlBytes(1).Buffer;  
  
                        // Create the SqlFileStream  
                        using (Stream fileStream = new SqlFileStream(path, transactionContext, FileAccess.Write, FileOptions.SequentialScan, allocationSize: 0))  
                        {  
                            // Write a single byte to the file. This will  
                            // replace any data in the file.  
                            fileStream.WriteByte(0x01);  
                        }  
                    }  
                }  
                tran.Commit();  
            }  
        }  
  
        private static void InsertFilestream(SqlConnectionStringBuilder connStringBuilder)  
        {  
            using (SqlConnection connection = new SqlConnection(connStringBuilder.ToString()))  
            {  
                connection.Open();  
  
                SqlCommand command = new SqlCommand("SELECT TOP(1) Photo.PathName(), GET_FILESTREAM_TRANSACTION_CONTEXT() FROM employees", connection);  
  
                SqlTransaction tran = connection.BeginTransaction(IsolationLevel.ReadCommitted);  
                command.Transaction = tran;  
  
                using (SqlDataReader reader = command.ExecuteReader())  
                {  
                    while (reader.Read())  
                    {  
                        // Get the pointer for file  
                        string path = reader.GetString(0);  
                        byte[] transactionContext = reader.GetSqlBytes(1).Buffer;  
  
                        using (Stream fileStream = new SqlFileStream(path, transactionContext, FileAccess.ReadWrite, FileOptions.SequentialScan, allocationSize: 0))  
                        {  
                            // Seek to the end of the file  
                            fileStream.Seek(0, SeekOrigin.End);  
  
                            // Append a single byte   
                            fileStream.WriteByte(0x01);  
                        }  
                    }  
                }  
                tran.Commit();  
            }  
  
        }  
    }  
}
```  
  
 <span data-ttu-id="f8a7e-129">別のサンプルを参照してください。[保存し、ファイル ストリーム列にバイナリ データをフェッチする方法](http://www.codeproject.com/Articles/32216/How-to-store-and-fetch-binary-data-into-a-file-str)します。</span><span class="sxs-lookup"><span data-stu-id="f8a7e-129">For another sample, see [How to store and fetch binary data into a file stream column](http://www.codeproject.com/Articles/32216/How-to-store-and-fetch-binary-data-into-a-file-str).</span></span>  
  
## <a name="resources-in-sql-server-books-online"></a><span data-ttu-id="f8a7e-130">SQL Server オンライン ブックの関連トピック</span><span class="sxs-lookup"><span data-stu-id="f8a7e-130">Resources in SQL Server Books Online</span></span>  
 <span data-ttu-id="f8a7e-131">FILESTREAM の詳細なドキュメントについては、SQL Server オンライン ブックの次のセクションにあります。</span><span class="sxs-lookup"><span data-stu-id="f8a7e-131">The complete documentation for FILESTREAM is located in the following sections in SQL Server Books Online.</span></span>  
  
|<span data-ttu-id="f8a7e-132">トピック</span><span class="sxs-lookup"><span data-stu-id="f8a7e-132">Topic</span></span>|<span data-ttu-id="f8a7e-133">説明</span><span class="sxs-lookup"><span data-stu-id="f8a7e-133">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="f8a7e-134">[設計と実装の FILESTREAM ストレージ](http://msdn2.microsoft.com/library/bb895234\(SQL.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="f8a7e-134">[Designing and Implementing FILESTREAM Storage](http://msdn2.microsoft.com/library/bb895234\(SQL.105\).aspx)</span></span>|<span data-ttu-id="f8a7e-135">FILESTREAM ドキュメントと関連項目へのリンクを示します。</span><span class="sxs-lookup"><span data-stu-id="f8a7e-135">Provides links to FILESTREAM documentation and related topics.</span></span>|  
|<span data-ttu-id="f8a7e-136">[FILESTREAM の概要](http://msdn2.microsoft.com/library/bb933993\(SQL.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="f8a7e-136">[FILESTREAM Overview](http://msdn2.microsoft.com/library/bb933993\(SQL.105\).aspx)</span></span>|<span data-ttu-id="f8a7e-137">FILESTREAM ストレージを使用するタイミング、および SQL Server データベース エンジンと NTFS ファイル システムを統合する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f8a7e-137">Describes when to use FILESTREAM storage and how it integrates the SQL Server Database Engine with an NTFS file system.</span></span>|  
|<span data-ttu-id="f8a7e-138">[FILESTREAM ストレージの概要](https://msdn.microsoft.com/library/bb933995\(SQL.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="f8a7e-138">[Getting Started with FILESTREAM Storage](https://msdn.microsoft.com/library/bb933995\(SQL.105\).aspx)</span></span>|<span data-ttu-id="f8a7e-139">FILESTREAM を SQL Server のインスタンス上で有効にする方法、データベースと FILESTREAM データを格納するテーブルの作成方法、および FILESTREAM データを含んでいる行の操作方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f8a7e-139">Describes how to enable FILESTREAM on an instance of SQL Server, how to create a database and a table to stored FILESTREAM data, and how to manipulate rows containing FILESTREAM data.</span></span>|  
|<span data-ttu-id="f8a7e-140">[クライアント アプリケーションでの FILESTREAM ストレージの使用](https://msdn.microsoft.com/library/bb933877\(SQL.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="f8a7e-140">[Using FILESTREAM Storage in Client Applications](https://msdn.microsoft.com/library/bb933877\(SQL.105\).aspx)</span></span>|<span data-ttu-id="f8a7e-141">FILESTREAM データを操作するための Win32 API 関数について説明します。</span><span class="sxs-lookup"><span data-stu-id="f8a7e-141">Describes the Win32 API functions for working with FILESTREAM data.</span></span>|  
|[<span data-ttu-id="f8a7e-142">FILESTREAM と他の SQL Server 機能</span><span class="sxs-lookup"><span data-stu-id="f8a7e-142">FILESTREAM and Other SQL Server Features</span></span>](/sql/relational-databases/blob/filestream-compatibility-with-other-sql-server-features)|<span data-ttu-id="f8a7e-143">FILESTREAM データを SQL Server の他の機能と共に使用する際の注意事項、ガイドライン、および制限事項について説明します。</span><span class="sxs-lookup"><span data-stu-id="f8a7e-143">Provides considerations, guidelines and limitations for using FILESTREAM data with other features of SQL Server.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f8a7e-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="f8a7e-144">See Also</span></span>  
 [<span data-ttu-id="f8a7e-145">SQL Server データ型と ADO.NET</span><span class="sxs-lookup"><span data-stu-id="f8a7e-145">SQL Server Data Types and ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-data-types.md)  
 [<span data-ttu-id="f8a7e-146">ADO.NET でのデータの取得および変更</span><span class="sxs-lookup"><span data-stu-id="f8a7e-146">Retrieving and Modifying Data in ADO.NET</span></span>](../../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [<span data-ttu-id="f8a7e-147">コード アクセス セキュリティと ADO.NET</span><span class="sxs-lookup"><span data-stu-id="f8a7e-147">Code Access Security and ADO.NET</span></span>](../../../../../docs/framework/data/adonet/code-access-security.md)  
 [<span data-ttu-id="f8a7e-148">SQL Server のバイナリ データと大きな値のデータ</span><span class="sxs-lookup"><span data-stu-id="f8a7e-148">SQL Server Binary and Large-Value Data</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-binary-and-large-value-data.md)  
 [<span data-ttu-id="f8a7e-149">ADO.NET のマネージド プロバイダーと DataSet デベロッパー センター</span><span class="sxs-lookup"><span data-stu-id="f8a7e-149">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
