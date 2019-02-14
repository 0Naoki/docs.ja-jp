---
title: '方法: Toolstrippanel を結合します。'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms], joining together
- ToolStripPanel control [Windows Forms], joining together
ms.assetid: 4eadda6d-e3b8-4151-aaf2-a8d564fbe6b3
ms.openlocfilehash: cebfcb417dc011ed8990e9d536cd165c2a92cb68
ms.sourcegitcommit: af0a22a4eb11bbcd33baec49150d551955b50a16
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2019
ms.locfileid: "56260739"
---
# <a name="how-to-join-toolstrippanels"></a><span data-ttu-id="56008-102">方法: Toolstrippanel を結合します。</span><span class="sxs-lookup"><span data-stu-id="56008-102">How to: Join ToolStripPanels</span></span>
<span data-ttu-id="56008-103">実行時に <xref:System.Windows.Forms.ToolStrip> コントロールを <xref:System.Windows.Forms.ToolStripPanel> に結合でき、これによりマルチ ドキュメント インターフェイス (MDI) アプリケーションの柔軟性を提供します。</span><span class="sxs-lookup"><span data-stu-id="56008-103">You can join <xref:System.Windows.Forms.ToolStrip> controls to a <xref:System.Windows.Forms.ToolStripPanel> at run time, which provides the flexibility of multiple-document interface (MDI) applications.</span></span>  
  
## <a name="example"></a><span data-ttu-id="56008-104">例</span><span class="sxs-lookup"><span data-stu-id="56008-104">Example</span></span>  
 <span data-ttu-id="56008-105">次のコード例は、<xref:System.Windows.Forms.ToolStrip> コントロールを <xref:System.Windows.Forms.ToolStripPanel> に結合する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="56008-105">The following code example demonstrates how to join <xref:System.Windows.Forms.ToolStrip> controls to a <xref:System.Windows.Forms.ToolStripPanel>.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#11)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#11)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="56008-106">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="56008-106">Compiling the Code</span></span>  
 <span data-ttu-id="56008-107">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="56008-107">This example requires:</span></span>  
  
-   <span data-ttu-id="56008-108">System.Design、System.Drawing、および System.Windows.Forms の各アセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="56008-108">References to the System.Design, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="56008-109">コマンドラインからこの例を Visual Basic または Visual c# の構築方法の詳細については、次を参照してください。 [、コマンドラインからビルドする](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)または[コマンド ライン ビルドで csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)します。</span><span class="sxs-lookup"><span data-stu-id="56008-109">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="56008-110">新しいプロジェクトにコードを貼り付けることによって、この例では、Visual Studio を構築することもできます。</span><span class="sxs-lookup"><span data-stu-id="56008-110">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56008-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="56008-111">See also</span></span>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStripPanel>
- [<span data-ttu-id="56008-112">Toolstrippanel を MDI で使用します。</span><span class="sxs-lookup"><span data-stu-id="56008-112">How to: Use ToolStripPanels for MDI</span></span>](../../../../docs/framework/winforms/controls/how-to-use-toolstrippanels-for-mdi.md)
