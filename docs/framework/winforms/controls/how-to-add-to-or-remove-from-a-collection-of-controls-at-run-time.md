---
title: '方法: コントロールのコレクションに対して実行時にコントロールを追加または削除する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- run time [Windows Forms], removing controls
- controls [Windows Forms], adding using collections
- controls collections
- collections [Windows Forms], adding items
- run time [Windows Forms], adding controls
- controls [Windows Forms], removing using collections
ms.assetid: 771bf895-3d5f-469b-a324-3528f343657e
ms.openlocfilehash: a868632d6868e6a82c4fa135444279b8ef4dc7af
ms.sourcegitcommit: 621a5f6df00152006160987395b93b5b55f7ffcd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "66301410"
---
# <a name="how-to-add-to-or-remove-from-a-collection-of-controls-at-run-time"></a><span data-ttu-id="f5dcd-102">方法: コントロールのコレクションに対して実行時にコントロールを追加または削除する</span><span class="sxs-lookup"><span data-stu-id="f5dcd-102">How to: Add to or Remove from a Collection of Controls at Run Time</span></span>
<span data-ttu-id="f5dcd-103">アプリケーション開発の一般的なタスクをするコントロールを追加し、フォーム上のコンテナー コントロールからコントロールを削除する (など、<xref:System.Windows.Forms.Panel>または<xref:System.Windows.Forms.GroupBox>コントロール、またはフォーム自体)。</span><span class="sxs-lookup"><span data-stu-id="f5dcd-103">Common tasks in application development are adding controls to and removing controls from any container control on your forms (such as the <xref:System.Windows.Forms.Panel> or <xref:System.Windows.Forms.GroupBox> control, or even the form itself).</span></span> <span data-ttu-id="f5dcd-104">デザイン時に、コントロールをパネルやグループ ボックスに直接ドラッグすることができます。</span><span class="sxs-lookup"><span data-stu-id="f5dcd-104">At design time, controls can be dragged directly onto a panel or group box.</span></span> <span data-ttu-id="f5dcd-105">実行時には、これらのコントロールは `Controls` コレクションを保持し、それらにどのコントロールが置かれているかを追跡します。</span><span class="sxs-lookup"><span data-stu-id="f5dcd-105">At run time, these controls maintain a `Controls` collection, which keeps track of what controls are placed on them.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f5dcd-106">次のコード例は、コントロールのコレクションを保持する任意のコントロールに適用されます。</span><span class="sxs-lookup"><span data-stu-id="f5dcd-106">The following code example applies to any control that maintains a collection of controls within it.</span></span>  
  
### <a name="to-add-a-control-to-a-collection-programmatically"></a><span data-ttu-id="f5dcd-107">プログラムを使用して、コレクションにコントロールを追加するには</span><span class="sxs-lookup"><span data-stu-id="f5dcd-107">To add a control to a collection programmatically</span></span>  
  
1. <span data-ttu-id="f5dcd-108">追加するコントロールのインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="f5dcd-108">Create an instance of the control to be added.</span></span>  
  
2. <span data-ttu-id="f5dcd-109">新しいコントロールのプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="f5dcd-109">Set properties of the new control.</span></span>  
  
