---
title: クエリ式の構文例:要素演算子
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 32268fe2-de18-4065-8060-f250def83837
ms.openlocfilehash: 19a68903783edfc190f0b32bd67fcc74e47937ea
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54681327"
---
# <a name="query-expression-syntax-examples-element-operators"></a>クエリ式の構文例:要素演算子
このトピックの例では、使用する方法を示します、<xref:System.Linq.Enumerable.First%2A>メソッド クエリを[AdventureWorks Sales Model](https://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832)クエリ式の構文を使用します。 これらの例で使用されている、AdventureWorks Sales Model は、AdventureWorks サンプル データベースの Contact、Address、Product、SalesOrderHeader、SalesOrderDetail の各テーブルから作成されています。  
  
 このトピックの例では、次を使用して`using` / `Imports`ステートメント。  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="first"></a>First  
  
### <a name="example"></a>例  
 次の例では、<xref:System.Linq.Enumerable.First%2A> メソッドを使用して、名が "Brooke" である最初の連絡先を取得します。  
  
 [!code-csharp[DP L2E Examples#FirstSimple](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#firstsimple)]
 [!code-vb[DP L2E Examples#FirstSimple](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#firstsimple)]  
  
## <a name="see-also"></a>関連項目
- [LINQ to Entities でのクエリ](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
