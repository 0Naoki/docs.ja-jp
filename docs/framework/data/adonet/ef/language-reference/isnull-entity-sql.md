---
title: ISNULL (Entity SQL)
ms.date: 03/30/2017
ms.assetid: dc7a0173-3664-4c90-a57b-5cbb0a8ed7ee
ms.openlocfilehash: 70ec49fd4643c67c6ad08fdda9166eeb8a64d254
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="isnull-entity-sql"></a>ISNULL (Entity SQL)
クエリ式が NULL かどうかを調べます。  
  
## <a name="syntax"></a>構文  
  
```  
expression IS [ NOT ] NULL  
```  
  
## <a name="arguments"></a>引数  
 `expression`  
 任意の有効なクエリ式。 コレクションにすることはできません。また、コレクション メンバーや、コレクション型のプロパティを持つレコード型を含めることはできません。  
  
 NOT  
 IS NULL の EDM.Boolean の結果を否定します。  
  
## <a name="return-value"></a>戻り値  
 `true` によって NULL が返される場合は `expression`、それ以外の場合は `false` です。  
  
## <a name="remarks"></a>コメント  
 外部結合の要素が NULL かどうかを確認するには、`IS NULL` を使用します。  
  
```  
select c   
      from LOB.Customers as c left outer join LOB.Orders as o   
                              on c.ID = o.CustomerID    
      where o is not null and o.OrderQuantity = @x  
```  
  
 メンバーに実際の値が含まれているかどうかを確認するには、`IS NULL` を使用します。  
  
```  
select c from LOB.Customer as c where c.DOB is not null  
```  
  
 次の表は、いくつかのパターンにおける `IS NULL` の動作を示しています。 すべての例外はクライアント側にスローされてから、プロバイダーが呼び出されます。  
  
|パターン|動作|  
|-------------|--------------|  
|null IS NULL|`true` を返します。|  
|TREAT (null AS EntityType) IS NULL|`true` を返します。|  
|TREAT (null AS ComplexType) IS NULL|エラーをスローします。|  
|TREAT (null AS RowType) IS NULL|エラーをスローします。|  
|EntityType IS NULL|`true` または `false` を返します。|  
|ComplexType IS NULL|エラーをスローします。|  
|RowType IS NULL|エラーをスローします。|  
  
## <a name="example"></a>例  
 次[!INCLUDE[esql](../../../../../../includes/esql-md.md)]クエリでは、IS NOT NULL 演算子を使用して、クエリ式が null でないかどうかを判断します。 このクエリは、AdventureWorks Sales Model に基づいています。 このクエリをコンパイルして実行するには、次の手順を実行します。  
  
1.  「 [StructuralType 結果を返すクエリの実行方法](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)」の手順に従います。  
  
2.  次のクエリを引数として `ExecuteStructuralTypeQuery` メソッドに渡します。  
  
 [!code-csharp[DP EntityServices Concepts 2#ISNULL](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#isnull)]  
  
## <a name="see-also"></a>関連項目  
 [Entity SQL リファレンス](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
