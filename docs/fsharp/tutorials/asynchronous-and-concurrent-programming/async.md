---
title: 非同期プログラミング
description: 学習方法F#非同期プログラミングが言語レベルのプログラミング モデルを簡単に使用し、自然言語を使用して実現されます。
ms.date: 06/20/2016
ms.openlocfilehash: 6925a0132f9beed6be5f9dded3630b551072bea2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59343455"
---
# <a name="async-programming-in-f"></a><span data-ttu-id="cd17f-103">F での非同期プログラミング\#</span><span class="sxs-lookup"><span data-stu-id="cd17f-103">Async Programming in F\#</span></span>

> [!NOTE]
> <span data-ttu-id="cd17f-104">この記事では、いくつか誤りが検出されました。</span><span class="sxs-lookup"><span data-stu-id="cd17f-104">Some inaccuracies have been discovered in this article.</span></span>  <span data-ttu-id="cd17f-105">書き換えられます。</span><span class="sxs-lookup"><span data-stu-id="cd17f-105">It is being rewritten.</span></span>  <span data-ttu-id="cd17f-106">参照してください[問題 #666](https://github.com/dotnet/docs/issues/666)への変更について説明します。</span><span class="sxs-lookup"><span data-stu-id="cd17f-106">See [Issue #666](https://github.com/dotnet/docs/issues/666) to learn about the changes.</span></span>

<span data-ttu-id="cd17f-107">非同期のプログラミングF#言語レベルのプログラミング モデルが使いやすく、自然言語にするように設計を行います。</span><span class="sxs-lookup"><span data-stu-id="cd17f-107">Async programming in F# can be accomplished through a language-level programming model designed to be easy to use and natural to the language.</span></span>

<span data-ttu-id="cd17f-108">非同期のプログラミングの中核となるF#は`Async<'T>`に、バック グラウンドで実行される作業の表現を`'T`特殊を介して、いずれかの型が返されます`return`キーワードまたは`unit`場合、非同期ワークフロー返される結果がありません。</span><span class="sxs-lookup"><span data-stu-id="cd17f-108">The core of async programming in F# is `Async<'T>`, a representation of work that can be triggered to run in the background, where `'T` is either the type returned via the special `return` keyword or `unit` if the async workflow has no result to return.</span></span>

<span data-ttu-id="cd17f-109">キーの概念を理解するが非同期式の型があること`Async<'T>`、これは単に、_仕様_非同期のコンテキストで実行する作業の。</span><span class="sxs-lookup"><span data-stu-id="cd17f-109">The key concept to understand is that an async expression’s type is `Async<'T>`, which is merely a _specification_ of work to be done in an asynchronous context.</span></span> <span data-ttu-id="cd17f-110">開始関数のいずれかで明示的に開始されるまでは実行されません (など`Async.RunSynchronously`)。</span><span class="sxs-lookup"><span data-stu-id="cd17f-110">It is not executed until you explicitly start it with one of the starting functions (such as `Async.RunSynchronously`).</span></span> <span data-ttu-id="cd17f-111">作業についての考え方を別の方法ですが、実際には非常に簡単に終了します。</span><span class="sxs-lookup"><span data-stu-id="cd17f-111">Although this is a different way of thinking about doing work, it ends up being quite simple in practice.</span></span>

<span data-ttu-id="cd17f-112">たとえば、メイン スレッドをブロックすることがなく dotnetfoundation.org から HTML をダウンロードしたいとします。</span><span class="sxs-lookup"><span data-stu-id="cd17f-112">For example, say you wanted to download the HTML from dotnetfoundation.org without blocking the main thread.</span></span> <span data-ttu-id="cd17f-113">このようなことを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="cd17f-113">You can accomplish it like this:</span></span>

```fsharp
open System
open System.Net

let fetchHtmlAsync url = 
    async {
        let uri = Uri(url)
        use webClient = new WebClient()

        // Execution of fetchHtmlAsync won't continue until the result
        // of AsyncDownloadString is bound.
        let! html = webClient.AsyncDownloadString(uri)
        return html
    }

let html = "https://dotnetfoundation.org" |> fetchHtmlAsync |> Async.RunSynchronously
printfn "%s" html
```

<span data-ttu-id="cd17f-114">以上です。</span><span class="sxs-lookup"><span data-stu-id="cd17f-114">And that’s it!</span></span> <span data-ttu-id="cd17f-115">使用を除き`async`、 `let!`、および`return`、これはごく普通F#コード。</span><span class="sxs-lookup"><span data-stu-id="cd17f-115">Aside from the use of `async`, `let!`, and `return`, this is just normal F# code.</span></span>

<span data-ttu-id="cd17f-116">注目すべきである、いくつかの構文構造があります。</span><span class="sxs-lookup"><span data-stu-id="cd17f-116">There are a few syntactical constructs which are worth noting:</span></span>

*   <span data-ttu-id="cd17f-117">`let!` (別のコンテキストで実行) される非同期式の結果にバインドします。</span><span class="sxs-lookup"><span data-stu-id="cd17f-117">`let!` binds the result of an async expression (which runs on another context).</span></span>
*   <span data-ttu-id="cd17f-118">`use!` 同様の機能`let!`がスコープ外になったときに、そのバインドされているリソースを破棄します。</span><span class="sxs-lookup"><span data-stu-id="cd17f-118">`use!` works just like `let!`, but disposes its bound resources when it goes out of scope.</span></span>
*   <span data-ttu-id="cd17f-119">`do!` 何も返しませんが、非同期ワークフローを待機します。</span><span class="sxs-lookup"><span data-stu-id="cd17f-119">`do!` will await an async workflow which doesn’t return anything.</span></span>
*   <span data-ttu-id="cd17f-120">`return` 単に非同期式から結果を返します。</span><span class="sxs-lookup"><span data-stu-id="cd17f-120">`return` simply returns a result from an async expression.</span></span>
*   <span data-ttu-id="cd17f-121">`return!` 別の非同期ワークフローを実行し、結果としてその戻り値を返します。</span><span class="sxs-lookup"><span data-stu-id="cd17f-121">`return!` executes another async workflow and returns its return value as a result.</span></span>

<span data-ttu-id="cd17f-122">さらに、通常`let`、 `use`、および`do`キーワードは、通常の関数内にある場合と同様、非同期バージョンと共に使用できます。</span><span class="sxs-lookup"><span data-stu-id="cd17f-122">Additionally, normal `let`, `use`, and `do` keywords can be used alongside the async versions just as they would in a normal function.</span></span>

## <a name="how-to-start-async-code-in-f"></a><span data-ttu-id="cd17f-123">F での非同期コードを起動する方法\#</span><span class="sxs-lookup"><span data-stu-id="cd17f-123">How to start Async Code in F\#</span></span>

<span data-ttu-id="cd17f-124">前述のように、非同期コードを明示的に開始する必要がある別のコンテキストで実行する作業の仕様です。</span><span class="sxs-lookup"><span data-stu-id="cd17f-124">As mentioned earlier, async code is a specification of work to be done in another context which needs to be explicitly started.</span></span> <span data-ttu-id="cd17f-125">これを実現する 2 つの主な方法を次に示します。</span><span class="sxs-lookup"><span data-stu-id="cd17f-125">Here are two primary ways to accomplish this:</span></span>

1. <span data-ttu-id="cd17f-126">`Async.RunSynchronously` 別のスレッドで非同期ワークフローを開始し、その結果を待機します。</span><span class="sxs-lookup"><span data-stu-id="cd17f-126">`Async.RunSynchronously` will start an async workflow on another thread and await its result.</span></span>

```fsharp
open System
open System.Net

let fetchHtmlAsync url = 
    async {
        let uri = Uri(url)
        use webClient = new WebClient()
        let! html = webClient.AsyncDownloadString(uri)
        return html
    }

 // Execution will pause until fetchHtmlAsync finishes
 let html = "https://dotnetfoundation.org" |> fetchHtmlAsync |> Async.RunSynchronously

 // you actually have the result from fetchHtmlAsync now!
 printfn "%s" html
 ```

2. <span data-ttu-id="cd17f-127">`Async.Start` 別のスレッドで非同期ワークフローが開始され、**いない**その結果を待機します。</span><span class="sxs-lookup"><span data-stu-id="cd17f-127">`Async.Start` will start an async workflow on another thread, and will **not** await its result.</span></span>

```fsharp
open System
open System.Net
  
let uploadDataAsync url data = 
    async {
        let uri = Uri(url)
        use webClient = new WebClient()
        webClient.UploadStringAsync(uri, data)
    }

let workflow = uploadDataAsync "https://url-to-upload-to.com" "hello, world!"

// Execution will continue after calling this!
Async.Start(workflow)

printfn "%s" "uploadDataAsync is running in the background..."
 ```

<span data-ttu-id="cd17f-128">具体的なシナリオで使用可能な非同期ワークフローを開始するには、その他の方法はあります。</span><span class="sxs-lookup"><span data-stu-id="cd17f-128">There are other ways to start an async workflow available for more specific scenarios.</span></span> <span data-ttu-id="cd17f-129">詳細については[非同期リファレンス](https://msdn.microsoft.com/library/ee370232.aspx)します。</span><span class="sxs-lookup"><span data-stu-id="cd17f-129">They are detailed [in the Async reference](https://msdn.microsoft.com/library/ee370232.aspx).</span></span>

### <a name="a-note-on-threads"></a><span data-ttu-id="cd17f-130">スレッドに関する注意事項</span><span class="sxs-lookup"><span data-stu-id="cd17f-130">A Note on Threads</span></span>

<span data-ttu-id="cd17f-131">別のスレッド"の"という語句は、上記のように、ことを把握することが重要**非同期ワークフローのためのファサードであるわけではないマルチ スレッド**します。</span><span class="sxs-lookup"><span data-stu-id="cd17f-131">The phrase "on another thread" is mentioned above, but it is important to know that **this does not mean that async workflows are a facade for multithreading**.</span></span> <span data-ttu-id="cd17f-132">ワークフロー実際に「移動」有益な処理の実行時間の短時間にそれらを借りて、スレッド間でします。</span><span class="sxs-lookup"><span data-stu-id="cd17f-132">The workflow actually "jumps" between threads, borrowing them for a small amount of time to do useful work.</span></span> <span data-ttu-id="cd17f-133">非同期ワークフローは実質的に「待機中に」(たとえば、何かを返すネットワーク呼び出しの待機など)、まで他の有益な処理を移動操作を実行時にそれを借りてが任意のスレッドが解放されます。</span><span class="sxs-lookup"><span data-stu-id="cd17f-133">When an async workflow is effectively "waiting" (for example, waiting for a network call to return something), any thread it was borrowing at the time is freed up to go do useful work on something else.</span></span> <span data-ttu-id="cd17f-134">これにより、非同期ワークフローで、できるだけ効率的に実行されるシステムを利用して大量の I/O シナリオの特に強力になります。</span><span class="sxs-lookup"><span data-stu-id="cd17f-134">This allows async workflows to utilize the system they run on as effectively as possible, and makes them especially strong for high-volume I/O scenarios.</span></span>

## <a name="how-to-add-parallelism-to-async-code"></a><span data-ttu-id="cd17f-135">非同期コードを並列処理を追加する方法</span><span class="sxs-lookup"><span data-stu-id="cd17f-135">How to Add Parallelism to Async Code</span></span>

<span data-ttu-id="cd17f-136">場合があります可能性があります必要がありますを並列では、複数の非同期ジョブを実行する、その結果を収集し、何らかの方法で解釈します。</span><span class="sxs-lookup"><span data-stu-id="cd17f-136">Sometimes you may need to perform multiple asynchronous jobs in parallel, collect their results, and interpret them in some way.</span></span> <span data-ttu-id="cd17f-137">`Async.Parallel` これを強制的に変換しなくても含まれるタスク並列ライブラリを使用することがなく実行できる`Task<'T>`と`Async<'T>`型。</span><span class="sxs-lookup"><span data-stu-id="cd17f-137">`Async.Parallel` allows you to do this without needing to use the Task Parallel Library, which would involve needing to coerce `Task<'T>` and `Async<'T>` types.</span></span>

<span data-ttu-id="cd17f-138">次の例を使用して`Async.Parallel`を並列で 4 つの人気のあるサイトから HTML をダウンロードするこれらのタスクを完了するまで待機し、ダウンロードされた HTML を印刷します。</span><span class="sxs-lookup"><span data-stu-id="cd17f-138">The following example will use `Async.Parallel` to download the HTML from four popular sites in parallel, wait for those tasks to complete, and then print the HTML which was downloaded.</span></span>

```fsharp
open System
open System.Net

let urlList = 
    [ "https://www.microsoft.com"
      "https://www.google.com"
      "https://www.amazon.com"
      "https://www.facebook.com" ]

let fetchHtmlAsync url = 
    async {
        let uri = Uri(url)
        use webClient = new WebClient()
        let! html = webClient.AsyncDownloadString(uri)
        return html
    }

let getHtmlList urls =
    urls
    |> Seq.map fetchHtmlAsync   // Build an Async<'T> for each site
    |> Async.Parallel           // Returns an Async<'T []>
    |> Async.RunSynchronously   // Wait for the result of the parallel work

let htmlList = getHtmlList urlList

// We now have the downloaded HTML for each site!
for html in htmlList do
    printfn "%s" html
```

## <a name="important-info-and-advice"></a><span data-ttu-id="cd17f-139">重要な情報とアドバイス</span><span class="sxs-lookup"><span data-stu-id="cd17f-139">Important Info and Advice</span></span>

*   <span data-ttu-id="cd17f-140">使用するすべての関数の最後に"Async"を追加します。</span><span class="sxs-lookup"><span data-stu-id="cd17f-140">Append "Async" to the end of any functions you’ll consume</span></span>

 <span data-ttu-id="cd17f-141">これは単なる名前付け規則が、これはやすく API の発見など。</span><span class="sxs-lookup"><span data-stu-id="cd17f-141">Although this is just a naming convention, it does make things like API discoverability easier.</span></span> <span data-ttu-id="cd17f-142">同じルーチンの同期および非同期のバージョンがある場合に特には、明示的に名前を使用して非同期であることをお勧めです。</span><span class="sxs-lookup"><span data-stu-id="cd17f-142">Particularly if there are synchronous and asynchronous versions of the same routine, it’s a good idea to explicitly state which is asynchronous via the name.</span></span>

*   <span data-ttu-id="cd17f-143">コンパイラをリッスンします。</span><span class="sxs-lookup"><span data-stu-id="cd17f-143">Listen to the compiler!</span></span>

 <span data-ttu-id="cd17f-144">F#コンパイラは非常に厳格な"async"コードを同期的に実行を行うような問題とされることはほぼ不可能です。</span><span class="sxs-lookup"><span data-stu-id="cd17f-144">F#’s compiler is very strict, making it nearly impossible to do something troubling like run "async" code synchronously.</span></span> <span data-ttu-id="cd17f-145">警告に遭遇した場合はどのように考えるかをコードが実行されません記号です。</span><span class="sxs-lookup"><span data-stu-id="cd17f-145">If you come across a warning, that’s a sign that the code won’t execute how you think it will.</span></span> <span data-ttu-id="cd17f-146">コンパイラを満足することができますと、ほとんどの場合に、コードは、想定どおりに実行されます。</span><span class="sxs-lookup"><span data-stu-id="cd17f-146">If you can make the compiler happy, your code will most likely execute as expected.</span></span>

## <a name="for-the-cvb-programmer-looking-into-f"></a><span data-ttu-id="cd17f-147">C#または VB プログラマが F を見る\#</span><span class="sxs-lookup"><span data-stu-id="cd17f-147">For the C#/VB Programmer Looking Into F\#</span></span>

<span data-ttu-id="cd17f-148">このセクションでは、非同期モデルに使い慣れている前提としていますC#/VB。</span><span class="sxs-lookup"><span data-stu-id="cd17f-148">This section assumes you’re familiar with the async model in C#/VB.</span></span> <span data-ttu-id="cd17f-149">そうでない場合[での非同期プログラミングC#](../../../csharp/async.md)は開始点です。</span><span class="sxs-lookup"><span data-stu-id="cd17f-149">If you are not, [Async Programming in C#](../../../csharp/async.md) is a starting point.</span></span>

<span data-ttu-id="cd17f-150">基本的な違いは、C#または VB の非同期モデルとF#非同期モデル。</span><span class="sxs-lookup"><span data-stu-id="cd17f-150">There is a fundamental difference between the C#/VB async model and the F# async model.</span></span>

<span data-ttu-id="cd17f-151">返す関数を呼び出すと、`Task`または`Task<'T>`、そのジョブがすでに実行を開始します。</span><span class="sxs-lookup"><span data-stu-id="cd17f-151">When you call a function which returns a `Task` or `Task<'T>`, that job has already begun execution.</span></span> <span data-ttu-id="cd17f-152">返されたハンドルは、既に実行中の非同期ジョブを表します。</span><span class="sxs-lookup"><span data-stu-id="cd17f-152">The handle returned represents an already-running asynchronous job.</span></span> <span data-ttu-id="cd17f-153">非同期関数を呼び出すこととこれに対し、 F#、`Async<'a>`返されるとなるジョブを表す**生成**時点。</span><span class="sxs-lookup"><span data-stu-id="cd17f-153">In contrast, when you call an async function in F#, the `Async<'a>` returned represents a job which will be **generated** at some point.</span></span> <span data-ttu-id="cd17f-154">非同期ジョブのために強力ですが、このモデルを理解することがF#を連結して、簡単に条件付きで実行され、コントロールの細かい粒度で開始します。</span><span class="sxs-lookup"><span data-stu-id="cd17f-154">Understanding this model is powerful, because it allows for asynchronous jobs in F# to be chained together easier, performed conditionally, and be started with a finer grain of control.</span></span>

<span data-ttu-id="cd17f-155">その他のいくつかの類似点と注目すべき違いがあります。</span><span class="sxs-lookup"><span data-stu-id="cd17f-155">There are a few other similarities and differences worth noting.</span></span>

### <a name="similarities"></a><span data-ttu-id="cd17f-156">類似点</span><span class="sxs-lookup"><span data-stu-id="cd17f-156">Similarities</span></span>

*   <span data-ttu-id="cd17f-157">`let!`、 `use!`、および`do!`に似ています`await`内から、非同期ジョブを呼び出すときに、`async{ }`ブロックします。</span><span class="sxs-lookup"><span data-stu-id="cd17f-157">`let!`, `use!`, and `do!` are analogous to `await` when calling an async job from within an `async{ }` block.</span></span>

 <span data-ttu-id="cd17f-158">次の 3 つのキーワードは内でのみ使用できます、`async { }`ブロック、方法と似ています`await`内で呼び出すことができますのみ、`async`メソッド。</span><span class="sxs-lookup"><span data-stu-id="cd17f-158">The three keywords can only be used within an `async { }` block, similar to how `await` can only be invoked inside an `async` method.</span></span> <span data-ttu-id="cd17f-159">つまり、`let!`キャプチャし、結果を使用する場合に`use!`は同じですが、何かのリソースが使用すると、後にクリーンアップする必要がありますと`do!`戻り値を完了する非同期ワークフローを待機する場合に続行する前にします。</span><span class="sxs-lookup"><span data-stu-id="cd17f-159">In short, `let!` is for when you want to capture and use a result, `use!` is the same but for something whose resources should get cleaned after it’s used, and `do!` is for when you want to wait for an async workflow with no return value to finish before moving on.</span></span>

*   <span data-ttu-id="cd17f-160">F#同様の方法でデータを並列化をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="cd17f-160">F# supports data-parallelism in a similar way.</span></span>

 <span data-ttu-id="cd17f-161">非常に異なる方法で動作が`Async.Parallel`に対応する`Task.WhenAll`をすべて終了すると、一連の非同期ジョブの結果としているシナリオでは。</span><span class="sxs-lookup"><span data-stu-id="cd17f-161">Although it operates very differently, `Async.Parallel` corresponds to `Task.WhenAll` for the scenario of wanting the results of a set of async jobs when they all complete.</span></span>

### <a name="differences"></a><span data-ttu-id="cd17f-162">相違点</span><span class="sxs-lookup"><span data-stu-id="cd17f-162">Differences</span></span>

*   <span data-ttu-id="cd17f-163">入れ子になった`let!`いないは許可されているとは異なり、入れ子になった `await`</span><span class="sxs-lookup"><span data-stu-id="cd17f-163">Nested `let!` is not allowed, unlike nested `await`</span></span>

 <span data-ttu-id="cd17f-164">異なり`await`、無期限にネストできます`let!`ことはできませんし、その結果を別の内部で使用する前にバインドされている必要があります`let!`、 `do!`、または`use!`します。</span><span class="sxs-lookup"><span data-stu-id="cd17f-164">Unlike `await`, which can be nested indefinitely, `let!` cannot and must have its result bound before using it inside of another `let!`, `do!`, or `use!`.</span></span>

*   <span data-ttu-id="cd17f-165">キャンセルのサポートは、非常に簡単F#よりもC#/VB.</span><span class="sxs-lookup"><span data-stu-id="cd17f-165">Cancellation support is simpler in F# than in C#/VB.</span></span>

 <span data-ttu-id="cd17f-166">タスクの途中での実行でのキャンセルをサポートしているC#または VB では、チェックが必要、`IsCancellationRequested`プロパティまたは呼び出す`ThrowIfCancellationRequested()`上、`CancellationToken`非同期メソッドに渡されるオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="cd17f-166">Supporting cancellation of a task midway through its execution in C#/VB requires checking the `IsCancellationRequested` property or calling `ThrowIfCancellationRequested()` on a `CancellationToken` object that’s passed into the async method.</span></span>

<span data-ttu-id="cd17f-167">これに対し、F#非同期ワークフローがより自然にキャンセル可能です。</span><span class="sxs-lookup"><span data-stu-id="cd17f-167">In contrast, F# async workflows are more naturally cancellable.</span></span> <span data-ttu-id="cd17f-168">キャンセルは、単純な 3 段階のプロセスです。</span><span class="sxs-lookup"><span data-stu-id="cd17f-168">Cancellation is a simple three-step process.</span></span>

1. <span data-ttu-id="cd17f-169">新規の `CancellationTokenSource` を作成します。</span><span class="sxs-lookup"><span data-stu-id="cd17f-169">Create a new `CancellationTokenSource`.</span></span>
2. <span data-ttu-id="cd17f-170">開始関数に渡します。</span><span class="sxs-lookup"><span data-stu-id="cd17f-170">Pass it into a starting function.</span></span>
3. <span data-ttu-id="cd17f-171">呼び出す`Cancel`トークンにします。</span><span class="sxs-lookup"><span data-stu-id="cd17f-171">Call `Cancel` on the token.</span></span>

<span data-ttu-id="cd17f-172">例:</span><span class="sxs-lookup"><span data-stu-id="cd17f-172">Example:</span></span>

```fsharp
open System.Threading

// Create a workflow which will loop forever.
let workflow =
    async {
        while true do
            printfn "Working..."
            do! Async.Sleep 1000
    }
    
let tokenSource = new CancellationTokenSource()

// Start the workflow in the background
Async.Start (workflow, tokenSource.Token)

// Executing the next line will stop the workflow
tokenSource.Cancel()
```

<span data-ttu-id="cd17f-173">以上です。</span><span class="sxs-lookup"><span data-stu-id="cd17f-173">And that’s it!</span></span>

## <a name="further-resources"></a><span data-ttu-id="cd17f-174">他のリソース:</span><span class="sxs-lookup"><span data-stu-id="cd17f-174">Further resources:</span></span>

*   [<span data-ttu-id="cd17f-175">MSDN での非同期ワークフロー</span><span class="sxs-lookup"><span data-stu-id="cd17f-175">Async Workflows on MSDN</span></span>](https://msdn.microsoft.com/library/dd233250.aspx)
*   [<span data-ttu-id="cd17f-176">非同期のシーケンスF#</span><span class="sxs-lookup"><span data-stu-id="cd17f-176">Asynchronous Sequences for F#</span></span>](https://fsprojects.github.io/FSharp.Control.AsyncSeq/library/AsyncSeq.html)
*   [<span data-ttu-id="cd17f-177">F#データを HTTP ユーティリティ</span><span class="sxs-lookup"><span data-stu-id="cd17f-177">F# Data HTTP Utilities</span></span>](https://fsharp.github.io/FSharp.Data/library/Http.html)