---
title: '方法: デザイナーを使用して Windows フォーム コントロールのアクセス キーを作成する'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], access keys
- Button control [Windows Forms], access keys
- dialog box controls [Windows Forms], mnemonics
- access keys [Windows Forms], creating for controls
- mnemonics [Windows Forms], adding to dialog box controls
- ampersand character in shortcut key
- Windows Forms controls, access keys
- examples [Windows Forms], controls
- Text property [Windows Forms], specifying access keys for controls
- keyboard shortcuts [Windows Forms], creating for controls
- access keys [Windows Forms], Windows Forms
- ALT key
ms.assetid: 4c374c4c-4ca9-4a68-ac96-9dc3ab0f518a
ms.openlocfilehash: 410fc0134046c5fa7e05bfcd38ce6818244a0a54
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59307874"
---
# <a name="how-to-create-access-keys-for-windows-forms-controls-using-the-designer"></a><span data-ttu-id="1340b-102">方法: デザイナーを使用して Windows フォーム コントロールのアクセス キーを作成する</span><span class="sxs-lookup"><span data-stu-id="1340b-102">How to: Create Access Keys for Windows Forms Controls Using the Designer</span></span>
<span data-ttu-id="1340b-103">*アクセス キー*がメニューやメニュー項目では、ボタンなどのコントロールのラベルのテキストに下線付きの文字。</span><span class="sxs-lookup"><span data-stu-id="1340b-103">An *access key* is an underlined character in the text of a menu, menu item, or the label of a control such as a button.</span></span> <span data-ttu-id="1340b-104">組み合わせて定義済みのアクセス キーを持つ、ALT キーを押してボタンを「クリックして」にユーザーができるようにします。</span><span class="sxs-lookup"><span data-stu-id="1340b-104">It enables the user to "click" a button by pressing the ALT key in combination with the predefined access key.</span></span> <span data-ttu-id="1340b-105">たとえば、フォームを印刷する手順を実行するボタンとその`Text`プロパティを設定すると、実行時のボタン テキストに下線付きで表示するには、"P"を"P"により、文字の文字の前に「印刷、」アンパサンドを追加する (&)。</span><span class="sxs-lookup"><span data-stu-id="1340b-105">For example, if a button runs a procedure to print a form, and therefore its `Text` property is set to "Print," adding an ampersand (&) before the letter "P" causes the letter "P" to be underlined in the button text at run time.</span></span> <span data-ttu-id="1340b-106">ユーザーには、ALT キーを押しながら P キーを押して、ボタンに関連付けられているコマンドを実行できます。</span><span class="sxs-lookup"><span data-stu-id="1340b-106">The user can run the command associated with the button by pressing ALT+P.</span></span> <span data-ttu-id="1340b-107">フォーカスを受け取ることはできませんが、コントロールのアクセス キーを持つことはできません。</span><span class="sxs-lookup"><span data-stu-id="1340b-107">You cannot have an access key for a control that cannot receive focus.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1340b-108">実際に画面に表示されるダイアログ ボックスとメニュー コマンドは、アクティブな設定またはエディションによっては、ヘルプの説明と異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="1340b-108">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="1340b-109">設定を変更するには、 **[ツール]** メニューの **[設定のインポートとエクスポート]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1340b-109">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="1340b-110">詳細については、「[Visual Studio IDE のカスタマイズ](/visualstudio/ide/personalizing-the-visual-studio-ide)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1340b-110">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-create-an-access-key-for-a-control"></a><span data-ttu-id="1340b-111">コントロールのアクセス キーを作成するには</span><span class="sxs-lookup"><span data-stu-id="1340b-111">To create an access key for a control</span></span>  
  
1. <span data-ttu-id="1340b-112">**プロパティ**ウィンドウで、設定、`Text`プロパティへのアクセス キーとなる文字の前にアンパサンドを含む文字列 (&)。</span><span class="sxs-lookup"><span data-stu-id="1340b-112">In the **Properties** window, set the `Text` property to a string that includes an ampersand (&) before the letter that will be the access key.</span></span> <span data-ttu-id="1340b-113">たとえば、アクセス キーとして、文字"P"を設定する次のように入力します。 **& 印刷**グリッドにします。</span><span class="sxs-lookup"><span data-stu-id="1340b-113">For example, to set the letter "P" as the access key, type **&Print** into the grid.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1340b-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="1340b-114">See also</span></span>

- <xref:System.Windows.Forms.Button>
- [<span data-ttu-id="1340b-115">方法: Windows フォームのボタン クリックに応答するには</span><span class="sxs-lookup"><span data-stu-id="1340b-115">How to: Respond to Windows Forms Button Clicks</span></span>](how-to-respond-to-windows-forms-button-clicks.md)
- [<span data-ttu-id="1340b-116">方法: によって表示されるテキストを設定、Windows フォーム コントロール</span><span class="sxs-lookup"><span data-stu-id="1340b-116">How to: Set the Text Displayed by a Windows Forms Control</span></span>](how-to-set-the-text-displayed-by-a-windows-forms-control.md)
- [<span data-ttu-id="1340b-117">各 Windows フォーム コントロールのラベル設定とショートカットの作成</span><span class="sxs-lookup"><span data-stu-id="1340b-117">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
