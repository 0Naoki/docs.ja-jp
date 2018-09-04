---
title: '方法 : Windows フォームの DataGridView 行にバインドされたオブジェクトにアクセスする'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- object binding [Windows Forms], accessing bound objects
- data grids [Windows Forms], accessing bound objects
- DataGridView control [Windows Forms], accessing objects bound to rows
ms.assetid: 0e05748f-4403-4eb8-8b2f-b098108181b5
ms.openlocfilehash: 72dc0c55a946bfa8ffc6f87bdbf353a20205185e
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "43500600"
---
# <a name="how-to-access-objects-bound-to-windows-forms-datagridview-rows"></a><span data-ttu-id="9e0f1-102">方法 : Windows フォームの DataGridView 行にバインドされたオブジェクトにアクセスする</span><span class="sxs-lookup"><span data-stu-id="9e0f1-102">How to: Access Objects Bound to Windows Forms DataGridView Rows</span></span>
<span data-ttu-id="9e0f1-103">場合によっては、ビジネス オブジェクトのコレクションに格納されている情報のテーブルを表示すると便利です。</span><span class="sxs-lookup"><span data-stu-id="9e0f1-103">Sometimes it is useful to display a table of information stored in a collection of business objects.</span></span> <span data-ttu-id="9e0f1-104"><xref:System.Windows.Forms.DataGridView> コントロールをそのようなコレクションにバインドすると、<xref:System.ComponentModel.BrowsableAttribute> によって参照不可にマークされない限り、各パブリック プロパティが独自の列に表示されます。</span><span class="sxs-lookup"><span data-stu-id="9e0f1-104">When you bind a <xref:System.Windows.Forms.DataGridView> control to such a collection, each public property is displayed in its own column unless the property has been marked non-browsable with a <xref:System.ComponentModel.BrowsableAttribute>.</span></span> <span data-ttu-id="9e0f1-105">たとえば、`Customer` オブジェクトのコレクションに**名前**や**アドレス**などの列が含まれるようになります。</span><span class="sxs-lookup"><span data-stu-id="9e0f1-105">For example, a collection of `Customer` objects would have columns such as **Name** and **Address**.</span></span>  
  
 <span data-ttu-id="9e0f1-106">アクセスする追加情報とコードがこれらのオブジェクトに含まれている場合は、行オブジェクトを介してアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="9e0f1-106">If these objects contain additional information and code that you want to access, you can reach it through row objects.</span></span> <span data-ttu-id="9e0f1-107">次のコード例では、ユーザーが複数の行を選択し、ボタンをクリックすると、対応する顧客のそれぞれに請求書を送信できます。</span><span class="sxs-lookup"><span data-stu-id="9e0f1-107">In the following code example, users can select multiple rows and click a button to send an invoice to each of the corresponding customers.</span></span>  
  
### <a name="to-access-row-bound-objects"></a><span data-ttu-id="9e0f1-108">行にバインドされたオブジェクトにアクセスするには</span><span class="sxs-lookup"><span data-stu-id="9e0f1-108">To access row-bound objects</span></span>  
  
-   <span data-ttu-id="9e0f1-109"><xref:System.Windows.Forms.DataGridViewRow.DataBoundItem%2A?displayProperty=nameWithType> プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="9e0f1-109">Use the <xref:System.Windows.Forms.DataGridViewRow.DataBoundItem%2A?displayProperty=nameWithType> property.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewObjectBinding#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewObjectBinding/CS/datagridviewobjectbinding.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridViewObjectBinding#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewObjectBinding/VB/datagridviewobjectbinding.vb#10)]  
  
## <a name="example"></a><span data-ttu-id="9e0f1-110">例</span><span class="sxs-lookup"><span data-stu-id="9e0f1-110">Example</span></span>  
 <span data-ttu-id="9e0f1-111">完全なコード例には、単純な `Customer` 実装が含まれ、<xref:System.Windows.Forms.DataGridView> を `Customer` オブジェクトがいくつか含まれる <xref:System.Collections.ArrayList> にバインドします。</span><span class="sxs-lookup"><span data-stu-id="9e0f1-111">The complete code example includes a simple `Customer` implementation and binds the <xref:System.Windows.Forms.DataGridView> to an <xref:System.Collections.ArrayList> containing a few `Customer` objects.</span></span> <span data-ttu-id="9e0f1-112"><xref:System.Windows.Forms.Button?displayProperty=nameWithType> の <xref:System.Windows.Forms.Control.Click> イベント ハンドラーは、行を介して `Customer` オブジェクトにアクセスする必要があります。これは、<xref:System.Windows.Forms.Form.Load?displayProperty=nameWithType> イベント ハンドラーの外部で、顧客のコレクションにアクセスできないためです。</span><span class="sxs-lookup"><span data-stu-id="9e0f1-112">The <xref:System.Windows.Forms.Control.Click> event handler of the <xref:System.Windows.Forms.Button?displayProperty=nameWithType> must access the `Customer` objects through the rows, because the customer collection is not accessible outside the <xref:System.Windows.Forms.Form.Load?displayProperty=nameWithType> event handler.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataGridViewObjectBinding#00](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewObjectBinding/CS/datagridviewobjectbinding.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewObjectBinding#00](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewObjectBinding/VB/datagridviewobjectbinding.vb#00)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="9e0f1-113">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="9e0f1-113">Compiling the Code</span></span>  
 <span data-ttu-id="9e0f1-114">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="9e0f1-114">This example requires:</span></span>  
  
-   <span data-ttu-id="9e0f1-115">System アセンブリおよび System.Windows.Forms アセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="9e0f1-115">References to the System and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="9e0f1-116">コマンドラインからこの例を Visual Basic または Visual c# の構築方法の詳細については、次を参照してください。 [、コマンドラインからビルドする](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md)または[コマンド ライン ビルドで csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)します。</span><span class="sxs-lookup"><span data-stu-id="9e0f1-116">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="9e0f1-117">新しいプロジェクトにコードを貼り付けることによって、この例では、Visual Studio を構築することもできます。</span><span class="sxs-lookup"><span data-stu-id="9e0f1-117">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="9e0f1-118">「[方法: 完成した Windows フォーム コードの例を Visual Studio を使ってコンパイルして実行する](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\))」も参照してください。</span><span class="sxs-lookup"><span data-stu-id="9e0f1-118">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e0f1-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="9e0f1-119">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridViewRow>  
 <xref:System.Windows.Forms.DataGridViewRow.DataBoundItem%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="9e0f1-120">Windows フォーム DataGridView コントロールでのデータの表示</span><span class="sxs-lookup"><span data-stu-id="9e0f1-120">Displaying Data in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="9e0f1-121">方法: オブジェクトを Windows フォーム DataGridView コントロールにバインドする</span><span class="sxs-lookup"><span data-stu-id="9e0f1-121">How to: Bind Objects to Windows Forms DataGridView Controls</span></span>](../../../../docs/framework/winforms/controls/how-to-bind-objects-to-windows-forms-datagridview-controls.md)
