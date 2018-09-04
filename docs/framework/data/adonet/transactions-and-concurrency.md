---
title: トランザクションと同時実行
ms.date: 03/30/2017
ms.assetid: f46570de-9e50-4fe6-8710-a8c31fa8569b
ms.openlocfilehash: bd47c5e0e2b2086e5fd0482bf4319ebab5674a54
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "43563388"
---
# <a name="transactions-and-concurrency"></a>トランザクションと同時実行
トランザクションは、単一のコマンド、またはパッケージとして実行されるコマンドのグループで構成されます。 トランザクションを使用することで、複数の操作を 1 つの作業単位にまとめることができます。 トランザクションのあるポイントで障害が発生した場合は、トランザクションが開始される前の状態にすべての更新をロールバックできます。  
  
 データの一貫性を保証するために、トランザクションは ACID プロパティ (原始性、一貫性、分離性、および持続性) に準拠する必要があります。 Microsoft SQL Server など、ほとんどのリレーショナル データベース システムでは、クライアント アプリケーションが更新、挿入、または削除の操作を行うたびに、ロック、ログ、およびトランザクション管理の機能を提供し、トランザクションをサポートします。  
  
> [!NOTE]
>  複数のリソースがかかわるトランザクションで、ロックがあまりにも長く保持されると、同時実行数が少なくなる場合があります。 そのため、トランザクションはできるだけ短くします。  
  
 トランザクションに、同じデータベースまたはサーバーの複数のテーブルが含まれている場合、一般的にストアド プロシージャ内の明示的トランザクションの方がパフォーマンスが向上します。 SQL Server のストアド プロシージャにトランザクションを作成するには、Transact-SQL ステートメントの `BEGIN TRANSACTION`、`COMMIT TRANSACTION`、および `ROLLBACK TRANSACTION` を使用します。 詳細については、SQL Server オンライン ブックを参照してください。  
  
 SQL Server と Oracle 間のトランザクションなどの他のリソース マネージャーに関連するトランザクションでは、分散トランザクションが必要です。  
  
## <a name="in-this-section"></a>このセクションの内容  
 [ローカル トランザクション](../../../../docs/framework/data/adonet/local-transactions.md)  
 データベースに対してトランザクションを実行する方法を示します。  
  
 [分散トランザクション](../../../../docs/framework/data/adonet/distributed-transactions.md)  
 ADO.NET で分散トランザクションを実行する方法について説明します。  
  
 [SQL Server と System.Transactions の統合](../../../../docs/framework/data/adonet/system-transactions-integration-with-sql-server.md)  
 説明<xref:System.Transactions>分散トランザクションを使用するための SQL Server と統合します。  
  
 [オプティミスティック同時実行制御](../../../../docs/framework/data/adonet/optimistic-concurrency.md)  
 オプティミスティック同時実行制御とペシミスティック同時実行制御について、および同時実行違反をテストする方法について説明します。  
  
## <a name="see-also"></a>関連項目  
 [トランザクションの基礎](../../../../docs/framework/data/transactions/transaction-fundamentals.md)  
 [データ ソースへの接続](../../../../docs/framework/data/adonet/connecting-to-a-data-source.md)  
 [コマンドおよびパラメーター](../../../../docs/framework/data/adonet/commands-and-parameters.md)  
 [DataAdapter と DataReader](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)  
 [DbProviderFactories](../../../../docs/framework/data/adonet/dbproviderfactories.md)  
 [ADO.NET のマネージド プロバイダーと DataSet デベロッパー センター](https://go.microsoft.com/fwlink/?LinkId=217917)
