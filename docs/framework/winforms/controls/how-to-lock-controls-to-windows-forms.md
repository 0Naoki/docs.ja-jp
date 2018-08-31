---
title: '方法 : Windows フォームにコントロールをロックする'
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms controls, locking
- controls [Windows Forms], locking
ms.assetid: 94efe0d2-c14e-4d14-b903-63ea9b07e290
ms.openlocfilehash: 8de22ae6667446620867f3c15aac3c4af65582bf
ms.sourcegitcommit: fe02afbc39e78afd78cc6050e4a9c12a75f579f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2018
ms.locfileid: "43253631"
---
# <a name="how-to-lock-controls-to-windows-forms"></a><span data-ttu-id="3be9d-102">方法 : Windows フォームにコントロールをロックする</span><span class="sxs-lookup"><span data-stu-id="3be9d-102">How to: Lock Controls to Windows Forms</span></span>
<span data-ttu-id="3be9d-103">Windows アプリケーションのユーザー インターフェイス (UI) を設計するときは、正しく配置を誤って移動や、その他のプロパティを設定するときにサイズを変更しないようにすると、コントロールをロックできます。</span><span class="sxs-lookup"><span data-stu-id="3be9d-103">When you design the user interface (UI) of your Windows application, you can lock the controls once they are positioned correctly, so that you do not inadvertently move or resize them when setting other properties.</span></span>  
  
 <span data-ttu-id="3be9d-104">さらに、ロックして、フォーム、一度に多くのコントロールをフォームには、上のすべてのコントロールをロック解除することができますか、個々 のコントロールのロックを解除することができます。</span><span class="sxs-lookup"><span data-stu-id="3be9d-104">Additionally, you can lock and unlock all the controls on the form at once, which is helpful for forms with many controls, or you can unlock individual controls.</span></span> <span data-ttu-id="3be9d-105">すべてのコントロールを配置し、フォーム上の任意の場所が後、を誤って移動を防ぐためにすべてのロックします。</span><span class="sxs-lookup"><span data-stu-id="3be9d-105">Once you have placed all the controls where you want them on the form, lock them all in place to prevent erroneous movement.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3be9d-106">実際に画面に表示されるダイアログ ボックスとメニュー コマンドは、アクティブな設定またはエディションによっては、ヘルプの説明と異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="3be9d-106">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="3be9d-107">設定を変更するには、 **[ツール]** メニューの **[設定のインポートとエクスポート]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3be9d-107">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="3be9d-108">詳細については、「[Visual Studio IDE のカスタマイズ](/visualstudio/ide/personalizing-the-visual-studio-ide)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3be9d-108">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-lock-a-control"></a><span data-ttu-id="3be9d-109">コントロールをロックするには</span><span class="sxs-lookup"><span data-stu-id="3be9d-109">To lock a control</span></span>  
  
1.  <span data-ttu-id="3be9d-110">**プロパティ**ウィンドウで、をクリックして、**ロック**プロパティと選択`true`します。</span><span class="sxs-lookup"><span data-stu-id="3be9d-110">In the **Properties** window, click the **Locked** property and select `true`.</span></span> <span data-ttu-id="3be9d-111">(名前をダブルクリックするとは、プロパティの設定を切り替えます。)</span><span class="sxs-lookup"><span data-stu-id="3be9d-111">(Double-clicking the name toggles the property setting.)</span></span>  
  
     <span data-ttu-id="3be9d-112">または、コントロールを右クリックし、選択**ロック コントロール**します。</span><span class="sxs-lookup"><span data-stu-id="3be9d-112">Alternatively, right-click the control and choose **Lock Controls**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3be9d-113">コントロールがロックされないように、デザイン サーフェイスの新しいサイズまたは場所にドラッグされています。</span><span class="sxs-lookup"><span data-stu-id="3be9d-113">Locking controls prevents them from being dragged to a new size or location on the design surface.</span></span> <span data-ttu-id="3be9d-114">ただし、することができます、サイズや位置を変更ことで、コントロールの**プロパティ**ウィンドウまたはコード。</span><span class="sxs-lookup"><span data-stu-id="3be9d-114">However, you can still change the size or location of controls by means of the **Properties** window or in code.</span></span>  
  
### <a name="to-lock-all-the-controls-on-a-form"></a><span data-ttu-id="3be9d-115">フォーム上のすべてのコントロールをロックするには</span><span class="sxs-lookup"><span data-stu-id="3be9d-115">To lock all the controls on a form</span></span>  
  
1.  <span data-ttu-id="3be9d-116">**形式**] メニューの [選択**ロック コントロール**します。</span><span class="sxs-lookup"><span data-stu-id="3be9d-116">From the **Format** menu, choose **Lock Controls**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3be9d-117">このコマンドは、フォームがコントロールであるため、フォームのサイズもをロックします。</span><span class="sxs-lookup"><span data-stu-id="3be9d-117">This command locks the form's size as well, because a form is a control.</span></span>  
  
### <a name="to-unlock-all-locked-controls-on-a-form"></a><span data-ttu-id="3be9d-118">フォーム上のコントロールがロックされているすべてのロックを解除するには</span><span class="sxs-lookup"><span data-stu-id="3be9d-118">To unlock all locked controls on a form</span></span>  
  
1.  <span data-ttu-id="3be9d-119">**形式**] メニューの [選択**ロック コントロール**します。</span><span class="sxs-lookup"><span data-stu-id="3be9d-119">From the **Format** menu, choose **Lock Controls**.</span></span>  
  
     <span data-ttu-id="3be9d-120">フォーム上のすべてのロックされているコントロールがロックを解除します。</span><span class="sxs-lookup"><span data-stu-id="3be9d-120">All previously locked controls on the form are now unlocked.</span></span>  
  
### <a name="to-unlock-locked-controls-individually"></a><span data-ttu-id="3be9d-121">ロックを解除するには、コントロールを個別にロック</span><span class="sxs-lookup"><span data-stu-id="3be9d-121">To unlock locked controls individually</span></span>  
  
1.  <span data-ttu-id="3be9d-122">**プロパティ**ウィンドウで、をクリックして、**ロック**プロパティと選択`false`します。</span><span class="sxs-lookup"><span data-stu-id="3be9d-122">In the **Properties** window, click the **Locked** property and select `false`.</span></span> <span data-ttu-id="3be9d-123">(名前をダブルクリックするとは、プロパティの設定を切り替えます。)</span><span class="sxs-lookup"><span data-stu-id="3be9d-123">(Double-clicking the name toggles the property setting.)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3be9d-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="3be9d-124">See Also</span></span>  
 [<span data-ttu-id="3be9d-125">Windows フォーム コントロール</span><span class="sxs-lookup"><span data-stu-id="3be9d-125">Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/index.md)  
 [<span data-ttu-id="3be9d-126">Windows フォームでのコントロールの配置</span><span class="sxs-lookup"><span data-stu-id="3be9d-126">Arranging Controls on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)  
 [<span data-ttu-id="3be9d-127">各 Windows フォーム コントロールのラベル設定とショートカットの作成</span><span class="sxs-lookup"><span data-stu-id="3be9d-127">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)  
 [<span data-ttu-id="3be9d-128">Windows フォームで使用するコントロール</span><span class="sxs-lookup"><span data-stu-id="3be9d-128">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 [<span data-ttu-id="3be9d-129">Windows フォーム コントロールの機能別一覧</span><span class="sxs-lookup"><span data-stu-id="3be9d-129">Windows Forms Controls by Function</span></span>](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md)
