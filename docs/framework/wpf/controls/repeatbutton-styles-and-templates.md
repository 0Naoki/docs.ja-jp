---
title: RepeatButton のスタイルとテンプレート
ms.date: 03/30/2017
helpviewer_keywords:
- RepeatButton [WPF], styles and templates
- styles [WPF], RepeatButton
- templates [WPF], RepeatButton
- parts [WPF], RepeatButton
- ControlTemplate [WPF], RepeatButton
- states [WPF], RepeatButton
ms.assetid: fd340743-f44f-4990-9077-085301469670
ms.openlocfilehash: 86f212326bc707e4b07b8cab8d9a95d4f6ef8920
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62053316"
---
# <a name="repeatbutton-styles-and-templates"></a><span data-ttu-id="c34a7-102">RepeatButton のスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="c34a7-102">RepeatButton Styles and Templates</span></span>

<span data-ttu-id="c34a7-103">このトピックでは、スタイルとテンプレートについて説明します、<xref:System.Windows.Controls.Primitives.RepeatButton>コントロール。</span><span class="sxs-lookup"><span data-stu-id="c34a7-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Primitives.RepeatButton> control.</span></span> <span data-ttu-id="c34a7-104">既定値を変更する<xref:System.Windows.Controls.ControlTemplate>固有の外観を制御します。</span><span class="sxs-lookup"><span data-stu-id="c34a7-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="c34a7-105">詳細については、「[ControlTemplate の作成による既存のコントロールの外観のカスタマイズ](customizing-the-appearance-of-an-existing-control.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c34a7-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>

## <a name="repeatbutton-parts"></a><span data-ttu-id="c34a7-106">RepeatButton のパーツ</span><span class="sxs-lookup"><span data-stu-id="c34a7-106">RepeatButton Parts</span></span>

<span data-ttu-id="c34a7-107"><xref:System.Windows.Controls.Primitives.RepeatButton>コントロールには、名前付きパーツはありません。</span><span class="sxs-lookup"><span data-stu-id="c34a7-107">The <xref:System.Windows.Controls.Primitives.RepeatButton> control does not have any named parts.</span></span>

## <a name="repeatbutton-states"></a><span data-ttu-id="c34a7-108">RepeatButton の状態</span><span class="sxs-lookup"><span data-stu-id="c34a7-108">RepeatButton States</span></span>

<span data-ttu-id="c34a7-109">次の表のビジュアルの状態、<xref:System.Windows.Controls.Primitives.RepeatButton>コントロール。</span><span class="sxs-lookup"><span data-stu-id="c34a7-109">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.RepeatButton> control.</span></span>

|<span data-ttu-id="c34a7-110">VisualState 名</span><span class="sxs-lookup"><span data-stu-id="c34a7-110">VisualState Name</span></span>|<span data-ttu-id="c34a7-111">VisualStateGroup 名</span><span class="sxs-lookup"><span data-stu-id="c34a7-111">VisualStateGroup Name</span></span>|<span data-ttu-id="c34a7-112">説明</span><span class="sxs-lookup"><span data-stu-id="c34a7-112">Description</span></span>|
|-|-|-|
|<span data-ttu-id="c34a7-113">標準</span><span class="sxs-lookup"><span data-stu-id="c34a7-113">Normal</span></span>|<span data-ttu-id="c34a7-114">CommonStates</span><span class="sxs-lookup"><span data-stu-id="c34a7-114">CommonStates</span></span>|<span data-ttu-id="c34a7-115">既定の状態です。</span><span class="sxs-lookup"><span data-stu-id="c34a7-115">The default state.</span></span>|
|<span data-ttu-id="c34a7-116">MouseOver</span><span class="sxs-lookup"><span data-stu-id="c34a7-116">MouseOver</span></span>|<span data-ttu-id="c34a7-117">CommonStates</span><span class="sxs-lookup"><span data-stu-id="c34a7-117">CommonStates</span></span>|<span data-ttu-id="c34a7-118">マウス ポインターがコントロール上に配置されています。</span><span class="sxs-lookup"><span data-stu-id="c34a7-118">The mouse pointer is positioned over the control.</span></span>|
|<span data-ttu-id="c34a7-119">押されている</span><span class="sxs-lookup"><span data-stu-id="c34a7-119">Pressed</span></span>|<span data-ttu-id="c34a7-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="c34a7-120">CommonStates</span></span>|<span data-ttu-id="c34a7-121">コントロールが押されています。</span><span class="sxs-lookup"><span data-stu-id="c34a7-121">The control is pressed.</span></span>|
|<span data-ttu-id="c34a7-122">無効</span><span class="sxs-lookup"><span data-stu-id="c34a7-122">Disabled</span></span>|<span data-ttu-id="c34a7-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="c34a7-123">CommonStates</span></span>|<span data-ttu-id="c34a7-124">コントロールが無効になっています。</span><span class="sxs-lookup"><span data-stu-id="c34a7-124">The control is disabled.</span></span>|
|<span data-ttu-id="c34a7-125">フォーカスされている</span><span class="sxs-lookup"><span data-stu-id="c34a7-125">Focused</span></span>|<span data-ttu-id="c34a7-126">FocusStates</span><span class="sxs-lookup"><span data-stu-id="c34a7-126">FocusStates</span></span>|<span data-ttu-id="c34a7-127">コントロールにフォーカスがあります。</span><span class="sxs-lookup"><span data-stu-id="c34a7-127">The control has focus.</span></span>|
|<span data-ttu-id="c34a7-128">フォーカスされていない</span><span class="sxs-lookup"><span data-stu-id="c34a7-128">Unfocused</span></span>|<span data-ttu-id="c34a7-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="c34a7-129">FocusStates</span></span>|<span data-ttu-id="c34a7-130">コントロールにフォーカスがありません。</span><span class="sxs-lookup"><span data-stu-id="c34a7-130">The control does not have focus.</span></span>|
|<span data-ttu-id="c34a7-131">有効</span><span class="sxs-lookup"><span data-stu-id="c34a7-131">Valid</span></span>|<span data-ttu-id="c34a7-132">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="c34a7-132">ValidationStates</span></span>|<span data-ttu-id="c34a7-133">コントロールを使用して、<xref:System.Windows.Controls.Validation>クラスおよび<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>添付プロパティは`false`します。</span><span class="sxs-lookup"><span data-stu-id="c34a7-133">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|
|<span data-ttu-id="c34a7-134">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="c34a7-134">InvalidFocused</span></span>|<span data-ttu-id="c34a7-135">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="c34a7-135">ValidationStates</span></span>|<span data-ttu-id="c34a7-136"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>添付プロパティは`true`がコントロールにフォーカスします。</span><span class="sxs-lookup"><span data-stu-id="c34a7-136">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|
|<span data-ttu-id="c34a7-137">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="c34a7-137">InvalidUnfocused</span></span>|<span data-ttu-id="c34a7-138">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="c34a7-138">ValidationStates</span></span>|<span data-ttu-id="c34a7-139"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>添付プロパティは`true`がコントロールにフォーカスがないです。</span><span class="sxs-lookup"><span data-stu-id="c34a7-139">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|

## <a name="repeatbutton-controltemplate-example"></a><span data-ttu-id="c34a7-140">RepeatButton ControlTemplate の例</span><span class="sxs-lookup"><span data-stu-id="c34a7-140">RepeatButton ControlTemplate Example</span></span>

<span data-ttu-id="c34a7-141">次の例は、定義する方法を示します、<xref:System.Windows.Controls.ControlTemplate>の<xref:System.Windows.Controls.Primitives.RepeatButton>コントロール。</span><span class="sxs-lookup"><span data-stu-id="c34a7-141">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Primitives.RepeatButton> control.</span></span>

[!code-xaml[ControlTemplateExamples#RepeatButton](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/scrollbar.xaml#repeatbutton)]

<span data-ttu-id="c34a7-142">前の例では、次のリソースの 1 つ以上を使用します。</span><span class="sxs-lookup"><span data-stu-id="c34a7-142">The preceding example uses one or more of the following resources.</span></span>

[!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]

<span data-ttu-id="c34a7-143">完全なサンプルについては、[Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c34a7-143">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>

## <a name="see-also"></a><span data-ttu-id="c34a7-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="c34a7-144">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="c34a7-145">コントロールのスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="c34a7-145">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="c34a7-146">コントロールのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="c34a7-146">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="c34a7-147">スタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="c34a7-147">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="c34a7-148">ControlTemplate の作成による既存のコントロールの外観のカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="c34a7-148">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
