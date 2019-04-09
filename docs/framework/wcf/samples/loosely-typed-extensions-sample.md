---
title: 弱く型指定された拡張のサンプル
ms.date: 03/30/2017
ms.assetid: 56ce265b-8163-4b85-98e7-7692a12c4357
ms.openlocfilehash: f22d5b2c1c7680b750d8bd26da10588e0ca9f585
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59086794"
---
# <a name="loosely-typed-extensions-sample"></a><span data-ttu-id="198fa-102">弱く型指定された拡張のサンプル</span><span class="sxs-lookup"><span data-stu-id="198fa-102">Loosely-Typed Extensions Sample</span></span>
<span data-ttu-id="198fa-103">配信オブジェクト モデルでは、拡張データをさまざまな方法で処理できます。拡張データとは、配信フィードの XML 表現に含まれているが、<xref:System.ServiceModel.Syndication.SyndicationFeed> や <xref:System.ServiceModel.Syndication.SyndicationItem> などのクラスによって明示的に公開されない情報のことです。</span><span class="sxs-lookup"><span data-stu-id="198fa-103">The Syndication object model provides rich support for working with extension data—information that is present in a syndication feed's XML representation but not explicitly exposed by classes such as <xref:System.ServiceModel.Syndication.SyndicationFeed> and <xref:System.ServiceModel.Syndication.SyndicationItem>.</span></span> <span data-ttu-id="198fa-104">このサンプルでは、拡張データを処理する基本的な方法を示します。</span><span class="sxs-lookup"><span data-stu-id="198fa-104">This sample illustrates the basic techniques for working with extension data.</span></span>  
  
 <span data-ttu-id="198fa-105">このサンプルでは、例を示す目的で <xref:System.ServiceModel.Syndication.SyndicationFeed> クラスを使用します。</span><span class="sxs-lookup"><span data-stu-id="198fa-105">The sample uses the <xref:System.ServiceModel.Syndication.SyndicationFeed> class for the purposes of the example.</span></span> <span data-ttu-id="198fa-106">ただし、このサンプルで示すパターンは、拡張データをサポートするすべての配信クラスで使用できます。</span><span class="sxs-lookup"><span data-stu-id="198fa-106">However, the patterns demonstrated in this sample can be used with all of the Syndication classes that support extension data:</span></span>  
  
 <xref:System.ServiceModel.Syndication.SyndicationFeed>  
  
 <xref:System.ServiceModel.Syndication.SyndicationItem>  
  
 <xref:System.ServiceModel.Syndication.SyndicationCategory>  
  
 <xref:System.ServiceModel.Syndication.SyndicationPerson>  
  
 <xref:System.ServiceModel.Syndication.SyndicationLink>  
  
## <a name="sample-xml"></a><span data-ttu-id="198fa-107">サンプル XML</span><span class="sxs-lookup"><span data-stu-id="198fa-107">Sample XML</span></span>  
 <span data-ttu-id="198fa-108">このサンプルで使用される XML ドキュメントは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="198fa-108">For reference, the following XML document is used in this sample.</span></span>  
  
```xml  
<?xml version="1.0" encoding="IBM437"?>  
<feed myAttribute="someValue" xmlns="http://www.w3.org/2005/Atom">  
  <title type="text"></title>  
  <id>uuid:8f60c7b3-a3c0-4de7-a642-2165d77ce3c1;id=1</id>  
  <updated>2007-09-07T22:15:34Z</updated>  
  <simpleString xmlns="">hello, world!</simpleString>  
  <simpleString xmlns="">another simple string</simpleString>  
  <DataContractExtension xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns="http://schemas.d  
atacontract.org/2004/07/Microsoft.Syndication.Samples">  
    <Key>X</Key>  
    <Value>4</Value>  
  </DataContractExtension>  
  <XmlSerializerExtension xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://ww  
w.w3.org/2001/XMLSchema" xmlns="">  
    <Key>Y</Key>  
    <Value>8</Value>  
  </XmlSerializerExtension>  
  <xElementExtension xmlns="">  
    <Key attr1="someValue">Z</Key>  
    <Value attr1="someValue">15</Value>  
  </xElementExtension>  
</feed>  
```  
  
 <span data-ttu-id="198fa-109">このドキュメントには、次の拡張データが含まれています。</span><span class="sxs-lookup"><span data-stu-id="198fa-109">This document contains the following pieces of extension data:</span></span>  
  
