---
title: インク スレッド モデル
ms.date: 03/30/2017
helpviewer_keywords:
- application user interface thread [WPF]
- stylus plug-in
- ink threading model [WPF]
- ink [WPF], rendering
- pen thread [WPF]
- threading model [WPF]
- rendering ink [WPF]
- dynamic rendering thread [WPF]
- ink collection plug-in
- plug-ins [WPF], for ink
ms.assetid: c85fcad1-cb50-4431-847c-ac4145a35c89
ms.openlocfilehash: 80e7ef202c46a23069766512cf4e67bb21a49564
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2019
ms.locfileid: "59335322"
---
# <a name="the-ink-threading-model"></a><span data-ttu-id="c2163-102">インク スレッド モデル</span><span class="sxs-lookup"><span data-stu-id="c2163-102">The Ink Threading Model</span></span>
<span data-ttu-id="c2163-103">よく似た書き込みと紙とペンの正規表現では、Tablet PC 上のインクの利点の 1 つ。</span><span class="sxs-lookup"><span data-stu-id="c2163-103">One of the benefits of ink on a Tablet PC is that it feels a lot like writing with a regular pen and paper.</span></span>  <span data-ttu-id="c2163-104">これを行うには、タブレット ペンは、マウスは、ユーザーの書き込みとして、インクをレンダリングするよりもはるかに高いレートで入力データを収集します。</span><span class="sxs-lookup"><span data-stu-id="c2163-104">To accomplish this, the tablet pen collects input data at a much higher rate than a mouse does and renders the ink as the user writes.</span></span>  <span data-ttu-id="c2163-105">ブロックになることができますがあるために、アプリケーションのユーザー インターフェイス (UI) スレッドはペン データとレンダリングのインクを収集するために十分ではありません。</span><span class="sxs-lookup"><span data-stu-id="c2163-105">The application's user interface (UI) thread is not sufficient for collecting pen data and rendering ink, because it can become blocked.</span></span>  <span data-ttu-id="c2163-106">これを解決するために、[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]アプリケーションが、ユーザーがインクを書き込むときに、追加の 2 つのスレッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="c2163-106">To solve this, a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application uses two additional threads when a user writes ink.</span></span>  
  
 <span data-ttu-id="c2163-107">次の一覧には、収集およびデジタル インクの描画に参加しているスレッドがについて説明します。</span><span class="sxs-lookup"><span data-stu-id="c2163-107">The following list describes the threads that take part in collecting and rendering digital ink:</span></span>  
  
-   <span data-ttu-id="c2163-108">ペン スレッドのスレッド、スタイラスからの入力を受け取る。</span><span class="sxs-lookup"><span data-stu-id="c2163-108">Pen thread - the thread that takes input from the stylus.</span></span>  <span data-ttu-id="c2163-109">(実際には、スレッド プールでは、これは、このトピックでは、ペン スレッドとしてそれを参照)。</span><span class="sxs-lookup"><span data-stu-id="c2163-109">(In reality, this is a thread pool, but this topic refers to it as a pen thread.)</span></span>  
  
-   <span data-ttu-id="c2163-110">アプリケーション ユーザー インターフェイス スレッドで、アプリケーションのユーザー インターフェイスを制御するスレッド。</span><span class="sxs-lookup"><span data-stu-id="c2163-110">Application user interface thread - the thread that controls the user interface of the application.</span></span>  
  
