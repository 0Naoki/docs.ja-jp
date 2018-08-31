---
title: LINQ to Entities クエリ内の式
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d70b502f-6a15-4120-b4fe-500b173ad9cc
ms.openlocfilehash: dccf3ab1a619222cdf2db54673718eb103aee2fb
ms.sourcegitcommit: a368166a51e5204c0224fbf5e46476e3ed122817
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2018
ms.locfileid: "43331723"
---
# <a name="expressions-in-linq-to-entities-queries"></a>LINQ to Entities クエリ内の式
式は、単一の値、オブジェクト、メソッド、または名前空間として評価されるコード フラグメントです。 式には、リテラル値、メソッド呼び出し、演算子とそのオペランド、または単純な名前を含めることができます。 単純な名前には、変数、型メンバー、メソッド パラメーター、名前空間、または型の名前を指定できます。 式では、他の式をパラメーターとして使用する演算子、またはパラメーターが他のメソッド呼び出しであるメソッド呼び出しを使用できます。 したがって、単純な式だけでなく、非常に複雑な式も作成できます。  
  
 [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)]クエリ、式には、内の型で許可されているもの、<xref:System.Linq.Expressions>名前空間、ラムダ式を含むです。 [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] クエリで使用可能な式は、[!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] に対してクエリを実行するために使用可能な式のスーパーセットです。  式に対するクエリの一部である、[!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)]でサポートされる操作に制限されて`ObjectQuery<T>`と基になるデータ ソース。  
  
 次の例では、`Where` 句で使用される比較の式を示します。  
  
 [!code-csharp[DP L2E Conceptual Examples#WhereExpression](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#whereexpression)]
 [!code-vb[DP L2E Conceptual Examples#WhereExpression](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#whereexpression)]  
  
> [!NOTE]
>  C# の `unchecked` などの特殊な言語構造は、[!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] では意味がありません。  
  
## <a name="in-this-section"></a>このセクションの内容  
 [定数式](../../../../../../docs/framework/data/adonet/ef/language-reference/constant-expressions.md)  
  
 [比較式](../../../../../../docs/framework/data/adonet/ef/language-reference/comparison-expressions.md)  
  
 [NULL 比較](../../../../../../docs/framework/data/adonet/ef/language-reference/null-comparisons.md)  
  
 [初期化式](../../../../../../docs/framework/data/adonet/ef/language-reference/initialization-expressions.md)  
  
 [ナビゲーション プロパティ](https://msdn.microsoft.com/library/41e1e6b9-8a57-467d-99d9-1857d2ca2ea5)  
  
## <a name="see-also"></a>関連項目  
 [ADO.NET Entity Framework](../../../../../../docs/framework/data/adonet/ef/index.md)
