---
title: XML 要素リテラル (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlLiteralElement
helpviewer_keywords:
- XML element literal [Visual Basic]
- element literal [Visual Basic]
- XML literals [Visual Basic], element
ms.assetid: 95039642-7893-48b7-b23f-45a6c55d8f67
ms.openlocfilehash: 7bd47d2461ba86dfbd1d5ff5993382914116f9ba
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "58842253"
---
# <a name="xml-element-literal-visual-basic"></a><span data-ttu-id="0b763-102">XML 要素リテラル (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0b763-102">XML Element Literal (Visual Basic)</span></span>

<span data-ttu-id="0b763-103">表すリテラル、<xref:System.Xml.Linq.XElement>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="0b763-103">A literal that represents an <xref:System.Xml.Linq.XElement> object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b763-104">構文</span><span class="sxs-lookup"><span data-stu-id="0b763-104">Syntax</span></span>  
  
```xml  
<name [ attributeList ] />  
-or-  
<name [ attributeList ] > [ elementContents ] </[ name ]>  
```  
  
## <a name="parts"></a><span data-ttu-id="0b763-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="0b763-105">Parts</span></span>  
  
-   `<`  
  
     <span data-ttu-id="0b763-106">必須。</span><span class="sxs-lookup"><span data-stu-id="0b763-106">Required.</span></span> <span data-ttu-id="0b763-107">開始要素タグが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0b763-107">Opens the starting element tag.</span></span>  
  
-   `name`  
  
     <span data-ttu-id="0b763-108">必須。</span><span class="sxs-lookup"><span data-stu-id="0b763-108">Required.</span></span> <span data-ttu-id="0b763-109">要素名</span><span class="sxs-lookup"><span data-stu-id="0b763-109">Name of the element.</span></span> <span data-ttu-id="0b763-110">形式は、次のいずれかです。</span><span class="sxs-lookup"><span data-stu-id="0b763-110">The format is one of the following:</span></span>  
  
    -   <span data-ttu-id="0b763-111">要素名の形式のリテラル テキスト`[ePrefix:]eName`、場所。</span><span class="sxs-lookup"><span data-stu-id="0b763-111">Literal text for the element name, of the form `[ePrefix:]eName`, where:</span></span>  
  
        |<span data-ttu-id="0b763-112">パーツ</span><span class="sxs-lookup"><span data-stu-id="0b763-112">Part</span></span>|<span data-ttu-id="0b763-113">説明</span><span class="sxs-lookup"><span data-stu-id="0b763-113">Description</span></span>|  
        |---|---|  
        |`ePrefix`|<span data-ttu-id="0b763-114">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="0b763-114">Optional.</span></span> <span data-ttu-id="0b763-115">要素の XML 名前空間プレフィックス。</span><span class="sxs-lookup"><span data-stu-id="0b763-115">XML namespace prefix for the element.</span></span> <span data-ttu-id="0b763-116">グローバル XML 名前空間で定義されている必要があります、`Imports`ファイルまたはプロジェクト レベル、またはこの要素または親要素で定義されているローカル XML 名前空間のステートメント。</span><span class="sxs-lookup"><span data-stu-id="0b763-116">Must be a global XML namespace that is defined with an `Imports` statement in the file or at the project level, or a local XML namespace that is defined in this element or a parent element.</span></span>|  
        |`eName`|<span data-ttu-id="0b763-117">必須。</span><span class="sxs-lookup"><span data-stu-id="0b763-117">Required.</span></span> <span data-ttu-id="0b763-118">要素名</span><span class="sxs-lookup"><span data-stu-id="0b763-118">Name of the element.</span></span> <span data-ttu-id="0b763-119">形式は、次のいずれかです。</span><span class="sxs-lookup"><span data-stu-id="0b763-119">The format is one of the following:</span></span><br /><br /> <span data-ttu-id="0b763-120">リテラル テキスト。</span><span class="sxs-lookup"><span data-stu-id="0b763-120">-   Literal text.</span></span> <span data-ttu-id="0b763-121">参照してください[宣言する XML 要素と属性の名前](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)します。</span><span class="sxs-lookup"><span data-stu-id="0b763-121">See [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span><br /><span data-ttu-id="0b763-122">形式の式を埋め込み`<%= eNameExp %>`します。</span><span class="sxs-lookup"><span data-stu-id="0b763-122">-   Embedded expression of the form `<%= eNameExp %>`.</span></span> <span data-ttu-id="0b763-123">型`eNameExp`必要があります`String`または暗黙的に変換できる型<xref:System.Xml.Linq.XName>します。</span><span class="sxs-lookup"><span data-stu-id="0b763-123">The type of `eNameExp` must be `String` or a type that is implicitly convertible to <xref:System.Xml.Linq.XName>.</span></span>|  
  
    -   <span data-ttu-id="0b763-124">形式の式を埋め込む`<%= nameExp %>`します。</span><span class="sxs-lookup"><span data-stu-id="0b763-124">Embedded expression of the form `<%= nameExp %>`.</span></span> <span data-ttu-id="0b763-125">型`nameExp`あります`String`または型に暗黙的に変換<xref:System.Xml.Linq.XName>します。</span><span class="sxs-lookup"><span data-stu-id="0b763-125">The type of `nameExp` must be `String` or a type implicitly convertible to <xref:System.Xml.Linq.XName>.</span></span> <span data-ttu-id="0b763-126">埋め込み式は、要素の終了タグでは許可されません。</span><span class="sxs-lookup"><span data-stu-id="0b763-126">An embedded expression is not allowed in a closing tag of an element.</span></span>  
  
-   `attributeList`  
  
     <span data-ttu-id="0b763-127">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="0b763-127">Optional.</span></span> <span data-ttu-id="0b763-128">属性の一覧は、リテラルで宣言します。</span><span class="sxs-lookup"><span data-stu-id="0b763-128">List of attributes declared in the literal.</span></span>  
  
     `attribute [ attribute ... ]`  
  
     <span data-ttu-id="0b763-129">各`attribute`が次の構文のいずれか。</span><span class="sxs-lookup"><span data-stu-id="0b763-129">Each `attribute` has one of the following syntaxes:</span></span>  
  
    -   <span data-ttu-id="0b763-130">属性を割り当てる、フォームの`[aPrefix:]aName=aValue`、場所。</span><span class="sxs-lookup"><span data-stu-id="0b763-130">Attribute assignment, of the form `[aPrefix:]aName=aValue`, where:</span></span>  
  
        |<span data-ttu-id="0b763-131">パーツ</span><span class="sxs-lookup"><span data-stu-id="0b763-131">Part</span></span>|<span data-ttu-id="0b763-132">説明</span><span class="sxs-lookup"><span data-stu-id="0b763-132">Description</span></span>|  
        |---|---|  
        |`aPrefix`|<span data-ttu-id="0b763-133">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="0b763-133">Optional.</span></span> <span data-ttu-id="0b763-134">属性の XML 名前空間プレフィックス。</span><span class="sxs-lookup"><span data-stu-id="0b763-134">XML namespace prefix for the attribute.</span></span> <span data-ttu-id="0b763-135">グローバル XML 名前空間で定義されている必要があります、`Imports`ステートメント、またはこの要素または親要素で定義されているローカル XML 名前空間。</span><span class="sxs-lookup"><span data-stu-id="0b763-135">Must be a global XML namespace that is defined with an `Imports` statement, or a local XML namespace that is defined in this element or a parent element.</span></span>|  
        |`aName`|<span data-ttu-id="0b763-136">必須。</span><span class="sxs-lookup"><span data-stu-id="0b763-136">Required.</span></span> <span data-ttu-id="0b763-137">属性の名前。</span><span class="sxs-lookup"><span data-stu-id="0b763-137">Name of the attribute.</span></span> <span data-ttu-id="0b763-138">形式は、次のいずれかです。</span><span class="sxs-lookup"><span data-stu-id="0b763-138">The format is one of the following:</span></span><br /><br /> <span data-ttu-id="0b763-139">リテラル テキスト。</span><span class="sxs-lookup"><span data-stu-id="0b763-139">-   Literal text.</span></span> <span data-ttu-id="0b763-140">参照してください[宣言する XML 要素と属性の名前](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)します。</span><span class="sxs-lookup"><span data-stu-id="0b763-140">See [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span><br /><span data-ttu-id="0b763-141">形式の式を埋め込み`<%= aNameExp %>`します。</span><span class="sxs-lookup"><span data-stu-id="0b763-141">-   Embedded expression of the form `<%= aNameExp %>`.</span></span> <span data-ttu-id="0b763-142">型`aNameExp`必要があります`String`または暗黙的に変換できる型<xref:System.Xml.Linq.XName>します。</span><span class="sxs-lookup"><span data-stu-id="0b763-142">The type of `aNameExp` must be `String` or a type that is implicitly convertible to <xref:System.Xml.Linq.XName>.</span></span>|  
        |`aValue`|<span data-ttu-id="0b763-143">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="0b763-143">Optional.</span></span> <span data-ttu-id="0b763-144">属性の値。</span><span class="sxs-lookup"><span data-stu-id="0b763-144">Value of the attribute.</span></span> <span data-ttu-id="0b763-145">形式は、次のいずれかです。</span><span class="sxs-lookup"><span data-stu-id="0b763-145">The format is one of the following:</span></span><br /><br /> <span data-ttu-id="0b763-146">、引用符で囲まれているリテラル テキスト。</span><span class="sxs-lookup"><span data-stu-id="0b763-146">-   Literal text, enclosed in quotation marks.</span></span><br /><span data-ttu-id="0b763-147">形式の式を埋め込み`<%= aValueExp %>`します。</span><span class="sxs-lookup"><span data-stu-id="0b763-147">-   Embedded expression of the form `<%= aValueExp %>`.</span></span> <span data-ttu-id="0b763-148">任意の型を許可します。</span><span class="sxs-lookup"><span data-stu-id="0b763-148">Any type is allowed.</span></span>|  
  
    -   <span data-ttu-id="0b763-149">形式の式を埋め込む`<%= aExp %>`します。</span><span class="sxs-lookup"><span data-stu-id="0b763-149">Embedded expression of the form `<%= aExp %>`.</span></span>  
  
-   `/>`  
  
     <span data-ttu-id="0b763-150">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="0b763-150">Optional.</span></span> <span data-ttu-id="0b763-151">要素がコンテンツのない、空の要素であることを示します。</span><span class="sxs-lookup"><span data-stu-id="0b763-151">Indicates that the element is an empty element, without content.</span></span>  
  
-   `>`  
  
     <span data-ttu-id="0b763-152">必須。</span><span class="sxs-lookup"><span data-stu-id="0b763-152">Required.</span></span> <span data-ttu-id="0b763-153">以降、または空要素タグを終了します。</span><span class="sxs-lookup"><span data-stu-id="0b763-153">Ends the beginning or empty element tag.</span></span>  
  
-   `elementContents`  
  
     <span data-ttu-id="0b763-154">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="0b763-154">Optional.</span></span> <span data-ttu-id="0b763-155">要素のコンテンツ。</span><span class="sxs-lookup"><span data-stu-id="0b763-155">Content of the element.</span></span>  
  
     `content [ content ... ]`  
  
     <span data-ttu-id="0b763-156">各`content`次のいずれかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="0b763-156">Each `content` can be one of the following:</span></span>  
  
    -   <span data-ttu-id="0b763-157">リテラル テキスト。</span><span class="sxs-lookup"><span data-stu-id="0b763-157">Literal text.</span></span> <span data-ttu-id="0b763-158">内のすべての空白`elementContents`任意のリテラル テキストがある場合に重要になります。</span><span class="sxs-lookup"><span data-stu-id="0b763-158">All the white space in `elementContents` becomes significant if there is any literal text.</span></span>  
  
    -   <span data-ttu-id="0b763-159">形式の式を埋め込む`<%= contentExp %>`します。</span><span class="sxs-lookup"><span data-stu-id="0b763-159">Embedded expression of the form `<%= contentExp %>`.</span></span>  
  
    -   <span data-ttu-id="0b763-160">XML 要素リテラル。</span><span class="sxs-lookup"><span data-stu-id="0b763-160">XML element literal.</span></span>  
  
    -   <span data-ttu-id="0b763-161">XML コメント リテラルです。</span><span class="sxs-lookup"><span data-stu-id="0b763-161">XML comment literal.</span></span> <span data-ttu-id="0b763-162">参照してください[XML コメント リテラル](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md)します。</span><span class="sxs-lookup"><span data-stu-id="0b763-162">See [XML Comment Literal](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md).</span></span>  
  
    -   <span data-ttu-id="0b763-163">XML 処理命令リテラル。</span><span class="sxs-lookup"><span data-stu-id="0b763-163">XML processing instruction literal.</span></span> <span data-ttu-id="0b763-164">参照してください[XML 処理命令リテラル](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md)します。</span><span class="sxs-lookup"><span data-stu-id="0b763-164">See [XML Processing Instruction Literal](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md).</span></span>  
  
    -   <span data-ttu-id="0b763-165">XML CDATA リテラル。</span><span class="sxs-lookup"><span data-stu-id="0b763-165">XML CDATA literal.</span></span> <span data-ttu-id="0b763-166">参照してください[XML CDATA リテラル](../../../visual-basic/language-reference/xml-literals/xml-cdata-literal.md)します。</span><span class="sxs-lookup"><span data-stu-id="0b763-166">See [XML CDATA Literal](../../../visual-basic/language-reference/xml-literals/xml-cdata-literal.md).</span></span>  
  
-   `</[name]>`  
  
     <span data-ttu-id="0b763-167">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="0b763-167">Optional.</span></span> <span data-ttu-id="0b763-168">要素の終了タグを表します。</span><span class="sxs-lookup"><span data-stu-id="0b763-168">Represents the closing tag for the element.</span></span> <span data-ttu-id="0b763-169">省略可能な`name`埋め込み式の結果がある場合に、パラメーターは使用できません。</span><span class="sxs-lookup"><span data-stu-id="0b763-169">The optional `name` parameter is not allowed when it is the result of an embedded expression.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0b763-170">戻り値</span><span class="sxs-lookup"><span data-stu-id="0b763-170">Return Value</span></span>  
 <span data-ttu-id="0b763-171"><xref:System.Xml.Linq.XElement> オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="0b763-171">An <xref:System.Xml.Linq.XElement> object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0b763-172">Remarks</span><span class="sxs-lookup"><span data-stu-id="0b763-172">Remarks</span></span>  
 <span data-ttu-id="0b763-173">作成する XML 要素リテラルの構文を使用する<xref:System.Xml.Linq.XElement>コード内のオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="0b763-173">You can use the XML element literal syntax to create <xref:System.Xml.Linq.XElement> objects in your code.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0b763-174">XML リテラルは、行継続文字を使用せず複数の行にまたがることができます。</span><span class="sxs-lookup"><span data-stu-id="0b763-174">An XML literal can span multiple lines without using line continuation characters.</span></span> <span data-ttu-id="0b763-175">この機能を使用すると、XML ドキュメントから内容をコピーして、Visual Basic プログラムに直接貼り付けることができます。</span><span class="sxs-lookup"><span data-stu-id="0b763-175">This feature enables you to copy content from an XML document and paste it directly into a Visual Basic program.</span></span>  
  
 <span data-ttu-id="0b763-176">埋め込み式形式の`<%= exp %>`XML 要素リテラルに動的な情報を追加することを有効にします。</span><span class="sxs-lookup"><span data-stu-id="0b763-176">Embedded expressions of the form `<%= exp %>` enable you to add dynamic information to an XML element literal.</span></span> <span data-ttu-id="0b763-177">詳細については、次を参照してください。 [XML での埋め込み式](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)します。</span><span class="sxs-lookup"><span data-stu-id="0b763-177">For more information, see [Embedded Expressions in XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).</span></span>  
  
 <span data-ttu-id="0b763-178">Visual Basic コンパイラへの呼び出しにリテラル XML 要素に変換して、<xref:System.Xml.Linq.XElement.%23ctor%2A>コンス トラクターおよび、必要な場合、<xref:System.Xml.Linq.XAttribute.%23ctor%2A>コンス トラクター。</span><span class="sxs-lookup"><span data-stu-id="0b763-178">The Visual Basic compiler converts the XML element literal into calls to the <xref:System.Xml.Linq.XElement.%23ctor%2A> constructor and, if it is required, the <xref:System.Xml.Linq.XAttribute.%23ctor%2A> constructor.</span></span>  
  
## <a name="xml-namespaces"></a><span data-ttu-id="0b763-179">XML 名前空間</span><span class="sxs-lookup"><span data-stu-id="0b763-179">XML Namespaces</span></span>  
 <span data-ttu-id="0b763-180">XML 名前空間プレフィックスは、コードで何度も同じ名前空間の要素で XML リテラルを作成する必要がある場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="0b763-180">XML namespace prefixes are useful when you have to create XML literals with elements from the same namespace many times in code.</span></span> <span data-ttu-id="0b763-181">使用して定義するグローバルの XML 名前空間プレフィックスを使用することができます、`Imports`ステートメント、またはローカルのプレフィックスは、使用して定義する、`xmlns:xmlPrefix="xmlNamespace"`属性構文。</span><span class="sxs-lookup"><span data-stu-id="0b763-181">You can use global XML namespace prefixes, which you define by using the `Imports` statement, or local prefixes, which you define by using the `xmlns:xmlPrefix="xmlNamespace"` attribute syntax.</span></span> <span data-ttu-id="0b763-182">詳細については、次を参照してください。 [Imports ステートメント (XML Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)します。</span><span class="sxs-lookup"><span data-stu-id="0b763-182">For more information, see [Imports Statement (XML Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).</span></span>  
  
 <span data-ttu-id="0b763-183">XML 名前空間のスコープの規則に従ってローカル プレフィックスはグローバル プレフィックスに優先します。</span><span class="sxs-lookup"><span data-stu-id="0b763-183">In accordance with the scoping rules for XML namespaces, local prefixes take precedence over global prefixes.</span></span> <span data-ttu-id="0b763-184">ただし、XML リテラルには、XML 名前空間が定義されている場合はその名前空間は埋め込み式の中で表示される式を使用できません。</span><span class="sxs-lookup"><span data-stu-id="0b763-184">However, if an XML literal defines an XML namespace, that namespace is not available to expressions that appear in an embedded expression.</span></span> <span data-ttu-id="0b763-185">埋め込み式は、グローバルの XML 名前空間のみにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="0b763-185">The embedded expression can access only the global XML namespace.</span></span>  
  
 <span data-ttu-id="0b763-186">Visual Basic コンパイラでは、各グローバル生成されたコード内の 1 つのローカルの名前空間定義への XML リテラルで使用される XML 名前空間に変換します。</span><span class="sxs-lookup"><span data-stu-id="0b763-186">The Visual Basic compiler converts each global XML namespace that is used by an XML literal into a one local namespace definition in the generated code.</span></span> <span data-ttu-id="0b763-187">使用されていないグローバルの XML 名前空間は、生成されたコードでは表示されません。</span><span class="sxs-lookup"><span data-stu-id="0b763-187">Global XML namespaces that are not used do not appear in the generated code.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0b763-188">例</span><span class="sxs-lookup"><span data-stu-id="0b763-188">Example</span></span>  
 <span data-ttu-id="0b763-189">次の例では、2 つの入れ子になった空の要素を含む単純な XML 要素を作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="0b763-189">The following example shows how to create a simple XML element that has two nested empty elements.</span></span>  
  
 [!code-vb[VbXMLSamples#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples9.vb#20)]  
  
 <span data-ttu-id="0b763-190">例では、次のテキストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0b763-190">The example displays the following text.</span></span> <span data-ttu-id="0b763-191">リテラルが空の要素の構造を維持することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="0b763-191">Notice that the literal preserves the structure of the empty elements.</span></span>  
  
```xml  
<outer>  
  <inner1></inner1>  
  <inner2 />  
</outer>  
```  
  
## <a name="example"></a><span data-ttu-id="0b763-192">例</span><span class="sxs-lookup"><span data-stu-id="0b763-192">Example</span></span>  
 <span data-ttu-id="0b763-193">次の例は、組み込み式を使用して、要素の名前を指定し、属性を作成する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="0b763-193">The following example shows how to use embedded expressions to name an element and create attributes.</span></span>  
  
 [!code-vb[VbXMLSamples#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples9.vb#21)]  
  
 <span data-ttu-id="0b763-194">このコードを実行すると、次のテキストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0b763-194">This code displays the following text:</span></span>  
  
```xml  
<book isbn="1234" author="My Author" year="1999" title="My Book" />  
```  
  
## <a name="example"></a><span data-ttu-id="0b763-195">例</span><span class="sxs-lookup"><span data-stu-id="0b763-195">Example</span></span>  
 <span data-ttu-id="0b763-196">次の例では、`ns` を名前空間プレフィックスとして宣言します。</span><span class="sxs-lookup"><span data-stu-id="0b763-196">The following example declares `ns` as an XML namespace prefix.</span></span> <span data-ttu-id="0b763-197">XML リテラルを作成する名前空間のプレフィックスを使用し、要素の最終的なフォームを表示します。</span><span class="sxs-lookup"><span data-stu-id="0b763-197">It then uses the prefix of the namespace to create an XML literal and displays the element's final form.</span></span>  
  
 [!code-vb[VbXMLSamples#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples10.vb#22)]  
  
 <span data-ttu-id="0b763-198">このコードを実行すると、次のテキストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0b763-198">This code displays the following text:</span></span>  
  
```xml  
<ns:outer xmlns:ns="http://SomeNamespace">  
  <ns:middle xmlns:ns="http://NewNamespace">  
    <ns:inner1 />  
    <inner2 xmlns="http://SomeNamespace" />  
  </ns:middle>  
</ns:outer>  
```  
  
 <span data-ttu-id="0b763-199">コンパイラが XML 名前空間のプレフィックス定義にグローバル XML 名前空間のプレフィックスを変換することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="0b763-199">Notice that the compiler converted the prefix of the global XML namespace into a prefix definition for the XML namespace.</span></span> <span data-ttu-id="0b763-200">\<Ns:middle > 要素の XML 名前空間プレフィックスを再定義、 \<ns:inner1 > 要素。</span><span class="sxs-lookup"><span data-stu-id="0b763-200">The \<ns:middle> element redefines the XML namespace prefix for the \<ns:inner1> element.</span></span> <span data-ttu-id="0b763-201">ただし、 \<ns:inner2 > 要素で定義された名前空間を使用して、`Imports`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="0b763-201">However, the \<ns:inner2> element uses the namespace defined by the `Imports` statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b763-202">関連項目</span><span class="sxs-lookup"><span data-stu-id="0b763-202">See also</span></span>

- <xref:System.Xml.Linq.XElement>
- [<span data-ttu-id="0b763-203">宣言する XML 要素と属性の名前</span><span class="sxs-lookup"><span data-stu-id="0b763-203">Names of Declared XML Elements and Attributes</span></span>](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
- [<span data-ttu-id="0b763-204">XML コメント リテラル</span><span class="sxs-lookup"><span data-stu-id="0b763-204">XML Comment Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md)
- [<span data-ttu-id="0b763-205">XML CDATA リテラル</span><span class="sxs-lookup"><span data-stu-id="0b763-205">XML CDATA Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-cdata-literal.md)
- [<span data-ttu-id="0b763-206">XML リテラル</span><span class="sxs-lookup"><span data-stu-id="0b763-206">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)
- [<span data-ttu-id="0b763-207">Visual Basic での XML の作成</span><span class="sxs-lookup"><span data-stu-id="0b763-207">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [<span data-ttu-id="0b763-208">XML での埋め込み式</span><span class="sxs-lookup"><span data-stu-id="0b763-208">Embedded Expressions in XML</span></span>](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)
- [<span data-ttu-id="0b763-209">Imports ステートメント (XML 名前空間)</span><span class="sxs-lookup"><span data-stu-id="0b763-209">Imports Statement (XML Namespace)</span></span>](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)
