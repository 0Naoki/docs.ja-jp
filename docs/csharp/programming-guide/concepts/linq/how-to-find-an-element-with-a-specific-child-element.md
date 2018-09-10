---
title: '方法: 特定の子要素を持つ要素を検索する (C#)'
ms.date: 07/20/2015
ms.assetid: 00cf5555-374e-4369-bf93-7bd2e7f21db3
ms.openlocfilehash: 36a6981a26f6f75c74256369c78361ee7f129a3e
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "43527821"
---
# <a name="how-to-find-an-element-with-a-specific-child-element-c"></a><span data-ttu-id="78bed-102">方法: 特定の子要素を持つ要素を検索する (C#)</span><span class="sxs-lookup"><span data-stu-id="78bed-102">How to: Find an Element with a Specific Child Element (C#)</span></span>
<span data-ttu-id="78bed-103">このトピックでは、特定の値を含む子要素を持つ特定の要素を検索する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="78bed-103">This topic shows how to find a particular element that has a child element with a specific value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="78bed-104">例</span><span class="sxs-lookup"><span data-stu-id="78bed-104">Example</span></span>  
 <span data-ttu-id="78bed-105">この例では、"Examp2.EXE" の値を含む `Test` 子要素を持つ `CommandLine` 要素を検索します。</span><span class="sxs-lookup"><span data-stu-id="78bed-105">The example finds the `Test` element that has a `CommandLine` child element with the value of "Examp2.EXE".</span></span>  
  
 <span data-ttu-id="78bed-106">この例では、「[サンプル XML ファイル: テスト構成 (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-test-configuration-linq-to-xml.md)」の XML ドキュメントを使用します。</span><span class="sxs-lookup"><span data-stu-id="78bed-106">This example uses the following XML document: [Sample XML File: Test Configuration (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-test-configuration-linq-to-xml.md).</span></span>  
  
```csharp  
XElement root = XElement.Load("TestConfig.xml");  
IEnumerable<XElement> tests =  
    from el in root.Elements("Test")  
    where (string)el.Element("CommandLine") == "Examp2.EXE"  
    select el;  
foreach (XElement el in tests)  
    Console.WriteLine((string)el.Attribute("TestId"));  
```  
  
 <span data-ttu-id="78bed-107">このコードを実行すると、次の出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="78bed-107">This code produces the following output:</span></span>  
  
```  
0002  
0006  
```  
  
## <a name="example"></a><span data-ttu-id="78bed-108">例</span><span class="sxs-lookup"><span data-stu-id="78bed-108">Example</span></span>  
 <span data-ttu-id="78bed-109">次の例は名前空間に含まれている XML 用のクエリです。これらのクエリは上の例と同じ機能を表しています。</span><span class="sxs-lookup"><span data-stu-id="78bed-109">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="78bed-110">詳細については、「[XML 名前空間の使用 (C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="78bed-110">For more information, see [Working with XML Namespaces (C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span></span>  
  
 <span data-ttu-id="78bed-111">この例では、「[サンプル XML ファイル : 名前空間内のテスト構成](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-test-configuration-in-a-namespace1.md)」の XML ドキュメントを使用します。</span><span class="sxs-lookup"><span data-stu-id="78bed-111">This example uses the following XML document: [Sample XML File: Test Configuration in a Namespace](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-test-configuration-in-a-namespace1.md).</span></span>  
  
```csharp  
XElement root = XElement.Load("TestConfigInNamespace.xml");  
XNamespace ad = "http://www.adatum.com";  
IEnumerable<XElement> tests =  
    from el in root.Elements(ad + "Test")  
    where (string)el.Element(ad + "CommandLine") == "Examp2.EXE"  
    select el;  
foreach (XElement el in tests)  
    Console.WriteLine((string)el.Attribute("TestId"));  
```  
  
 <span data-ttu-id="78bed-112">このコードを実行すると、次の出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="78bed-112">This code produces the following output:</span></span>  
  
```  
0002  
0006  
```  
  
## <a name="see-also"></a><span data-ttu-id="78bed-113">参照</span><span class="sxs-lookup"><span data-stu-id="78bed-113">See Also</span></span>

- <xref:System.Xml.Linq.XElement.Attribute%2A>  
- <xref:System.Xml.Linq.XContainer.Elements%2A>  
- [<span data-ttu-id="78bed-114">基本的なクエリ (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="78bed-114">Basic Queries (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)  
- [<span data-ttu-id="78bed-115">標準クエリ演算子の概要 (C#)</span><span class="sxs-lookup"><span data-stu-id="78bed-115">Standard Query Operators Overview (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)  
- [<span data-ttu-id="78bed-116">射影操作 (C#)</span><span class="sxs-lookup"><span data-stu-id="78bed-116">Projection Operations (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/projection-operations.md)
