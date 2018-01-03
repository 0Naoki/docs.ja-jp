---
title: SET (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 28b4deac-c7e4-4f09-b428-4d352ef2dc94
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 12ce6c47db89fe91fd11a94aa10a47b57b45d736
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="set-entity-sql"></a>SET (Entity SQL)
SET 式は、重複する要素をすべて除外した新しいコレクションを生成することによって、オブジェクトのコレクションを 1 つの集合に変換します。  
  
## <a name="syntax"></a>構文  
  
```  
SET ( expression )  
```  
  
## <a name="arguments"></a>引数  
 `expression`  
 コレクションを返す任意の有効なクエリ式。  
  
## <a name="remarks"></a>コメント  
 集合式 `SET(c)` は、論理上、次の select ステートメントと等価です。  
  
```  
SELECT VALUE DISTINCT c FROM c  
```  
  
 `SET` は、 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] の集合演算子の 1 つです。 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] のすべての集合演算子は左から右に評価されます。 参照してください[EXCEPT](../../../../../../docs/framework/data/adonet/ef/language-reference/except-entity-sql.md)の優先順位について、[!INCLUDE[esql](../../../../../../includes/esql-md.md)]演算子を設定します。  
  
## <a name="example"></a>例  
 次の Entity SQL クエリでは、SET 式を使用して、オブジェクトのコレクションを 1 つの集合に変換します。 このクエリは、AdventureWorks Sales Model に基づいています。 このクエリをコンパイルして実行するには、次の手順を実行します。  
  
1.  」の手順に従って[する方法: PrimitiveType 結果が返されますそのクエリを実行する](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md)です。  
  
2.  次のクエリを引数として `ExecutePrimitiveTypeQuery` メソッドに渡します。  
  
 [!code-csharp[DP EntityServices Concepts 2#SET](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#set)]  
  
## <a name="see-also"></a>参照  
 [Entity SQL リファレンス](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
