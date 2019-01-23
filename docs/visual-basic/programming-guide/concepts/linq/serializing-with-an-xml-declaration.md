---
title: XML 宣言 (Visual Basic) 付きのシリアル化
ms.date: 07/20/2015
ms.assetid: 8726f79e-2bb0-4ba0-969d-197cca591647
ms.openlocfilehash: d0d6ccfdffa76de61c36e4cdb3f68f7cf85f1e68
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54558476"
---
# <a name="serializing-with-an-xml-declaration-visual-basic"></a><span data-ttu-id="68651-102">XML 宣言 (Visual Basic) 付きのシリアル化</span><span class="sxs-lookup"><span data-stu-id="68651-102">Serializing with an XML Declaration (Visual Basic)</span></span>
<span data-ttu-id="68651-103">このトピックでは、シリアル化を実行する際に XML 宣言を生成するかどうかを制御する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="68651-103">This topic describes how to control whether serialization generates an XML declaration.</span></span>  
  
## <a name="xml-declaration-generation"></a><span data-ttu-id="68651-104">XML 宣言の生成</span><span class="sxs-lookup"><span data-stu-id="68651-104">XML Declaration Generation</span></span>  
 <span data-ttu-id="68651-105"><xref:System.IO.File> メソッドまたは <xref:System.IO.TextWriter> メソッドを使用して <xref:System.Xml.Linq.XElement.Save%2A?displayProperty=nameWithType> または <xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=nameWithType> にシリアル化すると、XML 宣言が生成されます。</span><span class="sxs-lookup"><span data-stu-id="68651-105">Serializing to a <xref:System.IO.File> or a <xref:System.IO.TextWriter> using the <xref:System.Xml.Linq.XElement.Save%2A?displayProperty=nameWithType> method or the <xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=nameWithType> method generates an XML declaration.</span></span> <span data-ttu-id="68651-106"><xref:System.Xml.XmlWriter> にシリアル化する場合は、<xref:System.Xml.XmlWriterSettings> オブジェクトで指定したライター設定により、XML 宣言が生成されるかどうかが決定されます。</span><span class="sxs-lookup"><span data-stu-id="68651-106">When you serialize to an <xref:System.Xml.XmlWriter>, the writer settings (specified in an <xref:System.Xml.XmlWriterSettings> object) determine whether an XML declaration is generated or not.</span></span>  
  
 <span data-ttu-id="68651-107">`ToString` メソッドを使用して文字列にシリアル化する場合、生成される XML には XML 宣言は含まれません。</span><span class="sxs-lookup"><span data-stu-id="68651-107">If you are serializing to a string using the `ToString` method, the resulting XML will not include an XML declaration.</span></span>  
  
### <a name="serializing-with-an-xml-declaration"></a><span data-ttu-id="68651-108">XML 宣言付きのシリアル化</span><span class="sxs-lookup"><span data-stu-id="68651-108">Serializing with an XML Declaration</span></span>  
 <span data-ttu-id="68651-109">次の例では、<xref:System.Xml.Linq.XElement> を作成し、ドキュメントをファイルに保存して、そのファイルをコンソールに出力します。</span><span class="sxs-lookup"><span data-stu-id="68651-109">The following example creates an <xref:System.Xml.Linq.XElement>, saves the document to a file, and then prints the file to the console:</span></span>  
  
```vb  
Dim root As XElement = <Root>  
                           <Child>child content</Child>  
                       </Root>  
root.Save("Root.xml")  
Dim str As String = File.ReadAllText("Root.xml")  
Console.WriteLine(str)  
```  
  
 <span data-ttu-id="68651-110">この例を実行すると、次の出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="68651-110">This example produces the following output:</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<Root>  
  <Child>child content</Child>  
</Root>  
```  
  
### <a name="serializing-without-an-xml-declaration"></a><span data-ttu-id="68651-111">XML 宣言なしでのシリアル化</span><span class="sxs-lookup"><span data-stu-id="68651-111">Serializing without an XML Declaration</span></span>  
 <span data-ttu-id="68651-112"><xref:System.Xml.Linq.XElement> を <xref:System.Xml.XmlWriter> に保存する方法を次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="68651-112">The following example shows how to save an <xref:System.Xml.Linq.XElement> to an <xref:System.Xml.XmlWriter>.</span></span>  
  
```vb  
Dim sb As StringBuilder = New StringBuilder()  
Dim xws As XmlWriterSettings = New XmlWriterSettings()  
xws.OmitXmlDeclaration = True  
  
Using xw As XmlWriter = XmlWriter.Create(sb, xws)  
    Dim root = <Root>  
                   <Child>child content</Child>  
               </Root>  
    root.Save(xw)  
End Using  
Console.WriteLine(sb.ToString())  
```  
  
 <span data-ttu-id="68651-113">この例を実行すると、次の出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="68651-113">This example produces the following output:</span></span>  
  
```xml  
<Root><Child>child content</Child></Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="68651-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="68651-114">See also</span></span>
- [<span data-ttu-id="68651-115">シリアル化する XML ツリー (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="68651-115">Serializing XML Trees (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/serializing-xml-trees.md)
