---
title: '方法: 特定の要素名を持つ子孫を検索する (C#)'
ms.date: 07/20/2015
ms.assetid: f684da20-bee9-47f5-9607-7e3fd7e67470
ms.openlocfilehash: dbb955697e4d4b0ed5aad9c00c37e73bbd32b7b4
ms.sourcegitcommit: eb9ff6f364cde6f11322e03800d8f5ce302f3c73
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/01/2019
ms.locfileid: "68709940"
---
# <a name="how-to-find-descendants-with-a-specific-element-name-c"></a><span data-ttu-id="d95d0-102">方法: 特定の要素名を持つ子孫を検索する (C#)</span><span class="sxs-lookup"><span data-stu-id="d95d0-102">How to: Find Descendants with a Specific Element Name (C#)</span></span>
<span data-ttu-id="d95d0-103">特定の名前を持つ子孫をすべて検索しなければならない場合があります。</span><span class="sxs-lookup"><span data-stu-id="d95d0-103">Sometimes you want to find all descendants with a particular name.</span></span> <span data-ttu-id="d95d0-104">すべての子孫を反復処理するコードを記述することもできますが、<xref:System.Xml.Linq.XContainer.Descendants%2A> 軸を使用する方が簡単です。</span><span class="sxs-lookup"><span data-stu-id="d95d0-104">You could write code to iterate through all of the descendants, but it is easier to use the <xref:System.Xml.Linq.XContainer.Descendants%2A> axis.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d95d0-105">例</span><span class="sxs-lookup"><span data-stu-id="d95d0-105">Example</span></span>  
 <span data-ttu-id="d95d0-106">要素名に基づいて子孫を検索する方法の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="d95d0-106">The following example shows how to find descendants based on the element name.</span></span>  
  
```csharp  
XElement root = XElement.Parse(@"<root>  
  <para>  
    <r>  
      <t>Some text </t>  
    </r>  
    <n>  
      <r>  
        <t>that is broken up into </t>  
      </r>  
    </n>  
    <n>  
      <r>  
        <t>multiple segments.</t>  
      </r>  
    </n>  
  </para>  
</root>");  
IEnumerable<string> textSegs =  
    from seg in root.Descendants("t")  
    select (string)seg;  
  
string str = textSegs.Aggregate(new StringBuilder(),  
    (sb, i) => sb.Append(i),  
    sp => sp.ToString()  
);  
  
Console.WriteLine(str);  
```  
  
 <span data-ttu-id="d95d0-107">このコードを実行すると、次の出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="d95d0-107">This code produces the following output:</span></span>  
  
```  
Some text that is broken up into multiple segments.  
```  
  
## <a name="example"></a><span data-ttu-id="d95d0-108">例</span><span class="sxs-lookup"><span data-stu-id="d95d0-108">Example</span></span>  
 <span data-ttu-id="d95d0-109">次の例は名前空間に含まれている XML 用のクエリです。これらのクエリは上の例と同じ機能を表しています。</span><span class="sxs-lookup"><span data-stu-id="d95d0-109">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="d95d0-110">詳細については、「[名前空間の概要 (LINQ to XML)](namespaces-overview-linq-to-xml.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d95d0-110">For more information, see [Namespaces Overview (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span></span>  
  
```csharp  
XElement root = XElement.Parse(@"<root xmlns='http://www.adatum.com'>  
  <para>  
    <r>  
      <t>Some text </t>  
    </r>  
    <n>  
      <r>  
        <t>that is broken up into </t>  
      </r>  
    </n>  
    <n>  
      <r>  
        <t>multiple segments.</t>  
      </r>  
    </n>  
  </para>  
</root>");  
XNamespace ad = "http://www.adatum.com";  
IEnumerable<string> textSegs =  
    from seg in root.Descendants(ad + "t")  
    select (string)seg;  
  
string str = textSegs.Aggregate(new StringBuilder(),  
    (sb, i) => sb.Append(i),  
    sp => sp.ToString()  
);  
  
Console.WriteLine(str);  
```  
  
 <span data-ttu-id="d95d0-111">このコードを実行すると、次の出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="d95d0-111">This code produces the following output:</span></span>  
  
```  
Some text that is broken up into multiple segments.  
```  
  
## <a name="see-also"></a><span data-ttu-id="d95d0-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="d95d0-112">See also</span></span>

- <xref:System.Xml.Linq.XContainer.Descendants%2A>