-   <span data-ttu-id="c2163-111">動的レンダリング スレッドで、ユーザーの中に、インクをレンダリングするスレッドは、ストロークを描画します。</span><span class="sxs-lookup"><span data-stu-id="c2163-111">Dynamic rendering thread - the thread that renders the ink while the user draws a stroke.</span></span> <span data-ttu-id="c2163-112">Presentation Foundation のウィンドウで説明したように、動的レンダリング スレッドは、アプリケーションの他の UI 要素を描画するスレッドを異なる[スレッド モデル](threading-model.md)します。</span><span class="sxs-lookup"><span data-stu-id="c2163-112">The dynamic rendering thread is different than the thread that renders other UI elements for the application, as mentioned in Window Presentation Foundation [Threading Model](threading-model.md).</span></span>  
  
 <span data-ttu-id="c2163-113">手描き入力のモデルは、同じアプリケーションを使用しているかどうか、<xref:System.Windows.Controls.InkCanvas>またはカスタム コントロールでのような[インク入力コントロールの作成](creating-an-ink-input-control.md)です。</span><span class="sxs-lookup"><span data-stu-id="c2163-113">The inking model is the same whether the application uses the <xref:System.Windows.Controls.InkCanvas> or a custom control similar to the one in [Creating an Ink Input Control](creating-an-ink-input-control.md).</span></span>  <span data-ttu-id="c2163-114">このトピックの観点でスレッド処理について説明しますが、 <xref:System.Windows.Controls.InkCanvas>、カスタム コントロールを作成するときに、同じ概念が適用されます。</span><span class="sxs-lookup"><span data-stu-id="c2163-114">Although this topic discusses threading in terms of the <xref:System.Windows.Controls.InkCanvas>, the same concepts apply when you create a custom control.</span></span>  
  
## <a name="threading-overview"></a><span data-ttu-id="c2163-115">スレッド処理の概要</span><span class="sxs-lookup"><span data-stu-id="c2163-115">Threading Overview</span></span>  
 <span data-ttu-id="c2163-116">次の図は、ユーザーがストロークを描画するときに、スレッド処理モデルを示します。</span><span class="sxs-lookup"><span data-stu-id="c2163-116">The following diagram illustrates the threading model when a user draws a stroke:</span></span>  
  
 <span data-ttu-id="c2163-117">![ストローク描画中のスレッド処理モデル。](./media/inkthreading-drawingink.png "InkThreading_DrawingInk")</span><span class="sxs-lookup"><span data-stu-id="c2163-117">![Threading model while drawing a stroke.](./media/inkthreading-drawingink.png "InkThreading_DrawingInk")</span></span>  
  
1. <span data-ttu-id="c2163-118">ユーザーがストロークを描画中に発生するアクション</span><span class="sxs-lookup"><span data-stu-id="c2163-118">Actions occurring while the user draws the stroke</span></span>  
  
    1.  <span data-ttu-id="c2163-119">ユーザーがストロークを描画、ときに、ペン スレッド上でスタイラス ポイントが提供されます。</span><span class="sxs-lookup"><span data-stu-id="c2163-119">When the user draws a stroke, the stylus points come in on the pen thread.</span></span>  <span data-ttu-id="c2163-120">スタイラス プラグインを含む、<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>ペン スレッド上でスタイラス ポイントをそのまま使用する前にそれらを変更することや、<xref:System.Windows.Controls.InkCanvas>がそれらを受け取る。</span><span class="sxs-lookup"><span data-stu-id="c2163-120">Stylus plug-ins, including the <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>, accept the stylus points on the pen thread and have the chance to modify them before the <xref:System.Windows.Controls.InkCanvas> receives them.</span></span>  
  
    2.  <span data-ttu-id="c2163-121"><xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>動的レンダリング スレッド上でスタイラス ポイントを表示します。</span><span class="sxs-lookup"><span data-stu-id="c2163-121">The <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> renders the stylus points on the dynamic rendering thread.</span></span> <span data-ttu-id="c2163-122">これは、前の手順と同時に発生します。</span><span class="sxs-lookup"><span data-stu-id="c2163-122">This happens at the same time as the previous step.</span></span>  
  
    3.  <span data-ttu-id="c2163-123"><xref:System.Windows.Controls.InkCanvas> UI スレッド上でスタイラス ポイントを受信します。</span><span class="sxs-lookup"><span data-stu-id="c2163-123">The <xref:System.Windows.Controls.InkCanvas> receives the stylus points on the UI thread.</span></span>  
  
