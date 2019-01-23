---
title: 'チュートリアル: Windows フォーム コントロールのスマート タグを使用した共通タスクの実行'
ms.date: 03/30/2017
helpviewer_keywords:
- DesignerAction object model
- smart tags
- designer actions
ms.assetid: cac337e6-00f6-4584-80f4-75728f5ea113
ms.openlocfilehash: b17fbaea48660a47630dd310c74be9cd3cc78609
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54579317"
---
# <a name="walkthrough-performing-common-tasks-using-smart-tags-on-windows-forms-controls"></a><span data-ttu-id="3e16e-102">チュートリアル: Windows フォーム コントロールのスマート タグを使用した共通タスクの実行</span><span class="sxs-lookup"><span data-stu-id="3e16e-102">Walkthrough: Performing Common Tasks Using Smart Tags on Windows Forms Controls</span></span>
<span data-ttu-id="3e16e-103">Windows フォーム アプリケーションのフォームとコントロールを作成するときは、繰り返し実行する多くのタスクを使用します。</span><span class="sxs-lookup"><span data-stu-id="3e16e-103">As you construct forms and controls for your Windows Forms application, there are many tasks you will perform repeatedly.</span></span> <span data-ttu-id="3e16e-104">これらは、発生する、一般的に実行されるタスクの一部を示します。</span><span class="sxs-lookup"><span data-stu-id="3e16e-104">These are some of the commonly performed tasks you will encounter:</span></span>  
  
-   <span data-ttu-id="3e16e-105">追加またはでタブを削除する、<xref:System.Windows.Forms.TabControl>します。</span><span class="sxs-lookup"><span data-stu-id="3e16e-105">Adding or removing a tab on a <xref:System.Windows.Forms.TabControl>.</span></span>  
  
-   <span data-ttu-id="3e16e-106">コントロールは、その親にドッキングします。</span><span class="sxs-lookup"><span data-stu-id="3e16e-106">Docking a control to its parent.</span></span>  
  
-   <span data-ttu-id="3e16e-107">向きの変更、<xref:System.Windows.Forms.SplitContainer>コントロール。</span><span class="sxs-lookup"><span data-stu-id="3e16e-107">Changing the orientation of a <xref:System.Windows.Forms.SplitContainer> control.</span></span>  
  
 <span data-ttu-id="3e16e-108">開発のスピード、多くのコントロールは、デザイン時に 1 つのジェスチャで上記のような一般的なタスクを実行するための状況依存のメニューにはスマート タグを提供します。</span><span class="sxs-lookup"><span data-stu-id="3e16e-108">To speed development, many controls offer smart tags, which are context-sensitive menus that allow you to perform common tasks like these in a single gesture at design time.</span></span> <span data-ttu-id="3e16e-109">これらのタスクが呼び出されます*スマート タグの動詞*します。</span><span class="sxs-lookup"><span data-stu-id="3e16e-109">These tasks are called *smart-tag verbs*.</span></span>  
  
 <span data-ttu-id="3e16e-110">スマート タグは、有効期間にわたって、デザイナーでコントロールのインスタンスに接続されたままし、常に利用します。</span><span class="sxs-lookup"><span data-stu-id="3e16e-110">Smart tags remain attached to a control instance for its lifetime in the designer and are always available.</span></span>  
  
 <span data-ttu-id="3e16e-111">このチュートリアルでは、以下のタスクを行います。</span><span class="sxs-lookup"><span data-stu-id="3e16e-111">Tasks illustrated in this walkthrough include:</span></span>  
  
-   <span data-ttu-id="3e16e-112">Windows フォーム プロジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="3e16e-112">Creating a Windows Forms project</span></span>  
  
-   <span data-ttu-id="3e16e-113">スマート タグを使用します。</span><span class="sxs-lookup"><span data-stu-id="3e16e-113">Using smart tags</span></span>  
  
-   <span data-ttu-id="3e16e-114">有効にして、スマート タグを無効化</span><span class="sxs-lookup"><span data-stu-id="3e16e-114">Enabling and Disabling Smart Tags</span></span>  
  
 <span data-ttu-id="3e16e-115">終了すると、これらの重要なレイアウト機能が果たす役割について理解できます。</span><span class="sxs-lookup"><span data-stu-id="3e16e-115">When you are finished, you will have an understanding of the role played by these important layout features.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3e16e-116">実際に画面に表示されるダイアログ ボックスとメニュー コマンドは、アクティブな設定またはエディションによっては、ヘルプの説明と異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="3e16e-116">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="3e16e-117">設定を変更するには、 **[ツール]** メニューの **[設定のインポートとエクスポート]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3e16e-117">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="3e16e-118">詳細については、「[Visual Studio IDE のカスタマイズ](/visualstudio/ide/personalizing-the-visual-studio-ide)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e16e-118">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="3e16e-119">プロジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="3e16e-119">Creating the Project</span></span>  
 <span data-ttu-id="3e16e-120">最初にプロジェクトを作成し、フォームを設定します。</span><span class="sxs-lookup"><span data-stu-id="3e16e-120">The first step is to create the project and set up the form.</span></span>  
  
#### <a name="to-create-the-project"></a><span data-ttu-id="3e16e-121">プロジェクトを作成するには</span><span class="sxs-lookup"><span data-stu-id="3e16e-121">To create the project</span></span>  
  
