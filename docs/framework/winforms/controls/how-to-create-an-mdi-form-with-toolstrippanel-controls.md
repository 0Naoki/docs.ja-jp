---
title: '方法: ToolStripPanel コントロールを持つ MDI フォームを作成します。'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStripPanel control [Windows Forms]
- MDI [Windows Forms], creating forms
- multiple document interface forms
- MDI forms [Windows Forms]
- ToolStrip control [Windows Forms]
- MDI forms [Windows Forms], creating
ms.assetid: d198ef8e-f7c4-4b3f-a7f5-ce858cb90cec
ms.openlocfilehash: 22057fe2e9ae6fb68cf5876e9f312dc23379540c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54628176"
---
# <a name="how-to-create-an-mdi-form-with-toolstrippanel-controls"></a><span data-ttu-id="ab060-102">方法: ToolStripPanel コントロールを持つ MDI フォームを作成します。</span><span class="sxs-lookup"><span data-stu-id="ab060-102">How to: Create an MDI Form with ToolStripPanel Controls</span></span>
<span data-ttu-id="ab060-103">上下左右すべての側に <xref:System.Windows.Forms.ToolStrip> コントロールを配置したマルチ ドキュメント インターフェイス (MDI) フォームを作成できます。</span><span class="sxs-lookup"><span data-stu-id="ab060-103">You can create a multiple document interface (MDI) form that has <xref:System.Windows.Forms.ToolStrip> controls framing it on all four sides.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ab060-104">例</span><span class="sxs-lookup"><span data-stu-id="ab060-104">Example</span></span>  
 <span data-ttu-id="ab060-105">次のコード例は、ドッキングされた <xref:System.Windows.Forms.ToolStripPanel> コントロールを使用して、4 つの <xref:System.Windows.Forms.ToolStrip> コントロールを MDI ウィンドウの周囲に配置する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="ab060-105">The following code example demonstrates how to use docked <xref:System.Windows.Forms.ToolStripPanel> controls to frame an MDI window with four <xref:System.Windows.Forms.ToolStrip> controls.</span></span>  
  
 <span data-ttu-id="ab060-106">この例では、<xref:System.Windows.Forms.ToolStripPanel.Join%2A> メソッドにより、<xref:System.Windows.Forms.ToolStrip> コントロールを、対応する <xref:System.Windows.Forms.ToolStripPanel> コントロールにアタッチしています。</span><span class="sxs-lookup"><span data-stu-id="ab060-106">In the example, the <xref:System.Windows.Forms.ToolStripPanel.Join%2A> method attaches the <xref:System.Windows.Forms.ToolStrip> controls to the corresponding <xref:System.Windows.Forms.ToolStripPanel> controls.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#1)]  
[!code-csharp[System.Windows.Forms.ToolStrip.Misc#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#10)]
[!code-vb[System.Windows.Forms.ToolStrip.Misc#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#10)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="ab060-107">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="ab060-107">Compiling the Code</span></span>  
 <span data-ttu-id="ab060-108">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="ab060-108">This example requires:</span></span>  
  
-   <span data-ttu-id="ab060-109">System.Drawing アセンブリおよび System.Windows.Forms アセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="ab060-109">References to the System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="ab060-110">コマンドラインからこの例を Visual Basic または Visual c# の構築方法の詳細については、次を参照してください。 [、コマンドラインからビルドする](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md)または[コマンド ライン ビルドで csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)します。</span><span class="sxs-lookup"><span data-stu-id="ab060-110">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="ab060-111">新しいプロジェクトにコードを貼り付けることによって、この例では、Visual Studio を構築することもできます。</span><span class="sxs-lookup"><span data-stu-id="ab060-111">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="ab060-112">参照してください[方法。Visual Studio を使用して、完全な Windows フォームのコードの例をコンパイルして](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\))します。</span><span class="sxs-lookup"><span data-stu-id="ab060-112">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab060-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="ab060-113">See also</span></span>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStripPanel>
- <xref:System.Windows.Forms.ToolStripPanel.Join%2A>
- <xref:System.Windows.Forms.ToolStripItem>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [<span data-ttu-id="ab060-114">ToolStrip コントロール</span><span class="sxs-lookup"><span data-stu-id="ab060-114">ToolStrip Control</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)
