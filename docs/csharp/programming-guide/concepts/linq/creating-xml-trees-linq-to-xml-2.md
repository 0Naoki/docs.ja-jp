---
title: C# での XML ツリーの作成 (LINQ to XML)
ms.date: 08/31/2018
ms.assetid: cc74234a-0bac-4327-9c8c-5a2ead15b595
ms.openlocfilehash: 41da4de20558508844b56a492b603f947ae04b81
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/02/2018
ms.locfileid: "43399252"
---
# <a name="creating-xml-trees-in-c-linq-to-xml"></a><span data-ttu-id="7d56c-102">C# での XML ツリーの作成 (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="7d56c-102">Creating XML trees in C# (LINQ to XML)</span></span>
<span data-ttu-id="7d56c-103">ここでは、C# での XML ツリーの作成について説明します。</span><span class="sxs-lookup"><span data-stu-id="7d56c-103">This section provides information about creating XML trees in C#.</span></span>  
  
 <span data-ttu-id="7d56c-104">LINQ クエリの結果を <xref:System.Xml.Linq.XElement> のコンテンツとして使用する方法については、「[関数型構築 (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/functional-construction-linq-to-xml.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7d56c-104">For information about using the results of LINQ queries as the content for an <xref:System.Xml.Linq.XElement>, see [Functional Construction (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/functional-construction-linq-to-xml.md).</span></span>  
  
## <a name="constructing-elements"></a><span data-ttu-id="7d56c-105">要素の構築</span><span class="sxs-lookup"><span data-stu-id="7d56c-105">Constructing elements</span></span>
 <span data-ttu-id="7d56c-106"><xref:System.Xml.Linq.XElement> コンストラクターと <xref:System.Xml.Linq.XAttribute> コンストラクターのシグネチャを使用すると、要素または属性のコンテンツを引数としてコンストラクターに渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="7d56c-106">The signatures of the <xref:System.Xml.Linq.XElement> and <xref:System.Xml.Linq.XAttribute> constructors let you pass the contents of the element or attribute as arguments to the constructor.</span></span> <span data-ttu-id="7d56c-107">いずれかのコンストラクターは任意の数の引数を受け取るため、任意の数の子要素を渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="7d56c-107">Because one of the constructors takes a variable number of arguments, you can pass any number of child elements.</span></span> <span data-ttu-id="7d56c-108">もちろん、それらの子要素のそれぞれに、さらに子要素を含めることもできます。</span><span class="sxs-lookup"><span data-stu-id="7d56c-108">Of course, each of those child elements can contain their own child elements.</span></span> <span data-ttu-id="7d56c-109">いずれの要素にも、任意の数の属性を追加できます。</span><span class="sxs-lookup"><span data-stu-id="7d56c-109">For any element, you can add any number of attributes.</span></span>  
  
 <span data-ttu-id="7d56c-110"><xref:System.Xml.Linq.XNode> オブジェクト (<xref:System.Xml.Linq.XElement> を含む) や <xref:System.Xml.Linq.XAttribute> オブジェクトの追加時に、新しいコンテンツに親がない場合、単にオブジェクトが XML ツリーにアタッチされます。</span><span class="sxs-lookup"><span data-stu-id="7d56c-110">When adding <xref:System.Xml.Linq.XNode> (including <xref:System.Xml.Linq.XElement>) or <xref:System.Xml.Linq.XAttribute> objects, if the new content has no parent, the objects are simply attached to the XML tree.</span></span> <span data-ttu-id="7d56c-111">新しいコンテンツに既に親があり、別の XML ツリーの一部となっている場合は、新しいコンテンツが複製され、新しく複製されたコンテンツが XML ツリーにアタッチされます。</span><span class="sxs-lookup"><span data-stu-id="7d56c-111">If the new content already is parented, and is part of another XML tree, the new content is cloned, and the newly cloned content is attached to the XML tree.</span></span> <span data-ttu-id="7d56c-112">このトピックの最後の例では、この動作について説明します。</span><span class="sxs-lookup"><span data-stu-id="7d56c-112">The last example in this topic demonstrates this.</span></span>  
  
 <span data-ttu-id="7d56c-113">`contacts`<xref:System.Xml.Linq.XElement> を作成するには、次のコードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="7d56c-113">To create a `contacts`<xref:System.Xml.Linq.XElement>, you could use the following code:</span></span>  
  
```csharp  
XElement contacts =  
    new XElement("Contacts",  
        new XElement("Contact",  
            new XElement("Name", "Patrick Hines"),   
            new XElement("Phone", "206-555-0144"),  
            new XElement("Address",  
                new XElement("Street1", "123 Main St"),  
                new XElement("City", "Mercer Island"),  
                new XElement("State", "WA"),  
                new XElement("Postal", "68042")  
            )  
        )  
    );  
```  
  
 <span data-ttu-id="7d56c-114">適切にインデントされていれば、<xref:System.Xml.Linq.XElement> オブジェクトを構築するコードは、基になる XML の構造によく似ています。</span><span class="sxs-lookup"><span data-stu-id="7d56c-114">If indented properly, the code to construct <xref:System.Xml.Linq.XElement> objects closely resembles the structure of the underlying XML.</span></span>  
  
## <a name="xelement-constructors"></a><span data-ttu-id="7d56c-115">XElement コンストラクター</span><span class="sxs-lookup"><span data-stu-id="7d56c-115">XElement constructors</span></span>  
 <span data-ttu-id="7d56c-116"><xref:System.Xml.Linq.XElement> クラスは、関数型構築で次のコンストラクターを使用します。</span><span class="sxs-lookup"><span data-stu-id="7d56c-116">The <xref:System.Xml.Linq.XElement> class uses the following constructors for functional construction.</span></span> <span data-ttu-id="7d56c-117"><xref:System.Xml.Linq.XElement> のコンストラクターはこれ以外にも存在しますが、関数型構築に使用されないものはこの一覧に示していません。</span><span class="sxs-lookup"><span data-stu-id="7d56c-117">Note that there are some other constructors for <xref:System.Xml.Linq.XElement>, but because they are not used for functional construction they are not listed here.</span></span>  
  
|<span data-ttu-id="7d56c-118">コンストラクター</span><span class="sxs-lookup"><span data-stu-id="7d56c-118">Constructor</span></span>|<span data-ttu-id="7d56c-119">説明</span><span class="sxs-lookup"><span data-stu-id="7d56c-119">Description</span></span>|  
|-----------------|-----------------|  
|`XElement(XName name, object content)`|<span data-ttu-id="7d56c-120"><xref:System.Xml.Linq.XElement> を作成します。</span><span class="sxs-lookup"><span data-stu-id="7d56c-120">Creates an <xref:System.Xml.Linq.XElement>.</span></span> <span data-ttu-id="7d56c-121">`name` パラメーターには要素の名前を指定し、`content` には要素のコンテンツを指定します。</span><span class="sxs-lookup"><span data-stu-id="7d56c-121">The `name` parameter specifies the name of the element; `content` specifies the content of the element.</span></span>|  
|`XElement(XName name)`|<span data-ttu-id="7d56c-122">指定した名前で <xref:System.Xml.Linq.XElement> を初期化して、<xref:System.Xml.Linq.XName> を作成します。</span><span class="sxs-lookup"><span data-stu-id="7d56c-122">Creates an <xref:System.Xml.Linq.XElement> with its <xref:System.Xml.Linq.XName> initialized to the specified name.</span></span>|  
|`XElement(XName name, params object[] content)`|<span data-ttu-id="7d56c-123">指定した名前で <xref:System.Xml.Linq.XElement> を初期化して、<xref:System.Xml.Linq.XName> を作成します。</span><span class="sxs-lookup"><span data-stu-id="7d56c-123">Creates an <xref:System.Xml.Linq.XElement> with its <xref:System.Xml.Linq.XName> initialized to the specified name.</span></span> <span data-ttu-id="7d56c-124">属性や子要素が、パラメーター リストのコンテンツから作成されます。</span><span class="sxs-lookup"><span data-stu-id="7d56c-124">The attributes and/or child elements are created from the contents of the parameter list.</span></span>|  
  
 <span data-ttu-id="7d56c-125">`content` パラメーターは非常に柔軟です。</span><span class="sxs-lookup"><span data-stu-id="7d56c-125">The `content` parameter is extremely flexible.</span></span> <span data-ttu-id="7d56c-126"><xref:System.Xml.Linq.XElement> の有効な子オブジェクトの型すべてがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="7d56c-126">It supports any type of object that is a valid child of an <xref:System.Xml.Linq.XElement>.</span></span> <span data-ttu-id="7d56c-127">このパラメーターで渡されるさまざまな型のオブジェクトには、次の規則が適用されます。</span><span class="sxs-lookup"><span data-stu-id="7d56c-127">The following rules apply to different types of objects passed in this parameter:</span></span>  
  
-   <span data-ttu-id="7d56c-128">文字列はテキスト コンテンツとして追加されます。</span><span class="sxs-lookup"><span data-stu-id="7d56c-128">A string is added as text content.</span></span>  
  
-   <span data-ttu-id="7d56c-129"><xref:System.Xml.Linq.XElement> は子要素として追加されます。</span><span class="sxs-lookup"><span data-stu-id="7d56c-129">An <xref:System.Xml.Linq.XElement> is added as a child element.</span></span>  
  
-   <span data-ttu-id="7d56c-130"><xref:System.Xml.Linq.XAttribute> は属性として追加されます。</span><span class="sxs-lookup"><span data-stu-id="7d56c-130">An <xref:System.Xml.Linq.XAttribute> is added as an attribute.</span></span>  
  
-   <span data-ttu-id="7d56c-131"><xref:System.Xml.Linq.XProcessingInstruction>、<xref:System.Xml.Linq.XComment>、または <xref:System.Xml.Linq.XText> は、子コンテンツとして追加されます。</span><span class="sxs-lookup"><span data-stu-id="7d56c-131">An <xref:System.Xml.Linq.XProcessingInstruction>, <xref:System.Xml.Linq.XComment>, or <xref:System.Xml.Linq.XText> is added as child content.</span></span>  
  
-   <span data-ttu-id="7d56c-132"><xref:System.Collections.IEnumerable> は列挙され、その結果にこれらの規則が再帰的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="7d56c-132">An <xref:System.Collections.IEnumerable> is enumerated, and these rules are applied recursively to the results.</span></span>  
  
-   <span data-ttu-id="7d56c-133">その他の型に対しては `ToString` メソッドが呼び出され、その結果がテキスト コンテンツとして追加されます。</span><span class="sxs-lookup"><span data-stu-id="7d56c-133">For any other type, its `ToString` method is called and the result is added as text content.</span></span>  
  
### <a name="creating-an-xelement-with-content"></a><span data-ttu-id="7d56c-134">コンテンツを持つ XElement の作成</span><span class="sxs-lookup"><span data-stu-id="7d56c-134">Creating an XElement with content</span></span>  
 <span data-ttu-id="7d56c-135">単純コンテンツが含まれる <xref:System.Xml.Linq.XElement> は、1 回のメソッド呼び出しで作成できます。</span><span class="sxs-lookup"><span data-stu-id="7d56c-135">You can create an <xref:System.Xml.Linq.XElement> that contains simple content with a single method call.</span></span> <span data-ttu-id="7d56c-136">そのためには、次のように、コンテンツを 2 番目のパラメーターとして指定します。</span><span class="sxs-lookup"><span data-stu-id="7d56c-136">To do this, specify the content as the second parameter, as follows:</span></span>  
  
```csharp  
XElement n = new XElement("Customer", "Adventure Works");  
Console.WriteLine(n);  
```  
  
 <span data-ttu-id="7d56c-137">この例を実行すると、次の出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="7d56c-137">This example produces the following output:</span></span>  
  
```xml  
<Customer>Adventure Works</Customer>  
```  
  
 <span data-ttu-id="7d56c-138">任意の型のオブジェクトをコンテンツとして渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="7d56c-138">You can pass any type of object as the content.</span></span> <span data-ttu-id="7d56c-139">たとえば、次のコードでは、浮動小数点数がコンテンツとして含まれる要素を作成します。</span><span class="sxs-lookup"><span data-stu-id="7d56c-139">For example, the following code creates an element that contains a floating point number as content:</span></span>  
  
```csharp  
XElement n = new XElement("Cost", 324.50);  
Console.WriteLine(n);  
```  
  
 <span data-ttu-id="7d56c-140">この例を実行すると、次の出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="7d56c-140">This example produces the following output:</span></span>  
  
```xml  
<Cost>324.5</Cost>  
```  
  
 <span data-ttu-id="7d56c-141">浮動小数点数はボックス化されてコンストラクターに渡されます。</span><span class="sxs-lookup"><span data-stu-id="7d56c-141">The floating point number is boxed and passed in to the constructor.</span></span> <span data-ttu-id="7d56c-142">ボックス化された数は文字列に変換され、要素のコンテンツとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="7d56c-142">The boxed number is converted to a string and used as the content of the element.</span></span>  
  
### <a name="creating-an-xelement-with-a-child-element"></a><span data-ttu-id="7d56c-143">子要素を持つ XElement の作成</span><span class="sxs-lookup"><span data-stu-id="7d56c-143">Creating an XElement with a child element</span></span>  
 <span data-ttu-id="7d56c-144"><xref:System.Xml.Linq.XElement> クラスのインスタンスをコンテンツ引数として渡すと、コンストラクターによって、子要素を持つ要素が作成されます。</span><span class="sxs-lookup"><span data-stu-id="7d56c-144">If you pass an instance of the <xref:System.Xml.Linq.XElement> class for the content argument, the constructor creates an element with a child element:</span></span>  
  
```csharp  
XElement shippingUnit = new XElement("ShippingUnit",  
    new XElement("Cost", 324.50)  
);  
Console.WriteLine(shippingUnit);  
```  
  
 <span data-ttu-id="7d56c-145">この例を実行すると、次の出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="7d56c-145">This example produces the following output:</span></span>  
  
```xml  
<ShippingUnit>  
  <Cost>324.5</Cost>  
</ShippingUnit>  
```  
  
### <a name="creating-an-xelement-with-multiple-child-elements"></a><span data-ttu-id="7d56c-146">複数の子要素を持つ XElement の作成</span><span class="sxs-lookup"><span data-stu-id="7d56c-146">Creating an XElement with multiple child elements</span></span>  
 <span data-ttu-id="7d56c-147">複数の <xref:System.Xml.Linq.XElement> オブジェクトをコンテンツとして渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="7d56c-147">You can pass in a number of <xref:System.Xml.Linq.XElement> objects for the content.</span></span> <span data-ttu-id="7d56c-148">各 <xref:System.Xml.Linq.XElement> オブジェクトは、子要素として格納されます。</span><span class="sxs-lookup"><span data-stu-id="7d56c-148">Each of the <xref:System.Xml.Linq.XElement> objects is included as a child element.</span></span>  
  
```csharp  
XElement address = new XElement("Address",  
    new XElement("Street1", "123 Main St"),  
    new XElement("City", "Mercer Island"),  
    new XElement("State", "WA"),  
    new XElement("Postal", "68042")  
);  
Console.WriteLine(address);  
```  
  
 <span data-ttu-id="7d56c-149">この例を実行すると、次の出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="7d56c-149">This example produces the following output:</span></span>  
  
```xml  
<Address>  
  <Street1>123 Main St</Street1>  
  <City>Mercer Island</City>  
  <State>WA</State>  
  <Postal>68042</Postal>  
</Address>  
```  
  
 <span data-ttu-id="7d56c-150">上の例を次のように拡張すると、完全な XML ツリーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="7d56c-150">By extending the above example, you can create an entire XML tree, as follows:</span></span>  
  
```csharp  
XElement contacts =  
    new XElement("Contacts",  
        new XElement("Contact",  
            new XElement("Name", "Patrick Hines"),                                                   
            new XElement("Phone", "206-555-0144"),  
            new XElement("Address",  
                new XElement("Street1", "123 Main St"),  
                new XElement("City", "Mercer Island"),  
                new XElement("State", "WA"),  
                new XElement("Postal", "68042")  
            )  
        )  
    );  
Console.WriteLine(contacts);  
```  
  
 <span data-ttu-id="7d56c-151">この例を実行すると、次の出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="7d56c-151">This example produces the following output:</span></span>  
  
```xml  
<Contacts>  
  <Contact>  
    <Name>Patrick Hines</Name>  
    <Phone>206-555-0144</Phone>  
    <Address>  
      <Street1>123 Main St</Street1>  
      <City>Mercer Island</City>  
      <State>WA</State>  
      <Postal>68042</Postal>  
    </Address>  
  </Contact>  
</Contacts>  
```  
  
### <a name="creating-an-empty-element"></a><span data-ttu-id="7d56c-152">空要素の作成</span><span class="sxs-lookup"><span data-stu-id="7d56c-152">Creating an empty element</span></span>  
 <span data-ttu-id="7d56c-153">空の <xref:System.Xml.Linq.XElement> を作成する場合は、コンストラクターにコンテンツを渡しません。</span><span class="sxs-lookup"><span data-stu-id="7d56c-153">To create an empty <xref:System.Xml.Linq.XElement>, you do not pass any content to the constructor.</span></span> <span data-ttu-id="7d56c-154">次の例では、空要素を作成します。</span><span class="sxs-lookup"><span data-stu-id="7d56c-154">The following example creates an empty element:</span></span>  
  
```csharp  
XElement n = new XElement("Customer");  
Console.WriteLine(n);  
```  
  
 <span data-ttu-id="7d56c-155">この例を実行すると、次の出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="7d56c-155">This example produces the following output:</span></span>  
  
```xml  
<Customer />  
```  
  
### <a name="attaching-vs-cloning"></a><span data-ttu-id="7d56c-156">アタッチと複製の比較</span><span class="sxs-lookup"><span data-stu-id="7d56c-156">Attaching vs. cloning</span></span>  
 <span data-ttu-id="7d56c-157">既に説明したように、<xref:System.Xml.Linq.XNode> オブジェクト (<xref:System.Xml.Linq.XElement> を含む) や <xref:System.Xml.Linq.XAttribute> オブジェクトの追加時に、新しいコンテンツに親がない場合、単にオブジェクトが XML ツリーにアタッチされます。</span><span class="sxs-lookup"><span data-stu-id="7d56c-157">As mentioned previously, when adding <xref:System.Xml.Linq.XNode> (including <xref:System.Xml.Linq.XElement>) or <xref:System.Xml.Linq.XAttribute> objects, if the new content has no parent, the objects are simply attached to the XML tree.</span></span> <span data-ttu-id="7d56c-158">新しいコンテンツに既に親があり、別の XML ツリーの一部となっている場合は、新しいコンテンツが複製され、新しく複製されたコンテンツが XML ツリーにアタッチされます。</span><span class="sxs-lookup"><span data-stu-id="7d56c-158">If the new content already is parented and is part of another XML tree, the new content is cloned, and the newly cloned content is attached to the XML tree.</span></span>  

<span data-ttu-id="7d56c-159">次の例では、親を持つ要素をツリーに追加する場合と親を持たない要素をツリーに追加する場合の動作を示します。</span><span class="sxs-lookup"><span data-stu-id="7d56c-159">The following example demonstrates the behavior when you add a parented element to a tree, and when you add an element with no parent to a tree.</span></span>

```csharp  
// Create a tree with a child element.  
XElement xmlTree1 = new XElement("Root",  
    new XElement("Child1", 1)  
);  
  
// Create an element that is not parented.  
XElement child2 = new XElement("Child2", 2);  
  
// Create a tree and add Child1 and Child2 to it.  
XElement xmlTree2 = new XElement("Root",  
    xmlTree1.Element("Child1"),  
    child2  
);  
  
// Compare Child1 identity.  
Console.WriteLine("Child1 was {0}",  
    xmlTree1.Element("Child1") == xmlTree2.Element("Child1") ?  
    "attached" : "cloned");  
  
// Compare Child2 identity.  
Console.WriteLine("Child2 was {0}",  
    child2 == xmlTree2.Element("Child2") ?  
    "attached" : "cloned");  

// The example displays the following output:  
//    Child1 was cloned  
//    Child2 was attached  
```

## <a name="see-also"></a><span data-ttu-id="7d56c-160">関連項目</span><span class="sxs-lookup"><span data-stu-id="7d56c-160">See also</span></span>

- [<span data-ttu-id="7d56c-161">XML ツリーの作成 (C#)</span><span class="sxs-lookup"><span data-stu-id="7d56c-161">Creating XML Trees (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/creating-xml-trees.md)