3. <span data-ttu-id="f5dcd-110">親コントロールの `Controls` コレクションにコントロールを追加します。</span><span class="sxs-lookup"><span data-stu-id="f5dcd-110">Add the control to the `Controls` collection of the parent control.</span></span>  
  
     <span data-ttu-id="f5dcd-111">次のコード例のインスタンスを作成する方法を示しています、<xref:System.Windows.Forms.Button>コントロール。</span><span class="sxs-lookup"><span data-stu-id="f5dcd-111">The following code example shows how to create an instance of the <xref:System.Windows.Forms.Button> control.</span></span> <span data-ttu-id="f5dcd-112">使用して、フォームが必要です、<xref:System.Windows.Forms.Panel>コントロールとボタンのイベント処理メソッドが作成される、 `NewPanelButton_Click`、既に存在します。</span><span class="sxs-lookup"><span data-stu-id="f5dcd-112">It requires a form with a <xref:System.Windows.Forms.Panel> control and that the event-handling method for the button being created, `NewPanelButton_Click`, already exists.</span></span>  
  
    ```vb  
    Public NewPanelButton As New Button()  
  
    Public Sub AddNewControl()  
       ' The Add method will accept as a parameter any object that derives  
       ' from the Control class. In this case, it is a Button control.  
       Panel1.Controls.Add(NewPanelButton)  
       ' The event handler indicated for the Click event in the code   
       ' below is used as an example. Substite the appropriate event  
       ' handler for your application.  
       AddHandler NewPanelButton.Click, AddressOf NewPanelButton_Click  
    End Sub  
    ```  
  
    ```csharp  
    public Button newPanelButton = new Button();  
  
    public void addNewControl()  
    {   
       // The Add method will accept as a parameter any object that derives  
       // from the Control class. In this case, it is a Button control.  
       panel1.Controls.Add(newPanelButton);  
       // The event handler indicated for the Click event in the code   
       // below is used as an example. Substitute the appropriate event  
       // handler for your application.  
       this.newPanelButton.Click += new System.EventHandler(this. NewPanelButton_Click);  
    }  
    ```  
  
### <a name="to-remove-controls-from-a-collection-programmatically"></a><span data-ttu-id="f5dcd-113">プログラムを使用してコレクションからコントロールを削除するには</span><span class="sxs-lookup"><span data-stu-id="f5dcd-113">To remove controls from a collection programmatically</span></span>  
  
1. <span data-ttu-id="f5dcd-114">イベントからイベント ハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="f5dcd-114">Remove the event handler from the event.</span></span> <span data-ttu-id="f5dcd-115">Visual Basic で使用して、 [RemoveHandler ステートメント](~/docs/visual-basic/language-reference/statements/removehandler-statement.md)キーワード、C#を使用して、 [-= 演算子](~/docs/csharp/language-reference/operators/subtraction-operator.md)します。</span><span class="sxs-lookup"><span data-stu-id="f5dcd-115">In Visual Basic, use the [RemoveHandler Statement](~/docs/visual-basic/language-reference/statements/removehandler-statement.md) keyword; in C#, use the [-= operator](~/docs/csharp/language-reference/operators/subtraction-operator.md).</span></span>  
  
2. <span data-ttu-id="f5dcd-116">`Remove` メソッドを使用して、パネルの `Controls` コレクションから目的のコントロールを削除します。</span><span class="sxs-lookup"><span data-stu-id="f5dcd-116">Use the `Remove` method to delete the desired control from the panel's `Controls` collection.</span></span>  
  
3. <span data-ttu-id="f5dcd-117">呼び出す、<xref:System.Windows.Forms.Control.Dispose%2A>コントロールによって使用されるすべてのリソースを解放します。</span><span class="sxs-lookup"><span data-stu-id="f5dcd-117">Call the <xref:System.Windows.Forms.Control.Dispose%2A> method to release all the resources used by the control.</span></span>  
  
    ```vb  
    Public Sub RemoveControl()  
    ' NOTE: The code below uses the instance of   
    ' the button (NewPanelButton) from the previous example.  
       If Panel1.Controls.Contains(NewPanelButton) Then  
          RemoveHandler NewPanelButton.Click, AddressOf _   
             NewPanelButton_Click  
          Panel1.Controls.Remove(NewPanelButton)  
          NewPanelButton.Dispose()  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void removeControl(object sender, System.EventArgs e)  
    {  
    // NOTE: The code below uses the instance of   
    // the button (newPanelButton) from the previous example.  
       if(panel1.Controls.Contains(newPanelButton))  
       {  
          this.newPanelButton.Click -= new System.EventHandler(this.   
             NewPanelButton_Click);  
          panel1.Controls.Remove(newPanelButton);  
          newPanelButton.Dispose();  
       }  
    }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="f5dcd-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="f5dcd-118">See also</span></span>

- <xref:System.Windows.Forms.Panel>
- [<span data-ttu-id="f5dcd-119">Panel コントロール</span><span class="sxs-lookup"><span data-stu-id="f5dcd-119">Panel Control</span></span>](panel-control-windows-forms.md)
