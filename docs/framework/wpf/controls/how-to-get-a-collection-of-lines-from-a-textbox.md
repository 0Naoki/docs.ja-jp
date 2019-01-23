---
title: '方法: TextBox から行のコレクションを取得する'
ms.date: 03/30/2017
helpviewer_keywords:
- lines [WPF], getting collection of
- TextBox control [WPF], getting collection of lines
ms.assetid: a12f529d-b926-47f6-92bf-cad5f17b532a
ms.openlocfilehash: a63470c6f0db72340f482bf638910685aa3f461f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54561765"
---
# <a name="how-to-get-a-collection-of-lines-from-a-textbox"></a><span data-ttu-id="ca80c-102">方法: TextBox から行のコレクションを取得する</span><span class="sxs-lookup"><span data-stu-id="ca80c-102">How to: Get a Collection of Lines from a TextBox</span></span>
<span data-ttu-id="ca80c-103">この例からのテキストの行のコレクションを取得する方法を示しています、<xref:System.Windows.Controls.TextBox>します。</span><span class="sxs-lookup"><span data-stu-id="ca80c-103">This example shows how to get a collection of lines of text from a <xref:System.Windows.Controls.TextBox>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ca80c-104">例</span><span class="sxs-lookup"><span data-stu-id="ca80c-104">Example</span></span>  
 <span data-ttu-id="ca80c-105">次の例を受け取る単純なメソッドを示しています、<xref:System.Windows.Controls.TextBox>引数として返す、<xref:System.Collections.Specialized.StringCollection>内のテキストの行を含む、 **TextBox**。</span><span class="sxs-lookup"><span data-stu-id="ca80c-105">The following example shows a simple method that takes a <xref:System.Windows.Controls.TextBox> as the argument, and returns a <xref:System.Collections.Specialized.StringCollection> containing the lines of text in the **TextBox**.</span></span>  <span data-ttu-id="ca80c-106"><xref:System.Windows.Controls.TextBox.LineCount%2A>プロパティを使用して、現在の行の数を調べます、 **TextBox**と<xref:System.Windows.Controls.TextBox.GetLineText%2A>メソッドを使用して各行を抽出し、行のコレクションに追加します。</span><span class="sxs-lookup"><span data-stu-id="ca80c-106">The <xref:System.Windows.Controls.TextBox.LineCount%2A> property is used to determine how many lines are currently in the **TextBox**, and the <xref:System.Windows.Controls.TextBox.GetLineText%2A> method is then used to extract each line and add it to the collection of lines.</span></span>  
  
 [!code-csharp[TextBox_MiscCode#_TextBox_GetLines](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_textbox_getlines)]  
  
## <a name="see-also"></a><span data-ttu-id="ca80c-107">関連項目</span><span class="sxs-lookup"><span data-stu-id="ca80c-107">See also</span></span>
- [<span data-ttu-id="ca80c-108">TextBox の概要</span><span class="sxs-lookup"><span data-stu-id="ca80c-108">TextBox Overview</span></span>](../../../../docs/framework/wpf/controls/textbox-overview.md)
- [<span data-ttu-id="ca80c-109">RichTextBox の概要</span><span class="sxs-lookup"><span data-stu-id="ca80c-109">RichTextBox Overview</span></span>](../../../../docs/framework/wpf/controls/richtextbox-overview.md)
