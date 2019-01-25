---
title: '方法: アプリケーション間でドラッグ アンド ドロップ操作を実行します。'
ms.date: 03/30/2017
helpviewer_keywords:
- drag and drop [Windows Forms], between applications
ms.assetid: fa347436-2b12-4dd6-8507-59d7241f6a06
ms.openlocfilehash: 89b1b89c01ba80393e0965858d7767d5c9029003
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54718429"
---
# <a name="how-to-perform-drag-and-drop-operations-between-applications"></a><span data-ttu-id="56c77-102">方法: アプリケーション間でドラッグ アンド ドロップ操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="56c77-102">How to: Perform Drag-and-Drop Operations Between Applications</span></span>
<span data-ttu-id="56c77-103">アプリケーション間でのドラッグ アンド ドロップ操作の実行は、アプリケーション内での場合と同じですが、両方のアプリケーションが <xref:System.Windows.Forms.DragEventArgs.AllowedEffect%2A> プロパティと <xref:System.Windows.Forms.DragEventArgs.Effect%2A> プロパティの間で確立された "契約" に従って動作する必要があります。</span><span class="sxs-lookup"><span data-stu-id="56c77-103">Performing drag-and-drop operations between applications is no different than enabling this action within an application, as long as both applications involved behave according to the "contract" established between the <xref:System.Windows.Forms.DragEventArgs.AllowedEffect%2A> and <xref:System.Windows.Forms.DragEventArgs.Effect%2A> properties.</span></span>  
  
 <span data-ttu-id="56c77-104">次の手順では、作成した Windows ベースのアプリケーションと、Windows オペレーティング システムに含まれるワードパッドというワード プロセッサを使用して、アプリケーション間でのドラッグ アンド ドロップ操作を行います。</span><span class="sxs-lookup"><span data-stu-id="56c77-104">In the following procedure, you will use a Windows-based application you create and the WordPad word processor that is included with the Windows operating system to perform drag-and-drop operations between applications.</span></span> <span data-ttu-id="56c77-105">ワードパッドには、ドラッグ アンド ドロップされたテキストに対して実行できる処理のセットが定義されています。コードを記述する Windows ベースのアプリケーションはこれらの効果に従って動作するため、ドラッグ アンド ドロップ操作を正常に完了できます。</span><span class="sxs-lookup"><span data-stu-id="56c77-105">WordPad has a certain set of allowed effects for text being dragged and dropped; the Windows-based application you will write code for will work with these effects so that drag-and-drop operations may be completed successfully.</span></span>  
  
### <a name="to-perform-a-drag-and-drop-procedure-between-applications"></a><span data-ttu-id="56c77-106">アプリケーション間でドラッグ アンド ドロップ手順を実行するには</span><span class="sxs-lookup"><span data-stu-id="56c77-106">To perform a drag-and-drop procedure between applications</span></span>  
  
1.  <span data-ttu-id="56c77-107">新しい Windows フォーム アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="56c77-107">Create a new Windows Forms application.</span></span>  
  
2.  <span data-ttu-id="56c77-108">フォームに <xref:System.Windows.Forms.TextBox> コントロールを追加します。</span><span class="sxs-lookup"><span data-stu-id="56c77-108">Add a <xref:System.Windows.Forms.TextBox> control to your form.</span></span>  
  
3.  <span data-ttu-id="56c77-109">ドロップされたデータを受け取るように <xref:System.Windows.Forms.TextBox> コントロールを設定します。</span><span class="sxs-lookup"><span data-stu-id="56c77-109">Configure the <xref:System.Windows.Forms.TextBox> control to receive dropped data.</span></span>  
  
     <span data-ttu-id="56c77-110">詳細については、「[チュートリアル:Windows フォームにおけるドラッグ アンド ドロップ操作の実行](../../../../docs/framework/winforms/advanced/walkthrough-performing-a-drag-and-drop-operation-in-windows-forms.md)します。</span><span class="sxs-lookup"><span data-stu-id="56c77-110">For more information, see [Walkthrough: Performing a Drag-and-Drop Operation in Windows Forms](../../../../docs/framework/winforms/advanced/walkthrough-performing-a-drag-and-drop-operation-in-windows-forms.md).</span></span>  
  
