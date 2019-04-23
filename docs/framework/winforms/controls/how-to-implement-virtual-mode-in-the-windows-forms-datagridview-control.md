---
title: '方法: Windows フォーム DataGridView コントロールで仮想モードを実装する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data [Windows Forms], managing large data sets
- DataGridView control [Windows Forms], virtual mode
- virtual mode
- DataGridView control [Windows Forms], large data sets
ms.assetid: 98236267-f08e-4918-bcf9-77acf050a3ca
ms.openlocfilehash: d5b34f5c9d9e6db9c3fd06f2c09f62c196c96d0a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59146245"
---
# <a name="how-to-implement-virtual-mode-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="b409f-102">方法: Windows フォーム DataGridView コントロールで仮想モードを実装する</span><span class="sxs-lookup"><span data-stu-id="b409f-102">How to: Implement Virtual Mode in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="b409f-103">次のコード例は、<xref:System.Windows.Forms.DataGridView.VirtualMode%2A> プロパティを `true` に設定した <xref:System.Windows.Forms.DataGridView> コントロールを使用して、大規模なデータ セットを管理する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="b409f-103">The following code example demonstrates how to manage large sets of data using a <xref:System.Windows.Forms.DataGridView> control with its <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> property set to `true`.</span></span>  
  
 <span data-ttu-id="b409f-104">このコード例の詳細については、次を参照してください。[チュートリアル。仮想モードの実装で、Windows フォーム DataGridView コントロール](implementing-virtual-mode-wf-datagridview-control.md)します。</span><span class="sxs-lookup"><span data-stu-id="b409f-104">For a complete explanation of this code example, see [Walkthrough: Implementing Virtual Mode in the Windows Forms DataGridView Control](implementing-virtual-mode-wf-datagridview-control.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b409f-105">例</span><span class="sxs-lookup"><span data-stu-id="b409f-105">Example</span></span>  
 [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#000](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#000)]
 [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#000](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#000)]
 [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#000](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#000)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="b409f-106">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="b409f-106">Compiling the Code</span></span>  
 <span data-ttu-id="b409f-107">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="b409f-107">This example requires:</span></span>  
  
-   <span data-ttu-id="b409f-108">System アセンブリおよび System.Windows.Forms アセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="b409f-108">References to the System and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="b409f-109">Visual Basic または Visual C# のコマンドラインからこの例をビルドする方法については、[コマンド ラインからのビルド](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)または[csc.exe を使用したコマンド ラインからのビルド](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b409f-109">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="b409f-110">この例は、新しいプロジェクトにコードを貼り付けることによって Visual Studio で構築することもできます。</span><span class="sxs-lookup"><span data-stu-id="b409f-110">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b409f-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="b409f-111">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>
- <xref:System.Windows.Forms.DataGridView.CellValueNeeded>
- <xref:System.Windows.Forms.DataGridView.CellValuePushed>
- <xref:System.Windows.Forms.DataGridView.NewRowNeeded>
- <xref:System.Windows.Forms.DataGridView.RowValidated>
- <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded>
- <xref:System.Windows.Forms.DataGridView.CancelRowEdit>
- <xref:System.Windows.Forms.DataGridView.UserDeletingRow>
- [<span data-ttu-id="b409f-112">チュートリアル: Windows フォームの DataGridView コントロールで仮想モードの実装</span><span class="sxs-lookup"><span data-stu-id="b409f-112">Walkthrough: Implementing Virtual Mode in the Windows Forms DataGridView Control</span></span>](implementing-virtual-mode-wf-datagridview-control.md)
- [<span data-ttu-id="b409f-113">Windows フォーム DataGridView コントロールでのパフォーマンス チューニング</span><span class="sxs-lookup"><span data-stu-id="b409f-113">Performance Tuning in the Windows Forms DataGridView Control</span></span>](performance-tuning-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="b409f-114">Windows フォーム DataGridView コントロールでの仮想モード</span><span class="sxs-lookup"><span data-stu-id="b409f-114">Virtual Mode in the Windows Forms DataGridView Control</span></span>](virtual-mode-in-the-windows-forms-datagridview-control.md)
