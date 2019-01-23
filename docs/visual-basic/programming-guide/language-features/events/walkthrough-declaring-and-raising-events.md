---
title: 宣言と発生イベント (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- declarations [Visual Basic], events
- events [Visual Basic], walkthroughs
- declaring events [Visual Basic], walkthroughs
- events [Visual Basic], declaring
- events [Visual Basic], raising
- raising events [Visual Basic], walkthroughs
ms.assetid: 8ffb3be8-097d-4d3c-b71e-04555ebda2a2
ms.openlocfilehash: f792109f1d1117b5b112e06da1510938e4b8a5ec
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54580496"
---
# <a name="walkthrough-declaring-and-raising-events-visual-basic"></a><span data-ttu-id="4fc8d-102">チュートリアル: 宣言と発生イベント (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4fc8d-102">Walkthrough: Declaring and Raising Events (Visual Basic)</span></span>
<span data-ttu-id="4fc8d-103">このチュートリアルを宣言してという名前のクラスのイベントを発生させる方法について説明`Widget`します。</span><span class="sxs-lookup"><span data-stu-id="4fc8d-103">This walkthrough demonstrates how to declare and raise events for a class named `Widget`.</span></span> <span data-ttu-id="4fc8d-104">手順を完了した後可能性がある、関連トピック[チュートリアル。イベントの処理](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md)からのイベントを使用する方法を示す`Widget`アプリケーションで状態情報を提供するオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="4fc8d-104">After you complete the steps, you might want to read the companion topic, [Walkthrough: Handling Events](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md), which shows how to use events from `Widget` objects to provide status information in an application.</span></span>  
  
## <a name="the-widget-class"></a><span data-ttu-id="4fc8d-105">ウィジェット クラス</span><span class="sxs-lookup"><span data-stu-id="4fc8d-105">The Widget Class</span></span>  
 <span data-ttu-id="4fc8d-106">今のところ必要のある想定を`Widget`クラス。</span><span class="sxs-lookup"><span data-stu-id="4fc8d-106">Assume for the moment that you have a `Widget` class.</span></span> <span data-ttu-id="4fc8d-107">`Widget`クラスにメソッドを実行するには長い時間がかかることがあり、ある種の完了のインジケーターを配置できるアプリケーションをします。</span><span class="sxs-lookup"><span data-stu-id="4fc8d-107">Your `Widget` class has a method that can take a long time to execute, and you want your application to be able to put up some kind of completion indicator.</span></span>  
  
 <span data-ttu-id="4fc8d-108">もちろん、行うことができます、`Widget`オブジェクト % 完了ダイアログ ボックスの表示が、すべてのプロジェクトを使用した場合は、そのダイアログ ボックスで、そのしするスタックは、`Widget`クラス。</span><span class="sxs-lookup"><span data-stu-id="4fc8d-108">Of course, you could make the `Widget` object show a percent-complete dialog box, but then you would be stuck with that dialog box in every project in which you used the `Widget` class.</span></span> <span data-ttu-id="4fc8d-109">オブジェクトの設計の原則は、ユーザー インターフェイス オブジェクト ハンドルを使用するアプリケーション、オブジェクトの全体的な目的は、フォームまたはダイアログ ボックスを管理する場合を除き、します。</span><span class="sxs-lookup"><span data-stu-id="4fc8d-109">A good principle of object design is to let the application that uses an object handle the user interface—unless the whole purpose of the object is to manage a form or dialog box.</span></span>  
  
 <span data-ttu-id="4fc8d-110">目的は、`Widget`を追加することが、他のタスクを実行するには、`PercentDone`イベントと let プロシージャを呼び出す`Widget`メソッド処理 's イベントと表示状態を更新します。</span><span class="sxs-lookup"><span data-stu-id="4fc8d-110">The purpose of `Widget` is to perform other tasks, so it is better to add a `PercentDone` event and let the procedure that calls `Widget`'s methods handle that event and display status updates.</span></span> <span data-ttu-id="4fc8d-111">`PercentDone`イベントは、タスクをキャンセルするためのメカニズムも提供できます。</span><span class="sxs-lookup"><span data-stu-id="4fc8d-111">The `PercentDone` event can also provide a mechanism for canceling the task.</span></span>  
  
#### <a name="to-build-the-code-example-for-this-topic"></a><span data-ttu-id="4fc8d-112">このトピックのコード例をビルドするには</span><span class="sxs-lookup"><span data-stu-id="4fc8d-112">To build the code example for this topic</span></span>  
  
1.  <span data-ttu-id="4fc8d-113">新しい Visual Basic Windows アプリケーション プロジェクトを開き、という名前のフォームを作成する`Form1`します。</span><span class="sxs-lookup"><span data-stu-id="4fc8d-113">Open a new Visual Basic Windows Application project and create a form named `Form1`.</span></span>  
  
2.  <span data-ttu-id="4fc8d-114">2 つのボタンとラベルを追加`Form1`します。</span><span class="sxs-lookup"><span data-stu-id="4fc8d-114">Add two buttons and a label to `Form1`.</span></span>  
  
3.  <span data-ttu-id="4fc8d-115">次の表のように、各オブジェクトに名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="4fc8d-115">Name the objects as shown in the following table.</span></span>  
  
    |<span data-ttu-id="4fc8d-116">オブジェクト</span><span class="sxs-lookup"><span data-stu-id="4fc8d-116">Object</span></span>|<span data-ttu-id="4fc8d-117">プロパティ</span><span class="sxs-lookup"><span data-stu-id="4fc8d-117">Property</span></span>|<span data-ttu-id="4fc8d-118">設定</span><span class="sxs-lookup"><span data-stu-id="4fc8d-118">Setting</span></span>|  
    |------------|--------------|-------------|  
    |`Button1`|`Text`|<span data-ttu-id="4fc8d-119">開始タスク</span><span class="sxs-lookup"><span data-stu-id="4fc8d-119">Start Task</span></span>|  
    |`Button2`|`Text`|<span data-ttu-id="4fc8d-120">キャンセル</span><span class="sxs-lookup"><span data-stu-id="4fc8d-120">Cancel</span></span>|  
    |`Label`|<span data-ttu-id="4fc8d-121">`(Name)`, `Text`</span><span class="sxs-lookup"><span data-stu-id="4fc8d-121">`(Name)`, `Text`</span></span>|<span data-ttu-id="4fc8d-122">lblPercentDone, 0</span><span class="sxs-lookup"><span data-stu-id="4fc8d-122">lblPercentDone, 0</span></span>|  
  
4.  <span data-ttu-id="4fc8d-123">**プロジェクト**] メニューの [選択**クラスの追加**という名前のクラスを追加する`Widget.vb`をプロジェクトにします。</span><span class="sxs-lookup"><span data-stu-id="4fc8d-123">On the **Project** menu, choose **Add Class** to add a class named `Widget.vb` to the project.</span></span>  
  
#### <a name="to-declare-an-event-for-the-widget-class"></a><span data-ttu-id="4fc8d-124">ウィジェットのクラスのイベントを宣言するには</span><span class="sxs-lookup"><span data-stu-id="4fc8d-124">To declare an event for the Widget class</span></span>  
  
-   <span data-ttu-id="4fc8d-125">使用して、`Event`でイベントを宣言するキーワード、`Widget`クラス。</span><span class="sxs-lookup"><span data-stu-id="4fc8d-125">Use the `Event` keyword to declare an event in the `Widget` class.</span></span> <span data-ttu-id="4fc8d-126">イベントことがあります`ByVal`と`ByRef`、引数として`Widget`の`PercentDone`イベントを示します。</span><span class="sxs-lookup"><span data-stu-id="4fc8d-126">Note that an event can have `ByVal` and `ByRef` arguments, as `Widget`'s `PercentDone` event demonstrates:</span></span>  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#1](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-declaring-and-raising-events_1.vb)]  
  
 <span data-ttu-id="4fc8d-127">呼び出し元のオブジェクトを受信すると、 `PercentDone` 、イベント、`Percent`引数には、タスクが完了の割合が含まれています。</span><span class="sxs-lookup"><span data-stu-id="4fc8d-127">When the calling object receives a `PercentDone` event, the `Percent` argument contains the percentage of the task that is complete.</span></span> <span data-ttu-id="4fc8d-128">`Cancel`に引数を設定することができます`True`イベントを発生させたメソッドをキャンセルします。</span><span class="sxs-lookup"><span data-stu-id="4fc8d-128">The `Cancel` argument can be set to `True` to cancel the method that raised the event.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4fc8d-129">例外を次のプロシージャの引数と同様に、イベント引数を宣言できます。イベントを使用できない`Optional`または`ParamArray`引数、およびイベントに戻り値がありません。</span><span class="sxs-lookup"><span data-stu-id="4fc8d-129">You can declare event arguments just as you do arguments of procedures, with the following exceptions: Events cannot have `Optional` or `ParamArray` arguments, and events do not have return values.</span></span>  
  
 <span data-ttu-id="4fc8d-130">`PercentDone`イベントは、`LongTask`のメソッド、`Widget`クラス。</span><span class="sxs-lookup"><span data-stu-id="4fc8d-130">The `PercentDone` event is raised by the `LongTask` method of the `Widget` class.</span></span> <span data-ttu-id="4fc8d-131">`LongTask` 2 つの引数: 時間の長さメソッドが行う作業、および前に最小の時間間隔を装う`LongTask`させる一時停止、`PercentDone`イベント。</span><span class="sxs-lookup"><span data-stu-id="4fc8d-131">`LongTask` takes two arguments: the length of time the method pretends to be doing work, and the minimum time interval before `LongTask` pauses to raise the `PercentDone` event.</span></span>  
  
#### <a name="to-raise-the-percentdone-event"></a><span data-ttu-id="4fc8d-132">ですイベントを発生させる</span><span class="sxs-lookup"><span data-stu-id="4fc8d-132">To raise the PercentDone event</span></span>  
  
1.  <span data-ttu-id="4fc8d-133">アクセスを簡略化する、 `Timer` 、このクラスによって使用されるプロパティの追加、`Imports`クラスのモジュールの宣言セクションの先頭にステートメントの上、`Class Widget`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="4fc8d-133">To simplify access to the `Timer` property used by this class, add an `Imports` statement to the top of the declarations section of your class module, above the `Class Widget` statement.</span></span>  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#2](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-declaring-and-raising-events_2.vb)]  
  
2.  <span data-ttu-id="4fc8d-134">`Widget` クラスに次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="4fc8d-134">Add the following code to the `Widget` class:</span></span>  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#3](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-declaring-and-raising-events_3.vb)]  
  
 <span data-ttu-id="4fc8d-135">アプリケーションを呼び出すと、`LongTask`メソッド、`Widget`クラスが生成、`PercentDone`イベントすべて`MinimumInterval`秒。</span><span class="sxs-lookup"><span data-stu-id="4fc8d-135">When your application calls the `LongTask` method, the `Widget` class raises the `PercentDone` event every `MinimumInterval` seconds.</span></span> <span data-ttu-id="4fc8d-136">イベントが返されるときに`LongTask`かどうかをチェック、`Cancel`引数に設定された`True`します。</span><span class="sxs-lookup"><span data-stu-id="4fc8d-136">When the event returns, `LongTask` checks to see if the `Cancel` argument was set to `True`.</span></span>  
  
 <span data-ttu-id="4fc8d-137">免責事項をいくつかは、ここで必要です。</span><span class="sxs-lookup"><span data-stu-id="4fc8d-137">A few disclaimers are necessary here.</span></span> <span data-ttu-id="4fc8d-138">わかりやすくするため、`LongTask`プロシージャでは、事前にわかってタスクがどれくらいの時間を前提としています。</span><span class="sxs-lookup"><span data-stu-id="4fc8d-138">For simplicity, the `LongTask` procedure assumes you know in advance how long the task will take.</span></span> <span data-ttu-id="4fc8d-139">これは、ケースではほとんどありません。</span><span class="sxs-lookup"><span data-stu-id="4fc8d-139">This is almost never the case.</span></span> <span data-ttu-id="4fc8d-140">何かが発生していることを示す値を取得するまでに経過する時間数では単には、多くの場合、最も重要なユーザーに、タスクを均等なサイズのチャンクに分割することは困難であり、できます。</span><span class="sxs-lookup"><span data-stu-id="4fc8d-140">Dividing tasks into chunks of even size can be difficult, and often what matters most to users is simply the amount of time that passes before they get an indication that something is happening.</span></span>  
  
 <span data-ttu-id="4fc8d-141">このサンプルでは別の欠陥を発見することがあります。</span><span class="sxs-lookup"><span data-stu-id="4fc8d-141">You may have spotted another flaw in this sample.</span></span> <span data-ttu-id="4fc8d-142">`Timer`プロパティは、午前 0 時から経過した秒数を返します。 直前の午前 0 時に開始されている場合、アプリケーションとして行き詰まってそのため、します。</span><span class="sxs-lookup"><span data-stu-id="4fc8d-142">The `Timer` property returns the number of seconds that have passed since midnight; therefore, the application gets stuck if it is started just before midnight.</span></span> <span data-ttu-id="4fc8d-143">時間の計測をより慎重なアプローチはこのなどの境界条件を考慮に入れるに入れるかなどのプロパティを使用して`Now`します。</span><span class="sxs-lookup"><span data-stu-id="4fc8d-143">A more careful approach to measuring time would take boundary conditions such as this into consideration, or avoid them altogether, using properties such as `Now`.</span></span>  
  
 <span data-ttu-id="4fc8d-144">これで、`Widget`クラスは、イベントを発生させることができます、次のように次のチュートリアルに進むことができます。</span><span class="sxs-lookup"><span data-stu-id="4fc8d-144">Now that the `Widget` class can raise events, you can move to the next walkthrough.</span></span> <span data-ttu-id="4fc8d-145">[チュートリアル: イベントの処理](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md)を使用する方法を示します`WithEvents`でイベント ハンドラーを関連付ける、`PercentDone`イベント。</span><span class="sxs-lookup"><span data-stu-id="4fc8d-145">[Walkthrough: Handling Events](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md) demonstrates how to use `WithEvents` to associate an event handler with the `PercentDone` event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4fc8d-146">関連項目</span><span class="sxs-lookup"><span data-stu-id="4fc8d-146">See also</span></span>
- <xref:Microsoft.VisualBasic.DateAndTime.Timer%2A>
- <xref:Microsoft.VisualBasic.DateAndTime.Now%2A>
- [<span data-ttu-id="4fc8d-147">チュートリアル: イベントの処理</span><span class="sxs-lookup"><span data-stu-id="4fc8d-147">Walkthrough: Handling Events</span></span>](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md)
- [<span data-ttu-id="4fc8d-148">イベント</span><span class="sxs-lookup"><span data-stu-id="4fc8d-148">Events</span></span>](../../../../visual-basic/programming-guide/language-features/events/index.md)