-   <span data-ttu-id="198fa-110">`myAttribute` 要素の `<feed>` 属性。</span><span class="sxs-lookup"><span data-stu-id="198fa-110">The `myAttribute` attribute of the `<feed>` element.</span></span>  
  
-   `<simpleString>` <span data-ttu-id="198fa-111">要素。</span><span class="sxs-lookup"><span data-stu-id="198fa-111">element.</span></span>  
  
-   `<DataContractExtension>` <span data-ttu-id="198fa-112">要素。</span><span class="sxs-lookup"><span data-stu-id="198fa-112">element.</span></span>  
  
-   `<XmlSerializerExtension>` <span data-ttu-id="198fa-113">要素。</span><span class="sxs-lookup"><span data-stu-id="198fa-113">element.</span></span>  
  
-   `<xElementExtension>` <span data-ttu-id="198fa-114">要素。</span><span class="sxs-lookup"><span data-stu-id="198fa-114">element.</span></span>  
  
## <a name="writing-extension-data"></a><span data-ttu-id="198fa-115">拡張データの書き込み</span><span class="sxs-lookup"><span data-stu-id="198fa-115">Writing Extension Data</span></span>  
 <span data-ttu-id="198fa-116">属性の拡張は、次のサンプル コードに示すように、エントリを <xref:System.ServiceModel.Syndication.SyndicationFeed.AttributeExtensions%2A> コレクションに追加することによって作成されます。</span><span class="sxs-lookup"><span data-stu-id="198fa-116">Attribute extensions are created by adding entries to the <xref:System.ServiceModel.Syndication.SyndicationFeed.AttributeExtensions%2A> collection as shown in the following sample code.</span></span>  
  
```  
//Attribute extensions are stored in a dictionary indexed by   
// XmlQualifiedName  
feed.AttributeExtensions.Add(new XmlQualifiedName("myAttribute", ""), "someValue");  
```  
  
 <span data-ttu-id="198fa-117">要素拡張は、エントリを <xref:System.ServiceModel.Syndication.SyndicationFeed.ElementExtensions%2A> コレクションに追加することによって作成されます。</span><span class="sxs-lookup"><span data-stu-id="198fa-117">Element extensions are created by adding entries to the <xref:System.ServiceModel.Syndication.SyndicationFeed.ElementExtensions%2A> collection.</span></span> <span data-ttu-id="198fa-118">これらの拡張には、文字列などの基本的な値、.NET Framework オブジェクトの XML シリアル化、および手動で入力された XML ノードを指定できます。</span><span class="sxs-lookup"><span data-stu-id="198fa-118">These extensions can by basic values such as strings, XML serializations of .NET Framework objects, or XML nodes coded by hand.</span></span>  
  
 <span data-ttu-id="198fa-119">次のサンプル コードでは、`simpleString` という拡張要素が作成されます。</span><span class="sxs-lookup"><span data-stu-id="198fa-119">The following sample code creates an extension element named `simpleString`.</span></span>  
  
