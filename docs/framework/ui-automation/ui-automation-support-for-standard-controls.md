---
title: UI オートメーションによる標準コントロールのサポート
ms.date: 03/30/2017
helpviewer_keywords:
- controls, UI Automation support for
- UI Automation, support for standard controls
ms.assetid: 3770ea8a-2655-4add-9c59-fe0610ad5084
ms.openlocfilehash: 5dbd547378faf885f5d0349ff77d124b0b860591
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2019
ms.locfileid: "57677631"
---
# <a name="ui-automation-support-for-standard-controls"></a><span data-ttu-id="89a3f-102">UI オートメーションによる標準コントロールのサポート</span><span class="sxs-lookup"><span data-stu-id="89a3f-102">UI Automation Support for Standard Controls</span></span>
> [!NOTE]
>  <span data-ttu-id="89a3f-103">このドキュメントは、[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 名前空間で定義されているマネージド <xref:System.Windows.Automation> クラスを使用する .NET Framework 開発者を対象としています。</span><span class="sxs-lookup"><span data-stu-id="89a3f-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="89a3f-104">に関する最新情報については[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]を参照してください[Windows Automation API:UI オートメーション](https://go.microsoft.com/fwlink/?LinkID=156746)します。</span><span class="sxs-lookup"><span data-stu-id="89a3f-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="89a3f-105">このトピックでは、 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] 、 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)]、および [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)]フレームワーク向けに開発されたアプリケーションの標準コントロールに対する [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)] サポートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="89a3f-105">This topic contains information about [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] support for standard controls in applications developed for the [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)], and [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)] frameworks.</span></span>  
  
