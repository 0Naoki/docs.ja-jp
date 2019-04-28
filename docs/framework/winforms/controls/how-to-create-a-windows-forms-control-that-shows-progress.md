---
title: '方法: 進行状況を示す Windows フォーム コントロールを作成する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], progress tracking
- controls [Windows Forms], creating
- progress [Windows Forms], reporting [Windows Forms]
- FlashTrackBar custom control
ms.assetid: 24c5a2e3-058c-4b8d-a217-c06e6a130c2f
ms.openlocfilehash: 1f457d6e2b0eb73da7a16dc93ea80a14ddb4b2c2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61746723"
---
# <a name="how-to-create-a-windows-forms-control-that-shows-progress"></a><span data-ttu-id="63847-102">方法: 進行状況を示す Windows フォーム コントロールを作成する</span><span class="sxs-lookup"><span data-stu-id="63847-102">How to: Create a Windows Forms Control That Shows Progress</span></span>
<span data-ttu-id="63847-103">次のコード例は、アプリケーションのレベルまたは進行状況の表示にに使用できる `FlashTrackBar` というカスタム コントロールを示していいます。</span><span class="sxs-lookup"><span data-stu-id="63847-103">The following code example shows a custom control called `FlashTrackBar` that can be used to show the user the level or the progress of an application.</span></span> <span data-ttu-id="63847-104">これは、グラデーションを使用して、進行状況を視覚的に表示します。</span><span class="sxs-lookup"><span data-stu-id="63847-104">It uses a gradient to visually represent progress.</span></span>  
  
 <span data-ttu-id="63847-105">`FlashTrackBar` コントロールには次のような機能が含まれます。</span><span class="sxs-lookup"><span data-stu-id="63847-105">The `FlashTrackBar` control illustrates the following concepts:</span></span>  
  
- <span data-ttu-id="63847-106">カスタム プロパティの定義。</span><span class="sxs-lookup"><span data-stu-id="63847-106">Defining custom properties.</span></span>  
  
- <span data-ttu-id="63847-107">カスタム イベントの定義 </span><span class="sxs-lookup"><span data-stu-id="63847-107">Defining custom events.</span></span> <span data-ttu-id="63847-108">(`FlashTrackBar` が `ValueChanged` イベントを定義します)。</span><span class="sxs-lookup"><span data-stu-id="63847-108">(`FlashTrackBar` defines the `ValueChanged` event.)</span></span>  
  
- <span data-ttu-id="63847-109">オーバーライドする、<xref:System.Windows.Forms.Control.OnPaint%2A>コントロールを描画するロジックを提供するメソッド。</span><span class="sxs-lookup"><span data-stu-id="63847-109">Overriding the <xref:System.Windows.Forms.Control.OnPaint%2A> method to provide logic to draw the control.</span></span>  
  
- <span data-ttu-id="63847-110">使用して、コントロールを描画するために使用できる面積を計算、<xref:System.Windows.Forms.Control.ClientRectangle%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="63847-110">Computing the area available for drawing the control by using its <xref:System.Windows.Forms.Control.ClientRectangle%2A> property.</span></span> <span data-ttu-id="63847-111">`FlashTrackBar` は、`OptimizedInvalidate` メソッドでこの計算を実行します。</span><span class="sxs-lookup"><span data-stu-id="63847-111">`FlashTrackBar` does this in its `OptimizedInvalidate` method.</span></span>  
  
- <span data-ttu-id="63847-112">Windows フォーム デザイナー内でプロパティが変更されたときの、プロパティのシリアル化または永続化の実装。</span><span class="sxs-lookup"><span data-stu-id="63847-112">Implementing serialization or persistence for a property when it is changed in the Windows Forms Designer.</span></span> <span data-ttu-id="63847-113">`FlashTrackBar` は `StartColor` プロパティと `EndColor` プロパティをシリアル化するために、`ShouldSerializeStartColor` メソッドと `ShouldSerializeEndColor` メソッドを定義します。</span><span class="sxs-lookup"><span data-stu-id="63847-113">`FlashTrackBar` defines the `ShouldSerializeStartColor` and `ShouldSerializeEndColor` methods for serializing its `StartColor` and `EndColor` properties.</span></span>  
  
 <span data-ttu-id="63847-114">`FlashTrackBar` によって定義されるカスタム プロパティを次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="63847-114">The following table shows the custom properties defined by `FlashTrackBar`.</span></span>  
  
