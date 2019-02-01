---
title: '方法: コンテキストに基づいて要素を検索するクエリを記述する (C#)'
ms.date: 07/20/2015
ms.assetid: 3ff79ef0-fc8b-42fe-8cc0-10dc32b06b4e
ms.openlocfilehash: 93bfd77ce6bb7be1d305f20f56da67e8fb9c22f0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54667951"
---
# <a name="how-to-write-a-query-that-finds-elements-based-on-context-c"></a><span data-ttu-id="a4f42-102">方法: コンテキストに基づいて要素を検索するクエリを記述する (C#)</span><span class="sxs-lookup"><span data-stu-id="a4f42-102">How to: Write a Query that Finds Elements Based on Context (C#)</span></span>
<span data-ttu-id="a4f42-103">コンテキストに基づいて要素を選択するクエリの記述が必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="a4f42-103">Sometimes you might have to write a query that selects elements based on their context.</span></span> <span data-ttu-id="a4f42-104">つまり、前の兄弟要素や次の兄弟要素に基づいてフィルターしたり、</span><span class="sxs-lookup"><span data-stu-id="a4f42-104">You might want to filter based on preceding or following sibling elements.</span></span> <span data-ttu-id="a4f42-105">子要素や祖先要素に基づいてフィルターすることが必要になる場合が考えられます。</span><span class="sxs-lookup"><span data-stu-id="a4f42-105">You might want to filter based on child or ancestor elements.</span></span>  
  
 <span data-ttu-id="a4f42-106">これを実現するには、クエリを記述し、そのクエリの結果を `where` 句で使用します。</span><span class="sxs-lookup"><span data-stu-id="a4f42-106">You can do this by writing a query and using the results of the query in the `where` clause.</span></span> <span data-ttu-id="a4f42-107">最初に NULL に対してテストし、次に値をテストする必要がある場合は、`let` 句でクエリを実行し、次にその結果を `where` 句で使用する方が便利です。</span><span class="sxs-lookup"><span data-stu-id="a4f42-107">If you have to first test against null, and then test the value, it is more convenient to do the query in a `let` clause, and then use the results in the `where` clause.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a4f42-108">例</span><span class="sxs-lookup"><span data-stu-id="a4f42-108">Example</span></span>  
 <span data-ttu-id="a4f42-109">次の例では、`p` 要素の直前の `ul` 要素をすべて選択します。</span><span class="sxs-lookup"><span data-stu-id="a4f42-109">The following example selects all `p` elements that are immediately followed by a `ul` element.</span></span>  
  
```csharp  
XElement doc = XElement.Parse(@"<Root>  
    <p id=""1""/>  
    <ul>abc</ul>  
    <Child>  
        <p id=""2""/>  
        <notul/>  
        <p id=""3""/>  
        <ul>def</ul>  
        <p id=""4""/>  
    </Child>  
    <Child>  
        <p id=""5""/>  
        <notul/>  
        <p id=""6""/>  
        <ul>abc</ul>  
        <p id=""7""/>  
    </Child>  
</Root>");  
  
IEnumerable<XElement> items =  
    from e in doc.Descendants("p")  
    let z = e.ElementsAfterSelf().FirstOrDefault()  
    where z != null && z.Name.LocalName == "ul"  
    select e;  
  
foreach (XElement e in items)  
    Console.WriteLine("id = {0}", (string)e.Attribute("id"));  
```  
  
 <span data-ttu-id="a4f42-110">このコードを実行すると、次の出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="a4f42-110">This code produces the following output:</span></span>  
  
```  
id = 1  
id = 3  
id = 6  
```  
  
## <a name="example"></a><span data-ttu-id="a4f42-111">例</span><span class="sxs-lookup"><span data-stu-id="a4f42-111">Example</span></span>  
 <span data-ttu-id="a4f42-112">次の例は名前空間に含まれている XML 用のクエリです。これらのクエリは上の例と同じ機能を表しています。</span><span class="sxs-lookup"><span data-stu-id="a4f42-112">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="a4f42-113">詳細については、「[XML 名前空間の使用 (C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a4f42-113">For more information, see [Working with XML Namespaces (C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span></span>  
  
```csharp  
XElement doc = XElement.Parse(@"<Root xmlns='http://www.adatum.com'>  
    <p id=""1""/>  
    <ul>abc</ul>  
    <Child>  
        <p id=""2""/>  
        <notul/>  
        <p id=""3""/>  
        <ul>def</ul>  
        <p id=""4""/>  
    </Child>  
    <Child>  
        <p id=""5""/>  
        <notul/>  
        <p id=""6""/>  
        <ul>abc</ul>  
        <p id=""7""/>  
    </Child>  
</Root>");  
  
XNamespace ad = "http://www.adatum.com";  
  
IEnumerable<XElement> items =  
    from e in doc.Descendants(ad + "p")  
    let z = e.ElementsAfterSelf().FirstOrDefault()  
    where z != null && z.Name == ad.GetName("ul")  
    select e;  
  
foreach (XElement e in items)  
    Console.WriteLine("id = {0}", (string)e.Attribute("id"));  
```  
  
 <span data-ttu-id="a4f42-114">このコードを実行すると、次の出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="a4f42-114">This code produces the following output:</span></span>  
  
```  
id = 1  
id = 3  
id = 6  
```  
  
## <a name="see-also"></a><span data-ttu-id="a4f42-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="a4f42-115">See also</span></span>

- <xref:System.Xml.Linq.XElement.Parse%2A>
- <xref:System.Xml.Linq.XContainer.Descendants%2A>
- <xref:System.Xml.Linq.XNode.ElementsAfterSelf%2A>
- <xref:System.Linq.Enumerable.FirstOrDefault%2A>
- [<span data-ttu-id="a4f42-116">基本的なクエリ (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="a4f42-116">Basic Queries (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)
