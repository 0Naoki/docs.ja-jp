---
title: '方法: 描画の Graphics オブジェクトを作成します。'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- graphics [Windows Forms], creating
- images [Windows Forms], creating
- GDI+, creating images
ms.assetid: 162861f9-f050-445e-8abb-b2c43a918b8b
ms.openlocfilehash: e609fbff29d058c04a839a5dcb79aab16a518298
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/09/2019
ms.locfileid: "57709052"
---
# <a name="how-to-create-graphics-objects-for-drawing"></a><span data-ttu-id="59976-102">方法: 描画の Graphics オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="59976-102">How to: Create Graphics Objects for Drawing</span></span>
<span data-ttu-id="59976-103">直線と図形を描画することができます、前に、テキストのレンダリングまたは表示し、操作を使用したイメージ[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]、作成する必要がある、<xref:System.Drawing.Graphics>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="59976-103">Before you can draw lines and shapes, render text, or display and manipulate images with [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], you need to create a <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="59976-104"><xref:System.Drawing.Graphics>オブジェクトが表す、[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]描画面、およびグラフィカル イメージを作成するために使用するオブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="59976-104">The <xref:System.Drawing.Graphics> object represents a [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] drawing surface, and is the object that is used to create graphical images.</span></span>  
  
 <span data-ttu-id="59976-105">グラフィックスを操作には、2 つの手順があります。</span><span class="sxs-lookup"><span data-stu-id="59976-105">There are two steps in working with graphics:</span></span>  
  
1.  <span data-ttu-id="59976-106">作成、<xref:System.Drawing.Graphics>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="59976-106">Creating a <xref:System.Drawing.Graphics> object.</span></span>  
  
2.  <span data-ttu-id="59976-107">使用して、<xref:System.Drawing.Graphics>直線と図形の描画、テキストのレンダリングまたは表示、およびイメージを操作するオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="59976-107">Using the <xref:System.Drawing.Graphics> object to draw lines and shapes, render text, or display and manipulate images.</span></span>  
  
## <a name="creating-a-graphics-object"></a><span data-ttu-id="59976-108">グラフィックス オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="59976-108">Creating a Graphics Object</span></span>  
 <span data-ttu-id="59976-109">グラフィックス オブジェクトは、さまざまな方法で作成できます。</span><span class="sxs-lookup"><span data-stu-id="59976-109">A graphics object can be created in a variety of ways.</span></span>  
  
#### <a name="to-create-a-graphics-object"></a><span data-ttu-id="59976-110">グラフィックス オブジェクトを作成するには</span><span class="sxs-lookup"><span data-stu-id="59976-110">To create a graphics object</span></span>  
  
-   <span data-ttu-id="59976-111">一部として、グラフィックス オブジェクトへの参照を受け取る、<xref:System.Windows.Forms.PaintEventArgs>で、<xref:System.Windows.Forms.Control.Paint>フォームまたはコントロールのイベント。</span><span class="sxs-lookup"><span data-stu-id="59976-111">Receive a reference to a graphics object as part of the <xref:System.Windows.Forms.PaintEventArgs> in the <xref:System.Windows.Forms.Control.Paint> event of a form or control.</span></span> <span data-ttu-id="59976-112">これは、グラフィックス オブジェクトへの参照を取得する方法、コントロールの描画コードを作成するときに、通常は。</span><span class="sxs-lookup"><span data-stu-id="59976-112">This is usually how you obtain a reference to a graphics object when creating painting code for a control.</span></span> <span data-ttu-id="59976-113">同様に、取得することも、グラフィックス オブジェクトのプロパティとして、<xref:System.Drawing.Printing.PrintPageEventArgs>処理するときに、<xref:System.Drawing.Printing.PrintDocument.PrintPage>イベントを<xref:System.Drawing.Printing.PrintDocument>します。</span><span class="sxs-lookup"><span data-stu-id="59976-113">Similarly, you can also obtain a graphics object as a property of the <xref:System.Drawing.Printing.PrintPageEventArgs> when handling the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event for a <xref:System.Drawing.Printing.PrintDocument>.</span></span>  
  
     <span data-ttu-id="59976-114">- または -</span><span class="sxs-lookup"><span data-stu-id="59976-114">-or-</span></span>  
  
