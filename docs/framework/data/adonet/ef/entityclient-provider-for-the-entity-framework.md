---
title: Entity Framework 用の EntityClient プロバイダー
ms.date: 03/30/2017
ms.assetid: 8c5db787-78e6-4a34-8dc1-188bca0aca5e
ms.openlocfilehash: 1bafdc250c7edc009352d668e8ee7962a86fe8bf
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2018
ms.locfileid: "43806174"
---
# <a name="entityclient-provider-for-the-entity-framework"></a>Entity Framework 用の EntityClient プロバイダー
EntityClient プロバイダーは、概念モデルで記述されているデータにアクセスするために Entity Framework アプリケーションで使用するデータ プロバイダーです。 概念モデルについては、次を参照してください。[モデリング ファイルとマッピング](../../../../../docs/framework/data/adonet/ef/modeling-and-mapping.md)します。 EntityClient は、他の .NET Framework データ プロバイダーを使用してデータ ソースにアクセスします。 たとえば、EntityClient は、SQL Server データベースにアクセスするときは .NET Framework Data Provider for SQL Server (SqlClient) を使用します。 SqlClient プロバイダーについては、次を参照してください。 [Entity Framework 用 SqlClient](../../../../../docs/framework/data/adonet/ef/sqlclient-for-the-entity-framework.md)します。 EntityClient プロバイダーは <xref:System.Data.EntityClient> 名前空間で実装されます。  
  
## <a name="managing-connections"></a>接続の管理  
 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]ストレージ固有の上にビルド[!INCLUDE[vstecado](../../../../../includes/vstecado-md.md)]提供することで、データ プロバイダー、<xref:System.Data.EntityClient.EntityConnection>基になるデータ プロバイダーおよびリレーショナル データベースにします。 構築する、<xref:System.Data.EntityClient.EntityConnection>オブジェクトを必要なモデルとマッピング、およびストレージ固有のデータ プロバイダー名と接続文字列を含むメタデータのセットを参照することがあります。 後に、<xref:System.Data.EntityClient.EntityConnection>はインプレースで概念モデルから生成されたクラスを使用してエンティティにアクセスできます。  
  
 app.config ファイルの接続文字列を指定できます。  
  
 <xref:System.Data.EntityClient> には、<xref:System.Data.EntityClient.EntityConnectionStringBuilder> クラスも含まれています。 このクラスを使用すると、開発者はこのクラスのプロパティおよびメソッドを使用することによって、正しい構文の接続文字列をプログラムで作成し、既存の接続文字列の解析や再作成を行うことができます。 詳細については、次を参照してください。[方法: EntityConnection の接続文字列を構築](../../../../../docs/framework/data/adonet/ef/how-to-build-an-entityconnection-connection-string.md)します。  
  
## <a name="creating-queries"></a>クエリの作成  
 [!INCLUDE[esql](../../../../../includes/esql-md.md)]言語は、ストレージの影響を受けない sql のエンティティの概念スキーマを直接操作し、継承やリレーションシップなどの Entity Data Model 概念をサポートします。 <xref:System.Data.EntityClient.EntityCommand>を実行するクラスが使用される、 [!INCLUDE[esql](../../../../../includes/esql-md.md)] entity model に対してコマンド。 <xref:System.Data.EntityClient.EntityCommand> オブジェクトを構築する場合は、ストアド プロシージャ名またはクエリ テキストを指定できます。 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] は、ストレージ固有のデータ プロバイダーと連携し、汎用的な [!INCLUDE[esql](../../../../../includes/esql-md.md)] をストレージ固有のクエリに変換します。 書き込みの詳細については[!INCLUDE[esql](../../../../../includes/esql-md.md)]クエリを参照してください[Entity SQL 言語](../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md)します。  
  
 次の例では、作成、<xref:System.Data.EntityClient.EntityCommand>オブジェクトられ、[!INCLUDE[esql](../../../../../includes/esql-md.md)]クエリ テキストにその<xref:System.Data.EntityClient.EntityCommand.CommandText%2A?displayProperty=nameWithType>プロパティ。 これは、[!INCLUDE[esql](../../../../../includes/esql-md.md)]クエリは、概念モデルから表示価格で並べ替えた製品を要求します。 次のコードでは、ストレージ モデルが認識されません。  
  
 `EntityCommand cmd = conn.CreateCommand();`  
  
 `cmd.CommandText = @"` `SELECT VALUE p`  
  
 `FROM AdventureWorksEntities.Product AS p`  
  
 `ORDER BY p.ListPrice ";`  
  
