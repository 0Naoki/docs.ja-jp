---
title: XML 宣言付きのシリアル化 (C#)
ms.date: 07/20/2015
ms.assetid: c237fa4a-a042-40fd-886f-17b54c66bb75
ms.openlocfilehash: 613280efc8c734c53c4af9252b4b83e2dd942f36
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/09/2018
ms.locfileid: "44222358"
---
# <a name="serializing-with-an-xml-declaration-c"></a><span data-ttu-id="3e41b-102">XML 宣言付きのシリアル化 (C#)</span><span class="sxs-lookup"><span data-stu-id="3e41b-102">Serializing with an XML Declaration (C#)</span></span>
<span data-ttu-id="3e41b-103">このトピックでは、シリアル化を実行する際に XML 宣言を生成するかどうかを制御する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="3e41b-103">This topic describes how to control whether serialization generates an XML declaration.</span></span>  
  
## <a name="xml-declaration-generation"></a><span data-ttu-id="3e41b-104">XML 宣言の生成</span><span class="sxs-lookup"><span data-stu-id="3e41b-104">XML Declaration Generation</span></span>  
 <span data-ttu-id="3e41b-105"><xref:System.IO.File> メソッドまたは <xref:System.IO.TextWriter> メソッドを使用して <xref:System.Xml.Linq.XElement.Save%2A?displayProperty=nameWithType> または <xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=nameWithType> にシリアル化すると、XML 宣言が生成されます。</span><span class="sxs-lookup"><span data-stu-id="3e41b-105">Serializing to a <xref:System.IO.File> or a <xref:System.IO.TextWriter> using the <xref:System.Xml.Linq.XElement.Save%2A?displayProperty=nameWithType> method or the <xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=nameWithType> method generates an XML declaration.</span></span> <span data-ttu-id="3e41b-106"><xref:System.Xml.XmlWriter> にシリアル化する場合は、<xref:System.Xml.XmlWriterSettings> オブジェクトで指定したライター設定により、XML 宣言が生成されるかどうかが決定されます。</span><span class="sxs-lookup"><span data-stu-id="3e41b-106">When you serialize to an <xref:System.Xml.XmlWriter>, the writer settings (specified in an <xref:System.Xml.XmlWriterSettings> object) determine whether an XML declaration is generated or not.</span></span>  
  
 <span data-ttu-id="3e41b-107">`ToString` メソッドを使用して文字列にシリアル化する場合、生成される XML には XML 宣言は含まれません。</span><span class="sxs-lookup"><span data-stu-id="3e41b-107">If you are serializing to a string using the `ToString` method, the resulting XML will not include an XML declaration.</span></span>  
  
### <a name="serializing-with-an-xml-declaration"></a><span data-ttu-id="3e41b-108">XML 宣言付きのシリアル化</span><span class="sxs-lookup"><span data-stu-id="3e41b-108">Serializing with an XML Declaration</span></span>  
 <span data-ttu-id="3e41b-109">次の例では、<xref:System.Xml.Linq.XElement> を作成し、ドキュメントをファイルに保存して、そのファイルをコンソールに出力します。</span><span class="sxs-lookup"><span data-stu-id="3e41b-109">The following example creates an <xref:System.Xml.Linq.XElement>, saves the document to a file, and then prints the file to the console:</span></span>  
  
```csharp  
XElement root = new XElement("Root",  
    new XElement("Child", "child content")  
);  
root.Save("Root.xml");  
string str = File.ReadAllText("Root.xml");  
Console.WriteLine(str);  
```  
  
 <span data-ttu-id="3e41b-110">この例を実行すると、次の出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="3e41b-110">This example produces the following output:</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<Root>  
  <Child>child content</Child>  
</Root>  
```  
  
### <a name="serializing-without-an-xml-declaration"></a><span data-ttu-id="3e41b-111">XML 宣言なしでのシリアル化</span><span class="sxs-lookup"><span data-stu-id="3e41b-111">Serializing without an XML Declaration</span></span>  
 <span data-ttu-id="3e41b-112"><xref:System.Xml.Linq.XElement> を <xref:System.Xml.XmlWriter> に保存する方法を次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="3e41b-112">The following example shows how to save an <xref:System.Xml.Linq.XElement> to an <xref:System.Xml.XmlWriter>.</span></span>  
  
```csharp  
StringBuilder sb = new StringBuilder();  
XmlWriterSettings xws = new XmlWriterSettings();  
xws.OmitXmlDeclaration = true;  
  
using (XmlWriter xw = XmlWriter.Create(sb, xws)) {  
    XElement root = new XElement("Root",  
        new XElement("Child", "child content")  
    );  
    root.Save(xw);  
}  
Console.WriteLine(sb.ToString());  
```  
  
 <span data-ttu-id="3e41b-113">この例を実行すると、次の出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="3e41b-113">This example produces the following output:</span></span>  
  
```xml  
<Root><Child>child content</Child></Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="3e41b-114">参照</span><span class="sxs-lookup"><span data-stu-id="3e41b-114">See Also</span></span>

- [<span data-ttu-id="3e41b-115">XML ツリーのシリアル化 (C#)</span><span class="sxs-lookup"><span data-stu-id="3e41b-115">Serializing XML Trees (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/serializing-xml-trees.md)
