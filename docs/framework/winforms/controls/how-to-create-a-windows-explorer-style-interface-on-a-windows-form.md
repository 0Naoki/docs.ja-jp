---
title: '方法: Windows フォームで Windows エクスプ ローラー スタイルのインターフェイスを作成します。'
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Explorer [Windows Forms], creating with Windows Forms
- SplitContainer control [Windows Forms], Explorer-style interface
- forms [Windows Forms], Windows Explorer type
ms.assetid: 9a3d5f4f-5dda-4350-9ad5-57ce5976dc47
ms.openlocfilehash: 0b61961aff04a089ce12f4b96637e3f05023e929
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54511099"
---
# <a name="how-to-create-a-windows-explorerstyle-interface-on-a-windows-form"></a><span data-ttu-id="ca52a-102">方法: Windows フォームで Windows エクスプ ローラー スタイルのインターフェイスを作成します。</span><span class="sxs-lookup"><span data-stu-id="ca52a-102">How to: Create a Windows Explorer–Style Interface on a Windows Form</span></span>
<span data-ttu-id="ca52a-103">Windows エクスプ ローラーは、準備ができて、慣れ親しんだのためのアプリケーションの一般的なユーザー インターフェイス選択です。</span><span class="sxs-lookup"><span data-stu-id="ca52a-103">Windows Explorer is a common user-interface choice for applications because of its ready familiarity.</span></span>  
  
 <span data-ttu-id="ca52a-104">Windows エクスプ ローラーは、基本的に、<xref:System.Windows.Forms.TreeView>コントロールと<xref:System.Windows.Forms.ListView>別のパネル上のコントロール。</span><span class="sxs-lookup"><span data-stu-id="ca52a-104">Windows Explorer is, essentially, a <xref:System.Windows.Forms.TreeView> control and a <xref:System.Windows.Forms.ListView> control on separate panels.</span></span> <span data-ttu-id="ca52a-105">パネルは、スプリッターによってサイズ変更可能で行われます。</span><span class="sxs-lookup"><span data-stu-id="ca52a-105">The panels are made resizable by a splitter.</span></span> <span data-ttu-id="ca52a-106">このコントロールの配置は、情報の表示と参照は非常に効果的です。</span><span class="sxs-lookup"><span data-stu-id="ca52a-106">This arrangement of controls is very effective for displaying and browsing information.</span></span>  
  
 <span data-ttu-id="ca52a-107">次の手順では、Windows エクスプ ローラーのようなフォームでコントロールを配置する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="ca52a-107">The following steps show how to arrange controls in a Windows Explorer-like form.</span></span> <span data-ttu-id="ca52a-108">Windows エクスプ ローラー アプリケーションのファイル参照機能を追加する方法は表示されません。</span><span class="sxs-lookup"><span data-stu-id="ca52a-108">They do not show how to add the file-browsing functionality of the Windows Explorer application.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ca52a-109">実際に画面に表示されるダイアログ ボックスとメニュー コマンドは、アクティブな設定またはエディションによっては、ヘルプの説明と異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="ca52a-109">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="ca52a-110">設定を変更するには、 **[ツール]** メニューの **[設定のインポートとエクスポート]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ca52a-110">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="ca52a-111">詳細については、「[Visual Studio IDE のカスタマイズ](/visualstudio/ide/personalizing-the-visual-studio-ide)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ca52a-111">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-create-a-windows-explorer-style-windows-form"></a><span data-ttu-id="ca52a-112">Windows エクスプ ローラー スタイルの Windows フォームを作成するには</span><span class="sxs-lookup"><span data-stu-id="ca52a-112">To create a Windows Explorer-style Windows Form</span></span>  
  