## <a name="executing-queries"></a>クエリの実行  
 クエリを実行すると、そのクエリが解析され、正規コマンド ツリーに変換されます。 すべての後続の処理は、コマンド ツリーで行われます。 コマンド ツリーは <xref:System.Data.EntityClient> など、[!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] と基になる <xref:System.Data.SqlClient> データ プロバイダー間の通信手段です。  
  
 概念モデルに対する <xref:System.Data.EntityClient.EntityDataReader> の実行結果は、<xref:System.Data.EntityClient.EntityCommand> によって公開されます。 <xref:System.Data.EntityClient.EntityDataReader> を返すコマンドを実行するには、<xref:System.Data.EntityClient.EntityCommand.ExecuteReader%2A> を呼び出します。 <xref:System.Data.EntityClient.EntityDataReader> は、構造化されたさまざまな結果を記述するための <xref:System.Data.IExtendedDataRecord> を実装します。  
  
## <a name="managing-transactions"></a>トランザクションの管理  
 Entity Framework では、自動トランザクションと明示的トランザクションという 2 つの使用方法があります。 自動トランザクションでは <xref:System.Transactions> 名前空間を使用し、明示的トランザクションでは <xref:System.Data.EntityClient.EntityTransaction> クラスを使用します。  
  
 は、概念モデルで公開されるデータを更新するには参照してください[方法: Entity Framework でトランザクションを管理](https://msdn.microsoft.com/library/4a55eb7f-f826-4a48-9df1-aebe2352ebef)します。  
  
## <a name="in-this-section"></a>このセクションの内容  
 [EntityConnection の接続文字列を作成する方法](../../../../../docs/framework/data/adonet/ef/how-to-build-an-entityconnection-connection-string.md)  
  
 [PrimitiveType 結果を返すクエリの実行方法](../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md)  
  
 [StructuralType 結果を返すクエリの実行方法](../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)  
  
 [RefType 結果を返すクエリの実行方法](../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-reftype-results.md)  
  
 [複合型を返すクエリの実行方法](../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-complex-types.md)  
  
 [入れ子になったコレクションを返すクエリの実行方法](../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-nested-collections.md)  
  
 [EntityCommand を使用してパラメーター化 Entity SQL クエリを実行する方法](../../../../../docs/framework/data/adonet/ef/how-to-execute-a-parameterized-entity-sql-query-using-entitycommand.md)  
  
 [EntityCommand を使用してパラメーター化されたストアド プロシージャを実行する方法](../../../../../docs/framework/data/adonet/ef/how-to-execute-a-parameterized-stored-procedure-using-entitycommand.md)  
  
 [ポリモーフィック クエリを実行する方法](../../../../../docs/framework/data/adonet/ef/how-to-execute-a-polymorphic-query.md)  
  
 [Navigate 演算子でリレーションシップをナビゲートする方法](../../../../../docs/framework/data/adonet/ef/how-to-navigate-relationships-with-the-navigate-operator.md)  
  
## <a name="see-also"></a>関連項目  
 [接続とトランザクションの管理](https://msdn.microsoft.com/library/b6659d2a-9a45-4e98-acaa-d7a8029e5b99)  
 [ADO.NET Entity Framework](../../../../../docs/framework/data/adonet/ef/index.md)  
 [言語リファレンス](../../../../../docs/framework/data/adonet/ef/language-reference/index.md)