4.  <span data-ttu-id="56c77-111">作成した Windows ベースのアプリケーションを実行し、アプリケーションの実行中にワードパッドを起動します。</span><span class="sxs-lookup"><span data-stu-id="56c77-111">Run your Windows-based application, and while the application is running, run WordPad.</span></span>  
  
     <span data-ttu-id="56c77-112">ワードパッドは、Windows によってインストールされるテキスト エディターであり、ドラッグ アンド ドロップ操作をサポートします。</span><span class="sxs-lookup"><span data-stu-id="56c77-112">WordPad is a text editor installed by Windows that allows drag-and-drop operations.</span></span> <span data-ttu-id="56c77-113">キーを押してアクセス、**開始**ボタンをクリックして**実行**、」と入力し、`WordPad`のテキスト ボックスに、**実行**をクリックしてダイアログボックス**OK**します。</span><span class="sxs-lookup"><span data-stu-id="56c77-113">It is accessible by pressing the **Start** button, selecting **Run**, and then typing `WordPad` into the text box of the **Run** dialog box and clicking **OK**.</span></span>  
  
5.  <span data-ttu-id="56c77-114">ワードパッドが起動したら、テキストの文字列を入力します。</span><span class="sxs-lookup"><span data-stu-id="56c77-114">Once WordPad is open, type a string of text into it.</span></span>  
  
6.  <span data-ttu-id="56c77-115">マウスを使用してテキストを選択し、選択したテキストを Windows ベースのアプリケーションの <xref:System.Windows.Forms.TextBox> コントロールにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="56c77-115">Using the mouse, select the text, and then drag the selected text over to the <xref:System.Windows.Forms.TextBox> control in your Windows-based application.</span></span>  
  
     <span data-ttu-id="56c77-116">マウスを <xref:System.Windows.Forms.TextBox> コントロールに移動すると (そして、その結果 <xref:System.Windows.Forms.Control.DragEnter> イベントが発生すると)、マウス ポインターの形が変化し、選択したテキストを <xref:System.Windows.Forms.TextBox> コントロールにドロップできます。</span><span class="sxs-lookup"><span data-stu-id="56c77-116">Observe that when you mouse over the <xref:System.Windows.Forms.TextBox> control (and, consequently, raise the <xref:System.Windows.Forms.Control.DragEnter> event), the cursor changes, and you can drop the selected text into the <xref:System.Windows.Forms.TextBox> control.</span></span>  
  
     <span data-ttu-id="56c77-117">また、テキスト文字列をワードパッドにドラッグ アンド ドロップできるように <xref:System.Windows.Forms.TextBox> コントロールを設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="56c77-117">Additionally, you can configure your <xref:System.Windows.Forms.TextBox> control to allow text strings to be dragged and dropped into WordPad.</span></span> <span data-ttu-id="56c77-118">詳細については、「[チュートリアル:Windows フォームにおけるドラッグ アンド ドロップ操作の実行](../../../../docs/framework/winforms/advanced/walkthrough-performing-a-drag-and-drop-operation-in-windows-forms.md)します。</span><span class="sxs-lookup"><span data-stu-id="56c77-118">For more information, see [Walkthrough: Performing a Drag-and-Drop Operation in Windows Forms](../../../../docs/framework/winforms/advanced/walkthrough-performing-a-drag-and-drop-operation-in-windows-forms.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56c77-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="56c77-119">See also</span></span>
- [<span data-ttu-id="56c77-120">方法: データをクリップボードに追加します。</span><span class="sxs-lookup"><span data-stu-id="56c77-120">How to: Add Data to the Clipboard</span></span>](../../../../docs/framework/winforms/advanced/how-to-add-data-to-the-clipboard.md)
- [<span data-ttu-id="56c77-121">方法: クリップボードからデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="56c77-121">How to: Retrieve Data from the Clipboard</span></span>](../../../../docs/framework/winforms/advanced/how-to-retrieve-data-from-the-clipboard.md)
- [<span data-ttu-id="56c77-122">ドラッグ アンド ドロップ操作とクリップボードのサポート</span><span class="sxs-lookup"><span data-stu-id="56c77-122">Drag-and-Drop Operations and Clipboard Support</span></span>](../../../../docs/framework/winforms/advanced/drag-and-drop-operations-and-clipboard-support.md)
