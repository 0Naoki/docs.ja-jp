---
title: "LINQ to SQL の主な機能"
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
ms.assetid: 061d98b2-baa7-4336-8ad2-c14de8134d91
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 70e783c0ad6b13097aaa1912f1338714a1f43f73
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="what-you-can-do-with-linq-to-sql"></a>LINQ to SQL の主な機能
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] は、SQL 開発者が期待するすべての主要な機能に対応しています。 情報の照会、テーブルへの情報の挿入、およびテーブルの情報の更新と削除を行うことができます。  
  
## <a name="selecting"></a>選択  
 選択 (*射影*) は、 [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] クエリを任意のプログラミング言語で記述し、そのクエリを実行して結果を取得することにより実現されます。 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 自体は、必要なすべての操作を、使い慣れた SQL の操作に変換します。 詳細については、「 [LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/index.md)」を参照してください。  
  
 次の例では、ロンドン在住の顧客の会社名を取得し、コンソール ウィンドウに表示します。  
  
 [!code-csharp[DLinqGettingStarted#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqGettingStarted/cs/Program.cs#1)]
 [!code-vb[DLinqGettingStarted#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqGettingStarted/vb/Module1.vb#1)]  
  
## <a name="inserting"></a>挿入  
 SQL の `Insert`を実行するには、前もって作成したオブジェクト モデルにオブジェクトを追加し、 <xref:System.Data.Linq.DataContext.SubmitChanges%2A> の <xref:System.Data.Linq.DataContext>を呼び出します。  
  
 `Customers` を使って、新規の顧客の情報を <xref:System.Data.Linq.Table%601.InsertOnSubmit%2A>テーブルに追加する方法を次の例に示します。  
  
 [!code-csharp[DLinqGettingStarted#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqGettingStarted/cs/Program.cs#2)]
 [!code-vb[DLinqGettingStarted#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqGettingStarted/vb/Module1.vb#2)]  
  
## <a name="updating"></a>Updating  
 データベース エントリの `Update` (更新) を実行するには、目的の項目をまず取得し、それをオブジェクト モデル内で直接編集します。 オブジェクトを変更した後で、 <xref:System.Data.Linq.DataContext.SubmitChanges%2A> の <xref:System.Data.Linq.DataContext> を呼び出してデータベースを更新します。  
  
 ロンドン出身のすべての顧客を取得する例を次に示します。 その後で、市の名前を "London" から "London - Metro" に変更します。 最後に、 <xref:System.Data.Linq.DataContext.SubmitChanges%2A> を呼び出して、変更をデータベースに送信します。  
  
 [!code-csharp[DLinqGettingStarted#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqGettingStarted/cs/Program.cs#3)]
 [!code-vb[DLinqGettingStarted#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqGettingStarted/vb/Module1.vb#3)]  
  
## <a name="deleting"></a>削除中  
 項目を `Delete` (削除) するには、項目を所属先のコレクションから削除してから、 <xref:System.Data.Linq.DataContext.SubmitChanges%2A> の <xref:System.Data.Linq.DataContext> を呼び出して、変更をコミットします。  
  
> [!NOTE]
>  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]連鎖削除操作は認識されません。 制約を持つテーブルの行を削除する場合を参照してください[する方法: 行をデータベースから削除](../../../../../../docs/framework/data/adonet/sql/linq/how-to-delete-rows-from-the-database.md)です。  
  
 次の例では、 `CustomerID` が `98128` の顧客をデータベースから取得します。 次に、顧客の行が取得されたことを確認した後で、 <xref:System.Data.Linq.Table%601.DeleteOnSubmit%2A> を呼び出して、このオブジェクトをコレクションから削除します。 最後に、 <xref:System.Data.Linq.DataContext.SubmitChanges%2A> を呼び出して、削除をデータベースに転送します。  
  
 [!code-csharp[DLinqGettingStarted#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqGettingStarted/cs/Program.cs#4)]
 [!code-vb[DLinqGettingStarted#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqGettingStarted/vb/Module1.vb#4)]  
  
## <a name="see-also"></a>参照  
 [プログラミング ガイド](../../../../../../docs/framework/data/adonet/sql/linq/programming-guide.md)  
 [LINQ to SQL オブジェクト モデル](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)  
 [はじめに](../../../../../../docs/framework/data/adonet/sql/linq/getting-started.md)
