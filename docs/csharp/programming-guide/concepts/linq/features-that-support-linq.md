---
title: "LINQ をサポートする C# の機能 | Microsoft Docs"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- LINQ [C#], features supporting LINQ
ms.assetid: 524b0078-ebfd-45a7-b390-f2ceb9d84797
caps.latest.revision: 23
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: f844e967e2abb7ea23e04a797017261e33bb4d75
ms.lasthandoff: 03/13/2017

---
# <a name="c-features-that-support-linq"></a>LINQ をサポートする C# の機能
このセクションでは、C# 3.0 で導入された新しい言語構成要素について説明します。 これらの新機能はすべてある程度まで [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] クエリで使用されていますが、[!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] だけでなく、これらの機能が役立つと思われるあらゆる状況で使用できます。  
  
## <a name="query-expressions"></a>クエリ式  
 クエリ式は、SQL や XQuery に似た宣言型構文を使用して、IEnumerable コレクションを照会します。 クエリ構文は、コンパイル時に、[!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] プロバイダーの標準クエリ演算子拡張メソッドの実装に対するメソッド呼び出しに変換されます。 アプリケーションは、`using` ディレクティブを使用して適切な名前空間を指定することにより、スコープ内の標準クエリ演算子を制御します。 次のクエリ式では、文字列の配列を受け取り、文字列の最初の文字を基に文字列をグループ化し、グループを並び替えています。  
  
```  
var query = from str in stringArray  
            group str by str[0] into stringGroup  
            orderby stringGroup.Key  
            select stringGroup;  
```  
  
 詳細については、「[LINQ クエリ式](../../../../csharp/programming-guide/linq-query-expressions/index.md)」を参照してください。  
  
## <a name="implicitly-typed-variables-var"></a>暗黙的に型指定された変数 (var)  
 変数を宣言して初期化するときに、型を明示的に指定する代わりに、次に示すように [var](../../../../csharp/language-reference/keywords/var.md) 修飾子を使用すると、コンパイラが型を推論して代入するように指示できます。  
  
```  
var number = 5;  
var name = "Virginia";  
var query = from str in stringArray  
            where str[0] == 'm'  
            select str;  
```  
  
 `var` として宣言された変数は、明示的に型を指定した変数とまったく同じように厳密に型指定されます。 `var` を使用すると匿名型を作成できますが、任意のローカル変数にも使用できます。 また、暗黙的な型指定を使用して、配列を宣言することもできます。  
  
 詳細については、「[暗黙的に型指定されたローカル変数](../../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md)」を参照してください。  
  
## <a name="object-and-collection-initializers"></a>オブジェクト初期化子とコレクション初期化子  
 オブジェクト初期化子とコレクション初期化子を使用すると、オブジェクトのコンストラクターを明示的に呼び出さなくても、オブジェクトを初期化できます。 通常、初期化子は、ソース データを新しいデータ型に投影するクエリ式で使用されます。 パブリックな `Name` プロパティと `Phone` プロパティを持つ `Customer` という名前のクラスがある場合、オブジェクト初期化子は次のコードのように使用できます。  
  
```  
Customer cust = new Customer { Name = "Mike", Phone = "555-1212" };  
```  
  
 詳細については、「[オブジェクト初期化子とコレクション初期化子](../../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md)」を参照してください。  
  
## <a name="anonymous-types"></a>匿名型  
 匿名型はコンパイラによって作成され、型名はコンパイラにしかわかりません。 匿名型を使用すると、個別に名前付き型を定義しなくても、クエリ結果内のプロパティのセットを一時的にグループ化できるため便利です。 次に示すように、匿名型は new 式とオブジェクト初期化子を使用して初期化されます。  
  
```  
select new {name = cust.Name, phone = cust.Phone};  
```  
  
 詳細については、「[匿名型](../../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)」を参照してください。  
  
## <a name="extension-methods"></a>拡張メソッド  
 拡張メソッドは型に関連付けることができる静的メソッドであるため、その型のインスタンス メソッドと同じように呼び出すことができます。 この機能を使用すると、既存の型を実際に変更しなくても、その型に新しいメソッドを実質的に "追加" できます。 標準クエリ演算子は、<xref:System.Collections.Generic.IEnumerable%601> を実装する任意の型で [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] クエリ機能を実現する拡張メソッドのセットです。  
  
 詳細については、「[拡張メソッド](../../../../csharp/programming-guide/classes-and-structs/extension-methods.md)」を参照してください。  
  
## <a name="lambda-expressions"></a>ラムダ式  
 ラムダ式は、=> 演算子を使用して関数本体からパラメーター入力を分離するインライン関数で、コンパイル時にデリゲートまたは式ツリーに変換されます。 [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] プログラミングでは、標準クエリ演算子に対する直接メソッド呼び出しを行う場合にラムダ式を使用します。  
  
 詳細については次を参照してください:  
  
-   [匿名関数](../../../../csharp/programming-guide/statements-expressions-operators/anonymous-functions.md)  
  
-   [ラムダ式](../../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)  
  
-   [式ツリー (C#)](../../../../csharp/programming-guide/concepts/expression-trees/index.md)  
  
## <a name="auto-implemented-properties"></a>自動実装プロパティ  
 自動実装プロパティによって、プロパティの宣言が簡略化されます。 次の例に示すようなプロパティを宣言すると、コンパイラによってプライベートの匿名バッキング フィールドが作成されます。このフィールドには、プロパティ getter およびプロパティ setter でしかアクセスできません。  
  
```  
public string Name {get; set;}  
```  
  
 詳細については、「[自動実装プロパティ](../../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [統合言語クエリ (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/index.md)