1.  <span data-ttu-id="ca52a-113">新しい Windows アプリケーション プロジェクトを作成 (**ファイル** > **新規** > **プロジェクト** > **Visual c#** または**Visual Basic** > **クラシック デスクトップ** > **Windows フォーム アプリケーション**)。</span><span class="sxs-lookup"><span data-stu-id="ca52a-113">Create a new Windows Application project (**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **Windows Forms Application**).</span></span>  
  
2.  <span data-ttu-id="ca52a-114">**ツールボックス**:</span><span class="sxs-lookup"><span data-stu-id="ca52a-114">From the **Toolbox**:</span></span>  
  
    1.  <span data-ttu-id="ca52a-115">ドラッグ、<xref:System.Windows.Forms.SplitContainer>コントロールをフォームにします。</span><span class="sxs-lookup"><span data-stu-id="ca52a-115">Drag a <xref:System.Windows.Forms.SplitContainer> control onto your form.</span></span>  
  
    2.  <span data-ttu-id="ca52a-116">ドラッグ、<xref:System.Windows.Forms.TreeView>にコントロールを**SplitterPanel1** (のパネル、<xref:System.Windows.Forms.SplitContainer>マークされているコントロール**Panel1**)。</span><span class="sxs-lookup"><span data-stu-id="ca52a-116">Drag a <xref:System.Windows.Forms.TreeView> control into **SplitterPanel1** (the panel of the <xref:System.Windows.Forms.SplitContainer> control marked **Panel1**).</span></span>  
  
    3.  <span data-ttu-id="ca52a-117">ドラッグ、<xref:System.Windows.Forms.ListView>にコントロールを**SplitterPanel2** (のパネル、<xref:System.Windows.Forms.SplitContainer>マークされているコントロール**Panel2**)。</span><span class="sxs-lookup"><span data-stu-id="ca52a-117">Drag a <xref:System.Windows.Forms.ListView> control into **SplitterPanel2** (the panel of the <xref:System.Windows.Forms.SplitContainer> control marked **Panel2**).</span></span>  
  
3.  <span data-ttu-id="ca52a-118">CTRL キーをクリックするとさらに 3 つすべてのコントロールを選択します。</span><span class="sxs-lookup"><span data-stu-id="ca52a-118">Select all three controls by pressing the CTRL key and clicking them in turn.</span></span> <span data-ttu-id="ca52a-119">選択すると、<xref:System.Windows.Forms.SplitContainer>コントロールをパネルではなく、スプリッター バーをクリックします。</span><span class="sxs-lookup"><span data-stu-id="ca52a-119">When you select the <xref:System.Windows.Forms.SplitContainer> control, click the splitter bar, rather than the panels.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ca52a-120">使用しないでください、**すべて選択**コマンドを**編集**メニュー。</span><span class="sxs-lookup"><span data-stu-id="ca52a-120">Do not use the **Select All** command on the **Edit** menu.</span></span> <span data-ttu-id="ca52a-121">これを行う場合、次の手順で必要なプロパティでは表示されません、**プロパティ**ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="ca52a-121">If you do so, the property needed in the next step will not appear in the **Properties** window.</span></span>  
  
4.  <span data-ttu-id="ca52a-122">**[プロパティ]** ウィンドウで、 <xref:System.Windows.Forms.SplitContainer.Dock%2A> プロパティを <xref:System.Windows.Forms.DockStyle.Fill>に設定します。</span><span class="sxs-lookup"><span data-stu-id="ca52a-122">In the **Properties** window, set the <xref:System.Windows.Forms.SplitContainer.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>  
  
5.  <span data-ttu-id="ca52a-123">F5 キーを押してアプリケーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="ca52a-123">Press F5 to run the application.</span></span>  
  
     <span data-ttu-id="ca52a-124">フォームには、Windows エクスプ ローラーのような 2 つの部分のユーザー インターフェイスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ca52a-124">The form displays a two-part user interface, similar to that of the Windows Explorer.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ca52a-125">分割線をドラッグすると、パネルでは、自身サイズを変更します。</span><span class="sxs-lookup"><span data-stu-id="ca52a-125">When you drag the splitter, the panels resize themselves.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca52a-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="ca52a-126">See also</span></span>
- <xref:System.Windows.Forms.SplitContainer>
- [<span data-ttu-id="ca52a-127">方法: Windows フォームでマルチペイン ユーザー インターフェイスを作成します。</span><span class="sxs-lookup"><span data-stu-id="ca52a-127">How to: Create a Multipane User Interface with Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-create-a-multipane-user-interface-with-windows-forms.md)
- [<span data-ttu-id="ca52a-128">方法: サイズ変更および位置指定動作を分割ウィンドウを定義します。</span><span class="sxs-lookup"><span data-stu-id="ca52a-128">How to: Define Resize and Positioning Behavior in a Split Window</span></span>](../../../../docs/framework/winforms/controls/how-to-define-resize-and-positioning-behavior-in-a-split-window.md)
- [<span data-ttu-id="ca52a-129">方法: ウィンドウを水平方向に分割します。</span><span class="sxs-lookup"><span data-stu-id="ca52a-129">How to: Split a Window Horizontally</span></span>](../../../../docs/framework/winforms/controls/how-to-split-a-window-horizontally.md)
- [<span data-ttu-id="ca52a-130">SplitContainer コントロール</span><span class="sxs-lookup"><span data-stu-id="ca52a-130">SplitContainer Control</span></span>](../../../../docs/framework/winforms/controls/splitcontainer-control-windows-forms.md)
