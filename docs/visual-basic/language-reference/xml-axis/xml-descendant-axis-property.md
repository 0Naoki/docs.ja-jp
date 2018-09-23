---
title: XML 子孫軸プロパティ (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlPropertyDescendantsAxis
helpviewer_keywords:
- Visual Basic code, accessing XML
- XML descendant axis property [Visual Basic]
- descendant axis property [Visual Baisc]
- XML axis [Visual Basic], descendant
- XML [Visual Basic], accessing
ms.assetid: a178f85b-5d54-438f-8479-40b62af6fe76
ms.openlocfilehash: 6040401ce3e98c835677be3c4cc7698013348f37
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2018
ms.locfileid: "46703779"
---
# <a name="xml-descendant-axis-property-visual-basic"></a><span data-ttu-id="51f13-102">XML 子孫軸プロパティ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="51f13-102">XML Descendant Axis Property (Visual Basic)</span></span>
<span data-ttu-id="51f13-103">次の子孫にアクセスできます。<xref:System.Xml.Linq.XElement>オブジェクト、<xref:System.Xml.Linq.XDocument>オブジェクト、コレクションの<xref:System.Xml.Linq.XElement>オブジェクト、または一連の<xref:System.Xml.Linq.XDocument>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="51f13-103">Provides access to the descendants of the following: an <xref:System.Xml.Linq.XElement> object, an <xref:System.Xml.Linq.XDocument> object, a collection of <xref:System.Xml.Linq.XElement> objects, or a collection of <xref:System.Xml.Linq.XDocument> objects.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51f13-104">構文</span><span class="sxs-lookup"><span data-stu-id="51f13-104">Syntax</span></span>  
  
```  
object...<descendant>  
```  
  
## <a name="parts"></a><span data-ttu-id="51f13-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="51f13-105">Parts</span></span>  
 `object`  
 <span data-ttu-id="51f13-106">必須。</span><span class="sxs-lookup"><span data-stu-id="51f13-106">Required.</span></span> <span data-ttu-id="51f13-107"><xref:System.Xml.Linq.XElement> オブジェクト、<xref:System.Xml.Linq.XDocument> オブジェクト、<xref:System.Xml.Linq.XElement> オブジェクトのコレクション、または <xref:System.Xml.Linq.XDocument> オブジェクトのコレクションです。</span><span class="sxs-lookup"><span data-stu-id="51f13-107">An <xref:System.Xml.Linq.XElement> object, an <xref:System.Xml.Linq.XDocument> object, a collection of <xref:System.Xml.Linq.XElement> objects, or a collection of <xref:System.Xml.Linq.XDocument> objects.</span></span>  
  
 <span data-ttu-id="51f13-108">...<</span><span class="sxs-lookup"><span data-stu-id="51f13-108">...<</span></span>  
 <span data-ttu-id="51f13-109">必須。</span><span class="sxs-lookup"><span data-stu-id="51f13-109">Required.</span></span> <span data-ttu-id="51f13-110">子孫軸プロパティの開始を示します。</span><span class="sxs-lookup"><span data-stu-id="51f13-110">Denotes the start of a descendant axis property.</span></span>  
  
 `descendant`  
 <span data-ttu-id="51f13-111">必須。</span><span class="sxs-lookup"><span data-stu-id="51f13-111">Required.</span></span> <span data-ttu-id="51f13-112">フォームにアクセスする子孫ノードの名前 [`prefix``:`]`name`します。</span><span class="sxs-lookup"><span data-stu-id="51f13-112">Name of the descendant nodes to access, of the form [`prefix``:`]`name`.</span></span>  
  
|<span data-ttu-id="51f13-113">パーツ</span><span class="sxs-lookup"><span data-stu-id="51f13-113">Part</span></span>|<span data-ttu-id="51f13-114">説明</span><span class="sxs-lookup"><span data-stu-id="51f13-114">Description</span></span>|  
|----------|-----------------|  
|`prefix`|<span data-ttu-id="51f13-115">任意。</span><span class="sxs-lookup"><span data-stu-id="51f13-115">Optional.</span></span> <span data-ttu-id="51f13-116">子孫ノードの XML 名前空間プレフィックス。</span><span class="sxs-lookup"><span data-stu-id="51f13-116">XML namespace prefix for the descendant node.</span></span> <span data-ttu-id="51f13-117">使用して定義されているグローバル XML 名前空間にある必要があります、`Imports`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="51f13-117">Must be a global XML namespace that is defined by using an `Imports` statement.</span></span>|  
|`name`|<span data-ttu-id="51f13-118">必須。</span><span class="sxs-lookup"><span data-stu-id="51f13-118">Required.</span></span> <span data-ttu-id="51f13-119">子孫ノードのローカル名。</span><span class="sxs-lookup"><span data-stu-id="51f13-119">Local name of the descendant node.</span></span> <span data-ttu-id="51f13-120">参照してください[宣言する XML 要素と属性の名前](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)します。</span><span class="sxs-lookup"><span data-stu-id="51f13-120">See [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span>|  
  
 \>  
 <span data-ttu-id="51f13-121">必須。</span><span class="sxs-lookup"><span data-stu-id="51f13-121">Required.</span></span> <span data-ttu-id="51f13-122">子孫軸プロパティの終了を示します。</span><span class="sxs-lookup"><span data-stu-id="51f13-122">Denotes the end of a descendant axis property.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="51f13-123">戻り値</span><span class="sxs-lookup"><span data-stu-id="51f13-123">Return Value</span></span>  
 <span data-ttu-id="51f13-124"><xref:System.Xml.Linq.XElement> オブジェクトのコレクション。</span><span class="sxs-lookup"><span data-stu-id="51f13-124">A collection of <xref:System.Xml.Linq.XElement> objects.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="51f13-125">Remarks</span><span class="sxs-lookup"><span data-stu-id="51f13-125">Remarks</span></span>  
 <span data-ttu-id="51f13-126">XML 子孫軸プロパティを使用して情報を取得する子孫ノードにアクセスすることができます、<xref:System.Xml.Linq.XElement>または<xref:System.Xml.Linq.XDocument>オブジェクトのコレクションから、または<xref:System.Xml.Linq.XElement>または<xref:System.Xml.Linq.XDocument>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="51f13-126">You can use an XML descendant axis property to access descendant nodes by name from an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> object, or from a collection of <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> objects.</span></span> <span data-ttu-id="51f13-127">XML を使用して、`Value`返されたコレクション内の最初の子孫ノードの値にアクセスするプロパティ。</span><span class="sxs-lookup"><span data-stu-id="51f13-127">Use the XML `Value` property to access the value of the first descendant node in the returned collection.</span></span> <span data-ttu-id="51f13-128">詳細については、次を参照してください。 [XML Value プロパティ](../../../visual-basic/language-reference/xml-axis/xml-value-property.md)します。</span><span class="sxs-lookup"><span data-stu-id="51f13-128">For more information, see [XML Value Property](../../../visual-basic/language-reference/xml-axis/xml-value-property.md).</span></span>  
  
 <span data-ttu-id="51f13-129">Visual Basic コンパイラでは、descendant 軸のプロパティへの呼び出しに変換します、<xref:System.Xml.Linq.XContainer.Descendants%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="51f13-129">The Visual Basic compiler converts descendant axis properties into calls to the <xref:System.Xml.Linq.XContainer.Descendants%2A> method.</span></span>  
  
## <a name="xml-namespaces"></a><span data-ttu-id="51f13-130">XML 名前空間</span><span class="sxs-lookup"><span data-stu-id="51f13-130">XML Namespaces</span></span>  
 <span data-ttu-id="51f13-131">Descendant 軸のプロパティの名前をグローバルに宣言されている XML 名前空間のみを使用できます、`Imports`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="51f13-131">The name in a descendant axis property can use only XML namespaces declared globally with the `Imports` statement.</span></span> <span data-ttu-id="51f13-132">XML 要素リテラル内でローカルに宣言されている XML 名前空間は使用できません。</span><span class="sxs-lookup"><span data-stu-id="51f13-132">It cannot use XML namespaces declared locally within XML element literals.</span></span> <span data-ttu-id="51f13-133">詳細については、次を参照してください。 [Imports ステートメント (XML Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)します。</span><span class="sxs-lookup"><span data-stu-id="51f13-133">For more information, see [Imports Statement (XML Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="51f13-134">例</span><span class="sxs-lookup"><span data-stu-id="51f13-134">Example</span></span>  
 <span data-ttu-id="51f13-135">次の例は、という名前の最初の子孫ノードの値にアクセスする方法を示しています。`name`という名前のすべての子孫ノードの値と`phone`から、`contacts`オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="51f13-135">The following example shows how to access the value of the first descendant node named `name` and the values of all descendant nodes named `phone` from the `contacts` object.</span></span>  
  
 [!code-vb[VbXMLSamples#25](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-descendant-axis-property_1.vb)]  
  
 <span data-ttu-id="51f13-136">このコードを実行すると、次のテキストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="51f13-136">This code displays the following text:</span></span>  
  
 `Name: Patrick Hines`  
  
 `Home Phone = 206-555-0144`  
  
## <a name="example"></a><span data-ttu-id="51f13-137">例</span><span class="sxs-lookup"><span data-stu-id="51f13-137">Example</span></span>  
 <span data-ttu-id="51f13-138">次の例では、`ns` を名前空間プレフィックスとして宣言します。</span><span class="sxs-lookup"><span data-stu-id="51f13-138">The following example declares `ns` as an XML namespace prefix.</span></span> <span data-ttu-id="51f13-139">XML リテラルを作成し、修飾名を持つ最初の子ノードの値にアクセスする次の名前空間のプレフィックスを使用して`ns:name`します。</span><span class="sxs-lookup"><span data-stu-id="51f13-139">It then uses the prefix of the namespace to create an XML literal and access the value of the first child node with the qualified name `ns:name`.</span></span>  
  
 [!code-vb[VbXMLSamples#26](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-descendant-axis-property_2.vb)]  
  
 <span data-ttu-id="51f13-140">このコードを実行すると、次のテキストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="51f13-140">This code displays the following text:</span></span>  
  
 `Name: Patrick Hines`  
  
## <a name="see-also"></a><span data-ttu-id="51f13-141">関連項目</span><span class="sxs-lookup"><span data-stu-id="51f13-141">See Also</span></span>  
 <xref:System.Xml.Linq.XElement>  
 [<span data-ttu-id="51f13-142">XML 軸プロパティ</span><span class="sxs-lookup"><span data-stu-id="51f13-142">XML Axis Properties</span></span>](../../../visual-basic/language-reference/xml-axis/index.md)  
 [<span data-ttu-id="51f13-143">XML リテラル</span><span class="sxs-lookup"><span data-stu-id="51f13-143">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)  
 [<span data-ttu-id="51f13-144">Visual Basic での XML の作成</span><span class="sxs-lookup"><span data-stu-id="51f13-144">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 [<span data-ttu-id="51f13-145">宣言する XML 要素と属性の名前</span><span class="sxs-lookup"><span data-stu-id="51f13-145">Names of Declared XML Elements and Attributes</span></span>](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
