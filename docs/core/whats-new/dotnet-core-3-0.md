---
title: .NET Core 3.0 の新機能
description: .NET Core 3.0 の新機能について説明します。
dev_langs:
- csharp
- vb
author: thraka
ms.author: adegeo
ms.date: 12/31/2018
ms.openlocfilehash: baaa2676865c475e331ec889e7b10ae326b552fa
ms.sourcegitcommit: b8ace47d839f943f785b89e2fff8092b0bf8f565
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "55675089"
---
# <a name="whats-new-in-net-core-30-preview-2"></a><span data-ttu-id="9eb01-103">.NET Core 3.0 (Preview 2) の新機能</span><span class="sxs-lookup"><span data-stu-id="9eb01-103">What's new in .NET Core 3.0 (Preview 2)</span></span>

<span data-ttu-id="9eb01-104">この記事では、.NET Core 3.0 (Preview 2) の新機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="9eb01-104">This article describes what is new in .NET Core 3.0 (preview 2).</span></span> <span data-ttu-id="9eb01-105">最も大きな強化点の 1 つは、Windows デスクトップ アプリケーションのサポートです (Windows のみ)。</span><span class="sxs-lookup"><span data-stu-id="9eb01-105">One of the biggest enhancements is support for Windows desktop applications (Windows only).</span></span> <span data-ttu-id="9eb01-106">Windows デスクトップという .NET Core 3.0 SDK コンポーネントを利用して、Windows フォームおよび Windows Presentation Foundation (WPF) アプリケーションを移植することができます。</span><span class="sxs-lookup"><span data-stu-id="9eb01-106">By utilizing a .NET Core 3.0 SDK component called Windows Desktop, you can port your Windows Forms and Windows Presentation Foundation (WPF) applications.</span></span> <span data-ttu-id="9eb01-107">誤解のないように言うと、Windows Desktop コンポーネントは Windows でのみサポートされており、Windows にのみ含まれています。</span><span class="sxs-lookup"><span data-stu-id="9eb01-107">To be clear, the Windows Desktop component is only supported and included on Windows.</span></span> <span data-ttu-id="9eb01-108">詳細については、以下の「[Windows デスクトップ](#windows-desktop)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9eb01-108">For more information, see the section [Windows desktop](#windows-desktop) below.</span></span>

<span data-ttu-id="9eb01-109">.NET Core 3.0 では C# 8.0 のサポートが追加されています。</span><span class="sxs-lookup"><span data-stu-id="9eb01-109">.NET Core 3.0 adds support for C# 8.0.</span></span>

<span data-ttu-id="9eb01-110">[.NET Core 3 Preview 2 を今すぐダウンロード](https://aka.ms/netcore3download)して Windows、Mac、Linux 上で使い始めましょう。</span><span class="sxs-lookup"><span data-stu-id="9eb01-110">[Download and get started with .NET Core 3 Preview 2](https://aka.ms/netcore3download) right now on Windows, Mac and Linux.</span></span> <span data-ttu-id="9eb01-111">リリースの詳細については、[.NET Core 3 Preview 2 のリリース ノート](https://aka.ms/netcore3releasenotes)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9eb01-111">You can see complete details of the release in the [.NET Core 3 Preview 2 release notes](https://aka.ms/netcore3releasenotes).</span></span>

<span data-ttu-id="9eb01-112">Preview 1 でリリースされた内容の詳細については、[.NET Core 3.0 Preview 1 の発表](https://blogs.msdn.microsoft.com/dotnet/2018/12/04/announcing-net-core-3-preview-1-and-open-sourcing-windows-desktop-frameworks/)に関する記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9eb01-112">For more information about what was released with Preview 1, see the [.NET Core 3.0 Preview 1 announcement](https://blogs.msdn.microsoft.com/dotnet/2018/12/04/announcing-net-core-3-preview-1-and-open-sourcing-windows-desktop-frameworks/).</span></span>

<span data-ttu-id="9eb01-113">Preview 2 でリリースされた内容の詳細については、[.NET Core 3.0 Preview 1 の発表]()に関する記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9eb01-113">For more information about what was released with Preview 2, see the [.NET Core 3.0 Preview 1 announcement]().</span></span>

## <a name="c-8"></a><span data-ttu-id="9eb01-114">C# 8</span><span class="sxs-lookup"><span data-stu-id="9eb01-114">C# 8</span></span>

<span data-ttu-id="9eb01-115">.NET Core 3.0 では C# 8 をサポートしており、.NET Core 3.0 Preview 2 からは、次の新機能がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="9eb01-115">.NET Core 3.0 supports C# 8, and as of .NET Core 3.0 Preview 2, supports these new features.</span></span> <span data-ttu-id="9eb01-116">C# 8.0 機能の詳細については、次のブログ記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9eb01-116">For more information about C# 8.0 features, see the following blog posts:</span></span>

- [<span data-ttu-id="9eb01-117">C# 8.0 でのパターンの有効活用</span><span class="sxs-lookup"><span data-stu-id="9eb01-117">Do more with patterns in C# 8.0</span></span>](https://blogs.msdn.microsoft.com/dotnet/2019/01/24/do-more-with-patterns-in-c-8-0/)
- [<span data-ttu-id="9eb01-118">C# 8.0 を使ってみる</span><span class="sxs-lookup"><span data-stu-id="9eb01-118">Take C# 8.0 for a spin</span></span>](https://blogs.msdn.microsoft.com/dotnet/2018/12/05/take-c-8-0-for-a-spin/)
- [<span data-ttu-id="9eb01-119">C# 8.0 のビルド</span><span class="sxs-lookup"><span data-stu-id="9eb01-119">Building C# 8.0</span></span>](https://blogs.msdn.microsoft.com/dotnet/2018/11/12/building-c-8-0/)


### <a name="ranges-and-indices"></a><span data-ttu-id="9eb01-120">範囲とインデックス</span><span class="sxs-lookup"><span data-stu-id="9eb01-120">Ranges and indices</span></span>

<span data-ttu-id="9eb01-121">新しい `Index` 型はインデックス作成に使用できます。</span><span class="sxs-lookup"><span data-stu-id="9eb01-121">The new `Index` type can be used for indexing.</span></span> <span data-ttu-id="9eb01-122">先頭からカウントする `int` か、末尾からカウントするプレフィックス `^` 演算子 (C#) を使用して作成することができます。</span><span class="sxs-lookup"><span data-stu-id="9eb01-122">You can create one from an `int` that counts from the beginning, or with a prefix `^` operator (C#) that counts from the end:</span></span>

```csharp
Index i1 = 3;  // number 3 from beginning
Index i2 = ^4; // number 4 from end
int[] a = { 0, 1, 2, 3, 4, 5, 6, 7, 8, 9 };
Console.WriteLine($"{a[i1]}, {a[i2]}"); // "3, 6"
```

<span data-ttu-id="9eb01-123">また、`Range` 型もあります。これは開始値と終了値の 2 つの `Index` 値から構成され、`x..y` の範囲式 (C#) で記述できます。</span><span class="sxs-lookup"><span data-stu-id="9eb01-123">There is also a `Range` type, which consists of two `Index` values, one for the start and one for the end, and can be written with a `x..y` range expression (C#).</span></span> <span data-ttu-id="9eb01-124">これで、スライスを生成するために `Range` を使用してインデックスを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="9eb01-124">You can then index with a `Range` in order to produce a slice:</span></span>

```csharp
var slice = a[i1..i2]; // { 3, 4, 5 }
```

### <a name="async-streams"></a><span data-ttu-id="9eb01-125">非同期ストリーム</span><span class="sxs-lookup"><span data-stu-id="9eb01-125">Async streams</span></span>

<span data-ttu-id="9eb01-126">`IAsyncEnumerable<T>` 型は、`IEnumerable<T>` の新しい非同期バージョンです。</span><span class="sxs-lookup"><span data-stu-id="9eb01-126">The `IAsyncEnumerable<T>` type is a new asynchronous version of `IEnumerable<T>`.</span></span> <span data-ttu-id="9eb01-127">この言語では、その要素を使用するために `IAsyncEnumerable<T>` よりも `await foreach` を行い、要素を生成するために `yield return` を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="9eb01-127">The language lets you `await foreach` over `IAsyncEnumerable<T>` to consume their elements, and use `yield return` to them to produce elements.</span></span>

<span data-ttu-id="9eb01-128">非同期ストリームの生成の両方の使用例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="9eb01-128">The following example demonstrates both production and consumption of async streams.</span></span> <span data-ttu-id="9eb01-129">`foreach` ステートメントは非同期であり、`yield return` を使用して呼び出し元の非同期ストリームを生成します。</span><span class="sxs-lookup"><span data-stu-id="9eb01-129">The `foreach` statement is async and itself uses `yield return` to produce an async stream for callers.</span></span> <span data-ttu-id="9eb01-130">(`yield return` を使用する) このパターンは、非同期ストリームを生成するモデルに推奨されます。</span><span class="sxs-lookup"><span data-stu-id="9eb01-130">This pattern (using `yield return`) is the recommended model for producing async streams.</span></span>

```csharp
async IAsyncEnumerable<int> GetBigResultsAsync()
{
    await foreach (var result in GetResultsAsync())
    {
        if (result > 20) yield return result; 
    }
}
```

<span data-ttu-id="9eb01-131">`await foreach` を実行できるだけでなく、非同期反復子を作成することもできます。たとえば、`await` と`yield` の両方を行うことができる `IAsyncEnumerable/IAsyncEnumerator` を返す反復子です。</span><span class="sxs-lookup"><span data-stu-id="9eb01-131">In addition to being able to `await foreach`, you can also create async iterators, for example, an iterator that returns an `IAsyncEnumerable/IAsyncEnumerator` that you can both `await` and `yield` in.</span></span> <span data-ttu-id="9eb01-132">破棄する必要があるオブジェクトの場合は、`Stream` や `Timer` など、さまざまな BCL 型が実装する `IAsyncDisposable` を使用できます。</span><span class="sxs-lookup"><span data-stu-id="9eb01-132">For objects that need to be disposed, you can use `IAsyncDisposable`, which various BCL types implement, such as `Stream` and `Timer`.</span></span>

>[!NOTE]
><span data-ttu-id="9eb01-133">Visual Studio 2019 Preview 2 または [Visual Studio Code 用の C# 拡張機能](https://github.com/OmniSharp/omnisharp-vscode/releases/tag/v1.18.0-beta5)の最新のプレビューのいずれかを使用して開発を行う場合、非同期ストリームを使用するには、NET Core 3.0 Preview 2 が必要です。</span><span class="sxs-lookup"><span data-stu-id="9eb01-133">You need .NET Core 3.0 Preview 2 to use async streams if you want to develop with either Visual Studio 2019 Preview 2 or the latest preview of the [C# extension for Visual Studio Code](https://github.com/OmniSharp/omnisharp-vscode/releases/tag/v1.18.0-beta5).</span></span> <span data-ttu-id="9eb01-134">コマンドラインで .NET Core 3.0 Preview 2 を使用する場合、すべて期待どおりに機能します。</span><span class="sxs-lookup"><span data-stu-id="9eb01-134">If you are using .NET Core 3.0 Preview 2 at the command line, then everything will work as expected.</span></span>

### <a name="using-declarations"></a><span data-ttu-id="9eb01-135">using 宣言</span><span class="sxs-lookup"><span data-stu-id="9eb01-135">Using Declarations</span></span>

<span data-ttu-id="9eb01-136">*using 宣言*は、オブジェクが適切に破棄されることを保証するための新しい方法です。</span><span class="sxs-lookup"><span data-stu-id="9eb01-136">*Using declarations* are a new way to ensure your object is properly disposed.</span></span> <span data-ttu-id="9eb01-137">*using 宣言*は、オブジェクトがスコープ内にある間は、オブジェクトをアクティブに保ちます。</span><span class="sxs-lookup"><span data-stu-id="9eb01-137">A *using declaration* keeps the object alive while it is still in scope.</span></span> <span data-ttu-id="9eb01-138">オブジェクトがスコープ外になると、そのオブジェクトは自動的に破棄されます。</span><span class="sxs-lookup"><span data-stu-id="9eb01-138">Once the object becomes out of scope, it is automatically disposed.</span></span> <span data-ttu-id="9eb01-139">これにより入れ子になった *using ステートメント*が削減され、コードが簡潔になります。</span><span class="sxs-lookup"><span data-stu-id="9eb01-139">This will reduce nested *using statements* and make your code cleaner.</span></span>

```csharp
static void Main(string[] args)
{
    using var options = Parse(args);
    if (options["verbose"]) { WriteLine("Logging..."); }

} // options disposed here
```

### <a name="switch-expressions"></a><span data-ttu-id="9eb01-140">switch 式</span><span class="sxs-lookup"><span data-stu-id="9eb01-140">Switch Expressions</span></span>

<span data-ttu-id="9eb01-141">*switch 式*は、*switch ステートメント*を実行するためのより簡潔な方法ですが、式なので値が返されます。</span><span class="sxs-lookup"><span data-stu-id="9eb01-141">*Switch expressions* are a cleaner way of doing a *switch statement* but, since it's an expression, returns a value.</span></span> <span data-ttu-id="9eb01-142">また、*switch 式*はパターン マッチングに完全に統合されており、破棄パターン `_` を使用して `default` 値を表します。</span><span class="sxs-lookup"><span data-stu-id="9eb01-142">*Switch expressions* are also fully integrated with pattern matching, and use the discard pattern, `_`, to represent the `default` value.</span></span>

<span data-ttu-id="9eb01-143">*switch 式*の構文は、次の例で確認できます。</span><span class="sxs-lookup"><span data-stu-id="9eb01-143">You can see the syntax for *switch expressions* in the following example:</span></span>

```csharp
static string Display(object o) => o switch
{
    Point { X: 0, Y: 0 }         => "origin",
    Point { X: var x, Y: var y } => $"({x}, {y})",
    _                            => "unknown"
};
```

<span data-ttu-id="9eb01-144">この例では、2 つのパターンが使われています。</span><span class="sxs-lookup"><span data-stu-id="9eb01-144">There are two patterns at play in this example.</span></span> <span data-ttu-id="9eb01-145">`o` は最初に `Point` *型パターン*と照合し、次に *{中かっこ}* 内の*プロパティ パターン*と照合します。</span><span class="sxs-lookup"><span data-stu-id="9eb01-145">`o` first matches with the `Point` *type pattern* and then with the *property pattern* inside the *{curly braces}*.</span></span> <span data-ttu-id="9eb01-146">`_` は `discard pattern` を表します。これは *switch ステートメント*の `default` と同じです。</span><span class="sxs-lookup"><span data-stu-id="9eb01-146">The `_` describes the `discard pattern`, which is the same as `default` for *switch statements*.</span></span>

<span data-ttu-id="9eb01-147">パターンを使用すると、意図のテストを実装する手続き型コードではなく、意図をキャプチャする宣言型コードを記述できます。</span><span class="sxs-lookup"><span data-stu-id="9eb01-147">Patterns enable you to write declarative code that captures your intent instead of procedural code that implements tests for it.</span></span> <span data-ttu-id="9eb01-148">コンパイラによって、面倒な手続き型コードが実装されるようになり、それが常に正しく実行されることが保証されます。</span><span class="sxs-lookup"><span data-stu-id="9eb01-148">The compiler becomes responsible for implementing that boring procedural code and is guaranteed to always do it correctly.</span></span>

<span data-ttu-id="9eb01-149">*switch 式*よりも *switch ステートメント*の方が適しているケースは今後もあり、パターンはどちらの構文スタイルでも使用できます。</span><span class="sxs-lookup"><span data-stu-id="9eb01-149">There will still be cases where *switch statements* will be a better choice than *switch expressions* and patterns can be used with both syntax styles.</span></span>

<span data-ttu-id="9eb01-150">詳細については、「[Do more with patterns in C# 8.0](https://blogs.msdn.microsoft.com/dotnet/2019/01/24/do-more-with-patterns-in-c-8-0/)」 (C# 8.0 でのパターンの有効活用) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9eb01-150">For more information, see [Do more with patterns in C# 8.0](https://blogs.msdn.microsoft.com/dotnet/2019/01/24/do-more-with-patterns-in-c-8-0/).</span></span>

## <a name="ieee-floating-point-improvements"></a><span data-ttu-id="9eb01-151">IEEE 浮動小数点の改良</span><span class="sxs-lookup"><span data-stu-id="9eb01-151">IEEE Floating-point improvements</span></span>

<span data-ttu-id="9eb01-152">浮動ポイント API は、[IEEE 754-2008 リビジョン](https://en.wikipedia.org/wiki/IEEE_754-2008_revision)に準拠するように更新中です。</span><span class="sxs-lookup"><span data-stu-id="9eb01-152">Floating point APIs are in the process of being updated to comply with [IEEE 754-2008 revision](https://en.wikipedia.org/wiki/IEEE_754-2008_revision).</span></span> <span data-ttu-id="9eb01-153">これらの変更の目的は、すべての "必要な" 操作を公開し、それらの動作が IEEE 仕様に準拠していることを保証することです。</span><span class="sxs-lookup"><span data-stu-id="9eb01-153">The goal of these changes is to expose all "required" operations and ensure that they are behaviorally compliant with the IEEE spec.</span></span>

<span data-ttu-id="9eb01-154">解析および書式設定の修正:</span><span class="sxs-lookup"><span data-stu-id="9eb01-154">Parsing and formatting fixes:</span></span>

* <span data-ttu-id="9eb01-155">任意の長さの入力を正しく解析して丸める。</span><span class="sxs-lookup"><span data-stu-id="9eb01-155">Correctly parse and round inputs of any length.</span></span>
* <span data-ttu-id="9eb01-156">負のゼロを正しく解析して書式設定する。</span><span class="sxs-lookup"><span data-stu-id="9eb01-156">Correctly parse and format negative zero.</span></span>
* <span data-ttu-id="9eb01-157">大文字と小文字を区別しないチェックを実行し、可能な場合には省略可能な先行の `+` を許可することで、無限大と NaN を正しく解析する。</span><span class="sxs-lookup"><span data-stu-id="9eb01-157">Correctly parse Infinity and NaN by performing a case-insensitive check and allowing an optional preceding `+` where applicable.</span></span>

<span data-ttu-id="9eb01-158">新しい Math API には、次のものがあります。</span><span class="sxs-lookup"><span data-stu-id="9eb01-158">New Math APIs have:</span></span>

* `BitIncrement/BitDecrement`\
<span data-ttu-id="9eb01-159">`nextUp` および `nextDown` の IEEE 演算に相当します。</span><span class="sxs-lookup"><span data-stu-id="9eb01-159">Corresponds to the `nextUp` and `nextDown` IEEE operations.</span></span> <span data-ttu-id="9eb01-160">入力よりも大きいか小さいかを比較する最小の浮動小数点をそれぞれ返します。</span><span class="sxs-lookup"><span data-stu-id="9eb01-160">They return the smallest floating-point number that compares greater or lesser than the input (respectively).</span></span> <span data-ttu-id="9eb01-161">たとえば、`Math.BitIncrement(0.0)` は `double.Epsilon` を返します。</span><span class="sxs-lookup"><span data-stu-id="9eb01-161">For example, `Math.BitIncrement(0.0)` would return `double.Epsilon`.</span></span>

* `MaxMagnitude/MinMagnitude`\
<span data-ttu-id="9eb01-162">`maxNumMag` および `minNumMag` の IEEE 演算に相当します。2 つの入力の大きさがより大きいまたはより小さい値をそれぞれ返します。</span><span class="sxs-lookup"><span data-stu-id="9eb01-162">Corresponds to the `maxNumMag` and `minNumMag` IEEE operations, they return the value that is greater or lesser in magnitude of the two inputs (respectively).</span></span> <span data-ttu-id="9eb01-163">たとえば、`Math.MaxMagnitude(2.0, -3.0)` は `-3.0` を返します。</span><span class="sxs-lookup"><span data-stu-id="9eb01-163">For example, `Math.MaxMagnitude(2.0, -3.0)` would return `-3.0`.</span></span>

* `ILogB`\
<span data-ttu-id="9eb01-164">整数値を返す `logB` IEEE 演算に相当します。入力パラメーターの 2 を底とする積分対数を返します。</span><span class="sxs-lookup"><span data-stu-id="9eb01-164">Corresponds to the `logB` IEEE operation which returns an integral value, it returns the integral base-2 log of the input parameter.</span></span> <span data-ttu-id="9eb01-165">これは実質的に `floor(log2(x))` と同じですが、最小限の丸め誤差で実行されます。</span><span class="sxs-lookup"><span data-stu-id="9eb01-165">This is effectively the same as `floor(log2(x))`, but done with minimal rounding error.</span></span>

* `ScaleB`\
<span data-ttu-id="9eb01-166">整数値を受け取る `scaleB` IEEE 演算に相当します。これは実質的に `x * pow(2, n)` と同じですが、最小限の丸め誤差で実行されます。</span><span class="sxs-lookup"><span data-stu-id="9eb01-166">Corresponds to the `scaleB` IEEE operation which takes an integral value, it returns effectively `x * pow(2, n)`, but is done with minimal rounding error.</span></span>

* `Log2`\
<span data-ttu-id="9eb01-167">`log2` IEEE 演算に相当します。2 を底とする対数を返します。</span><span class="sxs-lookup"><span data-stu-id="9eb01-167">Corresponds to the `log2` IEEE operation, it returns the base-2 logarithm.</span></span> <span data-ttu-id="9eb01-168">丸め誤差を最小限に抑えます。</span><span class="sxs-lookup"><span data-stu-id="9eb01-168">It minimizes rounding error.</span></span>

* `FusedMultiplyAdd`\
<span data-ttu-id="9eb01-169">`fma` IEEE 演算に相当します。融合型積和演算を実行します。</span><span class="sxs-lookup"><span data-stu-id="9eb01-169">Corresponds to the `fma` IEEE operation, it performs a fused multiply add.</span></span> <span data-ttu-id="9eb01-170">つまり、単一操作として `(x * y) + z` を実行することで、丸め誤差を最小限に抑えます。</span><span class="sxs-lookup"><span data-stu-id="9eb01-170">That is, it does `(x * y) + z` as a single operation, there-by minimizing the rounding error.</span></span> <span data-ttu-id="9eb01-171">例では、`FusedMultiplyAdd(1e308, 2.0, -1e308)` は `1e308` を返します。</span><span class="sxs-lookup"><span data-stu-id="9eb01-171">An example would be `FusedMultiplyAdd(1e308, 2.0, -1e308)` which returns `1e308`.</span></span> <span data-ttu-id="9eb01-172">正規の `(1e308 * 2.0) - 1e308` は `double.PositiveInfinity` を返します。</span><span class="sxs-lookup"><span data-stu-id="9eb01-172">The regular `(1e308 * 2.0) - 1e308` returns `double.PositiveInfinity`.</span></span>

* `CopySign`\
<span data-ttu-id="9eb01-173">`copySign` IEEE 演算に相当します。`x` の値を返しますが、`y` の符号と共に返されます。</span><span class="sxs-lookup"><span data-stu-id="9eb01-173">Corresponds to the `copySign` IEEE operation, it returns the value of `x`, but with the sign of `y`.</span></span>

## <a name="net-platform-dependent-intrinsics"></a><span data-ttu-id="9eb01-174">.NET プラットフォーム依存性</span><span class="sxs-lookup"><span data-stu-id="9eb01-174">.NET Platform Dependent Intrinsics</span></span>

<span data-ttu-id="9eb01-175">特定のパフォーマンス指向 CPU 命令 (**SIMD** や **ビット操作命令**セット) にアクセスできるようにする API が追加されました。</span><span class="sxs-lookup"><span data-stu-id="9eb01-175">APIs have been added that allow access to certain perf-oriented CPU instructions, such as the **SIMD** or **Bit Manipulation instruction** sets.</span></span> <span data-ttu-id="9eb01-176">これらの命令は、データを並列で効率的に処理するといった、特定のシナリオでパフォーマンスを大幅に向上するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="9eb01-176">These instructions can help achieve big performance improvements in certain scenarios, such as processing data efficiently in parallel.</span></span> <span data-ttu-id="9eb01-177">プログラムで使用する API の公開に加え、.NET ライブラリでパフォーマンスを向上させるためにこれらの命令が使用されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="9eb01-177">In addition to exposing the APIs for your programs to use, the .NET libraries have begun using these instructions to improve performance.</span></span>

<span data-ttu-id="9eb01-178">次の CoreCLR PR は、実装または使用によるいくつかの組み込みを示しています。</span><span class="sxs-lookup"><span data-stu-id="9eb01-178">The following CoreCLR PRs demonstrate a few of the intrinsics, either via implementation or use:</span></span>

* [<span data-ttu-id="9eb01-179">SSE2 ハードウェアの単純な組み込みの実装</span><span class="sxs-lookup"><span data-stu-id="9eb01-179">Implement simple SSE2 hardware intrinsics</span></span>](https://github.com/dotnet/coreclr/pull/15585)
* [<span data-ttu-id="9eb01-180">SSE ハードウェアの組み込みの実装</span><span class="sxs-lookup"><span data-stu-id="9eb01-180">Implement the SSE hardware intrinsics</span></span>](https://github.com/dotnet/coreclr/pull/15538)
* [<span data-ttu-id="9eb01-181">Arm64 ベース HW の組み込み</span><span class="sxs-lookup"><span data-stu-id="9eb01-181">Arm64 Base HW Intrinsics</span></span>](https://github.com/dotnet/coreclr/pull/16822)
* [<span data-ttu-id="9eb01-182">Locate{First|Last}Found{Byte|Char} に TZCNT と LZCNT を使用する</span><span class="sxs-lookup"><span data-stu-id="9eb01-182">Use TZCNT and LZCNT for Locate{First|Last}Found{Byte|Char}</span></span>](https://github.com/dotnet/coreclr/pull/21073)

<span data-ttu-id="9eb01-183">詳細については、[.NET プラットフォーム依存性](https://github.com/dotnet/designs/blob/master/accepted/platform-intrinsics.md)のセクションを参照してください。ここでは、このハードウェア インフラストラクチャを定義するための方法を定義して、Microsoft、チップ ベンダー、またはその他の企業や個人が、.NET コードに公開する必要があるハードウェア/チップ API を定義できるようにします。</span><span class="sxs-lookup"><span data-stu-id="9eb01-183">For more information, see [.NET Platform Dependent Intrinsics](https://github.com/dotnet/designs/blob/master/accepted/platform-intrinsics.md), which defines an approach for defining this hardware infrastructure, allowing Microsoft, chip vendors, or any other company or individual to define hardware/chip APIs that should be exposed to .NET code.</span></span>

## <a name="default-executables"></a><span data-ttu-id="9eb01-184">既定の実行可能ファイル</span><span class="sxs-lookup"><span data-stu-id="9eb01-184">Default executables</span></span>

<span data-ttu-id="9eb01-185">.NET Core では、既定で[フレームワーク依存の実行可能ファイル](../deploying/index.md#framework-dependent-executables-fde)が作成されるようになります。</span><span class="sxs-lookup"><span data-stu-id="9eb01-185">.NET Core will now build [framework-dependent executables](../deploying/index.md#framework-dependent-executables-fde) by default.</span></span> <span data-ttu-id="9eb01-186">これは、グローバルにインストールされているバージョンの .NET Core を使用するアプリケーションの新機能です。</span><span class="sxs-lookup"><span data-stu-id="9eb01-186">This is new for applications that use a globally installed version of .NET Core.</span></span> <span data-ttu-id="9eb01-187">これまでは、[自己完結型のデプロイ](../deploying/index.md#self-contained-deployments-scd)でのみ実行可能ファイルが生成されました。</span><span class="sxs-lookup"><span data-stu-id="9eb01-187">Until now, only [self-contained deployments](../deploying/index.md#self-contained-deployments-scd) would produce an executable.</span></span>

<span data-ttu-id="9eb01-188">`dotnet build` または `dotnet publish` の実行中に、使用している SDK の環境およびプラットフォームと一致する実行可能ファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="9eb01-188">During `dotnet build` or `dotnet publish`, an executable is created provided that matches the environment and platform of the SDK you are using.</span></span> <span data-ttu-id="9eb01-189">これらの実行可能ファイルでは、次のような他のネイティブ実行可能ファイルと同じことを期待できます。</span><span class="sxs-lookup"><span data-stu-id="9eb01-189">You can expect the same things with these executables as you would other native executables, such as:</span></span>

* <span data-ttu-id="9eb01-190">実行可能ファイルはダブルクリックすることができます。</span><span class="sxs-lookup"><span data-stu-id="9eb01-190">You can double-click on the executable.</span></span>
* <span data-ttu-id="9eb01-191">Windows では `myapp.exe`、Linux と macOS では`./myapp` など、コマンド プロンプトからアプリケーションを直接起動できます。</span><span class="sxs-lookup"><span data-stu-id="9eb01-191">You can launch the application from a command prompt directly, such as `myapp.exe` on Windows, and `./myapp` on Linux and macOS.</span></span>

## <a name="build-copies-dependencies"></a><span data-ttu-id="9eb01-192">ビルドによる依存関係のコピー</span><span class="sxs-lookup"><span data-stu-id="9eb01-192">Build copies dependencies</span></span>

<span data-ttu-id="9eb01-193">`dotnet build` で、アプリケーションの NuGet 依存関係が NuGet キャッシュからビルド出力フォルダーにコピーされるようになりました。</span><span class="sxs-lookup"><span data-stu-id="9eb01-193">`dotnet build` now copies NuGet dependencies for your application from the NuGet cache to the build output folder.</span></span> <span data-ttu-id="9eb01-194">以前は、依存関係のコピーは `dotnet publish` の一部としてのみ行われていました。</span><span class="sxs-lookup"><span data-stu-id="9eb01-194">Previously, dependencies were only copied as part of `dotnet publish`.</span></span> 

<span data-ttu-id="9eb01-195">リンクや razor ページの発行など、まだ発行が必要な操作がいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="9eb01-195">There are some operations, like linking and razor page publishing that will still require publishing.</span></span>


## <a name="local-dotnet-tools"></a><span data-ttu-id="9eb01-196">ローカルの dotnet ツール</span><span class="sxs-lookup"><span data-stu-id="9eb01-196">Local dotnet tools</span></span>

>[!WARNING]
><span data-ttu-id="9eb01-197">.NET Core のローカル ツールは、.NET Core 3.0 Preview 1 と .NET Core 3.0 Preview 2 の間で変更されました。</span><span class="sxs-lookup"><span data-stu-id="9eb01-197">There was a change in .NET Core Local Tools between .NET Core 3.0 Preview 1 and .NET Core 3.0 Preview 2.</span></span>  <span data-ttu-id="9eb01-198">`dotnet tool restore` や `dotnet tool install` のようなコマンドを実行して、Preview 1 でローカル ツールを試した場合は、Preview 2 でローカル ツールが正しく動作するためには、事前にローカル ツールのキャッシュ フォルダーを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9eb01-198">If you tried out local tools in Preview 1 by running a command like `dotnet tool restore` or `dotnet tool install`, you need to delete your local tools cache folder before local tools will work correctly in Preview 2.</span></span> <span data-ttu-id="9eb01-199">このフォルダーは次の場所にあります。</span><span class="sxs-lookup"><span data-stu-id="9eb01-199">This folder is located at:</span></span>
>
><span data-ttu-id="9eb01-200">Mac、Linux の場合: `rm -r $HOME/.dotnet/toolResolverCache`</span><span class="sxs-lookup"><span data-stu-id="9eb01-200">On mac, Linux: `rm -r $HOME/.dotnet/toolResolverCache`</span></span>
>
><span data-ttu-id="9eb01-201">Windows の場合: `rmdir /s %USERPROFILE%\.dotnet\toolResolverCache`</span><span class="sxs-lookup"><span data-stu-id="9eb01-201">On Windows: `rmdir /s %USERPROFILE%\.dotnet\toolResolverCache`</span></span>
>
><span data-ttu-id="9eb01-202">このフォルダーを削除しないと、エラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9eb01-202">If you do not delete this folder, you will receive an error.</span></span>

<span data-ttu-id="9eb01-203">.NET Core 2.1 はグローバル ツールをサポートしていましたが、.NET Core 3.0 にはローカル ツールが追加されました。</span><span class="sxs-lookup"><span data-stu-id="9eb01-203">While .NET Core 2.1 supported global tools, .NET Core 3.0 now has local tools.</span></span> <span data-ttu-id="9eb01-204">ローカル ツールはグローバル ツールに似ていますが、ディスク上の特定の場所に関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="9eb01-204">Local tools are similar to global tools but are associated with a particular location on disk.</span></span> <span data-ttu-id="9eb01-205">これで、プロジェクト単位およびリポジトリ単位のツールが可能になります。</span><span class="sxs-lookup"><span data-stu-id="9eb01-205">This enables per-project and per-repository tooling.</span></span> <span data-ttu-id="9eb01-206">ローカルにインストールされたツールはいずれも、グローバルでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="9eb01-206">Any tool installed locally isn't available globally.</span></span> <span data-ttu-id="9eb01-207">ツールは、NuGet パッケージとして配布されます。</span><span class="sxs-lookup"><span data-stu-id="9eb01-207">Tools are distributed as NuGet packages.</span></span>

<span data-ttu-id="9eb01-208">ローカル ツールは、現在のディレクトリ内のマニフェスト ファイル名 `dotnet-tools.json` に依存しています。</span><span class="sxs-lookup"><span data-stu-id="9eb01-208">Local tools rely on a manifest file name `dotnet-tools.json` in your current directory.</span></span> <span data-ttu-id="9eb01-209">このマニフェスト ファイルは、ツールをそのフォルダー下で使用できるように定義します。</span><span class="sxs-lookup"><span data-stu-id="9eb01-209">This manifest file defines the tools to be available at that folder and below.</span></span> <span data-ttu-id="9eb01-210">リポジトリのルートにこのマニフェスト ファイルを作成することで、コードを複製したすべての人が、コードを正常に処理するために必要なツールを復元し、使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="9eb01-210">By creating this manifest file at the root of your repository, you ensure anyone cloning your code can restore and use the tools that are needed to successfully work with your code.</span></span>

<span data-ttu-id="9eb01-211">`dotnet-tools.json` マニフェスト ファイルを作成するには、次を使用します。</span><span class="sxs-lookup"><span data-stu-id="9eb01-211">To create a `dotnet-tools.json` manifest file, use:</span></span>

```console
dotnet new tool-manifest
```

<span data-ttu-id="9eb01-212">次を使用してローカル マニフェストに新しいツールを追加します。</span><span class="sxs-lookup"><span data-stu-id="9eb01-212">Add a new tool to the local manifest with:</span></span>

```console
dotnet tool install <packageId>
```

<span data-ttu-id="9eb01-213">次を使用してローカル マニフェストに含まれるツールの一覧を表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="9eb01-213">You can also list the tools in the local manifest with:</span></span>

```console
dotnet tool list
```

<span data-ttu-id="9eb01-214">どのようなツールがグローバルにインストールされているかを表示するには、次を使用します。</span><span class="sxs-lookup"><span data-stu-id="9eb01-214">To see what tools are installed globally, use:</span></span>

```console
dotnet tool list -g
```

<span data-ttu-id="9eb01-215">ローカル ツール マニフェスト ファイルは使用できるが、マニフェストで定義されたツールがインストールされていない場合は、次のコマンドを使用して、自動的にこれらのツールをダウンロードしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="9eb01-215">When the local tools manifest file is available, but the tools defined in the manifest have not been installed, use the following command to automatically download and install those tools:</span></span>

```console
dotnet tool restore
```

<span data-ttu-id="9eb01-216">次のコマンドでローカル ツールを実行します。</span><span class="sxs-lookup"><span data-stu-id="9eb01-216">Run a local tool with the following command:</span></span>

```console
dotnet tool run <tool-command-name>
```

<span data-ttu-id="9eb01-217">ローカル ツールが実行されると、dotnet で現在のディレクトリ構造内のマニフェストが検索されます。</span><span class="sxs-lookup"><span data-stu-id="9eb01-217">When a local tool is run, dotnet searches for a manifest up the current directory structure.</span></span> <span data-ttu-id="9eb01-218">ツール マニフェスト ファイルが見つかると、要求されたツールが検索されます。</span><span class="sxs-lookup"><span data-stu-id="9eb01-218">When a tool manifest file is found, it is searched for the requested tool.</span></span> <span data-ttu-id="9eb01-219">キャッシュではなくマニフェスト内にツールが見つかった場合は、エラーが表示され、ユーザーは `dotnet tool restore` を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9eb01-219">If the tool is found in the manifest, but not the cache, the user receives an error and needs to run `dotnet tool restore`.</span></span>

<span data-ttu-id="9eb01-220">ローカル ツール マニフェスト ファイルからツールを削除するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="9eb01-220">To remove a tool from the local tool manifest file, run the following command:</span></span>

```console
dotnet tool uninstall <packageId>
```

<span data-ttu-id="9eb01-221">ツール マニフェスト ファイルは、手動で編集できるように設計されています。そのため、リポジトリを操作するために必要なバージョンを更新することができます。</span><span class="sxs-lookup"><span data-stu-id="9eb01-221">The tool manifest file is designed to allow hand editing – which you might do to update the required version for working with the repository.</span></span> <span data-ttu-id="9eb01-222">`dotnet-tools.json` ファイルの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="9eb01-222">Here is an example `dotnet-tools.json` file:</span></span>

```json
{
  "version": 1,
  "isRoot": true,
  "tools": {
    "dotnetsay": {
      "version": "2.1.4",
      "commands": [
        "dotnetsay"
      ]
    },
    "t-rex": {
      "version": "1.0.103",
      "commands": [
        "t-rex"
      ]
    }
  }
}
```

<span data-ttu-id="9eb01-223">グローバル ツールとローカル ツールの両方で、ランタイムの互換バージョンが必要です。</span><span class="sxs-lookup"><span data-stu-id="9eb01-223">For both global and local tools, a compatible version of the runtime is required.</span></span> <span data-ttu-id="9eb01-224">現在 NuGet.org 上にある多くのツールは、.NET Core Runtime 2.1 をターゲットとしています。</span><span class="sxs-lookup"><span data-stu-id="9eb01-224">Many tools currently on NuGet.org target .NET Core Runtime 2.1.</span></span> <span data-ttu-id="9eb01-225">グローバルにまたはローカルにそれらをインストールするには、[NET Core 2.1 ランタイム](https://dotnet.microsoft.com/download/dotnet-core/2.1)をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9eb01-225">To install those globally or locally, you would still need to install the [NET Core 2.1 Runtime](https://dotnet.microsoft.com/download/dotnet-core/2.1).</span></span>

## <a name="windows-desktop"></a><span data-ttu-id="9eb01-226">Windows デスクトップ</span><span class="sxs-lookup"><span data-stu-id="9eb01-226">Windows desktop</span></span>

<span data-ttu-id="9eb01-227">.NET Core 3.0 Preview 1 以降では、WPF および Windows フォームを使用して Windows デスクトップ アプリケーションを構築できます。</span><span class="sxs-lookup"><span data-stu-id="9eb01-227">Starting with .NET Core 3.0 Preview 1, you can build Windows desktop applications using WPF and Windows Forms.</span></span> <span data-ttu-id="9eb01-228">これらのフレームワークでは、Windows UI XAML ライブラリ (WinUI) の最新のコントロールと Fluent スタイルを [XAML Islands](/windows/uwp/xaml-platform/xaml-host-controls) 経由で使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="9eb01-228">These frameworks also support using modern controls and Fluent styling from the Windows UI XAML Library (WinUI) via [XAML islands](/windows/uwp/xaml-platform/xaml-host-controls).</span></span>

<span data-ttu-id="9eb01-229">Windows デスクトップ コンポーネントは、Windows .NET Core 3.0 SDK の一部です。</span><span class="sxs-lookup"><span data-stu-id="9eb01-229">The Windows Desktop component is part of the Windows .NET Core 3.0 SDK.</span></span>

<span data-ttu-id="9eb01-230">次の `dotnet` コマンドを使用して、新しい WPF または Windows フォーム アプリケーションを作成できます。</span><span class="sxs-lookup"><span data-stu-id="9eb01-230">You can create a new WPF or Windows Forms app with the following `dotnet` commands:</span></span>

```console
dotnet new wpf
dotnet new winforms
```

<span data-ttu-id="9eb01-231">Visual Studio 2019 Preview 2 では、.NET Core 3.0 Windows フォームと WPF 用に、**新しいプロジェクト** テンプレートが追加されました。</span><span class="sxs-lookup"><span data-stu-id="9eb01-231">Visual Studio 2019 Preview 2 adds **New Project** templates for .NET Core 3.0 Windows Forms and WPF.</span></span> <span data-ttu-id="9eb01-232">デザイナーは、まだサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="9eb01-232">Designers are still not yet supported.</span></span> <span data-ttu-id="9eb01-233">また、これらのプロジェクトは、Visual Studio 2019 で開いたり、起動したり、デバッグしたりすることができます。</span><span class="sxs-lookup"><span data-stu-id="9eb01-233">And you can open, launch, and debug these projects in Visual Studio 2019.</span></span>

<span data-ttu-id="9eb01-234">Visual Studio 2017 15.9 では、[.NET Core のプレビューを有効にする](https://blogs.msdn.microsoft.com/dotnet/2018/11/13/net-core-tooling-update-for-visual-studio-2017-version-15-9/)機能が追加されていますが、この機能をオンにする必要があり、これはサポートされているシナリオではありません。</span><span class="sxs-lookup"><span data-stu-id="9eb01-234">Visual Studio 2017 15.9 adds the ability to [enable .NET Core previews](https://blogs.msdn.microsoft.com/dotnet/2018/11/13/net-core-tooling-update-for-visual-studio-2017-version-15-9/), but you need to turn that feature on, and it's not a supported scenario.</span></span>

<span data-ttu-id="9eb01-235">新しいプロジェクトは既存の .NET Core プロジェクトと同じですが、いくつかの追加もあります。</span><span class="sxs-lookup"><span data-stu-id="9eb01-235">The new projects are the same as existing .NET Core projects, with a couple additions.</span></span> <span data-ttu-id="9eb01-236">基本的な .NET Core コンソール プロジェクトと基本的な Windows フォームおよび WPF プロジェクトとの比較を次に示します。</span><span class="sxs-lookup"><span data-stu-id="9eb01-236">Here is the comparison of the basic .NET Core console project and a basic Windows Forms and WPF project.</span></span>

<span data-ttu-id="9eb01-237">.NET Core コンソール プロジェクトでは、`Microsoft.NET.Sdk` SDK が使用され、`netcoreapp3.0` ターゲット フレームワークを介して .NET Core 3.0 への依存関係が宣言されます。</span><span class="sxs-lookup"><span data-stu-id="9eb01-237">In a .NET Core console project, the project uses the `Microsoft.NET.Sdk` SDK and declares a dependency on .NET Core 3.0 via the `netcoreapp3.0` target framework.</span></span> <span data-ttu-id="9eb01-238">Windows デスクトップ アプリを作成するには、`Microsoft.NET.Sdk.WindowsDesktop` SDK を使用し、使用する UI フレームワークを選択します。</span><span class="sxs-lookup"><span data-stu-id="9eb01-238">To create a Windows Desktop app, use the `Microsoft.NET.Sdk.WindowsDesktop` SDK and choose which UI framework to use:</span></span>

```diff
-<Project Sdk="Microsoft.NET.Sdk">
+<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp3.0</TargetFramework>
+   <UseWPF>true</UseWPF>
  </PropertyGroup>
</Project>
```

<span data-ttu-id="9eb01-239">WPF でなく Windows フォームを選択するには、`UseWPF` の代わりに `UseWindowsForms` を設定します。</span><span class="sxs-lookup"><span data-stu-id="9eb01-239">To choose Windows Forms over WPF, set `UseWindowsForms` instead of `UseWPF`:</span></span>

```diff
<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp3.0</TargetFramework>
-   <UseWPF>true</UseWPF>
+   <UseWindowsForms>true</UseWindowsForms>
  </PropertyGroup>
</Project>
```

<span data-ttu-id="9eb01-240">Windows フォーム ダイアログが WPF コントロールをホストしている場合など、アプリが両方のフレームワークを使用する場合は、`UseWPF` および `UseWindowsForms` の両方を `true` に設定できます。</span><span class="sxs-lookup"><span data-stu-id="9eb01-240">Both `UseWPF` and `UseWindowsForms` can be set to `true` if the app uses both frameworks, for example when a Windows Forms dialog is hosting a WPF control.</span></span>

<span data-ttu-id="9eb01-241">[dotnet/winforms](https://github.com/dotnet/winforms/issues)、[dotnet/wpf](https://github.com/dotnet/wpf/issues)、[dotnet/core](https://github.com/dotnet/core/issues) リポジトリに関するフィードバックをお寄せください。</span><span class="sxs-lookup"><span data-stu-id="9eb01-241">Please share your feedback on the [dotnet/winforms](https://github.com/dotnet/winforms/issues),  [dotnet/wpf](https://github.com/dotnet/wpf/issues) and [dotnet/core](https://github.com/dotnet/core/issues) repos.</span></span>

## <a name="msix-deployment-for-windows-desktop"></a><span data-ttu-id="9eb01-242">Windows Desktop への MSIX の展開</span><span class="sxs-lookup"><span data-stu-id="9eb01-242">MSIX Deployment for Windows Desktop</span></span>

<span data-ttu-id="9eb01-243">[MSIX](https://docs.microsoft.com/windows/msix/) は Windows アプリの新しいパッケージ形式です。</span><span class="sxs-lookup"><span data-stu-id="9eb01-243">[MSIX](https://docs.microsoft.com/windows/msix/) is a new Windows app package format.</span></span> <span data-ttu-id="9eb01-244">これは、Windows 10 に .NET Core 3.0 のデスクトップ アプリケーションを展開するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="9eb01-244">It can be used to deploy .NET Core 3.0 desktop applications to Windows 10.</span></span>

<span data-ttu-id="9eb01-245">[Windows アプリケーション パッケージ プロジェクト](https://docs.microsoft.com/windows/uwp/porting/desktop-to-uwp-packaging-dot-net)は、Visual Studio 2019 Preview 2 で使用でき、[自己完結型](../deploying/#self-contained-deployments-scd)の .NET Core アプリケーションを使用して、MSIX パッケージを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="9eb01-245">The [Windows Application Packaging Project](https://docs.microsoft.com/windows/uwp/porting/desktop-to-uwp-packaging-dot-net), available in Visual Studio 2019 Preview 2, allows you to create MSIX packages with [self-contained](../deploying/#self-contained-deployments-scd) .NET Core applications.</span></span>

><span data-ttu-id="9eb01-246">メモ:.NET Core プロジェクト ファイルの `<RuntimeIdentifiers>` プロパティで、サポートされているランタイムを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9eb01-246">Note: The .NET Core project file must specify the supported runtimes in the `<RuntimeIdentifiers>` property:</span></span>
```xml
<RuntimeIdentifiers>win-x86;win-x64</RuntimeIdentifiers>
```

## <a name="fast-built-in-json-support"></a><span data-ttu-id="9eb01-247">高速な組み込み JSON のサポート</span><span class="sxs-lookup"><span data-stu-id="9eb01-247">Fast built-in JSON support</span></span>

<span data-ttu-id="9eb01-248">.NET エコシステムは、[**Json.NET**](https://www.newtonsoft.com/json) や他のよく使われている JSON ライブラリに依存しています。これは今後も推奨されます。</span><span class="sxs-lookup"><span data-stu-id="9eb01-248">The .NET ecosystem has relied on [**Json.NET**](https://www.newtonsoft.com/json) and other popular JSON libraries, which continue to be good choices.</span></span> <span data-ttu-id="9eb01-249">**Json.NET** では .NET の文字列が基本のデータ型 (内部的には UTF-16) として使用されます。</span><span class="sxs-lookup"><span data-stu-id="9eb01-249">**Json.NET** uses .NET strings as its base datatype, which are UTF-16 under the hood.</span></span>

<span data-ttu-id="9eb01-250">新しい組み込みの JSON サポートは、高パフォーマンス、低割り当てで、`Span<byte>` に基づいています。</span><span class="sxs-lookup"><span data-stu-id="9eb01-250">The new built-in JSON support is high-performance, low allocation, and based on `Span<byte>`.</span></span> <span data-ttu-id="9eb01-251">3 つの新しい JSON 関連の主な型が、.NET Core 3.0 の `System.Text.Json` 名前空間に追加されました。</span><span class="sxs-lookup"><span data-stu-id="9eb01-251">Three new main JSON-related types have been added to .NET Core 3.0 the `System.Text.Json` namespace.</span></span>

### <a name="utf8jsonreader"></a><span data-ttu-id="9eb01-252">Utf8JsonReader</span><span class="sxs-lookup"><span data-stu-id="9eb01-252">Utf8JsonReader</span></span>

<span data-ttu-id="9eb01-253">`System.Text.Json.Utf8JsonReader` は、UTF-8 でエンコードされた JSON テキスト用の高パフォーマンス、低割り当て、転送のみのリーダーです。`ReadOnlySpan<byte>` から読み取られます。</span><span class="sxs-lookup"><span data-stu-id="9eb01-253">`System.Text.Json.Utf8JsonReader` is a high-performance, low allocation, forward-only reader for UTF-8 encoded JSON text, read from a `ReadOnlySpan<byte>`.</span></span> <span data-ttu-id="9eb01-254">`Utf8JsonReader` は基本的で低レベルの型であり、カスタム パーサーとデシリアライザーを構築するために利用できます。</span><span class="sxs-lookup"><span data-stu-id="9eb01-254">The `Utf8JsonReader` is a foundational, low-level type, that can be leveraged to build custom parsers and deserializers.</span></span> <span data-ttu-id="9eb01-255">新しい `Utf8JsonReader` を使用して JSON ペイロードを読み取る処理は、**Json.NET** のリーダーを使用する場合より 2 倍高速です。</span><span class="sxs-lookup"><span data-stu-id="9eb01-255">Reading through a JSON payload using the new `Utf8JsonReader` is 2x faster than using the reader from **Json.NET**.</span></span> <span data-ttu-id="9eb01-256">JSON トークンを (UTF-16) 文字列として実現する必要が出てくるまでは割り当てられません。</span><span class="sxs-lookup"><span data-stu-id="9eb01-256">It does not allocate until you need to actualize JSON tokens as (UTF-16) strings.</span></span>

<span data-ttu-id="9eb01-257">この新しい API には、次のコンポーネントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="9eb01-257">This new API will include the following components:</span></span>

* <span data-ttu-id="9eb01-258">Preview 1:JSON リーダー (シーケンシャル アクセス)</span><span class="sxs-lookup"><span data-stu-id="9eb01-258">In Preview 1: JSON reader (sequential access)</span></span>
* <span data-ttu-id="9eb01-259">次の予定:JSON ライター、DOM (ランダム アクセス)、poco シリアライザー、poco デシリアライザー</span><span class="sxs-lookup"><span data-stu-id="9eb01-259">Coming next: JSON writer, DOM (random access), poco serializer, poco deserializer</span></span>

<span data-ttu-id="9eb01-260">出発点として使用できる `Utf8JsonReader` の基本的なリーダー ループを次に示します。</span><span class="sxs-lookup"><span data-stu-id="9eb01-260">Here is the basic reader loop for the `Utf8JsonReader` that can be used as a starting point:</span></span>

```csharp
using System.Text.Json;

public static void Utf8JsonReaderLoop(ReadOnlySpan<byte> dataUtf8)
{
    var json = new Utf8JsonReader(dataUtf8, isFinalBlock: true, state: default);

    while (json.Read())
    {
        JsonTokenType tokenType = json.TokenType;
        ReadOnlySpan<byte> valueSpan = json.ValueSpan;
        switch (tokenType)
        {
            case JsonTokenType.StartObject:
            case JsonTokenType.EndObject:
                break;
            case JsonTokenType.StartArray:
            case JsonTokenType.EndArray:
                break;
            case JsonTokenType.PropertyName:
                break;
            case JsonTokenType.String:
                string valueString = json.GetStringValue();
                break;
            case JsonTokenType.Number:
                if (!json.TryGetInt32Value(out int valueInteger))
                {
                    throw new FormatException();
                }
                break;
            case JsonTokenType.True:
            case JsonTokenType.False:
                bool valueBool = json.GetBooleanValue();
                break;
            case JsonTokenType.Null:
                break;
            default:
                throw new ArgumentException();
        }
    }

    dataUtf8 = dataUtf8.Slice((int)json.BytesConsumed);
    JsonReaderState state = json.CurrentState;
}
```

### <a name="utf8jsonwriter"></a><span data-ttu-id="9eb01-261">Utf8JsonWriter</span><span class="sxs-lookup"><span data-stu-id="9eb01-261">Utf8JsonWriter</span></span>

<span data-ttu-id="9eb01-262">`System.Text.Json.Utf8JsonWriter` は、`String`、`Int32`、`DateTime` のような一般的な.NET 型から UTF-8 でエンコードされた JSON テキストを書き込むための、ハイパフォーマンス、非キャッシュ、前方参照専用の方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="9eb01-262">`System.Text.Json.Utf8JsonWriter` provides a high-performance, non-cached, forward-only way to write UTF-8 encoded JSON text from common .NET types like `String`, `Int32`, and `DateTime`.</span></span> <span data-ttu-id="9eb01-263">リーダーと同様に、ライターは基本的で低レベルの型であり、カスタム シリアライザーを構築するために利用できます。</span><span class="sxs-lookup"><span data-stu-id="9eb01-263">Like the reader, the writer is a foundational, low-level type, that can be leveraged to build custom serializers.</span></span> <span data-ttu-id="9eb01-264">新しい `Utf8JsonWriter` を使用して JSON ペイロードを書き込むと、**Json.NET** からライターを使用するよりも 30 - 80% 高速になり、割り当てが行われません。</span><span class="sxs-lookup"><span data-stu-id="9eb01-264">Writing a JSON payload using the new `Utf8JsonWriter` is 30-80% faster than using the writer from **Json.NET** and does not allocate.</span></span>

<span data-ttu-id="9eb01-265">出発点として使用できる `Utf8JsonWriter` の使用例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="9eb01-265">Here is a sample usage of the `Utf8JsonWriter` that can be used as a starting point:</span></span>

```csharp
static int WriteJson(IBufferWriter<byte> output, long[] extraData)
{
    var json = new Utf8JsonWriter(output, state: default);

    json.WriteStartObject();

    json.WriteNumber("age", 15, escape: false);
    json.WriteString("date", DateTime.Now);
    json.WriteString("first", "John");
    json.WriteString("last", "Smith");

    json.WriteStartArray("phoneNumbers", escape: false);
    json.WriteStringValue("425-000-1212", escape: false);
    json.WriteStringValue("425-000-1213");
    json.WriteEndArray();

    json.WriteStartObject("address");
    json.WriteString("street", "1 Microsoft Way");
    json.WriteString("city", "Redmond");
    json.WriteNumber("zip", 98052);
    json.WriteEndObject();

    json.WriteStartArray("ExtraArray");
    for (var i = 0; i < extraData.Length; i++)
    {
        json.WriteNumberValue(extraData[i]);
    }
    json.WriteEndArray();

    json.WriteEndObject();

    json.Flush(isFinalBlock: true);

    return (int)json.BytesWritten;
}
```

<span data-ttu-id="9eb01-266">`Utf8JsonWriter` は、json データを同期的に書き込む出力場所として `IBufferWriter<byte>` を受け入れ、呼び出し元のユーザーは具象実装を提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9eb01-266">The `Utf8JsonWriter` accepts `IBufferWriter<byte>` as the output location to synchronously write the json data into, and you as the caller need to provide a concrete implementation.</span></span> <span data-ttu-id="9eb01-267">プラットフォームには現在、このインターフェイスの実装が含まれていません。</span><span class="sxs-lookup"><span data-stu-id="9eb01-267">The platform does not currently include an implementation of this interface.</span></span> <span data-ttu-id="9eb01-268">`IBufferWriter<byte>` の例については、[https://gist.github.com/ahsonkhan/c76a1cc4dc7107537c3fdc0079a68b35](https://gist.github.com/ahsonkhan/c76a1cc4dc7107537c3fdc0079a68b35) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9eb01-268">For an example of `IBufferWriter<byte>`, see [https://gist.github.com/ahsonkhan/c76a1cc4dc7107537c3fdc0079a68b35](https://gist.github.com/ahsonkhan/c76a1cc4dc7107537c3fdc0079a68b35)</span></span>

### <a name="jsondocument"></a><span data-ttu-id="9eb01-269">JsonDocument</span><span class="sxs-lookup"><span data-stu-id="9eb01-269">JsonDocument</span></span>

<span data-ttu-id="9eb01-270">`System.Text.Json.JsonDocument` は、`Utf8JsonReader` に基づいています。</span><span class="sxs-lookup"><span data-stu-id="9eb01-270">`System.Text.Json.JsonDocument` is built on top of the `Utf8JsonReader`.</span></span> <span data-ttu-id="9eb01-271">`JsonDocument` は、JSON データを解析し、ランダム アクセスと列挙型をサポートするためにクエリできる読み取り専用ドキュメント オブジェクト モデル (DOM) をビルドする機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="9eb01-271">The `JsonDocument` provides the ability to parse JSON data and build a read-only Document Object Model (DOM) that can be queried to support random access and enumeration.</span></span> <span data-ttu-id="9eb01-272">データを作成する JSON 要素には、`RootElement` というプロパティとして `JsonDocument` によって公開される `JsonElement` 型を使用してアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="9eb01-272">The JSON elements that compose the data can be accessed via the `JsonElement` type which is exposed by the `JsonDocument` as a property called `RootElement`.</span></span> <span data-ttu-id="9eb01-273">`JsonElement` には、JSON 配列とオブジェクト列挙子とともに、JSON テキストを一般的な .NET 型に変換する API が含まれています。</span><span class="sxs-lookup"><span data-stu-id="9eb01-273">The `JsonElement` contains the JSON array and object enumerators along with APIs to convert JSON text to common .NET types.</span></span> <span data-ttu-id="9eb01-274">一般的な JSON ペイロードを解析し、`JsonDocument` を使用してそのメンバーすべてにアクセスすると、適度にサイズ指定された (つまり 1 MB 未満) データに対する割り当てがごくわずかしかない **Json.NET** よりも 2 - 3 倍高速になります。</span><span class="sxs-lookup"><span data-stu-id="9eb01-274">Parsing a typical JSON payload and accessing all its members using the `JsonDocument` is 2-3x faster than **Json.NET** with very little allocations for data that is reasonably sized (i.e. < 1 MB).</span></span>

<span data-ttu-id="9eb01-275">出発点として使用できる `JsonDocument` および `JsonElement` の使用例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="9eb01-275">Here is a sample usage of the `JsonDocument` and `JsonElement` that can be used as a starting point:</span></span>

```csharp
static double ParseJson()
{
    const string json = " [ { \"name\": \"John\" }, [ \"425-000-1212\", 15 ], { \"grades\": [ 90, 80, 100, 75 ] } ]";

    double average = -1;

    using (JsonDocument doc = JsonDocument.Parse(json))
    {
        JsonElement root = doc.RootElement;
        JsonElement info = root[1];

        string phoneNumber = info[0].GetString();
        int age = info[1].GetInt32();

        JsonElement grades = root[2].GetProperty("grades");

        double sum = 0;
        foreach (JsonElement grade in grades.EnumerateArray())
        {
            sum += grade.GetInt32();
        }

        int numberOfCourses = grades.GetArrayLength();
        average = sum / numberOfCourses;
    }

    return average;
}
```

## <a name="assembly-unloadability"></a><span data-ttu-id="9eb01-276">アセンブリのアンローダビリティ</span><span class="sxs-lookup"><span data-stu-id="9eb01-276">Assembly Unloadability</span></span>

<span data-ttu-id="9eb01-277">アセンブリのアンローダビリティは、`AssemblyLoadContext` の新機能です。</span><span class="sxs-lookup"><span data-stu-id="9eb01-277">Assembly unloadability is a new capability of `AssemblyLoadContext`.</span></span> <span data-ttu-id="9eb01-278">この新機能は、API の観点からはきわめて透過的で、いくつかの新しい API で公開されます。</span><span class="sxs-lookup"><span data-stu-id="9eb01-278">This new feature is largely transparent from an API perspective, exposed with just a few new APIs.</span></span> <span data-ttu-id="9eb01-279">これによりローダー コンテキストをアンロードできるようにして、インスタンス化された型、静的フィールド、およびアセンブリ自体に対してすべてのメモリを解放します。</span><span class="sxs-lookup"><span data-stu-id="9eb01-279">It enables a loader context to be unloaded, releasing all memory for instantiated types, static fields and for the assembly itself.</span></span> <span data-ttu-id="9eb01-280">メモリ リークが発生することなく、アプリケーションは、このメカニズムを使用して永遠にアセンブリを読み込みおよびアンロードできる必要があります。</span><span class="sxs-lookup"><span data-stu-id="9eb01-280">An application should be able to load and unload assemblies via this mechanism forever without experiencing a memory leak.</span></span>

<span data-ttu-id="9eb01-281">この新機能は、次のようなシナリオに使用できます。</span><span class="sxs-lookup"><span data-stu-id="9eb01-281">This new capability can be used for scenarios similar to:</span></span>

* <span data-ttu-id="9eb01-282">動的プラグインの読み込みとアンロードが必要なプラグイン シナリオ。</span><span class="sxs-lookup"><span data-stu-id="9eb01-282">Plugin scenarios where dynamic plugin loading and unloading is required.</span></span> 
* <span data-ttu-id="9eb01-283">コードを動的にコンパイルし、実行し、フラッシュする。</span><span class="sxs-lookup"><span data-stu-id="9eb01-283">Dynamically compiling, running and then flushing code.</span></span> <span data-ttu-id="9eb01-284">Web サイト、スクリプト エンジンなどに便利。</span><span class="sxs-lookup"><span data-stu-id="9eb01-284">Useful for web sites, scripting engines, etc.</span></span>
* <span data-ttu-id="9eb01-285">イントロスペクション (ReflectionOnlyLoad など) のアセンブリの読み込み。ただし多くの場合、(Preview 1 でリリースされた) [MetadataLoadContext](#type-metadataloadcontext) の方が適しています。</span><span class="sxs-lookup"><span data-stu-id="9eb01-285">Loading assemblies for introspection (like ReflectionOnlyLoad), although [MetadataLoadContext](#type-metadataloadcontext) (released in Preview 1) will be a better choice in many cases.</span></span>

<span data-ttu-id="9eb01-286">詳細については、[アンローダビリティの使用](https://github.com/dotnet/coreclr/pull/22221)に関するドキュメントをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="9eb01-286">For more information, see the [Using Unloadability](https://github.com/dotnet/coreclr/pull/22221) document.</span></span>

<span data-ttu-id="9eb01-287">アセンブリのアンロードには、ローダー コンテキストの外部からマネージド オブジェクトへのすべての参照が理解され、管理されるようにするため、細心の注意が必要です。</span><span class="sxs-lookup"><span data-stu-id="9eb01-287">Assembly unloading requires significant care to ensure that all references to managed objects from outside a loader context are understood and managed.</span></span> <span data-ttu-id="9eb01-288">ローダー コンテキストがアンロードされるように要求されると、ローダー コンテキストがそれ自体に対してのみ自己矛盾がないように、すべての外部参照が参照解除されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="9eb01-288">When the loader context is requested to be unloaded, any outside references need to have been unreferenced so that the loader context is self-consistent only to itself.</span></span>

<span data-ttu-id="9eb01-289">アセンブリのアンローダビリティは、.NET Core でサポートされていないアプリケーション ドメイン (AppDomains) によって、.NET Framework で提供されました。</span><span class="sxs-lookup"><span data-stu-id="9eb01-289">Assembly unloadability was provided in the .NET Framework by Application Domains (AppDomains), which are not supported with .NET Core.</span></span> <span data-ttu-id="9eb01-290">この新しいモデルと比べて、AppDomains には利点と制限事項がありました。</span><span class="sxs-lookup"><span data-stu-id="9eb01-290">AppDomains had both benefits and limitations compared to this new model.</span></span> <span data-ttu-id="9eb01-291">AppDomains と比べて、この新しいローダー モデルがより柔軟で高いパフォーマンスになるように検討します。</span><span class="sxs-lookup"><span data-stu-id="9eb01-291">Consider this new loader model to be more flexible and higher performant when compared to AppDomains.</span></span>

## <a name="windows-native-interop"></a><span data-ttu-id="9eb01-292">Windows のネイティブ相互運用機能</span><span class="sxs-lookup"><span data-stu-id="9eb01-292">Windows Native Interop</span></span>

<span data-ttu-id="9eb01-293">Windows では、フラット C API、COM、および WinRT の形式で、質の高いネイティブ API を提供しています。</span><span class="sxs-lookup"><span data-stu-id="9eb01-293">Windows offers a rich native API, in the form of flat C APIs, COM, and WinRT.</span></span> <span data-ttu-id="9eb01-294">**P/Invoke** は .NET Core 1.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="9eb01-294">Since .NET Core 1.0, **P/Invoke** has been supported.</span></span> <span data-ttu-id="9eb01-295">.NET Core 3.0 では、**CoCreate COM API** と **WinRT API をアクティブ化**する機能のサポートが追加されました。</span><span class="sxs-lookup"><span data-stu-id="9eb01-295">Now with .NET Core 3.0, support for the ability to **CoCreate COM APIs** and **Activate WinRT APIs** has been added.</span></span>

<span data-ttu-id="9eb01-296">[Excel デモのソース コード](https://github.com/dotnet/samples/tree/master/core/extensions/ExcelDemo)での COM の使用例を確認できます。</span><span class="sxs-lookup"><span data-stu-id="9eb01-296">You can see an example of using COM with the [Excel Demo source code](https://github.com/dotnet/samples/tree/master/core/extensions/ExcelDemo).</span></span>


## <a name="type-sequencereader"></a><span data-ttu-id="9eb01-297">型:SequenceReader</span><span class="sxs-lookup"><span data-stu-id="9eb01-297">Type: SequenceReader</span></span>

<span data-ttu-id="9eb01-298">.NET Core 3.0 には、`ReadOnlySequence<T>` のリーダーとして使用できる `System.Buffers.SequenceReader` が追加されました。</span><span class="sxs-lookup"><span data-stu-id="9eb01-298">In .NET Core 3.0, `System.Buffers.SequenceReader` has been added which can be used as a reader for `ReadOnlySequence<T>`.</span></span> <span data-ttu-id="9eb01-299">これにより、バッキング バッファーを複数回通過できる `System.IO.Pipelines` データの簡単、高パフォーマンスな、低割り当ての解析が可能になります。</span><span class="sxs-lookup"><span data-stu-id="9eb01-299">This allows easy, high performance, low allocation parsing of `System.IO.Pipelines` data that can cross multiple backing buffers.</span></span> 

<span data-ttu-id="9eb01-300">次の例では、入力 `Sequence` を有効な `CR/LF` 区切りの行に分割します。</span><span class="sxs-lookup"><span data-stu-id="9eb01-300">The following example breaks an input `Sequence` into valid `CR/LF` delimited lines:</span></span>

```csharp
private static ReadOnlySpan<byte> CRLF => new byte[] { (byte)'\r', (byte)'\n' };

public static void ReadLines(ReadOnlySequence<byte> sequence)
{
    SequenceReader<byte> reader = new SequenceReader<byte>(sequence);

    while (!reader.End)
    {
        if (!reader.TryReadToAny(out ReadOnlySpan<byte> line, CRLF, advancePastDelimiter:false))
        {
            // Couldn't find another delimiter
            // ...
        }

        if (!reader.IsNext(CRLF, advancePast: true))
        {
            // Not a good CR/LF pair
            // ...
        }

        // line is valid, process
        ProcessLine(line);
    }
}
```

## <a name="type-metadataloadcontext"></a><span data-ttu-id="9eb01-301">型:MetadataLoadContext</span><span class="sxs-lookup"><span data-stu-id="9eb01-301">Type: MetadataLoadContext</span></span>

<span data-ttu-id="9eb01-302">呼び出し元のアプリケーション ドメインに影響を与えることなく、アセンブリ メタデータを読み取ることができる `MetadataLoadContext` 型が追加されました。</span><span class="sxs-lookup"><span data-stu-id="9eb01-302">The `MetadataLoadContext` type has been added that enables reading assembly metadata without affecting the caller’s application domain.</span></span> <span data-ttu-id="9eb01-303">現在の運用環境とは異なるアーキテクチャおよびプラットフォーム向けに構築されたアセンブリなど、アセンブリはデータとして読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="9eb01-303">Assemblies are read as data, including assemblies built for different architectures and platforms than the current runtime environment.</span></span> <span data-ttu-id="9eb01-304">`MetadataLoadContext` は <xref:System.Reflection.Assembly.ReflectionOnlyLoad*> と重複しています。これは .NET Framework でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="9eb01-304">`MetadataLoadContext` overlaps with the <xref:System.Reflection.Assembly.ReflectionOnlyLoad*>, which is only available in the .NET Framework.</span></span>

<span data-ttu-id="9eb01-305">`MetdataLoadContext` は、[System.Reflection.MetadataLoadContext パッケージ](https://www.nuget.org/packages/System.Reflection.MetadataLoadContext)で使用できます。</span><span class="sxs-lookup"><span data-stu-id="9eb01-305">`MetdataLoadContext` is available in the [System.Reflection.MetadataLoadContext package](https://www.nuget.org/packages/System.Reflection.MetadataLoadContext).</span></span> <span data-ttu-id="9eb01-306">これは .NET Standard 2.0 パッケージです。</span><span class="sxs-lookup"><span data-stu-id="9eb01-306">It is a .NET Standard 2.0 package.</span></span>

<span data-ttu-id="9eb01-307">`MetadataLoadContext` は、<xref:System.Runtime.Loader.AssemblyLoadContext> 型に似ていますがその型に基づいていない API を公開しています。</span><span class="sxs-lookup"><span data-stu-id="9eb01-307">The `MetadataLoadContext` exposes APIs similar to the <xref:System.Runtime.Loader.AssemblyLoadContext> type, but is not based on that type.</span></span> <span data-ttu-id="9eb01-308"><xref:System.Runtime.Loader.AssemblyLoadContext> と同様に、`MetadataLoadContext` を使用すると、分離したアセンブリの読み込み中にアセンブリを読み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="9eb01-308">Much like <xref:System.Runtime.Loader.AssemblyLoadContext>, the `MetadataLoadContext` enables loading assemblies within an isolated assembly loading universe.</span></span> <span data-ttu-id="9eb01-309">`MetdataLoadContext` API から <xref:System.Reflection.Assembly> オブジェクトが返され、使い慣れたリフレクション API を使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="9eb01-309">`MetdataLoadContext` APIs return <xref:System.Reflection.Assembly> objects, enabling the use of familiar reflection APIs.</span></span> <span data-ttu-id="9eb01-310">[MethodBase.Invoke](https://github.com/dotnet/corefx/blob/master/src/System.Reflection.MetadataLoadContext/src/System/Reflection/TypeLoading/Methods/RoMethod.cs#L127) などの実行指向の API は使用できず、InvalidOperationException がスローされます。</span><span class="sxs-lookup"><span data-stu-id="9eb01-310">Execution-oriented APIs, such as [MethodBase.Invoke](https://github.com/dotnet/corefx/blob/master/src/System.Reflection.MetadataLoadContext/src/System/Reflection/TypeLoading/Methods/RoMethod.cs#L127), are not allowed and will throw InvalidOperationException.</span></span>

<span data-ttu-id="9eb01-311">次のサンプルは、特定のインターフェイスを実装するアセンブリ内で具象型を検索する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="9eb01-311">The following sample demonstrates how to find concrete types in an assembly that implements a given interface:</span></span>

```csharp
var paths = new string[] {@"C:\myapp\mscorlib.dll", @"C:\myapp\myapp.dll"};
var resolver = new PathAssemblyResolver(paths);
using (var lc = new MetadataLoadContext(resolver))
{
    Assembly a = lc.LoadFromAssemblyName("myapp");
    Type myInterface = a.GetType("MyApp.IPluginInterface");
    foreach (Type t in a.GetTypes())
    {
        if (t.IsClass && myInterface.IsAssignableFrom(t))
            Console.WriteLine($"Class {t.FullName} implements IPluginInterface");
    }
}
```

<span data-ttu-id="9eb01-312">`MetadataLoadContext` のシナリオには、一連のアセンブリをデータとして検査し、検査の実行後にすべてのファイル ロックとメモリを解放する必要がある、設計時の機能、ビルド時のツール、およびランタイムのライトアップ機能が含まれます。</span><span class="sxs-lookup"><span data-stu-id="9eb01-312">Scenarios for `MetadataLoadContext` include design-time features, build-time tooling, and runtime light-up features that need to inspect a set of assemblies as data and have all file locks and memory freed after inspection is performed.</span></span>

<span data-ttu-id="9eb01-313">`MetadataLoadContext` には、コンストラクターに渡されるリゾルバー クラスがあります。</span><span class="sxs-lookup"><span data-stu-id="9eb01-313">The `MetadataLoadContext` has a resolver class passed to its constructor.</span></span> <span data-ttu-id="9eb01-314">リゾルバーのジョブは、`AssemblyName` が指定された `Assembly` の読み込みです。</span><span class="sxs-lookup"><span data-stu-id="9eb01-314">The resolver's job is to load an `Assembly` given its `AssemblyName`.</span></span> <span data-ttu-id="9eb01-315">リゾルバー クラスは、抽象 `MetadataAssemblyResolver` クラスから派生します。</span><span class="sxs-lookup"><span data-stu-id="9eb01-315">The resolver class derives from the abstract `MetadataAssemblyResolver` class.</span></span> <span data-ttu-id="9eb01-316">パスベースのシナリオの場合、リゾルバーの実装は `PathAssemblyResolver` で提供されています。</span><span class="sxs-lookup"><span data-stu-id="9eb01-316">An implementation of the resolver for path-based scenarios is provided with `PathAssemblyResolver`.</span></span>

<span data-ttu-id="9eb01-317">[MetadataLoadContext テスト](https://github.com/dotnet/corefx/tree/master/src/System.Reflection.MetadataLoadContext/tests/src/Tests)は多数のユース ケースを示しています。</span><span class="sxs-lookup"><span data-stu-id="9eb01-317">The [MetadataLoadContext tests](https://github.com/dotnet/corefx/tree/master/src/System.Reflection.MetadataLoadContext/tests/src/Tests) demonstrate many use cases.</span></span> <span data-ttu-id="9eb01-318">[アセンブリ テスト](https://github.com/dotnet/corefx/blob/master/src/System.Reflection.MetadataLoadContext/tests/src/Tests/Assembly/AssemblyTests.cs)から始めることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="9eb01-318">The [Assembly tests](https://github.com/dotnet/corefx/blob/master/src/System.Reflection.MetadataLoadContext/tests/src/Tests/Assembly/AssemblyTests.cs) are a good place to start.</span></span>

## <a name="tls-13--openssl-111-on-linux"></a><span data-ttu-id="9eb01-319">Linux 上の TLS 1.3 と OpenSSL 1.1.1</span><span class="sxs-lookup"><span data-stu-id="9eb01-319">TLS 1.3 & OpenSSL 1.1.1 on Linux</span></span>

<span data-ttu-id="9eb01-320">現在、.NET Core では、特定の環境で使用できるようになったら、[OpenSSL 1.1.1 の TLS 1.3 のサポート](https://www.openssl.org/blog/blog/2018/09/11/release111/)を利用する予定です。</span><span class="sxs-lookup"><span data-stu-id="9eb01-320">.NET Core will now take advantage of [TLS 1.3 support in OpenSSL 1.1.1](https://www.openssl.org/blog/blog/2018/09/11/release111/), when it is available in a given environment.</span></span> <span data-ttu-id="9eb01-321">[OpenSSL チーム](https://www.openssl.org/blog/blog/2018/09/11/release111/)によると、TLS 1.3 には複数の利点があります。</span><span class="sxs-lookup"><span data-stu-id="9eb01-321">There are multiple benefits of TLS 1.3, per the [OpenSSL team](https://www.openssl.org/blog/blog/2018/09/11/release111/):</span></span>

* <span data-ttu-id="9eb01-322">クライアントとサーバー間に必要なラウンド トリップ回数の減少による接続時間の改善。</span><span class="sxs-lookup"><span data-stu-id="9eb01-322">Improved connection times due to a reduction in the number of round trips required between the client and server.</span></span>

* <span data-ttu-id="9eb01-323">さまざまな非推奨で安全ではない暗号化アルゴリズムの削除と、より多くの接続ハンドシェイクの暗号化によるセキュリティの向上。</span><span class="sxs-lookup"><span data-stu-id="9eb01-323">Improved security due to the removal of various obsolete and insecure cryptographic algorithms and encryption of more of the connection handshake.</span></span>

<span data-ttu-id="9eb01-324">.NET Core 3.0 Preview 1 では、**OpenSSL 1.1.1**、**OpenSSL 1.1.0**、または **OpenSSL 1.0.2** を利用することができます (Linux システム上で検出された任意の最適なバージョン)。</span><span class="sxs-lookup"><span data-stu-id="9eb01-324">.NET Core 3.0 Preview 1 is capable of utilizing **OpenSSL 1.1.1**, **OpenSSL 1.1.0**, or **OpenSSL 1.0.2** (whatever the best version found is, on a Linux system).</span></span>  <span data-ttu-id="9eb01-325">**OpenSSL 1.1.1** を使用可能で、クライアントとサーバーの両方が **TLS 1.3** をサポートしている場合、`SslProtocols.None` (システムの既定のプロトコル) を使用するときに、SslStream 型と HttpClient 型は **TLS 1.3** を使用します。</span><span class="sxs-lookup"><span data-stu-id="9eb01-325">When **OpenSSL 1.1.1** is available the SslStream and HttpClient types will use **TLS 1.3** when using `SslProtocols.None` (system default protocols), assuming both the client and server support **TLS 1.3**.</span></span>

<span data-ttu-id="9eb01-326">次のサンプルは、<https://www.cloudflare.com> に接続している Ubuntu 18.10 上の .NET Core 3.0 Preview 1 を示しています。</span><span class="sxs-lookup"><span data-stu-id="9eb01-326">The following sample demonstrates .NET Core 3.0 Preview 1 on Ubuntu 18.10 connecting to <https://www.cloudflare.com>:</span></span>

```csharp
using System;
using System.Net.Security;
using System.Net.Sockets;
using System.Threading.Tasks;

namespace tlstest
{
    class Program
    {
        static async Task Main()
        {
            using (TcpClient tcpClient = new TcpClient())
            {
                string targetHost = "www.cloudflare.com";

                await tcpClient.ConnectAsync(targetHost, 443);

                using (SslStream sslStream = new SslStream(tcpClient.GetStream()))
                {
                    await sslStream.AuthenticateAsClientAsync(targetHost);
                    await Console.Out.WriteLineAsync($"Connected to {targetHost} with {sslStream.SslProtocol}");
                }
            }
        }
    }
}
```

```console
user@comp-ubuntu1810:~/tlstest$ dotnet run
Connected to www.cloudflare.com with Tls13
user@comp-ubuntu1810:~/tlstest$ openssl version
OpenSSL 1.1.1  11 Sep 2018
```

>[!IMPORTANT]
><span data-ttu-id="9eb01-327">Windows と macOS はまだ **TLS 1.3** をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="9eb01-327">Windows and macOS do not yet support **TLS 1.3**.</span></span> <span data-ttu-id="9eb01-328">サポートされるようになったら、.NET Core 3.0 はこれらのオペレーティング システムで **TLS 1.3** をサポートする予定です。</span><span class="sxs-lookup"><span data-stu-id="9eb01-328">.NET Core 3.0 will support **TLS 1.3** on these operating systems when support becomes available.</span></span>

## <a name="cryptography"></a><span data-ttu-id="9eb01-329">暗号</span><span class="sxs-lookup"><span data-stu-id="9eb01-329">Cryptography</span></span>

<span data-ttu-id="9eb01-330">`System.Security.Cryptography.AesGcm` および `System.Security.Cryptography.AesCcm` で実装された **AES-GCM** および **AES-CCM** 暗号のサポートが追加されました。</span><span class="sxs-lookup"><span data-stu-id="9eb01-330">Support has been added for **AES-GCM** and **AES-CCM** ciphers, implemented via `System.Security.Cryptography.AesGcm` and `System.Security.Cryptography.AesCcm`.</span></span> <span data-ttu-id="9eb01-331">これらのアルゴリズムは、[Authenticated Encryption with Association Data (AEAD) アルゴリズム](https://en.wikipedia.org/wiki/Authenticated_encryption) であり、.NET Core に追加された最初の Authenticated Encryption (AE) アルゴリズムでもあります。</span><span class="sxs-lookup"><span data-stu-id="9eb01-331">These algorithms are both [Authenticated Encryption with Association Data (AEAD) algorithms](https://en.wikipedia.org/wiki/Authenticated_encryption), and the first Authenticated Encryption (AE) algorithms added to .NET Core.</span></span>

<span data-ttu-id="9eb01-332">次のコードは、**AesGcm** 暗号を使用してランダム データの暗号化と復号化を行う例です。</span><span class="sxs-lookup"><span data-stu-id="9eb01-332">The following code demonstrates using **AesGcm** cipher to encrypt and decrypt random data.</span></span>

<span data-ttu-id="9eb01-333">**AesCcm** のコードは、ほぼ同じになります (クラスの変数名のみが異なります)。</span><span class="sxs-lookup"><span data-stu-id="9eb01-333">The code for **AesCcm** would look almost identical (only the class variable names would be different).</span></span>

```csharp
// key should be: pre-known, derived, or transported via another channel, such as RSA encryption
byte[] key = new byte[16];
RandomNumberGenerator.Fill(key);

byte[] nonce = new byte[12];
RandomNumberGenerator.Fill(nonce);

// normally this would be your data
byte[] dataToEncrypt = new byte[1234];
byte[] associatedData = new byte[333];
RandomNumberGenerator.Fill(dataToEncrypt);
RandomNumberGenerator.Fill(associatedData);

// these will be filled during the encryption
byte[] tag = new byte[16];
byte[] ciphertext = new byte[dataToEncrypt.Length];

using (AesGcm aesGcm = new AesGcm(key))
{
    aesGcm.Encrypt(nonce, dataToEncrypt, ciphertext, tag, associatedData);
}

// tag, nonce, ciphertext, associatedData should be sent to the other part

byte[] decryptedData = new byte[ciphertext.Length];

using (AesGcm aesGcm = new AesGcm(key))
{
    aesGcm.Decrypt(nonce, ciphertext, tag, decryptedData, associatedData);
}

// do something with the data
// this should always print that data is the same
Console.WriteLine($"AES-GCM: Decrypted data is{(dataToEncrypt.SequenceEqual(decryptedData) ? "the same as" : "different than")} original data.");
```

## <a name="cryptographic-key-importexport"></a><span data-ttu-id="9eb01-334">暗号化キーのインポート/エクスポート</span><span class="sxs-lookup"><span data-stu-id="9eb01-334">Cryptographic Key Import/Export</span></span>

<span data-ttu-id="9eb01-335">.NET Core 3.0 Preview 1 は、標準形式からの非対称の公開キーと秘密キーのインポートとエクスポートをサポートしています。X.509 証明書を使用する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="9eb01-335">.NET Core 3.0 Preview 1 supports the import and export of asymmetric public and private keys from standard formats, without needing to use an X.509 certificate.</span></span>

<span data-ttu-id="9eb01-336">すべてのキーの種類 (RSA、DSA、ECDsa、ECDiffieHellman) は、公開キー用の **X.509 SubjectPublicKeyInfo** 形式と、秘密キー用の **PKCS#8 PrivateKeyInfo** および **PKCS#8 EncryptedPrivateKeyInfo** 形式をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="9eb01-336">All key types (RSA, DSA, ECDsa, ECDiffieHellman) support the **X.509 SubjectPublicKeyInfo** format for public keys, and the **PKCS#8 PrivateKeyInfo** and **PKCS#8 EncryptedPrivateKeyInfo** formats for private keys.</span></span> <span data-ttu-id="9eb01-337">RSA は、さらに **PKCS#1 RSAPublicKey** および **PKCS#1 RSAPrivateKey** をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="9eb01-337">RSA additionally supports **PKCS#1 RSAPublicKey** and **PKCS#1 RSAPrivateKey**.</span></span> <span data-ttu-id="9eb01-338">いずれのエクスポートメソッドからも、DER でエンコードされたバイナリ データが生成され、インポート メソッドもそのようなデータを期待します。</span><span class="sxs-lookup"><span data-stu-id="9eb01-338">The export methods all produce DER-encoded binary data, and the import methods expect the same.</span></span> <span data-ttu-id="9eb01-339">キーがテキストに適した PEM 形式で格納されている場合、呼び出し元は import メソッドを呼び出す前にコンテンツを base64 でデコードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9eb01-339">If a key is stored in the text-friendly PEM format, the caller will need to base64-decode the content before calling an import method.</span></span>

```csharp
using System;
using System.IO;
using System.Security.Cryptography;

namespace rsakeyprint
{
    class Program
    {
        static void Main(string[] args)
        {
            using (RSA rsa = RSA.Create())
            {
                byte[] keyBytes = File.ReadAllBytes(args[0]);
                rsa.ImportRSAPrivateKey(keyBytes, out int bytesRead);
 
                Console.WriteLine($"Read {bytesRead} bytes, {keyBytes.Length-bytesRead} extra byte(s) in file.");
                RSAParameters rsaParameters = rsa.ExportParameters(true);
                Console.WriteLine(BitConverter.ToString(rsaParameters.D));
            }
        }
    }
}
```

```console
user@comp-ubuntu1810:~/rsakeyprint$ echo Making a small key to save on screen space.
Making a small key to save on screen space.
user@comp-ubuntu1810:~/rsakeyprint$ openssl genrsa 768 | openssl rsa -outform der -out rsa.key
Generating RSA private key, 768 bit long modulus (2 primes)
..+++++++
........+++++++
e is 65537 (0x010001)
writing RSA key
user@comp-ubuntu1810:~/rsakeyprint$ dotnet run rsa.key
Read 461 bytes, 0 extra byte(s) in file.
0F-D0-82-34-F8-13-38-4A-7F-C7-52-4A-F6-93-F8-FB-6D-98-7A-6A-04-3B-BC-35-8C-7D-AC-A5-A3-6E-AD-C1-66-30-81-2C-2A-DE-DA-60-03-6A-2C-D9-76-15-7F-61-97-57-
79-E1-6E-45-62-C3-83-04-97-CB-32-EF-C5-17-5F-99-60-92-AE-B6-34-6F-30-06-03-AC-BF-15-24-43-84-EB-83-60-EF-4D-3B-BD-D9-5D-56-26-F0-51-CE-F1
user@comp-ubuntu1810:~/rsakeyprint$ openssl rsa -in rsa.key -inform der -text -noout | grep -A7 private
privateExponent:
    0f:d0:82:34:f8:13:38:4a:7f:c7:52:4a:f6:93:f8:
    fb:6d:98:7a:6a:04:3b:bc:35:8c:7d:ac:a5:a3:6e:
    ad:c1:66:30:81:2c:2a:de:da:60:03:6a:2c:d9:76:
    15:7f:61:97:57:79:e1:6e:45:62:c3:83:04:97:cb:
    32:ef:c5:17:5f:99:60:92:ae:b6:34:6f:30:06:03:
    ac:bf:15:24:43:84:eb:83:60:ef:4d:3b:bd:d9:5d:
    56:26:f0:51:ce:f1
```

<span data-ttu-id="9eb01-340">PKCS#8 ファイルは `System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo` クラスで検査できます。</span><span class="sxs-lookup"><span data-stu-id="9eb01-340">PKCS#8 files can be inspected with the `System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo` class.</span></span>

<span data-ttu-id="9eb01-341">PFX/PKCS#12 ファイルは、それぞれ `System.Security.Cryptography.Pkcs.Pkcs12Info` および `System.Security.Cryptography.Pkcs.Pkcs12Builder` を使用して検査および操作できます。</span><span class="sxs-lookup"><span data-stu-id="9eb01-341">PFX/PKCS#12 files can be inspected and manipulated with `System.Security.Cryptography.Pkcs.Pkcs12Info` and `System.Security.Cryptography.Pkcs.Pkcs12Builder`, respectively.</span></span>

## <a name="serialport-for-linux"></a><span data-ttu-id="9eb01-342">Linux 用 SerialPort</span><span class="sxs-lookup"><span data-stu-id="9eb01-342">SerialPort for Linux</span></span>

<span data-ttu-id="9eb01-343">.NET Core 3.0 は Linux 上で <xref:System.IO.Ports.SerialPort?displayProperty=nameWithType> をサポートするようになりました。</span><span class="sxs-lookup"><span data-stu-id="9eb01-343">.NET Core 3.0 now supports <xref:System.IO.Ports.SerialPort?displayProperty=nameWithType> on Linux.</span></span>

<span data-ttu-id="9eb01-344">以前の .NET Core では、Windows 上の `SerialPort` 型の使用のみをサポートしていました。</span><span class="sxs-lookup"><span data-stu-id="9eb01-344">Previously, .NET Core only supported using the `SerialPort` type on Windows.</span></span>

## <a name="more-bcl-improvements"></a><span data-ttu-id="9eb01-345">その他の BCL の機能強化</span><span class="sxs-lookup"><span data-stu-id="9eb01-345">More BCL Improvements</span></span>

<span data-ttu-id="9eb01-346">.NET Core 2.1 で導入された `Span<T>`、`Memory<T>`、および関連する型は、.NET Core 3.0 で最適化されました。</span><span class="sxs-lookup"><span data-stu-id="9eb01-346">The `Span<T>`, `Memory<T>`, and related types that were introduced in .NET Core 2.1, have been optimized in .NET Core 3.0.</span></span> <span data-ttu-id="9eb01-347">スパン構築、スライス、解析、書式設定などの一般的な操作がより効率的になりました。</span><span class="sxs-lookup"><span data-stu-id="9eb01-347">Common operations such as span construction, slicing, parsing, and formatting now perform better.</span></span> 

<span data-ttu-id="9eb01-348">さらに、`String` のような型が内部的に改善され、`Dictionary<TKey, TValue>` やその他のコレクションのキーとして使用した場合の効率が改善されました。</span><span class="sxs-lookup"><span data-stu-id="9eb01-348">Additionally, types like `String` have seen under-the-cover improvements to make them more efficient when used as keys with `Dictionary<TKey, TValue>` and other collections.</span></span> <span data-ttu-id="9eb01-349">これらの機能強化を利用するためにコードを変更する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="9eb01-349">No code changes are required to benefit from these improvements.</span></span>

<span data-ttu-id="9eb01-350">.NET Core 3 Preview 1 では、次の機能強化も追加されました。</span><span class="sxs-lookup"><span data-stu-id="9eb01-350">The following improvements are also new in .NET Core 3 Preview 1:</span></span>

* <span data-ttu-id="9eb01-351">HttpClient に組み込まれた Brotli のサポート</span><span class="sxs-lookup"><span data-stu-id="9eb01-351">Brotli support built in to HttpClient</span></span>
* <span data-ttu-id="9eb01-352">ThreadPool.UnsafeQueueWorkItem(IThreadPoolWorkItem)</span><span class="sxs-lookup"><span data-stu-id="9eb01-352">ThreadPool.UnsafeQueueWorkItem(IThreadPoolWorkItem)</span></span>
* <span data-ttu-id="9eb01-353">Unsafe.Unbox</span><span class="sxs-lookup"><span data-stu-id="9eb01-353">Unsafe.Unbox</span></span>
* <span data-ttu-id="9eb01-354">CancellationToken.Unregister</span><span class="sxs-lookup"><span data-stu-id="9eb01-354">CancellationToken.Unregister</span></span>
* <span data-ttu-id="9eb01-355">複合算術演算子</span><span class="sxs-lookup"><span data-stu-id="9eb01-355">Complex arithmetic operators</span></span>
* <span data-ttu-id="9eb01-356">TCP のキープ アライブのためのソケット API</span><span class="sxs-lookup"><span data-stu-id="9eb01-356">Socket APIs for TCP keep alive</span></span>
* <span data-ttu-id="9eb01-357">StringBuilder.GetChunks</span><span class="sxs-lookup"><span data-stu-id="9eb01-357">StringBuilder.GetChunks</span></span>
* <span data-ttu-id="9eb01-358">IPEndPoint の解析</span><span class="sxs-lookup"><span data-stu-id="9eb01-358">IPEndPoint parsing</span></span>
* <span data-ttu-id="9eb01-359">RandomNumberGenerator.GetInt32</span><span class="sxs-lookup"><span data-stu-id="9eb01-359">RandomNumberGenerator.GetInt32</span></span>

## <a name="tiered-compilation"></a><span data-ttu-id="9eb01-360">階層型コンパイル</span><span class="sxs-lookup"><span data-stu-id="9eb01-360">Tiered compilation</span></span>

<span data-ttu-id="9eb01-361">.NET Core 3.0 では、[階層型コンパイル](https://blogs.msdn.microsoft.com/dotnet/2018/08/02/tiered-compilation-preview-in-net-core-2-1/)が既定で有効になりました。</span><span class="sxs-lookup"><span data-stu-id="9eb01-361">[Tiered compilation](https://blogs.msdn.microsoft.com/dotnet/2018/08/02/tiered-compilation-preview-in-net-core-2-1/) is on by default with .NET Core 3.0.</span></span> <span data-ttu-id="9eb01-362">起動時とスループットの最大化の両方でパフォーマンスを向上するために、状況に応じてランタイムが Just-In-Time (JIT) コンパイラを使用できるようにする機能です。</span><span class="sxs-lookup"><span data-stu-id="9eb01-362">It is a feature that enables the runtime to more adaptively use the Just-In-Time (JIT) compiler to get better performance, both at startup and to maximize throughput.</span></span>

<span data-ttu-id="9eb01-363">この機能は、[.NET Core 2.1](https://blogs.msdn.microsoft.com/dotnet/2018/05/30/announcing-net-core-2-1/) のオプトイン機能として追加され、[.NET Core 2.2 Preview 2](https://blogs.msdn.microsoft.com/dotnet/2018/09/12/announcing-net-core-2-2-preview-2/) で既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="9eb01-363">This feature was added as an opt-in feature in [.NET Core 2.1](https://blogs.msdn.microsoft.com/dotnet/2018/05/30/announcing-net-core-2-1/) and then was enabled by default in [.NET Core 2.2 Preview 2](https://blogs.msdn.microsoft.com/dotnet/2018/09/12/announcing-net-core-2-2-preview-2/).</span></span> <span data-ttu-id="9eb01-364">その後、.NET Core 2.2 リリースではオプトイン機能に戻りました。</span><span class="sxs-lookup"><span data-stu-id="9eb01-364">Subsequently, it has been reverted back to opt in with the .NET Core 2.2 release.</span></span>

## <a name="arm64-linux-support"></a><span data-ttu-id="9eb01-365">ARM64 Linux のサポート</span><span class="sxs-lookup"><span data-stu-id="9eb01-365">ARM64 Linux support</span></span>

<span data-ttu-id="9eb01-366">ARM64 for Linux のサポートが追加されました。</span><span class="sxs-lookup"><span data-stu-id="9eb01-366">Support has been added for ARM64 for Linux.</span></span> <span data-ttu-id="9eb01-367">現在、ARM64 の主なユース ケースは、IoT シナリオを使用しています。</span><span class="sxs-lookup"><span data-stu-id="9eb01-367">The primary use case for ARM64 is currently with IoT scenarios.</span></span>

<span data-ttu-id="9eb01-368">Alpine、Debian、Ubuntu [Docker イメージは .NET Core for ARM64](https://hub.docker.com/r/microsoft/dotnet/) で使用できます。</span><span class="sxs-lookup"><span data-stu-id="9eb01-368">Alpine, Debian and Ubuntu [Docker images are available for .NET Core for ARM64](https://hub.docker.com/r/microsoft/dotnet/).</span></span>

<span data-ttu-id="9eb01-369">詳細については、「[.NET Core ARM64 Status](https://github.com/dotnet/announcements/issues/82)」(.NET Core Runtime ARM64 の状態) を確認してください。</span><span class="sxs-lookup"><span data-stu-id="9eb01-369">Please check [.NET Core ARM64 Status](https://github.com/dotnet/announcements/issues/82) for more information.</span></span>

>[!NOTE]
> <span data-ttu-id="9eb01-370">**ARM64** Windows のサポートはまだ使用できません。</span><span class="sxs-lookup"><span data-stu-id="9eb01-370">**ARM64** Windows support isn't yet available.</span></span>

## <a name="install-net-core-30-previews-on-linux-with-snap"></a><span data-ttu-id="9eb01-371">スナップを使用して、Linux に .NET Core 3.0 のプレビューをインストールする</span><span class="sxs-lookup"><span data-stu-id="9eb01-371">Install .NET Core 3.0 Previews on Linux with Snap</span></span>

<span data-ttu-id="9eb01-372">スナップは、[スナップをサポートする Linux ディストリビューション](https://docs.snapcraft.io/installing-snapd/6735)に .NET Core のプレビューをインストールして試すための推奨方法です。</span><span class="sxs-lookup"><span data-stu-id="9eb01-372">Snap is the preferred way to install and try .NET Core previews on [Linux distributions that support Snap](https://docs.snapcraft.io/installing-snapd/6735).</span></span>

<span data-ttu-id="9eb01-373">お使いのシステムにスナップを構成したら、次のコマンドを実行して [.NET Core SDK 3.0 Preview SDK](https://snapcraft.io/dotnet-sdk) をインストールします。</span><span class="sxs-lookup"><span data-stu-id="9eb01-373">After configuring Snap on your system, run the following command to install the [.NET Core SDK 3.0 Preview SDK](https://snapcraft.io/dotnet-sdk).</span></span>

```console
sudo snap install dotnet-sdk --beta --classic
```
 
<span data-ttu-id="9eb01-374">スナップ パッケージを使用して .NET Core をインストールすると、既定の .NET Core コマンドは、単なる `dotnet` ではなく、`dotnet-sdk.dotnet` になります。</span><span class="sxs-lookup"><span data-stu-id="9eb01-374">When .NET Core in installed using the Snap package, the default .NET Core command is `dotnet-sdk.dotnet`, as opposed to just `dotnet`.</span></span> <span data-ttu-id="9eb01-375">名前空間で指定したコマンドの利点は、グローバルにインストールされている可能性がある .NET Core バージョンと競合しないことです。</span><span class="sxs-lookup"><span data-stu-id="9eb01-375">The benefit of the namespaced command is that it will not conflict with a globally installed .NET Core version you may have.</span></span> <span data-ttu-id="9eb01-376">このコマンドは、次を使用して、`dotnet` のエイリアスにすることができます。</span><span class="sxs-lookup"><span data-stu-id="9eb01-376">This command can be aliased to `dotnet` with:</span></span>

```console
sudo snap alias dotnet-sdk.dotnet dotnet
```

<span data-ttu-id="9eb01-377">一部のディストリビューションでは、SSL 証明書へのアクセスを有効にするため、追加の手順が必要です。</span><span class="sxs-lookup"><span data-stu-id="9eb01-377">Some distros require an additional step to enable access to the SSL certificate.</span></span> <span data-ttu-id="9eb01-378">詳細については、[Linux のセットアップ](https://github.com/dotnet/core/blob/master/Documentation/linux-setup.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9eb01-378">See our [Linux Setup](https://github.com/dotnet/core/blob/master/Documentation/linux-setup.md) for details.</span></span>

## <a name="gpio-support-for-raspberry-pi"></a><span data-ttu-id="9eb01-379">Raspberry Pi の GPIO サポート</span><span class="sxs-lookup"><span data-stu-id="9eb01-379">GPIO Support for Raspberry Pi</span></span>

<span data-ttu-id="9eb01-380">GPIO プログラミングで使用することができる 2 つの新しいパッケージが NuGet にリリースされました。</span><span class="sxs-lookup"><span data-stu-id="9eb01-380">Two new packages have been released to NuGet that you can use for GPIO programming.</span></span>

* [<span data-ttu-id="9eb01-381">System.Device.Gpio</span><span class="sxs-lookup"><span data-stu-id="9eb01-381">System.Device.Gpio</span></span>](https://www.nuget.org/packages/System.Device.Gpio/0.1.0-prerelease.19078.2)
* [<span data-ttu-id="9eb01-382">Iot.Device.Bindings</span><span class="sxs-lookup"><span data-stu-id="9eb01-382">Iot.Device.Bindings</span></span>](https://www.nuget.org/packages/Iot.Device.Bindings/0.1.0-prerelease.19078.2)

<span data-ttu-id="9eb01-383">GPIO パッケージには、GPIO、SPI、I2C および PWM デバイス用の API が含まれています。</span><span class="sxs-lookup"><span data-stu-id="9eb01-383">The GPIO Packages includes APIs for GPIO, SPI, I2C and PWM devices.</span></span> <span data-ttu-id="9eb01-384">IoT バインド パッケージには、さまざまなチップとセンサーのための[デバイス バインド](https://github.com/dotnet/iot/blob/master/src/devices/README.md)が含まれています。これは [dotnet/iot - src/devices](https://github.com/dotnet/iot/tree/master/src/devices) で入手可能なものと同じです。</span><span class="sxs-lookup"><span data-stu-id="9eb01-384">The IoT bindings package includes [device bindings](https://github.com/dotnet/iot/blob/master/src/devices/README.md) for various chips and sensors, the same ones available at [dotnet/iot - src/devices](https://github.com/dotnet/iot/tree/master/src/devices).</span></span>

<span data-ttu-id="9eb01-385">.NET Core 3.0 Preview 1 の一部として発表された更新されたシリアル ポート API は、これらのパッケージには含まれていませんが、.NET Core プラットフォームの一部として使用できます。</span><span class="sxs-lookup"><span data-stu-id="9eb01-385">The updated serial port APIs that were announced as part of .NET Core 3.0 Preview 1 are not part of these packages but are available as part of the .NET Core platform.</span></span>


## <a name="platform-support"></a><span data-ttu-id="9eb01-386">プラットフォームのサポート</span><span class="sxs-lookup"><span data-stu-id="9eb01-386">Platform Support</span></span>

<span data-ttu-id="9eb01-387">.NET Core 3 は、次のオペレーティング システムでサポートされます。</span><span class="sxs-lookup"><span data-stu-id="9eb01-387">.NET Core 3 will be supported on the following operating systems:</span></span>

* <span data-ttu-id="9eb01-388">Windows クライアント:7、8.1、10 (1607 以降)</span><span class="sxs-lookup"><span data-stu-id="9eb01-388">Windows Client: 7, 8.1, 10 (1607+)</span></span>
* <span data-ttu-id="9eb01-389">Windows Server:20012 R2 SP1+</span><span class="sxs-lookup"><span data-stu-id="9eb01-389">Windows Server: 20012 R2 SP1+</span></span>
* <span data-ttu-id="9eb01-390">macOS:10.12+</span><span class="sxs-lookup"><span data-stu-id="9eb01-390">macOS: 10.12+</span></span>
* <span data-ttu-id="9eb01-391">RHEL:6+</span><span class="sxs-lookup"><span data-stu-id="9eb01-391">RHEL: 6+</span></span>
* <span data-ttu-id="9eb01-392">Fedora:26+</span><span class="sxs-lookup"><span data-stu-id="9eb01-392">Fedora: 26+</span></span>
* <span data-ttu-id="9eb01-393">Ubuntu:16.04+</span><span class="sxs-lookup"><span data-stu-id="9eb01-393">Ubuntu: 16.04+</span></span>
* <span data-ttu-id="9eb01-394">Debian:9+</span><span class="sxs-lookup"><span data-stu-id="9eb01-394">Debian: 9+</span></span>
* <span data-ttu-id="9eb01-395">SLES:12+</span><span class="sxs-lookup"><span data-stu-id="9eb01-395">SLES: 12+</span></span>
* <span data-ttu-id="9eb01-396">openSUSE:42.3+</span><span class="sxs-lookup"><span data-stu-id="9eb01-396">openSUSE: 42.3+</span></span>
* <span data-ttu-id="9eb01-397">Alpine:3.8+</span><span class="sxs-lookup"><span data-stu-id="9eb01-397">Alpine: 3.8+</span></span>

<span data-ttu-id="9eb01-398">チップのサポートは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="9eb01-398">Chip support follows:</span></span>

* <span data-ttu-id="9eb01-399">Windows、macOS および Linux 上の x64</span><span class="sxs-lookup"><span data-stu-id="9eb01-399">x64 on Windows, macOS, and Linux</span></span>
* <span data-ttu-id="9eb01-400">Windows 上の x86</span><span class="sxs-lookup"><span data-stu-id="9eb01-400">x86 on Windows</span></span>
* <span data-ttu-id="9eb01-401">Windows および Linux 上の ARM32</span><span class="sxs-lookup"><span data-stu-id="9eb01-401">ARM32 on Windows and Linux</span></span>
* <span data-ttu-id="9eb01-402">Linux 上の ARM64</span><span class="sxs-lookup"><span data-stu-id="9eb01-402">ARM64 on Linux</span></span>

<span data-ttu-id="9eb01-403">Linux の場合、ARM32 は Debian 9 以降および Ubuntu 16.04 以降でサポートされます。</span><span class="sxs-lookup"><span data-stu-id="9eb01-403">For Linux, ARM32 is supported on Debian 9+ and Ubuntu 16.04+.</span></span> <span data-ttu-id="9eb01-404">ARM64 の場合、Alpine 3.8 を追加した ARM32 と同じです。</span><span class="sxs-lookup"><span data-stu-id="9eb01-404">For ARM64, it is the same as ARM32 with the addition of Alpine 3.8.</span></span> <span data-ttu-id="9eb01-405">これらは、X64 でサポートされているため、これらのディストリビューションの同じバージョンです。</span><span class="sxs-lookup"><span data-stu-id="9eb01-405">These are the same versions of those distros as is supported for X64.</span></span>

<span data-ttu-id="9eb01-406">.NET Core 3.0 用の Docker イメージは、[Docker Hub の microsoft/dotnet](https://hub.docker.com/r/microsoft/dotnet/) で入手できます。</span><span class="sxs-lookup"><span data-stu-id="9eb01-406">Docker images for .NET Core 3.0 are available at [microsoft/dotnet on Docker Hub](https://hub.docker.com/r/microsoft/dotnet/).</span></span> <span data-ttu-id="9eb01-407">Microsoft は現在、[Microsoft コンテナー レジストリ (MCR)](https://cloudblogs.microsoft.com/opensource/2019/01/17/improved-discovery-experience-microsoft-containers-docker-hub/) の採用プロセスの最中で、最終的な .NET Core 3.0 イメージは MCR にのみ公開することを想定しています。</span><span class="sxs-lookup"><span data-stu-id="9eb01-407">Microsoft is currently in the process of adopting [Microsoft Container Registry (MCR)](https://cloudblogs.microsoft.com/opensource/2019/01/17/improved-discovery-experience-microsoft-containers-docker-hub/) and it is expected that the final .NET Core 3.0 images will only be published to MCR.</span></span>