2. <span data-ttu-id="c2163-124">ユーザーがストロークを終了した後に発生するアクション</span><span class="sxs-lookup"><span data-stu-id="c2163-124">Actions occurring after the user ends the stroke</span></span>  
  
    1.  <span data-ttu-id="c2163-125">ユーザーは、ストロークの描画が完了すると、<xref:System.Windows.Controls.InkCanvas>作成、<xref:System.Windows.Ink.Stroke>オブジェクトし、それに追加、 <xref:System.Windows.Controls.InkPresenter>、静的に表示されます。</span><span class="sxs-lookup"><span data-stu-id="c2163-125">When the user finishes drawing the stroke, the <xref:System.Windows.Controls.InkCanvas> creates a <xref:System.Windows.Ink.Stroke> object and adds it to the <xref:System.Windows.Controls.InkPresenter>, which statically renders it.</span></span>  
  
    2.  <span data-ttu-id="c2163-126">UI スレッドのアラート、<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>します線が表示される静的にするため、<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>ストロークのビジュアル表現を削除します。</span><span class="sxs-lookup"><span data-stu-id="c2163-126">The UI thread alerts the <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> that the stroke is statically rendered, so the <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> removes its visual representation of the stroke.</span></span>  
  
## <a name="ink-collection-and-stylus-plug-ins"></a><span data-ttu-id="c2163-127">インクの収集とスタイラス プラグイン</span><span class="sxs-lookup"><span data-stu-id="c2163-127">Ink collection and Stylus Plug-ins</span></span>  
 <span data-ttu-id="c2163-128">各<xref:System.Windows.UIElement>が、<xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>します。</span><span class="sxs-lookup"><span data-stu-id="c2163-128">Each <xref:System.Windows.UIElement> has a <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>.</span></span>  <span data-ttu-id="c2163-129"><xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>内のオブジェクト、<xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>受信し、ペン スレッド上でスタイラス ポイントを変更することができます。</span><span class="sxs-lookup"><span data-stu-id="c2163-129">The <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> objects in the <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection> receive and can modify the stylus points on the pen thread.</span></span> <span data-ttu-id="c2163-130"><xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>オブジェクト内の順序に従ってスタイラス ポイントの受信、<xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>します。</span><span class="sxs-lookup"><span data-stu-id="c2163-130">The <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> objects receive the stylus points according to their order in the <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>.</span></span>  
  
 <span data-ttu-id="c2163-131">次の図に、仮定の状況で、<xref:System.Windows.UIElement.StylusPlugIns%2A>のコレクションを<xref:System.Windows.UIElement>が含まれています`stylusPlugin1`、 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>、および`stylusPlugin2`点で、順序。</span><span class="sxs-lookup"><span data-stu-id="c2163-131">The following diagram illustrates the hypothetical situation where the <xref:System.Windows.UIElement.StylusPlugIns%2A> collection of a <xref:System.Windows.UIElement> contains `stylusPlugin1`, a <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>, and `stylusPlugin2`, in that order.</span></span>  
  
 <span data-ttu-id="c2163-132">![スタイラス プラグインの順序では、出力に影響します。](./media/inkthreading-pluginorder.png "InkThreading_PluginOrder")</span><span class="sxs-lookup"><span data-stu-id="c2163-132">![Order of Stylus Plugins affect output.](./media/inkthreading-pluginorder.png "InkThreading_PluginOrder")</span></span>  
  
 <span data-ttu-id="c2163-133">前の図で、次の動作が行わをれます。</span><span class="sxs-lookup"><span data-stu-id="c2163-133">In the previous diagram, the following behavior takes place:</span></span>  
  
1. `StylusPlugin1` <span data-ttu-id="c2163-134">x の値を変更し、y です。</span><span class="sxs-lookup"><span data-stu-id="c2163-134">modifies the values for x and y.</span></span>  
  
2. <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> <span data-ttu-id="c2163-135">変更後のスタイラス ポイントを受信し、動的レンダリング スレッドでレンダリングします。</span><span class="sxs-lookup"><span data-stu-id="c2163-135">receives the modified stylus points and renders them on the dynamic rendering thread.</span></span>  
  
3. `StylusPlugin2` <span data-ttu-id="c2163-136">変更後のスタイラス ポイントを受信し、さらに x の値を変更し、y です。</span><span class="sxs-lookup"><span data-stu-id="c2163-136">receives the modified stylus points and further modifies the values for x and y.</span></span>  
  
