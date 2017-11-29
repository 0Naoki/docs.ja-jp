---
title: ".NET Framework データ プロバイダー"
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
ms.assetid: 03a9fc62-2d24-491a-9fe6-d6bdb6dcb131
caps.latest.revision: "13"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 4c11b826a51cc4f1563729728626fb8041e31ee1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2017
---
# <a name="net-framework-data-providers"></a>.NET Framework データ プロバイダー
[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] データ プロバイダーは、データベースに接続して、コマンドを実行したり、結果を取得したりする目的で使用されます。 その結果は、直接処理されるか、必要に応じてユーザーに公開されるように <xref:System.Data.DataSet> に格納されるか、取得したデータセットを複数のソースからのデータと組み合わせるか、または、層間でリモート処理されます。 軽量な[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] データ プロバイダーでは、データ ソースとコード間に形成される層が最小限で済むため、機能を犠牲にすることなく、パフォーマンスを高めることができます。  
  
 次の表に、 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]に含まれているデータ プロバイダーを示します。  
  
|[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] データ プロバイダー|説明|  
|-------------------------------------------------------------------------------|-----------------|  
|[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Data Provider for [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)]|Microsoft [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)]へのデータ アクセスを提供します。 <xref:System.Data.SqlClient> 名前空間を使用してください。|  
|[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Data Provider for OLE DB|OLE DB を使用して公開されるデータ ソースに対応。 <xref:System.Data.OleDb> 名前空間を使用してください。|  
|[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Data Provider for ODBC|ODBC を使用して公開されるデータ ソースに対応。 <xref:System.Data.Odbc> 名前空間を使用してください。|  
|[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Data Provider for Oracle|Oracle データ ソースに対応。 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Data Provider for Oracle は、Oracle クライアント ソフトウェア バージョン 8.1.7 以降をサポートしています。 <xref:System.Data.OracleClient> 名前空間を使用してください。|  
|EntityClient プロバイダー|エンティティ データ モデル (EDM) アプリケーションにデータ アクセスを提供します。 <xref:System.Data.EntityClient> 名前空間を使用してください。|  
|[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Data Provider for [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] Compact 4.0|Microsoft [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] Compact 4.0 へのデータ アクセスを提供します。 [System.Data.SqlServerCe](http://msdn.microsoft.com/library/system.data.sqlserverce.aspx) 名前空間を使用します。|  
  
## <a name="core-objects-of-net-framework-data-providers"></a>.NET Framework Data Providers の核となるオブジェクト  
 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] データ プロバイダーを構成する核となる 4 つのオブジェクトの概要を、次の表に示します。  
  
|Object|説明|  
|------------|-----------------|  
|`Connection`|特定のデータ ソースへの接続を確立します。 すべての `Connection` オブジェクトの基本クラスは <xref:System.Data.Common.DbConnection> クラスです。|  
|`Command`|データ ソースに対してコマンドを実行します。 `Parameters` を公開し、 `Transaction` から `Connection`のスコープ内で実行できます。 すべての `Command` オブジェクトの基本クラスは <xref:System.Data.Common.DbCommand> クラスです。|  
|`DataReader`|データ ソースから、前方参照専用で読み取り専用のデータ ストリームを読み取ります。 すべての `DataReader` オブジェクトの基本クラスは <xref:System.Data.Common.DbDataReader> クラスです。|  
|`DataAdapter`|`DataSet` にデータ ソースのデータを読み込んだり、データ ソースの更新内容を解決したりします。 すべての `DataAdapter` オブジェクトの基本クラスは <xref:System.Data.Common.DbDataAdapter> クラスです。|  
  
 前の表で示した核となるクラスの他に、 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] データ プロバイダーには次の表に示すクラスも含まれます。  
  
|Object|説明|  
|------------|-----------------|  
|`Transaction`|データ ソースでトランザクション内にコマンドを追加します。 すべての `Transaction` オブジェクトの基本クラスは <xref:System.Data.Common.DbTransaction> クラスです。 ADO.NET は、 <xref:System.Transactions> 名前空間のクラスを使ったトランザクションもサポートします。|  
|`CommandBuilder`|`DataAdapter` のコマンド プロパティを自動的に生成したり、ストアド プロシージャからパラメーター情報を取得したり、 `Parameters` オブジェクトの `Command` コレクションにパラメーターを設定したりするためのヘルパー オブジェクトです。 すべての `CommandBuilder` オブジェクトの基本クラスは <xref:System.Data.Common.DbCommandBuilder> クラスです。|  
|`ConnectionStringBuilder`|`Connection` オブジェクトが使用する接続文字列を簡単に作成および管理するためのヘルパー オブジェクトです。 すべての `ConnectionStringBuilder` オブジェクトの基本クラスは <xref:System.Data.Common.DbConnectionStringBuilder> クラスです。|  
|`Parameter`|コマンドやストアド プロシージャの入力パラメーター、出力パラメーター、および戻り値パラメーターを定義します。 すべての `Parameter` オブジェクトの基本クラスは <xref:System.Data.Common.DbParameter> クラスです。|  
|`Exception`|データ ソースでエラーが検出されたときに返されます。 クライアントで検出されたエラーの場合、 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] データ プロバイダーは [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 例外をスローします。 すべての `Exception` オブジェクトの基本クラスは <xref:System.Data.Common.DbException> クラスです。|  
|`Error`|データ ソースから返された警告またはエラー情報を公開します。|  
|`ClientPermission`|[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] データ プロバイダーにコード アクセス セキュリティ属性を提供します。 すべての `ClientPermission` オブジェクトの基本クラスは <xref:System.Data.Common.DBDataPermission> クラスです。|  
  
## <a name="net-framework-data-provider-for-includessnoversionincludesssnoversion-mdmd-sqlclient"></a>.NET Framework Data Provider for [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] (SqlClient)  
 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Data Provider for [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] (SqlClient) は独自のプロトコルを使用して [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)]と通信します。 これは軽量で高速に動作します。OLE DB または ODBC (Open Database Connectivity) 層を追加しなくても、直接 [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] にアクセスするように最適化されているためです。 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Data Provider for [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] と [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Data Provider for OLE DB の対比を次の図に示します。 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Data Provider for OLE DB は、接続プールとトランザクション サービスを提供する OLE DB Service コンポーネントと、データ ソース用の OLE DB プロバイダーの両方をとおして OLE DB データ ソースと通信します。  
  
> [!NOTE]
>  [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Data Provider for ODBC は、 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Data Provider for OLE DB に似たアーキテクチャを持っています。たとえば、ODBC Service コンポーネントへの呼び出しを行います。  
  
 ![データ プロバイダー](../../../../docs/framework/data/adonet/media/netdataproviders-bpuedev11.gif "NETDataProviders_bpuedev11")  
.NET Framework Data Provider for SQL Server と .NET Framework Data Provider for OLE DB の比較  
  
 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Data Provider for [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] クラスは、名前空間 <xref:System.Data.SqlClient> 内に配置されます。  
  
 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Data Provider for [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] はローカル トランザクションと分散トランザクションのどちらもサポートします。 分散トランザクションの場合、既定で、 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Data Provider for [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)]は自動的にトランザクションに参加し、トランザクションの詳細を Windows コンポーネント サービスまたは <xref:System.Transactions>から取得します。 詳細については、次を参照してください。[トランザクションと同時実行](../../../../docs/framework/data/adonet/transactions-and-concurrency.md)です。  
  
 名前空間 `System.Data.SqlClient` をユーザーのアプリケーションにインクルードする方法を次のコード サンプルで示します。  
  
```vb  
Imports System.Data.SqlClient  
```  
  
```csharp  
using System.Data.SqlClient;  
```  
  
## <a name="net-framework-data-provider-for-ole-db"></a>.NET Framework Data Provider for OLE DB  
 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Data Provider for OLE DB (OleDb) は、COM 相互運用機能を介してネイティブ OLE DB を使用することで、データへのアクセスを可能にします。 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Data Provider for OLE DB はローカル トランザクションと分散トランザクションのどちらもサポートします。 分散トランザクションの場合、既定で、 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Data Provider for OLE DB は自動的にトランザクションに参加し、トランザクションの詳細を Windows コンポーネント サービスから取得します。 詳細については、次を参照してください。[トランザクションと同時実行](../../../../docs/framework/data/adonet/transactions-and-concurrency.md)です。  
  
 [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)]とのテストが完了しているプロバイダーを次の表に示します。  
  
|ドライバー|プロバイダー|  
|------------|--------------|  
|SQLOLEDB|Microsoft OLE DB Provider for [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)]|  
|MSDAORA|Microsoft OLE DB Provider for Oracle|  
|Microsoft.Jet.OLEDB.4.0|OLE DB Provider for Microsoft Jet|  
  
> [!NOTE]
>  [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] アプリケーションなどのマルチスレッド アプリケーションのデータ ソースとして Access (Jet) データベースを使用することはお勧めできません。 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] アプリケーションのデータ ソースとして Jet を使用する必要がある場合、 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] アプリケーションから Access データベースへの接続で問題が発生することがあるので注意してください。  
  
 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Data Provider for OLE DB は OLE DB バージョン 2.5 のインターフェイスをサポートしていません。 OLE DB 2.5 インターフェイスのサポートを必要とする OLE DB Providers は、 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Data Provider for OLE DB と併用した場合、適切に機能しません。 これには Microsoft OLE DB Provider for Exchange および Microsoft OLE DB Provider for Internet Publishing が含まれます。  
  
 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Data Provider for OLE DB と OLE DB Provider for ODBC (MSDASQL) は併用できません。 [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)]を使用して ODBC データ ソースにアクセスするには、 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Data Provider for ODBC を使用してください。  
  
 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Data Provider for OLE DB クラスは、名前空間 <xref:System.Data.OleDb> 内に配置されます。 名前空間 `System.Data.OleDb` をユーザーのアプリケーションにインクルードする方法を次のコード サンプルで示します。  
  