1.  <span data-ttu-id="3e16e-122">"SmartTagsExample"と呼ばれる Windows ベースのアプリケーション プロジェクトを作成する (**ファイル** > **新規** > **プロジェクト** >  **Visual c#** または**Visual Basic** > **クラシック デスクトップ** > **Windows フォーム アプリケーション**)。</span><span class="sxs-lookup"><span data-stu-id="3e16e-122">Create a Windows-based application project called "SmartTagsExample" (**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **Windows Forms Application**).</span></span>  
  
2.  <span data-ttu-id="3e16e-123">フォームを選択、 **Windows フォーム デザイナー**します。</span><span class="sxs-lookup"><span data-stu-id="3e16e-123">Select the form in the **Windows Forms Designer**.</span></span>  
  
## <a name="using-smart-tags"></a><span data-ttu-id="3e16e-124">スマート タグを使用します。</span><span class="sxs-lookup"><span data-stu-id="3e16e-124">Using Smart Tags</span></span>  
 <span data-ttu-id="3e16e-125">スマート タグは、提供するコントロールのデザイン時に常に使用できます。</span><span class="sxs-lookup"><span data-stu-id="3e16e-125">Smart tags are always available at design time on controls that offer them.</span></span>  
  
#### <a name="to-use-smart-tags"></a><span data-ttu-id="3e16e-126">スマート タグを使用するには</span><span class="sxs-lookup"><span data-stu-id="3e16e-126">To use smart tags</span></span>  
  
1.  <span data-ttu-id="3e16e-127">ドラッグ、<xref:System.Windows.Forms.TabControl>から、**ツールボックス**フォームにします。</span><span class="sxs-lookup"><span data-stu-id="3e16e-127">Drag a <xref:System.Windows.Forms.TabControl> from the **Toolbox** onto your form.</span></span> <span data-ttu-id="3e16e-128">スマート タグ グリフに注意してください (![スマート タグ グリフ](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) のサイド バイ サイドで表示される、<xref:System.Windows.Forms.TabControl>します。</span><span class="sxs-lookup"><span data-stu-id="3e16e-128">Note the smart-tag glyph (![Smart Tag Glyph](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) that appears on the side of the <xref:System.Windows.Forms.TabControl>.</span></span>  
  
2.  <span data-ttu-id="3e16e-129">スマート タグ グリフをクリックします。</span><span class="sxs-lookup"><span data-stu-id="3e16e-129">Click the smart-tag glyph.</span></span> <span data-ttu-id="3e16e-130">グリフの横に表示されるショートカット メニューで、選択、**タブの追加**項目。</span><span class="sxs-lookup"><span data-stu-id="3e16e-130">In the shortcut menu that appears next to the glyph, select the **Add Tab** item.</span></span> <span data-ttu-id="3e16e-131">新しいタブ ページが追加されたことを確認、<xref:System.Windows.Forms.TabControl>します。</span><span class="sxs-lookup"><span data-stu-id="3e16e-131">Observe that a new tab page is added to the <xref:System.Windows.Forms.TabControl>.</span></span>  
  
3.  <span data-ttu-id="3e16e-132"><xref:System.Windows.Forms.TableLayoutPanel> ツールボックス **から** コントロールをフォームにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="3e16e-132">Drag a <xref:System.Windows.Forms.TableLayoutPanel> control from the **Toolbox** onto your form.</span></span>  
  
4.  <span data-ttu-id="3e16e-133">スマート タグ グリフをクリックします。</span><span class="sxs-lookup"><span data-stu-id="3e16e-133">Click the smart-tag glyph.</span></span> <span data-ttu-id="3e16e-134">グリフの横に表示されるショートカット メニューで、選択、**列の追加**項目。</span><span class="sxs-lookup"><span data-stu-id="3e16e-134">In the shortcut menu that appears next to the glyph, select the **Add Column** item.</span></span> <span data-ttu-id="3e16e-135">新しい列が追加されたことを確認、<xref:System.Windows.Forms.TableLayoutPanel>コントロール。</span><span class="sxs-lookup"><span data-stu-id="3e16e-135">Observe that a new column is added to the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>  
  
5.  <span data-ttu-id="3e16e-136"><xref:System.Windows.Forms.SplitContainer> ツールボックス **から** コントロールをフォームにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="3e16e-136">Drag a <xref:System.Windows.Forms.SplitContainer> control from the **Toolbox** onto your form.</span></span>  
  
6.  <span data-ttu-id="3e16e-137">スマート タグ グリフをクリックします。</span><span class="sxs-lookup"><span data-stu-id="3e16e-137">Click the smart-tag glyph.</span></span> <span data-ttu-id="3e16e-138">グリフの横に表示されるショートカット メニューで、選択、**水平分割の向き**項目。</span><span class="sxs-lookup"><span data-stu-id="3e16e-138">In the shortcut menu that appears next to the glyph, select the **Horizontal splitter orientation** item.</span></span> <span data-ttu-id="3e16e-139">観察、<xref:System.Windows.Forms.SplitContainer>コントロールのスプリッター バーが水平方向します。</span><span class="sxs-lookup"><span data-stu-id="3e16e-139">Observe that the <xref:System.Windows.Forms.SplitContainer> control's splitter bar is now oriented horizontally.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e16e-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="3e16e-140">See also</span></span>
- <xref:System.Windows.Forms.TextBox>
- <xref:System.Windows.Forms.TabControl>
- <xref:System.Windows.Forms.SplitContainer>
- <xref:System.ComponentModel.Design.DesignerActionList>
- [<span data-ttu-id="3e16e-141">チュートリアル: Windows フォーム コンポーネントにスマート タグの追加</span><span class="sxs-lookup"><span data-stu-id="3e16e-141">Walkthrough: Adding Smart Tags to a Windows Forms Component</span></span>](https://msdn.microsoft.com/library/a6814169-fa7d-4527-808c-637ca5c95f63)
