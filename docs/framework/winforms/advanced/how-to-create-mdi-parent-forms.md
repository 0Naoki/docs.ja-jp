---
title: '方法: MDI 親フォームを作成します。'
ms.date: 03/30/2017
helpviewer_keywords:
- parent forms
- MDI [Windows Forms], creating forms
ms.assetid: 12c71221-2377-4bb6-b10b-7b4b300fd462
ms.openlocfilehash: 5da7f1a53412cf30a5898fec096aaa01e3aa65d2
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/09/2019
ms.locfileid: "57722985"
---
# <a name="how-to-create-mdi-parent-forms"></a><span data-ttu-id="b1df5-102">方法: MDI 親フォームを作成します。</span><span class="sxs-lookup"><span data-stu-id="b1df5-102">How to: Create MDI Parent Forms</span></span>
> [!IMPORTANT]
>  <span data-ttu-id="b1df5-103">このトピックでは、既に <xref:System.Windows.Forms.MainMenu> コントロールで置き換えられている <xref:System.Windows.Forms.MenuStrip> コントロールを使用します。</span><span class="sxs-lookup"><span data-stu-id="b1df5-103">This topic uses the <xref:System.Windows.Forms.MainMenu> control, which has been replaced by the <xref:System.Windows.Forms.MenuStrip> control.</span></span> <span data-ttu-id="b1df5-104">
  <xref:System.Windows.Forms.MainMenu> コントロールは、下位互換性と将来の使用 (必要に応じて) の両方のために保持されています。</span><span class="sxs-lookup"><span data-stu-id="b1df5-104">The <xref:System.Windows.Forms.MainMenu> control is retained for both backward compatibility and future use, if you choose.</span></span>  <span data-ttu-id="b1df5-105">使用して親フォームの MDI の作成については、<xref:System.Windows.Forms.MenuStrip>を参照してください[方法。MenuStrip を MDI ウィンドウのリストを作成する](../controls/how-to-create-an-mdi-window-list-with-menustrip-windows-forms.md)します。</span><span class="sxs-lookup"><span data-stu-id="b1df5-105">For information about creating a MDI parent Form by using a <xref:System.Windows.Forms.MenuStrip>, see [How to: Create an MDI Window List with MenuStrip](../controls/how-to-create-an-mdi-window-list-with-menustrip-windows-forms.md).</span></span>  
  
 <span data-ttu-id="b1df5-106">マルチドキュメント インターフェイス (MDI) アプリケーションの基盤となるのは、MDI 親フォームです。</span><span class="sxs-lookup"><span data-stu-id="b1df5-106">The foundation of a Multiple-Document Interface (MDI) application is the MDI parent form.</span></span> <span data-ttu-id="b1df5-107">これは、サブウィンドウである MDI 子ウィンドウを含むフォームで、ユーザーは MDI 子ウィンドウで MDI アプリケーションと対話します。</span><span class="sxs-lookup"><span data-stu-id="b1df5-107">This is the form that contains the MDI child windows, which are the sub-windows wherein the user interacts with the MDI application.</span></span> <span data-ttu-id="b1df5-108">MDI 親フォームの作成は簡単で、Windows フォーム デザイナーまたはプログラムで作成できます。</span><span class="sxs-lookup"><span data-stu-id="b1df5-108">Creating an MDI parent form is easy, both in the Windows Forms Designer and programmatically.</span></span>  
  
### <a name="to-create-an-mdi-parent-form-at-design-time"></a><span data-ttu-id="b1df5-109">デザイン時に MDI 親フォームを作成するには</span><span class="sxs-lookup"><span data-stu-id="b1df5-109">To create an MDI parent form at design time</span></span>  
  
1.  <span data-ttu-id="b1df5-110">Windows アプリケーション プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="b1df5-110">Create a Windows Application project.</span></span>  
  