4. <span data-ttu-id="c2163-137">アプリケーションでは、スタイラス ポイントを収集し、ユーザーがストロークを終了すると、静的にストロークを描画します。</span><span class="sxs-lookup"><span data-stu-id="c2163-137">The application collects the stylus points, and, when the user finishes the stroke, statically renders the stroke.</span></span>  
  
 <span data-ttu-id="c2163-138">ものとします`stylusPlugin1`四角形にスタイラス ポイントを制限し、`stylusPlugin2`右側にスタイラス ポイントを変換します。</span><span class="sxs-lookup"><span data-stu-id="c2163-138">Suppose that `stylusPlugin1` restricts the stylus points to a rectangle and `stylusPlugin2` translates the stylus points to the right.</span></span>  <span data-ttu-id="c2163-139">前のシナリオで、<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>受信制限付きのスタイラス ポイントが、翻訳されたスタイラス ポイントではありません。</span><span class="sxs-lookup"><span data-stu-id="c2163-139">In the previous scenario, the <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> receives the restricted stylus points, but not the translated stylus points.</span></span>  <span data-ttu-id="c2163-140">ユーザーがストロークを描画ストロークは、四角形の境界内レンダリングされますが、ユーザーが、ペンを持ち上げるまでに変換する線が表示されません。</span><span class="sxs-lookup"><span data-stu-id="c2163-140">When the user draws the stroke, the stroke is rendered within the bounds of the rectangle, but the stroke doesn't appear to be translated until the user lifts the pen.</span></span>  
  
