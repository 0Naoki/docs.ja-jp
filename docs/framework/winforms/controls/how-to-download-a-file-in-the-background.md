---
title: '方法: バックグラウンドでファイルをダウンロードする'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- BackgroundWorker component
- background tasks
- Asynchronous Pattern
- forms [Windows Forms], multithreading
- components [Windows Forms], asynchronous
- forms [Windows Forms], background operations
- threading [Windows Forms], background operations
- background operations
ms.assetid: 9b7bc5ae-051c-4904-9720-18f6667388bd
ms.openlocfilehash: af5a607b4800635d096e83b55a5bd5a912c8538d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59128779"
---
# <a name="how-to-download-a-file-in-the-background"></a><span data-ttu-id="534fc-102">方法: バックグラウンドでファイルをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="534fc-102">How to: Download a File in the Background</span></span>
<span data-ttu-id="534fc-103">ファイルのダウンロードは一般的なタスクであり、時間のかかる可能性があるこの操作を別のスレッドで実行すると便利です。</span><span class="sxs-lookup"><span data-stu-id="534fc-103">Downloading a file is a common task, and it is often useful to run this potentially time-consuming operation on a separate thread.</span></span> <span data-ttu-id="534fc-104">ごくわずかなコードでこのタスクを実行するには、<xref:System.ComponentModel.BackgroundWorker> コンポーネントを使用します。</span><span class="sxs-lookup"><span data-stu-id="534fc-104">Use the <xref:System.ComponentModel.BackgroundWorker> component to accomplish this task with very little code.</span></span>  
  