2.  <span data-ttu-id="b1df5-111">**プロパティ**ウィンドウで、設定、<xref:System.Windows.Forms.Form.IsMdiContainer%2A>プロパティを**true**します。</span><span class="sxs-lookup"><span data-stu-id="b1df5-111">In the **Properties** window, set the <xref:System.Windows.Forms.Form.IsMdiContainer%2A> property to **true**.</span></span>  
  
     <span data-ttu-id="b1df5-112">これによって、フォームが子ウィンドウの MDI コンテナーとして指定されます。</span><span class="sxs-lookup"><span data-stu-id="b1df5-112">This designates the form as an MDI container for child windows.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b1df5-113">**[プロパティ]** ウィンドウでプロパティを設定するときに、必要に応じて、`WindowState` プロパティを **[Maximized]** に設定することもできます。MDI 子ウィンドウは、親フォームが最大化しているときに最も簡単に操作できます。</span><span class="sxs-lookup"><span data-stu-id="b1df5-113">While setting properties in the **Properties** window, you can also set the `WindowState` property to **Maximized**, if you like, as it is easiest to manipulate MDI child windows when the parent form is maximized.</span></span> <span data-ttu-id="b1df5-114">また、MDI 親フォームの端には、<xref:System.Windows.Forms.Control.BackColor%2A?displayProperty=nameWithType> プロパティを使用して設定した背景色ではなく、(Windows システムのコントロール パネルで設定した) システム カラーが適用されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="b1df5-114">Additionally, be aware that the edge of the MDI parent form will pick up the system color (set in the Windows System Control Panel), rather than the back color you set using the <xref:System.Windows.Forms.Control.BackColor%2A?displayProperty=nameWithType> property.</span></span>  
  
3.  <span data-ttu-id="b1df5-115">**[ツールボックス]** から、**[MenuStrip]** コントロールをフォームにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="b1df5-115">From the **Toolbox**, drag a **MenuStrip** control to the form.</span></span> <span data-ttu-id="b1df5-116">**Text** プロパティを「**ファイル (F)**」に設定し、「**新規作成 (N)**」と「**閉じる (C)**」というサブメニュー項目を指定して、トップレベルのメニュー項目を作成します。</span><span class="sxs-lookup"><span data-stu-id="b1df5-116">Create a top-level menu item with the **Text** property set to **&File** with submenu items called **&New** and **&Close**.</span></span> <span data-ttu-id="b1df5-117">また、「**ウィンドウ (W)**」というトップレベルのメニュー項目も作成します。</span><span class="sxs-lookup"><span data-stu-id="b1df5-117">Also create a top-level menu item called **&Window**.</span></span>  
  
     <span data-ttu-id="b1df5-118">最初のメニューでは、実行時にメニュー項目を作成したり非表示にしたりします。2 つ目のメニューでは、開いている MDI 子ウィンドウを追跡します。</span><span class="sxs-lookup"><span data-stu-id="b1df5-118">The first menu will create and hide menu items at run time, and the second menu will keep track of the open MDI child windows.</span></span> <span data-ttu-id="b1df5-119">これで、MDI 親ウィンドウの作成が完了しました。</span><span class="sxs-lookup"><span data-stu-id="b1df5-119">At this point, you have created an MDI parent window.</span></span>  
  
4.  <span data-ttu-id="b1df5-120">**F5** キーを押してアプリケーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="b1df5-120">Press **F5** to run the application.</span></span> <span data-ttu-id="b1df5-121">MDI 親フォーム内で動作する windows MDI 子フォームを作成する方法の詳細については、次を参照してください。[方法。MDI 子フォームを作成](how-to-create-mdi-child-forms.md)です。</span><span class="sxs-lookup"><span data-stu-id="b1df5-121">For information about creating MDI child windows that operate within the MDI parent form, see [How to: Create MDI Child Forms](how-to-create-mdi-child-forms.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1df5-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="b1df5-122">See also</span></span>
- [<span data-ttu-id="b1df5-123">マルチ ドキュメント インターフェイス (MDI) アプリケーション</span><span class="sxs-lookup"><span data-stu-id="b1df5-123">Multiple-Document Interface (MDI) Applications</span></span>](multiple-document-interface-mdi-applications.md)
- [<span data-ttu-id="b1df5-124">方法: MDI 子フォームを作成します。</span><span class="sxs-lookup"><span data-stu-id="b1df5-124">How to: Create MDI Child Forms</span></span>](how-to-create-mdi-child-forms.md)
- [<span data-ttu-id="b1df5-125">方法: アクティブな MDI 子を決定します。</span><span class="sxs-lookup"><span data-stu-id="b1df5-125">How to: Determine the Active MDI Child</span></span>](how-to-determine-the-active-mdi-child.md)
- [<span data-ttu-id="b1df5-126">方法: アクティブな MDI 子ウィンドウにデータを送信します。</span><span class="sxs-lookup"><span data-stu-id="b1df5-126">How to: Send Data to the Active MDI Child</span></span>](how-to-send-data-to-the-active-mdi-child.md)
- [<span data-ttu-id="b1df5-127">方法: MDI 子フォームを配置します。</span><span class="sxs-lookup"><span data-stu-id="b1df5-127">How to: Arrange MDI Child Forms</span></span>](how-to-arrange-mdi-child-forms.md)
