---
title: '方法 : Windows フォーム ListView コントロールに挿入マークを表示する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- ListView control [Windows Forms], drag operations
- graphics [Windows Forms], insertion marks
- drop and drag [Windows Forms], insertion marks
- insertion marks
ms.assetid: 88d0a15b-25fd-4dc3-a685-297351311940
ms.openlocfilehash: b9b6e1911d3e372861ebcdc5a175314d69c89175
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/08/2018
ms.locfileid: "44192328"
---
# <a name="how-to-display-an-insertion-mark-in-a-windows-forms-listview-control"></a><span data-ttu-id="cc87f-102">方法 : Windows フォーム ListView コントロールに挿入マークを表示する</span><span class="sxs-lookup"><span data-stu-id="cc87f-102">How to: Display an Insertion Mark in a Windows Forms ListView Control</span></span>
<span data-ttu-id="cc87f-103"><xref:System.Windows.Forms.ListView> コントロールの挿入マークは、ドラッグされた項目の挿入先となるポイントをユーザーに表示します。</span><span class="sxs-lookup"><span data-stu-id="cc87f-103">The insertion mark in the <xref:System.Windows.Forms.ListView> control shows users the point where dragged items will be inserted.</span></span> <span data-ttu-id="cc87f-104">ユーザーが項目をその他の 2 つの項目の間のポイントにドラッグすると、項目の予期される新しい場所に挿入マークが表示されます。</span><span class="sxs-lookup"><span data-stu-id="cc87f-104">When a user drags an item to a point between two other items, the insertion mark shows the item's expected new location.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cc87f-105">挿入マーク機能は、アプリケーションから <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> メソッドを呼び出した場合に、[!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="cc87f-105">The insertion mark feature is available only on [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] when your application calls the <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="cc87f-106">以前のオペレーティング システムでは、挿入マークに関連するすべてのコードは効果がなく、挿入マークは表示されません。</span><span class="sxs-lookup"><span data-stu-id="cc87f-106">On earlier operating systems, any code relating to the insertion mark has no effect and the insertion mark will not appear.</span></span> <span data-ttu-id="cc87f-107">詳細については、「<xref:System.Windows.Forms.ListViewInsertionMark>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cc87f-107">For more information, see <xref:System.Windows.Forms.ListViewInsertionMark>.</span></span>  
  
 <span data-ttu-id="cc87f-108">次の図は、挿入マークを示しています。</span><span class="sxs-lookup"><span data-stu-id="cc87f-108">The following image shows an insertion mark:</span></span>  
  
 <span data-ttu-id="cc87f-109">![ListView 挿入記号](../../../../docs/framework/winforms/controls/media/listviewinsertion.gif "ListViewInsertion")</span><span class="sxs-lookup"><span data-stu-id="cc87f-109">![A ListView Insertion Mark](../../../../docs/framework/winforms/controls/media/listviewinsertion.gif "ListViewInsertion")</span></span>  
  
 <span data-ttu-id="cc87f-110">この機能の使用方法を次のコード例に示します。</span><span class="sxs-lookup"><span data-stu-id="cc87f-110">The following code example demonstrates how to use this feature.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cc87f-111">例</span><span class="sxs-lookup"><span data-stu-id="cc87f-111">Example</span></span>  
 [!code-cpp[System.Windows.Forms.ListView.InsertionMark#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ListView.InsertionMark/CPP/listviewinsertionmarkexample.cpp#1)]
 [!code-csharp[System.Windows.Forms.ListView.InsertionMark#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListView.InsertionMark/CS/listviewinsertionmarkexample.cs#1)]
 [!code-vb[System.Windows.Forms.ListView.InsertionMark#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListView.InsertionMark/VB/listviewinsertionmarkexample.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="cc87f-112">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="cc87f-112">Compiling the Code</span></span>  
 <span data-ttu-id="cc87f-113">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="cc87f-113">This example requires:</span></span>  
  
-   <span data-ttu-id="cc87f-114">System アセンブリおよび System.Windows.Forms アセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="cc87f-114">References to the System and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="cc87f-115">コマンドラインからこの例を Visual Basic または Visual c# の構築方法の詳細については、次を参照してください。 [、コマンドラインからビルドする](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md)または[コマンド ライン ビルドで csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)します。</span><span class="sxs-lookup"><span data-stu-id="cc87f-115">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="cc87f-116">新しいプロジェクトにコードを貼り付けることによって、この例では、Visual Studio を構築することもできます。</span><span class="sxs-lookup"><span data-stu-id="cc87f-116">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="cc87f-117">「[方法: 完成した Windows フォーム コードの例を Visual Studio を使ってコンパイルして実行する](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\))」も参照してください。</span><span class="sxs-lookup"><span data-stu-id="cc87f-117">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc87f-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="cc87f-118">See Also</span></span>  
 <xref:System.Windows.Forms.ListView>  
 <xref:System.Windows.Forms.ListView.InsertionMark%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.ListViewInsertionMark>  
 [<span data-ttu-id="cc87f-119">ListView コントロール</span><span class="sxs-lookup"><span data-stu-id="cc87f-119">ListView Control</span></span>](../../../../docs/framework/winforms/controls/listview-control-windows-forms.md)  
 [<span data-ttu-id="cc87f-120">ListView コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="cc87f-120">ListView Control Overview</span></span>](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)  
 [<span data-ttu-id="cc87f-121">Windows XP の機能と Windows フォーム コントロール</span><span class="sxs-lookup"><span data-stu-id="cc87f-121">Windows XP Features and Windows Forms Controls</span></span>](https://msdn.microsoft.com/library/bc7fab94-fce9-4bf1-a8ad-a5837c91c3c0)  
 [<span data-ttu-id="cc87f-122">チュートリアル: Windows フォームにおけるドラッグ アンド ドロップ操作の実行</span><span class="sxs-lookup"><span data-stu-id="cc87f-122">Walkthrough: Performing a Drag-and-Drop Operation in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/walkthrough-performing-a-drag-and-drop-operation-in-windows-forms.md)
