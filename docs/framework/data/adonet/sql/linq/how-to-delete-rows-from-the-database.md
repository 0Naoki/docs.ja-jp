---
title: '方法 : 行をデータベースから削除する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 2144c99b-8055-4080-a5c6-1ea14335e2a3
ms.openlocfilehash: 179656fbecdc8efbef323c1882d756dea564c152
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-delete-rows-from-the-database"></a>方法 : 行をデータベースから削除する
データベース内の行を削除するには、対応するから削除[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]テーブルに関連付けられたコレクションからのオブジェクト。 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 適切な SQL への変更を変換`DELETE`コマンド。  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] は連鎖削除操作をサポートせず、認識もしません。 制約を持つテーブルの行を削除するには、次のいずれかのタスクを完了する必要があります。  
  
-   データベース内の外部キー制約で `ON DELETE CASCADE` 規則を設定する。  
  
-   独自のコードを使用して、親オブジェクトの削除を妨げる子オブジェクトを最初に削除する。  
  
 それ以外の場合は、例外がスローされます。 後で説明する 2 番目のコード例を参照してください。  
  
> [!NOTE]
>  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] の `Insert`、`Update`、および `Delete` の既定のデータベース操作メソッドはオーバーライドできます。 詳細については、次を参照してください。[のカスタマイズを挿入、更新、および削除を行う](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md)です。  
>   
>  Visual Studio を使用している開発者が使用できる、[!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)]同じ用途のストアド プロシージャを開発します。  
  
 以下の手順では、有効な <xref:System.Data.Linq.DataContext> で Northwind データベースに接続されるものと想定しています。 詳細については、次を参照してください。[する方法: データベースへの接続](../../../../../../docs/framework/data/adonet/sql/linq/how-to-connect-to-a-database.md)です。  
  
### <a name="to-delete-a-row-in-the-database"></a>データベースから行を削除するには  
  
1.  データベースで削除する行をクエリします。  
  
2.  <xref:System.Data.Linq.Table%601.DeleteOnSubmit%2A> メソッドを呼び出します。  
  
3.  データベースに変更内容を送信します。  
  
## <a name="example"></a>例  
 この最初のコード例では、注文 #11000 に属する注文詳細情報をデータベースに照会し、それらの注文詳細情報を削除するようにマークして、変更をデータベースに送信します。  
  
 [!code-csharp[System.Data.Linq.Table#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.table/cs/program.cs#3)]
 [!code-vb[System.Data.Linq.Table#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.table/vb/module1.vb#3)]  
  
## <a name="example"></a>例  
 この 2 番目のコード例の目的は、注文 (#10250) を削除することです。 このコードは、まず、`OrderDetails` テーブルを調べて、削除対象の注文に子が存在するかどうかを確認します。 注文に子が存在する場合は、最初に子を、次に注文を削除するようにマークします。 <xref:System.Data.Linq.DataContext> によって、データベース制約に従って削除コマンドがデータベースに送信され、正しい順序で実際の削除が行われます。  
  
 [!code-csharp[DLinqCascadeWorkaround#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCascadeWorkaround/cs/Program.cs#1)]
 [!code-vb[DLinqCascadeWorkaround#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCascadeWorkaround/vb/Module1.vb#1)]  
  
## <a name="see-also"></a>関連項目  
 [方法 : 変更の競合を管理する](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)  
 [方法: 更新、挿入、および削除 (O/R デザイナー) を実行するストアド プロシージャを割り当てる](/visualstudio/data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer)  
 [データの変更と変更の送信](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)
