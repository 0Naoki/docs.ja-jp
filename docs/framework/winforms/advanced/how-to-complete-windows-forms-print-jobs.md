---
title: '方法: Windows フォームの印刷ジョブを完了する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- print jobs [Windows Forms], completing in Windows Forms
- printing [Windows Forms], print jobs
ms.assetid: 23ec74f7-34c5-4710-82a0-ee2914518548
ms.openlocfilehash: 256b9a3d8842aaa4b032e67ebac9ca6a9e1ef34a
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2019
ms.locfileid: "59293756"
---
# <a name="how-to-complete-windows-forms-print-jobs"></a><span data-ttu-id="a340d-102">方法: Windows フォームの印刷ジョブを完了する</span><span class="sxs-lookup"><span data-stu-id="a340d-102">How to: Complete Windows Forms Print Jobs</span></span>
<span data-ttu-id="a340d-103">多くの場合、ワード プロセッサや他の印刷に関連するアプリケーションは、印刷ジョブが完了したユーザーにメッセージを表示するオプションを提供します。</span><span class="sxs-lookup"><span data-stu-id="a340d-103">Frequently, word processors and other applications that involve printing will provide the option to display a message to users that a print job is complete.</span></span> <span data-ttu-id="a340d-104">処理することにより、Windows フォーム内でこの機能を行うことができます、<xref:System.Drawing.Printing.PrintDocument.EndPrint>のイベント、<xref:System.Drawing.Printing.PrintDocument>コンポーネント。</span><span class="sxs-lookup"><span data-stu-id="a340d-104">You can provide this functionality in your Windows Forms by handling the <xref:System.Drawing.Printing.PrintDocument.EndPrint> event of the <xref:System.Drawing.Printing.PrintDocument> component.</span></span>  
  
 <span data-ttu-id="a340d-105">次の手順で Windows ベースのアプリケーションを作成することが必要です、<xref:System.Drawing.Printing.PrintDocument>コンポーネントをこれは、Windows ベースのアプリケーションから印刷を有効にする標準的な方法です。</span><span class="sxs-lookup"><span data-stu-id="a340d-105">The following procedure requires that you have created a Windows-based application with a <xref:System.Drawing.Printing.PrintDocument> component on it, which is the standard way of enabling printing from a Windows-based application.</span></span> <span data-ttu-id="a340d-106">使用して Windows フォームからの印刷の詳細については、<xref:System.Drawing.Printing.PrintDocument>コンポーネントを参照してください[方法。標準の Windows フォーム印刷ジョブを作成](how-to-create-standard-windows-forms-print-jobs.md)です。</span><span class="sxs-lookup"><span data-stu-id="a340d-106">For more information about printing from Windows Forms using the <xref:System.Drawing.Printing.PrintDocument> component, see [How to: Create Standard Windows Forms Print Jobs](how-to-create-standard-windows-forms-print-jobs.md).</span></span>  
  
### <a name="to-complete-a-print-job"></a><span data-ttu-id="a340d-107">印刷ジョブを完了するには</span><span class="sxs-lookup"><span data-stu-id="a340d-107">To complete a print job</span></span>  
  
1. <span data-ttu-id="a340d-108">設定、<xref:System.Drawing.Printing.PrintDocument.DocumentName%2A>のプロパティ、<xref:System.Drawing.Printing.PrintDocument>コンポーネント。</span><span class="sxs-lookup"><span data-stu-id="a340d-108">Set the <xref:System.Drawing.Printing.PrintDocument.DocumentName%2A> property of the <xref:System.Drawing.Printing.PrintDocument> component.</span></span>  
  
    ```vb  
    PrintDocument1.DocumentName = "MyTextFile"  
    ```  
  
    ```csharp  
    printDocument1.DocumentName = "MyTextFile";  
    ```  
  
    ```cpp  
    printDocument1->DocumentName = "MyTextFile";  
    ```  
  
2. <span data-ttu-id="a340d-109"><xref:System.Drawing.Printing.PrintDocument.EndPrint> イベントを処理するコードを記述します。</span><span class="sxs-lookup"><span data-stu-id="a340d-109">Write code to handle the <xref:System.Drawing.Printing.PrintDocument.EndPrint> event.</span></span>  
  
     <span data-ttu-id="a340d-110">次のコード例では、メッセージ ボックスが表示されます、ドキュメントの印刷が完了したことを示します。</span><span class="sxs-lookup"><span data-stu-id="a340d-110">In the following code example, a message box is displayed, indicating that the document has finished printing.</span></span>  
  
    ```vb  
    Private Sub PrintDocument1_EndPrint(ByVal sender As Object, ByVal e As System.Drawing.Printing.PrintEventArgs) Handles PrintDocument1.EndPrint  
       MessageBox.Show(PrintDocument1.DocumentName + " has finished printing.")  
    End Sub  
    ```  
  
    ```csharp  
    private void printDocument1_EndPrint(object sender,   
    System.Drawing.Printing.PrintEventArgs e)  
    {  
       MessageBox.Show(printDocument1.DocumentName +   
          " has finished printing.");  
    }  
    ```  
  
    ```cpp  
    private:  
       void printDocument1_EndPrint(System::Object ^ sender,  
          System::Drawing::Printing::PrintEventArgs ^ e)  
       {  
          MessageBox::Show(String::Concat(printDocument1->DocumentName,  
             " has finished printing."));  
       }  
    ```  
  
     <span data-ttu-id="a340d-111">(Visual c# と[!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)])、イベント ハンドラーを登録するフォームのコンス トラクターで、次のコードを配置します。</span><span class="sxs-lookup"><span data-stu-id="a340d-111">(Visual C# and [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.printDocument1.EndPrint += new  
       System.Drawing.Printing.PrintEventHandler  
       (this.printDocument1_EndPrint);  
    ```  
  
    ```cpp  
    this->printDocument1->EndPrint += gcnew  
       System::Drawing::Printing::PrintEventHandler  
       (this, &Form1::printDocument1_EndPrint);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="a340d-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="a340d-112">See also</span></span>

- <xref:System.Drawing.Printing.PrintDocument>
- [<span data-ttu-id="a340d-113">Windows フォームにおける印刷のサポート</span><span class="sxs-lookup"><span data-stu-id="a340d-113">Windows Forms Print Support</span></span>](windows-forms-print-support.md)
