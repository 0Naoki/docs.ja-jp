---
title: '方法: Windows フォーム コントロールを DBNull データベース値にバインドします。'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- BindingSource component [Windows Forms], binding to DBNull values
- examples [Windows Forms], BindingSource component
- controls [Windows Forms], binding to DBNull values
ms.assetid: 96494e6f-5f40-4f83-af97-bbd7192c2af8
ms.openlocfilehash: b2a5c7234d2815da734ee291fef223f20744b81e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54658131"
---
# <a name="how-to-bind-windows-forms-controls-to-dbnull-database-values"></a><span data-ttu-id="7f9e1-102">方法: Windows フォーム コントロールを DBNull データベース値にバインドします。</span><span class="sxs-lookup"><span data-stu-id="7f9e1-102">How to: Bind Windows Forms Controls to DBNull Database Values</span></span>
<span data-ttu-id="7f9e1-103">データ ソースに Windows フォーム コントロールをバインドして、データ ソースが <xref:System.DBNull> 値を返す場合、イベントの処理、書式設定、または解析なしで、適切な値に置き換えることができます。</span><span class="sxs-lookup"><span data-stu-id="7f9e1-103">When you bind Windows Forms controls to a data source and the data source returns a <xref:System.DBNull> value, you can substitute an appropriate value without handling, formatting, or parsing events.</span></span> <span data-ttu-id="7f9e1-104"><xref:System.Windows.Forms.Binding.NullValue%2A> プロパティは、データ ソースの値を書式設定または解析する際、<xref:System.DBNull> を指定されたオブジェクトに変換します。</span><span class="sxs-lookup"><span data-stu-id="7f9e1-104">The <xref:System.Windows.Forms.Binding.NullValue%2A> property will convert <xref:System.DBNull> to a specified object when formatting or parsing the data source values.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7f9e1-105">例</span><span class="sxs-lookup"><span data-stu-id="7f9e1-105">Example</span></span>  
 <span data-ttu-id="7f9e1-106">次の例では、2 つの異なる状況で <xref:System.DBNull> の値をバインドする方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="7f9e1-106">The following example demonstrates how to bind a <xref:System.DBNull> value in two different situations.</span></span> <span data-ttu-id="7f9e1-107">1 つ目は、文字列のプロパティに対して <xref:System.Windows.Forms.Binding.NullValue%2A> を設定する方法を示し、2 つ目は、イメージのプロパティに対して <xref:System.Windows.Forms.Binding.NullValue%2A> を設定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="7f9e1-107">The first demonstrates how to set the <xref:System.Windows.Forms.Binding.NullValue%2A> for a string property; the second demonstrates how to set the <xref:System.Windows.Forms.Binding.NullValue%2A> for an image property.</span></span>  
  
 [!code-csharp[System.Windows.Forms.BindingDBNull#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BindingDBNull/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.BindingDBNull#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BindingDBNull/VB/form1.vb#1)]  
  
 <span data-ttu-id="7f9e1-108">バインドされたプロパティの種類と <xref:System.Windows.Forms.Binding.NullValue%2A> プロパティは同じにする必要があります。そうでないとエラーが発生し、<xref:System.Windows.Forms.Binding.NullValue%2A> の値はそれ以上処理されません。</span><span class="sxs-lookup"><span data-stu-id="7f9e1-108">The types of the bound property and the <xref:System.Windows.Forms.Binding.NullValue%2A> property must be the same or an error will result, and no further <xref:System.Windows.Forms.Binding.NullValue%2A> values will be processed.</span></span> <span data-ttu-id="7f9e1-109">このような場合は、例外はスローされません。</span><span class="sxs-lookup"><span data-stu-id="7f9e1-109">In this situation, an exception will not be thrown.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="7f9e1-110">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="7f9e1-110">Compiling the Code</span></span>  
 <span data-ttu-id="7f9e1-111">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="7f9e1-111">This example requires:</span></span>  
  
-   <span data-ttu-id="7f9e1-112">System、System.Data、System.Drawing、および System.Windows.Forms の各アセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="7f9e1-112">References to the System, System.Data, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="7f9e1-113">コマンドラインからこの例を Visual Basic または Visual c# の構築方法の詳細については、次を参照してください。 [、コマンドラインからビルドする](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md)または[コマンド ライン ビルドで csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)します。</span><span class="sxs-lookup"><span data-stu-id="7f9e1-113">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="7f9e1-114">新しいプロジェクトにコードを貼り付けることによって、この例では、Visual Studio を構築することもできます。</span><span class="sxs-lookup"><span data-stu-id="7f9e1-114">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="7f9e1-115">参照してください[方法。Visual Studio を使用して、完全な Windows フォームのコードの例をコンパイルして](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\))します。</span><span class="sxs-lookup"><span data-stu-id="7f9e1-115">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f9e1-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="7f9e1-116">See also</span></span>
- [<span data-ttu-id="7f9e1-117">BindingSource コンポーネント</span><span class="sxs-lookup"><span data-stu-id="7f9e1-117">BindingSource Component</span></span>](../../../../docs/framework/winforms/controls/bindingsource-component.md)
- [<span data-ttu-id="7f9e1-118">方法: エラーとデータ バインドで発生する例外を処理します。</span><span class="sxs-lookup"><span data-stu-id="7f9e1-118">How to: Handle Errors and Exceptions that Occur with Databinding</span></span>](../../../../docs/framework/winforms/controls/how-to-handle-errors-and-exceptions-that-occur-with-databinding.md)
- [<span data-ttu-id="7f9e1-119">方法: Windows フォーム コントロールを型にバインドします。</span><span class="sxs-lookup"><span data-stu-id="7f9e1-119">How to: Bind a Windows Forms Control to a Type</span></span>](../../../../docs/framework/winforms/controls/how-to-bind-a-windows-forms-control-to-a-type.md)
