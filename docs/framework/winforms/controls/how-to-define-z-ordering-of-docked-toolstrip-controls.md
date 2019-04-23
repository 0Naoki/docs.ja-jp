---
title: '方法: ドッキングされた ToolStrip コントロールの Z オーダーを定義する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStrip control [Windows Forms]
- MenuStrip control [Windows Forms]
- toolbars [Windows Forms], specifying z-order
- z-order
ms.assetid: 8b595429-ba9f-46af-9c55-3d5cc53f7fff
ms.openlocfilehash: 3347722383b7388c00335683537e00851e642bb6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59129169"
---
# <a name="how-to-define-z-ordering-of-docked-toolstrip-controls"></a><span data-ttu-id="da9cf-102">方法: ドッキングされた ToolStrip コントロールの Z オーダーを定義する</span><span class="sxs-lookup"><span data-stu-id="da9cf-102">How to: Define Z-Ordering of Docked ToolStrip Controls</span></span>
<span data-ttu-id="da9cf-103">ドッキングを使用して <xref:System.Windows.Forms.ToolStrip> コントロールを正しく配置するには、フォームの z オーダーでコントロールを正しく配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="da9cf-103">To position a <xref:System.Windows.Forms.ToolStrip> control correctly with docking, you must position the control correctly in the form's z-order.</span></span>  
  
## <a name="example"></a><span data-ttu-id="da9cf-104">例</span><span class="sxs-lookup"><span data-stu-id="da9cf-104">Example</span></span>  
 <span data-ttu-id="da9cf-105">次のコード例は、z オーダーを指定することで、<xref:System.Windows.Forms.ToolStrip> コントロールと、ドッキングされた <xref:System.Windows.Forms.MenuStrip> コントロールを調整する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="da9cf-105">The following code example demonstrates how to arrange a <xref:System.Windows.Forms.ToolStrip> control and a docked <xref:System.Windows.Forms.MenuStrip> control by specifying the z-order.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#21)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#21)]  
  
 <span data-ttu-id="da9cf-106">Z オーダーは、<xref:System.Windows.Forms.ToolStrip> と <xref:System.Windows.Forms.MenuStrip> の順序によって決まります。</span><span class="sxs-lookup"><span data-stu-id="da9cf-106">The z-order is determined by the order in which the <xref:System.Windows.Forms.ToolStrip> and <xref:System.Windows.Forms.MenuStrip></span></span>  
  
 <span data-ttu-id="da9cf-107">コントロールはフォームの <xref:System.Windows.Forms.Control.Controls%2A> コレクションに追加されます。</span><span class="sxs-lookup"><span data-stu-id="da9cf-107">controls are added to the form's <xref:System.Windows.Forms.Control.Controls%2A> collection.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#23](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#23)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#23)]  
  
 <span data-ttu-id="da9cf-108"><xref:System.Windows.Forms.Control.ControlCollection.Add%2A> メソッドへのこれらの呼び出しの順序を反転し、レイアウトへの影響を示します。</span><span class="sxs-lookup"><span data-stu-id="da9cf-108">Reverse the order of these calls to the <xref:System.Windows.Forms.Control.ControlCollection.Add%2A> method and view the effect on the layout.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="da9cf-109">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="da9cf-109">Compiling the Code</span></span>  
 <span data-ttu-id="da9cf-110">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="da9cf-110">This example requires:</span></span>  
  
-   <span data-ttu-id="da9cf-111">System.Design、System.Drawing、および System.Windows.Forms の各アセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="da9cf-111">References to the System.Design, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="da9cf-112">この例をコマンドラインから Visual Basic または Visual C# にビルドする方法の詳細については、[コマンドラインからのビルド](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)または[csc.exe を使用したコマンド ラインからのビルド](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="da9cf-112">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="da9cf-113">新しいプロジェクトにコードを貼り付けることによって、この例では、Visual Studio を構築することもできます。</span><span class="sxs-lookup"><span data-stu-id="da9cf-113">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da9cf-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="da9cf-114">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.Control.ControlCollection.Add%2A>
- <xref:System.Windows.Forms.Control.Controls%2A>
- <xref:System.Windows.Forms.Control.Dock%2A>
- [<span data-ttu-id="da9cf-115">ToolStrip コントロール</span><span class="sxs-lookup"><span data-stu-id="da9cf-115">ToolStrip Control</span></span>](toolstrip-control-windows-forms.md)
