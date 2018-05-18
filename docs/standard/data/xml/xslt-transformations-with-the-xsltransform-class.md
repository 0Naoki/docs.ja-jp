---
title: XslTransform クラスを使用した XSLT 変換
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 500335af-f9b5-413b-968a-e6d9a824478c
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ece159b35cfbc83e05432b93ce7df06a5ca9fcac
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="xslt-transformations-with-the-xsltransform-class"></a>XslTransform クラスを使用した XSLT 変換
> [!NOTE]
>  <xref:System.Xml.Xsl.XslTransform> では、[!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)] クラスが廃止されています。 <xref:System.Xml.Xsl.XslCompiledTransform> クラスを使用して XSLT (Extensible Stylesheet Language for Transformations) 変換を実行できます。 詳しくは、「[XslCompiledTransform クラスの使用](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md)」および「[XslTransform クラスからの移行](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md)」をご覧ください。  
  
 XSLT の目的は、たとえば、XML を Web サイトで使われる HTML に変換したり、XML ドキュメントをアプリケーションが必要とするフィールドのみが含まれたドキュメントに変換するなど、ソース XML ドキュメントの内容を形式や構造の異なる別のドキュメントに変換することです。 この変換処理の仕様は、www.w3.org/TR/xslt にある W3C (World Wide Web Consortium) 勧告『XSLT Version 1.0』で規定されています。 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] では、<xref:System.Xml.Xsl.XslTransform> 名前空間にある <xref:System.Xml.Xsl> クラスが、この仕様の機能を実装する XSLT プロセッサです。 W3C 勧告『XSLT Version 1.0』から実装された機能の他に、「[XslTransform からの出力](../../../../docs/standard/data/xml/outputs-from-an-xsltransform.md)」に記載されている機能がいくつかあります。 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] の変換アーキテクチャを次の図に示します。  
  
## <a name="overview"></a>概要  
 ![XSLT 変換アーキテクチャ](../../../../docs/standard/data/xml/media/xslttransformationswithxsltransformclass.gif "xsltTransformationsWithXslTransformClass")  
変換アーキテクチャ  
  
 XSLT 勧告では、XPath (XML Path Language) を使って XML ドキュメントの一部を選択します。XPath とは、ドキュメント ツリーのノード間を移動するのに使われるクエリ言語です。 図に示すように、XPath の [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] の実装は、<xref:System.Xml.XmlDocument>、<xref:System.Xml.XmlDataDocument>、<xref:System.Xml.XPath.XPathDocument> など、複数のクラスに格納されている XML の一部を選択するのに使用されます。 <xref:System.Xml.XPath.XPathDocument> は最適化された XSLT データ ストアであり、これを <xref:System.Xml.Xsl.XslTransform> と共に使用することで、パフォーマンスの高い XSLT 変換を実行できます。  
  
 <xref:System.Xml.Xsl.XslTransform> と XPath を使用するときによく使われるクラスと、それぞれの機能を次の表に示します。  
  
|クラスまたはインターフェイス|関数|  
|------------------------|--------------|  
|<xref:System.Xml.XPath.XPathNavigator>|ストア内で移動するためのカーソル スタイルのモデルを提供し、XPath クエリをサポートする API です。 元になるストアを編集する機能は提供しません。 編集には <xref:System.Xml.XmlDocument> クラスを使用します。|  
|<xref:System.Xml.XPath.IXPathNavigable>|`CreateNavigator` に <xref:System.Xml.XPath.XPathNavigator> メソッドを提供するストア用のインターフェイスです。|  
|<xref:System.Xml.XmlDocument>|対象のドキュメントの編集を有効にします。 このクラスは <xref:System.Xml.XPath.IXPathNavigable> を実装しているため、後で XSLT 変換が必要になるドキュメントの編集が可能です。 詳細については、「[XslTransform への XmlDocument の入力](../../../../docs/standard/data/xml/xmldocument-input-to-xsltransform.md)」を参照してください。|  
|<xref:System.Xml.XmlDataDocument>|これは <xref:System.Xml.XmlDocument> の派生クラスです。 このクラスは、<xref:System.Data.DataSet> を使用してリレーショナル環境と XML 環境との橋渡しをし、<xref:System.Data.DataSet> で指定された対応付けに従って XML ドキュメント内の構造化データのストレージを最適化します。 このクラスは <xref:System.Xml.XPath.IXPathNavigable> を実装しているため、データベースから取得したリレーショナル データに対して XSLT 変換を実行できます。 詳細については、「[XML とリレーショナル データおよび ADO.NET との統合](../../../../docs/standard/data/xml/xml-integration-with-relational-data-and-adonet.md)」を参照してください。|  
|<xref:System.Xml.XPath.XPathDocument>|このクラスは、<xref:System.Xml.Xsl.XslTransform> の処理および XPath クエリ用に最適化されており、パフォーマンスの高い読み取り専用キャッシュを提供します。 このクラスは <xref:System.Xml.XPath.IXPathNavigable> を実装しており、XSLT 変換に使用するストアとして適しています。|  
|<xref:System.Xml.XPath.XPathNodeIterator>|XPath ノード セット内を移動できるようにします。 <xref:System.Xml.XPath.XPathNavigator> のすべての XPath 選択メソッドは <xref:System.Xml.XPath.XPathNodeIterator> を返します。 同じストアに対して、選択されているノード セットを表す複数の <xref:System.Xml.XPath.XPathNodeIterator> オブジェクトを作成できます。|  
  