-   <span data-ttu-id="59976-115">呼び出す、<xref:System.Windows.Forms.Control.CreateGraphics%2A>コントロールまたはフォームへの参照を取得する方法、<xref:System.Drawing.Graphics>コントロールまたはフォームの描画サーフェイスを表すオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="59976-115">Call the <xref:System.Windows.Forms.Control.CreateGraphics%2A> method of a control or form to obtain a reference to a <xref:System.Drawing.Graphics> object that represents the drawing surface of that control or form.</span></span> <span data-ttu-id="59976-116">フォームまたは既に存在しているコントロールを描画する場合は、このメソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="59976-116">Use this method if you want to draw on a form or control that already exists.</span></span>  
  
     <span data-ttu-id="59976-117">- または -</span><span class="sxs-lookup"><span data-stu-id="59976-117">-or-</span></span>  
  
-   <span data-ttu-id="59976-118">作成、<xref:System.Drawing.Graphics>オブジェクトから継承する任意のオブジェクトから<xref:System.Drawing.Image>します。</span><span class="sxs-lookup"><span data-stu-id="59976-118">Create a <xref:System.Drawing.Graphics> object from any object that inherits from <xref:System.Drawing.Image>.</span></span> <span data-ttu-id="59976-119">この方法は、既存のイメージを変更するときに便利です。</span><span class="sxs-lookup"><span data-stu-id="59976-119">This approach is useful when you want to alter an already existing image.</span></span>  
  
     <span data-ttu-id="59976-120">次のセクションでは、これらの各プロセスの詳細を提供します。</span><span class="sxs-lookup"><span data-stu-id="59976-120">The following sections give details about each of these processes.</span></span>  
  
## <a name="painteventargs-in-the-paint-event-handler"></a><span data-ttu-id="59976-121">ペイントのイベント ハンドラーで PaintEventArgs</span><span class="sxs-lookup"><span data-stu-id="59976-121">PaintEventArgs in the Paint Event Handler</span></span>  
 <span data-ttu-id="59976-122">プログラミングを行う際、<xref:System.Windows.Forms.PaintEventHandler>コントロールまたは<xref:System.Drawing.Printing.PrintDocument.PrintPage>の<xref:System.Drawing.Printing.PrintDocument>、グラフィックス オブジェクトは、いずれかのプロパティとして提供されます<xref:System.Windows.Forms.PaintEventArgs>または<xref:System.Drawing.Printing.PrintPageEventArgs>します。</span><span class="sxs-lookup"><span data-stu-id="59976-122">When programming the <xref:System.Windows.Forms.PaintEventHandler> for controls or the <xref:System.Drawing.Printing.PrintDocument.PrintPage> for a <xref:System.Drawing.Printing.PrintDocument>, a graphics object is provided as one of the properties of <xref:System.Windows.Forms.PaintEventArgs> or <xref:System.Drawing.Printing.PrintPageEventArgs>.</span></span>  
  
#### <a name="to-obtain-a-reference-to-a-graphics-object-from-the-painteventargs-in-the-paint-event"></a><span data-ttu-id="59976-123">描画イベントで PaintEventArgs からグラフィックス オブジェクトへの参照を取得するには</span><span class="sxs-lookup"><span data-stu-id="59976-123">To obtain a reference to a Graphics object from the PaintEventArgs in the Paint event</span></span>  
  
1.  <span data-ttu-id="59976-124">宣言、<xref:System.Drawing.Graphics>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="59976-124">Declare the <xref:System.Drawing.Graphics> object.</span></span>  
  
2.  <span data-ttu-id="59976-125">参照する変数を割り当てる、<xref:System.Drawing.Graphics>の一部として渡されたオブジェクト、<xref:System.Windows.Forms.PaintEventArgs>します。</span><span class="sxs-lookup"><span data-stu-id="59976-125">Assign the variable to refer to the <xref:System.Drawing.Graphics> object passed as part of the <xref:System.Windows.Forms.PaintEventArgs>.</span></span>  
  