```  
feed.ElementExtensions.Add("simpleString", "", "hello, world!");  
```  
  
 <span data-ttu-id="198fa-120">この要素の XML 名前空間が空の名前空間 ("")、その値は「こんにちは, world!」を文字列に含まれているテキスト ノード。</span><span class="sxs-lookup"><span data-stu-id="198fa-120">The XML namespace for this element is the empty namespace ("") and its value is a text node that contains the string "hello, world!".</span></span>  
  
 <span data-ttu-id="198fa-121">入れ子になった多数の要素で構成される複雑な要素拡張を作成する方法の 1 つに、次の例に示すように、.NET Framework API をシリアル化に使用する方法があります (<xref:System.Runtime.Serialization.DataContractSerializer> と <xref:System.Xml.Serialization.XmlSerializer> の両方がサポートされています)。</span><span class="sxs-lookup"><span data-stu-id="198fa-121">One way to create complex element extensions that consist of many nested elements is to use the .NET Framework APIs for serialization (both the <xref:System.Runtime.Serialization.DataContractSerializer> and the <xref:System.Xml.Serialization.XmlSerializer> are supported) as shown in the following examples.</span></span>  
  
```  
feed.ElementExtensions.Add( new DataContractExtension() { Key = "X", Value = 4 } );  
feed.ElementExtensions.Add( new XmlSerializerExtension { Key = "Y", Value = 8 }, new XmlSerializer( typeof( XmlSerializerExtension ) ) );  
```  
  
 <span data-ttu-id="198fa-122">この例の `DataContractExtension` と `XmlSerializerExtension` は、シリアライザで使用するために記述されたカスタム型です。</span><span class="sxs-lookup"><span data-stu-id="198fa-122">In this example, the `DataContractExtension` and `XmlSerializerExtension` are custom types written for use with a serializer.</span></span>  
  
 <span data-ttu-id="198fa-123"><xref:System.ServiceModel.Syndication.SyndicationElementExtensionCollection> クラスを使用すると、<xref:System.Xml.XmlReader> インスタンスから要素拡張を作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="198fa-123">The <xref:System.ServiceModel.Syndication.SyndicationElementExtensionCollection> class can also be used to create element extensions from an <xref:System.Xml.XmlReader> instance.</span></span> <span data-ttu-id="198fa-124">これによって、次のサンプル コードに示すように、<xref:System.Xml.Linq.XElement> などの XML 処理 API と簡単に統合できるようになります。</span><span class="sxs-lookup"><span data-stu-id="198fa-124">This allows for easy integration with XML processing APIs such as <xref:System.Xml.Linq.XElement> as shown in the following sample code.</span></span>  
  
```  
feed.ElementExtensions.Add(new XElement("xElementExtension",  
        new XElement("Key", new XAttribute("attr1", "someValue"), "Z"),  
        new XElement("Value", new XAttribute("attr1", "someValue"),   
        "15")).CreateReader());  
```  
  
## <a name="reading-extension-data"></a><span data-ttu-id="198fa-125">拡張データの読み取り</span><span class="sxs-lookup"><span data-stu-id="198fa-125">Reading Extension Data</span></span>  
 <span data-ttu-id="198fa-126">属性の拡張の値は、次のサンプル コードに示すように、<xref:System.ServiceModel.Syndication.SyndicationFeed.AttributeExtensions%2A> を使用して <xref:System.Xml.XmlQualifiedName> コレクションの属性を検索することによって取得できます。</span><span class="sxs-lookup"><span data-stu-id="198fa-126">The values for attribute extensions can be obtained by looking up the attribute in the <xref:System.ServiceModel.Syndication.SyndicationFeed.AttributeExtensions%2A> collection by its <xref:System.Xml.XmlQualifiedName> as shown in the following sample code.</span></span>  
  
```  
Console.WriteLine( feed.AttributeExtensions[ new XmlQualifiedName( "myAttribute", "" )]);  
```  
  
 <span data-ttu-id="198fa-127">要素拡張には、`ReadElementExtensions<T>` メソッドを使用してアクセスします。</span><span class="sxs-lookup"><span data-stu-id="198fa-127">Element extensions are accessed using the `ReadElementExtensions<T>` method.</span></span>  
  
