---
title: プログラムによる RichTextBox での選択の変更
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- changing selections in a text box [WPF]
- changing selections in a RichTextBox [WPF]
ms.assetid: f1213205-1ad7-4cd2-b115-460173cc5aa3
ms.openlocfilehash: b8acfe7cde1fe5dae96cd6324f75c5b146be9ec9
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59096227"
---
# <a name="change-selection-in-a-richtextbox-programmatically"></a><span data-ttu-id="b3698-102">プログラムによる RichTextBox での選択の変更</span><span class="sxs-lookup"><span data-stu-id="b3698-102">Change Selection in a RichTextBox Programmatically</span></span>
<span data-ttu-id="b3698-103">この例は、プログラムでの現在の選択を変更する方法を示します、<xref:System.Windows.Controls.RichTextBox>します。</span><span class="sxs-lookup"><span data-stu-id="b3698-103">This example shows how to programmatically change the current selection in a <xref:System.Windows.Controls.RichTextBox>.</span></span> <span data-ttu-id="b3698-104">この選択は、ユーザーは、ユーザー インターフェイスを使用して、コンテンツを選択した場合と同じです。</span><span class="sxs-lookup"><span data-stu-id="b3698-104">This selection is the same as if the user had selected the content by using the user interface.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b3698-105">例</span><span class="sxs-lookup"><span data-stu-id="b3698-105">Example</span></span>  
 <span data-ttu-id="b3698-106">次[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]コードを説明する名前付き<xref:System.Windows.Controls.RichTextBox>単純コンテンツを持つコントロール。</span><span class="sxs-lookup"><span data-stu-id="b3698-106">The following [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] code describes a named <xref:System.Windows.Controls.RichTextBox> control with simple content.</span></span>  
  
 [!code-xaml[RichTextBoxMiscSnippets_snip#ChangeSelectionProgrammaticalyExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/ChangeSelectionProgrammaticaly.xaml#changeselectionprogrammaticalyexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="b3698-107">例</span><span class="sxs-lookup"><span data-stu-id="b3698-107">Example</span></span>  
 <span data-ttu-id="b3698-108">次のコードは、内部で、ユーザーがクリックしたときにプログラムでいくつかの任意のテキストを選択、<xref:System.Windows.Controls.RichTextBox>します。</span><span class="sxs-lookup"><span data-stu-id="b3698-108">The following code programmatically selects some arbitrary text when the user clicks inside the <xref:System.Windows.Controls.RichTextBox>.</span></span>  
  
 [!code-csharp[RichTextBoxMiscSnippets_snip#ChangeSelectionProgrammaticalyCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/ChangeSelectionProgrammaticaly.xaml.cs#changeselectionprogrammaticalycodeexamplewholepage)]
 [!code-vb[RichTextBoxMiscSnippets_snip#ChangeSelectionProgrammaticalyCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/VisualBasic/ChangeSelectionProgrammaticaly.xaml.vb#changeselectionprogrammaticalycodeexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="b3698-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="b3698-109">See also</span></span>

- [<span data-ttu-id="b3698-110">RichTextBox の概要</span><span class="sxs-lookup"><span data-stu-id="b3698-110">RichTextBox Overview</span></span>](richtextbox-overview.md)
- [<span data-ttu-id="b3698-111">TextBox の概要</span><span class="sxs-lookup"><span data-stu-id="b3698-111">TextBox Overview</span></span>](textbox-overview.md)
