---
title: SQL Server での複数データベースにまたがるアクセスの有効化
ms.date: 03/30/2017
ms.assetid: 10663fb6-434c-4c81-8178-ec894b9cf895
ms.openlocfilehash: 22fa2b48d795fb81b4740ce882f9bff632deabbd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="enabling-cross-database-access-in-sql-server"></a>SQL Server での複数データベースにまたがるアクセスの有効化
複数データベースの組み合わせ所有権は、あるデータベースのプロシージャが、別のデータベースのオブジェクトに依存している場合に作用します。 複数データベースの組み合わせ所有権は、単一データベースの組み合わせ所有権とほぼ同じように機能しますが、所有権の連鎖性を保つために、すべてのオブジェクトの所有者が同じログイン アカウントにマップされていることが必要です。 ソース データベース内のソース オブジェクトおよびターゲット データベース内のターゲット オブジェクトが同じログイン アカウントによって所有されている場合、ターゲット オブジェクトに対する権限は SQL Server によってチェックされません。  
  
## <a name="off-by-default"></a>既定で無効の機能  
 複数データベースにまたがる組み合わせ所有権は、既定では無効になっています。 次に示したように、複数データベースの組み合わせ所有権はセキュリティ上のリスクを伴うため無効にすることをお勧めします。  
  
-   `db_ddladmin` データベース ロールまたは `db_owners` データベース ロールのデータベース所有者およびメンバーは、他のユーザーによって所有されたオブジェクトを作成できます。 これらのオブジェクトが、他のデータベースのオブジェクトに依存している可能性もあります。 これは、複数データベースの組み合わせ所有権を有効にした場合、すべてのデータベースのデータについて、これらのユーザーを完全に信頼する必要があることを意味します。  
  
-   CREATE DATABASE 権限を持つユーザーは、新しいデータベースを作成したり、既存のデータベースをアタッチしたりできます。 複数データベースの組み合わせ所有権を有効にした場合、これらのユーザーが、新たに作成したデータベースから (または、アタッチしたデータベースから)、権限を持たない他のデータベース内のオブジェクトにアクセスできます。  
  
## <a name="enabling-cross-database-ownership-chaining"></a>複数データベースの組み合わせ所有権の有効化  
 高い権限が与えられたユーザーを完全に信頼できる環境であれば、複数データベースの組み合わせ所有権を有効にすることができます。 複数データベースの組み合わせ所有権は、セットアップ時にすべてのデータベースを対象に構成できるほか、[!INCLUDE[tsql](../../../../../includes/tsql-md.md)] コマンドの `sp_configure` および `ALTER DATABASE` を使用して特定のデータベースを対象に構成することもできます。  
  
 複数データベースの組み合わせ所有権を個別に構成するには、`sp_configure` を使用し、サーバーに対してこの機能を無効にします。 次に、ALTER DATABASE コマンドで SET DB_CHAINING ON を指定し、必要なデータベースに対してのみ、複数データベースの組み合わせ所有権を構成します。  
  
 次のサンプルでは、すべてのデータベースに対して複数データベースの組み合わせ所有権を有効にします。  
  
```  
EXECUTE sp_configure 'show advanced', 1;  
RECONFIGURE;  
EXECUTE sp_configure 'cross db ownership chaining', 1;  
RECONFIGURE;  
```  
  
 次のサンプルでは、特定のデータベースに対して複数データベースの組み合わせ所有権を有効にします。  
  
```  
ALTER DATABASE Database1 SET DB_CHAINING ON;  
ALTER DATABASE Database2 SET DB_CHAINING ON;  
```  
  
### <a name="dynamic-sql"></a>動的 SQL  
 動的に生成された SQL ステートメントの実行では、同じユーザーが両方のデータベースに存在しない限り、複数データベースの組み合わせ所有権は機能しません。 別のデータベース内のデータにアクセスするストアド プロシージャを作成し、両方のデータベースに存在する証明書と、プロシージャに署名して SQL Server でこの問題を回避操作できます。 これにより、ユーザーは、データベースへのアクセス許可が付与されていなくても、そのプロシージャによって使用されるデータベース リソースにアクセスできるようになります。  
  
## <a name="external-resources"></a>外部リソース  
 詳細については、次のリソースを参照してください。  
  
|リソース|説明|  
|--------------|-----------------|  
|[EXECUTE AS の使用によるデータベースの権限借用の拡張](http://msdn.microsoft.com/library/ms188304\(SQL.105\).aspx)と[Cross DB Ownership Chaining オプション](http://msdn.microsoft.com/library/ms188694.aspx)SQL Server オンライン ブックします。|複数データベースの SQL Server のインスタンスの組み合わせ所有権を構成する方法について説明します。|  
  
## <a name="see-also"></a>関連項目  
 [ADO.NET アプリケーションのセキュリティ保護](../../../../../docs/framework/data/adonet/securing-ado-net-applications.md)  
 [SQL Server セキュリティの概要](../../../../../docs/framework/data/adonet/sql/overview-of-sql-server-security.md)  
 [SQL Server でのストアド プロシージャを使用したアクセス許可の管理](../../../../../docs/framework/data/adonet/sql/managing-permissions-with-stored-procedures-in-sql-server.md)  
 [SQL Server での安全な動的 SQL の作成](../../../../../docs/framework/data/adonet/sql/writing-secure-dynamic-sql-in-sql-server.md)  
 [SQL Server でのストアド プロシージャの署名](../../../../../docs/framework/data/adonet/sql/signing-stored-procedures-in-sql-server.md)  
 [ADO.NET のマネージ プロバイダーと DataSet デベロッパー センター](http://go.microsoft.com/fwlink/?LinkId=217917)
