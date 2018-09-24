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
ms.openlocfilehash: 67062ab87182bcb42793cb166323020178ac1688
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "45746420"
---
# <a name="xslt-transformations-with-the-xsltransform-class"></a><span data-ttu-id="109c3-102">XslTransform クラスを使用した XSLT 変換</span><span class="sxs-lookup"><span data-stu-id="109c3-102">XSLT Transformations with the XslTransform Class</span></span>

> [!NOTE]
> <span data-ttu-id="109c3-103"><xref:System.Xml.Xsl.XslTransform> では、[!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)] クラスが廃止されています。</span><span class="sxs-lookup"><span data-stu-id="109c3-103">The <xref:System.Xml.Xsl.XslTransform> class is obsolete in the [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)].</span></span> <span data-ttu-id="109c3-104"><xref:System.Xml.Xsl.XslCompiledTransform> クラスを使用して XSLT (Extensible Stylesheet Language for Transformations) 変換を実行できます。</span><span class="sxs-lookup"><span data-stu-id="109c3-104">You can perform Extensible Stylesheet Language for Transformations (XSLT) transformations using the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span> <span data-ttu-id="109c3-105">詳しくは、「[XslCompiledTransform クラスの使用](using-the-xslcompiledtransform-class.md)」および「[XslTransform クラスからの移行](migrating-from-the-xsltransform-class.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="109c3-105">See [Using the XslCompiledTransform Class](using-the-xslcompiledtransform-class.md) and [Migrating From the XslTransform Class](migrating-from-the-xsltransform-class.md) for more information.</span></span>

<span data-ttu-id="109c3-106">XSLT の目的は、たとえば、XML を Web サイトで使われる HTML に変換したり、XML ドキュメントをアプリケーションが必要とするフィールドのみが含まれたドキュメントに変換するなど、ソース XML ドキュメントの内容を形式や構造の異なる別のドキュメントに変換することです。</span><span class="sxs-lookup"><span data-stu-id="109c3-106">The goal of the XSLT is to transform the content of a source XML document into another document that is different in format or structure (for example, to transform XML into HTML for use on a Web site or to transform it into a document that contains only the fields required by an application).</span></span> <span data-ttu-id="109c3-107">この変換処理の仕様は、W3C (World Wide Web Consortium) [勧告 XSLT バージョン 1.0](https://www.w3.org/TR/1999/REC-xslt-19991116) で規定されています。</span><span class="sxs-lookup"><span data-stu-id="109c3-107">This transformation process is specified by the World Wide Web Consortium (W3C)[XSLT version 1.0 recommendation](https://www.w3.org/TR/1999/REC-xslt-19991116).</span></span> <span data-ttu-id="109c3-108">[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] では、<xref:System.Xml.Xsl.XslTransform> 名前空間にある <xref:System.Xml.Xsl> クラスが、この仕様の機能を実装する XSLT プロセッサです。</span><span class="sxs-lookup"><span data-stu-id="109c3-108">In the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], the <xref:System.Xml.Xsl.XslTransform> class, found in the <xref:System.Xml.Xsl> namespace, is the XSLT processor that implements the functionality of this specification.</span></span> <span data-ttu-id="109c3-109">W3C 勧告『XSLT Version 1.0』から実装された機能の他に、「[XslTransform からの出力](outputs-from-an-xsltransform.md)」に記載されている機能がいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="109c3-109">There are a small number of features that have not been implemented from the W3C XSLT 1.0 recommendation, listed in [Outputs from an XslTransform](outputs-from-an-xsltransform.md).</span></span> <span data-ttu-id="109c3-110">[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] の変換アーキテクチャを次の図に示します。</span><span class="sxs-lookup"><span data-stu-id="109c3-110">The following figure shows the transformation architecture of the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)].</span></span>

## <a name="overview"></a><span data-ttu-id="109c3-111">概要</span><span class="sxs-lookup"><span data-stu-id="109c3-111">Overview</span></span>

<span data-ttu-id="109c3-112">![XSLT 変換アーキテクチャ](media/xslttransformationswithxsltransformclass.gif "xsltTransformationsWithXslTransformClass")</span><span class="sxs-lookup"><span data-stu-id="109c3-112">![XSLT Transformation Architecture](media/xslttransformationswithxsltransformclass.gif "xsltTransformationsWithXslTransformClass")</span></span>  
<span data-ttu-id="109c3-113">変換アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="109c3-113">Transformation Architecture</span></span>

<span data-ttu-id="109c3-114">XSLT 勧告では、XPath (XML Path Language) を使って XML ドキュメントの一部を選択します。XPath とは、ドキュメント ツリーのノード間を移動するのに使われるクエリ言語です。</span><span class="sxs-lookup"><span data-stu-id="109c3-114">The XSLT recommendation uses XML Path Language (XPath) to select parts of an XML document, where XPath is a query language used to navigate nodes of a document tree.</span></span> <span data-ttu-id="109c3-115">図に示すように、XPath の [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] の実装は、<xref:System.Xml.XmlDocument>、<xref:System.Xml.XmlDataDocument>、<xref:System.Xml.XPath.XPathDocument> など、複数のクラスに格納されている XML の一部を選択するのに使用されます。</span><span class="sxs-lookup"><span data-stu-id="109c3-115">As shown in the diagram, the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] implementation of XPath is used to select parts of XML stored in several classes, such as an <xref:System.Xml.XmlDocument>, an <xref:System.Xml.XmlDataDocument>, and an <xref:System.Xml.XPath.XPathDocument>.</span></span> <span data-ttu-id="109c3-116"><xref:System.Xml.XPath.XPathDocument> は最適化された XSLT データ ストアであり、これを <xref:System.Xml.Xsl.XslTransform> と共に使用することで、パフォーマンスの高い XSLT 変換を実行できます。</span><span class="sxs-lookup"><span data-stu-id="109c3-116">An <xref:System.Xml.XPath.XPathDocument> is an optimized XSLT data store, and when used with <xref:System.Xml.Xsl.XslTransform>, it provides XSLT transformations with good performance.</span></span>

<span data-ttu-id="109c3-117"><xref:System.Xml.Xsl.XslTransform> と XPath を使用するときによく使われるクラスと、それぞれの機能を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="109c3-117">The following table list commonly uses classes when working with <xref:System.Xml.Xsl.XslTransform> and XPath and their function.</span></span>

|<span data-ttu-id="109c3-118">クラスまたはインターフェイス</span><span class="sxs-lookup"><span data-stu-id="109c3-118">Class or Interface</span></span>|<span data-ttu-id="109c3-119">関数</span><span class="sxs-lookup"><span data-stu-id="109c3-119">Function</span></span>|
|------------------------|--------------|
|<xref:System.Xml.XPath.XPathNavigator>|<span data-ttu-id="109c3-120">ストア内で移動するためのカーソル スタイルのモデルを提供し、XPath クエリをサポートする API です。</span><span class="sxs-lookup"><span data-stu-id="109c3-120">It is an API that provides a cursor style model for navigating over a store, along with XPath query support.</span></span> <span data-ttu-id="109c3-121">元になるストアを編集する機能は提供しません。</span><span class="sxs-lookup"><span data-stu-id="109c3-121">It does not provide editing of the underlying store.</span></span> <span data-ttu-id="109c3-122">編集には <xref:System.Xml.XmlDocument> クラスを使用します。</span><span class="sxs-lookup"><span data-stu-id="109c3-122">For editing, use the <xref:System.Xml.XmlDocument> class.</span></span>|
|<xref:System.Xml.XPath.IXPathNavigable>|<span data-ttu-id="109c3-123">`CreateNavigator` に <xref:System.Xml.XPath.XPathNavigator> メソッドを提供するストア用のインターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="109c3-123">It is an interface that provides a `CreateNavigator` method to an <xref:System.Xml.XPath.XPathNavigator> for the store.</span></span>|
|<xref:System.Xml.XmlDocument>|<span data-ttu-id="109c3-124">対象のドキュメントの編集を有効にします。</span><span class="sxs-lookup"><span data-stu-id="109c3-124">It enables editing of this document.</span></span> <span data-ttu-id="109c3-125">このクラスは <xref:System.Xml.XPath.IXPathNavigable> を実装しているため、後で XSLT 変換が必要になるドキュメントの編集が可能です。</span><span class="sxs-lookup"><span data-stu-id="109c3-125">It implements <xref:System.Xml.XPath.IXPathNavigable>, allowing document-editing scenarios where XSLT transformations are subsequently required.</span></span> <span data-ttu-id="109c3-126">詳細については、「[XslTransform への XmlDocument の入力](xmldocument-input-to-xsltransform.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="109c3-126">For more information, see [XmlDocument Input to XslTransform](xmldocument-input-to-xsltransform.md).</span></span>|
|<xref:System.Xml.XmlDataDocument>|<span data-ttu-id="109c3-127">これは <xref:System.Xml.XmlDocument> の派生クラスです。</span><span class="sxs-lookup"><span data-stu-id="109c3-127">It is derived from the <xref:System.Xml.XmlDocument>.</span></span> <span data-ttu-id="109c3-128">このクラスは、<xref:System.Data.DataSet> を使用してリレーショナル環境と XML 環境との橋渡しをし、<xref:System.Data.DataSet> で指定された対応付けに従って XML ドキュメント内の構造化データのストレージを最適化します。</span><span class="sxs-lookup"><span data-stu-id="109c3-128">It bridges the relational and XML worlds by using a <xref:System.Data.DataSet> to optimize storage of structured data within the XML document according to specified mappings on the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="109c3-129">このクラスは <xref:System.Xml.XPath.IXPathNavigable> を実装しているため、データベースから取得したリレーショナル データに対して XSLT 変換を実行できます。</span><span class="sxs-lookup"><span data-stu-id="109c3-129">It implements <xref:System.Xml.XPath.IXPathNavigable>, allowing scenarios where XSLT transformations can be performed over relational data retrieved from a database.</span></span> <span data-ttu-id="109c3-130">詳細については、「[XML とリレーショナル データおよび ADO.NET との統合](xml-integration-with-relational-data-and-adonet.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="109c3-130">For more information, see [XML Integration with Relational Data and ADO.NET](xml-integration-with-relational-data-and-adonet.md).</span></span>|
|<xref:System.Xml.XPath.XPathDocument>|<span data-ttu-id="109c3-131">このクラスは、<xref:System.Xml.Xsl.XslTransform> の処理および XPath クエリ用に最適化されており、パフォーマンスの高い読み取り専用キャッシュを提供します。</span><span class="sxs-lookup"><span data-stu-id="109c3-131">This class is optimized for <xref:System.Xml.Xsl.XslTransform> processing and XPath queries, and it provides a read-only high performance cache.</span></span> <span data-ttu-id="109c3-132">このクラスは <xref:System.Xml.XPath.IXPathNavigable> を実装しており、XSLT 変換に使用するストアとして適しています。</span><span class="sxs-lookup"><span data-stu-id="109c3-132">It implements <xref:System.Xml.XPath.IXPathNavigable> and is the preferred store to use for XSLT transformations.</span></span>|
|<xref:System.Xml.XPath.XPathNodeIterator>|<span data-ttu-id="109c3-133">XPath ノード セット内を移動できるようにします。</span><span class="sxs-lookup"><span data-stu-id="109c3-133">It provides navigation over XPath node sets.</span></span> <span data-ttu-id="109c3-134"><xref:System.Xml.XPath.XPathNavigator> のすべての XPath 選択メソッドは <xref:System.Xml.XPath.XPathNodeIterator> を返します。</span><span class="sxs-lookup"><span data-stu-id="109c3-134">All XPath selection methods on the <xref:System.Xml.XPath.XPathNavigator> return an <xref:System.Xml.XPath.XPathNodeIterator>.</span></span> <span data-ttu-id="109c3-135">同じストアに対して、選択されているノード セットを表す複数の <xref:System.Xml.XPath.XPathNodeIterator> オブジェクトを作成できます。</span><span class="sxs-lookup"><span data-stu-id="109c3-135">Multiple <xref:System.Xml.XPath.XPathNodeIterator> objects can be created over the same store, each representing a selected set of nodes.</span></span>|

## <a name="msxml-xslt-extensions"></a><span data-ttu-id="109c3-136">MSXML XSLT 拡張機能</span><span class="sxs-lookup"><span data-stu-id="109c3-136">MSXML XSLT Extensions</span></span>

<span data-ttu-id="109c3-137">`msxsl:script` クラスがサポートしている Microsoft XML コア サービス (MSXML) XSLT 拡張機能は、`msxsl:node-set` 関数と <xref:System.Xml.Xsl.XslTransform> 関数のみです。</span><span class="sxs-lookup"><span data-stu-id="109c3-137">The `msxsl:script` and `msxsl:node-set` functions are the only Microsoft XML Core Services (MSXML) XSLT extensions supported by the <xref:System.Xml.Xsl.XslTransform> class.</span></span>

## <a name="example"></a><span data-ttu-id="109c3-138">例</span><span class="sxs-lookup"><span data-stu-id="109c3-138">Example</span></span>

<span data-ttu-id="109c3-139">XSL スタイル シートを読み込み、mydata.xml というファイルを <xref:System.Xml.XPath.XPathDocument> に読み込み、myStyleSheet.xsl という架空のファイルに格納されているデータの変換を実行し、書式設定された出力をコンソールに送信するコード サンプルを次に示します。</span><span class="sxs-lookup"><span data-stu-id="109c3-139">The following code example loads an XSLT style sheet, reads a file called mydata.xml into an <xref:System.Xml.XPath.XPathDocument>, and performs a transformation on the data on a fictitious file called myStyleSheet.xsl, sending the formatted output to the console.</span></span>

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
        XPathDocument xpathdocument = new XPathDocument(filename);
        XmlTextWriter writer = new XmlTextWriter(Console.Out);
        writer.Formatting = Formatting.Indented;

        xslt.Transform(xpathdocument, null, writer, null);
    }
}
```

## <a name="see-also"></a><span data-ttu-id="109c3-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="109c3-140">See also</span></span>

- <xref:System.Xml.Xsl.XslTransform>  
- [<span data-ttu-id="109c3-141">XslTransform クラスによる XSLT プロセッサの実装</span><span class="sxs-lookup"><span data-stu-id="109c3-141">XslTransform Class Implements the XSLT Processor</span></span>](xsltransform-class-implements-the-xslt-processor.md)  
- [<span data-ttu-id="109c3-142">XslTransform クラスの随意動作の実装</span><span class="sxs-lookup"><span data-stu-id="109c3-142">Implementation of Discretionary Behaviors in the XslTransform Class</span></span>](implementation-of-discretionary-behaviors-in-the-xsltransform-class.md)  
- [<span data-ttu-id="109c3-143">変換における XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="109c3-143">XPathNavigator in Transformations</span></span>](xpathnavigator-in-transformations.md)  
- [<span data-ttu-id="109c3-144">変換における XPathNodeIterator</span><span class="sxs-lookup"><span data-stu-id="109c3-144">XPathNodeIterator in Transformations</span></span>](xpathnodeiterator-in-transformations.md)  
- [<span data-ttu-id="109c3-145">XslTransform への XPathDocument の入力</span><span class="sxs-lookup"><span data-stu-id="109c3-145">XPathDocument Input to XslTransform</span></span>](xpathdocument-input-to-xsltransform.md)  
- [<span data-ttu-id="109c3-146">XslTransform への XmlDataDocument の入力</span><span class="sxs-lookup"><span data-stu-id="109c3-146">XmlDataDocument Input to XslTransform</span></span>](xmldatadocument-input-to-xsltransform.md)  
- [<span data-ttu-id="109c3-147">XslTransform への XmlDocument の入力</span><span class="sxs-lookup"><span data-stu-id="109c3-147">XmlDocument Input to XslTransform</span></span>](xmldocument-input-to-xsltransform.md)  