## <a name="example"></a><span data-ttu-id="534fc-105">例</span><span class="sxs-lookup"><span data-stu-id="534fc-105">Example</span></span>  
 <span data-ttu-id="534fc-106">次のコード例は、<xref:System.ComponentModel.BackgroundWorker> コンポーネントを使用して、URL からの XML ファイルを読み込む方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="534fc-106">The following code example demonstrates how to use a <xref:System.ComponentModel.BackgroundWorker> component to load an XML file from a URL.</span></span> <span data-ttu-id="534fc-107">ユーザーがクリックしたとき、**ダウンロード**ボタン、<xref:System.Windows.Forms.Control.Click>イベント ハンドラーの呼び出し、<xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A>のメソッドを<xref:System.ComponentModel.BackgroundWorker>コンポーネント ダウンロード操作を開始します。</span><span class="sxs-lookup"><span data-stu-id="534fc-107">When the user clicks the **Download** button, the <xref:System.Windows.Forms.Control.Click> event handler calls the <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> method of a <xref:System.ComponentModel.BackgroundWorker> component to start the download operation.</span></span> <span data-ttu-id="534fc-108">ダウンロード中はボタンが無効になり、ダウンロードが完了すると有効になります。</span><span class="sxs-lookup"><span data-stu-id="534fc-108">The button is disabled for the duration of the download, and then enabled when the download is complete.</span></span> <span data-ttu-id="534fc-109"><xref:System.Windows.Forms.MessageBox> にファイルの内容が表示されます。</span><span class="sxs-lookup"><span data-stu-id="534fc-109">A <xref:System.Windows.Forms.MessageBox> displays the contents of the file.</span></span>  
  
 [!code-csharp[System.ComponentModel.BackgroundWorker.IsBusy#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.IsBusy/CS/Form1.cs#1)]
 [!code-vb[System.ComponentModel.BackgroundWorker.IsBusy#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.IsBusy/VB/Form1.vb#1)]  
  
 **<span data-ttu-id="534fc-110">ファイルのダウンロード</span><span class="sxs-lookup"><span data-stu-id="534fc-110">Downloading the file</span></span>**  
  
 <span data-ttu-id="534fc-111">ファイルが <xref:System.ComponentModel.BackgroundWorker.DoWork> イベント ハンドラーを実行する <xref:System.ComponentModel.BackgroundWorker> コンポーネントのワーカー スレッドにダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="534fc-111">The file is downloaded on the <xref:System.ComponentModel.BackgroundWorker> component's worker thread, which runs the <xref:System.ComponentModel.BackgroundWorker.DoWork> event handler.</span></span> <span data-ttu-id="534fc-112">このスレッドは、コードが <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> メソッドを呼び出すときに開始されます。</span><span class="sxs-lookup"><span data-stu-id="534fc-112">This thread starts when your code calls the <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> method.</span></span>  
  
 [!code-csharp[System.ComponentModel.BackgroundWorker.IsBusy#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.IsBusy/CS/Form1.cs#3)]
 [!code-vb[System.ComponentModel.BackgroundWorker.IsBusy#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.IsBusy/VB/Form1.vb#3)]  
  
 **<span data-ttu-id="534fc-113">完了する BackgroundWorker を待機する</span><span class="sxs-lookup"><span data-stu-id="534fc-113">Waiting for a BackgroundWorker to finish</span></span>**  
  
 <span data-ttu-id="534fc-114">`downloadButton_Click` イベント ハンドラーが <xref:System.ComponentModel.BackgroundWorker> コンポーネントの非同期タスクの終了を待機する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="534fc-114">The `downloadButton_Click` event handler demonstrates how to wait for a <xref:System.ComponentModel.BackgroundWorker> component to finish its asynchronous task.</span></span>  
  
 <span data-ttu-id="534fc-115">アプリケーションがイベントへの応答のみを実行し、バック グラウンド スレッドを待機している間にメイン スレッドでその他の作業を実行しないようにする場合は、ハンドラーを終了します。</span><span class="sxs-lookup"><span data-stu-id="534fc-115">If you only want the application to respond to events and do not want to do any work in the main thread while you wait for the background thread to complete, just exit the handler.</span></span>  
  
 <span data-ttu-id="534fc-116">メイン スレッドで処理を続行する場合は、<xref:System.ComponentModel.BackgroundWorker.IsBusy%2A> プロパティを使用して、<xref:System.ComponentModel.BackgroundWorker> スレッドをまだ実行するかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="534fc-116">If you want to continue doing work in the main thread, use the <xref:System.ComponentModel.BackgroundWorker.IsBusy%2A> property to determine whether the <xref:System.ComponentModel.BackgroundWorker> thread is still running.</span></span> <span data-ttu-id="534fc-117">例では、ダウンロードの処理中に、進行状況バーが更新されます。</span><span class="sxs-lookup"><span data-stu-id="534fc-117">In the example, a progress bar is updated while the download is processing.</span></span> <span data-ttu-id="534fc-118">必ず <xref:System.Windows.Forms.Application.DoEvents%2A?displayProperty=nameWithType> メソッドを呼び出して、UI 応答性を維持してください。</span><span class="sxs-lookup"><span data-stu-id="534fc-118">Be sure to call the <xref:System.Windows.Forms.Application.DoEvents%2A?displayProperty=nameWithType> method to keep the UI responsive.</span></span>  
  
 [!code-csharp[System.ComponentModel.BackgroundWorker.IsBusy#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.IsBusy/CS/Form1.cs#2)]
 [!code-vb[System.ComponentModel.BackgroundWorker.IsBusy#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.IsBusy/VB/Form1.vb#2)]  
  
 **<span data-ttu-id="534fc-119">結果の表示</span><span class="sxs-lookup"><span data-stu-id="534fc-119">Displaying the result</span></span>**  
  
 <span data-ttu-id="534fc-120">`backgroundWorker1_RunWorkerCompleted` メソッドは、<xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> イベントを処理し、バック グラウンド操作が完了したときに呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="534fc-120">The `backgroundWorker1_RunWorkerCompleted` method handles the <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> event and is called when the background operation is completed.</span></span> <span data-ttu-id="534fc-121">このメソッドはまず、<xref:System.ComponentModel.AsyncCompletedEventArgs.Error%2A?displayProperty=nameWithType> プロパティを確認します。</span><span class="sxs-lookup"><span data-stu-id="534fc-121">This method first checks the <xref:System.ComponentModel.AsyncCompletedEventArgs.Error%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="534fc-122"><xref:System.ComponentModel.AsyncCompletedEventArgs.Error%2A?displayProperty=nameWithType> が `null` の場合に、このメソッドはファイルの内容を表示します。</span><span class="sxs-lookup"><span data-stu-id="534fc-122">If <xref:System.ComponentModel.AsyncCompletedEventArgs.Error%2A?displayProperty=nameWithType> is `null`, then this method displays the contents of the file.</span></span> <span data-ttu-id="534fc-123">これで、ダウンロードを開始したときに無効になっていた [ダウンロード] ボタンが有効になり、進行状況バーがリセットされます。</span><span class="sxs-lookup"><span data-stu-id="534fc-123">It then enables the download button, which was disabled when the download began, and it resets the progress bar.</span></span>  
  
 [!code-csharp[System.ComponentModel.BackgroundWorker.IsBusy#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.IsBusy/CS/Form1.cs#4)]
 [!code-vb[System.ComponentModel.BackgroundWorker.IsBusy#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.IsBusy/VB/Form1.vb#4)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="534fc-124">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="534fc-124">Compiling the Code</span></span>  
 <span data-ttu-id="534fc-125">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="534fc-125">This example requires:</span></span>  
  
-   <span data-ttu-id="534fc-126">System.Drawing、System.Windows.Forms、および System.Xml の各アセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="534fc-126">References to the System.Drawing, System.Windows.Forms, and System.Xml assemblies.</span></span>  
  
 <span data-ttu-id="534fc-127">コマンドラインからこの例を Visual Basic または Visual C# の構築方法の詳細については、[、コマンドラインからビルドする](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)または[コマンド ライン ビルドで csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="534fc-127">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="534fc-128">新しいプロジェクトにコードを貼り付けることによって、この例では、Visual Studio を構築することもできます。</span><span class="sxs-lookup"><span data-stu-id="534fc-128">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="534fc-129">信頼性の高いプログラミング</span><span class="sxs-lookup"><span data-stu-id="534fc-129">Robust Programming</span></span>  
 <span data-ttu-id="534fc-130"><xref:System.ComponentModel.BackgroundWorker.DoWork> イベント ハンドラーにより影響を受けている可能性がある <xref:System.ComponentModel.RunWorkerCompletedEventArgs.Result%2A?displayProperty=nameWithType> プロパティまたはその他のオブジェクトへのアクセスを試みる前に、常に <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> イベント ハンドラーの <xref:System.ComponentModel.AsyncCompletedEventArgs.Error%2A?displayProperty=nameWithType> プロパティを確認してください。</span><span class="sxs-lookup"><span data-stu-id="534fc-130">Always check the <xref:System.ComponentModel.AsyncCompletedEventArgs.Error%2A?displayProperty=nameWithType> property in your <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> event handler before attempting to access the <xref:System.ComponentModel.RunWorkerCompletedEventArgs.Result%2A?displayProperty=nameWithType> property or any other object that may have been affected by the <xref:System.ComponentModel.BackgroundWorker.DoWork> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="534fc-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="534fc-131">See also</span></span>

- <xref:System.ComponentModel.BackgroundWorker>
- [<span data-ttu-id="534fc-132">方法: バックグラウンドで操作を実行する</span><span class="sxs-lookup"><span data-stu-id="534fc-132">How to: Run an Operation in the Background</span></span>](how-to-run-an-operation-in-the-background.md)
- [<span data-ttu-id="534fc-133">方法: バックグラウンド操作を使用するフォームを実装する</span><span class="sxs-lookup"><span data-stu-id="534fc-133">How to: Implement a Form That Uses a Background Operation</span></span>](how-to-implement-a-form-that-uses-a-background-operation.md)
