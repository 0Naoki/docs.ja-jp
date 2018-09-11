---
title: '方法 : UserControl クラスを継承する'
ms.date: 03/30/2017
helpviewer_keywords:
- inheritance [Windows Forms], Windows Forms custom controls
- UserControl class [Windows Forms], inheriting from
- user controls [Windows Forms], creating
- composite controls [Windows Forms], creating
ms.assetid: 67713625-e2e4-4f6a-bce7-0855ee5043d9
ms.openlocfilehash: 5a826b9fc68bebfa32049a38899ddffaacd25607
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2018
ms.locfileid: "44260133"
---
# <a name="how-to-inherit-from-the-usercontrol-class"></a><span data-ttu-id="1c2e7-102">方法 : UserControl クラスを継承する</span><span class="sxs-lookup"><span data-stu-id="1c2e7-102">How to: Inherit from the UserControl Class</span></span>
<span data-ttu-id="1c2e7-103">カスタム コードを使用して 1 つ以上の Windows フォーム コントロールの機能を組み合わせるには、"*ユーザー コントロール*" を作成します。</span><span class="sxs-lookup"><span data-stu-id="1c2e7-103">To combine the functionality of one or more Windows Forms controls with custom code, you can create a *user control*.</span></span> <span data-ttu-id="1c2e7-104">ユーザー コントロールは、迅速なコントロール開発、標準の Windows フォーム コントロールの機能、およびカスタム プロパティやカスタム メソッドの多用途性を組み合わせたものです。</span><span class="sxs-lookup"><span data-stu-id="1c2e7-104">User controls combine rapid control development, standard Windows Forms control functionality, and the versatility of custom properties and methods.</span></span> <span data-ttu-id="1c2e7-105">ユーザー コントロールの作成を開始すると、デザイナーが表示され、標準の Windows フォーム コントロールを配置できます。</span><span class="sxs-lookup"><span data-stu-id="1c2e7-105">When you begin creating a user control, you are presented with a visible designer, upon which you can place standard Windows Forms controls.</span></span> <span data-ttu-id="1c2e7-106">これらのコントロールは、標準コントロールの外観と動作 (ルック アンド フィール) に加えて、固有の機能のすべてを保持します。</span><span class="sxs-lookup"><span data-stu-id="1c2e7-106">These controls retain all of their inherent functionality, as well as the appearance and behavior (look and feel) of standard controls.</span></span> <span data-ttu-id="1c2e7-107">ただし、これらのコントロールをユーザー コントロールに組み込んだ場合、コードを介して使用することはできなくなります。</span><span class="sxs-lookup"><span data-stu-id="1c2e7-107">Once these controls are built into the user control, however, they are no longer available to you through code.</span></span> <span data-ttu-id="1c2e7-108">ユーザー コントロールは独自の描画を行い、標準コントロールに関連付けられた基本的な機能もすべて処理します。</span><span class="sxs-lookup"><span data-stu-id="1c2e7-108">The user control does its own painting and also handles all of the basic functionality associated with controls.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1c2e7-109">実際に画面に表示されるダイアログ ボックスとメニュー コマンドは、アクティブな設定またはエディションによっては、ヘルプの説明と異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="1c2e7-109">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="1c2e7-110">設定を変更するには、 **[ツール]** メニューの **[設定のインポートとエクスポート]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1c2e7-110">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="1c2e7-111">詳細については、「[Visual Studio IDE のカスタマイズ](/visualstudio/ide/personalizing-the-visual-studio-ide)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1c2e7-111">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-create-a-user-control"></a><span data-ttu-id="1c2e7-112">ユーザー コントロールを作成するには</span><span class="sxs-lookup"><span data-stu-id="1c2e7-112">To create a user control</span></span>  
  
1.  <span data-ttu-id="1c2e7-113">新しい **Windows コントロール ライブラリ** プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="1c2e7-113">Create a new **Windows Control Library** project.</span></span>  
  
     <span data-ttu-id="1c2e7-114">空白のユーザー コントロールを含む新しいプロジェクトが作成されます。</span><span class="sxs-lookup"><span data-stu-id="1c2e7-114">A new project is created with a blank user control.</span></span>  
  
