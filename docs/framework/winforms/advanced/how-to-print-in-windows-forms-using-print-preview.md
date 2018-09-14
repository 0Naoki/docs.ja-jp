---
title: '方法 : Windows フォームで印刷プレビューを使用して印刷する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- printing [Windows Forms], using print preview
- printing [Windows Forms], with print preview
- print preview
ms.assetid: 4a16f7e2-ae10-4485-b0ae-3d558334d0fe
ms.openlocfilehash: ff113b3abfb8363e65d7ccb101973b6821d97262
ms.sourcegitcommit: 76a304c79a32aa13889ebcf4b9789a4542b48e3e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/13/2018
ms.locfileid: "45515731"
---
# <a name="how-to-print-in-windows-forms-using-print-preview"></a><span data-ttu-id="e0054-102">方法 : Windows フォームで印刷プレビューを使用して印刷する</span><span class="sxs-lookup"><span data-stu-id="e0054-102">How to: Print in Windows Forms Using Print Preview</span></span>
<span data-ttu-id="e0054-103">Windows フォームのプログラミングでは、印刷サービスに加えて印刷プレビューを提供することは非常に一般的です。</span><span class="sxs-lookup"><span data-stu-id="e0054-103">It is very common in Windows Forms programming to offer print preview in addition to printing services.</span></span> <span data-ttu-id="e0054-104">印刷プレビューのサービスをアプリケーションに追加する簡単な方法は、ファイルの印刷に <xref:System.Windows.Forms.PrintPreviewDialog> コントロールを <xref:System.Drawing.Printing.PrintDocument.PrintPage> イベント処理ロジックと組み合わせて使用することです。</span><span class="sxs-lookup"><span data-stu-id="e0054-104">An easy way to add print preview services to your application is to use a <xref:System.Windows.Forms.PrintPreviewDialog> control in combination with the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event-handling logic for printing a file.</span></span>  
  
### <a name="to-preview-a-text-document-with-a-printpreviewdialog-control"></a><span data-ttu-id="e0054-105">PrintPreviewDialog コントロールのテキスト ドキュメントをプレビューするには</span><span class="sxs-lookup"><span data-stu-id="e0054-105">To preview a text document with a PrintPreviewDialog control</span></span>  
  