```vb  
Imports System.Data.OleDb  
```  
  
```csharp  
using System.Data.OleDb;  
```  
  
## <a name="net-framework-data-provider-for-odbc"></a>.NET Framework Data Provider for ODBC  
 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Data Provider for ODBC (Odbc) は、ネイティブ ODBC ドライバー マネージャー (DM) を使用することで、データへのアクセスを可能にします。 ODBC データ プロバイダーはローカル トランザクションと分散トランザクションのどちらもサポートします。 分散トランザクションの場合、既定で、ODBC データ プロバイダーは自動的にトランザクションに参加し、トランザクションの詳細を Windows コンポーネント サービスから取得します。 詳細については、次を参照してください。[トランザクションと同時実行](../../../../docs/framework/data/adonet/transactions-and-concurrency.md)です。  
  
 [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)]とのテストが完了している ODBC ドライバーを次の表に示します。  
  
|ドライバー|  
|------------|  
|[!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)]|  
|Microsoft ODBC for Oracle|  
|Microsoft Access ドライバー (*.mdb)|  
  
 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Data Provider for ODBC クラスは、名前空間 <xref:System.Data.Odbc> 内に配置されます。  
  
 名前空間 `System.Data.Odbc` をユーザーのアプリケーションにインクルードする方法を次のコード サンプルで示します。  
  
