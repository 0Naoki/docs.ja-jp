---
title: TabControl コントロールの概要 (Windows フォーム)
ms.date: 03/30/2017
f1_keywords:
- TabControl
helpviewer_keywords:
- TabControl control [Windows Forms], about TabControl control
- tab pages [Windows Forms], about tab pages
- property pages [Windows Forms], Windows Forms
- Windows Forms dialog boxes [Windows Forms], tabs
ms.assetid: 2b4ea784-a39d-463c-81d8-af74ce068476
ms.openlocfilehash: 266421ac7182b80a0628b92d1f357afd48ca5e7e
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/09/2019
ms.locfileid: "57712761"
---
# <a name="tabcontrol-control-overview-windows-forms"></a><span data-ttu-id="ed237-102">TabControl コントロールの概要 (Windows フォーム)</span><span class="sxs-lookup"><span data-stu-id="ed237-102">TabControl Control Overview (Windows Forms)</span></span>
<span data-ttu-id="ed237-103">Windows フォーム <xref:System.Windows.Forms.TabControl> は、ノートの仕切りや書類キャビネットのフォルダー セットのラベルに似た、複数のタブを表示します。</span><span class="sxs-lookup"><span data-stu-id="ed237-103">The Windows Forms <xref:System.Windows.Forms.TabControl> displays multiple tabs, like dividers in a notebook or labels in a set of folders in a filing cabinet.</span></span> <span data-ttu-id="ed237-104">タブには画像やその他のコントロールを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="ed237-104">The tabs can contain pictures and other controls.</span></span> <span data-ttu-id="ed237-105">タブ コントロールは、Windows オペレーティング システムのコントロール パネルの表示プロパティなど、多くの場所に表示される複数のページ ダイアログ ボックスの種類を生成するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="ed237-105">You can use the tab control to produce the kind of multiple-page dialog box that appears many places in the Windows operating system, such as the Control Panel Display Properties.</span></span> <span data-ttu-id="ed237-106">さらに、<xref:System.Windows.Forms.TabControl>関連のプロパティのグループの設定に使用されるプロパティ ページを作成するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="ed237-106">Additionally, the <xref:System.Windows.Forms.TabControl> can be used to create property pages, which are used to set a group of related properties.</span></span>  
  
## <a name="working-with-tabcontrol"></a><span data-ttu-id="ed237-107">TabControl の操作</span><span class="sxs-lookup"><span data-stu-id="ed237-107">Working with TabControl</span></span>  
 <span data-ttu-id="ed237-108">最も重要なプロパティ、<xref:System.Windows.Forms.TabControl>は<xref:System.Windows.Forms.TabControl.TabPages%2A>、個々 のタブが含まれています。</span><span class="sxs-lookup"><span data-stu-id="ed237-108">The most important property of the <xref:System.Windows.Forms.TabControl> is <xref:System.Windows.Forms.TabControl.TabPages%2A>, which contains the individual tabs.</span></span> <span data-ttu-id="ed237-109">各タブは、<xref:System.Windows.Forms.TabPage>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="ed237-109">Each individual tab is a <xref:System.Windows.Forms.TabPage> object.</span></span> <span data-ttu-id="ed237-110">タブをクリックすると生成、<xref:System.Windows.Forms.Control.Click>をイベント<xref:System.Windows.Forms.TabPage>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="ed237-110">When a tab is clicked, it raises the <xref:System.Windows.Forms.Control.Click> event for that <xref:System.Windows.Forms.TabPage> object.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed237-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="ed237-111">See also</span></span>
- <xref:System.Windows.Forms.TabControl>
- [<span data-ttu-id="ed237-112">TabControl コントロール</span><span class="sxs-lookup"><span data-stu-id="ed237-112">TabControl Control</span></span>](tabcontrol-control-windows-forms.md)
- [<span data-ttu-id="ed237-113">方法: Windows フォーム TabControl の外観を変更します。</span><span class="sxs-lookup"><span data-stu-id="ed237-113">How to: Change the Appearance of the Windows Forms TabControl</span></span>](how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)
- [<span data-ttu-id="ed237-114">方法: タブ ページにコントロールを追加します。</span><span class="sxs-lookup"><span data-stu-id="ed237-114">How to: Add a Control to a Tab Page</span></span>](how-to-add-a-control-to-a-tab-page.md)
- [<span data-ttu-id="ed237-115">方法: Windows フォーム tabcontrol のタブ追加および削除</span><span class="sxs-lookup"><span data-stu-id="ed237-115">How to: Add and Remove Tabs with the Windows Forms TabControl</span></span>](how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol.md)
- [<span data-ttu-id="ed237-116">方法: タブ ページを無効にします。</span><span class="sxs-lookup"><span data-stu-id="ed237-116">How to: Disable Tab Pages</span></span>](how-to-disable-tab-pages.md)
- [<span data-ttu-id="ed237-117">Windows フォームのダイアログ ボックス</span><span class="sxs-lookup"><span data-stu-id="ed237-117">Dialog Boxes in Windows Forms</span></span>](../dialog-boxes-in-windows-forms.md)
