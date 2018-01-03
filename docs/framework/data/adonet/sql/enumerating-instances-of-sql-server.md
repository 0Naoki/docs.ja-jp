---
title: "SQL Server のインスタンスの列挙 (ADO.NET)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: ddf1c83c-9d40-45e6-b04d-9828c6cbbfdc
caps.latest.revision: "8"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 679196a6cc21705c8cc07e373a928f3c77c6befb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="enumerating-instances-of-sql-server-adonet"></a>SQL Server のインスタンスの列挙 (ADO.NET)
[!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] では、アプリケーションは現在のネットワーク内の [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] インスタンスを検索できます。 <xref:System.Data.Sql.SqlDataSourceEnumerator> クラスは、表示可能なすべてのサーバーに関する情報が含まれた <xref:System.Data.DataTable> を提供することで、アプリケーション開発者にこの情報を公開します。 これは、テーブルには、ユーザーが新しい接続を作成しようとしたときに指定されたリストと一致してで利用可能なすべてのサーバーを含むドロップダウン リストを展開しているネットワークで使用できるサーバー インスタンスの一覧が含まれています返される、**接続。プロパティ** ダイアログ ボックス。 結果には一部のインスタンスが表示されないことがあります。  
  
> [!NOTE]
>  大半の Windows サービスと同様に、できるだけ少ない特権で SQL Browser サービスを実行することをお勧めします。 SQL Browser サービスの詳細および SQL Browser サービスの動作を管理する方法については、[!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] オンライン ブックを参照してください。  
  
## <a name="retrieving-an-enumerator-instance"></a>列挙子インスタンスの取得  
 使用可能な [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] インスタンスに関する情報を含むテーブルを取得するには、まず、共有プロパティまたは静的プロパティである <xref:System.Data.Sql.SqlDataSourceEnumerator.Instance%2A> プロパティを使用して列挙子を取得する必要があります。  
  
```vb  
Dim instance As System.Data.Sql.SqlDataSourceEnumerator = _  
   System.Data.Sql.SqlDataSourceEnumerator.Instance  
```  
  
```csharp  
System.Data.Sql.SqlDataSourceEnumerator instance =   
   System.Data.Sql.SqlDataSourceEnumerator.Instance  
```  
  
 静的なインスタンスを取得したら、使用可能なサーバーに関する情報が含まれた <xref:System.Data.Sql.SqlDataSourceEnumerator.GetDataSources%2A> を返す <xref:System.Data.DataTable> メソッドを呼び出すことができます。  
  
```vb  
Dim dataTable As System.Data.DataTable = instance.GetDataSources()  
```  
  
```csharp  
System.Data.DataTable dataTable = instance.GetDataSources();  
```  
  
 このメソッド呼び出しから返されるテーブルには、次の列が含まれています。これらすべての列に `string` 値が含まれています。  
  
|Column|説明|  
|------------|-----------------|  
|**サーバー名**|サーバーの名前。|  
|**InstanceName**|サーバー インスタンスの名前。 サーバーが既定のインスタンスとして実行されている場合は空白になります。|  
|**IsClustered**|サーバーがクラスターの一部になっているかどうかを示します。|  
|**Version**|サーバーのバージョン。 例:<br /><br /> -9.00.x ([!INCLUDE[ssVersion2005](../../../../../includes/ssversion2005-md.md)])<br />-10.0.xx ([!INCLUDE[ssKatmai](../../../../../includes/sskatmai-md.md)])<br />-10.50.x ([!INCLUDE[ssKilimanjaro](../../../../../includes/sskilimanjaro-md.md)])<br />-11.0.xx ([!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] 2012)|  
  
## <a name="enumeration-limitations"></a>列挙の制約  
 使用可能なサーバーの一部が表示されないことがあります。 サーバーの一覧は、タイムアウトやネットワーク トラフィックなどの要因によって異なることがあります。 そのため、2 回続けて呼び出しても、呼び出しごとにリストが異なる可能性があります。 同じネットワーク上のサーバーのみがリストに表示されます。 通常、ブロードキャスト パケットはルーターを経由しません。そのため、特定のサーバーがリストに表示されないことがありますが、その状態はいつ呼び出しを行っても変わりません。  
  
 一覧に含まれているサーバーは、`IsClustered` やバージョンなどの追加情報を持っている場合も、持っていない場合もあります。 サーバーが持っている情報は、一覧が取得された方法によって異なります。 [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] Browser サービスを介して一覧に表示されるサーバーには、一覧に名前しか表示されない、Windows インフラストラクチャを介して検索されたサーバーより多くの詳細情報が含まれています。  
  
> [!NOTE]
>  サーバー列挙は、完全に信頼された環境で実行している場合にのみ利用できます。 部分的に信頼された環境で実行されているアセンブリは、<xref:System.Data.SqlClient.SqlClientPermission> Code Access Security (CAS) アクセス許可を持っている場合でも、サーバー列挙を使用できません。  
  
 [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] では、SQL Browser という名前の外部の Windows サービスを利用して、<xref:System.Data.Sql.SqlDataSourceEnumerator> に情報を提供します。 このサービスは既定で有効になりますが、管理者がこのサービスをオフにしたり無効にしたりすると、サーバー インスタンスがこのクラスから見えなくなります。  
  
## <a name="example"></a>例  
 次のコンソール アプリケーションは、表示可能なすべての [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] インスタンスに関する情報を取得し、その情報をコンソール ウィンドウに表示します。  
  
```vb  
Imports System.Data.Sql  
  
Module Module1  
  Sub Main()  
    ' Retrieve the enumerator instance and then the data.  
    Dim instance As SqlDataSourceEnumerator = _  
     SqlDataSourceEnumerator.Instance  
    Dim table As System.Data.DataTable = instance.GetDataSources()  
  
    ' Display the contents of the table.  
    DisplayData(table)  
  
    Console.WriteLine("Press any key to continue.")  
    Console.ReadKey()  
  End Sub  
  
  Private Sub DisplayData(ByVal table As DataTable)  
    For Each row As DataRow In table.Rows  
      For Each col As DataColumn In table.Columns  
        Console.WriteLine("{0} = {1}", col.ColumnName, row(col))  
      Next  
      Console.WriteLine("============================")  
    Next  
  End Sub  
End Module  
```  
  
```csharp  
using System.Data.Sql;  
  
class Program  
{  
  static void Main()  
  {  
    // Retrieve the enumerator instance and then the data.  
    SqlDataSourceEnumerator instance =  
      SqlDataSourceEnumerator.Instance;  
    System.Data.DataTable table = instance.GetDataSources();  
  
    // Display the contents of the table.  
    DisplayData(table);  
  
    Console.WriteLine("Press any key to continue.");  
    Console.ReadKey();  
  }  
  
  private static void DisplayData(System.Data.DataTable table)  
  {  
    foreach (System.Data.DataRow row in table.Rows)  
    {  
      foreach (System.Data.DataColumn col in table.Columns)  
      {  
        Console.WriteLine("{0} = {1}", col.ColumnName, row[col]);  
      }  
      Console.WriteLine("============================");  
    }  
  }  
}  
```  
  
## <a name="see-also"></a>参照  
 [SQL Server と ADO.NET](../../../../../docs/framework/data/adonet/sql/index.md)  
 [ADO.NET のマネージ プロバイダーと DataSet デベロッパー センター](http://go.microsoft.com/fwlink/?LinkId=217917)
