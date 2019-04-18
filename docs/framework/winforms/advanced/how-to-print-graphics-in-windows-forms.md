---
title: '方法: Windows フォームでグラフィックスを印刷する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- graphics [Windows Forms], printing
- printing [Windows Forms], graphics
ms.assetid: 32b891e6-52ff-4fea-a9ff-2ce5db20a4c6
ms.openlocfilehash: 55459482d0994c581164128b17c08a7ca90d0717
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2019
ms.locfileid: "59339100"
---
# <a name="how-to-print-graphics-in-windows-forms"></a><span data-ttu-id="b2c0d-102">方法: Windows フォームでグラフィックスを印刷する</span><span class="sxs-lookup"><span data-stu-id="b2c0d-102">How to: Print Graphics in Windows Forms</span></span>
<span data-ttu-id="b2c0d-103">多くの場合、Windows ベースのアプリケーションでグラフィックスを印刷するされます。</span><span class="sxs-lookup"><span data-stu-id="b2c0d-103">Frequently, you will want to print graphics in your Windows-based application.</span></span> <span data-ttu-id="b2c0d-104"><xref:System.Drawing.Graphics>クラスは、画面やプリンターなどのデバイスにオブジェクトを描画するためのメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="b2c0d-104">The <xref:System.Drawing.Graphics> class provides methods for drawing objects to a device, such as a screen or printer.</span></span>  
  
### <a name="to-print-graphics"></a><span data-ttu-id="b2c0d-105">グラフィックスを印刷するには</span><span class="sxs-lookup"><span data-stu-id="b2c0d-105">To print graphics</span></span>  
  
1. <span data-ttu-id="b2c0d-106">追加、<xref:System.Drawing.Printing.PrintDocument>コンポーネントをフォームにします。</span><span class="sxs-lookup"><span data-stu-id="b2c0d-106">Add a <xref:System.Drawing.Printing.PrintDocument> component to your form.</span></span>  
  
2. <span data-ttu-id="b2c0d-107"><xref:System.Drawing.Printing.PrintDocument.PrintPage>イベント ハンドラーを使用して、<xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A>のプロパティ、<xref:System.Drawing.Printing.PrintPageEventArgs>クラスにどのようなグラフィックスを印刷するプリンターの指示をします。</span><span class="sxs-lookup"><span data-stu-id="b2c0d-107">In the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event handler, use the <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> property of the <xref:System.Drawing.Printing.PrintPageEventArgs> class to instruct the printer on what kind of graphics to print.</span></span>  
  
     <span data-ttu-id="b2c0d-108">次のコード例では、外接する四角形内に青い楕円を作成するために使用するイベント ハンドラーを示します。</span><span class="sxs-lookup"><span data-stu-id="b2c0d-108">The following code example shows an event handler used to create a blue ellipse within a bounding rectangle.</span></span> <span data-ttu-id="b2c0d-109">四角形が次の位置およびサイズ: 100 から始まる 250 の幅、高さ 250 150。</span><span class="sxs-lookup"><span data-stu-id="b2c0d-109">The rectangle has the following location and dimensions: beginning at 100, 150 with a width of 250 and a height of 250.</span></span>  
  
    ```vb  
    Private Sub PrintDocument1_PrintPage(ByVal sender As Object, ByVal e As System.Drawing.Printing.PrintPageEventArgs) Handles PrintDocument1.PrintPage  
       e.Graphics.FillEllipse(Brushes.Blue, New Rectangle(100, 150, 250, 250))  
    End Sub  
    ```  
  
    ```csharp  
    private void printDocument1_PrintPage(object sender,   
    System.Drawing.Printing.PrintPageEventArgs e)  
    {  
       e.Graphics.FillRectangle(Brushes.Blue,   
         new Rectangle(100, 150, 250, 250));  
    }  
    ```  
  
    ```cpp  
    private:  
       void printDocument1_PrintPage(System::Object ^ sender,  
          System::Drawing::Printing::PrintPageEventArgs ^ e)  
       {  
          e->Graphics->FillRectangle(Brushes::Blue,  
             Rectangle(100, 150, 250, 250));  
       }  
    ```  
  
     <span data-ttu-id="b2c0d-110">(Visual C# と[!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)])、イベント ハンドラーを登録するフォームのコンス トラクターで、次のコードを配置します。</span><span class="sxs-lookup"><span data-stu-id="b2c0d-110">(Visual C# and [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.printDocument1.PrintPage += new  
       System.Drawing.Printing.PrintPageEventHandler  
       (this.printDocument1_PrintPage);  
    ```  
  
    ```cpp  
    this->printDocument1->PrintPage += gcnew  
       System::Drawing::Printing::PrintPageEventHandler  
       (this, &Form1::printDocument1_PrintPage);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="b2c0d-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="b2c0d-111">See also</span></span>

- <xref:System.Drawing.Graphics>
- <xref:System.Drawing.Brush>
- [<span data-ttu-id="b2c0d-112">Windows フォームにおける印刷のサポート</span><span class="sxs-lookup"><span data-stu-id="b2c0d-112">Windows Forms Print Support</span></span>](windows-forms-print-support.md)
