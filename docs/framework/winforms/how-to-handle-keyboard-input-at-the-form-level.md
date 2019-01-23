---
title: '方法: フォーム レベルでキーボード入力を処理します。'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- keyboard input [Windows Forms], at form level
- Windows Forms, handling keyboard input
- keyboards [Windows Forms], form-level input
ms.assetid: d7f8b390-dc91-42d2-ae0f-2ffa388127ad
ms.openlocfilehash: ba17788933cb87215dc66d248357b3333ec04838
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54573371"
---
# <a name="how-to-handle-keyboard-input-at-the-form-level"></a><span data-ttu-id="8ef41-102">方法: フォーム レベルでキーボード入力を処理します。</span><span class="sxs-lookup"><span data-stu-id="8ef41-102">How to: Handle Keyboard Input at the Form Level</span></span>
<span data-ttu-id="8ef41-103">Windows フォームでは、キーボード メッセージがコントロールに到達する前に、それらのメッセージをフォーム レベルで処理できます。</span><span class="sxs-lookup"><span data-stu-id="8ef41-103">Windows Forms provides the ability to handle keyboard messages at the form level, before the messages reach a control.</span></span> <span data-ttu-id="8ef41-104">ここでは、このタスクを実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8ef41-104">This topic shows how to accomplish this task.</span></span>  
  
### <a name="to-handle-a-keyboard-message-at-the-form-level"></a><span data-ttu-id="8ef41-105">キーボード入力をフォーム レベルで処理するには</span><span class="sxs-lookup"><span data-stu-id="8ef41-105">To handle a keyboard message at the form level</span></span>  
  
-   <span data-ttu-id="8ef41-106">スタートアップ フォームの <xref:System.Windows.Forms.Control.KeyPress> イベントまたは <xref:System.Windows.Forms.Control.KeyDown> イベントを処理し、このフォームの <xref:System.Windows.Forms.Form.KeyPreview%2A> プロパティを `true` に設定して、キーボード メッセージがフォーム上のコントロールに到達する前にフォームによって受け取られるようにします。</span><span class="sxs-lookup"><span data-stu-id="8ef41-106">Handle the <xref:System.Windows.Forms.Control.KeyPress> or <xref:System.Windows.Forms.Control.KeyDown> event of the startup form, and set the <xref:System.Windows.Forms.Form.KeyPreview%2A> property of the form to `true` so that keyboard messages are received by the form before they reach any controls on the form.</span></span> <span data-ttu-id="8ef41-107">次のコード例では、<xref:System.Windows.Forms.Control.KeyPress> イベントを処理して、すべての数値キーを検出し、"1"、"4"、および "7" の各キーを使用します。</span><span class="sxs-lookup"><span data-stu-id="8ef41-107">The following code example handles the <xref:System.Windows.Forms.Control.KeyPress> event by detecting all of the number keys and consuming '1', '4', and '7'.</span></span>  
  
     [!code-cpp[System.Windows.Forms.KeyboardInputForm#10](../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInputForm/cpp/form1.cpp#10)]
     [!code-csharp[System.Windows.Forms.KeyboardInputForm#10](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInputForm/CS/form1.cs#10)]
     [!code-vb[System.Windows.Forms.KeyboardInputForm#10](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInputForm/VB/form1.vb#10)]  
  
## <a name="example"></a><span data-ttu-id="8ef41-108">例</span><span class="sxs-lookup"><span data-stu-id="8ef41-108">Example</span></span>  
 <span data-ttu-id="8ef41-109">次のコード例は、上の例の完全なアプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="8ef41-109">The following code example is the entire application for the above example.</span></span> <span data-ttu-id="8ef41-110">このアプリケーションには、<xref:System.Windows.Forms.TextBox> の他に、<xref:System.Windows.Forms.TextBox> からフォーカスを移動できるようにするいくつかのコントロールが含まれています。</span><span class="sxs-lookup"><span data-stu-id="8ef41-110">The application includes a <xref:System.Windows.Forms.TextBox> along with several other controls that allow you to move focus from the <xref:System.Windows.Forms.TextBox>.</span></span> <span data-ttu-id="8ef41-111">メイン <xref:System.Windows.Forms.Form> の <xref:System.Windows.Forms.Control.KeyPress> イベントは "1"、"4"、および "7" の各キーを使用し、<xref:System.Windows.Forms.TextBox> の <xref:System.Windows.Forms.Control.KeyPress> イベントは "2"、"5"、および "8" の各キーを使用します。残りのキーは表示されるだけです。</span><span class="sxs-lookup"><span data-stu-id="8ef41-111">The <xref:System.Windows.Forms.Control.KeyPress> event of the main <xref:System.Windows.Forms.Form> consumes '1', '4', and '7', and the <xref:System.Windows.Forms.Control.KeyPress> event of the <xref:System.Windows.Forms.TextBox> consumes '2', '5', and '8' while displaying the remaining keys.</span></span> <span data-ttu-id="8ef41-112"><xref:System.Windows.Forms.TextBox> にフォーカスがあるときに数値キーを押すと生成される <xref:System.Windows.Forms.MessageBox> 出力と、他のコントロールのいずれかにフォーカスがあるときに数値キーを押すと生成される <xref:System.Windows.Forms.MessageBox> 出力を比較してください。</span><span class="sxs-lookup"><span data-stu-id="8ef41-112">Compare the <xref:System.Windows.Forms.MessageBox> output when you press a number key while the <xref:System.Windows.Forms.TextBox> has focus with the <xref:System.Windows.Forms.MessageBox> output when you press a number key while focus is on one of the other controls.</span></span>  
  
 [!code-cpp[System.Windows.Forms.KeyBoardInputForm#0](../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInputForm/cpp/form1.cpp#0)]
 [!code-csharp[System.Windows.Forms.KeyBoardInputForm#0](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInputForm/CS/form1.cs#0)]
 [!code-vb[System.Windows.Forms.KeyBoardInputForm#0](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInputForm/VB/form1.vb#0)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="8ef41-113">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="8ef41-113">Compiling the Code</span></span>  
 <span data-ttu-id="8ef41-114">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="8ef41-114">This example requires:</span></span>  
  
-   <span data-ttu-id="8ef41-115">System、System.Drawing、および System.Windows.Forms の各アセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="8ef41-115">References to the System, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="8ef41-116">コマンドラインからこの例を Visual Basic または Visual c# の構築方法の詳細については、次を参照してください。 [、コマンドラインからビルドする](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md)または[コマンド ライン ビルドで csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)します。</span><span class="sxs-lookup"><span data-stu-id="8ef41-116">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="8ef41-117">新しいプロジェクトにコードを貼り付けることによって、この例では、Visual Studio を構築することもできます。</span><span class="sxs-lookup"><span data-stu-id="8ef41-117">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="8ef41-118">参照してください[方法。Visual Studio を使用して、完全な Windows フォームのコードの例をコンパイルして](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\))します。</span><span class="sxs-lookup"><span data-stu-id="8ef41-118">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ef41-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="8ef41-119">See also</span></span>
- [<span data-ttu-id="8ef41-120">Windows フォーム アプリケーションにおけるキーボード入力</span><span class="sxs-lookup"><span data-stu-id="8ef41-120">Keyboard Input in a Windows Forms Application</span></span>](../../../docs/framework/winforms/keyboard-input-in-a-windows-forms-application.md)
