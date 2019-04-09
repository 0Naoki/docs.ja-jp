---
title: '方法: RichTextBox からテキスト コンテンツを抽出する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text content [WPF], extracting
- RichTextBox control [WPF], extracting text content
- content [WPF], extracting
- extracting text content [WPF]
ms.assetid: f13c093f-1a05-45b3-ac8f-c9ea5e4a11c5
ms.openlocfilehash: 220da59ec893528c99014e9ec95fb185c461b291
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59086118"
---
# <a name="how-to-extract-the-text-content-from-a-richtextbox"></a><span data-ttu-id="51489-102">方法: RichTextBox からテキスト コンテンツを抽出する</span><span class="sxs-lookup"><span data-stu-id="51489-102">How to: Extract the Text Content from a RichTextBox</span></span>
<span data-ttu-id="51489-103">この例の内容を抽出する方法を示しています、<xref:System.Windows.Controls.RichTextBox>プレーン テキストとして。</span><span class="sxs-lookup"><span data-stu-id="51489-103">This example shows how to extract the contents of a <xref:System.Windows.Controls.RichTextBox> as plain text.</span></span>  
  
## <a name="example"></a><span data-ttu-id="51489-104">例</span><span class="sxs-lookup"><span data-stu-id="51489-104">Example</span></span>  
 <span data-ttu-id="51489-105">次[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]コードを説明する名前付き<xref:System.Windows.Controls.RichTextBox>単純コンテンツを持つコントロール。</span><span class="sxs-lookup"><span data-stu-id="51489-105">The following [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] code describes a named <xref:System.Windows.Controls.RichTextBox> control with simple content.</span></span>  
  
 [!code-xaml[RichTextBoxSnippets#_RTB_XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxSnippets/CSharp/Window1.xaml#_rtb_xaml)]  
  
## <a name="example"></a><span data-ttu-id="51489-106">例</span><span class="sxs-lookup"><span data-stu-id="51489-106">Example</span></span>  
 <span data-ttu-id="51489-107">次のコードを受け取るメソッドを実装する、<xref:System.Windows.Controls.RichTextBox>を引数としてのプレーン テキストの内容を表す文字列を返します、<xref:System.Windows.Controls.RichTextBox>します。</span><span class="sxs-lookup"><span data-stu-id="51489-107">The following code implements a method that takes a <xref:System.Windows.Controls.RichTextBox> as an argument, and returns a string representing the plain text contents of the <xref:System.Windows.Controls.RichTextBox>.</span></span>  
  
 <span data-ttu-id="51489-108">新しいメソッドを作成<xref:System.Windows.Documents.TextRange>の内容から、<xref:System.Windows.Controls.RichTextBox>を使用して、<xref:System.Windows.Documents.FlowDocument.ContentStart%2A>と<xref:System.Windows.Documents.FlowDocument.ContentEnd%2A>を抽出する内容の範囲を示すためにします。</span><span class="sxs-lookup"><span data-stu-id="51489-108">The method creates a new <xref:System.Windows.Documents.TextRange> from the contents of the <xref:System.Windows.Controls.RichTextBox>, using the <xref:System.Windows.Documents.FlowDocument.ContentStart%2A> and <xref:System.Windows.Documents.FlowDocument.ContentEnd%2A> to indicate the range of the contents to extract.</span></span>  <xref:System.Windows.Documents.FlowDocument.ContentStart%2A> <span data-ttu-id="51489-109"><xref:System.Windows.Documents.FlowDocument.ContentEnd%2A>各プロパティを返す、<xref:System.Windows.Documents.TextPointer>の内容を表す基になる FlowDocument でアクセスできるは、<xref:System.Windows.Controls.RichTextBox>します。</span><span class="sxs-lookup"><span data-stu-id="51489-109">and <xref:System.Windows.Documents.FlowDocument.ContentEnd%2A> properties each return a <xref:System.Windows.Documents.TextPointer>, and are accessible on the underlying FlowDocument that represents the contents of the <xref:System.Windows.Controls.RichTextBox>.</span></span>  <xref:System.Windows.Documents.TextRange> <span data-ttu-id="51489-110">プレーン テキストの部分を返すテキスト プロパティを取得するには、提供、<xref:System.Windows.Documents.TextRange>を文字列として。</span><span class="sxs-lookup"><span data-stu-id="51489-110">provides a Text property, which returns the plain text portions of the <xref:System.Windows.Documents.TextRange> as a string.</span></span>  
  
 [!code-csharp[RichTextBoxSnippets#_RTB_StringFrom](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxSnippets/CSharp/Window1.xaml.cs#_rtb_stringfrom)]
 [!code-vb[RichTextBoxSnippets#_RTB_StringFrom](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBoxSnippets/visualbasic/window1.xaml.vb#_rtb_stringfrom)]  
  
## <a name="see-also"></a><span data-ttu-id="51489-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="51489-111">See also</span></span>

- [<span data-ttu-id="51489-112">RichTextBox の概要</span><span class="sxs-lookup"><span data-stu-id="51489-112">RichTextBox Overview</span></span>](richtextbox-overview.md)
- [<span data-ttu-id="51489-113">TextBox の概要</span><span class="sxs-lookup"><span data-stu-id="51489-113">TextBox Overview</span></span>](textbox-overview.md)