2.  <span data-ttu-id="1c2e7-115">コントロールを、**ツールボックス**の **[Windows フォーム]** タブからデザイナーにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="1c2e7-115">Drag controls from the **Windows Forms** tab of the **Toolbox** onto your designer.</span></span>  
  
3.  <span data-ttu-id="1c2e7-116">こうしたコントロールは、最終的なユーザー コントロールに表示するときと同じように、配置およびデザインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1c2e7-116">These controls should be positioned and designed as you want them to appear in the final user control.</span></span> <span data-ttu-id="1c2e7-117">開発者が内在コントロールにアクセスできるようにするには、内在コントロールをパブリックとして宣言するか、内在コントロールを選択して公開します。</span><span class="sxs-lookup"><span data-stu-id="1c2e7-117">If you want to allow developers to access the constituent controls, you must declare them as public, or selectively expose properties of the constituent control.</span></span> <span data-ttu-id="1c2e7-118">詳細については、「[方法: 内在コントロールのプロパティを公開する](../../../../docs/framework/winforms/controls/how-to-expose-properties-of-constituent-controls.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1c2e7-118">For details, see [How to: Expose Properties of Constituent Controls](../../../../docs/framework/winforms/controls/how-to-expose-properties-of-constituent-controls.md).</span></span>  
  
4.  <span data-ttu-id="1c2e7-119">コントロールに組み込むカスタム メソッドやカスタム プロパティを実装します。</span><span class="sxs-lookup"><span data-stu-id="1c2e7-119">Implement any custom methods or properties that your control will incorporate.</span></span>  
  
5.  <span data-ttu-id="1c2e7-120">F5 キーを押してプロジェクトをビルドし、**UserControl Test Container** でコントロールを実行します。</span><span class="sxs-lookup"><span data-stu-id="1c2e7-120">Press F5 to build the project and run your control in the **UserControl Test Container**.</span></span> <span data-ttu-id="1c2e7-121">詳細については、「[方法: UserControl の実行時の動作をテストする](../../../../docs/framework/winforms/controls/how-to-test-the-run-time-behavior-of-a-usercontrol.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1c2e7-121">For more information, see [How to: Test the Run-Time Behavior of a UserControl](../../../../docs/framework/winforms/controls/how-to-test-the-run-time-behavior-of-a-usercontrol.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c2e7-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="1c2e7-122">See Also</span></span>  
 [<span data-ttu-id="1c2e7-123">さまざまなカスタム コントロール</span><span class="sxs-lookup"><span data-stu-id="1c2e7-123">Varieties of Custom Controls</span></span>](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)  
 [<span data-ttu-id="1c2e7-124">方法: コントロール クラスを継承する</span><span class="sxs-lookup"><span data-stu-id="1c2e7-124">How to: Inherit from the Control Class</span></span>](../../../../docs/framework/winforms/controls/how-to-inherit-from-the-control-class.md)  
 [<span data-ttu-id="1c2e7-125">方法: 既存の Windows フォーム コントロールから継承する</span><span class="sxs-lookup"><span data-stu-id="1c2e7-125">How to: Inherit from Existing Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/how-to-inherit-from-existing-windows-forms-controls.md)  
 [<span data-ttu-id="1c2e7-126">方法: Windows フォームのコントロールを作成する</span><span class="sxs-lookup"><span data-stu-id="1c2e7-126">How to: Author Controls for Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-author-controls-for-windows-forms.md)  
 [<span data-ttu-id="1c2e7-127">Visual Basic での継承されたイベント ハンドラーのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="1c2e7-127">Troubleshooting Inherited Event Handlers in Visual Basic</span></span>](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)  
 [<span data-ttu-id="1c2e7-128">方法: UserControl の実行時の動作をテストする</span><span class="sxs-lookup"><span data-stu-id="1c2e7-128">How to: Test the Run-Time Behavior of a UserControl</span></span>](../../../../docs/framework/winforms/controls/how-to-test-the-run-time-behavior-of-a-usercontrol.md)
