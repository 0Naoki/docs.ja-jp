---
title: "方法: 空のクエリ結果セットをデバッグする (C#)"
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
ms.assetid: b569f0dc-425e-45a6-acbf-770fb761c981
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 78c6d612e11f50bedf8f1c2e9826775494faa465
ms.contentlocale: ja-jp
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-debug-empty-query-results-sets-c"></a>方法: 空のクエリ結果セットをデバッグする (C#)
XML ツリーのクエリにおける最も一般的な問題の 1 つは、XML ツリーに既定の名前空間がある場合に、XML が名前空間に含まれていないものとして開発者がクエリを記述してしまうことです。  
  
 このトピックの最初に示す一連の例では、既定の名前空間内の XML が読み込まれ、クエリが不適切に実行される典型的な例を示しています。  
  
 2 番目に示す一連の例では、名前空間内の XML に対してクエリを実行できるようにするために必要な修正を示しています。  
  
 詳細については、「[XML 名前空間の使用 (C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md)」を参照してください。  
  
## <a name="example"></a>例  
 この例では、名前空間内にある XML の作成、および空の結果セットを返すクエリを示します。  
  
```csharp  
XElement root = XElement.Parse(  
@"<Root xmlns='http://www.adventure-works.com'>  
    <Child>1</Child>  
    <Child>2</Child>  
    <Child>3</Child>  
    <AnotherChild>4</AnotherChild>  
    <AnotherChild>5</AnotherChild>  
    <AnotherChild>6</AnotherChild>  
</Root>");  
IEnumerable<XElement> c1 =  
    from el in root.Elements("Child")  
    select el;  
Console.WriteLine("Result set follows:");  
foreach (XElement el in c1)  
    Console.WriteLine((int)el);  
Console.WriteLine("End of result set");  
```  
  
 この例を実行すると、次の結果が得られます。  
  
```  
Result set follows:  
End of result set  
```  
  
## <a name="example"></a>例  
 この例では、名前空間内にある XML の作成と、適切に記述されたクエリを示します。  
  
 解決方法は、<xref:System.Xml.Linq.XNamespace> オブジェクトを宣言して初期化し、そのオブジェクトを <xref:System.Xml.Linq.XName> オブジェクトの指定時に使用することです。 この場合、<xref:System.Xml.Linq.XElement.Elements%2A> メソッドの引数は <xref:System.Xml.Linq.XName> オブジェクトです。  
  
```csharp  
XElement root = XElement.Parse(  
@"<Root xmlns='http://www.adventure-works.com'>  
    <Child>1</Child>  
    <Child>2</Child>  
    <Child>3</Child>  
    <AnotherChild>4</AnotherChild>  
    <AnotherChild>5</AnotherChild>  
    <AnotherChild>6</AnotherChild>  
</Root>");  
XNamespace aw = "http://www.adventure-works.com";  
IEnumerable<XElement> c1 =  
    from el in root.Elements(aw + "Child")  
    select el;  
Console.WriteLine("Result set follows:");  
foreach (XElement el in c1)  
    Console.WriteLine((int)el);  
Console.WriteLine("End of result set");  
```  
  
 この例を実行すると、次の結果が得られます。  
  
```  
Result set follows:  
1  
2  
3  
End of result set  
```  
  
## <a name="see-also"></a>関連項目  
 [基本的なクエリ (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)

