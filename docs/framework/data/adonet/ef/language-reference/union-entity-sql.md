---
title: UNION (Entity SQL)
ms.date: 03/30/2017
ms.assetid: df98a4db-b00d-4c8b-bd74-0d285f27e1df
ms.openlocfilehash: 52a7a332166250e8fa8084986fd0d89da6fdf42d
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="union-entity-sql"></a>UNION (Entity SQL)
複数のクエリの結果を 1 つのコレクションに結合します。  
  
## <a name="syntax"></a>構文  
  
```  
expression  
UNION [ ALL ]  
expression  
```  
  
## <a name="arguments"></a>引数  
 `expression`  
 コレクションと結合するコレクションを返す任意の有効なクエリ式。すべての式は、 `expression`と同じ型であるか、共通の基本データ型または派生型である必要があります。  
  
 UNION  
 複数のコレクションを結合し、1 つのコレクションとして返すことを指定します。  
  
 ALL  
 複数のコレクションを結合し、重複も含めて 1 つのコレクションとして返すことを指定します。 指定しない場合、重複は結果コレクションから削除されます。  
  
## <a name="return-value"></a>戻り値  
 `expression`と同じ型であるか、共通の基本データ型または派生型であるコレクション。  
  
## <a name="remarks"></a>コメント  
 UNION は、 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] の集合演算子の 1 つです。 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] のすべての集合演算子は左から右に評価されます。 優先順位について、 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set 演算子を参照してください[EXCEPT](../../../../../../docs/framework/data/adonet/ef/language-reference/except-entity-sql.md)です。  
  
## <a name="example"></a>例  
 次の Entity SQL クエリでは、UNION ALL 演算子を使用して、2 つのクエリの結果を 1 つのコレクションに結合します。 このクエリは、AdventureWorks Sales Model に基づいています。 このクエリをコンパイルして実行するには、次の手順を実行します。  
  
1.  「 [StructuralType 結果を返すクエリの実行方法](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)」の手順に従います。  
  
2.  次のクエリを引数として `ExecuteStructuralTypeQuery` メソッドに渡します。  
  
 [!code-csharp[DP EntityServices Concepts 2#UNION](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#union)]  
  
## <a name="see-also"></a>関連項目  
 [Entity SQL リファレンス](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
