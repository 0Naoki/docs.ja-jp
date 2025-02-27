---
title: セット操作 (C#)
ms.date: 07/20/2015
ms.assetid: 7c589367-ef8f-4161-9050-642c47e6bf63
ms.openlocfilehash: cea0c0ba4dd6c7f874f69e3ec4a179248397b67d
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2019
ms.locfileid: "69591119"
---
# <a name="set-operations-c"></a>セット操作 (C#)
LINQ のセット操作は、同一または別個のコレクション (またはセット) に等しい要素があるかどうかに基づいて、結果を生成するクエリ操作です。  
  
 次のセクションでは、セット操作を実行する標準クエリ演算子のメソッドの一覧を示します。  
  
## <a name="methods"></a>メソッド  
  
|メソッド名|説明|C# のクエリ式の構文|詳細情報|  
|-----------------|-----------------|---------------------------------|----------------------|  
|重複の除外|コレクションから重複する値を削除します。|適用不可。|<xref:System.Linq.Enumerable.Distinct%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Distinct%2A?displayProperty=nameWithType>|  
|除く|差集合 (一方のコレクションにだけ存在し、もう一方のコレクションには出現しない要素) を返します。|適用不可。|<xref:System.Linq.Enumerable.Except%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Except%2A?displayProperty=nameWithType>|  
|交差|積集合 (2 つのコレクションのそれぞれに出現する要素) を返します。|適用不可。|<xref:System.Linq.Enumerable.Intersect%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Intersect%2A?displayProperty=nameWithType>|  
|和集合|和集合 (2 つのコレクションのどちらかに出現する一意の要素) を返します。|適用不可。|<xref:System.Linq.Enumerable.Union%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Union%2A?displayProperty=nameWithType>|  
  
## <a name="comparison-of-set-operations"></a>セット操作の比較  
  
### <a name="distinct"></a>重複の除外  
 次の図は、文字のシーケンスに対する <xref:System.Linq.Enumerable.Distinct%2A?displayProperty=nameWithType> メソッドの動作を示しています。 返されたシーケンスには、入力シーケンスからの一意の要素が格納されています。  
  
 ![Distinct&#40;&#41; の動作を示すグラフィック。](./media/set-operations/distinct-method-behavior.png)  
  
### <a name="except"></a>除く  
 <xref:System.Linq.Enumerable.Except%2A?displayProperty=nameWithType> の動作を次の図に示します。 返されたシーケンスには、1 つ目の入力シーケンスのうち、2 つ目の入力シーケンスには存在しない要素が格納されています。  
  
 ![除く動作を示すグラフィック&#40;&#41;.](./media/set-operations/except-behavior-graphic.png "除く動作を示します。")  
  
### <a name="intersect"></a>交差  
 <xref:System.Linq.Enumerable.Intersect%2A?displayProperty=nameWithType> の動作を次の図に示します。 返されたシーケンスには、両方の入力シーケンスに共通する要素が格納されています。  
  
 ![2 つのシーケンスの交差部分を示すグラフィック。](./media/set-operations/intersection-two-sequences.png)  
 
### <a name="union"></a>和集合  
 次の図は、2 つの文字シーケンスに対する和集合演算を示しています。 返されたシーケンスには、両方の入力シーケンスからの一意の要素が格納されています。  
  
 ![2 つのシーケンスの結合を示すグラフィック。](./media/set-operations/union-operation-two-sequences.png)  
## <a name="see-also"></a>関連項目

- <xref:System.Linq>
- [標準クエリ演算子の概要 (C#)](./standard-query-operators-overview.md)
- [方法: 文字列コレクションを結合および比較する (LINQ) (C#)](./how-to-combine-and-compare-string-collections-linq.md)
- [方法: 2 つのリストの差集合を見つける (LINQ) (C#)](./how-to-find-the-set-difference-between-two-lists-linq.md)
