---
title: "数値のシーケンスの合計の計算"
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
ms.assetid: 24e335b0-984e-4825-8721-0a91b533b7c3
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 547d9f245d41fac2e2d65877ddbb2a8660d73c42
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/17/2018
---
# <a name="compute-the-sum-of-values-in-a-numeric-sequence"></a>数値のシーケンスの合計の計算
<xref:System.Linq.Enumerable.Sum%2A> 演算子を使用すると、シーケンス内の数値の合計を計算できます。  
  
 `Sum` の [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 演算子には、次の特性があります。  
  
-   標準クエリ演算子の集計演算子 `Sum` では、空のシーケンスや null のみを含むシーケンスはゼロに評価されます。 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] では、SQL のセマンティクスは維持されます。 したがって、空のシーケンスまたは null のみを含むシーケンスについては、`Sum` 演算子は 0 ではなく null に評価します。  
  
-   [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] での集計には、中間結果に対する SQL の制限が適用されます。 32 ビット整数の合計値は 64 ビットの結果を使用して計算されていないと、オーバーフローが発生する、[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]の翻訳`Sum`です。 これは、標準クエリ演算子の実装で、対応するメモリ内シーケンスでオーバーフローが発生しない場合でも起こる可能性があります。  
  
## <a name="example"></a>例  
 `Order` テーブルに含まれるすべての注文の運賃の合計を求める例を次に示します。  
  
 Northwind サンプル データベースに対してこのクエリを実行した場合の出力は、`64942.6900` です。  
  
 [!code-csharp[DLinqQueryExamples#12](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#12)]
 [!code-vb[DLinqQueryExamples#12](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#12)]  
  
## <a name="example"></a>例  
 すべての製品の受注単位の合計を求める例を次に示します。  
  
 Northwind サンプル データベースに対してこのクエリを実行した場合の出力は、`780` です。  
  
 `short` には `UnitsOnOrder` 型のオーバーロードがないため、short 型 (`Sum` など) をキャストする必要があります。  
  
 [!code-csharp[DLinqQueryExamples#13](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#13)]
 [!code-vb[DLinqQueryExamples#13](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#13)]  
  
## <a name="see-also"></a>参照  
 [集計クエリ](../../../../../../docs/framework/data/adonet/sql/linq/aggregate-queries.md)  
 [サンプル データベースのダウンロード](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)