|<span data-ttu-id="63847-115">プロパティ</span><span class="sxs-lookup"><span data-stu-id="63847-115">Property</span></span>|<span data-ttu-id="63847-116">説明</span><span class="sxs-lookup"><span data-stu-id="63847-116">Description</span></span>|  
|--------------|-----------------|  
|`AllowUserEdit`|<span data-ttu-id="63847-117">フラッシュ トラック バーをクリックまたはドラッグして値を変更できるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="63847-117">Indicates whether the user can change the value of the flash track bar by clicking and dragging it.</span></span>|  
|`EndColor`|<span data-ttu-id="63847-118">トラック バーの終了色を指定します。</span><span class="sxs-lookup"><span data-stu-id="63847-118">Specifies the ending color of the track bar.</span></span>|  
|`DarkenBy`|<span data-ttu-id="63847-119">前景のグラデーションを基準にして、背景のグラデーションをどの程度の濃さにするかを指定します。</span><span class="sxs-lookup"><span data-stu-id="63847-119">Specifies how much to darken the background with respect to the foreground gradient.</span></span>|  
|`Max`|<span data-ttu-id="63847-120">トラック バーの最大値を指定します。</span><span class="sxs-lookup"><span data-stu-id="63847-120">Specifies the maximum value of the track bar.</span></span>|  
|`Min`|<span data-ttu-id="63847-121">トラック バーの最小値を指定します。</span><span class="sxs-lookup"><span data-stu-id="63847-121">Specifies the minimum value of the track bar.</span></span>|  
|`StartColor`|<span data-ttu-id="63847-122">グラデーションの開始色を指定します。</span><span class="sxs-lookup"><span data-stu-id="63847-122">Specifies the starting color of the gradient.</span></span>|  
|`ShowPercentage`|<span data-ttu-id="63847-123">グラデーションの上にパーセントを表示するかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="63847-123">Indicates whether to display a percentage over the gradient.</span></span>|  
|`ShowValue`|<span data-ttu-id="63847-124">グラデーションの上に現在の値を表示するかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="63847-124">Indicates whether to display the current value over the gradient.</span></span>|  
|`ShowGradient`|<span data-ttu-id="63847-125">現在の値を表示した色のグラデーションをトラック バーに表示するかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="63847-125">Indicates whether the track bar should display a color gradient showing the current value.</span></span>|  
|-   `Value`|<span data-ttu-id="63847-126">トラック バーの現在の値を指定します。</span><span class="sxs-lookup"><span data-stu-id="63847-126">Specifies the current value of the track bar.</span></span>|  
  
 <span data-ttu-id="63847-127">次の表は、`FlashTrackBar:` によって定義される追加メンバーである、プロパティ変更イベント、およびイベントを発生させるメソッドを示しています。</span><span class="sxs-lookup"><span data-stu-id="63847-127">The following table shows additional members defined by `FlashTrackBar:` the property-changed event and the method that raises the event.</span></span>  
  