```vb  
Imports System.Data.Odbc  
```  
  
```csharp  
using System.Data.Odbc;  
```  
  
> [!NOTE]
>  [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Data Provider for ODBC を使用する場合、MDAC 2.6 以降が必要となります。MDAC 2.8 SP1 をお勧めします。 MDAC 2.8 SP1 は「 [データ アクセスおよびストレージ デベロッパー センター](http://go.microsoft.com/fwlink/?linkid=4173)」からダウンロードできます。  
  
## <a name="net-framework-data-provider-for-oracle"></a>.NET Framework Oracle 用データ プロバイダー  
 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Data Provider for Oracle (OracleClient) は、Oracle クライアント接続ソフトウェアを介して、Oracle データ ソースのデータへのアクセスを可能にします。 このデータ プロバイダーは Oracle クライアント ソフトウェア バージョン 8.1.7 以降をサポートしています。 データ プロバイダーはローカル トランザクションと分散トランザクションのどちらもサポートします。 詳細については、次を参照してください。[トランザクションと同時実行](../../../../docs/framework/data/adonet/transactions-and-concurrency.md)です。  
  
 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Data Provider for Oracle を使用する場合、Oracle データ ソースに接続する前に、Oracle クライアント ソフトウェア (バージョン 8.1.7 以降) をシステムにインストールする必要があります。  
  
 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Data Provider for Oracle クラスは、名前空間 <xref:System.Data.OracleClient> 内に配置され、 `System.Data.OracleClient.dll` アセンブリに格納されます。 このデータ プロバイダーを使用するアプリケーションをコンパイルする場合は、 `System.Data.dll` と `System.Data.OracleClient.dll` の両方を参照する必要があります。  
  
 名前空間 `System.Data.OracleClient` をユーザーのアプリケーションにインクルードする方法を次のコード サンプルで示します。  
  
```vb  
Imports System.Data  
Imports System.Data.OracleClient  
```  
  
```csharp  
using System.Data;  
using System.Data.OracleClient;  
```  
  
## <a name="choosing-a-net-framework-data-provider"></a>.NET Framework データ プロバイダーの選択  
 アプリケーションのデザインおよびデータ ソースによっては、 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] データ プロバイダーを選択すると、アプリケーションのパフォーマンス、能力、および整合性が向上します。 各 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] データ プロバイダーが持つ利点と制限事項を次の表で説明します。  
  