## <a name="msxml-xslt-extensions"></a>MSXML XSLT 拡張機能  
 `msxsl:script` クラスがサポートしている Microsoft XML コア サービス (MSXML) XSLT 拡張機能は、`msxsl:node-set` 関数と <xref:System.Xml.Xsl.XslTransform> 関数のみです。  
  
## <a name="example"></a>例  
 XSL スタイル シートを読み込み、mydata.xml というファイルを <xref:System.Xml.XPath.XPathDocument> に読み込み、myStyleSheet.xsl という架空のファイルに格納されているデータの変換を実行し、書式設定された出力をコンソールに送信するコード サンプルを次に示します。  
  
```vb  
Imports System  
Imports System.IO  
Imports System.Xml  
Imports System.Xml.XPath  
Imports System.Xml.Xsl  
  
Public Class Sample  
    Private filename As [String] = "mydata.xml"  
    Private stylesheet As [String] = "myStyleSheet.xsl"  
  
    Public Shared Sub Main()  
        Dim xslt As New XslTransform()  
        xslt.Load(stylesheet)  
        Dim xpathdocument As New XPathDocument(filename)  
        Dim writer As New XmlTextWriter(Console.Out)  
        writer.Formatting = Formatting.Indented  
  
        xslt.Transform(xpathdocument, Nothing, writer, Nothing)  
    End Sub 'Main  
End Class 'Sample  
```  
  
```csharp  
using System;  
using System.IO;  
using System.Xml;  
using System.Xml.XPath;  
using System.Xml.Xsl;  
  
public class Sample   
{  
    private const String filename = "mydata.xml";  
    private const String stylesheet = "myStyleSheet.xsl";  
  
    public static void Main()   
    {  
    XslTransform xslt = new XslTransform();  
    xslt.Load(stylesheet);  
    XPathDocument xpathdocument = new  
    XPathDocument(filename);  
    XmlTextWriter writer = new XmlTextWriter(Console.Out);  
    writer.Formatting=Formatting.Indented;  
  
    xslt.Transform(xpathdocument, null, writer, null);      
    }  
}  
```  
  
## <a name="see-also"></a>参照  
 <xref:System.Xml.Xsl.XslTransform>  
 [XslTransform クラスによる XSLT プロセッサの実装](../../../../docs/standard/data/xml/xsltransform-class-implements-the-xslt-processor.md)  
 [XslTransform クラスの随意動作の実装](../../../../docs/standard/data/xml/implementation-of-discretionary-behaviors-in-the-xsltransform-class.md)  
 [変換における XPathNavigator](../../../../docs/standard/data/xml/xpathnavigator-in-transformations.md)  
 [変換における XPathNodeIterator](../../../../docs/standard/data/xml/xpathnodeiterator-in-transformations.md)  
 [XslTransform への XPathDocument の入力](../../../../docs/standard/data/xml/xpathdocument-input-to-xsltransform.md)  
 [XslTransform への XmlDataDocument の入力](../../../../docs/standard/data/xml/xmldatadocument-input-to-xsltransform.md)  
 [XslTransform への XmlDocument の入力](../../../../docs/standard/data/xml/xmldocument-input-to-xsltransform.md)