|<span data-ttu-id="63847-128">メンバー</span><span class="sxs-lookup"><span data-stu-id="63847-128">Member</span></span>|<span data-ttu-id="63847-129">説明</span><span class="sxs-lookup"><span data-stu-id="63847-129">Description</span></span>|  
|------------|-----------------|  
|`ValueChanged`|<span data-ttu-id="63847-130">トラック バーの `Value` プロパティが変更されたときに発生するイベント。</span><span class="sxs-lookup"><span data-stu-id="63847-130">The event that is raised when the `Value` property of the track bar changes.</span></span>|  
|`OnValueChanged`|<span data-ttu-id="63847-131">`ValueChanged` イベントを発生させるメソッド。</span><span class="sxs-lookup"><span data-stu-id="63847-131">The method that raises the `ValueChanged` event.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="63847-132">`FlashTrackBar` 使用して、<xref:System.EventArgs>イベント データのクラスと<xref:System.EventHandler>イベント デリゲート。</span><span class="sxs-lookup"><span data-stu-id="63847-132">`FlashTrackBar` uses the <xref:System.EventArgs> class for event data and <xref:System.EventHandler> for the event delegate.</span></span>  
  
 <span data-ttu-id="63847-133">対応するを処理するために*EventName*イベント、`FlashTrackBar`から継承した次のメソッドを上書き<xref:System.Windows.Forms.Control?displayProperty=nameWithType>:</span><span class="sxs-lookup"><span data-stu-id="63847-133">To handle the corresponding *EventName* events, `FlashTrackBar` overrides the following methods that it inherits from <xref:System.Windows.Forms.Control?displayProperty=nameWithType>:</span></span>  
  
- <xref:System.Windows.Forms.Control.OnPaint%2A>  
  
- <xref:System.Windows.Forms.Control.OnMouseDown%2A>  
  
- <xref:System.Windows.Forms.Control.OnMouseMove%2A>  
  
- <xref:System.Windows.Forms.Control.OnMouseUp%2A>  
  
- <xref:System.Windows.Forms.Control.OnResize%2A>  
  
 <span data-ttu-id="63847-134">対応するプロパティ変更イベントを処理する`FlashTrackBar`から継承した次のメソッドを上書き<xref:System.Windows.Forms.Control?displayProperty=nameWithType>:</span><span class="sxs-lookup"><span data-stu-id="63847-134">To handle the corresponding property-changed events, `FlashTrackBar` overrides the following methods that it inherits from <xref:System.Windows.Forms.Control?displayProperty=nameWithType>:</span></span>  
  
- <xref:System.Windows.Forms.Control.OnBackColorChanged%2A>  
  
- <xref:System.Windows.Forms.Control.OnBackgroundImageChanged%2A>  
  
- <xref:System.Windows.Forms.Control.OnTextChanged%2A>  
  
## <a name="example"></a><span data-ttu-id="63847-135">例</span><span class="sxs-lookup"><span data-stu-id="63847-135">Example</span></span>  
 <span data-ttu-id="63847-136">`FlashTrackBar` コントロールは、次のコード一覧に示すとおり、`FlashTrackBarValueEditor` と `FlashTrackBarDarkenByEditor` という 2 つの UI 型エディターを定義します。</span><span class="sxs-lookup"><span data-stu-id="63847-136">The `FlashTrackBar` control defines two UI type editors, `FlashTrackBarValueEditor` and `FlashTrackBarDarkenByEditor`, which are shown in the following code listings.</span></span> <span data-ttu-id="63847-137">`HostApp` クラスは、Windows フォームで `FlashTrackBar` コントロールを使用します。</span><span class="sxs-lookup"><span data-stu-id="63847-137">The `HostApp` class uses the `FlashTrackBar` control on a Windows Form.</span></span>  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#1)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#1)]  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBarDarkenByEditor.cs#10)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBarDarkenByEditor.vb#10)]  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBarValueEditor.cs#20)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBarValueEditor.vb#20)]  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/HostApp.cs#30)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/HostApp.vb#30)]  
  
## <a name="see-also"></a><span data-ttu-id="63847-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="63847-138">See also</span></span>

- <span data-ttu-id="63847-139">[デザイン時サポートの拡張](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/37899azc(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="63847-139">[Extending Design-Time Support](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/37899azc(v=vs.120))</span></span>
- [<span data-ttu-id="63847-140">Windows フォーム コントロール開発の基本概念</span><span class="sxs-lookup"><span data-stu-id="63847-140">Windows Forms Control Development Basics</span></span>](windows-forms-control-development-basics.md)
