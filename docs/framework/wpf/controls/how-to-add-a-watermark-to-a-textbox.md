---
title: '方法: TextBox へのウォーターマークの追加'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- displaying a background image inside a text box to aid user input [WPF]
- aid usability of a TextBox using a background image [WPF]
ms.assetid: df89bdd8-a0fb-45e0-b312-dd53332d01a8
ms.openlocfilehash: 1ab8c0f9274f4d461c9c2be04ec0aaca5e753c7d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54531133"
---
# <a name="how-to-add-a-watermark-to-a-textbox"></a><span data-ttu-id="43a26-102">方法: TextBox へのウォーターマークの追加</span><span class="sxs-lookup"><span data-stu-id="43a26-102">How to: Add a Watermark to a TextBox</span></span>
<span data-ttu-id="43a26-103">次の例では、使いやすさを支援する方法を示しています、<xref:System.Windows.Controls.TextBox>内での説明の背景イメージを表示することによって、<xref:System.Windows.Controls.TextBox>この時点で、イメージを削除するまで、ユーザーがテキストを入力します。</span><span class="sxs-lookup"><span data-stu-id="43a26-103">The following example shows how to aid usability of a <xref:System.Windows.Controls.TextBox> by displaying an explanatory background image inside of the <xref:System.Windows.Controls.TextBox> until the user inputs text, at which point the image is removed.</span></span> <span data-ttu-id="43a26-104">さらに、背景画像は、ユーザー入力を削除する場合、再び復元します。</span><span class="sxs-lookup"><span data-stu-id="43a26-104">In addition, the background image is restored again if the user removes their input.</span></span> <span data-ttu-id="43a26-105">次の図を参照してください。</span><span class="sxs-lookup"><span data-stu-id="43a26-105">See illustration below.</span></span>  
  
 <span data-ttu-id="43a26-106">![背景イメージを含む TextBox](../../../../docs/framework/wpf/controls/media/editing-textbox-using-background-image.png "Editing_TextBox_using_background_image")</span><span class="sxs-lookup"><span data-stu-id="43a26-106">![A TextBox with a background image](../../../../docs/framework/wpf/controls/media/editing-textbox-using-background-image.png "Editing_TextBox_using_background_image")</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="43a26-107">背景イメージがこの例ではなく、単に操作で使用される理由、<xref:System.Windows.Controls.TextBox.Text%2A>プロパティの<xref:System.Windows.Controls.TextBox>が背景画像はデータ バインドが妨げられないようにします。</span><span class="sxs-lookup"><span data-stu-id="43a26-107">The reason a background image is used in this example rather then simply manipulating the <xref:System.Windows.Controls.TextBox.Text%2A> property of <xref:System.Windows.Controls.TextBox>, is that a background image will not interfere with data binding.</span></span>  
  
## <a name="example"></a><span data-ttu-id="43a26-108">例</span><span class="sxs-lookup"><span data-stu-id="43a26-108">Example</span></span>  
 [!code-xaml[TextBoxMiscSnippets_snip#TextBoxBackgroundExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/textbox_with_background_image.xaml#textboxbackgroundexamplewholepage)]  
  
 [!code-csharp[TextBoxMiscSnippets_snip#TextBoxBackgroundCodeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/textbox_with_background_image.xaml.cs#textboxbackgroundcodeexamplewholepage)]
 [!code-vb[TextBoxMiscSnippets_snip#TextBoxBackgroundCodeExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/visualbasic/textbox_with_background_image.xaml.vb#textboxbackgroundcodeexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="43a26-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="43a26-109">See also</span></span>
- [<span data-ttu-id="43a26-110">TextBox の概要</span><span class="sxs-lookup"><span data-stu-id="43a26-110">TextBox Overview</span></span>](../../../../docs/framework/wpf/controls/textbox-overview.md)
- [<span data-ttu-id="43a26-111">RichTextBox の概要</span><span class="sxs-lookup"><span data-stu-id="43a26-111">RichTextBox Overview</span></span>](../../../../docs/framework/wpf/controls/richtextbox-overview.md)
