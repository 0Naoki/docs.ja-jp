---
title: '方法: Blocks プロパティを介してフロー コンテンツ要素を操作する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- documents [WPF], manipulating flow content elements through Blocks property
- flow content elements [WPF], manipulating through Blocks property
- properties [WPF], Blocks [WPF], manipulating flow content elements
- Blocks property [WPF], manipulating flow content elements
ms.assetid: aeda4ece-b979-4818-a093-ef938e908751
ms.openlocfilehash: a988f47b6b147b0db285af1928a4260c5deba542
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57365855"
---
# <a name="how-to-manipulate-flow-content-elements-through-the-blocks-property"></a><span data-ttu-id="2bfc7-102">方法: Blocks プロパティを介してフロー コンテンツ要素を操作する</span><span class="sxs-lookup"><span data-stu-id="2bfc7-102">How to: Manipulate Flow Content Elements through the Blocks Property</span></span>
<span data-ttu-id="2bfc7-103">これらの例を紹介を介してフロー コンテンツ要素に対して実行できる一般的な操作の**ブロック**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="2bfc7-103">These examples demonstrate some of the more common operations that can be performed on flow content elements through the **Blocks** property.</span></span> <span data-ttu-id="2bfc7-104">このプロパティを使用して項目を追加および削除を<xref:System.Windows.Documents.BlockCollection>します。</span><span class="sxs-lookup"><span data-stu-id="2bfc7-104">This property is used to add and remove items from <xref:System.Windows.Documents.BlockCollection>.</span></span> <span data-ttu-id="2bfc7-105">フロー コンテンツ要素にその機能、**ブロック**プロパティが含まれます。</span><span class="sxs-lookup"><span data-stu-id="2bfc7-105">Flow content elements that feature a **Blocks** property include:</span></span>  
  
-   <xref:System.Windows.Documents.Figure>  
  
-   <xref:System.Windows.Documents.Floater>  
  
-   <xref:System.Windows.Documents.ListItem>  
  
-   <xref:System.Windows.Documents.Section>  
  
