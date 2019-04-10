---
title: データ ソースのデータの更新
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 55c545e5-dcd5-4323-a5b9-3825c2157462
ms.openlocfilehash: a12fa587d5df0ed95dd0f15ccfbe2ef886185b9e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59207481"
---
# <a name="updating-data-in-a-data-source"></a><span data-ttu-id="74b08-102">データ ソースのデータの更新</span><span class="sxs-lookup"><span data-stu-id="74b08-102">Updating Data in a Data Source</span></span>
<span data-ttu-id="74b08-103">データを変更する SQL ステートメント (INSERT、UPDATE、DELETE など) は行を返しません。</span><span class="sxs-lookup"><span data-stu-id="74b08-103">SQL statements that modify data (such as INSERT, UPDATE, or DELETE) do not return rows.</span></span> <span data-ttu-id="74b08-104">同様に、多くのストアド プロシージャは、アクションを実行しても行を返しません。</span><span class="sxs-lookup"><span data-stu-id="74b08-104">Similarly, many stored procedures perform an action but do not return rows.</span></span> <span data-ttu-id="74b08-105">行を返さないコマンドを実行するには、作成、**コマンド**適切な SQL コマンドを使用してオブジェクトと**接続**など必要な**パラメーター**します。</span><span class="sxs-lookup"><span data-stu-id="74b08-105">To execute commands that do not return rows, create a **Command** object with the appropriate SQL command and a **Connection**, including any required **Parameters**.</span></span> <span data-ttu-id="74b08-106">コマンドを実行、 **ExecuteNonQuery**のメソッド、**コマンド**オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="74b08-106">Execute the command with the **ExecuteNonQuery** method of the **Command** object.</span></span>  
  
 <span data-ttu-id="74b08-107">**ExecuteNonQuery**ステートメントまたはが実行されたストアド プロシージャによって影響を受ける行の数を表す整数を返します。</span><span class="sxs-lookup"><span data-stu-id="74b08-107">The **ExecuteNonQuery** method returns an integer that represents the number of rows affected by the statement or stored procedure that was executed.</span></span> <span data-ttu-id="74b08-108">複数のステートメントが実行された場合は、実行された各ステートメントの影響を受けたレコードの合計を示す値が返されます。</span><span class="sxs-lookup"><span data-stu-id="74b08-108">If multiple statements are executed, the value returned is the sum of the records affected by all of the statements executed.</span></span>  
  
## <a name="example"></a><span data-ttu-id="74b08-109">例</span><span class="sxs-lookup"><span data-stu-id="74b08-109">Example</span></span>  
 <span data-ttu-id="74b08-110">次のコード例を使用してデータベースにレコードを挿入する INSERT ステートメントを実行する**ExecuteNonQuery**します。</span><span class="sxs-lookup"><span data-stu-id="74b08-110">The following code example executes an INSERT statement to insert a record into a database using **ExecuteNonQuery**.</span></span>  
  
```vb  
' Assumes connection is a valid SqlConnection.  
connection.Open()  
  
Dim queryString As String = "INSERT INTO Customers " & _  
  "(CustomerID, CompanyName) Values('NWIND', 'Northwind Traders')"  
  
Dim command As SqlCommand = New SqlCommand(queryString, connection)  
Dim recordsAffected As Int32 = command.ExecuteNonQuery()  
```  
  
