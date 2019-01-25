---
title: '- (負の)(Entity SQL)'
ms.date: 03/30/2017
ms.assetid: 208e54ef-4741-4ec5-89d6-6ff700863cb0
ms.openlocfilehash: f33b672ecd635234b8a8859651d117aabdaf14d5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54745854"
---
# <a name="--negative-entity-sql"></a>- (負符号) (Entity SQL)
数値式の負の値を返します。  
  
## <a name="syntax"></a>構文  
  
```  
- expression  
```  
  
## <a name="arguments"></a>引数  
 `expression`  
 任意の数値データ型の有効な式。  
  
## <a name="result-types"></a>戻り値の型  
 `expression`のデータ型。  
  
## <a name="remarks"></a>Remarks  
 符号なしの型を `expression` に指定した場合、戻り値の型は、 `expression`の型と最も関連性の高い符号付きの型になります。 たとえば、 `expression` に Byte 型を指定した場合、Int16 型の値が返されます。  
  
## <a name="example"></a>例  
 次の Entity SQL クエリでは、- 算術演算子を使用して、数値式の負の値を返します。 このクエリは、AdventureWorks Sales Model に基づいています。 このクエリをコンパイルして実行するには、次の手順を実行します。  
  
1.  」の手順に従って[方法。StructuralType 結果を返すクエリを実行](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)します。  
  
2.  次のクエリを引数として `ExecuteStructuralTypeQuery` メソッドに渡します。  
  
 [!code-csharp[DP EntityServices Concepts 2#NEGATIVE](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#negative)]  
  
## <a name="see-also"></a>関連項目
- [Entity SQL リファレンス](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
