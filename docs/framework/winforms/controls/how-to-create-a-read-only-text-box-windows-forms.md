---
title: '方法: 読み取り専用テキスト ボックス (Windows フォーム) を作成します。'
ms.date: 03/30/2017
helpviewer_keywords:
- TextBox control [Windows Forms], read-only
- read-only text boxes
- text boxes [Windows Forms], read-only
ms.assetid: 60baa9ab-fa57-44ad-bb7c-61b05aa64296
ms.openlocfilehash: 89d331f6c7fad5880aff031eb808199292e493a6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54670343"
---
# <a name="how-to-create-a-read-only-text-box-windows-forms"></a><span data-ttu-id="9288e-102">方法: 読み取り専用テキスト ボックス (Windows フォーム) を作成します。</span><span class="sxs-lookup"><span data-stu-id="9288e-102">How to: Create a Read-Only Text Box (Windows Forms)</span></span>
<span data-ttu-id="9288e-103">編集可能な Windows フォームのテキスト ボックスは読み取り専用のコントロールに変換できます。</span><span class="sxs-lookup"><span data-stu-id="9288e-103">You can transform an editable Windows Forms text box into a read-only control.</span></span> <span data-ttu-id="9288e-104">たとえば、テキスト ボックスが通常は編集ができない可能性があります現時点では、アプリケーションの状態が原因値を表示する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9288e-104">For example, the text box may display a value that is usually edited but may not be currently, due to the state of the application.</span></span>  
  
### <a name="to-create-a-read-only-text-box"></a><span data-ttu-id="9288e-105">読み取り専用テキスト ボックスを作成するには</span><span class="sxs-lookup"><span data-stu-id="9288e-105">To create a read-only text box</span></span>  
  
1.  <span data-ttu-id="9288e-106">設定、<xref:System.Windows.Forms.TextBox>コントロールの<xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A>プロパティを`true`します。</span><span class="sxs-lookup"><span data-stu-id="9288e-106">Set the <xref:System.Windows.Forms.TextBox> control's <xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A> property to `true`.</span></span> <span data-ttu-id="9288e-107">プロパティを設定して`true`ユーザーがまだスクロールやテキスト ボックス内のテキストを強調表示、変更を許可しません。</span><span class="sxs-lookup"><span data-stu-id="9288e-107">With the property set to `true`, users can still scroll and highlight text in a text box without allowing changes.</span></span> <span data-ttu-id="9288e-108">A**コピー**コマンドは、テキスト ボックスでは、機能ですが**切り取り**と**貼り付け**のコマンドはできません。</span><span class="sxs-lookup"><span data-stu-id="9288e-108">A **Copy** command is functional in a text box, but **Cut** and **Paste** commands are not.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9288e-109"><xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A>プロパティでは、実行時にユーザーとの対話のみに影響します。</span><span class="sxs-lookup"><span data-stu-id="9288e-109">The <xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A> property only affects user interaction at run time.</span></span> <span data-ttu-id="9288e-110">まだ変更テキスト ボックスの内容プログラムで実行時に変更することで、<xref:System.Windows.Forms.TextBox.Text%2A>テキスト ボックスのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="9288e-110">You can still change text box contents programmatically at run time by changing the <xref:System.Windows.Forms.TextBox.Text%2A> property of the text box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9288e-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="9288e-111">See also</span></span>
- <xref:System.Windows.Forms.TextBox>
- [<span data-ttu-id="9288e-112">TextBox コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="9288e-112">TextBox Control Overview</span></span>](../../../../docs/framework/winforms/controls/textbox-control-overview-windows-forms.md)
- [<span data-ttu-id="9288e-113">方法: Windows フォーム TextBox コントロールでのカーソル位置を制御します。</span><span class="sxs-lookup"><span data-stu-id="9288e-113">How to: Control the Insertion Point in a Windows Forms TextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [<span data-ttu-id="9288e-114">方法: Windows フォーム TextBox コントロールでパスワード テキスト ボックスを作成します。</span><span class="sxs-lookup"><span data-stu-id="9288e-114">How to: Create a Password Text Box with the Windows Forms TextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="9288e-115">方法: 文字列に引用符を挿入します。</span><span class="sxs-lookup"><span data-stu-id="9288e-115">How to: Put Quotation Marks in a String</span></span>](../../../../docs/framework/winforms/controls/how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [<span data-ttu-id="9288e-116">方法: Windows フォームの TextBox コントロールでテキストを選択します。</span><span class="sxs-lookup"><span data-stu-id="9288e-116">How to: Select Text in the Windows Forms TextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-select-text-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="9288e-117">方法: Windows フォームの TextBox コントロールで複数の行を表示します。</span><span class="sxs-lookup"><span data-stu-id="9288e-117">How to: View Multiple Lines in the Windows Forms TextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="9288e-118">TextBox コントロール</span><span class="sxs-lookup"><span data-stu-id="9288e-118">TextBox Control</span></span>](../../../../docs/framework/winforms/controls/textbox-control-windows-forms.md)