```  
foreach( string s in feed2.ElementExtensions.ReadElementExtensions<string>("simpleString", ""))  
{  
    Console.WriteLine(s);  
}  
  
foreach (DataContractExtension dce in feed2.ElementExtensions.ReadElementExtensions<DataContractExtension>("DataContractExtension",  
"http://schemas.datacontract.org/2004/07/SyndicationExtensions"))  
{  
    Console.WriteLine(dce.ToString());  
}  
  
foreach (XmlSerializerExtension xse in feed2.ElementExtensions.ReadElementExtensions<XmlSerializerExtension>("XmlSerializerExtension", "", new XmlSerializer(typeof(XmlSerializerExtension))))  
{  
    Console.WriteLine(xse.ToString());  
}  
```  
  
 <span data-ttu-id="198fa-128">`XmlReader` メソッドを使用して、個々の要素拡張で <xref:System.ServiceModel.Syndication.SyndicationElementExtension.GetReader> を取得することも可能です。</span><span class="sxs-lookup"><span data-stu-id="198fa-128">It is also possible to obtain an `XmlReader` at individual element extensions by using the <xref:System.ServiceModel.Syndication.SyndicationElementExtension.GetReader> method.</span></span>  
  
```  
foreach (SyndicationElementExtension extension in feed2.ElementExtensions.Where<SyndicationElementExtension>(x => x.OuterName == "xElementExtension"))  
{  
    XNode xelement = XElement.ReadFrom(extension.GetReader());  
    Console.WriteLine(xelement.ToString());  
}  
```  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="198fa-129">サンプルをセットアップ、ビルド、および実行するには</span><span class="sxs-lookup"><span data-stu-id="198fa-129">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="198fa-130">実行したことを確認、 [Windows Communication Foundation サンプルの 1 回限りのセットアップ手順](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)します。</span><span class="sxs-lookup"><span data-stu-id="198fa-130">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="198fa-131">ソリューションの C# 版または Visual Basic .NET 版をビルドするには、「 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)」の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="198fa-131">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="198fa-132">1 つまたは複数コンピュータ構成では、サンプルを実行する手順については、 [Windows Communication Foundation サンプルの実行](../../../../docs/framework/wcf/samples/running-the-samples.md)します。</span><span class="sxs-lookup"><span data-stu-id="198fa-132">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="198fa-133">サンプルは、既にコンピューターにインストールされている場合があります。</span><span class="sxs-lookup"><span data-stu-id="198fa-133">The samples may already be installed on your machine.</span></span> <span data-ttu-id="198fa-134">続行する前に、次の (既定の) ディレクトリを確認してください。</span><span class="sxs-lookup"><span data-stu-id="198fa-134">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="198fa-135">このディレクトリが存在しない場合に移動[Windows Communication Foundation (WCF) と .NET Framework 4 向けの Windows Workflow Foundation (WF) サンプル](https://go.microsoft.com/fwlink/?LinkId=150780)すべて Windows Communication Foundation (WCF) をダウンロードして[!INCLUDE[wf1](../../../../includes/wf1-md.md)]サンプル。</span><span class="sxs-lookup"><span data-stu-id="198fa-135">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="198fa-136">このサンプルは、次のディレクトリに格納されます。</span><span class="sxs-lookup"><span data-stu-id="198fa-136">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Syndication\LooselyTypedExtensions`  
  
## <a name="see-also"></a><span data-ttu-id="198fa-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="198fa-137">See also</span></span>

- [<span data-ttu-id="198fa-138">厳密に型指定された拡張</span><span class="sxs-lookup"><span data-stu-id="198fa-138">Strongly-Typed Extensions</span></span>](../../../../docs/framework/wcf/samples/strongly-typed-extensions-sample.md)
- [<span data-ttu-id="198fa-139">WCF 配信</span><span class="sxs-lookup"><span data-stu-id="198fa-139">WCF Syndication</span></span>](../../../../docs/framework/wcf/feature-details/wcf-syndication.md)
