---
title: THEN (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 54222642-23c6-4f61-9861-67caca53ac5f
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 99fd941c963ff87203d7b315beb606d40001224d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2017
---
# <a name="then-entity-sql"></a>THEN (Entity SQL)
WHEN 句が `true`として評価された場合の結果です。  
  
## <a name="syntax"></a>構文  
  
```  
WHEN when_expression THEN then_expression  
```  
  
## <a name="arguments"></a>引数  
 `when_expression`  
 任意の有効なブール式。  
  
 `then_expression`  
 コレクションを返す任意の有効なクエリ式。  
  
## <a name="remarks"></a>コメント  
 `when_expression` が `true`として評価された場合、対応する `then-expression`が評価されます。 WHEN の条件が満たされなかった場合は、 `else-expression` が評価されます。 ただし、 `else-expression`が存在しない場合、結果は NULL になります。  
  
 例については、次を参照してください。[ケース](../../../../../../docs/framework/data/adonet/ef/language-reference/case-entity-sql.md)です。  
  
## <a name="example"></a>例  
 次の Entity SQL クエリでは、CASE 式を使用して、一連の `Boolean` 式を評価します。 このクエリは、AdventureWorks Sales Model に基づいています。 このクエリをコンパイルして実行するには、次の手順を実行します。  
  
1.  」の手順に従って[する方法: PrimitiveType 結果が返されますそのクエリを実行する](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md)です。  
  
2.  次のクエリを引数として `ExecutePrimitiveTypeQuery` メソッドに渡します。  
  
 [!code-csharp[DP EntityServices Concepts 2#CASE_WHEN_THEN_ELSE](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#case_when_then_else)]  
  
## <a name="see-also"></a>関連項目  
 [場合](../../../../../../docs/framework/data/adonet/ef/language-reference/case-entity-sql.md)  
 [Entity SQL リファレンス](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