### <a name="performing-operations-with-a-stylus-plug-in-on-the-ui-thread"></a><span data-ttu-id="c2163-141">操作プラグイン UI スレッド上でスタイラスを実行します。</span><span class="sxs-lookup"><span data-stu-id="c2163-141">Performing operations with a Stylus Plug-in on the UI thread</span></span>  
 <span data-ttu-id="c2163-142">正確なヒット テストは、ペン スレッド上で実行されることはできません、ためにによっては、いくつかの要素がスタイラス入力が他の要素のためのものを受け取ることがあります。</span><span class="sxs-lookup"><span data-stu-id="c2163-142">Because accurate hit-testing cannot be performed on the pen thread, some elements might occasionally receive stylus input intended for other elements.</span></span> <span data-ttu-id="c2163-143">サブスクライブしで操作を実行する操作を実行する前に、入力が正しく回送されたことを確認する必要がある場合、 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn.OnStylusDownProcessed%2A>、 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn.OnStylusMoveProcessed%2A>、または<xref:System.Windows.Input.StylusPlugIns.StylusPlugIn.OnStylusUpProcessed%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="c2163-143">If you need to make sure the input was routed correctly before performing an operation, subscribe to and perform the operation in the <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn.OnStylusDownProcessed%2A>, <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn.OnStylusMoveProcessed%2A>, or <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn.OnStylusUpProcessed%2A> method.</span></span> <span data-ttu-id="c2163-144">これらのメソッドは、正確なヒット テストが実行された後に、アプリケーション スレッドによって呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="c2163-144">These methods are invoked by the application thread after accurate hit-testing has been performed.</span></span> <span data-ttu-id="c2163-145">これらのメソッドにサブスクライブする、<xref:System.Windows.Input.StylusPlugIns.RawStylusInput.NotifyWhenProcessed%2A>ペン スレッド上で発生するメソッド内のメソッド。</span><span class="sxs-lookup"><span data-stu-id="c2163-145">To subscribe to these methods, call the <xref:System.Windows.Input.StylusPlugIns.RawStylusInput.NotifyWhenProcessed%2A> method in the method that occurs on the pen thread.</span></span>  
  
 <span data-ttu-id="c2163-146">次の図は、ペン スレッドとのスタイラス イベントに関して UI スレッド間のリレーションシップを<xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>します。</span><span class="sxs-lookup"><span data-stu-id="c2163-146">The following diagram illustrates the relationship between the pen thread and UI thread with respect to the stylus events of a <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>.</span></span>  
  
 <span data-ttu-id="c2163-147">![インク スレッド モデル&#40;UI およびペン&#41;](./media/inkthreading-plugincallbacks.png "InkThreading_PluginCallbacks")</span><span class="sxs-lookup"><span data-stu-id="c2163-147">![Ink Threading Models &#40;UI and Pen&#41;](./media/inkthreading-plugincallbacks.png "InkThreading_PluginCallbacks")</span></span>  
  
## <a name="rendering-ink"></a><span data-ttu-id="c2163-148">レンダリング インク</span><span class="sxs-lookup"><span data-stu-id="c2163-148">Rendering Ink</span></span>  
 <span data-ttu-id="c2163-149">ユーザーがストロークを描画、<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>を"flow"ペンから UI スレッドがビジー状態のときにさらに、インクが表示されるように、別のスレッドでインクをレンダリングします。</span><span class="sxs-lookup"><span data-stu-id="c2163-149">As the user draws a stroke, <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> renders the ink on a separate thread so the ink appears to "flow" from the pen even when the UI thread is busy.</span></span>  <span data-ttu-id="c2163-150"><xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>スタイラス ポイントを収集するように、動的レンダリング スレッドで、ビジュアル ツリーを構築します。</span><span class="sxs-lookup"><span data-stu-id="c2163-150">The <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> builds a visual tree on the dynamic rendering thread as it collects stylus points.</span></span>  <span data-ttu-id="c2163-151">ユーザーがストロークを終了すると、<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>アプリケーションは次の描画パスと、通知を要求します。</span><span class="sxs-lookup"><span data-stu-id="c2163-151">When the user finishes the stroke, the <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> asks to be notified when the application does the next rendering pass.</span></span>  <span data-ttu-id="c2163-152">アプリケーションが次の描画パスが完了したら、<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>そのビジュアル ツリーをクリーンアップします。</span><span class="sxs-lookup"><span data-stu-id="c2163-152">After the application completes the next rendering pass, the <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> cleans up its visual tree.</span></span>  <span data-ttu-id="c2163-153">このプロセスを説明する図を次に示します。</span><span class="sxs-lookup"><span data-stu-id="c2163-153">The following diagram illustrates this process.</span></span>  
  
 <span data-ttu-id="c2163-154">![インク スレッド ダイアグラム](./media/inkthreading-visualtree.png "InkThreading_VisualTree")</span><span class="sxs-lookup"><span data-stu-id="c2163-154">![Ink threading diagram](./media/inkthreading-visualtree.png "InkThreading_VisualTree")</span></span>  
  
1. <span data-ttu-id="c2163-155">ユーザーがストロークを開始します。</span><span class="sxs-lookup"><span data-stu-id="c2163-155">The user begins the stroke.</span></span>  
  
    1.  <span data-ttu-id="c2163-156"><xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>ビジュアル ツリーを作成します。</span><span class="sxs-lookup"><span data-stu-id="c2163-156">The <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> creates the visual tree.</span></span>  
  
2. <span data-ttu-id="c2163-157">ユーザーがストロークを描画します。</span><span class="sxs-lookup"><span data-stu-id="c2163-157">The user is drawing the stroke.</span></span>  
  
    1.  <span data-ttu-id="c2163-158"><xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>ビジュアル ツリーを構築します。</span><span class="sxs-lookup"><span data-stu-id="c2163-158">The <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> builds the visual tree.</span></span>  
  
3. <span data-ttu-id="c2163-159">ユーザーがストロークを終了します。</span><span class="sxs-lookup"><span data-stu-id="c2163-159">The user ends the stroke.</span></span>  
  
    1.  <span data-ttu-id="c2163-160"><xref:System.Windows.Controls.InkPresenter>ストロークをそのビジュアル ツリーに追加します。</span><span class="sxs-lookup"><span data-stu-id="c2163-160">The <xref:System.Windows.Controls.InkPresenter> adds the stroke to its visual tree.</span></span>  
  
    2.  <span data-ttu-id="c2163-161">Media Integration Layer (MIL) は、静的にストロークをレンダリングします。</span><span class="sxs-lookup"><span data-stu-id="c2163-161">The Media Integration Layer (MIL) statically renders the strokes.</span></span>  
  
    3.  <span data-ttu-id="c2163-162"><xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>ビジュアルをクリーンアップします。</span><span class="sxs-lookup"><span data-stu-id="c2163-162">The <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> cleans up the visuals.</span></span>
