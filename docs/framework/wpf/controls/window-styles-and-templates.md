---
title: ウィンドウのスタイルとテンプレート
ms.date: 03/30/2017
helpviewer_keywords:
- parts [WPF], Window
- templates [WPF], Window
- styles [WPF], Window
- ControlTemplate [WPF], Window
- Window [WPF], styles and templates
- states [WPF], Window
ms.assetid: 2dfdf025-347b-4342-bf28-95206c273f35
ms.openlocfilehash: 416202f22fcdad1d98f28889af6bdcdf5671587c
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57376300"
---
# <a name="window-styles-and-templates"></a><span data-ttu-id="6d406-102">ウィンドウのスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="6d406-102">Window Styles and Templates</span></span>
<span data-ttu-id="6d406-103">このトピックでは、スタイルとテンプレートについて説明します、<xref:System.Windows.Window>コントロール。</span><span class="sxs-lookup"><span data-stu-id="6d406-103">This topic describes the styles and templates for the <xref:System.Windows.Window> control.</span></span> <span data-ttu-id="6d406-104">既定値を変更する<xref:System.Windows.Controls.ControlTemplate>固有の外観を制御します。</span><span class="sxs-lookup"><span data-stu-id="6d406-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="6d406-105">詳細については、「[ControlTemplate の作成による既存のコントロールの外観のカスタマイズ](customizing-the-appearance-of-an-existing-control.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6d406-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="window-parts"></a><span data-ttu-id="6d406-106">ウィンドウの一部</span><span class="sxs-lookup"><span data-stu-id="6d406-106">Window Parts</span></span>  
 <span data-ttu-id="6d406-107"><xref:System.Windows.Window>コントロールには、名前付きパーツはありません。</span><span class="sxs-lookup"><span data-stu-id="6d406-107">The <xref:System.Windows.Window> control does not have any named parts.</span></span>  
  
## <a name="window-states"></a><span data-ttu-id="6d406-108">ウィンドウの状態</span><span class="sxs-lookup"><span data-stu-id="6d406-108">Window States</span></span>  
 <span data-ttu-id="6d406-109">次の表のビジュアルの状態、<xref:System.Windows.Window>コントロール。</span><span class="sxs-lookup"><span data-stu-id="6d406-109">The following table lists the visual states for the <xref:System.Windows.Window> control.</span></span>  
  
|<span data-ttu-id="6d406-110">VisualState 名</span><span class="sxs-lookup"><span data-stu-id="6d406-110">VisualState Name</span></span>|<span data-ttu-id="6d406-111">VisualStateGroup 名</span><span class="sxs-lookup"><span data-stu-id="6d406-111">VisualStateGroup Name</span></span>|<span data-ttu-id="6d406-112">説明</span><span class="sxs-lookup"><span data-stu-id="6d406-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="6d406-113">有効</span><span class="sxs-lookup"><span data-stu-id="6d406-113">Valid</span></span>|<span data-ttu-id="6d406-114">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="6d406-114">ValidationStates</span></span>|<span data-ttu-id="6d406-115">コントロールを使用して、<xref:System.Windows.Controls.Validation>クラスおよび<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>添付プロパティは`false`します。</span><span class="sxs-lookup"><span data-stu-id="6d406-115">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="6d406-116">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="6d406-116">InvalidFocused</span></span>|<span data-ttu-id="6d406-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="6d406-117">ValidationStates</span></span>|<span data-ttu-id="6d406-118"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>添付プロパティは`true`がコントロールにフォーカスします。</span><span class="sxs-lookup"><span data-stu-id="6d406-118">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="6d406-119">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="6d406-119">InvalidUnfocused</span></span>|<span data-ttu-id="6d406-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="6d406-120">ValidationStates</span></span>|<span data-ttu-id="6d406-121"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>添付プロパティは`true`がコントロールにフォーカスがないです。</span><span class="sxs-lookup"><span data-stu-id="6d406-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="window-controltemplate-example"></a><span data-ttu-id="6d406-122">ウィンドウの ControlTemplate の例</span><span class="sxs-lookup"><span data-stu-id="6d406-122">Window ControlTemplate Example</span></span>  
 <span data-ttu-id="6d406-123">次の例は、定義する方法を示します、<xref:System.Windows.Controls.ControlTemplate>の<xref:System.Windows.Window>コントロール。</span><span class="sxs-lookup"><span data-stu-id="6d406-123">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Window> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Window](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/window.xaml#window)]  
  
 <span data-ttu-id="6d406-124"><xref:System.Windows.Controls.ControlTemplate>次のリソースの 1 つ以上を使用します。</span><span class="sxs-lookup"><span data-stu-id="6d406-124">The <xref:System.Windows.Controls.ControlTemplate> uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ResizeGrip](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/resizegrip.xaml#resizegrip)]  
[!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="6d406-125">完全なサンプルについては、[Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6d406-125">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d406-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="6d406-126">See also</span></span>
- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="6d406-127">コントロールのスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="6d406-127">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="6d406-128">コントロールのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="6d406-128">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="6d406-129">スタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="6d406-129">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="6d406-130">ControlTemplate の作成による既存のコントロールの外観のカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="6d406-130">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
