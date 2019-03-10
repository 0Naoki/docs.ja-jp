---
title: '方法: デザイナーを使用して Windows フォーム tabcontrol のタブ追加および削除'
ms.date: 03/30/2017
helpviewer_keywords:
- tabs [Windows Forms], removing from pages
- TabPage control
- TabPage control [Windows Forms], adding and removing tabs
- tabs [Windows Forms], adding to pages
- tab pages
ms.assetid: 480633db-413a-45d2-9c8f-0427cc13adbe
ms.openlocfilehash: f58121455c346b2b615a5cf6e617e916618b4d6e
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/09/2019
ms.locfileid: "57720320"
---
# <a name="how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol-using-the-designer"></a><span data-ttu-id="bc1af-102">方法: デザイナーを使用して Windows フォーム tabcontrol のタブ追加および削除</span><span class="sxs-lookup"><span data-stu-id="bc1af-102">How to: Add and Remove Tabs with the Windows Forms TabControl Using the Designer</span></span>
<span data-ttu-id="bc1af-103">配置するとき、<xref:System.Windows.Forms.TabControl>コントロール フォームで、既定で 2 つのタブがあります。</span><span class="sxs-lookup"><span data-stu-id="bc1af-103">When you place a <xref:System.Windows.Forms.TabControl> control on your form, it contains two tabs by default.</span></span> <span data-ttu-id="bc1af-104">追加したり、デザイナーを使用してタブを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="bc1af-104">You can add or remove tabs using the designer.</span></span>  
  
 <span data-ttu-id="bc1af-105">次の手順が必要です、 **Windows アプリケーション**プロジェクトが含まれているフォームを<xref:System.Windows.Forms.TabControl>コントロール。</span><span class="sxs-lookup"><span data-stu-id="bc1af-105">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.TabControl> control.</span></span> <span data-ttu-id="bc1af-106">このようなプロジェクトの設定の詳細については、次を参照してください。[方法。Windows フォーム アプリケーション プロジェクトを作成](/visualstudio/ide/step-1-create-a-windows-forms-application-project)と[方法。Windows フォームにコントロールを追加](how-to-add-controls-to-windows-forms.md)します。</span><span class="sxs-lookup"><span data-stu-id="bc1af-106">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bc1af-107">実際に画面に表示されるダイアログ ボックスとメニュー コマンドは、アクティブな設定またはエディションによっては、ヘルプの説明と異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="bc1af-107">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="bc1af-108">設定を変更するには、 **[ツール]** メニューの **[設定のインポートとエクスポート]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bc1af-108">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="bc1af-109">詳細については、「[Visual Studio IDE のカスタマイズ](/visualstudio/ide/personalizing-the-visual-studio-ide)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bc1af-109">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-add-or-remove-a-tab-using-the-designer"></a><span data-ttu-id="bc1af-110">追加またはデザイナーを使用してタブを削除するには</span><span class="sxs-lookup"><span data-stu-id="bc1af-110">To add or remove a tab using the designer</span></span>  
  
-   <span data-ttu-id="bc1af-111">コントロールのスマート タグでは、次のようにクリックします**タブの追加**または**タブの削除。**</span><span class="sxs-lookup"><span data-stu-id="bc1af-111">On the control's smart tag, click **Add Tab** or **Remove Tab**</span></span>  
  
     <span data-ttu-id="bc1af-112">- または -</span><span class="sxs-lookup"><span data-stu-id="bc1af-112">-or-</span></span>  
  
     <span data-ttu-id="bc1af-113">**プロパティ**ウィンドウで、をクリックして、**省略記号**ボタン (![VisualStudioEllipsesButton スクリーン ショット](../media/vbellipsesbutton.png "vbEllipsesButton")) 横<xref:System.Windows.Forms.TabControl.TabPages%2A>プロパティを開き、 **TabPage コレクション エディター**します。</span><span class="sxs-lookup"><span data-stu-id="bc1af-113">In the **Properties** window, click the **Ellipsis** button (![VisualStudioEllipsesButton screenshot](../media/vbellipsesbutton.png "vbEllipsesButton")) next to the <xref:System.Windows.Forms.TabControl.TabPages%2A> property to open the **TabPage Collection Editor**.</span></span> <span data-ttu-id="bc1af-114">をクリックして、**追加**または**削除**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="bc1af-114">Click the **Add** or **Remove** button.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc1af-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="bc1af-115">See also</span></span>
- [<span data-ttu-id="bc1af-116">TabControl コントロール</span><span class="sxs-lookup"><span data-stu-id="bc1af-116">TabControl Control</span></span>](tabcontrol-control-windows-forms.md)
- [<span data-ttu-id="bc1af-117">TabControl コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="bc1af-117">TabControl Control Overview</span></span>](tabcontrol-control-overview-windows-forms.md)
- [<span data-ttu-id="bc1af-118">方法: タブ ページにコントロールを追加します。</span><span class="sxs-lookup"><span data-stu-id="bc1af-118">How to: Add a Control to a Tab Page</span></span>](how-to-add-a-control-to-a-tab-page.md)
- [<span data-ttu-id="bc1af-119">方法: タブ ページを無効にします。</span><span class="sxs-lookup"><span data-stu-id="bc1af-119">How to: Disable Tab Pages</span></span>](how-to-disable-tab-pages.md)
- [<span data-ttu-id="bc1af-120">方法: Windows フォーム TabControl の外観を変更します。</span><span class="sxs-lookup"><span data-stu-id="bc1af-120">How to: Change the Appearance of the Windows Forms TabControl</span></span>](how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)
