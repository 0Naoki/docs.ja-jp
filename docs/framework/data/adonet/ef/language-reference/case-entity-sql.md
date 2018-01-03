---
title: CASE (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 26a47873-e87d-4ba2-9e2c-3787c21efe89
caps.latest.revision: "5"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: df86e69684a111effc29a2663d18310b276f4b83
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="case-entity-sql"></a>CASE (Entity SQL)
一連の `Boolean` 式を評価して結果を決定します。  
  
## <a name="syntax"></a>構文  
  
```  
CASE  
     WHEN Boolean_expression THEN result_expression   
    [ ...n ]   
     [   
    ELSE else_result_expression   
     ]   
END  
```  
  
## <a name="arguments"></a>引数  
 `n`  
 複数の WHEN `Boolean_expression` THEN `result_expression` 句が使用できることを示すプレースホルダーです。  
  
 THEN `result_expression`  
 `Boolean_expression` が `true`に評価されると返される式です。 `result expression` は、任意の有効な式です。  
  
 ELSE `else_result_expression`  
 比較操作の評価がいずれも `true`でなかった場合に返される式です。 この引数を省略し、比較演算のいずれも `true`に評価されなかった場合、CASE は NULL を返します。 `else_result_expression` は、任意の有効な式です。 `else_result_expression` と任意の `result_expression` のデータ型は同一であるか、暗黙的な変換によって同一の型になる必要があります。  
  
 WHEN `Boolean_expression`  
 検索 CASE 形式を使用した場合に評価される `Boolean` 式です。 `Boolean_expression` は、任意の有効な `Boolean` 式です。  
  
## <a name="return-value"></a>戻り値  
 `result_expression` およびオプションの `else_result_expression`の一連の型の中から、最も優先順位の高い型を返します。  
  
## <a name="remarks"></a>コメント  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] の case 式は、 [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] の case 式と似ています。 case 式を使用すると、適切な結果が得られる式を、一連の条件判定によって決めることができます。 この形式の case 式では、1 つまたは複数の `Boolean` 式によって、最終的に使用される式が決定されます。  
  
 CASE 関数は、各 WHEN 句の `Boolean_expression` を指定された順序で評価し、 `result_expression` として評価された最初の `Boolean_expression` の `true`を返します。 残りの式は評価されません。 `Boolean_expression` の評価がいずれも `true`でなかった場合、データベース エンジンは、ELSE 句が指定されていれば `else_result_expression` を、ELSE 句が指定されていない場合は NULL 値を返します。  
  
 CASE ステートメントでマルチセットを取得することはできません。  
  
## <a name="example"></a>例  
 次の Entity SQL クエリでは、CASE 式を使用して、一連の `Boolean` 式を評価し、結果を取得しています。 このクエリは、AdventureWorks Sales Model に基づいています。 このクエリをコンパイルして実行するには、次の手順を実行します。  
  
1.  」の手順に従って[する方法: PrimitiveType 結果が返されますそのクエリを実行する](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md)です。  
  
2.  次のクエリを引数として `ExecutePrimitiveTypeQuery` メソッドに渡します。  
  
 [!code-csharp[DP EntityServices Concepts 2#CASE_WHEN_THEN_ELSE](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#case_when_then_else)]  
  
## <a name="see-also"></a>参照  
 [THEN](../../../../../../docs/framework/data/adonet/ef/language-reference/then-entity-sql.md)  
 [SELECT](../../../../../../docs/framework/data/adonet/ef/language-reference/select-entity-sql.md)  
 [Entity SQL リファレンス](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
