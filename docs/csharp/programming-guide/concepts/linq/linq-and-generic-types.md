---
title: LINQ とジェネリック型 (C#)
ms.date: 07/20/2015
helpviewer_keywords:
- LINQ [C#], generic types
- generic types [LINQ]
- generics [LINQ]
ms.assetid: 660e3799-25ca-462c-8c4a-8bce04fbb031
ms.openlocfilehash: f9bb4ec21685d21d0975529c7460944b5f0f9fc6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33327738"
---
# <a name="linq-and-generic-types-c"></a>LINQ とジェネリック型 (C#)
[!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] クエリは、[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] Version 2.0 で導入されたジェネリック型に基づいています。 クエリを記述するために、ジェネリックについて詳しく知っておく必要ありません。 ただし、次の 2 つの基本的な概念を理解しておくと役立ちます。  
  
1.  <xref:System.Collections.Generic.List%601> などのジェネリック コレクション クラスのインスタンスを作成するときに、リストに保持されるオブジェクトの型で "T" を置き換えます。 たとえば、文字列のリストは `List<string>` で表され、`Customer`オブジェクトのリストは `List<Customer>` で表されます。 ジェネリック リストは厳密に型指定されるため、要素を <xref:System.Object> として格納するコレクションと比べて多くの利点があります。 `Customer`を `List<string>` に追加しようとすると、コンパイル時にエラーが発生します。 実行時に型キャストを実行する必要がないため、ジェネリック コレクションを使用するのは簡単です。  
  
2.  <xref:System.Collections.Generic.IEnumerable%601> は、`foreach` ステートメントを使用してジェネリック コレクションのクラスを列挙できるようにするインターフェイスです。 <xref:System.Collections.ArrayList> などの非ジェネリック コレクション クラスが <xref:System.Collections.IEnumerable> をサポートするように、ジェネリック コレクション クラスは、<xref:System.Collections.Generic.IEnumerable%601> をサポートします。  
  
 ジェネリックの詳細については、「[ジェネリック](../../../../csharp/programming-guide/generics/index.md)」を参照してください。  
  
## <a name="ienumerablet-variables-in-linq-queries"></a>LINQ クエリの IEnumerable<T\> 変数  
 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] クエリ変数は、<xref:System.Collections.Generic.IEnumerable%601>、または <xref:System.Linq.IQueryable%601> などの派生型として型指定されます。 `IEnumerable<Customer>` として型指定されたクエリ変数が見つかった場合は、クエリが実行されたときに 0 個以上の `Customer` オブジェクトのシーケンスが作成されることを意味します。  
  
 [!code-csharp[csLINQGettingStarted#34](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/linq-and-generic-types_1.cs)]  
  
 詳細については、「[LINQ クエリ操作での型の関係](../../../../csharp/programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md)」を参照してください。  
  
## <a name="letting-the-compiler-handle-generic-type-declarations"></a>コンパイラによるジェネリック型の宣言の処理  
 必要に応じて、[var](../../../../csharp/language-reference/keywords/var.md) キーワードを使用することにより、ジェネリックの構文を回避することもできます。 `var` キーワードは、`from` 句で指定されたデータ ソースを調べてクエリ変数の型を推論するようにコンパイラに指示します。 次の例では、前の例と同じコンパイル済みのコードが生成されます。  
  
 [!code-csharp[csLINQGettingStarted#35](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/linq-and-generic-types_2.cs)]  
  
 `var` キーワードは、変数の型が明らかな場合、または入れ子にされたジェネリック型 (グループ クエリで生成されたものなど) を明示的に指定する必要がない場合に便利です。 一般に、`var` を使用すると、他の開発者にとってコードが読みにくくなる可能性があることを理解しておくことをお勧めします。 詳細については、「[暗黙的に型指定されるローカル変数](../../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md)」を参照してください。  
  
## <a name="see-also"></a>参照  
 [C# の LINQ の概要](../../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)  
 [ジェネリック](../../../../csharp/programming-guide/generics/index.md)
