---
title: DEREF (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4c78e833-b260-453d-9bf4-eb39857dd0fa
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 49ae645baccf877a8e9c0f80ac8827823b9d6c34
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2017
---
# <a name="deref-entity-sql"></a>DEREF (Entity SQL)
参照値を逆参照し、その逆参照の結果を生成します。  
  
## <a name="syntax"></a>構文  
  
```  
SELECT DEREF ( o.expression ) from Table as o;  
```  
  
## <a name="arguments"></a>引数  
 `expression`  
 コレクションを返す任意の有効なクエリ式。  
  
## <a name="return-value"></a>戻り値  
 参照されるエンティティの値。  
  
## <a name="remarks"></a>コメント  
 DEREF 演算子は参照値を逆参照し、その逆参照の結果を生成します。 たとえば場合、 `r` ref 型の参照は、\<T >、`Deref``(r)`型の式は、`T`によって参照されるエンティティを生成`r`です。 参照値が null または未解決 (つまり、参照先が存在しない) の場合、DEREF 演算子の結果は null になります。  
  
## <a name="example"></a>例  
 次の [!INCLUDE[esql](../../../../../../includes/esql-md.md)] クエリでは、DEREF 演算子を使用して参照値を逆参照し、その逆参照の結果を生成します。 このクエリは、AdventureWorks Sales Model に基づいています。 このクエリをコンパイルして実行するには、次の手順を実行します。  
  
1.  」の手順に従って[する方法: PrimitiveType 結果が返されますそのクエリを実行する](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md)です。  
  
2.  次のクエリを引数として ExecutePrimitiveTypeQuery メソッドに渡します。  
  
 [!code-csharp[DP EntityServices Concepts 2#DEREF](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#deref)]  
  
## <a name="see-also"></a>関連項目  
 [Entity SQL リファレンス](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [REF](../../../../../../docs/framework/data/adonet/ef/language-reference/ref-entity-sql.md)  
 [CREATEREF](../../../../../../docs/framework/data/adonet/ef/language-reference/createref-entity-sql.md)  
 [キー](../../../../../../docs/framework/data/adonet/ef/language-reference/key-entity-sql.md)  
 [Null 許容の構造化型](../../../../../../docs/framework/data/adonet/ef/language-reference/nullable-structured-types-entity-sql.md)
