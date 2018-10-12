---
title: '方法: XML リテラルに式を埋め込む (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- embedded expressions [Visual Basic]
- XML literals [Visual Basic], embedded expressions
ms.assetid: 75016fad-0141-42de-8564-5051be29487e
ms.openlocfilehash: 41dc6ef8d2ec2ffd6cd1cf793911f2e09f1a1e77
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2018
ms.locfileid: "42929517"
---
# <a name="how-to-embed-expressions-in-xml-literals-visual-basic"></a>方法: XML リテラルに式を埋め込む (Visual Basic)
埋め込み式 XML ドキュメント、フラグメント、または実行時に作成されたコンテンツを含む要素を作成するには、XML リテラルを組み合わせることができます。 次の例では、組み込み式を使用して、実行時にコンテンツの要素、属性、および要素名を設定する方法を示します。  
  
 埋め込み式の構文は、 `<%=` `exp` `%>`、同じ構文であるを[!INCLUDE[vstecasp](~/includes/vstecasp-md.md)]を使用します。 詳細については、次を参照してください。 [XML での埋め込み式](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)します。  
  
 使用することも、 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] Api を作成する[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]オブジェクト。 詳細については、「<xref:System.Xml.Linq.XElement>」を参照してください。  
  
## <a name="procedures"></a>手順  
  
#### <a name="to-insert-text-as-element-content"></a>要素の内容としてテキストを挿入するには  
  
-   次の例に含まれているテキストを挿入する方法を示しています、`contactName`かっこと右の名前の要素間変数。  
  
     [!code-vb[VbXMLSamples#39](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-embed-expressions-in-xml-literals_1.vb)]  
  
     この例を実行すると、次の出力が生成されます。  
  
    ```xml  
    <contact>  
      <name>Patrick Hines</name>  
    </contact>  
    ```  
  
#### <a name="to-insert-text-as-an-attribute-value"></a>属性値としてテキストを挿入するには  
  
-   次の例に含まれているテキストを挿入する方法を示しています、`phoneType`変数の値として、`type`属性。  
  
     [!code-vb[VbXMLSamples#40](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-embed-expressions-in-xml-literals_2.vb)]  
  
     この例を実行すると、次の出力が生成されます。  
  
    ```xml  
    <contact>  
      <phone type="home">206-555-0144</phone>  
    </contact>  
    ```  
  
#### <a name="to-insert-text-for-an-element-name"></a>要素名のテキストを挿入するには  
  
-   次の例に含まれているテキストを挿入する方法を示しています、`elementName`変数としての要素の名前。  
  
     この手法を使用して要素を作成するときに、それらを閉じる必要があります、 \</> タグです。  
  
     [!code-vb[VbXMLSamples#41](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-embed-expressions-in-xml-literals_3.vb)]  
  
     この例を実行すると、次の出力が生成されます。  
  
    ```xml  
    <contact>  
      <name>Patrick Hines</name>  
    </contact>  
    ```  
  
## <a name="see-also"></a>関連項目  
 [方法: XML リテラルを作成する](../../../../visual-basic/programming-guide/language-features/xml/how-to-create-xml-literals.md)  
 [XML での埋め込み式](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)  
 [Visual Basic での XML の作成](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)