3.  <span data-ttu-id="59976-126">フォームまたはコントロールを描画するコードを挿入します。</span><span class="sxs-lookup"><span data-stu-id="59976-126">Insert code to paint the form or control.</span></span>  
  
     <span data-ttu-id="59976-127">次の例を参照する方法を示しています、<xref:System.Drawing.Graphics>オブジェクトから、<xref:System.Windows.Forms.PaintEventArgs>で、<xref:System.Windows.Forms.Control.Paint>イベント。</span><span class="sxs-lookup"><span data-stu-id="59976-127">The following example shows how to reference a <xref:System.Drawing.Graphics> object from the <xref:System.Windows.Forms.PaintEventArgs> in the <xref:System.Windows.Forms.Control.Paint> event:</span></span>  
  
    ```vb  
    Private Sub Form1_Paint(sender As Object, pe As PaintEventArgs) Handles _  
       MyBase.Paint  
       ' Declares the Graphics object and sets it to the Graphics object  
       ' supplied in the PaintEventArgs.  
       Dim g As Graphics = pe.Graphics  
       ' Insert code to paint the form here.  
    End Sub  
    ```  
  
    ```csharp  
    private void Form1_Paint(object sender,   
       System.Windows.Forms.PaintEventArgs pe)   
    {  
       // Declares the Graphics object and sets it to the Graphics object  
       // supplied in the PaintEventArgs.  
       Graphics g = pe.Graphics;  
       // Insert code to paint the form here.  
    }  
    ```  
  
    ```cpp  
    private:  
       void Form1_Paint(System::Object ^ sender,  
          System::Windows::Forms::PaintEventArgs ^ pe)  
       {  
          // Declares the Graphics object and sets it to the Graphics object  
          // supplied in the PaintEventArgs.  
          Graphics ^ g = pe->Graphics;  
          // Insert code to paint the form here.  
       }  
    ```  
  
## <a name="creategraphics-method"></a><span data-ttu-id="59976-128">CreateGraphics メソッド</span><span class="sxs-lookup"><span data-stu-id="59976-128">CreateGraphics Method</span></span>  
 <span data-ttu-id="59976-129">使用することも、<xref:System.Windows.Forms.Control.CreateGraphics%2A>コントロールまたはフォームへの参照を取得する方法、<xref:System.Drawing.Graphics>コントロールまたはフォームの描画サーフェイスを表すオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="59976-129">You can also use the <xref:System.Windows.Forms.Control.CreateGraphics%2A> method of a control or form to obtain a reference to a <xref:System.Drawing.Graphics> object that represents the drawing surface of that control or form.</span></span>  
  
#### <a name="to-create-a-graphics-object-with-the-creategraphics-method"></a><span data-ttu-id="59976-130">CreateGraphics メソッドを使用して、グラフィックス オブジェクトを作成するには</span><span class="sxs-lookup"><span data-stu-id="59976-130">To create a Graphics object with the CreateGraphics method</span></span>  
  
-   <span data-ttu-id="59976-131">呼び出す、<xref:System.Windows.Forms.Control.CreateGraphics%2A>なるグラフィックスをレンダリングするフォームまたはコントロールのメソッド。</span><span class="sxs-lookup"><span data-stu-id="59976-131">Call the <xref:System.Windows.Forms.Control.CreateGraphics%2A> method of the form or control upon which you want to render graphics.</span></span>  
  
    ```vb  
    Dim g as Graphics  
    ' Sets g to a Graphics object representing the drawing surface of the  
    ' control or form g is a member of.  
    g = Me.CreateGraphics  
    ```  
  
    ```csharp  
    Graphics g;  
    // Sets g to a graphics object representing the drawing surface of the  
    // control or form g is a member of.  
    g = this.CreateGraphics();  
    ```  
  
    ```cpp  
    Graphics ^ g;  
    // Sets g to a graphics object representing the drawing surface of the  
    // control or form g is a member of.  
    g = this->CreateGraphics();  
    ```  
  
## <a name="create-from-an-image-object"></a><span data-ttu-id="59976-132">イメージ オブジェクトから作成します。</span><span class="sxs-lookup"><span data-stu-id="59976-132">Create from an Image Object</span></span>  
 <span data-ttu-id="59976-133">さらから派生した任意のオブジェクトから graphics オブジェクトを作成することができます、<xref:System.Drawing.Image>クラス。</span><span class="sxs-lookup"><span data-stu-id="59976-133">Additionally, you can create a graphics object from any object that derives from the <xref:System.Drawing.Image> class.</span></span>  
  
