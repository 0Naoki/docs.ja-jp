---
title: '方法: XDocument、XElement、または LINQ for XML クエリの結果にバインドする'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], binding to XDocument
- data binding [WPF], binding to XElement
ms.assetid: 6a629a49-fe1c-465d-b76a-3dcbf4307b64
ms.openlocfilehash: 67d81c02ca7a207a48190a3bf09b6ab5dbec17de
ms.sourcegitcommit: 8f95d3a37e591963ebbb9af6e90686fd5f3b8707
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2019
ms.locfileid: "56746404"
---
# <a name="how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results"></a><span data-ttu-id="e8fde-102">方法: XDocument、XElement、または LINQ for XML クエリの結果にバインドする</span><span class="sxs-lookup"><span data-stu-id="e8fde-102">How to: Bind to XDocument, XElement, or LINQ for XML Query Results</span></span>
<span data-ttu-id="e8fde-103">この例では、XML データの連結、<xref:System.Windows.Controls.ItemsControl>を使用して<xref:System.Xml.Linq.XDocument>します。</span><span class="sxs-lookup"><span data-stu-id="e8fde-103">This example demonstrates how to bind XML data to an <xref:System.Windows.Controls.ItemsControl> using <xref:System.Xml.Linq.XDocument>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e8fde-104">例</span><span class="sxs-lookup"><span data-stu-id="e8fde-104">Example</span></span>  
 <span data-ttu-id="e8fde-105">次の XAML コードを定義、<xref:System.Windows.Controls.ItemsControl>型のデータのデータ テンプレートが含まれています`Planet`で、 `http://planetsNS` XML 名前空間。</span><span class="sxs-lookup"><span data-stu-id="e8fde-105">The following XAML code defines an <xref:System.Windows.Controls.ItemsControl> and includes a data template for data of type `Planet` in the `http://planetsNS` XML namespace.</span></span> <span data-ttu-id="e8fde-106">名前空間を占有する XML データ型では、名前空間をかっこで囲んで含める必要があります。また、その XML データ型が、XAML マークアップ拡張機能が出現する可能性がある場所に出現する場合は、名前空間の前に、かっこのエスケープ シーケンスを使用して指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e8fde-106">An XML data type that occupies a namespace must include the namespace in braces, and if it appears where a XAML markup extension could appear, it must precede the namespace with a brace escape sequence.</span></span> <span data-ttu-id="e8fde-107">このコードに対応する動的プロパティにバインド、<xref:System.Xml.Linq.XContainer.Element%2A>と<xref:System.Xml.Linq.XElement.Attribute%2A>のメソッド、<xref:System.Xml.Linq.XElement>クラス。</span><span class="sxs-lookup"><span data-stu-id="e8fde-107">This code binds to dynamic properties that correspond to the <xref:System.Xml.Linq.XContainer.Element%2A> and <xref:System.Xml.Linq.XElement.Attribute%2A> methods of the <xref:System.Xml.Linq.XElement> class.</span></span> <span data-ttu-id="e8fde-108">動的プロパティによって、XAML がこれらのメソッドの名前を共有する動的プロパティにバインドできます。</span><span class="sxs-lookup"><span data-stu-id="e8fde-108">Dynamic properties enable XAML to bind to dynamic properties that share the names of methods.</span></span> <span data-ttu-id="e8fde-109">詳細については、「[LINQ to XML の動的プロパティ](/visualstudio/designers/linq-to-xml-dynamic-properties)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e8fde-109">To learn more, see [LINQ to XML Dynamic Properties](/visualstudio/designers/linq-to-xml-dynamic-properties).</span></span> <span data-ttu-id="e8fde-110">XML 用の既定の名前空間宣言が属性名には適用されないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="e8fde-110">Notice how the default namespace declaration for the XML does not apply to attribute names.</span></span>  
  
 [!code-xaml[XLinqExample#StackPanelResources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml#stackpanelresources)]  
[!code-xaml[XLinqExample#ItemsControl](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml#itemscontrol)]  
  
 <span data-ttu-id="e8fde-111">次の c# のコード呼び出し<xref:System.Xml.Linq.XDocument.Load%2A>という名前の要素のすべてのサブ要素をスタック パネルのデータ コンテキストを設定および`SolarSystemPlanets`で、 `http://planetsNS` XML 名前空間。</span><span class="sxs-lookup"><span data-stu-id="e8fde-111">The following C# code calls <xref:System.Xml.Linq.XDocument.Load%2A> and sets the stack panel data context to all subelements of the element named `SolarSystemPlanets` in the `http://planetsNS` XML namespace.</span></span>  
  
 [!code-csharp[XLinqExample#LoadDCFromFile](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml.cs#loaddcfromfile)]
 [!code-vb[XLinqExample#LoadDCFromFile](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/XLinqExample/visualbasic/window1.xaml.vb#loaddcfromfile)]  
  
 <span data-ttu-id="e8fde-112">使用して XAML リソースとして XML データを格納できる<xref:System.Windows.Data.ObjectDataProvider>します。</span><span class="sxs-lookup"><span data-stu-id="e8fde-112">XML data can be stored as a XAML resource using <xref:System.Windows.Data.ObjectDataProvider>.</span></span> <span data-ttu-id="e8fde-113">完全な例を参照してください。 [L2DBForm.xaml ソース コード](/visualstudio/designers/l2dbform-xaml-source-code)します。</span><span class="sxs-lookup"><span data-stu-id="e8fde-113">For a complete example, see  [L2DBForm.xaml source code](/visualstudio/designers/l2dbform-xaml-source-code).</span></span> <span data-ttu-id="e8fde-114">次の例は、コードでデータ コンテキストをオブジェクト リソースに設定する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="e8fde-114">The following sample shows how code can set the data context to an object resource.</span></span>  
  
 [!code-csharp[XLinqExample#LoadDCFromXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml.cs#loaddcfromxaml)]
 [!code-vb[XLinqExample#LoadDCFromXAML](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/XLinqExample/visualbasic/window1.xaml.vb#loaddcfromxaml)]  
  
 <span data-ttu-id="e8fde-115">マップされる動的プロパティ<xref:System.Xml.Linq.XContainer.Element%2A>と<xref:System.Xml.Linq.XElement.Attribute%2A>XAML 内の柔軟性を提供します。</span><span class="sxs-lookup"><span data-stu-id="e8fde-115">The dynamic properties that map to <xref:System.Xml.Linq.XContainer.Element%2A> and <xref:System.Xml.Linq.XElement.Attribute%2A> provide flexibility within XAML.</span></span> <span data-ttu-id="e8fde-116">コードを LINQ for XML クエリの結果にバインドすることもできます。</span><span class="sxs-lookup"><span data-stu-id="e8fde-116">Your code can also bind to the results of a LINQ for XML query.</span></span> <span data-ttu-id="e8fde-117">この例は、要素の値によって並べられたクエリ結果にバインドします。</span><span class="sxs-lookup"><span data-stu-id="e8fde-117">This example binds to query results ordered by an element value.</span></span>  
  
 [!code-csharp[XLinqExample#BindToResults](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml.cs#bindtoresults)]
 [!code-vb[XLinqExample#BindToResults](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/XLinqExample/visualbasic/window1.xaml.vb#bindtoresults)]  
  
## <a name="see-also"></a><span data-ttu-id="e8fde-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="e8fde-118">See also</span></span>
- [<span data-ttu-id="e8fde-119">バインディング ソースの概要</span><span class="sxs-lookup"><span data-stu-id="e8fde-119">Binding Sources Overview</span></span>](../../../../docs/framework/wpf/data/binding-sources-overview.md)
- [<span data-ttu-id="e8fde-120">LINQ to XML による WPF のデータ バインディングの概要</span><span class="sxs-lookup"><span data-stu-id="e8fde-120">WPF Data Binding with LINQ to XML Overview</span></span>](/visualstudio/designers/wpf-data-binding-with-linq-to-xml-overview)
- [<span data-ttu-id="e8fde-121">LINQ to XML を使用した WPF のデータ バインディングの例</span><span class="sxs-lookup"><span data-stu-id="e8fde-121">WPF Data Binding Using LINQ to XML Example</span></span>](/visualstudio/designers/wpf-data-binding-using-linq-to-xml-example)
- [<span data-ttu-id="e8fde-122">LINQ to XML の動的プロパティ</span><span class="sxs-lookup"><span data-stu-id="e8fde-122">LINQ to XML Dynamic Properties</span></span>](/visualstudio/designers/linq-to-xml-dynamic-properties)
