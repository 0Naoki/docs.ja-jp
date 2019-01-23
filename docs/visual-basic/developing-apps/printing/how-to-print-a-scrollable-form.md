---
title: '方法: スクロール可能フォーム (Visual Basic) 印刷します。'
ms.date: 07/20/2015
helpviewer_keywords:
- entire form [Visual Basic], printing
- scrollable form [Visual Basic], printing
ms.assetid: 1196e1cf-b77f-4928-a3e4-85b51ba3787d
ms.openlocfilehash: 6cec75eae8046befeb37da39e0b788f045ff4149
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54552503"
---
# <a name="how-to-print-a-scrollable-form-visual-basic"></a><span data-ttu-id="12070-102">方法: スクロール可能フォーム (Visual Basic) 印刷します。</span><span class="sxs-lookup"><span data-stu-id="12070-102">How to: Print a Scrollable Form (Visual Basic)</span></span>
<span data-ttu-id="12070-103"><xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> コンポーネントを使用すると、 <xref:System.Drawing.Printing.PrintDocument> コンポーネントを使わなくてもフォームのイメージをすばやく印刷できます。</span><span class="sxs-lookup"><span data-stu-id="12070-103">The <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> component enables you to quickly print an image of a form without using a <xref:System.Drawing.Printing.PrintDocument> component.</span></span> <span data-ttu-id="12070-104">既定では、フォームの現在見えている部分だけが印刷されます。ユーザーが実行時にフォームのサイズを変更した場合、イメージは意図されたとおりに印刷されない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="12070-104">By default, only the currently visible part of the form is printed; if a user has resized the form at run time, the image may not print as intended.</span></span> <span data-ttu-id="12070-105">次の手順は、フォームのサイズが変更された場合でもスクロール可能フォームのクライアント領域全体を印刷する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="12070-105">The following procedure shows how to print the complete client area of a scrollable form, even if the form has been resized.</span></span>  
  
 <span data-ttu-id="12070-106">PowerPack コントロールは、Visual Studio には含まれなくなりましたが、 [ダウンロード センター](https://www.microsoft.com/en-us/download/details.aspx?id=25169)からダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="12070-106">The PowerPack controls are no longer included in Visual Studio, but you can download them from the [Download Center](https://www.microsoft.com/en-us/download/details.aspx?id=25169).</span></span>  
  
### <a name="to-print-the-complete-client-area-of-a-scrollable-form"></a><span data-ttu-id="12070-107">スクロール可能フォームのクライアント領域全体を印刷するには</span><span class="sxs-lookup"><span data-stu-id="12070-107">To print the complete client area of a scrollable form</span></span>  
  
1.  <span data-ttu-id="12070-108">**ツールボックス**で、 **[Visual Basic PowerPacks]** タブをクリックして、 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> コンポーネントをフォームにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="12070-108">In the **Toolbox**, click the **Visual Basic PowerPacks** tab and then drag the <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> component onto the form.</span></span>  
  
     <span data-ttu-id="12070-109"><xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> コンポーネントがコンポーネント トレイに追加されます。</span><span class="sxs-lookup"><span data-stu-id="12070-109">The <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> component will be added to the component tray.</span></span>  
  
2.  <span data-ttu-id="12070-110">**[プロパティ]** ウィンドウで、 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A> プロパティを <xref:System.Drawing.Printing.PrintAction.PrintToPrinter>に設定します。</span><span class="sxs-lookup"><span data-stu-id="12070-110">In the **Properties** window, set the <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A> property to <xref:System.Drawing.Printing.PrintAction.PrintToPrinter>.</span></span>  
  
3.  <span data-ttu-id="12070-111">適切なイベント ハンドラー (たとえば `Click` [印刷] **の**`Button`イベント ハンドラー) に、次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="12070-111">Add the following code in the appropriate event handler (for example, in the `Click` event handler for a **Print**`Button`).</span></span>  
  
    ```  
    PrintForm1.Print(Me, PowerPacks.Printing.PrintForm.PrintOption.Scrollable)  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="12070-112">オペレーティング システムによっては、 <xref:System.Drawing.Graphics> メソッドによって描画されたテキストやグラフィックスが正しく印刷されないことがあります。</span><span class="sxs-lookup"><span data-stu-id="12070-112">On some operating systems, text or graphics drawn by <xref:System.Drawing.Graphics> methods may not print correctly.</span></span> <span data-ttu-id="12070-113">その場合、 `Scrollable` パラメーターを使用して印刷することはできません。</span><span class="sxs-lookup"><span data-stu-id="12070-113">In this case, you will not be able to print with the `Scrollable` parameter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12070-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="12070-114">See also</span></span>
- <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A>
- <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.Print%2A>
- [<span data-ttu-id="12070-115">PrintForm コンポーネント</span><span class="sxs-lookup"><span data-stu-id="12070-115">PrintForm Component</span></span>](../../../visual-basic/developing-apps/printing/printform-component.md)
- [<span data-ttu-id="12070-116">方法: フォームのクライアント領域を印刷する</span><span class="sxs-lookup"><span data-stu-id="12070-116">How to: Print the Client Area of a Form</span></span>](../../../visual-basic/developing-apps/printing/how-to-print-the-client-area-of-a-form.md)
- [<span data-ttu-id="12070-117">方法: フォームのクライアント領域と非クライアント領域を印刷する</span><span class="sxs-lookup"><span data-stu-id="12070-117">How to: Print Client and Non-Client Areas of a Form</span></span>](../../../visual-basic/developing-apps/printing/how-to-print-client-and-non-client-areas-of-a-form.md)