<a name="Windows_Presentation_Foundation_Controls"></a>   
## <a name="windows-presentation-foundation-controls"></a><span data-ttu-id="89a3f-106">Windows Presentation Foundation コントロール</span><span class="sxs-lookup"><span data-stu-id="89a3f-106">Windows Presentation Foundation Controls</span></span>  
 <span data-ttu-id="89a3f-107">ユーザー操作に関する情報やサポートを提供するすべての [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] コントロール要素は、 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]を全面的にネイティブ サポートしています。</span><span class="sxs-lookup"><span data-stu-id="89a3f-107">All [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] control elements that provide information or support for user interaction have full native support for [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="89a3f-108">パネルなどのその他の要素は、 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]からは認識できません。</span><span class="sxs-lookup"><span data-stu-id="89a3f-108">Other elements, such as panels, are not visible to [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span>  
  
<a name="Win32_Controls"></a>   
## <a name="win32-controls"></a><span data-ttu-id="89a3f-109">Win32 コントロール</span><span class="sxs-lookup"><span data-stu-id="89a3f-109">Win32 Controls</span></span>  
 <span data-ttu-id="89a3f-110">ほとんどの [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] コントロールは、UIAutomationClientsideProviders.dll のクライアント側プロバイダーによって [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] に公開されています。</span><span class="sxs-lookup"><span data-stu-id="89a3f-110">Most [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="89a3f-111">このアセンブリは、UI オートメーション クライアント アプリケーションで使用するために、自動的に登録されます。</span><span class="sxs-lookup"><span data-stu-id="89a3f-111">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="89a3f-112">完全なサポートは、ComCtrl32.dll のバージョン 6 ( [!INCLUDE[TLA#tla_winxp](../../../includes/tlasharptla-winxp-md.md)] 以降で使用可能) のコントロールに対してのみ提供されています。</span><span class="sxs-lookup"><span data-stu-id="89a3f-112">Full support is provided only for controls from version 6 of ComCtrl32.dll (available with [!INCLUDE[TLA#tla_winxp](../../../includes/tlasharptla-winxp-md.md)] and later).</span></span>  
  
 <span data-ttu-id="89a3f-113">次のコントロールがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="89a3f-113">The following controls are supported.</span></span>  
  
|<span data-ttu-id="89a3f-114">クラス名</span><span class="sxs-lookup"><span data-stu-id="89a3f-114">Class name</span></span>|<span data-ttu-id="89a3f-115">コントロール型</span><span class="sxs-lookup"><span data-stu-id="89a3f-115">Control Type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="89a3f-116">ボタン</span><span class="sxs-lookup"><span data-stu-id="89a3f-116">Button</span></span>|<span data-ttu-id="89a3f-117">ボタン</span><span class="sxs-lookup"><span data-stu-id="89a3f-117">Button</span></span>|  
|<span data-ttu-id="89a3f-118">ボタン</span><span class="sxs-lookup"><span data-stu-id="89a3f-118">Button</span></span>|<span data-ttu-id="89a3f-119">RadioButton</span><span class="sxs-lookup"><span data-stu-id="89a3f-119">RadioButton</span></span>|  
|<span data-ttu-id="89a3f-120">ボタン</span><span class="sxs-lookup"><span data-stu-id="89a3f-120">Button</span></span>|<span data-ttu-id="89a3f-121">グループ化</span><span class="sxs-lookup"><span data-stu-id="89a3f-121">Group</span></span>|  
|<span data-ttu-id="89a3f-122">ボタン</span><span class="sxs-lookup"><span data-stu-id="89a3f-122">Button</span></span>|<span data-ttu-id="89a3f-123">CheckBox</span><span class="sxs-lookup"><span data-stu-id="89a3f-123">CheckBox</span></span>|  
|<span data-ttu-id="89a3f-124">ボタン</span><span class="sxs-lookup"><span data-stu-id="89a3f-124">Button</span></span>|<span data-ttu-id="89a3f-125">ハイパーリンク</span><span class="sxs-lookup"><span data-stu-id="89a3f-125">Hyperlink</span></span>|  
|<span data-ttu-id="89a3f-126">ボタン</span><span class="sxs-lookup"><span data-stu-id="89a3f-126">Button</span></span>|<span data-ttu-id="89a3f-127">SplitButton</span><span class="sxs-lookup"><span data-stu-id="89a3f-127">SplitButton</span></span>|  
|<span data-ttu-id="89a3f-128">ボタン</span><span class="sxs-lookup"><span data-stu-id="89a3f-128">Button</span></span>|<span data-ttu-id="89a3f-129">CheckBox</span><span class="sxs-lookup"><span data-stu-id="89a3f-129">CheckBox</span></span>|  
|<span data-ttu-id="89a3f-130">ComboBoxEx32</span><span class="sxs-lookup"><span data-stu-id="89a3f-130">ComboBoxEx32</span></span>|<span data-ttu-id="89a3f-131">ComboBox</span><span class="sxs-lookup"><span data-stu-id="89a3f-131">ComboBox</span></span>|  
|<span data-ttu-id="89a3f-132">ComboBox</span><span class="sxs-lookup"><span data-stu-id="89a3f-132">ComboBox</span></span>|<span data-ttu-id="89a3f-133">ComboBox</span><span class="sxs-lookup"><span data-stu-id="89a3f-133">ComboBox</span></span>|  
|<span data-ttu-id="89a3f-134">編集</span><span class="sxs-lookup"><span data-stu-id="89a3f-134">Edit</span></span>|<span data-ttu-id="89a3f-135">ドキュメント</span><span class="sxs-lookup"><span data-stu-id="89a3f-135">Document</span></span>|  
|<span data-ttu-id="89a3f-136">編集</span><span class="sxs-lookup"><span data-stu-id="89a3f-136">Edit</span></span>|<span data-ttu-id="89a3f-137">編集</span><span class="sxs-lookup"><span data-stu-id="89a3f-137">Edit</span></span>|  
|<span data-ttu-id="89a3f-138">SysLink</span><span class="sxs-lookup"><span data-stu-id="89a3f-138">SysLink</span></span>|<span data-ttu-id="89a3f-139">ハイパーリンク</span><span class="sxs-lookup"><span data-stu-id="89a3f-139">Hyperlink</span></span>|  
|<span data-ttu-id="89a3f-140">スタティック</span><span class="sxs-lookup"><span data-stu-id="89a3f-140">Static</span></span>|<span data-ttu-id="89a3f-141">テキスト</span><span class="sxs-lookup"><span data-stu-id="89a3f-141">Text</span></span>|  
|<span data-ttu-id="89a3f-142">スタティック</span><span class="sxs-lookup"><span data-stu-id="89a3f-142">Static</span></span>|<span data-ttu-id="89a3f-143">イメージ</span><span class="sxs-lookup"><span data-stu-id="89a3f-143">Image</span></span>|  
|<span data-ttu-id="89a3f-144">SysIPAddress32</span><span class="sxs-lookup"><span data-stu-id="89a3f-144">SysIPAddress32</span></span>|<span data-ttu-id="89a3f-145">カスタム</span><span class="sxs-lookup"><span data-stu-id="89a3f-145">Custom</span></span>|  
|<span data-ttu-id="89a3f-146">SysHeader32</span><span class="sxs-lookup"><span data-stu-id="89a3f-146">SysHeader32</span></span>|<span data-ttu-id="89a3f-147">Header/HeaderItem</span><span class="sxs-lookup"><span data-stu-id="89a3f-147">Header/HeaderItem</span></span>|  
|<span data-ttu-id="89a3f-148">SysListView32</span><span class="sxs-lookup"><span data-stu-id="89a3f-148">SysListView32</span></span>|<span data-ttu-id="89a3f-149">DataGrid</span><span class="sxs-lookup"><span data-stu-id="89a3f-149">DataGrid</span></span>|  
|<span data-ttu-id="89a3f-150">SysListView32</span><span class="sxs-lookup"><span data-stu-id="89a3f-150">SysListView32</span></span>|<span data-ttu-id="89a3f-151">リスト</span><span class="sxs-lookup"><span data-stu-id="89a3f-151">List</span></span>|  
|<span data-ttu-id="89a3f-152">ListBox</span><span class="sxs-lookup"><span data-stu-id="89a3f-152">ListBox</span></span>|<span data-ttu-id="89a3f-153">リスト</span><span class="sxs-lookup"><span data-stu-id="89a3f-153">List</span></span>|  
|<span data-ttu-id="89a3f-154">ListBox</span><span class="sxs-lookup"><span data-stu-id="89a3f-154">ListBox</span></span>|<span data-ttu-id="89a3f-155">ListItem</span><span class="sxs-lookup"><span data-stu-id="89a3f-155">ListItem</span></span>|  
|<span data-ttu-id="89a3f-156">#32768</span><span class="sxs-lookup"><span data-stu-id="89a3f-156">#32768</span></span>|<span data-ttu-id="89a3f-157">メニュー</span><span class="sxs-lookup"><span data-stu-id="89a3f-157">Menu</span></span>|  
|<span data-ttu-id="89a3f-158">#32768</span><span class="sxs-lookup"><span data-stu-id="89a3f-158">#32768</span></span>|<span data-ttu-id="89a3f-159">MenuItem</span><span class="sxs-lookup"><span data-stu-id="89a3f-159">MenuItem</span></span>|  
|<span data-ttu-id="89a3f-160">msctls_progress32</span><span class="sxs-lookup"><span data-stu-id="89a3f-160">msctls_progress32</span></span>|<span data-ttu-id="89a3f-161">ProgressBar</span><span class="sxs-lookup"><span data-stu-id="89a3f-161">ProgressBar</span></span>|  
|<span data-ttu-id="89a3f-162">RichEdit</span><span class="sxs-lookup"><span data-stu-id="89a3f-162">RichEdit</span></span>|<span data-ttu-id="89a3f-163">ドキュメント。</span><span class="sxs-lookup"><span data-stu-id="89a3f-163">Document.</span></span> <span data-ttu-id="89a3f-164">注を参照。</span><span class="sxs-lookup"><span data-stu-id="89a3f-164">See note.</span></span>|  
|<span data-ttu-id="89a3f-165">RichEdit20A</span><span class="sxs-lookup"><span data-stu-id="89a3f-165">RichEdit20A</span></span>|<span data-ttu-id="89a3f-166">ドキュメント</span><span class="sxs-lookup"><span data-stu-id="89a3f-166">Document</span></span>|  
|<span data-ttu-id="89a3f-167">RichEdit20W</span><span class="sxs-lookup"><span data-stu-id="89a3f-167">RichEdit20W</span></span>|<span data-ttu-id="89a3f-168">ドキュメント</span><span class="sxs-lookup"><span data-stu-id="89a3f-168">Document</span></span>|  
|<span data-ttu-id="89a3f-169">RichEdit50W</span><span class="sxs-lookup"><span data-stu-id="89a3f-169">RichEdit50W</span></span>|<span data-ttu-id="89a3f-170">ドキュメント</span><span class="sxs-lookup"><span data-stu-id="89a3f-170">Document</span></span>|  
|<span data-ttu-id="89a3f-171">ScrollBar</span><span class="sxs-lookup"><span data-stu-id="89a3f-171">ScrollBar</span></span>|<span data-ttu-id="89a3f-172">スライダー</span><span class="sxs-lookup"><span data-stu-id="89a3f-172">Slider</span></span>|  
|<span data-ttu-id="89a3f-173">msctls_trackbar32</span><span class="sxs-lookup"><span data-stu-id="89a3f-173">msctls_trackbar32</span></span>|<span data-ttu-id="89a3f-174">スライダー</span><span class="sxs-lookup"><span data-stu-id="89a3f-174">Slider</span></span>|  
|<span data-ttu-id="89a3f-175">msctls_updown32</span><span class="sxs-lookup"><span data-stu-id="89a3f-175">msctls_updown32</span></span>|<span data-ttu-id="89a3f-176">Spinner</span><span class="sxs-lookup"><span data-stu-id="89a3f-176">Spinner</span></span>|  
|<span data-ttu-id="89a3f-177">msctls_statusbar32</span><span class="sxs-lookup"><span data-stu-id="89a3f-177">msctls_statusbar32</span></span>|<span data-ttu-id="89a3f-178">StatusBar</span><span class="sxs-lookup"><span data-stu-id="89a3f-178">StatusBar</span></span>|  
|<span data-ttu-id="89a3f-179">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="89a3f-179">SysTabControl32</span></span>|<span data-ttu-id="89a3f-180">タブ</span><span class="sxs-lookup"><span data-stu-id="89a3f-180">Tab</span></span>|  
|<span data-ttu-id="89a3f-181">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="89a3f-181">SysTabControl32</span></span>|<span data-ttu-id="89a3f-182">TabItem</span><span class="sxs-lookup"><span data-stu-id="89a3f-182">TabItem</span></span>|  
|<span data-ttu-id="89a3f-183">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="89a3f-183">ToolbarWindow32</span></span>|<span data-ttu-id="89a3f-184">ToolBar</span><span class="sxs-lookup"><span data-stu-id="89a3f-184">ToolBar</span></span>|  
|<span data-ttu-id="89a3f-185">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="89a3f-185">ToolbarWindow32</span></span>|<span data-ttu-id="89a3f-186">MenuItem</span><span class="sxs-lookup"><span data-stu-id="89a3f-186">MenuItem</span></span>|  
|<span data-ttu-id="89a3f-187">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="89a3f-187">ToolbarWindow32</span></span>|<span data-ttu-id="89a3f-188">ボタン</span><span class="sxs-lookup"><span data-stu-id="89a3f-188">Button</span></span>|  
|<span data-ttu-id="89a3f-189">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="89a3f-189">ToolbarWindow32</span></span>|<span data-ttu-id="89a3f-190">CheckBox</span><span class="sxs-lookup"><span data-stu-id="89a3f-190">CheckBox</span></span>|  
|<span data-ttu-id="89a3f-191">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="89a3f-191">ToolbarWindow32</span></span>|<span data-ttu-id="89a3f-192">RadioButton</span><span class="sxs-lookup"><span data-stu-id="89a3f-192">RadioButton</span></span>|  
|<span data-ttu-id="89a3f-193">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="89a3f-193">ToolbarWindow32</span></span>|<span data-ttu-id="89a3f-194">区切り記号</span><span class="sxs-lookup"><span data-stu-id="89a3f-194">Separator</span></span>|  
|<span data-ttu-id="89a3f-195">tooltips_class32</span><span class="sxs-lookup"><span data-stu-id="89a3f-195">tooltips_class32</span></span>|<span data-ttu-id="89a3f-196">ヒント</span><span class="sxs-lookup"><span data-stu-id="89a3f-196">ToolTip</span></span>|  
|<span data-ttu-id="89a3f-197">#32774</span><span class="sxs-lookup"><span data-stu-id="89a3f-197">#32774</span></span>|<span data-ttu-id="89a3f-198">ヒント</span><span class="sxs-lookup"><span data-stu-id="89a3f-198">ToolTip</span></span>|  
|<span data-ttu-id="89a3f-199">ReBarWindow32</span><span class="sxs-lookup"><span data-stu-id="89a3f-199">ReBarWindow32</span></span>|<span data-ttu-id="89a3f-200">ツール バー</span><span class="sxs-lookup"><span data-stu-id="89a3f-200">Toolbar</span></span>|  
|<span data-ttu-id="89a3f-201">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="89a3f-201">SysTreeView32</span></span>|<span data-ttu-id="89a3f-202">ツリー</span><span class="sxs-lookup"><span data-stu-id="89a3f-202">Tree</span></span>|  
|<span data-ttu-id="89a3f-203">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="89a3f-203">SysTreeView32</span></span>|<span data-ttu-id="89a3f-204">TreeItem</span><span class="sxs-lookup"><span data-stu-id="89a3f-204">TreeItem</span></span>|  
  
 <span data-ttu-id="89a3f-205">**注** RichEdit コントロールは、 [!INCLUDE[TLA#tla_winvista](../../../includes/tlasharptla-winvista-md.md)] に付属するバージョン (RichEd20.dll バージョン 3.1 以降、および MsftEdit.dll バージョン 4.1 以降) に対してのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="89a3f-205">**Note** The RichEdit control is supported only for versions shipped with [!INCLUDE[TLA#tla_winvista](../../../includes/tlasharptla-winvista-md.md)] (in RichEd20.dll version 3.1 and later, and MsftEdit.dll version 4.1 and later).</span></span>  
  
 <span data-ttu-id="89a3f-206">次のコントロールはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="89a3f-206">The following controls are not supported.</span></span>  
  
|<span data-ttu-id="89a3f-207">クラス名</span><span class="sxs-lookup"><span data-stu-id="89a3f-207">Class name</span></span>|<span data-ttu-id="89a3f-208">コントロール型</span><span class="sxs-lookup"><span data-stu-id="89a3f-208">Control type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="89a3f-209">SysAnimate32</span><span class="sxs-lookup"><span data-stu-id="89a3f-209">SysAnimate32</span></span>|<span data-ttu-id="89a3f-210">イメージ</span><span class="sxs-lookup"><span data-stu-id="89a3f-210">Image</span></span>|  
|<span data-ttu-id="89a3f-211">SysPager</span><span class="sxs-lookup"><span data-stu-id="89a3f-211">SysPager</span></span>|<span data-ttu-id="89a3f-212">Spinner</span><span class="sxs-lookup"><span data-stu-id="89a3f-212">Spinner</span></span>|  
|<span data-ttu-id="89a3f-213">SysDateTimePick32</span><span class="sxs-lookup"><span data-stu-id="89a3f-213">SysDateTimePick32</span></span>|<span data-ttu-id="89a3f-214">カスタム</span><span class="sxs-lookup"><span data-stu-id="89a3f-214">Custom</span></span>|  
|<span data-ttu-id="89a3f-215">SysMonthCal32</span><span class="sxs-lookup"><span data-stu-id="89a3f-215">SysMonthCal32</span></span>|<span data-ttu-id="89a3f-216">予定表</span><span class="sxs-lookup"><span data-stu-id="89a3f-216">Calendar</span></span>|  
|<span data-ttu-id="89a3f-217">MS_WINNOTE</span><span class="sxs-lookup"><span data-stu-id="89a3f-217">MS_WINNOTE</span></span>|<span data-ttu-id="89a3f-218">ヒント</span><span class="sxs-lookup"><span data-stu-id="89a3f-218">Tooltip</span></span>|  
|<span data-ttu-id="89a3f-219">VBBubble</span><span class="sxs-lookup"><span data-stu-id="89a3f-219">VBBubble</span></span>|<span data-ttu-id="89a3f-220">ヒント</span><span class="sxs-lookup"><span data-stu-id="89a3f-220">Tooltip</span></span>|  
|<span data-ttu-id="89a3f-221">ScrollBar (スタンドアロン コントロールとして使用される場合)</span><span class="sxs-lookup"><span data-stu-id="89a3f-221">ScrollBar (when used as a standalone control)</span></span>|<span data-ttu-id="89a3f-222">スライダー</span><span class="sxs-lookup"><span data-stu-id="89a3f-222">Slider</span></span>|  
|<span data-ttu-id="89a3f-223">SuperGrid</span><span class="sxs-lookup"><span data-stu-id="89a3f-223">SuperGrid</span></span>|<span data-ttu-id="89a3f-224">カスタム</span><span class="sxs-lookup"><span data-stu-id="89a3f-224">Custom</span></span>|  
  
<a name="Windows_Forms_Controls"></a>   
## <a name="windows-forms-controls"></a><span data-ttu-id="89a3f-225">Windows フォーム コントロール</span><span class="sxs-lookup"><span data-stu-id="89a3f-225">Windows Forms Controls</span></span>  
 <span data-ttu-id="89a3f-226">Windows フォーム コントロールに公開[!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)]UIAutomationClientsideProviders.dll のクライアント側プロバイダーを経由します。</span><span class="sxs-lookup"><span data-stu-id="89a3f-226">Windows Forms controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="89a3f-227">このアセンブリは、UI オートメーション クライアント アプリケーションで使用するために、自動的に登録されます。</span><span class="sxs-lookup"><span data-stu-id="89a3f-227">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="89a3f-228">通常、Windows フォーム コントロール用のマネージ ラッパー[!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)]で一般的なコントロールがサポートされる[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="89a3f-228">Typically, Windows Forms controls that are managed wrappers for [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] common controls are supported by [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="89a3f-229">次のコントロールがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="89a3f-229">The following controls are supported.</span></span>  
  
|<span data-ttu-id="89a3f-230">クラス名</span><span class="sxs-lookup"><span data-stu-id="89a3f-230">Class Name</span></span>|  
|----------------|  
|<span data-ttu-id="89a3f-231">ボタン</span><span class="sxs-lookup"><span data-stu-id="89a3f-231">Button</span></span>|  
|<span data-ttu-id="89a3f-232">CheckBox</span><span class="sxs-lookup"><span data-stu-id="89a3f-232">CheckBox</span></span>|  
|<span data-ttu-id="89a3f-233">CheckedListBox</span><span class="sxs-lookup"><span data-stu-id="89a3f-233">CheckedListBox</span></span>|  
|<span data-ttu-id="89a3f-234">ColorDialog</span><span class="sxs-lookup"><span data-stu-id="89a3f-234">ColorDialog</span></span>|  
|<span data-ttu-id="89a3f-235">ComboBox</span><span class="sxs-lookup"><span data-stu-id="89a3f-235">ComboBox</span></span>|  
|<span data-ttu-id="89a3f-236">FolderBrowser</span><span class="sxs-lookup"><span data-stu-id="89a3f-236">FolderBrowser</span></span>|  
|<span data-ttu-id="89a3f-237">FontDialog</span><span class="sxs-lookup"><span data-stu-id="89a3f-237">FontDialog</span></span>|  
|<span data-ttu-id="89a3f-238">GroupBox</span><span class="sxs-lookup"><span data-stu-id="89a3f-238">GroupBox</span></span>|  
|<span data-ttu-id="89a3f-239">HscrollBar</span><span class="sxs-lookup"><span data-stu-id="89a3f-239">HscrollBar</span></span>|  
|<span data-ttu-id="89a3f-240">ImageList</span><span class="sxs-lookup"><span data-stu-id="89a3f-240">ImageList</span></span>|  
|<span data-ttu-id="89a3f-241">group1</span><span class="sxs-lookup"><span data-stu-id="89a3f-241">Label</span></span>|  
|<span data-ttu-id="89a3f-242">ListBox</span><span class="sxs-lookup"><span data-stu-id="89a3f-242">ListBox</span></span>|  
|<span data-ttu-id="89a3f-243">ListView</span><span class="sxs-lookup"><span data-stu-id="89a3f-243">ListView</span></span>|  
|<span data-ttu-id="89a3f-244">MainMenu/ContextMenu</span><span class="sxs-lookup"><span data-stu-id="89a3f-244">MainMenu/ContextMenu</span></span>|  
|<span data-ttu-id="89a3f-245">MonthCalendar</span><span class="sxs-lookup"><span data-stu-id="89a3f-245">MonthCalendar</span></span>|  
|<span data-ttu-id="89a3f-246">NotifyIcon</span><span class="sxs-lookup"><span data-stu-id="89a3f-246">NotifyIcon</span></span>|  
|<span data-ttu-id="89a3f-247">OpenFileDialog</span><span class="sxs-lookup"><span data-stu-id="89a3f-247">OpenFileDialog</span></span>|  
|<span data-ttu-id="89a3f-248">PageSetupDialog</span><span class="sxs-lookup"><span data-stu-id="89a3f-248">PageSetupDialog</span></span>|  
|<span data-ttu-id="89a3f-249">PrintDialog</span><span class="sxs-lookup"><span data-stu-id="89a3f-249">PrintDialog</span></span>|  
|<span data-ttu-id="89a3f-250">ProgressBar</span><span class="sxs-lookup"><span data-stu-id="89a3f-250">ProgressBar</span></span>|  
|<span data-ttu-id="89a3f-251">RadioButton</span><span class="sxs-lookup"><span data-stu-id="89a3f-251">RadioButton</span></span>|  
|<span data-ttu-id="89a3f-252">RichTextBox</span><span class="sxs-lookup"><span data-stu-id="89a3f-252">RichTextBox</span></span>|  
|<span data-ttu-id="89a3f-253">SaveFileDialog</span><span class="sxs-lookup"><span data-stu-id="89a3f-253">SaveFileDialog</span></span>|  
|<span data-ttu-id="89a3f-254">ScrollableControl</span><span class="sxs-lookup"><span data-stu-id="89a3f-254">ScrollableControl</span></span>|  
|<span data-ttu-id="89a3f-255">SoundPlayer</span><span class="sxs-lookup"><span data-stu-id="89a3f-255">SoundPlayer</span></span>|  
|<span data-ttu-id="89a3f-256">StatusBar</span><span class="sxs-lookup"><span data-stu-id="89a3f-256">StatusBar</span></span>|  
|<span data-ttu-id="89a3f-257">TabControl/TabPage</span><span class="sxs-lookup"><span data-stu-id="89a3f-257">TabControl/TabPage</span></span>|  
|<span data-ttu-id="89a3f-258">TextBox</span><span class="sxs-lookup"><span data-stu-id="89a3f-258">TextBox</span></span>|  
|<span data-ttu-id="89a3f-259">タイマー</span><span class="sxs-lookup"><span data-stu-id="89a3f-259">Timer</span></span>|  
|<span data-ttu-id="89a3f-260">ToolBar</span><span class="sxs-lookup"><span data-stu-id="89a3f-260">Toolbar</span></span>|  
|<span data-ttu-id="89a3f-261">ヒント</span><span class="sxs-lookup"><span data-stu-id="89a3f-261">ToolTip</span></span>|  
|<span data-ttu-id="89a3f-262">TrackBar</span><span class="sxs-lookup"><span data-stu-id="89a3f-262">TrackBar</span></span>|  
|<span data-ttu-id="89a3f-263">TreeView</span><span class="sxs-lookup"><span data-stu-id="89a3f-263">TreeView</span></span>|  
|<span data-ttu-id="89a3f-264">VscrollBar</span><span class="sxs-lookup"><span data-stu-id="89a3f-264">VscrollBar</span></span>|  
|<span data-ttu-id="89a3f-265">Web ブラウザー</span><span class="sxs-lookup"><span data-stu-id="89a3f-265">WebBrowser</span></span>|  
  
 <span data-ttu-id="89a3f-266">次に示すコントロールは、 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] のサポートによってのみ、 [!INCLUDE[TLA#tla_aa](../../../includes/tlasharptla-aa-md.md)]に公開されています。</span><span class="sxs-lookup"><span data-stu-id="89a3f-266">The following controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] only through their support for [!INCLUDE[TLA#tla_aa](../../../includes/tlasharptla-aa-md.md)].</span></span> <span data-ttu-id="89a3f-267">一部の機能が使用できないことがあります。</span><span class="sxs-lookup"><span data-stu-id="89a3f-267">Some functionality may not be available.</span></span>  
  
|<span data-ttu-id="89a3f-268">コントロール名</span><span class="sxs-lookup"><span data-stu-id="89a3f-268">Control Name</span></span>|  
|------------------|  
|<span data-ttu-id="89a3f-269">BindingSource</span><span class="sxs-lookup"><span data-stu-id="89a3f-269">BindingSource</span></span>|  
|<span data-ttu-id="89a3f-270">DataGrid</span><span class="sxs-lookup"><span data-stu-id="89a3f-270">DataGrid</span></span>|  
|<span data-ttu-id="89a3f-271">DataGridView</span><span class="sxs-lookup"><span data-stu-id="89a3f-271">DataGridView</span></span>|  
|<span data-ttu-id="89a3f-272">DataNavigator</span><span class="sxs-lookup"><span data-stu-id="89a3f-272">DataNavigator</span></span>|  
|<span data-ttu-id="89a3f-273">DomainUpDown</span><span class="sxs-lookup"><span data-stu-id="89a3f-273">DomainUpDown</span></span>|  
|<span data-ttu-id="89a3f-274">ErrorProvider</span><span class="sxs-lookup"><span data-stu-id="89a3f-274">ErrorProvider</span></span>|  
|<span data-ttu-id="89a3f-275">FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="89a3f-275">FlowLayoutPanel</span></span>|  
|<span data-ttu-id="89a3f-276">フォーム</span><span class="sxs-lookup"><span data-stu-id="89a3f-276">Form</span></span>|  
|<span data-ttu-id="89a3f-277">LinkLabel</span><span class="sxs-lookup"><span data-stu-id="89a3f-277">LinkLabel</span></span>|  
|<span data-ttu-id="89a3f-278">HelpProvider</span><span class="sxs-lookup"><span data-stu-id="89a3f-278">HelpProvider</span></span>|  
|<span data-ttu-id="89a3f-279">MaskedTextBox</span><span class="sxs-lookup"><span data-stu-id="89a3f-279">MaskedTextBox</span></span>|  
|<span data-ttu-id="89a3f-280">MenuStrip/ContextMenuStrip</span><span class="sxs-lookup"><span data-stu-id="89a3f-280">MenuStrip/ContextMenuStrip</span></span>|  
|<span data-ttu-id="89a3f-281">NumericUpDown</span><span class="sxs-lookup"><span data-stu-id="89a3f-281">NumericUpDown</span></span>|  
|<span data-ttu-id="89a3f-282">パネル</span><span class="sxs-lookup"><span data-stu-id="89a3f-282">Panel</span></span>|  
|<span data-ttu-id="89a3f-283">PictureBox</span><span class="sxs-lookup"><span data-stu-id="89a3f-283">PictureBox</span></span>|  
|<span data-ttu-id="89a3f-284">PrintDocument</span><span class="sxs-lookup"><span data-stu-id="89a3f-284">PrintDocument</span></span>|  
|<span data-ttu-id="89a3f-285">PrintPreview-Control</span><span class="sxs-lookup"><span data-stu-id="89a3f-285">PrintPreview-Control</span></span>|  
|<span data-ttu-id="89a3f-286">PrintPreview-Dialog</span><span class="sxs-lookup"><span data-stu-id="89a3f-286">PrintPreview-Dialog</span></span>|  
|<span data-ttu-id="89a3f-287">PropertyGrid</span><span class="sxs-lookup"><span data-stu-id="89a3f-287">PropertyGrid</span></span>|  
|<span data-ttu-id="89a3f-288">UserControl</span><span class="sxs-lookup"><span data-stu-id="89a3f-288">UserControl</span></span>|  
|<span data-ttu-id="89a3f-289">ToolStrip</span><span class="sxs-lookup"><span data-stu-id="89a3f-289">ToolStrip</span></span>|  
|<span data-ttu-id="89a3f-290">TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="89a3f-290">TableLayoutPanel</span></span>|  
|<span data-ttu-id="89a3f-291">SplitContainer/SplitterPanel</span><span class="sxs-lookup"><span data-stu-id="89a3f-291">SplitContainer/SplitterPanel</span></span>|  
|<span data-ttu-id="89a3f-292">スプリッター</span><span class="sxs-lookup"><span data-stu-id="89a3f-292">Splitter</span></span>|  
|<span data-ttu-id="89a3f-293">RaftingContainer</span><span class="sxs-lookup"><span data-stu-id="89a3f-293">RaftingContainer</span></span>|  
|<span data-ttu-id="89a3f-294">StatusStrip</span><span class="sxs-lookup"><span data-stu-id="89a3f-294">StatusStrip</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="89a3f-295">関連項目</span><span class="sxs-lookup"><span data-stu-id="89a3f-295">See also</span></span>
- [<span data-ttu-id="89a3f-296">UI オートメーション コントロール型</span><span class="sxs-lookup"><span data-stu-id="89a3f-296">UI Automation Control Types</span></span>](../../../docs/framework/ui-automation/ui-automation-control-types.md)