|プロバイダー|ノート|  
|--------------|-----------|  
|[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Data Provider for [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)]|[!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)]を使用する中間層アプリケーションに推奨されています。<br /><br /> Microsoft Database Engine (MSDE) または [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)]を使用する単層アプリケーションに推奨されています。<br /><br /> SQLOLEDB (OLE DB Provider for [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] ) と [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Data Provider for OLE DB を併用する場合に推奨します。|  
|[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Data Provider for OLE DB|[!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)]では、このプロバイダーではなく [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Data Provider for [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] が推奨されます。<br /><br /> Microsoft Access データベースを使用する単層アプリケーションに推奨されます。 Access データベースを中間層アプリケーションで使用することはお勧めできません。|  
|[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]' Data Provider for ODBC|中間層アプリケーションおよび単層アプリケーションで ODBC データ ソースを使用する場合に推奨します。|  
|[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]' Data Provider for Oracle|中間層アプリケーションおよび単層アプリケーションで Oracle データ ソースを使用する場合に推奨します。|  
  
## <a name="entityclient-provider"></a>EntityClient プロバイダー  
 EntityClient プロバイダーは、エンティティ データ モデル (EDM) に基づくデータ アクセスで使用されます。 他の .NET Framework データ プロバイダーとは異なり、データ ソースと直接やり取りしません。 代わりに Entity SQL を使用して、基になるデータ プロバイダーと通信します。 詳細については、「 [EntityClient and Entity SQL](http://msdn.microsoft.com/en-us/49202ab9-ac98-4b4b-a05c-140e422bf527)」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [ADO.NET の概要](../../../../docs/framework/data/adonet/ado-net-overview.md)  
 [ADO.NET でのデータの取得および変更](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [ADO.NET のマネージ プロバイダーと DataSet デベロッパー センター](http://go.microsoft.com/fwlink/?LinkId=217917)
