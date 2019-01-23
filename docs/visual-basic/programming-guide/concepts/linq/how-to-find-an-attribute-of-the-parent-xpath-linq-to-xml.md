---
title: '方法: 親 (XPATH-LINQ to XML) の属性を検索 (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: 9d2572fd-27d4-426c-b079-16854cb9ec7d
ms.openlocfilehash: 15752805f35b145514d25208b6de44a7ed8ade47
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54580539"
---
# <a name="how-to-find-an-attribute-of-the-parent-xpath-linq-to-xml-visual-basic"></a>方法: 親 (XPATH-LINQ to XML) の属性を検索 (Visual Basic)
このトピックでは、親要素に移動してその属性を検索する方法を示します。  
  
 XPath 式を次に示します。  
  
 `../@id`  
  
## <a name="example"></a>例  
 この例では、まず `Author` 要素を検索します。 次に、親要素の `id` 属性を検索します。  
  
 この例では、次の XML ドキュメントを使用します。[サンプル XML ファイル:書籍 (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-books-linq-to-xml.md)します。  
  
```vb  
Dim books As XDocument = XDocument.Load("Books.xml")  
Dim author As XElement = books.Root.<Book>.<Author>.FirstOrDefault()  
  
' LINQ to XML query  
Dim att1 As XAttribute = author.Parent.Attribute("id")  
  
' XPath expression  
Dim att2 As XAttribute = DirectCast(author.XPathEvaluate("../@id"),  _  
    IEnumerable).Cast(Of XAttribute)().First()  
  
If att1 Is att2 Then  
    Console.WriteLine("Results are identical")  
Else  
    Console.WriteLine("Results differ")  
End If  
Console.WriteLine(att1)  
```  
  
 この例を実行すると、次の出力が生成されます。  
  
```  
Results are identical  
id="bk101"  
```  
  
## <a name="see-also"></a>関連項目
- [LINQ to XML XPath ユーザー (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
