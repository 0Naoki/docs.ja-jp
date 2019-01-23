---
title: PrintDocument コンポーネントの概要 (Windows フォーム)
ms.date: 03/30/2017
f1_keywords:
- PrintDocument
helpviewer_keywords:
- PrintDocument component [Windows Forms], about PrintDocument component
- printing [Windows Forms], PrintDocument component
ms.assetid: b59b4b60-dce5-42ca-8421-3a54a2f7bab0
ms.openlocfilehash: 2facbf0a567f81aa6debe2ca60f7f8eabc794bb0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54532345"
---
# <a name="printdocument-component-overview-windows-forms"></a><span data-ttu-id="e5c73-102">PrintDocument コンポーネントの概要 (Windows フォーム)</span><span class="sxs-lookup"><span data-stu-id="e5c73-102">PrintDocument Component Overview (Windows Forms)</span></span>
<span data-ttu-id="e5c73-103">Windows フォーム [PrintDocument](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md) コンポーネントを使用して、印刷対象を示すプロパティを設定し、Windows ベースのアプリケーション内でドキュメントを印刷できます。</span><span class="sxs-lookup"><span data-stu-id="e5c73-103">The Windows Forms [PrintDocument](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md) component is used to set the properties that describe what to print and the ability to print the document within Windows-based applications.</span></span> <span data-ttu-id="e5c73-104">このコンポーネントは、ドキュメント印刷のあらゆる側面を制御するために、[PrintDialog](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md) コンポーネントと組み合わせて使用できます。</span><span class="sxs-lookup"><span data-stu-id="e5c73-104">It can be used in conjunction with the [PrintDialog](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md) component to be in control of all aspects of document printing.</span></span>  
  
## <a name="working-with-the-printdocument-component"></a><span data-ttu-id="e5c73-105">PrintDocument コンポーネントの操作</span><span class="sxs-lookup"><span data-stu-id="e5c73-105">Working with the PrintDocument Component</span></span>  
 <span data-ttu-id="e5c73-106">2 つの主なシナリオを含む、<xref:System.Drawing.Printing.PrintDocument>コンポーネントします。</span><span class="sxs-lookup"><span data-stu-id="e5c73-106">Two of the main scenarios that involve the <xref:System.Drawing.Printing.PrintDocument> component are:</span></span>  
  
-   <span data-ttu-id="e5c73-107">簡易印刷ジョブ (個々のテキスト ファイルを印刷する場合など)。</span><span class="sxs-lookup"><span data-stu-id="e5c73-107">Simple print jobs, such as printing an individual text file.</span></span> <span data-ttu-id="e5c73-108">追加すると、このような場合、<xref:System.Drawing.Printing.PrintDocument>コンポーネントを Windows フォーム内のファイルを印刷するプログラミング ロジックを追加し、<xref:System.Drawing.Printing.PrintDocument.PrintPage>イベント ハンドラー。</span><span class="sxs-lookup"><span data-stu-id="e5c73-108">In such a case you would add the <xref:System.Drawing.Printing.PrintDocument> component to a Windows Form, then add programming logic that prints a file in the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event handler.</span></span> <span data-ttu-id="e5c73-109">プログラミング ロジック、<xref:System.Drawing.Printing.PrintDocument.Print%2A>ドキュメントを印刷する方法。</span><span class="sxs-lookup"><span data-stu-id="e5c73-109">The programming logic should culminate with the <xref:System.Drawing.Printing.PrintDocument.Print%2A> method to print the document.</span></span> <span data-ttu-id="e5c73-110">このメソッドは、送信、<xref:System.Drawing.Graphics>に含まれる、オブジェクト、<xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A>のプロパティ、<xref:System.Drawing.Printing.PrintPageEventArgs>プリンターへのクラス。</span><span class="sxs-lookup"><span data-stu-id="e5c73-110">This method sends a <xref:System.Drawing.Graphics> object, contained in the <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> property of the <xref:System.Drawing.Printing.PrintPageEventArgs> class, to the printer.</span></span> <span data-ttu-id="e5c73-111">使用してテキスト ドキュメントを印刷する方法を示す例については、<xref:System.Drawing.Printing.PrintDocument>コンポーネントを参照してください[方法。Windows フォームで複数ページのテキスト ファイルを印刷](../../../../docs/framework/winforms/advanced/how-to-print-a-multi-page-text-file-in-windows-forms.md)します。</span><span class="sxs-lookup"><span data-stu-id="e5c73-111">For an example that shows how to print a text document using the <xref:System.Drawing.Printing.PrintDocument> component, see [How to: Print a Multi-Page Text File in Windows Forms](../../../../docs/framework/winforms/advanced/how-to-print-a-multi-page-text-file-in-windows-forms.md).</span></span>  
  
-   <span data-ttu-id="e5c73-112">より複雑な印刷ジョブ (作成した印刷ロジックを再利用する場合など)。</span><span class="sxs-lookup"><span data-stu-id="e5c73-112">More complex print jobs, such as a situation where you will want to reuse printing logic you have written.</span></span> <span data-ttu-id="e5c73-113">このような場合は、新しいコンポーネントを派生させる、<xref:System.Drawing.Printing.PrintDocument>コンポーネントと上書き (を参照してください[オーバーライド](~/docs/visual-basic/language-reference/modifiers/overrides.md)Visual basic または[オーバーライド](~/docs/csharp/language-reference/keywords/override.md)のC#)、<xref:System.Drawing.Printing.PrintDocument.PrintPage>イベント。</span><span class="sxs-lookup"><span data-stu-id="e5c73-113">In such a case you would derive a new component from the <xref:System.Drawing.Printing.PrintDocument> component and override (see [Overrides](~/docs/visual-basic/language-reference/modifiers/overrides.md) for Visual Basic or [override](~/docs/csharp/language-reference/keywords/override.md) for C#) the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event.</span></span>  
  
 <span data-ttu-id="e5c73-114">フォームに追加されたとき、<xref:System.Drawing.Printing.PrintDocument>コンポーネント、Windows フォーム デザイナーの下部にあるトレイに表示されます。</span><span class="sxs-lookup"><span data-stu-id="e5c73-114">When it is added to a form, the <xref:System.Drawing.Printing.PrintDocument> component appears in the tray at the bottom of the Windows Forms Designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5c73-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="e5c73-115">See also</span></span>
- <xref:System.Drawing.Graphics>
- <xref:System.Drawing.Printing.PrintDocument>
- [<span data-ttu-id="e5c73-116">Windows フォームにおける印刷のサポート</span><span class="sxs-lookup"><span data-stu-id="e5c73-116">Windows Forms Print Support</span></span>](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md)
- [<span data-ttu-id="e5c73-117">PrintDocument コンポーネント</span><span class="sxs-lookup"><span data-stu-id="e5c73-117">PrintDocument Component</span></span>](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md)
