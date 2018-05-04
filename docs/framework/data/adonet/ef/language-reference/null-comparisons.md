---
title: NULL 比較
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ef88af8c-8dfe-4556-8b56-81df960a900b
ms.openlocfilehash: f4d4f6cdbb5ac6bae3af66d46599ec65aaae22f4
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="null-comparisons"></a>NULL 比較
データ ソースの `null` 値は不明な値を表します。 [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] クエリでは、NULL 値をチェックして、必ず NULL でない有効なデータを持つ行に特定の計算または比較を行うようにすることができます。 ただし、CLR の NULL セマンティクスは、データ ソースの NULL セマンティクスとは異なる場合があります。 ほとんどのデータベースでは、3 値論理を使用して NULL 比較を処理します。 つまり、null 値に対する比較には評価されません`true`または`false`、評価結果が`unknown`です。 これは、多くの場合は ANSI NULL の実装ですが、そうでない場合もあります。  
  
 SQL Server の既定では、NULL = NULL の比較は NULL 値を返します。 次の例では、`ShipDate` が NULL である行が結果セットから除外され、[!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] ステートメントは 0 行を返します。  
  
```  
-- Find order details and orders with no ship date.  
SELECT h.SalesOrderID  
FROM Sales.SalesOrderHeader h  
JOIN Sales.SalesOrderDetail o ON o.SalesOrderID = h.SalesOrderID  
WHERE h.ShipDate IS Null  
```  
  
 これは、NULL = NULL の比較が true を返す CLR の NULL セマンティクスとは大きく異なります。  
  
 次の LINQ クエリは CLR で表されますが、データ ソースで実行されます。 CLR セマンティクスがデータ ソースで使用される保証はないため、動作は予測できません。  
  
 [!code-csharp[DP L2E Conceptual Examples#JoinOnNull](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#joinonnull)]
 [!code-vb[DP L2E Conceptual Examples#JoinOnNull](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#joinonnull)]  
  
## <a name="key-selectors"></a>キー セレクター  
 A*キー セレクター*要素からキーを抽出する、標準クエリ演算子で使用される関数。 キー セレクター関数では、式を定数と比較できます。 式が NULL 定数と比較される場合、または 2 つの NULL 定数が比較される場合、CLR の NULL セマンティクスが使用されます。 データ ソースの NULL 値を持つ 2 つの列が比較される場合は、ストア NULL セマンティクスが使用されます。 キー セレクターは、<xref:System.Linq.Queryable.GroupBy%2A> など、グループ化や並べ替えの標準クエリ演算子で使用される場合が多く、クエリ結果の並べ替えやグループ化に使用するキーを選択できます。  
  
## <a name="null-property-on-a-null-object"></a>NULL オブジェクトの NULL プロパティ  
 [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] では、NULL オブジェクトのプロパティは NULL です。 CLR で NULL オブジェクトのプロパティを参照しようとすると、<xref:System.NullReferenceException> が返されます。 LINQ クエリに NULL オブジェクトのプロパティが含まれている場合、動作の一貫性が失われることがあります。  
  
 たとえば、次のクエリでは、`NewProduct` へのキャストはコマンド ツリー レイヤーで行われ、`Introduced` プロパティが NULL になる可能性があります。 <xref:System.DateTime> の比較が true に評価されるように NULL 比較がデータベースで定義されている場合に、その行が含められます。  
  
 [!code-csharp[DP L2E Conceptual Examples#CastResultsIsNull](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#castresultsisnull)]
 [!code-vb[DP L2E Conceptual Examples#CastResultsIsNull](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#castresultsisnull)]  
  
## <a name="passing-null-collections-to-aggregate-functions"></a>集計関数に NULL コレクションを渡す  
 [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)]をサポートするコレクションを渡すと、`IQueryable`で集計関数では、データベースで集計演算が実行されます。 メモリ内で実行されたクエリとデータベースで実行されたクエリの結果の違いがある可能性があります。 メモリ内のクエリを使用して、一致がない場合、クエリは 0 を返します。 データベースでは、これと同じクエリから `null` が返されます。 場合、`null`値が LINQ 集計関数に渡される、例外がスローされます。 受け入れるに`null`値、キャスト、型と null 許容型にクエリ結果を受信した種類のプロパティです。  
  
## <a name="see-also"></a>関連項目  
 [LINQ to Entities クエリ内の式](../../../../../../docs/framework/data/adonet/ef/language-reference/expressions-in-linq-to-entities-queries.md)
