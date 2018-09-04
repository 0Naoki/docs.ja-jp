---
title: DataReader によるデータの取得
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 97afc121-fb8b-465b-bab3-6d844420badb
ms.openlocfilehash: 4370a7a700a01943548bf067827e6640245caf4e
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "43516792"
---
# <a name="retrieving-data-using-a-datareader"></a>DataReader によるデータの取得
使用してデータの取得、 **DataReader**のインスタンスを作成、**コマンド**オブジェクトを作成した後、 **DataReader**呼び出して**Command.ExecuteReader**データ ソースから行を取得します。 次の例を使用して、 **DataReader**場所`reader`は有効な datareader と`command`有効な Command オブジェクトを表します。  
  
```  
reader = command.ExecuteReader();  
```  
  
 使用する、**読み取り**のメソッド、 **DataReader**クエリの結果から行を取得するオブジェクト。 返された行の各列をアクセスするには、名前または列の序数参照を渡すことによって、 **DataReader**します。 ただし、最高のパフォーマンスについて、 **DataReader**一連のネイティブ データ型の列の値にアクセスできるようにするメソッドを提供します (**GetDateTime**、 **GetDouble**、 **GetGuid**、 **GetInt32**など)。 データ プロバイダーに固有の型指定されたアクセサー メソッドの一覧については**DataReaders**を参照してください<xref:System.Data.OleDb.OleDbDataReader>と<xref:System.Data.SqlClient.SqlDataReader>します。 基になるデータ型がわかっている場合、型指定されたアクセサー メソッドを使用すると、列の値を取得するときに必要な型変換の量が少なくなります。  
  
