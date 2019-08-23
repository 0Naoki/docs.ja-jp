---
title: 内在コントロール
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [Windows Forms], constituent controls
- constituent controls [Windows Forms]
- user controls [Windows Forms], constituent controls
ms.assetid: 5565e720-198b-4bbd-a2bd-c447ba641798
ms.openlocfilehash: 522a1012fc7bdd54860b0538064ee073f7a761f7
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69918426"
---
# <a name="constituent-controls"></a><span data-ttu-id="93d28-102">内在コントロール</span><span class="sxs-lookup"><span data-stu-id="93d28-102">Constituent Controls</span></span>
<span data-ttu-id="93d28-103">ユーザー コントロールを構成するコントロール ("*内在コントロール*" と呼ばれます) は、カスタム グラフィックスのレンダリングに関してはそれほど柔軟ではありません。</span><span class="sxs-lookup"><span data-stu-id="93d28-103">The controls that make up a user control, or *constituent controls* as they are termed, are relatively inflexible when it comes to custom graphics rendering.</span></span> <span data-ttu-id="93d28-104">すべての Windows フォームコントロールは、独自の<xref:System.Windows.Forms.Control.OnPaint%2A>メソッドを使用して独自のレンダリングを処理します。</span><span class="sxs-lookup"><span data-stu-id="93d28-104">All Windows Forms controls handle their own rendering through their own <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span> <span data-ttu-id="93d28-105">このメソッドは保護されているため、開発者はアクセスできず、したがってコントロールが描画されるときに実行を防ぐことはできません。</span><span class="sxs-lookup"><span data-stu-id="93d28-105">Because this method is protected, it is not accessible to the developer, and thus cannot be prevented from executing when the control is painted.</span></span> <span data-ttu-id="93d28-106">ただし、これは、内在コントロールの外観に影響を与えるコードを追加できないという意味ではありません。</span><span class="sxs-lookup"><span data-stu-id="93d28-106">This does not mean, however, that you cannot add code to affect the appearance of constituent controls.</span></span> <span data-ttu-id="93d28-107">イベント ハンドラーを追加することで、追加のレンダリングを実現できます。</span><span class="sxs-lookup"><span data-stu-id="93d28-107">Additional rendering can be accomplished by adding an event handler.</span></span> <span data-ttu-id="93d28-108">たとえば、という名前<xref:System.Windows.Forms.UserControl> `MyButton`のボタンを使用してを作成したとします。</span><span class="sxs-lookup"><span data-stu-id="93d28-108">For example, suppose you were authoring a <xref:System.Windows.Forms.UserControl> with a button named `MyButton`.</span></span> <span data-ttu-id="93d28-109">によって<xref:System.Web.UI.WebControls.Button>提供された内容を超えて追加のレンダリングを使用する場合は、次のようなコードをユーザーコントロールに追加します。</span><span class="sxs-lookup"><span data-stu-id="93d28-109">If you wished to have additional rendering beyond what was provided by the <xref:System.Web.UI.WebControls.Button>, you would add code to your user control similar to the following:</span></span>  
  
```vb  
Public Sub MyPaint(ByVal sender as Object, e as PaintEventArgs) Handles _  
   MyButton.Paint  
   'Additional rendering code goes here  
End Sub  
```  
  
```csharp  
// Add the event handler to the button's Paint event.  
MyButton.Paint +=   
   new System.Windows.Forms.PaintEventHandler (this.MyPaint);  
// Create the custom painting method.  
protected void MyPaint (object sender,   
System.Windows.Forms.PaintEventArgs e)  
{  
   // Additional rendering code goes here.  
}  
```  
  
> [!NOTE]
> <span data-ttu-id="93d28-110">などの一部の Windows フォームコントロール<xref:System.Windows.Forms.TextBox>は、Windows によって直接描画されます。</span><span class="sxs-lookup"><span data-stu-id="93d28-110">Some Windows Forms controls, such as <xref:System.Windows.Forms.TextBox>, are painted directly by Windows.</span></span> <span data-ttu-id="93d28-111">これらのインスタンス<xref:System.Windows.Forms.Control.OnPaint%2A>では、メソッドは呼び出されません。したがって、上記の例は呼び出されません。</span><span class="sxs-lookup"><span data-stu-id="93d28-111">In these instances, the <xref:System.Windows.Forms.Control.OnPaint%2A> method is never called, and thus the above example will never be called.</span></span>  
  
 <span data-ttu-id="93d28-112">この例は、`MyButton.Paint` イベントが実行されるたびに実行するメソッドを作成し、それによって追加のグラフィカル表示をコントロールに追加します。</span><span class="sxs-lookup"><span data-stu-id="93d28-112">This creates a method that executes every time the `MyButton.Paint` event executes, thereby adding additional graphical representation to your control.</span></span> <span data-ttu-id="93d28-113">これにより `MyButton.OnPaint` の実行は妨げられないので、カスタム描画に加えて、ボタンによって通常実行されるすべての描画が実行されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="93d28-113">Note that this does not prevent the execution of `MyButton.OnPaint`, and thus all of the painting usually performed by a button will still be performed in addition to your custom painting.</span></span> <span data-ttu-id="93d28-114">GDI+ テクノロジとカスタム レンダリングについて詳しくは、「[Creating Graphical Images with GDI+](../advanced/how-to-create-graphics-objects-for-drawing.md)」 (GDI+ でのグラフィカル イメージの作成) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="93d28-114">For details about GDI+ technology and custom rendering, see the [Creating Graphical Images with GDI+](../advanced/how-to-create-graphics-objects-for-drawing.md).</span></span> <span data-ttu-id="93d28-115">コントロールの表示を独自のものにしたい場合の最善の方法は、継承コントロールを作成し、カスタム レンダリング コードをそこに記述するというものです。</span><span class="sxs-lookup"><span data-stu-id="93d28-115">If you wish to have a unique representation of your control, your best course of action is to create an inherited control, and to write custom rendering code for it.</span></span> <span data-ttu-id="93d28-116">詳しくは、「[ユーザー描画コントロール](user-drawn-controls.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="93d28-116">For details, see [User-Drawn Controls](user-drawn-controls.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93d28-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="93d28-117">See also</span></span>

- <xref:System.Windows.Forms.UserControl>
- <xref:System.Windows.Forms.Control.OnPaint%2A>
- [<span data-ttu-id="93d28-118">ユーザー描画コントロール</span><span class="sxs-lookup"><span data-stu-id="93d28-118">User-Drawn Controls</span></span>](user-drawn-controls.md)
- [<span data-ttu-id="93d28-119">方法: 描画用のグラフィックスオブジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="93d28-119">How to: Create Graphics Objects for Drawing</span></span>](../advanced/how-to-create-graphics-objects-for-drawing.md)
- [<span data-ttu-id="93d28-120">さまざまなカスタム コントロール</span><span class="sxs-lookup"><span data-stu-id="93d28-120">Varieties of Custom Controls</span></span>](varieties-of-custom-controls.md)
