---
title: "方法 : クエリで情報を取得する"
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
ms.assetid: e538d288-2070-40ca-9da6-4fbc68cd6ad0
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 55ef74cecf5a3669662e5fe189aea88b7d912344
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/17/2018
---
# <a name="how-to-query-for-information"></a>方法 : クエリで情報を取得する
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] クエリでは、[!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] クエリと同じ構文を使用します。 唯一の違いは、オブジェクトで参照されている[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]クエリは、データベース内の要素にマップされます。 詳細については、「[LINQ クエリの概要 (C#)](~/docs/csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md)」を参照してください。  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] は、作成したクエリを同等の SQL クエリに変換し、それをサーバーに送って処理します。  
  
 [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] クエリの機能の中には、[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] アプリケーションで特に注意を要するものがあります。 詳細については、次を参照してください。[クエリの概念](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)です。  
  
## <a name="example"></a>例  
 次のクエリは、ロンドンからの顧客のリストを取得します。 この例の `Customers` は、Northwind サンプル データベース内のテーブルです。  
  
 [!code-csharp[DLinqQuerying#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#1)]
 [!code-vb[DLinqQuerying#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#1)]  
  
## <a name="see-also"></a>参照  
 [オブジェクト モデルの作成](../../../../../../docs/framework/data/adonet/sql/linq/creating-the-object-model.md)  
 [サンプル データベースのダウンロード](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)  
 [データベースに対するクエリの実行](../../../../../../docs/framework/data/adonet/sql/linq/querying-the-database.md)