> [!NOTE]
>  .NET Framework の Windows Server 2003 のリリースには、追加のプロパティが含まれています、 **DataReader**、 **HasRows**、かを判断することができる**DataReader**がそこから読み取る前に結果を返した。  
  
 次のコード例を反復処理を**DataReader**オブジェクト、および各列から 2 つの列を返します。  
  
 [!code-csharp[DataWorks SqlClient.HasRows#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.HasRows/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.HasRows#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.HasRows/VB/source.vb#1)]  
  
 **DataReader**は手続き型のロジックを効率的にデータ ソースからの結果を順番に処理を可能にするデータのバッファリングされていないストリームを提供します。 **DataReader**データがメモリにキャッシュされていないため、大量のデータを取得するときにお勧めします。  
  
## <a name="closing-the-datareader"></a>DataReader の終了  
 常に呼び出す必要があります、**閉じる**メソッドを使用してが完了したら、 **DataReader**オブジェクト。  
  
 場合、**コマンド**の出力を含むパラメーターまたは戻り値の場合は、これらは使用できませんまで、 **DataReader**が閉じられました。  
  
 注意してください、 **DataReader**が開いて、**接続**によって排他的に使用されて**DataReader**します。 任意のコマンドを実行することはできません、**接続**、もう 1 つ作成を含む**DataReader**、まで、元の**DataReader**が閉じられました。  
  
> [!NOTE]
>  呼び出さないでください**閉じる**または**Dispose**上、**接続**、 **DataReader**、またはその他のマネージ オブジェクトで、 **Finalize**クラスのメソッド。 終了処理では、クラスに直接所有されているアンマネージ リソースだけを解放してください。 クラスがアンマネージ リソースを所有していない場合は含まれません、 **Finalize**メソッド、クラス定義にします。 詳細については、次を参照してください。[ガベージ コレクション](../../../../docs/standard/garbage-collection/index.md)します。  
  
## <a name="retrieving-multiple-result-sets-using-nextresult"></a>NextResult による複数の結果セットの取得  
 複数の結果セットが返された場合、 **DataReader**提供、 **NextResult**の順序で結果を反復処理するメソッドを設定します。 <xref:System.Data.SqlClient.SqlDataReader> メソッドを使用して、2 つの SELECT ステートメントの結果を処理する <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A> の例を次に示します。  
  
 [!code-csharp[DataWorks SqlClient.NextResult#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.NextResult/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.NextResult#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.NextResult/VB/source.vb#1)]  
  
## <a name="getting-schema-information-from-the-datareader"></a>DataReader からのスキーマ情報の取得  
 中に、 **DataReader**は開くことができますを取得する設定を使用して現在の結果に関するスキーマ情報、 **GetSchemaTable**メソッド。 **GetSchemaTable**を返します、<xref:System.Data.DataTable>行と、現在の結果セットのスキーマ情報を含む列を含むオブジェクト。 **DataTable**結果セットの列ごとに 1 つの行が含まれています。 スキーマ テーブル行の各列に返される列のプロパティにマップ、結果セット、 **ColumnName**プロパティの名前であり、列の値は、プロパティの値。 次のコード例のスキーマ情報を書き込みます**DataReader**します。  
  
 [!code-csharp[DataWorks SqlClient.GetSchemaTable#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.GetSchemaTable/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.GetSchemaTable#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.GetSchemaTable/VB/source.vb#1)]  
  
## <a name="working-with-ole-db-chapters"></a>OLE DB のチャプターの使用  
 階層的な行セット、つまりチャプター (OLE DB 型**DBTYPE_HCHAPTER**、ADO 型**adChapter**) を使用して取得できます、<xref:System.Data.OleDb.OleDbDataReader>します。 チャプターを含むクエリとして返される場合、 **DataReader**、章を内の列として返されます**DataReader**として公開されると、 **DataReader**オブジェクト。  
  
 ADO.NET**データセット**テーブル間の親子リレーションシップを使用して階層的な行セットを表すためも使用できます。 詳細については、次を参照してください。 [Dataset、Datatable、および Dataview](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)します。  
  
 MSDataShape プロバイダーを使用して、顧客リストの顧客別オーダーのチャプター列を生成するコード サンプルを次に示します。  
  
```vb  
Using connection As OleDbConnection = New OleDbConnection( _  
  "Provider=MSDataShape;Data Provider=SQLOLEDB;" & _  
  "Data Source=localhost;Integrated Security=SSPI;Initial Catalog=northwind")  
  
Dim custCMD As OleDbCommand = New OleDbCommand( _  
  "SHAPE {SELECT CustomerID, CompanyName FROM Customers} " & _  
  "APPEND ({SELECT CustomerID, OrderID FROM Orders} AS CustomerOrders " & _  
  "RELATE CustomerID TO CustomerID)", connection)  
connection.Open()  
  
Dim custReader As OleDbDataReader = custCMD.ExecuteReader()  
Dim orderReader As OleDbDataReader  
  
Do While custReader.Read()  
  Console.WriteLine("Orders for " & custReader.GetString(1))   
  ' custReader.GetString(1) = CompanyName  
  
  orderReader = custReader.GetValue(2)  
  ' custReader.GetValue(2) = Orders chapter as DataReader  
  
  Do While orderReader.Read()  
    Console.WriteLine(vbTab & orderReader.GetInt32(1))  
    ' orderReader.GetInt32(1) = OrderID  
  Loop  
  orderReader.Close()  
Loop  
' Make sure to always close readers and connections.  
custReader.Close()  
End Using  
```  
  
```csharp  
Using (OleDbConnection connection = new OleDbConnection(  
  "Provider=MSDataShape;Data Provider=SQLOLEDB;" +  
  "Data Source=localhost;Integrated Security=SSPI;Initial Catalog=northwind"));  
{  
OleDbCommand custCMD = new OleDbCommand(  
  "SHAPE {SELECT CustomerID, CompanyName FROM Customers} " +  
  "APPEND ({SELECT CustomerID, OrderID FROM Orders} AS CustomerOrders " +  
  "RELATE CustomerID TO CustomerID)", connection);  
connection.Open();  
  
OleDbDataReader custReader = custCMD.ExecuteReader();  
OleDbDataReader orderReader;  
  
while (custReader.Read())  
{  
  Console.WriteLine("Orders for " + custReader.GetString(1));   
  // custReader.GetString(1) = CompanyName  
  
  orderReader = (OleDbDataReader)custReader.GetValue(2);        
  // custReader.GetValue(2) = Orders chapter as DataReader  
  
  while (orderReader.Read())  
    Console.WriteLine("\t" + orderReader.GetInt32(1));          
    // orderReader.GetInt32(1) = OrderID  
  orderReader.Close();  
}  
// Make sure to always close readers and connections.  
custReader.Close();  
}  
```  
  
## <a name="returning-results-with-oracle-ref-cursors"></a>Oracle REF CURSOR による結果の取得  
 .NET Framework Data Provider for Oracle は、クエリ結果を返すために、Oracle REF CURSOR の使用をサポートしています。 Oracle REF CURSOR は <xref:System.Data.OracleClient.OracleDataReader> として返されます。  
  
 取得することができます、 **OracleDataReader**オブジェクトを使用して、Oracle REF CURSOR を表す、<xref:System.Data.OracleClient.OracleCommand.ExecuteReader%2A>メソッドをおよびするを指定できますも、<xref:System.Data.OracleClient.OracleCommand>として 1 つまたは複数の Oracle REF Cursor を返す、 **SelectCommand**の<xref:System.Data.OracleClient.OracleDataAdapter>塗りつぶしに使用される、<xref:System.Data.DataSet>します。  
  
 Oracle データ ソースから返された REF CURSOR にアクセスするには、作成、 **OracleCommand** 、クエリの REF CURSOR を参照する出力パラメーターを追加し、**パラメーター** のコレクション**OracleCommand**します。 パラメーターの名前は、クエリの REF CURSOR パラメーターの名前と一致させる必要があります。 設定するパラメーターの型**OracleType.Cursor**します。 **ExecuteReader**のメソッド、 **OracleCommand**が返されます、 **OracleDataReader** REF CURSOR の。  
  
 場合、 **OracleCommand**複数の REF CURSOR を返す複数の出力パラメーターを追加します。 それぞれの REF Cursor を呼び出すことによってアクセスできる、 **OracleCommand.ExecuteReader**メソッド。 呼び出し**ExecuteReader**を返します、 **OracleDataReader**最初の REF CURSOR を参照します。 呼び出して、 **OracleDataReader.NextResult**後続の REF Cursor にアクセスするメソッド。 パラメーター、 **OracleCommand.Parameters**コレクションの一致、REF CURSOR 出力パラメーターを名前で、 **OracleDataReader** に追加された順序でそれらにアクセスします。**パラメーター**コレクション。  
  
 たとえば、次のような Oracle パッケージとパッケージ本体があるとします。  
  
```  
CREATE OR REPLACE PACKAGE CURSPKG AS   
  TYPE T_CURSOR IS REF CURSOR;   
  PROCEDURE OPEN_TWO_CURSORS (EMPCURSOR OUT T_CURSOR,   
    DEPTCURSOR OUT T_CURSOR);   
END CURSPKG;  
  
CREATE OR REPLACE PACKAGE BODY CURSPKG AS   
  PROCEDURE OPEN_TWO_CURSORS (EMPCURSOR OUT T_CURSOR,   
    DEPTCURSOR OUT T_CURSOR)   
  IS   
  BEGIN   
    OPEN EMPCURSOR FOR SELECT * FROM DEMO.EMPLOYEE;   
    OPEN DEPTCURSOR FOR SELECT * FROM DEMO.DEPARTMENT;   
  END OPEN_TWO_CURSORS;   
END CURSPKG;   
```  
  
 次のコード作成、 **OracleCommand**型の 2 つのパラメーターを追加することで、前のバージョンの Oracle パッケージから REF Cursor を返す**OracleType.Cursor**を**パラメーター**コレクション。  
  
```vb  
Dim cursCmd As OracleCommand = New OracleCommand("CURSPKG.OPEN_TWO_CURSORS", oraConn)  
cursCmd.Parameters.Add("EMPCURSOR", OracleType.Cursor).Direction = ParameterDirection.Output  
cursCmd.Parameters.Add("DEPTCURSOR", OracleType.Cursor).Direction = ParameterDirection.Output  
```  
  
```csharp  
OracleCommand cursCmd = new OracleCommand("CURSPKG.OPEN_TWO_CURSORS", oraConn);  
cursCmd.Parameters.Add("EMPCURSOR", OracleType.Cursor).Direction = ParameterDirection.Output;  
cursCmd.Parameters.Add("DEPTCURSOR", OracleType.Cursor).Direction = ParameterDirection.Output;  
```  
  
 次のコードを使用して前のコマンドの結果を返します、**読み取り**と**NextResult**のメソッド、 **OracleDataReader**します。 REF CURSOR パラメーターは順番に返されます。  
  
```vb  
oraConn.Open()  
  
Dim cursCmd As OracleCommand = New OracleCommand("CURSPKG.OPEN_TWO_CURSORS", oraConn)  
cursCmd.CommandType = CommandType.StoredProcedure  
cursCmd.Parameters.Add("EMPCURSOR", OracleType.Cursor).Direction = ParameterDirection.Output  
cursCmd.Parameters.Add("DEPTCURSOR", OracleType.Cursor).Direction = ParameterDirection.Output  
  
Dim reader As OracleDataReader = cursCmd.ExecuteReader()  
  
Console.WriteLine(vbCrLf & "Emp ID" & vbTab & "Name")  
  
Do While reader.Read()  
  Console.WriteLine("{0}" & vbTab & "{1}, {2}", reader.GetOracleNumber(0), reader.GetString(1), reader.GetString(2))  
Loop  
  
reader.NextResult()  
  
Console.WriteLine(vbCrLf & "Dept ID" & vbTab & "Name")  
  
Do While reader.Read()  
  Console.WriteLine("{0}" & vbTab & "{1}", reader.GetOracleNumber(0), reader.GetString(1))  
Loop  
' Make sure to always close readers and connections.  
reader.Close()  
oraConn.Close()  
```  
  
```csharp  
oraConn.Open();  
  
OracleCommand cursCmd = new OracleCommand("CURSPKG.OPEN_TWO_CURSORS", oraConn);  
cursCmd.CommandType = CommandType.StoredProcedure;  
cursCmd.Parameters.Add("EMPCURSOR", OracleType.Cursor).Direction = ParameterDirection.Output;  
cursCmd.Parameters.Add("DEPTCURSOR", OracleType.Cursor).Direction = ParameterDirection.Output;  
  
OracleDataReader reader = cursCmd.ExecuteReader();  
  
Console.WriteLine("\nEmp ID\tName");  
  
while (reader.Read())  
  Console.WriteLine("{0}\t{1}, {2}", reader.GetOracleNumber(0), reader.GetString(1), reader.GetString(2));  
  
reader.NextResult();  
  
Console.WriteLine("\nDept ID\tName");  
  
while (reader.Read())  
  Console.WriteLine("{0}\t{1}", reader.GetOracleNumber(0), reader.GetString(1));  
// Make sure to always close readers and connections.  
reader.Close();  
oraConn.Close();  
```  
  
 次の例では、前のコマンドを使用して、事前設定、**データセット**Oracle パッケージの結果。  
  
> [!NOTE]
>  回避するために、 **OverflowException**、有効な .NET Framework 型に値を格納する前に、Oracle の NUMBER 型から変換を処理することをお勧め、 **DataRow**。 使用することができます、 **FillError**イベントかどうかを**OverflowException**が発生しました。 詳細については、 **FillError**イベントを参照してください[DataAdapter イベントの処理](../../../../docs/framework/data/adonet/handling-dataadapter-events.md)します。  
  
```vb  
Dim ds As DataSet = New DataSet()  
  
Dim adapter As OracleDataAdapter = New OracleDataAdapter(cursCmd)  
adapter.TableMappings.Add("Table", "Employees")  
adapter.TableMappings.Add("Table1", "Departments")  
  
adapter.Fill(ds)  
```  
  
```csharp  
DataSet ds = new DataSet();  
  
OracleDataAdapter adapter = new OracleDataAdapter(cursCmd);  
adapter.TableMappings.Add("Table", "Employees");  
adapter.TableMappings.Add("Table1", "Departments");  
  
adapter.Fill(ds);  
```  
  
## <a name="see-also"></a>関連項目  
 [Datareader の操作](https://msdn.microsoft.com/library/126a966a-d08d-4d22-a19f-f432908b2b54)  
 [DataAdapter と DataReader](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)  
 [コマンドおよびパラメーター](../../../../docs/framework/data/adonet/commands-and-parameters.md)  
 [データベース スキーマ情報の取得](../../../../docs/framework/data/adonet/retrieving-database-schema-information.md)  
 [ADO.NET のマネージド プロバイダーと DataSet デベロッパー センター](https://go.microsoft.com/fwlink/?LinkId=217917)
