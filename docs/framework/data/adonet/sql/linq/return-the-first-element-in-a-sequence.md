---
title: "シーケンスの最初の要素の取得"
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
ms.assetid: ccdc3777-b2c2-44e3-a627-abef8d79a555
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 476b8863d05f0c2d77b1b90c8795b85449ed3160
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="return-the-first-element-in-a-sequence"></a>シーケンスの最初の要素の取得
<xref:System.Linq.Enumerable.First%2A> 演算子を使用すると、シーケンスの内最初の要素を返すことができます。 <xref:System.Linq.Enumerable.First%2A> を使用するクエリは直ちに実行されます。  
  
> [!NOTE]
>  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] は <xref:System.Linq.Enumerable.Last%2A> 演算子をサポートしません。  
  
## <a name="example"></a>例  
 次のコードは、テーブル内の最初の `Shipper` を見つけます。  
  
 Northwind サンプル データベースに対してこのクエリを実行すると、結果は次のようになります。  
  
 `ID = 1, Company = Speedy Express`。  
  
 [!code-csharp[DLinqQueryExamples#14](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#14)]
 [!code-vb[DLinqQueryExamples#14](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#14)]  
  
## <a name="example"></a>例  
 次のコードは、`Customer` が BONAP の単一の `CustomerID` を見つけます。  
  
 Northwind サンプル データベースに対してこのクエリを実行すると、結果は `ID = BONAP, Contact = Laurence Lebihan` になります。  
  
 [!code-csharp[DLinqQueryExamples#15](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#15)]
 [!code-vb[DLinqQueryExamples#15](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#15)]  
  
## <a name="see-also"></a>参照  
 [クエリの例](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)  
 [サンプル データベースのダウンロード](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)
