---
title: '方法: Statusstrip 内で Spring プロパティを対話的に使用します。'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- StatusStrip control [Windows Forms]
- ToolStrip control [Windows Forms]
- status bars [Windows Forms], examples
- Spring property [Windows Forms]
ms.assetid: 18bde842-a93c-48dd-9db3-15738a1775ce
ms.openlocfilehash: 0e1d085b0695150e40c88683721134e9ea5116d9
ms.sourcegitcommit: af0a22a4eb11bbcd33baec49150d551955b50a16
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2019
ms.locfileid: "56260975"
---
# <a name="how-to-use-the-spring-property-interactively-in-a-statusstrip"></a><span data-ttu-id="e7a7e-102">方法: Statusstrip 内で Spring プロパティを対話的に使用します。</span><span class="sxs-lookup"><span data-stu-id="e7a7e-102">How to: Use the Spring Property Interactively in a StatusStrip</span></span>
<span data-ttu-id="e7a7e-103">
  <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A> プロパティを使用して、<xref:System.Windows.Forms.StatusStrip> コントロールに <xref:System.Windows.Forms.ToolStripStatusLabel> コントロールを配置できます。</span><span class="sxs-lookup"><span data-stu-id="e7a7e-103">You can use the <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A> property to position a <xref:System.Windows.Forms.ToolStripStatusLabel> control in a <xref:System.Windows.Forms.StatusStrip> control.</span></span> <span data-ttu-id="e7a7e-104">
  <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A> プロパティは、<xref:System.Windows.Forms.ToolStripStatusLabel> コントロールが <xref:System.Windows.Forms.StatusStrip> コントロールの使用可能な領域を自動的に入力するかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="e7a7e-104">The <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A> property determines whether the <xref:System.Windows.Forms.ToolStripStatusLabel> control automatically fills the available space on the <xref:System.Windows.Forms.StatusStrip> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e7a7e-105">例</span><span class="sxs-lookup"><span data-stu-id="e7a7e-105">Example</span></span>  
 <span data-ttu-id="e7a7e-106">次のコード例は、<xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A> プロパティを使用して、<xref:System.Windows.Forms.StatusStrip> コントロールに <xref:System.Windows.Forms.ToolStripStatusLabel> コントロールを配置する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="e7a7e-106">The following code example demonstrates how to use the <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A> property to position a <xref:System.Windows.Forms.ToolStripStatusLabel> control in a <xref:System.Windows.Forms.StatusStrip> control.</span></span> <span data-ttu-id="e7a7e-107">
  <xref:System.Windows.Forms.ToolStripItem.Click> イベント ハンドラーは、exclusive-or (XOR) 演算を実行して、<xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A> プロパティの値を切り替えます。</span><span class="sxs-lookup"><span data-stu-id="e7a7e-107">The <xref:System.Windows.Forms.ToolStripItem.Click> event handler performs an exclusive-or (XOR) operation to switch the value of the <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A> property.</span></span>  
  
 <span data-ttu-id="e7a7e-108">このコード例を使用するコンパイルし、アプリケーションを実行し、をクリックし、**中間 (スプリング)** 上、<xref:System.Windows.Forms.StatusStrip>コントロールの値を切り替えます、<xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="e7a7e-108">To use this code example, compile and run the application, and then click **Middle (Spring)** on the <xref:System.Windows.Forms.StatusStrip> control to switch the value of the <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A> property.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#1)]  
[!code-csharp[System.Windows.Forms.ToolStrip.Misc#50](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#50)]
[!code-vb[System.Windows.Forms.ToolStrip.Misc#50](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#50)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="e7a7e-109">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="e7a7e-109">Compiling the Code</span></span>  
 <span data-ttu-id="e7a7e-110">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e7a7e-110">This example requires:</span></span>  
  
-   <span data-ttu-id="e7a7e-111">System.Design、System.Drawing、および System.Windows.Forms の各アセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="e7a7e-111">References to the System.Design, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="e7a7e-112">コマンドラインからこの例を Visual Basic または Visual c# の構築方法の詳細については、次を参照してください。 [、コマンドラインからビルドする](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)または[コマンド ライン ビルドで csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)します。</span><span class="sxs-lookup"><span data-stu-id="e7a7e-112">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="e7a7e-113">新しいプロジェクトにコードを貼り付けることによって、この例では、Visual Studio を構築することもできます。</span><span class="sxs-lookup"><span data-stu-id="e7a7e-113">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7a7e-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="e7a7e-114">See also</span></span>
- <xref:System.Windows.Forms.ToolStripStatusLabel>
- <xref:System.Windows.Forms.StatusStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStripItem>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [<span data-ttu-id="e7a7e-115">ToolStrip コントロール</span><span class="sxs-lookup"><span data-stu-id="e7a7e-115">ToolStrip Control</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)
