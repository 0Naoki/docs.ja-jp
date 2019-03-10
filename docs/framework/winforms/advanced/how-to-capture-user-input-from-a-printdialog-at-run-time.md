---
title: '方法: 実行時に PrintDialog のユーザー入力をキャプチャします。'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- print options [Windows Forms], changing at run time
- printing [Windows Forms], options
- print options
- run time [Windows Forms], changing print options
ms.assetid: 438501d8-9a70-4fb3-aae6-e46579aba0c6
ms.openlocfilehash: 69a3632ddb4d68f5a916f5ffca020630abe1bd68
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/09/2019
ms.locfileid: "57707333"
---
# <a name="how-to-capture-user-input-from-a-printdialog-at-run-time"></a><span data-ttu-id="43f99-102">方法: 実行時に PrintDialog のユーザー入力をキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="43f99-102">How to: Capture User Input from a PrintDialog at Run Time</span></span>
<span data-ttu-id="43f99-103">デザイン時に印刷に関連するオプションを設定できますが、最も可能性の高いユーザーが行う選択により、実行時にこれらのオプションを変更するは場合があります。</span><span class="sxs-lookup"><span data-stu-id="43f99-103">While you can set options related to printing at design time, you will sometimes want to change these options at run time, most likely because of choices made by the user.</span></span> <span data-ttu-id="43f99-104">使用してドキュメントを印刷するためのユーザー入力をキャプチャすることができます、<xref:System.Windows.Forms.PrintDialog>と<xref:System.Drawing.Printing.PrintDocument>コンポーネント。</span><span class="sxs-lookup"><span data-stu-id="43f99-104">You can capture user input for printing a document using the <xref:System.Windows.Forms.PrintDialog> and the <xref:System.Drawing.Printing.PrintDocument> components.</span></span>  
  
### <a name="to-change-print-options-programmatically"></a><span data-ttu-id="43f99-105">プログラムで印刷オプションを変更するには</span><span class="sxs-lookup"><span data-stu-id="43f99-105">To change print options programmatically</span></span>  
  
1.  <span data-ttu-id="43f99-106">追加、<xref:System.Windows.Forms.PrintDialog>と<xref:System.Drawing.Printing.PrintDocument>コンポーネントをフォームにします。</span><span class="sxs-lookup"><span data-stu-id="43f99-106">Add a <xref:System.Windows.Forms.PrintDialog> and a <xref:System.Drawing.Printing.PrintDocument> component to your form.</span></span>  
  
2.  <span data-ttu-id="43f99-107">設定、<xref:System.Windows.Forms.PrintDialog.Document%2A>のプロパティ、<xref:System.Windows.Forms.PrintDialog>を<xref:System.Drawing.Printing.PrintDocument>フォームに追加します。</span><span class="sxs-lookup"><span data-stu-id="43f99-107">Set the <xref:System.Windows.Forms.PrintDialog.Document%2A> property of the <xref:System.Windows.Forms.PrintDialog> to the <xref:System.Drawing.Printing.PrintDocument> added to the form.</span></span>  
  
    ```vb  
    PrintDialog1.Document = PrintDocument1  
    ```  
  
    ```csharp  
    printDialog1.Document = PrintDocument1;  
    ```  
  
    ```cpp  
    printDialog1->Document = PrintDocument1;  
    ```  
  
3.  <span data-ttu-id="43f99-108">表示、<xref:System.Windows.Forms.PrintDialog>コンポーネントを使用して、<xref:System.Windows.Forms.CommonDialog.ShowDialog%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="43f99-108">Display the <xref:System.Windows.Forms.PrintDialog> component by using the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method.</span></span>  
  
    ```vb  
    PrintDialog1.ShowDialog()  
    ```  
  
    ```csharp  
    printDialog1.ShowDialog();  
    ```  
  
    ```cpp  
    printDialog1->ShowDialog();  
    ```  
  
4.  <span data-ttu-id="43f99-109">ダイアログ ボックスから、ユーザーの印刷オプションにコピーされる、<xref:System.Drawing.Printing.PrinterSettings>のプロパティ、<xref:System.Drawing.Printing.PrintDocument>コンポーネント。</span><span class="sxs-lookup"><span data-stu-id="43f99-109">The user's printing choices from the dialog will be copied to the <xref:System.Drawing.Printing.PrinterSettings> property of the <xref:System.Drawing.Printing.PrintDocument> component.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43f99-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="43f99-110">See also</span></span>
- [<span data-ttu-id="43f99-111">方法: Windows フォームで複数ページのテキスト ファイルを印刷します。</span><span class="sxs-lookup"><span data-stu-id="43f99-111">How to: Print a Multi-Page Text File in Windows Forms</span></span>](how-to-print-a-multi-page-text-file-in-windows-forms.md)
- [<span data-ttu-id="43f99-112">Windows フォームにおける印刷のサポート</span><span class="sxs-lookup"><span data-stu-id="43f99-112">Windows Forms Print Support</span></span>](windows-forms-print-support.md)