#### <a name="to-create-a-graphics-object-from-an-image"></a><span data-ttu-id="59976-134">イメージから Graphics オブジェクトを作成するには</span><span class="sxs-lookup"><span data-stu-id="59976-134">To create a Graphics object from an Image</span></span>  
  
-   <span data-ttu-id="59976-135">呼び出す、<xref:System.Drawing.Graphics.FromImage%2A?displayProperty=nameWithType>メソッドを作成したいイメージの変数の名前を指定して、<xref:System.Drawing.Graphics>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="59976-135">Call the <xref:System.Drawing.Graphics.FromImage%2A?displayProperty=nameWithType> method, supplying the name of the Image variable from which you want to create a <xref:System.Drawing.Graphics> object.</span></span>  
  
     <span data-ttu-id="59976-136">次の例は、使用する方法を示します、<xref:System.Drawing.Bitmap>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="59976-136">The following example shows how to use a <xref:System.Drawing.Bitmap> object:</span></span>  
  
    ```vb  
    Dim myBitmap as New Bitmap("C:\Documents and Settings\Joe\Pics\myPic.bmp")  
    Dim g as Graphics = Graphics.FromImage(myBitmap)  
    ```  
  
    ```csharp  
    Bitmap myBitmap = new Bitmap(@"C:\Documents and   
       Settings\Joe\Pics\myPic.bmp");  
    Graphics g = Graphics.FromImage(myBitmap);  
    ```  
  
    ```cpp  
    Bitmap ^ myBitmap = gcnew  
       Bitmap("D:\\Documents and Settings\\Joe\\Pics\\myPic.bmp");  
    Graphics ^ g = Graphics::FromImage(myBitmap);  
    ```  
  
> [!NOTE]
>  <span data-ttu-id="59976-137">作成できるだけ<xref:System.Drawing.Graphics>16、24 ビットおよび 32 ビットの .bmp ファイルなど、インデックスなしの .bmp ファイルからオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="59976-137">You can only create <xref:System.Drawing.Graphics> objects from nonindexed .bmp files, such as 16-bit, 24-bit, and 32-bit .bmp files.</span></span> <span data-ttu-id="59976-138">インデックスなしの .bmp ファイルの各ピクセルは、カラー テーブルにインデックスを保持するインデックス付きの .bmp ファイルのピクセルとは異なり、色を保持します。</span><span class="sxs-lookup"><span data-stu-id="59976-138">Each pixel of nonindexed .bmp files holds a color, in contrast to pixels of indexed .bmp files, which hold an index to a color table.</span></span>  
  
## <a name="drawing-and-manipulating-shapes-and-images"></a><span data-ttu-id="59976-139">描画と図形と画像の操作</span><span class="sxs-lookup"><span data-stu-id="59976-139">Drawing and Manipulating Shapes and Images</span></span>  
 <span data-ttu-id="59976-140">作成した後、<xref:System.Drawing.Graphics>オブジェクトは、直線と図形の描画、テキストのレンダリングまたは表示、およびイメージを操作するために使用可能性があります。</span><span class="sxs-lookup"><span data-stu-id="59976-140">After it is created, a <xref:System.Drawing.Graphics> object may be used to draw lines and shapes, render text, or display and manipulate images.</span></span> <span data-ttu-id="59976-141">使用されるプリンシパルのオブジェクト、<xref:System.Drawing.Graphics>オブジェクトには。</span><span class="sxs-lookup"><span data-stu-id="59976-141">The principal objects that are used with the <xref:System.Drawing.Graphics> object are:</span></span>  
  
-   <span data-ttu-id="59976-142"><xref:System.Drawing.Pen>クラス: 線を描画、図形のアウトラインまたは他の幾何学的表現のレンダリングに使用します。</span><span class="sxs-lookup"><span data-stu-id="59976-142">The <xref:System.Drawing.Pen> class—Used for drawing lines, outlining shapes, or rendering other geometric representations.</span></span>  
  
-   <span data-ttu-id="59976-143"><xref:System.Drawing.Brush>クラス、塗りつぶされた図形、イメージ、テキストなどのグラフィックスの領域を塗りつぶすときのために使用します。</span><span class="sxs-lookup"><span data-stu-id="59976-143">The <xref:System.Drawing.Brush> class—Used for filling areas of graphics, such as filled shapes, images, or text.</span></span>  
  