-   <xref:System.Windows.Documents.TableCell>  
  
 <span data-ttu-id="2bfc7-106">これらの例を使用する発生<xref:System.Windows.Documents.Section>フロー コンテンツ要素は、これらの手法はフロー コンテンツ要素のコレクションをホストするすべての要素に適用できます。</span><span class="sxs-lookup"><span data-stu-id="2bfc7-106">These examples happen to use <xref:System.Windows.Documents.Section> as the flow content element, but these techniques are applicable to all elements that host a flow content element collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2bfc7-107">例</span><span class="sxs-lookup"><span data-stu-id="2bfc7-107">Example</span></span>  
 <span data-ttu-id="2bfc7-108">次の例では、作成、新しい<xref:System.Windows.Documents.Section>しを使用して、**追加**を新しい段落を追加する方法、**セクション**内容。</span><span class="sxs-lookup"><span data-stu-id="2bfc7-108">The following example creates a new <xref:System.Windows.Documents.Section> and then uses the **Add** method to add a new Paragraph to the **Section** contents.</span></span>  
  
 [!code-csharp[FlowDocumentSnippets#_SectionBlocksAdd](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_sectionblocksadd)]
 [!code-vb[FlowDocumentSnippets#_SectionBlocksAdd](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_sectionblocksadd)]  
  
## <a name="example"></a><span data-ttu-id="2bfc7-109">例</span><span class="sxs-lookup"><span data-stu-id="2bfc7-109">Example</span></span>  
 <span data-ttu-id="2bfc7-110">次の例では、作成、新しい<xref:System.Windows.Documents.Paragraph>要素の開始位置に挿入し、<xref:System.Windows.Documents.Section>します。</span><span class="sxs-lookup"><span data-stu-id="2bfc7-110">The following example creates a new <xref:System.Windows.Documents.Paragraph> element and inserts it at the beginning of the <xref:System.Windows.Documents.Section>.</span></span>  
  
 [!code-csharp[FlowDocumentSnippets#_SectionBlocksInsert](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_sectionblocksinsert)]
 [!code-vb[FlowDocumentSnippets#_SectionBlocksInsert](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_sectionblocksinsert)]  
  
## <a name="example"></a><span data-ttu-id="2bfc7-111">例</span><span class="sxs-lookup"><span data-stu-id="2bfc7-111">Example</span></span>  
 <span data-ttu-id="2bfc7-112">次の例では、最上位レベルの数を取得します。<xref:System.Windows.Documents.Block>に含まれる要素、<xref:System.Windows.Documents.Section>します。</span><span class="sxs-lookup"><span data-stu-id="2bfc7-112">The following example gets the number of top-level <xref:System.Windows.Documents.Block> elements contained in the <xref:System.Windows.Documents.Section>.</span></span>  
  
 [!code-csharp[FlowDocumentSnippets#_SectionBlocksCount](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_sectionblockscount)]
 [!code-vb[FlowDocumentSnippets#_SectionBlocksCount](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_sectionblockscount)]  
  
## <a name="example"></a><span data-ttu-id="2bfc7-113">例</span><span class="sxs-lookup"><span data-stu-id="2bfc7-113">Example</span></span>  
 <span data-ttu-id="2bfc7-114">次の例では、削除、最終<xref:System.Windows.Documents.Block>内の要素、<xref:System.Windows.Documents.Section>します。</span><span class="sxs-lookup"><span data-stu-id="2bfc7-114">The following example deletes the last <xref:System.Windows.Documents.Block> element in the <xref:System.Windows.Documents.Section>.</span></span>  
  
 [!code-csharp[FlowDocumentSnippets#_SectionBlocksRemoveLast](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_sectionblocksremovelast)]
 [!code-vb[FlowDocumentSnippets#_SectionBlocksRemoveLast](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_sectionblocksremovelast)]  
  
## <a name="example"></a><span data-ttu-id="2bfc7-115">例</span><span class="sxs-lookup"><span data-stu-id="2bfc7-115">Example</span></span>  
 <span data-ttu-id="2bfc7-116">次の例では、すべての内容をクリア (<xref:System.Windows.Documents.Block>要素) から、<xref:System.Windows.Documents.Section>します。</span><span class="sxs-lookup"><span data-stu-id="2bfc7-116">The following example clears all of the contents (<xref:System.Windows.Documents.Block> elements) from the <xref:System.Windows.Documents.Section>.</span></span>  
  
 [!code-csharp[FlowDocumentSnippets#_SectionBlocksClear](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_sectionblocksclear)]
 [!code-vb[FlowDocumentSnippets#_SectionBlocksClear](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_sectionblocksclear)]  
  
## <a name="see-also"></a><span data-ttu-id="2bfc7-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="2bfc7-117">See also</span></span>
- <xref:System.Windows.Documents.BlockCollection>
- <xref:System.Windows.Documents.InlineCollection>
- <xref:System.Windows.Documents.ListItemCollection>
- [<span data-ttu-id="2bfc7-118">フロー ドキュメントの概要</span><span class="sxs-lookup"><span data-stu-id="2bfc7-118">Flow Document Overview</span></span>](flow-document-overview.md)
- [<span data-ttu-id="2bfc7-119">RowGroups プロパティを介してテーブルの行グループを操作する</span><span class="sxs-lookup"><span data-stu-id="2bfc7-119">Manipulate a Table's Row Groups through the RowGroups Property</span></span>](how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)
- [<span data-ttu-id="2bfc7-120">Columns プロパティによってテーブルの列を操作する</span><span class="sxs-lookup"><span data-stu-id="2bfc7-120">Manipulate a Table's Columns through the Columns Property</span></span>](how-to-manipulate-table-columns-through-the-columns-property.md)
- [<span data-ttu-id="2bfc7-121">RowGroups プロパティを介してテーブルの行グループを操作する</span><span class="sxs-lookup"><span data-stu-id="2bfc7-121">Manipulate a Table's Row Groups through the RowGroups Property</span></span>](how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)
