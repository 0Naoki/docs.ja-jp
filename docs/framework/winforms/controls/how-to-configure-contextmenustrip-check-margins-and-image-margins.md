---
title: '方法: ContextMenuStrip のチェックの余白とイメージの余白'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- context menus [Windows Forms], configuring check and image margins
- ContextMenuStrips [Windows Forms], configuring check and image margins
- margins [Windows Forms], setting check and image in Windows Forms ContextMenuStrips
ms.assetid: 3391c4c2-0c9e-4aa4-9492-13ff7644bdf2
ms.openlocfilehash: 9406a1dc0fca36a42674d5455e5529b703d87e3e
ms.sourcegitcommit: 30e2fe5cc4165aa6dde7218ec80a13def3255e98
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/13/2019
ms.locfileid: "56220089"
---
# <a name="how-to-configure-contextmenustrip-check-margins-and-image-margins"></a><span data-ttu-id="e2f92-102">方法: ContextMenuStrip のチェックの余白とイメージの余白</span><span class="sxs-lookup"><span data-stu-id="e2f92-102">How to: Configure ContextMenuStrip Check Margins and Image Margins</span></span>
<span data-ttu-id="e2f92-103">
  <xref:System.Windows.Forms.ToolStripDropDownMenu.ShowImageMargin%2A> プロパティと <xref:System.Windows.Forms.ToolStripDropDownMenu.ShowCheckMargin%2A> プロパティをさまざまな組み合わせで設定することにより、<xref:System.Windows.Forms.ContextMenuStrip> をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="e2f92-103">You can customize a <xref:System.Windows.Forms.ContextMenuStrip> by setting the <xref:System.Windows.Forms.ToolStripDropDownMenu.ShowImageMargin%2A> and <xref:System.Windows.Forms.ToolStripDropDownMenu.ShowCheckMargin%2A> properties in various combinations.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e2f92-104">例</span><span class="sxs-lookup"><span data-stu-id="e2f92-104">Example</span></span>  
 <span data-ttu-id="e2f92-105">次のコード例では、<xref:System.Windows.Forms.ContextMenuStrip> のチェックの余白とイメージの余白をカスタマイズする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e2f92-105">The following code example demonstrates how to set and customize the <xref:System.Windows.Forms.ContextMenuStrip> check and image margins.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#1)]  
[!code-csharp[System.Windows.Forms.ToolStrip.Misc#60](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#60)]
[!code-vb[System.Windows.Forms.ToolStrip.Misc#60](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#60)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="e2f92-106">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="e2f92-106">Compiling the Code</span></span>  
 <span data-ttu-id="e2f92-107">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e2f92-107">This example requires:</span></span>  
  
-   <span data-ttu-id="e2f92-108">System.Design、System.Drawing、および System.Windows.Forms の各アセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="e2f92-108">References to the System.Design, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="e2f92-109">コマンドラインからこの例を Visual Basic または Visual c# の構築方法の詳細については、次を参照してください。 [、コマンドラインからビルドする](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)または[コマンド ライン ビルドで csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)します。</span><span class="sxs-lookup"><span data-stu-id="e2f92-109">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="e2f92-110">新しいプロジェクトにコードを貼り付けることによって、この例では、Visual Studio を構築することもできます。</span><span class="sxs-lookup"><span data-stu-id="e2f92-110">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2f92-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="e2f92-111">See also</span></span>
- <xref:System.Windows.Forms.ContextMenuStrip>
- <xref:System.Windows.Forms.ToolStripDropDown>
- [<span data-ttu-id="e2f92-112">ToolStrip コントロール</span><span class="sxs-lookup"><span data-stu-id="e2f92-112">ToolStrip Control</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)
- [<span data-ttu-id="e2f92-113">方法: ContextMenuStrip コントロールでチェックの余白とイメージを有効にします。</span><span class="sxs-lookup"><span data-stu-id="e2f92-113">How to: Enable Check Margins and Image Margins in ContextMenuStrip Controls</span></span>](../../../../docs/framework/winforms/controls/how-to-enable-check-margins-and-image-margins-in-contextmenustrip-controls.md)