```csharp  
// Assumes connection is a valid SqlConnection.  
connection.Open();  
  
string queryString = "INSERT INTO Customers " +  
  "(CustomerID, CompanyName) Values('NWIND', 'Northwind Traders')";  
  
SqlCommand command = new SqlCommand(queryString, connection);  
Int32 recordsAffected = command.ExecuteNonQuery();  
```  
  
 <span data-ttu-id="74b08-111">次のコード例のサンプル コードで作成したストアド プロシージャを実行する[カタログ操作の実行](../../../../docs/framework/data/adonet/performing-catalog-operations.md)します。</span><span class="sxs-lookup"><span data-stu-id="74b08-111">The following code example executes the stored procedure created by the sample code in [Performing Catalog Operations](../../../../docs/framework/data/adonet/performing-catalog-operations.md).</span></span> <span data-ttu-id="74b08-112">ストアド プロシージャによって行が返されないため、 **ExecuteNonQuery**メソッドを使用するが、ストアド プロシージャが受け取る入力パラメーターと出力パラメーターと戻り値を返します。</span><span class="sxs-lookup"><span data-stu-id="74b08-112">No rows are returned by the stored procedure, so the **ExecuteNonQuery** method is used, but the stored procedure does receive an input parameter and returns an output parameter and a return value.</span></span>  
  
 <span data-ttu-id="74b08-113"><xref:System.Data.OleDb.OleDbCommand>オブジェクト、 **ReturnValue**にパラメーターを追加する必要があります、**パラメーター**コレクション最初。</span><span class="sxs-lookup"><span data-stu-id="74b08-113">For the <xref:System.Data.OleDb.OleDbCommand> object, the **ReturnValue** parameter must be added to the **Parameters** collection first.</span></span>  
  
```vb  
' Assumes connection is a valid SqlConnection.  
Dim command As SqlCommand = _  
   New SqlCommand("InsertCategory" , connection)  
command.CommandType = CommandType.StoredProcedure  
  
Dim parameter As SqlParameter = _  
 command.Parameters.Add("@RowCount", SqlDbType.Int)  
parameter.Direction = ParameterDirection.ReturnValue  
  
parameter = command.Parameters.Add( _  
  "@CategoryName", SqlDbType.NChar, 15)  
  
parameter = command.Parameters.Add("@Identity", SqlDbType.Int)  
parameter.Direction = ParameterDirection.Output  
  
command.Parameters("@CategoryName").Value = "New Category"  
command.ExecuteNonQuery()  
  
Dim categoryID As Int32 = CInt(command.Parameters("@Identity").Value)  
Dim rowCount As Int32 = CInt(command.Parameters("@RowCount").Value)   
```  
  
```csharp  
// Assumes connection is a valid SqlConnection.  
SqlCommand command = new SqlCommand("InsertCategory" , connection);  
command.CommandType = CommandType.StoredProcedure;  
  
SqlParameter parameter = command.Parameters.Add(  
  "@RowCount", SqlDbType.Int);  
parameter.Direction = ParameterDirection.ReturnValue;  
  
parameter = command.Parameters.Add(  
  "@CategoryName", SqlDbType.NChar, 15);  
  
parameter = command.Parameters.Add("@Identity", SqlDbType.Int);  
parameter.Direction = ParameterDirection.Output;  
  
command.Parameters["@CategoryName"].Value = "New Category";  
command.ExecuteNonQuery();  
  
Int32 categoryID = (Int32) command.Parameters["@Identity"].Value;  
Int32 rowCount = (Int32) command.Parameters["@RowCount"].Value;  
```  
  
## <a name="see-also"></a><span data-ttu-id="74b08-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="74b08-114">See also</span></span>

- [<span data-ttu-id="74b08-115">コマンドを使用したデータ変更</span><span class="sxs-lookup"><span data-stu-id="74b08-115">Using Commands to Modify Data</span></span>](../../../../docs/framework/data/adonet/using-commands-to-modify-data.md)
- [<span data-ttu-id="74b08-116">DataAdapter によるデータ ソースの更新</span><span class="sxs-lookup"><span data-stu-id="74b08-116">Updating Data Sources with DataAdapters</span></span>](../../../../docs/framework/data/adonet/updating-data-sources-with-dataadapters.md)
- [<span data-ttu-id="74b08-117">コマンドおよびパラメーター</span><span class="sxs-lookup"><span data-stu-id="74b08-117">Commands and Parameters</span></span>](../../../../docs/framework/data/adonet/commands-and-parameters.md)
- [<span data-ttu-id="74b08-118">ADO.NET のマネージド プロバイダーと DataSet デベロッパー センター</span><span class="sxs-lookup"><span data-stu-id="74b08-118">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
