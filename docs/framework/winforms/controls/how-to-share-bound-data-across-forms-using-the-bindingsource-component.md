---
title: '方法 : BindingSource コンポーネントを使用してフォーム間でバインド データを共有する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- examples [Windows Forms], BindingSource component
- data binding [Windows Forms], sharing data across forms
- BindingSource component [Windows Forms], examples
- BindingSource [Windows Forms], using with multiple forms
ms.assetid: a1a49630-db9c-4485-b888-1f62a373a4f7
ms.openlocfilehash: 765bdb7ee75d7e0c6461311263afe9481830673f
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2018
ms.locfileid: "43877257"
---
# <a name="how-to-share-bound-data-across-forms-using-the-bindingsource-component"></a><span data-ttu-id="37de0-102">方法 : BindingSource コンポーネントを使用してフォーム間でバインド データを共有する</span><span class="sxs-lookup"><span data-stu-id="37de0-102">How to: Share Bound Data Across Forms Using the BindingSource Component</span></span>
<span data-ttu-id="37de0-103"><xref:System.Windows.Forms.BindingSource> コンポーネントを使用してフォーム間でデータを簡単に共有できます。</span><span class="sxs-lookup"><span data-stu-id="37de0-103">You can easily share data across forms using the <xref:System.Windows.Forms.BindingSource> component.</span></span> <span data-ttu-id="37de0-104">たとえば、データ ソースのデータを集計する 1 つの読み取り専用のフォームと、データ ソース内の現在選択されているアイテムについての詳細情報を含む別の編集可能なフォームを表示することがあります。</span><span class="sxs-lookup"><span data-stu-id="37de0-104">For example, you may want to display one read-only form that summarizes the data-source data and another editable form that contains detailed information about the currently selected item in the data source.</span></span> <span data-ttu-id="37de0-105">この例は、このシナリオを示しています。</span><span class="sxs-lookup"><span data-stu-id="37de0-105">This example demonstrates this scenario.</span></span>  
  
## <a name="example"></a><span data-ttu-id="37de0-106">例</span><span class="sxs-lookup"><span data-stu-id="37de0-106">Example</span></span>  
 <span data-ttu-id="37de0-107">次のコード例は、<xref:System.Windows.Forms.BindingSource> およびフォーム間でバインドされたデータを共有する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="37de0-107">The following code example demonstrates how to share a <xref:System.Windows.Forms.BindingSource> and its bound data across forms.</span></span> <span data-ttu-id="37de0-108">この例で、共有された <xref:System.Windows.Forms.BindingSource> が子フォームのコンストラクターに渡されます。</span><span class="sxs-lookup"><span data-stu-id="37de0-108">In this example, the shared <xref:System.Windows.Forms.BindingSource> is passed to the constructor of the child form.</span></span> <span data-ttu-id="37de0-109">子フォームでは、メイン フォームで現在選択されているアイテムのデータをユーザーが編集することができます。</span><span class="sxs-lookup"><span data-stu-id="37de0-109">The child form allows the user to edit the data for the currently selected item in the main form.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="37de0-110">例の <xref:System.Windows.Forms.BindingSource> コンポーネントの <xref:System.Windows.Forms.BindingSource.BindingComplete> イベントは、2 つの形式が同期を保つために処理されます。</span><span class="sxs-lookup"><span data-stu-id="37de0-110">The <xref:System.Windows.Forms.BindingSource.BindingComplete> event for the <xref:System.Windows.Forms.BindingSource> component is handled in the example to ensure that the two forms remain synchronized.</span></span> <span data-ttu-id="37de0-111">これを実行する理由の詳細については、「[方法: 複数のコントロールを 1 つのデータ ソースにバインドして同期状態を保つ](../../../../docs/framework/winforms/multiple-controls-bound-to-data-source-synchronized.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="37de0-111">For more information about why this is done, see [How to: Ensure Multiple Controls Bound to the Same Data Source Remain Synchronized](../../../../docs/framework/winforms/multiple-controls-bound-to-data-source-synchronized.md).</span></span>  
  
 [!code-csharp[System.Windows.Forms.BindingSourceMultipleForms#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BindingSourceMultipleForms/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.BindingSourceMultipleForms#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BindingSourceMultipleForms/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="37de0-112">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="37de0-112">Compiling the Code</span></span>  
 <span data-ttu-id="37de0-113">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="37de0-113">This example requires:</span></span>  
  
-   <span data-ttu-id="37de0-114">System、System.Windows.Forms、System.Drawing、System.Data、および System.Xml アセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="37de0-114">References to the System, System.Windows.Forms, System.Drawing, System.Data, and System.Xml assemblies.</span></span>  
  
 <span data-ttu-id="37de0-115">コマンドラインからこの例を Visual Basic または Visual c# の構築方法の詳細については、次を参照してください。 [、コマンドラインからビルドする](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md)または[コマンド ライン ビルドで csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)します。</span><span class="sxs-lookup"><span data-stu-id="37de0-115">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="37de0-116">新しいプロジェクトにコードを貼り付けることによって、この例では、Visual Studio を構築することもできます。</span><span class="sxs-lookup"><span data-stu-id="37de0-116">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="37de0-117">「[方法: 完成した Windows フォーム コードの例を Visual Studio を使ってコンパイルして実行する](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\))」も参照してください。</span><span class="sxs-lookup"><span data-stu-id="37de0-117">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37de0-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="37de0-118">See Also</span></span>  
 [<span data-ttu-id="37de0-119">BindingSource コンポーネント</span><span class="sxs-lookup"><span data-stu-id="37de0-119">BindingSource Component</span></span>](../../../../docs/framework/winforms/controls/bindingsource-component.md)  
 [<span data-ttu-id="37de0-120">Windows フォームでのデータ バインディング</span><span class="sxs-lookup"><span data-stu-id="37de0-120">Windows Forms Data Binding</span></span>](../../../../docs/framework/winforms/windows-forms-data-binding.md)  
 [<span data-ttu-id="37de0-121">方法: データ バインドで発生するエラーと例外を処理する</span><span class="sxs-lookup"><span data-stu-id="37de0-121">How to: Handle Errors and Exceptions that Occur with Databinding</span></span>](../../../../docs/framework/winforms/controls/how-to-handle-errors-and-exceptions-that-occur-with-databinding.md)
