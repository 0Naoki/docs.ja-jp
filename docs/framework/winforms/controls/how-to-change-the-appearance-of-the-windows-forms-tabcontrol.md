---
title: '方法: Windows フォーム TabControl の外観を変更します。'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- icons [Windows Forms], displaying on tabs
- TabControl control [Windows Forms], changing page appearance
- tabs [Windows Forms], controlling appearance
- buttons [Windows Forms], displaying tabs as
ms.assetid: 7c6cc443-ed62-4d26-b94d-b8913b44f773
ms.openlocfilehash: 1ed062b3991d7738269d30a6ff13cda3c80927c2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54630321"
---
# <a name="how-to-change-the-appearance-of-the-windows-forms-tabcontrol"></a><span data-ttu-id="7e16d-102">方法: Windows フォーム TabControl の外観を変更します。</span><span class="sxs-lookup"><span data-stu-id="7e16d-102">How to: Change the Appearance of the Windows Forms TabControl</span></span>
<span data-ttu-id="7e16d-103">プロパティを使用して Windows フォームのタブの外観を変更することができます、<xref:System.Windows.Forms.TabControl>と<xref:System.Windows.Forms.TabPage>コントロールの個々 のタブを構成するオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="7e16d-103">You can change the appearance of tabs in Windows Forms by using properties of the <xref:System.Windows.Forms.TabControl> and the <xref:System.Windows.Forms.TabPage> objects that make up the individual tabs on the control.</span></span> <span data-ttu-id="7e16d-104">これらのプロパティを設定することができますタブ上のイメージを表示、水平方向にではなく縦方向にタブが表示されます、タブなどの複数の行を表示し有効または無効にタブ プログラムでします。</span><span class="sxs-lookup"><span data-stu-id="7e16d-104">By setting these properties, you can display images on tabs, display tabs vertically instead of horizontally, display multiple rows of tabs, and enable or disable tabs programmatically.</span></span>  
  
### <a name="to-display-an-icon-on-the-label-part-of-a-tab"></a><span data-ttu-id="7e16d-105">タブのラベルのアイコンを表示するには</span><span class="sxs-lookup"><span data-stu-id="7e16d-105">To display an icon on the label part of a tab</span></span>  
  
1.  <span data-ttu-id="7e16d-106">追加、<xref:System.Windows.Forms.ImageList>コントロールをフォームにします。</span><span class="sxs-lookup"><span data-stu-id="7e16d-106">Add an <xref:System.Windows.Forms.ImageList> control to the form.</span></span>  
  
2.  <span data-ttu-id="7e16d-107">イメージをイメージ リストに追加します。</span><span class="sxs-lookup"><span data-stu-id="7e16d-107">Add images to the image list.</span></span>  
  
     <span data-ttu-id="7e16d-108">イメージ リストの詳細については、次を参照してください。 [ImageList コンポーネント](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md)と[方法。追加または削除のイメージで、Windows フォームの ImageList コンポーネント](../../../../docs/framework/winforms/controls/how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md)します。</span><span class="sxs-lookup"><span data-stu-id="7e16d-108">For more information about image lists, see [ImageList Component](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md) and [How to: Add or Remove Images with the Windows Forms ImageList Component](../../../../docs/framework/winforms/controls/how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).</span></span>  
  
3.  <span data-ttu-id="7e16d-109">設定、<xref:System.Windows.Forms.TabControl.ImageList%2A>のプロパティ、<xref:System.Windows.Forms.TabControl>を<xref:System.Windows.Forms.ImageList>コントロール。</span><span class="sxs-lookup"><span data-stu-id="7e16d-109">Set the <xref:System.Windows.Forms.TabControl.ImageList%2A> property of the <xref:System.Windows.Forms.TabControl> to the <xref:System.Windows.Forms.ImageList> control.</span></span>  
  
4.  <span data-ttu-id="7e16d-110">設定、<xref:System.Windows.Forms.TabPage.ImageIndex%2A>のプロパティ、<xref:System.Windows.Forms.TabPage>リスト内の適切なイメージのインデックスにします。</span><span class="sxs-lookup"><span data-stu-id="7e16d-110">Set the <xref:System.Windows.Forms.TabPage.ImageIndex%2A> property of the <xref:System.Windows.Forms.TabPage> to the index of an appropriate image in the list.</span></span>  
  
### <a name="to-create-multiple-rows-of-tabs"></a><span data-ttu-id="7e16d-111">複数行のタブを作成するには</span><span class="sxs-lookup"><span data-stu-id="7e16d-111">To create multiple rows of tabs</span></span>  
  
1.  <span data-ttu-id="7e16d-112">選択するタブ ページの数を追加します。</span><span class="sxs-lookup"><span data-stu-id="7e16d-112">Add the number of tab pages you want.</span></span>  
  
2.  <span data-ttu-id="7e16d-113">設定、<xref:System.Windows.Forms.TabControl.Multiline%2A>のプロパティ、<xref:System.Windows.Forms.TabControl>に`true`します。</span><span class="sxs-lookup"><span data-stu-id="7e16d-113">Set the <xref:System.Windows.Forms.TabControl.Multiline%2A> property of the <xref:System.Windows.Forms.TabControl> to `true`.</span></span>  
  
