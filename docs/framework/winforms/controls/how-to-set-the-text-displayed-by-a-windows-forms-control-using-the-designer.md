---
title: '方法: Windows フォーム コントロールに表示するテキストをデザイナーで設定する'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], setting caption
- Windows Forms, setting the text displayed
ms.assetid: 9d18e0e0-f17f-4074-837d-e67ceeeaa89d
ms.openlocfilehash: 645ddedcb0de560737ee05db1375f09cfa2cd7ef
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59123860"
---
# <a name="how-to-set-the-text-displayed-by-a-windows-forms-control-using-the-designer"></a><span data-ttu-id="915d4-102">方法: Windows フォーム コントロールに表示するテキストをデザイナーで設定する</span><span class="sxs-lookup"><span data-stu-id="915d4-102">How to: Set the Text Displayed by a Windows Forms Control Using the Designer</span></span>
<span data-ttu-id="915d4-103">Windows フォーム コントロールは、通常、コントロールの主な機能に関連するいくつかのテキストを表示します。</span><span class="sxs-lookup"><span data-stu-id="915d4-103">Windows Forms controls typically display some text that is related to the primary function of the control.</span></span> <span data-ttu-id="915d4-104">たとえば、<xref:System.Windows.Forms.Button>コントロールには、通常、ボタンがクリックされたときに実行するアクションを示すキャプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="915d4-104">For example, a <xref:System.Windows.Forms.Button> control typically displays a caption that indicates what action will be performed when the button is clicked.</span></span> <span data-ttu-id="915d4-105">すべてのコントロールに対して、<xref:System.Windows.Forms.Control.Text%2A> プロパティを使用してテキストを設定または返すことができます。</span><span class="sxs-lookup"><span data-stu-id="915d4-105">For all controls, you can set or return the text by using the <xref:System.Windows.Forms.Control.Text%2A> property.</span></span> <span data-ttu-id="915d4-106"><xref:System.Windows.Forms.Control.Font%2A> プロパティを使用して、フォントを変更することができます。</span><span class="sxs-lookup"><span data-stu-id="915d4-106">You can change the font by using the <xref:System.Windows.Forms.Control.Font%2A> property.</span></span>  
  
### <a name="to-set-the-text-and-font-with-the-designer"></a><span data-ttu-id="915d4-107">テキストとデザイナーを使用したフォントを設定するには</span><span class="sxs-lookup"><span data-stu-id="915d4-107">To set the text and font with the designer</span></span>  
  
1.  <span data-ttu-id="915d4-108">[プロパティ] ウィンドウで次のように設定します。、<xref:System.Windows.Forms.Control.Text%2A>適切な文字列をコントロールのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="915d4-108">In the Properties window, set the <xref:System.Windows.Forms.Control.Text%2A> property of the control to an appropriate string.</span></span>  
  
     <span data-ttu-id="915d4-109">下線付きのショートカット キーを作成するアンパサンドが含まれています (&) は、ショートカット キーとなる文字の前にします。</span><span class="sxs-lookup"><span data-stu-id="915d4-109">To create an underlined shortcut key, includes an ampersand (&) before the letter that will be the shortcut key.</span></span>  
  
2.  <span data-ttu-id="915d4-110">[プロパティ] ウィンドウで、省略記号ボタンをクリックします。 (![VisualStudioEllipsesButton スクリーン ショット](../media/vbellipsesbutton.png "vbEllipsesButton")) 横に、<xref:System.Windows.Forms.Control.Font%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="915d4-110">In the Properties window, click the ellipsis button (![VisualStudioEllipsesButton screenshot](../media/vbellipsesbutton.png "vbEllipsesButton")) next to the <xref:System.Windows.Forms.Control.Font%2A> property.</span></span>  
  
     <span data-ttu-id="915d4-111">標準的なフォント ダイアログ ボックスで、フォント、フォント スタイル、サイズ、(取り消し線、下線) などの効果とスクリプトを選択します。</span><span class="sxs-lookup"><span data-stu-id="915d4-111">In the standard font dialog box, select the font, font style, size, effects (such as strikeout or underline), and script that you want.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="915d4-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="915d4-112">See also</span></span>

- [<span data-ttu-id="915d4-113">方法: Windows フォーム コントロールによって表示されるテキストを設定する</span><span class="sxs-lookup"><span data-stu-id="915d4-113">How to: Set the Text Displayed by a Windows Forms Control</span></span>](how-to-set-the-text-displayed-by-a-windows-forms-control.md)
- [<span data-ttu-id="915d4-114">フォントとテキストの使用</span><span class="sxs-lookup"><span data-stu-id="915d4-114">Using Fonts and Text</span></span>](../advanced/using-fonts-and-text.md)
- [<span data-ttu-id="915d4-115">各 Windows フォーム コントロールのラベル設定とショートカットの作成</span><span class="sxs-lookup"><span data-stu-id="915d4-115">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
