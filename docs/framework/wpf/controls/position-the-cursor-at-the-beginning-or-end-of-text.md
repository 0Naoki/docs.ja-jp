---
title: '方法: TextBox コントロールのテキストの先頭または末尾にカーソルを配置する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- positioning cursor [WPF]
- TextBox control [WPF], positioning cursor
- cursor [WPF], positioning
ms.assetid: c771a0b8-c6b4-4240-aecd-a21d0ba51a2e
ms.openlocfilehash: 2b280c6ea74a4b7a896f33a3552997a730d24a39
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54497619"
---
# <a name="how-to-position-the-cursor-at-the-beginning-or-end-of-text-in-a-textbox-control"></a><span data-ttu-id="fcca8-102">方法: TextBox コントロールのテキストの先頭または末尾にカーソルを配置する</span><span class="sxs-lookup"><span data-stu-id="fcca8-102">How to: Position the Cursor at the Beginning or End of Text in a TextBox Control</span></span>
<span data-ttu-id="fcca8-103">この例では、先頭またはのテキストの内容の末尾にカーソルを置き、<xref:System.Windows.Controls.TextBox>コントロール。</span><span class="sxs-lookup"><span data-stu-id="fcca8-103">This example shows how to position the cursor at the beginning or end of the text contents of a <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fcca8-104">例</span><span class="sxs-lookup"><span data-stu-id="fcca8-104">Example</span></span>  
 <span data-ttu-id="fcca8-105">次[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]コードについて説明します、<xref:System.Windows.Controls.TextBox>制御し、名前が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="fcca8-105">The following [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] code describes a <xref:System.Windows.Controls.TextBox> control and assigns it a Name.</span></span>  
  
 [!code-xaml[TextBox_MiscCode#_MoveCursorXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_movecursorxaml)]  
  
## <a name="example"></a><span data-ttu-id="fcca8-106">例</span><span class="sxs-lookup"><span data-stu-id="fcca8-106">Example</span></span>  
 <span data-ttu-id="fcca8-107">内容の先頭にカーソルを配置する、<xref:System.Windows.Controls.TextBox>コントロールを呼び出す、<xref:System.Windows.Controls.TextBox.Select%2A>メソッドと、選択範囲の開始位置の 0、および 0 の選択範囲の長さを指定します。</span><span class="sxs-lookup"><span data-stu-id="fcca8-107">To position the cursor at the beginning of the contents of a <xref:System.Windows.Controls.TextBox> control, call the <xref:System.Windows.Controls.TextBox.Select%2A> method and specify the selection start position of 0, and a selection length of 0.</span></span>  
  
 [!code-csharp[TextBox_MiscCode#_CursorToStart](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_cursortostart)]
 [!code-vb[TextBox_MiscCode#_CursorToStart](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_cursortostart)]  
  
## <a name="example"></a><span data-ttu-id="fcca8-108">例</span><span class="sxs-lookup"><span data-stu-id="fcca8-108">Example</span></span>  
 <span data-ttu-id="fcca8-109">内容の末尾にカーソルを配置する、<xref:System.Windows.Controls.TextBox>コントロールを呼び出す、<xref:System.Windows.Controls.TextBox.Select%2A>メソッドと、コンテンツのテキストの長さと選択範囲の長さを 0 に等しい選択の開始位置を指定します。</span><span class="sxs-lookup"><span data-stu-id="fcca8-109">To position the cursor at the end of the contents of a <xref:System.Windows.Controls.TextBox> control, call the <xref:System.Windows.Controls.TextBox.Select%2A> method and specify the selection start position equal to the  length of the text content, and a selection length of 0.</span></span>  
  
 [!code-csharp[TextBox_MiscCode#_CursorToEnd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_cursortoend)]
 [!code-vb[TextBox_MiscCode#_CursorToEnd](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_cursortoend)]  
  
## <a name="see-also"></a><span data-ttu-id="fcca8-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="fcca8-110">See also</span></span>
- [<span data-ttu-id="fcca8-111">TextBox の概要</span><span class="sxs-lookup"><span data-stu-id="fcca8-111">TextBox Overview</span></span>](../../../../docs/framework/wpf/controls/textbox-overview.md)
- [<span data-ttu-id="fcca8-112">RichTextBox の概要</span><span class="sxs-lookup"><span data-stu-id="fcca8-112">RichTextBox Overview</span></span>](../../../../docs/framework/wpf/controls/richtextbox-overview.md)