1.  <span data-ttu-id="e0054-106">フォームに <xref:System.Windows.Forms.PrintPreviewDialog>、 <xref:System.Drawing.Printing.PrintDocument>、および 2 つの文字列を追加します。</span><span class="sxs-lookup"><span data-stu-id="e0054-106">Add a <xref:System.Windows.Forms.PrintPreviewDialog>, <xref:System.Drawing.Printing.PrintDocument>, and two strings to your form.</span></span>  
  
     [!code-csharp[System.Drawing.Printing.PrintPreviewExample#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Printing.PrintPreviewExample/CS/Form1.cs#1)]
     [!code-vb[System.Drawing.Printing.PrintPreviewExample#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Printing.PrintPreviewExample/VB/Form1.vb#1)]  
  
2.  <span data-ttu-id="e0054-107"><xref:System.Drawing.Printing.PrintDocument.DocumentName%2A> プロパティを印刷するドキュメントに設定し、ドキュメントの内容を開いて前に追加した文字列に読み取ります。</span><span class="sxs-lookup"><span data-stu-id="e0054-107">Set the <xref:System.Drawing.Printing.PrintDocument.DocumentName%2A> property to the document you wish to print, and open and read the document's contents to the string you added previously.</span></span>  
  
     [!code-csharp[System.Drawing.Printing.PrintPreviewExample#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Printing.PrintPreviewExample/CS/Form1.cs#2)]
     [!code-vb[System.Drawing.Printing.PrintPreviewExample#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Printing.PrintPreviewExample/VB/Form1.vb#2)]  
  
3.  <span data-ttu-id="e0054-108">ドキュメントの印刷の場合と同様、 <xref:System.Drawing.Printing.PrintDocument.PrintPage> イベント ハンドラーで <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> クラスの <xref:System.Drawing.Printing.PrintPageEventArgs> プロパティと、ファイルの内容を使用して、1 ページあたりの行数を計算し、ドキュメントの内容を表示します。</span><span class="sxs-lookup"><span data-stu-id="e0054-108">As you would for printing the document, in the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event handler, use the <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> property of the <xref:System.Drawing.Printing.PrintPageEventArgs> class and the file contents to calculate lines per page and render the document's contents.</span></span> <span data-ttu-id="e0054-109">各ページを描画した後で、最後のページかどうかを確認し、 <xref:System.Drawing.Printing.PrintPageEventArgs.HasMorePages%2A> の <xref:System.Drawing.Printing.PrintPageEventArgs> プロパティを適切に設定します。</span><span class="sxs-lookup"><span data-stu-id="e0054-109">After each page is drawn, check to see if it is the last page, and set the <xref:System.Drawing.Printing.PrintPageEventArgs.HasMorePages%2A> property of the <xref:System.Drawing.Printing.PrintPageEventArgs> accordingly.</span></span> <span data-ttu-id="e0054-110"><xref:System.Drawing.Printing.PrintDocument.PrintPage> が <xref:System.Drawing.Printing.PrintPageEventArgs.HasMorePages%2A> になるまで `false`イベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="e0054-110">The <xref:System.Drawing.Printing.PrintDocument.PrintPage> event is raised until <xref:System.Drawing.Printing.PrintPageEventArgs.HasMorePages%2A> is `false`.</span></span> <span data-ttu-id="e0054-111">ドキュメントの表示が完了したら、表示される文字列をリセットします。</span><span class="sxs-lookup"><span data-stu-id="e0054-111">When the document has finished rendering, reset the string to be rendered.</span></span> <span data-ttu-id="e0054-112">また、 <xref:System.Drawing.Printing.PrintDocument.PrintPage> イベントがイベント処理メソッドに関連付けられていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e0054-112">Also, make sure the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event is associated with its event-handling method.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e0054-113">アプリケーションに印刷を実装した場合は、既に手順 2 および 3 を完了している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e0054-113">You may have already completed steps 2 and 3 if you have implemented printing in your application.</span></span>  
  
     <span data-ttu-id="e0054-114">次のコード例では、イベント ハンドラーが、フォームで使用されているものと同じフォントで "testPage.txt" ファイルの内容を印刷するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="e0054-114">In the following code example, the event handler is used to print the "testPage.txt" file in the same font used on the form.</span></span>  
  
     [!code-csharp[System.Drawing.Printing.PrintPreviewExample#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Printing.PrintPreviewExample/CS/Form1.cs#3)]
     [!code-vb[System.Drawing.Printing.PrintPreviewExample#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Printing.PrintPreviewExample/VB/Form1.vb#3)]  
  
4.  <span data-ttu-id="e0054-115"><xref:System.Windows.Forms.PrintPreviewDialog.Document%2A> コントロールの <xref:System.Windows.Forms.PrintPreviewDialog> のプロパティをフォームの <xref:System.Drawing.Printing.PrintDocument> コンポーネントに設定します。</span><span class="sxs-lookup"><span data-stu-id="e0054-115">Set the <xref:System.Windows.Forms.PrintPreviewDialog.Document%2A> property of the <xref:System.Windows.Forms.PrintPreviewDialog> control to the <xref:System.Drawing.Printing.PrintDocument> component on the form.</span></span>  
  
     [!code-csharp[System.Drawing.Printing.PrintPreviewExample#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Printing.PrintPreviewExample/CS/Form1.cs#5)]
     [!code-vb[System.Drawing.Printing.PrintPreviewExample#5](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Printing.PrintPreviewExample/VB/Form1.vb#5)]  
  
5.  <span data-ttu-id="e0054-116"><xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> コントロールの <xref:System.Windows.Forms.PrintPreviewDialog> メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="e0054-116">Call the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method on the <xref:System.Windows.Forms.PrintPreviewDialog> control.</span></span> <span data-ttu-id="e0054-117">通常はボタンの <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> イベント処理メソッドから <xref:System.Windows.Forms.Control.Click> を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="e0054-117">You would typically call <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> from the <xref:System.Windows.Forms.Control.Click> event-handling method of a button.</span></span> <span data-ttu-id="e0054-118"><xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> を呼び出すことで <xref:System.Drawing.Printing.PrintDocument.PrintPage> イベントが発生し、 <xref:System.Windows.Forms.PrintPreviewDialog> コントロールに出力を表示します。</span><span class="sxs-lookup"><span data-stu-id="e0054-118">Calling <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> raises the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event and renders the output to the <xref:System.Windows.Forms.PrintPreviewDialog> control.</span></span> <span data-ttu-id="e0054-119">ユーザーが、ダイアログの印刷アイコンをクリックすると、 <xref:System.Drawing.Printing.PrintDocument.PrintPage> イベントがもう一度発生し、プレビュー ダイアログではなく、プリンターに出力を送信します。</span><span class="sxs-lookup"><span data-stu-id="e0054-119">When the user clicks the print icon on the dialog, the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event is raised again, sending the output to the printer instead of the preview dialog.</span></span> <span data-ttu-id="e0054-120">これが理由で、手順 3 のレンダリング プロセスの最後に文字列がリセットされます。</span><span class="sxs-lookup"><span data-stu-id="e0054-120">This is why the string is reset at the end of the rendering process in step 3.</span></span>  
  
     <span data-ttu-id="e0054-121">次のコード例は、フォームのボタンの <xref:System.Windows.Forms.Control.Click> イベント処理メソッドを示します。</span><span class="sxs-lookup"><span data-stu-id="e0054-121">The following code example shows the <xref:System.Windows.Forms.Control.Click> event-handling method for a button on the form.</span></span> <span data-ttu-id="e0054-122">このイベント処理メソッドは、ドキュメントを読み込んで、印刷プレビューのダイアログを表示するメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="e0054-122">This event-handling method calls the methods to read the document and show the print preview dialog.</span></span>  
  
     [!code-csharp[System.Drawing.Printing.PrintPreviewExample#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Printing.PrintPreviewExample/CS/Form1.cs#4)]
     [!code-vb[System.Drawing.Printing.PrintPreviewExample#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Printing.PrintPreviewExample/VB/Form1.vb#4)]  
  
## <a name="example"></a><span data-ttu-id="e0054-123">例</span><span class="sxs-lookup"><span data-stu-id="e0054-123">Example</span></span>  
 [!code-csharp[System.Drawing.Printing.PrintPreviewExample#0](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Printing.PrintPreviewExample/CS/Form1.cs#0)]
 [!code-vb[System.Drawing.Printing.PrintPreviewExample#0](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Printing.PrintPreviewExample/VB/Form1.vb#0)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="e0054-124">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="e0054-124">Compiling the Code</span></span>  
 <span data-ttu-id="e0054-125">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e0054-125">This example requires:</span></span>  
  
-   <span data-ttu-id="e0054-126">System、System.Windows.Forms、System.Drawing の各アセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="e0054-126">References to the System, System.Windows.Forms, System.Drawing assemblies.</span></span>  
  
-   <span data-ttu-id="e0054-127">コマンドラインからこの例を Visual Basic または Visual c# の構築方法の詳細については、次を参照してください。 [、コマンドラインからビルドする](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md)または[コマンド ライン ビルドで csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)します。</span><span class="sxs-lookup"><span data-stu-id="e0054-127">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="e0054-128">新しいプロジェクトにコードを貼り付けることによって、この例では、Visual Studio を構築することもできます。</span><span class="sxs-lookup"><span data-stu-id="e0054-128">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="e0054-129">「[方法: 完成した Windows フォーム コードの例を Visual Studio を使ってコンパイルして実行する](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\))」も参照してください。</span><span class="sxs-lookup"><span data-stu-id="e0054-129">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0054-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="e0054-130">See Also</span></span>  
 [<span data-ttu-id="e0054-131">方法: Windows フォームで複数ページのテキスト ファイルを印刷する</span><span class="sxs-lookup"><span data-stu-id="e0054-131">How to: Print a Multi-Page Text File in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-print-a-multi-page-text-file-in-windows-forms.md)  
 [<span data-ttu-id="e0054-132">Windows フォームにおける印刷のサポート</span><span class="sxs-lookup"><span data-stu-id="e0054-132">Windows Forms Print Support</span></span>](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md)  
 [<span data-ttu-id="e0054-133">Windows フォームでのより安全な印刷</span><span class="sxs-lookup"><span data-stu-id="e0054-133">More Secure Printing in Windows Forms</span></span>](../../../../docs/framework/winforms/more-secure-printing-in-windows-forms.md)
