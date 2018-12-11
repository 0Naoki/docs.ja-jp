---
title: RaiseEvent ステートメント (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.RaiseEventMethod
- vb.RaiseEvent
- RaiseEvent
helpviewer_keywords:
- raising events [Visual Basic], RaiseEvent statement
- RaiseEvent statement [Visual Basic]
- event handlers, connecting events to
ms.assetid: f82e380a-1e6b-4047-bea8-c853f4d2c742
ms.openlocfilehash: ba4c05b3ef69d180f43ac3b90aa8fd6dee9c80fb
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2018
ms.locfileid: "53143299"
---
# <a name="raiseevent-statement"></a><span data-ttu-id="1962e-102">RaiseEvent ステートメント</span><span class="sxs-lookup"><span data-stu-id="1962e-102">RaiseEvent Statement</span></span>
<span data-ttu-id="1962e-103">クラス、フォーム、またはドキュメント内のモジュール レベルで宣言されているイベントをトリガーします。</span><span class="sxs-lookup"><span data-stu-id="1962e-103">Triggers an event declared at module level within a class, form, or document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1962e-104">構文</span><span class="sxs-lookup"><span data-stu-id="1962e-104">Syntax</span></span>  
  
```  
RaiseEvent eventname[( argumentlist )]  
```  
  
## <a name="parts"></a><span data-ttu-id="1962e-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="1962e-105">Parts</span></span>  
 `eventname`  
 <span data-ttu-id="1962e-106">必須。</span><span class="sxs-lookup"><span data-stu-id="1962e-106">Required.</span></span> <span data-ttu-id="1962e-107">トリガーするイベントの名前。</span><span class="sxs-lookup"><span data-stu-id="1962e-107">Name of the event to trigger.</span></span>  
  
 `argumentlist`  
 <span data-ttu-id="1962e-108">任意。</span><span class="sxs-lookup"><span data-stu-id="1962e-108">Optional.</span></span> <span data-ttu-id="1962e-109">変数、配列、または式のコンマ区切りのリスト。</span><span class="sxs-lookup"><span data-stu-id="1962e-109">Comma-delimited list of variables, arrays, or expressions.</span></span> <span data-ttu-id="1962e-110">`argumentlist`引数はかっこで囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="1962e-110">The `argumentlist` argument must be enclosed by parentheses.</span></span> <span data-ttu-id="1962e-111">引数がない場合は、かっこを省略する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1962e-111">If there are no arguments, the parentheses must be omitted.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1962e-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="1962e-112">Remarks</span></span>  
 <span data-ttu-id="1962e-113">必要な`eventname`は、モジュール内で宣言されたイベントの名前。</span><span class="sxs-lookup"><span data-stu-id="1962e-113">The required `eventname` is the name of an event declared within the module.</span></span> <span data-ttu-id="1962e-114">Visual Basic 変数の名前付け規則に従います。</span><span class="sxs-lookup"><span data-stu-id="1962e-114">It follows Visual Basic variable naming conventions.</span></span>  
  
 <span data-ttu-id="1962e-115">イベントが発生したモジュール内で宣言されていない、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="1962e-115">If the event has not been declared within the module in which it is raised, an error occurs.</span></span> <span data-ttu-id="1962e-116">次のコード フラグメントは、イベントの宣言とイベントが発生したプロシージャを示しています。</span><span class="sxs-lookup"><span data-stu-id="1962e-116">The following code fragment illustrates an event declaration and a procedure in which the event is raised.</span></span>  
  
 [!code-vb[VbVbalrEvents#37](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/raiseevent-statement_1.vb)]  
  
 <span data-ttu-id="1962e-117">使用することはできません`RaiseEvent`モジュールで明示的に宣言されていないイベントを発生させます。</span><span class="sxs-lookup"><span data-stu-id="1962e-117">You cannot use `RaiseEvent` to raise events that are not explicitly declared in the module.</span></span> <span data-ttu-id="1962e-118">たとえば、すべてのフォームの継承、<xref:System.Windows.Forms.Control.Click>からイベント<xref:System.Windows.Forms.Form?displayProperty=nameWithType>を使用して、発生することはできません`RaiseEvent`派生フォームでします。</span><span class="sxs-lookup"><span data-stu-id="1962e-118">For example, all forms inherit a <xref:System.Windows.Forms.Control.Click> event from <xref:System.Windows.Forms.Form?displayProperty=nameWithType>, it cannot be raised using `RaiseEvent` in a derived form.</span></span> <span data-ttu-id="1962e-119">宣言する場合、`Click`イベント モジュールでは、フォーム、フォーム自体のシャドウ<xref:System.Windows.Forms.Control.Click>イベント。</span><span class="sxs-lookup"><span data-stu-id="1962e-119">If you declare a `Click` event in the form module, it shadows the form's own <xref:System.Windows.Forms.Control.Click> event.</span></span> <span data-ttu-id="1962e-120">フォームを呼び出すことができますも<xref:System.Windows.Forms.Control.Click>イベントを呼び出すことによって、<xref:System.Windows.Forms.Control.OnClick%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="1962e-120">You can still invoke the form's <xref:System.Windows.Forms.Control.Click> event by calling the <xref:System.Windows.Forms.Control.OnClick%2A> method.</span></span>  
  
 <span data-ttu-id="1962e-121">既定では、Visual Basic で定義されたイベントは、接続が確立されている順序では、そのイベント ハンドラーを生成します。</span><span class="sxs-lookup"><span data-stu-id="1962e-121">By default, an event defined in Visual Basic raises its event handlers in the order that the connections are established.</span></span> <span data-ttu-id="1962e-122">イベントがあるため`ByRef`パラメーター、接続するプロセスは以前のイベント ハンドラーによって変更されているパラメーターを受け取ることがあります。</span><span class="sxs-lookup"><span data-stu-id="1962e-122">Because events can have `ByRef` parameters, a process that connects late may receive parameters that have been changed by an earlier event handler.</span></span> <span data-ttu-id="1962e-123">イベント ハンドラーの実行後は、イベントを発生させたサブルーチンに制御が返されます。</span><span class="sxs-lookup"><span data-stu-id="1962e-123">After the event handlers execute, control is returned to the subroutine that raised the event.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1962e-124">非共有イベントは、宣言されているクラスのコンス トラクター内では発生しません。</span><span class="sxs-lookup"><span data-stu-id="1962e-124">Non-shared events should not be raised within the constructor of the class in which they are declared.</span></span> <span data-ttu-id="1962e-125">このようなイベントでは、実行時エラーが発生しない、関連付けられているイベント ハンドラーによってキャッチするされない場合があります。</span><span class="sxs-lookup"><span data-stu-id="1962e-125">Although such events do not cause run-time errors, they may fail to be caught by associated event handlers.</span></span> <span data-ttu-id="1962e-126">使用して、`Shared`修飾子をコンス トラクターからイベントを発生させる必要がある場合は、共有イベントを作成します。</span><span class="sxs-lookup"><span data-stu-id="1962e-126">Use the `Shared` modifier to create a shared event if you need to raise an event from a constructor.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1962e-127">イベントの既定の動作を変更するには、カスタム イベントを定義します。</span><span class="sxs-lookup"><span data-stu-id="1962e-127">You can change the default behavior of events by defining a custom event.</span></span> <span data-ttu-id="1962e-128">カスタム イベントの場合、`RaiseEvent`ステートメントで呼び出されるイベントの`RaiseEvent`アクセサー。</span><span class="sxs-lookup"><span data-stu-id="1962e-128">For custom events, the `RaiseEvent` statement invokes the event's `RaiseEvent` accessor.</span></span> <span data-ttu-id="1962e-129">カスタム イベントの詳細については、次を参照してください。 [Event ステートメント](../../../visual-basic/language-reference/statements/event-statement.md)します。</span><span class="sxs-lookup"><span data-stu-id="1962e-129">For more information on custom events, see [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1962e-130">例</span><span class="sxs-lookup"><span data-stu-id="1962e-130">Example</span></span>  
 <span data-ttu-id="1962e-131">次の例では、イベントを使用して 10 秒から 0 秒までカウント ダウンします。</span><span class="sxs-lookup"><span data-stu-id="1962e-131">The following example uses events to count down seconds from 10 to 0.</span></span> <span data-ttu-id="1962e-132">このコードはいくつかのイベントに関連するメソッド、プロパティ、およびなど、ステートメント、`RaiseEvent`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="1962e-132">The code illustrates several of the event-related methods, properties, and statements, including the `RaiseEvent` statement.</span></span>  
  
 <span data-ttu-id="1962e-133">イベントを発生させるクラスをイベント ソース、イベントを処理するメソッドをイベント ハンドラーと呼びます。</span><span class="sxs-lookup"><span data-stu-id="1962e-133">The class that raises an event is the event source, and the methods that process the event are the event handlers.</span></span> <span data-ttu-id="1962e-134">イベント ソースでは、生成されるイベントに対して複数のイベント ハンドラーを設定できます。</span><span class="sxs-lookup"><span data-stu-id="1962e-134">An event source can have multiple handlers for the events it generates.</span></span> <span data-ttu-id="1962e-135">クラスでイベントが発生すると、そのイベントは、オブジェクトのインスタンスに対するイベントを処理するために選択されたすべてのクラスで発生します。</span><span class="sxs-lookup"><span data-stu-id="1962e-135">When the class raises the event, that event is raised on every class that has elected to handle events for that instance of the object.</span></span>  
  
 <span data-ttu-id="1962e-136">また、この例では、ボタン (`Button1`) とテキスト ボックス (`TextBox1`) を含んだフォーム (`Form1`) も使用しています。</span><span class="sxs-lookup"><span data-stu-id="1962e-136">The example also uses a form (`Form1`) with a button (`Button1`) and a text box (`TextBox1`).</span></span> <span data-ttu-id="1962e-137">ボタンをクリックすると、1 つ目のテキスト ボックスに 10 秒から 0 秒までのカウントダウンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1962e-137">When you click the button, the first text box displays a countdown from 10 to 0 seconds.</span></span> <span data-ttu-id="1962e-138">カウントダウンが終わると (10 秒が経過すると)、1 つ目のテキスト ボックスに "Done" と表示されます。</span><span class="sxs-lookup"><span data-stu-id="1962e-138">When the full time (10 seconds) has elapsed, the first text box displays "Done".</span></span>  
  
 <span data-ttu-id="1962e-139">`Form1` のコードでは、フォームの初期状態と終了状態を指定しています。</span><span class="sxs-lookup"><span data-stu-id="1962e-139">The code for `Form1` specifies the initial and terminal states of the form.</span></span> <span data-ttu-id="1962e-140">イベント発生時に実行されるコードも含まれています。</span><span class="sxs-lookup"><span data-stu-id="1962e-140">It also contains the code executed when events are raised.</span></span>  
  
 <span data-ttu-id="1962e-141">この例を使用する新しい Windows アプリケーション プロジェクトを開き、という名前のボタンを追加`Button1`という名前のテキスト ボックスと`TextBox1`という名前のメイン フォームに`Form1`します。</span><span class="sxs-lookup"><span data-stu-id="1962e-141">To use this example, open a new Windows Application project, add a button named `Button1` and a text box named `TextBox1` to the main form, named `Form1`.</span></span> <span data-ttu-id="1962e-142">次にフォームを右クリックし、をクリックして**コードの表示**コード エディターを開きます。</span><span class="sxs-lookup"><span data-stu-id="1962e-142">Then right-click the form and click **View Code** to open the Code Editor.</span></span>  
  
 <span data-ttu-id="1962e-143">追加、`WithEvents`変数の宣言セクションに、`Form1`クラス。</span><span class="sxs-lookup"><span data-stu-id="1962e-143">Add a `WithEvents` variable to the declarations section of the `Form1` class.</span></span>  
  
 [!code-vb[VbVbalrEvents#14](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/raiseevent-statement_2.vb)]  
  
## <a name="example"></a><span data-ttu-id="1962e-144">例</span><span class="sxs-lookup"><span data-stu-id="1962e-144">Example</span></span>  
 <span data-ttu-id="1962e-145">`Form1` のコードに次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="1962e-145">Add the following code to the code for `Form1`.</span></span> <span data-ttu-id="1962e-146">など、存在するすべての重複するプロシージャを置き換える`Form_Load`、または`Button_Click`します。</span><span class="sxs-lookup"><span data-stu-id="1962e-146">Replace any duplicate procedures that may exist, such as `Form_Load`, or `Button_Click`.</span></span>  
  
 [!code-vb[VbVbalrEvents#15](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/raiseevent-statement_3.vb)]  
  
 <span data-ttu-id="1962e-147">前の例を実行し、ボタンをクリックします。 f5 キーを押して**開始**します。</span><span class="sxs-lookup"><span data-stu-id="1962e-147">Press F5 to run the preceding example, and click the button labeled **Start**.</span></span> <span data-ttu-id="1962e-148">最初のテキスト ボックスで、秒のカウント ダウンが開始されます。</span><span class="sxs-lookup"><span data-stu-id="1962e-148">The first text box starts to count down the seconds.</span></span> <span data-ttu-id="1962e-149">カウントダウンが終わると (10 秒が経過すると)、1 つ目のテキスト ボックスに "Done" と表示されます。</span><span class="sxs-lookup"><span data-stu-id="1962e-149">When the full time (10 seconds) has elapsed, the first text box displays "Done".</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1962e-150">`My.Application.DoEvents`フォームは、メソッドがまったく同じ方法でイベントを処理できません。</span><span class="sxs-lookup"><span data-stu-id="1962e-150">The `My.Application.DoEvents` method does not process events in exactly the same way as the form does.</span></span> <span data-ttu-id="1962e-151">使用することができます、イベントを直接処理するためのフォームは、マルチ スレッドです。</span><span class="sxs-lookup"><span data-stu-id="1962e-151">To allow the form to handle the events directly, you can use multithreading.</span></span> <span data-ttu-id="1962e-152">詳細については、次を参照してください。[マネージ スレッド処理](../../../standard/threading/index.md)します。</span><span class="sxs-lookup"><span data-stu-id="1962e-152">For more information, see [Managed Threading](../../../standard/threading/index.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1962e-153">関連項目</span><span class="sxs-lookup"><span data-stu-id="1962e-153">See Also</span></span>  
 [<span data-ttu-id="1962e-154">イベント</span><span class="sxs-lookup"><span data-stu-id="1962e-154">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)  
 [<span data-ttu-id="1962e-155">Event ステートメント</span><span class="sxs-lookup"><span data-stu-id="1962e-155">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
 [<span data-ttu-id="1962e-156">AddHandler ステートメント</span><span class="sxs-lookup"><span data-stu-id="1962e-156">AddHandler Statement</span></span>](../../../visual-basic/language-reference/statements/addhandler-statement.md)  
 [<span data-ttu-id="1962e-157">RemoveHandler ステートメント</span><span class="sxs-lookup"><span data-stu-id="1962e-157">RemoveHandler Statement</span></span>](../../../visual-basic/language-reference/statements/removehandler-statement.md)  
 [<span data-ttu-id="1962e-158">Handles</span><span class="sxs-lookup"><span data-stu-id="1962e-158">Handles</span></span>](../../../visual-basic/language-reference/statements/handles-clause.md)
