---
title: データ型の変換 (C#)
ms.date: 07/20/2015
ms.assetid: 46e5682f-77a1-4302-8f93-a2b53c408808
ms.openlocfilehash: 9e8b7726b94871a17a4be50a9b24d8b73abcf79c
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2019
ms.locfileid: "69594615"
---
# <a name="converting-data-types-c"></a>データ型の変換 (C#)
変換メソッドは、入力オブジェクトの型を変更します。  
  
 LINQ クエリの変換操作は、さまざまなアプリケーションで役に立ちます。 次にいくつかの例を示します。  
  
- <xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=nameWithType> メソッドを使用すると、標準クエリ演算子の型のカスタム実装を非表示することができます。  
  
- <xref:System.Linq.Enumerable.OfType%2A?displayProperty=nameWithType> メソッドを使用すると、LINQ クエリのパラメーター化されていないコレクションを有効にすることができます。  
  
- <xref:System.Linq.Enumerable.ToArray%2A?displayProperty=nameWithType>、<xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=nameWithType>、<xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType>、および <xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=nameWithType> メソッドを使用すると、クエリが列挙されるまで延期させるのではなく、即時のクエリ実行を強制することができます。  
  
## <a name="methods"></a>メソッド  
 次の表には、データ型の変換を実行する標準クエリ演算子メソッドの一覧が示されています。  
  
 名前が "As" で始まるこの表の変換メソッドは、ソース コレクションの静的型を変更しますが、ソース コレクションを列挙しません。 名前が "To" で始まるメソッドは、ソース コレクションを列挙し、各項目を対応するコレクション型に変換します。  
  
|メソッド名|説明|C# のクエリ式の構文|詳細情報|  
|-----------------|-----------------|---------------------------------|----------------------|  
|AsEnumerable|<xref:System.Collections.Generic.IEnumerable%601> として型指定された入力を返します。|適用不可。|<xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=nameWithType>|  
|AsQueryable|(ジェネリック) <xref:System.Collections.IEnumerable> を (ジェネリック) <xref:System.Linq.IQueryable> に変換します。|適用不可。|<xref:System.Linq.Queryable.AsQueryable%2A?displayProperty=nameWithType>|  
|Cast|コレクションの要素を指定した型にキャストします。|明示的に型指定された範囲変数を使用します。 例:<br /><br /> `from string str in words`|<xref:System.Linq.Enumerable.Cast%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Cast%2A?displayProperty=nameWithType>|  
|OfType|指定した型にキャストできるかどうかに応じて値をフィルター処理します。|適用不可。|<xref:System.Linq.Enumerable.OfType%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OfType%2A?displayProperty=nameWithType>|  
|ToArray|コレクションを配列に変換します。 このメソッドはクエリの実行を強制します。|適用不可。|<xref:System.Linq.Enumerable.ToArray%2A?displayProperty=nameWithType>|  
|ToDictionary|キー セレクター関数に基づいて、<xref:System.Collections.Generic.Dictionary%602> に要素を変換します。 このメソッドはクエリの実行を強制します。|適用不可。|<xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=nameWithType>|  
|ToList|コレクションを <xref:System.Collections.Generic.List%601> に変換します。 このメソッドはクエリの実行を強制します。|適用不可。|<xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType>|  
|ToLookup|キー セレクター関数に基づいて、<xref:System.Linq.Lookup%602> (一対多の辞書) に要素を変換します。 このメソッドはクエリの実行を強制します。|適用不可。|<xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-example"></a>クエリ式の構文例  
 次のコード例では、サブタイプでのみ使用できるメンバーにアクセスする前に、明示的に型指定された範囲変数を使用して、型をそのサブタイプにキャストしています。  
  
```csharp  
class Plant  
{  
    public string Name { get; set; }  
}  
  
class CarnivorousPlant : Plant  
{  
    public string TrapType { get; set; }  
}  
  
static void Cast()  
{  
    Plant[] plants = new Plant[] {  
        new CarnivorousPlant { Name = "Venus Fly Trap", TrapType = "Snap Trap" },  
        new CarnivorousPlant { Name = "Pitcher Plant", TrapType = "Pitfall Trap" },  
        new CarnivorousPlant { Name = "Sundew", TrapType = "Flypaper Trap" },  
        new CarnivorousPlant { Name = "Waterwheel Plant", TrapType = "Snap Trap" }  
    };  
  
    var query = from CarnivorousPlant cPlant in plants  
                where cPlant.TrapType == "Snap Trap"  
                select cPlant;  
  
    foreach (Plant plant in query)  
        Console.WriteLine(plant.Name);  
  
    /* This code produces the following output:  
  
        Venus Fly Trap  
        Waterwheel Plant  
    */  
}  
```  
  
## <a name="see-also"></a>関連項目

- <xref:System.Linq>
- [標準クエリ演算子の概要 (C#)](./standard-query-operators-overview.md)
- [from 句](../../../language-reference/keywords/from-clause.md)
- [LINQ クエリ式](../../linq-query-expressions/index.md)
- [方法: LINQ を使用して ArrayList を照会する (C#)](./how-to-query-an-arraylist-with-linq.md)
