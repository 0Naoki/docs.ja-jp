---
title: '方法: 子孫要素を検索する (XPath-LINQ to XML) (C#)'
ms.date: 07/20/2015
ms.assetid: b318da39-bb8b-4c56-a019-e13b12b01831
ms.openlocfilehash: df1b151948b7b11757f2f8f312fa1f0bba00673a
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/25/2018
ms.locfileid: "47078579"
---
# <a name="how-to-find-descendant-elements-xpath-linq-to-xml-c"></a><span data-ttu-id="5a4b9-102">方法: 子孫要素を検索する (XPath-LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="5a4b9-102">How to: Find Descendant Elements (XPath-LINQ to XML) (C#)</span></span>
<span data-ttu-id="5a4b9-103">このトピックでは、特定の名前を指定して子孫要素を取得する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5a4b9-103">This topic shows how to get the descendant elements with a particular name.</span></span>  
  
 <span data-ttu-id="5a4b9-104">XPath 式は `//Name` です。</span><span class="sxs-lookup"><span data-stu-id="5a4b9-104">The XPath expression is `//Name`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5a4b9-105">例</span><span class="sxs-lookup"><span data-stu-id="5a4b9-105">Example</span></span>  
 <span data-ttu-id="5a4b9-106">この例では、`Name` という名前の子孫要素をすべて検索します。</span><span class="sxs-lookup"><span data-stu-id="5a4b9-106">This example finds all descendants named `Name`.</span></span>  
  
 <span data-ttu-id="5a4b9-107">この例では、「[サンプル XML ファイル: 複数の購買発注書 (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-linq-to-xml.md)」の XML ドキュメントを使用します。</span><span class="sxs-lookup"><span data-stu-id="5a4b9-107">This example uses the following XML document: [Sample XML File: Multiple Purchase Orders (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span></span>  
  
```csharp  
XDocument po = XDocument.Load("PurchaseOrders.xml");  
  
// LINQ to XML query  
IEnumerable<XElement> list1 = po.Root.Descendants("Name");  
  
// XPath expression  
IEnumerable<XElement> list2 = po.XPathSelectElements("//Name");  
  
if (list1.Count() == list2.Count() &&  
        list1.Intersect(list2).Count() == list1.Count())  
    Console.WriteLine("Results are identical");  
else  
    Console.WriteLine("Results differ");  
foreach (XElement el in list1)  
    Console.WriteLine(el);  
```  
  
 <span data-ttu-id="5a4b9-108">この例を実行すると、次の出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="5a4b9-108">This example produces the following output:</span></span>  
  
```  
Results are identical  
<Name>Ellen Adams</Name>  
<Name>Tai Yee</Name>  
<Name>Cristian Osorio</Name>  
<Name>Cristian Osorio</Name>  
<Name>Jessica Arnold</Name>  
<Name>Jessica Arnold</Name>  
```  
  
## <a name="see-also"></a><span data-ttu-id="5a4b9-109">参照</span><span class="sxs-lookup"><span data-stu-id="5a4b9-109">See Also</span></span>

- [<span data-ttu-id="5a4b9-110">XPath ユーザー向けの LINQ to XML (C#)</span><span class="sxs-lookup"><span data-stu-id="5a4b9-110">LINQ to XML for XPath Users (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