3.  <span data-ttu-id="7e16d-114">複数の行にタブは表示されていない場合は、設定、<xref:System.Windows.Forms.Control.Width%2A>のプロパティ、<xref:System.Windows.Forms.TabControl>より、すべてのタブ幅を狭くします。</span><span class="sxs-lookup"><span data-stu-id="7e16d-114">If the tabs do not already appear in multiple rows, set the <xref:System.Windows.Forms.Control.Width%2A> property of the <xref:System.Windows.Forms.TabControl> to be narrower than all the tabs.</span></span>  
  
### <a name="to-arrange-tabs-on-the-side-of-the-control"></a><span data-ttu-id="7e16d-115">コントロールの横にあるタブを配置するには</span><span class="sxs-lookup"><span data-stu-id="7e16d-115">To arrange tabs on the side of the control</span></span>  
  
-   <span data-ttu-id="7e16d-116">設定、<xref:System.Windows.Forms.TabControl.Alignment%2A>のプロパティ、<xref:System.Windows.Forms.TabControl>に<xref:System.Windows.Forms.TabAlignment.Left>または<xref:System.Windows.Forms.TabAlignment.Right>します。</span><span class="sxs-lookup"><span data-stu-id="7e16d-116">Set the <xref:System.Windows.Forms.TabControl.Alignment%2A> property of the <xref:System.Windows.Forms.TabControl> to <xref:System.Windows.Forms.TabAlignment.Left> or <xref:System.Windows.Forms.TabAlignment.Right>.</span></span>  
  
### <a name="to-programmatically-enable-or-disable-all-controls-on-a-tab"></a><span data-ttu-id="7e16d-117">プログラムで有効にまたはタブのすべてのコントロールを無効にするには</span><span class="sxs-lookup"><span data-stu-id="7e16d-117">To programmatically enable or disable all controls on a tab</span></span>  
  
1.  <span data-ttu-id="7e16d-118">設定、<xref:System.Windows.Forms.TabPage.Enabled%2A>のプロパティ、<xref:System.Windows.Forms.TabPage>に`true`または`false`します。</span><span class="sxs-lookup"><span data-stu-id="7e16d-118">Set the <xref:System.Windows.Forms.TabPage.Enabled%2A> property of the <xref:System.Windows.Forms.TabPage> to `true` or `false`.</span></span>  
  
    ```vb  
    TabPage1.Enabled = False  
    ```  
  
    ```csharp  
    tabPage1.Enabled = false;  
    ```  
  
    ```cpp  
    tabPage1->Enabled = false;  
    ```  
  
### <a name="to-display-tabs-as-buttons"></a><span data-ttu-id="7e16d-119">タブのボタンとして表示するには</span><span class="sxs-lookup"><span data-stu-id="7e16d-119">To display tabs as buttons</span></span>  
  
-   <span data-ttu-id="7e16d-120">設定、<xref:System.Windows.Forms.TabControl.Appearance%2A>のプロパティ、<xref:System.Windows.Forms.TabControl>に<xref:System.Windows.Forms.TabAppearance.Buttons>または<xref:System.Windows.Forms.TabAppearance.FlatButtons>します。</span><span class="sxs-lookup"><span data-stu-id="7e16d-120">Set the <xref:System.Windows.Forms.TabControl.Appearance%2A> property of the <xref:System.Windows.Forms.TabControl> to <xref:System.Windows.Forms.TabAppearance.Buttons> or <xref:System.Windows.Forms.TabAppearance.FlatButtons>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e16d-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="7e16d-121">See also</span></span>
- [<span data-ttu-id="7e16d-122">TabControl コントロール</span><span class="sxs-lookup"><span data-stu-id="7e16d-122">TabControl Control</span></span>](../../../../docs/framework/winforms/controls/tabcontrol-control-windows-forms.md)
- [<span data-ttu-id="7e16d-123">TabControl コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="7e16d-123">TabControl Control Overview</span></span>](../../../../docs/framework/winforms/controls/tabcontrol-control-overview-windows-forms.md)
- [<span data-ttu-id="7e16d-124">方法: タブ ページにコントロールを追加します。</span><span class="sxs-lookup"><span data-stu-id="7e16d-124">How to: Add a Control to a Tab Page</span></span>](../../../../docs/framework/winforms/controls/how-to-add-a-control-to-a-tab-page.md)
- [<span data-ttu-id="7e16d-125">方法: タブ ページを無効にします。</span><span class="sxs-lookup"><span data-stu-id="7e16d-125">How to: Disable Tab Pages</span></span>](../../../../docs/framework/winforms/controls/how-to-disable-tab-pages.md)
- [<span data-ttu-id="7e16d-126">方法: Windows フォーム tabcontrol のタブ追加および削除</span><span class="sxs-lookup"><span data-stu-id="7e16d-126">How to: Add and Remove Tabs with the Windows Forms TabControl</span></span>](../../../../docs/framework/winforms/controls/how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol.md)