-   <span data-ttu-id="59976-144"><xref:System.Drawing.Font>クラス-テキストのレンダリング時に使用する図形の内容の説明を提供します。</span><span class="sxs-lookup"><span data-stu-id="59976-144">The <xref:System.Drawing.Font> class—Provides a description of what shapes to use when rendering text.</span></span>  
  
-   <span data-ttu-id="59976-145"><xref:System.Drawing.Color>構造体などを表示するさまざまな色を表します。</span><span class="sxs-lookup"><span data-stu-id="59976-145">The <xref:System.Drawing.Color> structure—Represents the different colors to display.</span></span>  
  
#### <a name="to-use-the-graphics-object-you-have-created"></a><span data-ttu-id="59976-146">作成したグラフィック オブジェクトを使用するには</span><span class="sxs-lookup"><span data-stu-id="59976-146">To use the Graphics object you have created</span></span>  
  
-   <span data-ttu-id="59976-147">必要なものを描画するために上記の適切なオブジェクトを使用します。</span><span class="sxs-lookup"><span data-stu-id="59976-147">Work with the appropriate object listed above to draw what you need.</span></span>  
  
     <span data-ttu-id="59976-148">詳細については、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="59976-148">For more information, see the following topics:</span></span>  
  
    |<span data-ttu-id="59976-149">表示するには</span><span class="sxs-lookup"><span data-stu-id="59976-149">To render</span></span>|<span data-ttu-id="59976-150">解決方法</span><span class="sxs-lookup"><span data-stu-id="59976-150">See</span></span>|  
    |---------------|---------|  
    |<span data-ttu-id="59976-151">線</span><span class="sxs-lookup"><span data-stu-id="59976-151">Lines</span></span>|[<span data-ttu-id="59976-152">方法: Windows フォームに直線を描画します。</span><span class="sxs-lookup"><span data-stu-id="59976-152">How to: Draw a Line on a Windows Form</span></span>](how-to-draw-a-line-on-a-windows-form.md)|  
    |<span data-ttu-id="59976-153">図形</span><span class="sxs-lookup"><span data-stu-id="59976-153">Shapes</span></span>|[<span data-ttu-id="59976-154">方法: 形状のアウトラインを描画します。</span><span class="sxs-lookup"><span data-stu-id="59976-154">How to: Draw an Outlined Shape</span></span>](how-to-draw-an-outlined-shape.md)|  
    |<span data-ttu-id="59976-155">テキスト</span><span class="sxs-lookup"><span data-stu-id="59976-155">Text</span></span>|[<span data-ttu-id="59976-156">方法: Windows フォーム上のテキストの描画</span><span class="sxs-lookup"><span data-stu-id="59976-156">How to: Draw Text on a Windows Form</span></span>](how-to-draw-text-on-a-windows-form.md)|  
    |<span data-ttu-id="59976-157">イメージ</span><span class="sxs-lookup"><span data-stu-id="59976-157">Images</span></span>|[<span data-ttu-id="59976-158">方法: GDI + を使用したイメージをレンダリングします。</span><span class="sxs-lookup"><span data-stu-id="59976-158">How to: Render Images with GDI+</span></span>](how-to-render-images-with-gdi.md)|  
  
## <a name="see-also"></a><span data-ttu-id="59976-159">関連項目</span><span class="sxs-lookup"><span data-stu-id="59976-159">See also</span></span>
- [<span data-ttu-id="59976-160">グラフィックス プログラミングについて</span><span class="sxs-lookup"><span data-stu-id="59976-160">Getting Started with Graphics Programming</span></span>](getting-started-with-graphics-programming.md)
- [<span data-ttu-id="59976-161">Windows フォームにおけるグラフィックスと描画</span><span class="sxs-lookup"><span data-stu-id="59976-161">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="59976-162">直線、曲線、および図形</span><span class="sxs-lookup"><span data-stu-id="59976-162">Lines, Curves, and Shapes</span></span>](lines-curves-and-shapes.md)
- [<span data-ttu-id="59976-163">方法: GDI + を使用したイメージをレンダリングします。</span><span class="sxs-lookup"><span data-stu-id="59976-163">How to: Render Images with GDI+</span></span>](how-to-render-images-with-gdi.md)
