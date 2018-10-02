---
title: Byref (f#)
description: Byref と f# での低レベルのプログラミングに使用される byref のような種類について説明します。
ms.date: 09/02/2018
ms.openlocfilehash: 6131104e4325f77da84368c337f998c6b2b5309b
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/02/2018
ms.locfileid: "48030815"
---
# <a name="byrefs"></a><span data-ttu-id="311d3-103">Byref</span><span class="sxs-lookup"><span data-stu-id="311d3-103">Byrefs</span></span>

<span data-ttu-id="311d3-104">F# 低レベルのプログラミングの領域で処理する 2 つの主要な機能領域があります。</span><span class="sxs-lookup"><span data-stu-id="311d3-104">F# has two major feature areas that deal in the space of low-level programming:</span></span>

* <span data-ttu-id="311d3-105">`byref` / `inref` / `outref`マネージ ポインターである型。</span><span class="sxs-lookup"><span data-stu-id="311d3-105">The `byref`/`inref`/`outref` types, which are a managed pointers.</span></span> <span data-ttu-id="311d3-106">使用量に制限があるできるように、実行時に無効なプログラムをコンパイルすることはできません。</span><span class="sxs-lookup"><span data-stu-id="311d3-106">They have restrictions on usage so that you cannot compile a program that is invalid at runtime.</span></span>
* <span data-ttu-id="311d3-107">A `byref`-これは構造体のように、[構造](structures.md)のようなセマンティクスと同じコンパイル時の制限を持つ`byref<'T>`します。</span><span class="sxs-lookup"><span data-stu-id="311d3-107">A `byref`-like struct, which is a [structure](structures.md) that has similar semantics and the same compile-time restrictions as `byref<'T>`.</span></span> <span data-ttu-id="311d3-108">1 つの例は、<xref:System.Span%601>します。</span><span class="sxs-lookup"><span data-stu-id="311d3-108">One example is <xref:System.Span%601>.</span></span>

## <a name="syntax"></a><span data-ttu-id="311d3-109">構文</span><span class="sxs-lookup"><span data-stu-id="311d3-109">Syntax</span></span>

```fsharp
// Byref types as parameters
let f (x: byref<'T>) = ()
let g (x: inref<'T>) = ()
let h (x: outref<'T>) = ()

// Calling a function with a byref parameter
let mutable x = 3
f &x

// Declaring a byref-like struct
open System.Runtime.CompilerServices

[<Struct; IsByRefLike>]
type S(count1: int, count2: int) =
    member x.Count1 = count1
    member x.Count2 = count2
```

## <a name="byref-inref-and-outref"></a><span data-ttu-id="311d3-110">Byref、inref、および outref</span><span class="sxs-lookup"><span data-stu-id="311d3-110">Byref, inref, and outref</span></span>

<span data-ttu-id="311d3-111">3 つの形式がある`byref`:</span><span class="sxs-lookup"><span data-stu-id="311d3-111">There are three forms of `byref`:</span></span>

* <span data-ttu-id="311d3-112">`inref<'T>`、基になる値を読み取るためのマネージ ポインター。</span><span class="sxs-lookup"><span data-stu-id="311d3-112">`inref<'T>`, a managed pointer for reading the underlying value.</span></span>
* <span data-ttu-id="311d3-113">`outref<'T>`、基になる値を書き込むためのマネージ ポインター。</span><span class="sxs-lookup"><span data-stu-id="311d3-113">`outref<'T>`, a managed pointer for writing to the underlying value.</span></span>
* <span data-ttu-id="311d3-114">`byref<'T>`、基になる値の読み取りと書き込み用のマネージ ポインター。</span><span class="sxs-lookup"><span data-stu-id="311d3-114">`byref<'T>`, a managed pointer for reading and writing the underlying value.</span></span>

<span data-ttu-id="311d3-115">A`byref<'T>`を渡すことができます、`inref<'T>`が必要です。</span><span class="sxs-lookup"><span data-stu-id="311d3-115">A `byref<'T>` can be passed where an `inref<'T>` is expected.</span></span> <span data-ttu-id="311d3-116">同様に、`byref<'T>`を渡すことができます、`outref<'T>`が必要です。</span><span class="sxs-lookup"><span data-stu-id="311d3-116">Similarly, a `byref<'T>` can be passed where an `outref<'T>` is expected.</span></span>

## <a name="using-byrefs"></a><span data-ttu-id="311d3-117">Byref を使用します。</span><span class="sxs-lookup"><span data-stu-id="311d3-117">Using byrefs</span></span>

<span data-ttu-id="311d3-118">使用する、 `inref<'T>`、ポインター値を取得する必要がある`&`:</span><span class="sxs-lookup"><span data-stu-id="311d3-118">To use a `inref<'T>`, you need to get a pointer value with `&`:</span></span>

```fsharp
open System

let f (dt: inref<DateTime>) =
    printfn "Now: %s" (dt.ToString())

let dt = DateTime.Now
f &dt // Pass a pointer to 'dt'
```

<span data-ttu-id="311d3-119">使用して、ポインターに書き込む、`outref<'T>`または`byref<'T>`へのポインターを取得する値を行う必要があります`mutable`します。</span><span class="sxs-lookup"><span data-stu-id="311d3-119">To write to the pointer by using an `outref<'T>` or `byref<'T>`, you must also make the value you grab a pointer to `mutable`.</span></span>

```fsharp
open System

let f (dt: byref<DateTime>) =
    printfn "Now: %s" (dt.ToString())
    dt <- DateTime.Now

// Make 'dt' mutable
let mutable dt = DateTime.Now

// Now you can pass the pointer to 'dt'
f &dt
```

<span data-ttu-id="311d3-120">読み取りではなくポインターのみを記述する場合は、使用を検討して`outref<'T>`の代わりに`byref<'T>`します。</span><span class="sxs-lookup"><span data-stu-id="311d3-120">If you are only writing the pointer instead of reading it, consider using `outref<'T>` instead of `byref<'T>`.</span></span>

### <a name="inref-semantics"></a><span data-ttu-id="311d3-121">Inref セマンティクス</span><span class="sxs-lookup"><span data-stu-id="311d3-121">Inref semantics</span></span>

<span data-ttu-id="311d3-122">次のコードがあるとします。</span><span class="sxs-lookup"><span data-stu-id="311d3-122">Consider the following code:</span></span>

```fsharp
let f (x: inref<SomeStruct>) = s.SomeField
```

<span data-ttu-id="311d3-123">意味は次の意味としては。</span><span class="sxs-lookup"><span data-stu-id="311d3-123">Semantically, this means the following:</span></span>

* <span data-ttu-id="311d3-124">所有者、`x`ポインターにのみ使用できますが、値の読み取り。</span><span class="sxs-lookup"><span data-stu-id="311d3-124">The holder of the `x` pointer may only use it to read the value.</span></span>
* <span data-ttu-id="311d3-125">ポインターが取得される`struct`内で入れ子になったフィールド`SomeStruct`型を指定して、`inref<_>`します。</span><span class="sxs-lookup"><span data-stu-id="311d3-125">Any pointer acquired to `struct` fields nested within `SomeStruct` are given type `inref<_>`.</span></span>

<span data-ttu-id="311d3-126">次に示します。 また場合は true。</span><span class="sxs-lookup"><span data-stu-id="311d3-126">The following is also true:</span></span>

* <span data-ttu-id="311d3-127">ない暗黙的の他のスレッドまたはエイリアスへの書き込みアクセスはありません。`x`します。</span><span class="sxs-lookup"><span data-stu-id="311d3-127">There is no implication that other threads or aliases do not have write access to `x`.</span></span>
* <span data-ttu-id="311d3-128">意味はありませんが`SomeStruct`して不変`x`されている、 `inref`。</span><span class="sxs-lookup"><span data-stu-id="311d3-128">There is no implication that `SomeStruct` is immutable by virtue of `x` being an `inref`.</span></span>

<span data-ttu-id="311d3-129">ただし、f# のある値型**は**、変更できない、`this`ポインターは、推論、`inref`します。</span><span class="sxs-lookup"><span data-stu-id="311d3-129">However, for F# value types that **are** immutable, the `this` pointer is inferred to be an `inref`.</span></span>

<span data-ttu-id="311d3-130">一緒にこれらのルールのすべてからの所有者といって、`inref`ポインターは、即時に示されるメモリの内容を変更できません。</span><span class="sxs-lookup"><span data-stu-id="311d3-130">All of these rules together mean that the holder of an `inref` pointer may not modify the immediate contents of the memory being pointed to.</span></span>

### <a name="outref-semantics"></a><span data-ttu-id="311d3-131">Outref セマンティクス</span><span class="sxs-lookup"><span data-stu-id="311d3-131">Outref semantics</span></span>

<span data-ttu-id="311d3-132">目的は、`outref<'T>`をからポインターを読み取るだけことを示すことです。</span><span class="sxs-lookup"><span data-stu-id="311d3-132">The purpose of `outref<'T>` is to indicate that the pointer should only be read from.</span></span> <span data-ttu-id="311d3-133">予期せず、`outref<'T>`名前とは異なり値の読み取り、基になることができます。</span><span class="sxs-lookup"><span data-stu-id="311d3-133">Unexpectedly, `outref<'T>` permits reading the underlying value despite its name.</span></span> <span data-ttu-id="311d3-134">これは、互換性のため。</span><span class="sxs-lookup"><span data-stu-id="311d3-134">This is for compatibility purposes.</span></span> <span data-ttu-id="311d3-135">意味としては、`outref<'T>`は変わりません`byref<'T>`します。</span><span class="sxs-lookup"><span data-stu-id="311d3-135">Semantically, `outref<'T>` is no different than `byref<'T>`.</span></span>

### <a name="interop-with-c"></a><span data-ttu-id="311d3-136">C# との相互運用</span><span class="sxs-lookup"><span data-stu-id="311d3-136">Interop with C#</span></span> #

<span data-ttu-id="311d3-137">C# のサポート、`in ref`と`out ref`に加えて、キーワード`ref`を返します。</span><span class="sxs-lookup"><span data-stu-id="311d3-137">C# supports the `in ref` and `out ref` keywords, in addition to `ref` returns.</span></span> <span data-ttu-id="311d3-138">次の表は、f# を解釈する方法と c# は出力を示しています。</span><span class="sxs-lookup"><span data-stu-id="311d3-138">The following table shows how F# interprets what C# emits:</span></span>

|<span data-ttu-id="311d3-139">コンス トラクター (C#)</span><span class="sxs-lookup"><span data-stu-id="311d3-139">C# construct</span></span>|<span data-ttu-id="311d3-140">F# は推測します。</span><span class="sxs-lookup"><span data-stu-id="311d3-140">F# infers</span></span>|
|------------|---------|
|<span data-ttu-id="311d3-141">`ref` 戻り値</span><span class="sxs-lookup"><span data-stu-id="311d3-141">`ref` return value</span></span>|`outref<'T>`|
|<span data-ttu-id="311d3-142">`ref readonly` 戻り値</span><span class="sxs-lookup"><span data-stu-id="311d3-142">`ref readonly` return value</span></span>|`inref<'T>`|
|<span data-ttu-id="311d3-143">`in ref` パラメーター</span><span class="sxs-lookup"><span data-stu-id="311d3-143">`in ref` parameter</span></span>|`inref<'T>`|
|<span data-ttu-id="311d3-144">`out ref` パラメーター</span><span class="sxs-lookup"><span data-stu-id="311d3-144">`out ref` parameter</span></span>|`outref<'T>`|

<span data-ttu-id="311d3-145">次の表では、どのような f# は出力を示します。</span><span class="sxs-lookup"><span data-stu-id="311d3-145">The following table shows what F# emits:</span></span>

|<span data-ttu-id="311d3-146">F# の構成要素</span><span class="sxs-lookup"><span data-stu-id="311d3-146">F# construct</span></span>|<span data-ttu-id="311d3-147">生成されたコンス トラクター</span><span class="sxs-lookup"><span data-stu-id="311d3-147">Emitted construct</span></span>|
|------------|-----------------|
|<span data-ttu-id="311d3-148">`inref<'T>` 引数</span><span class="sxs-lookup"><span data-stu-id="311d3-148">`inref<'T>` argument</span></span>|<span data-ttu-id="311d3-149">`[In]` 引数の属性</span><span class="sxs-lookup"><span data-stu-id="311d3-149">`[In]` attribute on argument</span></span>|
|<span data-ttu-id="311d3-150">`inref<'T>` 戻り値</span><span class="sxs-lookup"><span data-stu-id="311d3-150">`inref<'T>` return</span></span>|<span data-ttu-id="311d3-151">`modreq` 値の属性</span><span class="sxs-lookup"><span data-stu-id="311d3-151">`modreq` attribute on value</span></span>|
|<span data-ttu-id="311d3-152">`inref<'T>` 抽象スロットまたは実装</span><span class="sxs-lookup"><span data-stu-id="311d3-152">`inref<'T>` in abstract slot or implementation</span></span>|<span data-ttu-id="311d3-153">`modreq` 引数または戻り値</span><span class="sxs-lookup"><span data-stu-id="311d3-153">`modreq` on argument or return</span></span>|
|<span data-ttu-id="311d3-154">`outref<'T>` 引数</span><span class="sxs-lookup"><span data-stu-id="311d3-154">`outref<'T>` argument</span></span>|<span data-ttu-id="311d3-155">`[Out]` 引数の属性</span><span class="sxs-lookup"><span data-stu-id="311d3-155">`[Out]` attribute on argument</span></span>|

### <a name="type-inference-and-overloading-rules"></a><span data-ttu-id="311d3-156">型の推定とオーバー ロードの規則</span><span class="sxs-lookup"><span data-stu-id="311d3-156">Type inference and overloading rules</span></span>

<span data-ttu-id="311d3-157">`inref<'T>`型は、次の場合に f# コンパイラによって推論されます。</span><span class="sxs-lookup"><span data-stu-id="311d3-157">An `inref<'T>` type is inferred by the F# compiler in the following cases:</span></span>

1. <span data-ttu-id="311d3-158">.NET パラメーターまたは戻り値型を持つ、`IsReadOnly`属性。</span><span class="sxs-lookup"><span data-stu-id="311d3-158">A .NET parameter or return type that has an `IsReadOnly` attribute.</span></span>
2. <span data-ttu-id="311d3-159">`this`変更可能なフィールドを持たない構造体の型のポインター。</span><span class="sxs-lookup"><span data-stu-id="311d3-159">The `this` pointer on a struct type that has no mutable fields.</span></span>
3. <span data-ttu-id="311d3-160">メモリの場所のアドレスが別の派生`inref<_>`ポインター。</span><span class="sxs-lookup"><span data-stu-id="311d3-160">The address of a memory location derived from another `inref<_>` pointer.</span></span>

<span data-ttu-id="311d3-161">暗黙的なアドレスのとき、`inref`が行われている、型の引数とオーバー ロード`SomeType`型の引数とオーバー ロードに優先`inref<SomeType>`。</span><span class="sxs-lookup"><span data-stu-id="311d3-161">When an implicit address of an `inref` is being taken, an overload with an argument of type `SomeType` is preferred to an overload with an argument of type `inref<SomeType>`.</span></span> <span data-ttu-id="311d3-162">例えば:</span><span class="sxs-lookup"><span data-stu-id="311d3-162">For example:</span></span>

```fsharp
type C() =
    static member M(x: System.DateTime) = x.AddDays(1.0)
    static member M(x: inref<System.DateTime>) = x.AddDays(2.0)
    static member M2(x: System.DateTime, y: int) = x.AddDays(1.0)
    static member M2(x: inref<System.DateTime>, y: int) = x.AddDays(2.0)

let res = System.DateTime.Now
let v =  C.M(res)
let v2 =  C.M2(res, 4)
```

<span data-ttu-id="311d3-163">どちらを取るオーバー ロード`System.DateTime`を取るオーバー ロードではなく解決`inref<System.DateTime>`します。</span><span class="sxs-lookup"><span data-stu-id="311d3-163">In both cases, the overloads taking `System.DateTime` are resolved rather than the overloads taking `inref<System.DateTime>`.</span></span>

## <a name="byref-like-structs"></a><span data-ttu-id="311d3-164">Byref のような構造体</span><span class="sxs-lookup"><span data-stu-id="311d3-164">Byref-like structs</span></span>

<span data-ttu-id="311d3-165">加え、 `byref` / `inref` / `outref`の 3 つに従うことができます独自の構造体を定義する`byref`-などのセマンティクスです。</span><span class="sxs-lookup"><span data-stu-id="311d3-165">In addition to the `byref`/`inref`/`outref` trio, you can define your own structs that can adhere to `byref`-like semantics.</span></span> <span data-ttu-id="311d3-166">これは、<xref:System.Runtime.CompilerServices.IsByRefLikeAttribute>属性。</span><span class="sxs-lookup"><span data-stu-id="311d3-166">This is done with the <xref:System.Runtime.CompilerServices.IsByRefLikeAttribute> attribute:</span></span>

```fsharp
open System
open System.Runtime.CompilerServices

[<IsByRefLike; Struct>]
type S(count1: Span<int>, count2: Span<int>) =
    member x.Count1 = count1
    member x.Count2 = count2
```

<span data-ttu-id="311d3-167">`IsByRefLike` 限りません`Struct`します。</span><span class="sxs-lookup"><span data-stu-id="311d3-167">`IsByRefLike` does not imply `Struct`.</span></span> <span data-ttu-id="311d3-168">両方は、型に存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="311d3-168">Both must be present on the type.</span></span>

<span data-ttu-id="311d3-169">A"`byref`のような"f# の構造体はスタック バインド値の型。</span><span class="sxs-lookup"><span data-stu-id="311d3-169">A "`byref`-like" struct in F# is a stack-bound value type.</span></span> <span data-ttu-id="311d3-170">マネージ ヒープに割り当てられることはありません。</span><span class="sxs-lookup"><span data-stu-id="311d3-170">It is never allocated on the managed heap.</span></span> <span data-ttu-id="311d3-171">A `byref`-と同様に、強力な確認については、有効期間と非キャプチャのセットをそのポリシーが適用されて、構造体です、高性能なプログラミングに便利です。</span><span class="sxs-lookup"><span data-stu-id="311d3-171">A `byref`-like struct is useful for high-performance programming, as it is enforced with set of strong checks about lifetime and non-capture.</span></span> <span data-ttu-id="311d3-172">規則は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="311d3-172">The rules are:</span></span>

* <span data-ttu-id="311d3-173">メソッドを返します関数パラメーター、メソッド パラメーター、ローカル変数を使用ができます。</span><span class="sxs-lookup"><span data-stu-id="311d3-173">They can be used as function parameters, method parameters, local variables, method returns.</span></span>
* <span data-ttu-id="311d3-174">静的またはインスタンス クラスまたは構造体を通常のメンバーができません。</span><span class="sxs-lookup"><span data-stu-id="311d3-174">They cannot be static or instance members of a class or normal struct.</span></span>
* <span data-ttu-id="311d3-175">任意のクロージャ コンストラクトをキャプチャできない (`async`メソッドまたはラムダ式)。</span><span class="sxs-lookup"><span data-stu-id="311d3-175">They cannot be captured by any closure construct (`async` methods or lambda expressions).</span></span>
* <span data-ttu-id="311d3-176">これらは、ジェネリック パラメーターとして使用できません。</span><span class="sxs-lookup"><span data-stu-id="311d3-176">They cannot be used as a generic parameter.</span></span>

<span data-ttu-id="311d3-177">この最後の点が f# パイプライン スタイル プログラミングでは、非常に重要として`|>`はその入力の型をパラメーター化されるジェネリック関数です。</span><span class="sxs-lookup"><span data-stu-id="311d3-177">This last point is crucial for F# pipeline-style programming, as `|>` is a generic function that parameterizes its input types.</span></span> <span data-ttu-id="311d3-178">この制限を緩和することがあります`|>`今後は、インライン、本体内にインライン展開の非ジェネリック関数への呼び出しを行いません。</span><span class="sxs-lookup"><span data-stu-id="311d3-178">This restriction may be relaxed for `|>` in the future, as it is inline and does not make any calls to non-inlined generic functions in its body.</span></span>

<span data-ttu-id="311d3-179">これらの規則は、使用状況を制限する非常に強く、それによって、安全な方法でのハイ パフォーマンス コンピューティングの約束を実行するためにします。</span><span class="sxs-lookup"><span data-stu-id="311d3-179">Although these rules very strongly restrict usage, they do so to fulfill the promise of high-performance computing in a safe manner.</span></span>

## <a name="byref-returns"></a><span data-ttu-id="311d3-180">Byref 戻り値します。</span><span class="sxs-lookup"><span data-stu-id="311d3-180">Byref returns</span></span>

<span data-ttu-id="311d3-181">F# の関数からの byref 戻り値またはメンバーを生成および使用されることができます。</span><span class="sxs-lookup"><span data-stu-id="311d3-181">Byref returns from F# functions or members can be produced and consumed.</span></span> <span data-ttu-id="311d3-182">使用するときに、 `byref`-メソッドを返すには、値が暗黙的に逆参照します。</span><span class="sxs-lookup"><span data-stu-id="311d3-182">When consuming a `byref`-returning method, the value is implicitly dereferenced.</span></span> <span data-ttu-id="311d3-183">例えば:</span><span class="sxs-lookup"><span data-stu-id="311d3-183">For example:</span></span>

```fsharp
let safeSum(bytes: Span<byte>) =
    let mutable sum = 0
    for i in 0 .. bytes.Length - 1 do
        sum <- sum + int bytes.[i]
    sum

let sum = safeSum(mySpanOfBytes)
printfn "%d" sum // 'sum' is of type 'int'
```

<span data-ttu-id="311d3-184">複数の連鎖呼び出しを使って参照を渡すなど、暗黙の型の逆参照を回避するために使用`&x`(場所`x`値です)。</span><span class="sxs-lookup"><span data-stu-id="311d3-184">To avoid the implicit dereference, such as passing a reference through multiple chained calls, use `&x` (where `x` is the value).</span></span>

<span data-ttu-id="311d3-185">戻り値を割り当てることができますも直接`byref`します。</span><span class="sxs-lookup"><span data-stu-id="311d3-185">You can also directly assign to a return `byref`.</span></span> <span data-ttu-id="311d3-186">次の (非常に命令的) プログラムを検討してください。</span><span class="sxs-lookup"><span data-stu-id="311d3-186">Consider the following (highly imperative) program:</span></span>

```fsharp
type C() =
    let mutable nums = [| 1; 3; 7; 15; 31; 63; 127; 255; 511; 1023 |]

    override __.ToString() = String.Join(' ', nums)

    member __.FindLargestSmallerThan(target: int) =
        let mutable ctr = nums.Length - 1

        while ctr > 0 && nums.[ctr] >= target do ctr <- ctr - 1

        if ctr > 0 then &nums.[ctr] else &nums.[0]

[<EntryPoint>]
let main argv =
    let c = C()
    printfn "Original sequence: %s" (c.ToString())

    let v = &c.FindLargestSmallerThan 16

    v <- v*2 // Directly assign to the byref return

    printfn "New sequence:      %s" (c.ToString())

    0 // return an integer exit code
```

<span data-ttu-id="311d3-187">出力結果は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="311d3-187">This is the output:</span></span>

```console
Original sequence: 1 3 7 15 31 63 127 255 511 1023
New sequence:      1 3 7 30 31 63 127 255 511 1023
```

## <a name="scoping-for-byrefs"></a><span data-ttu-id="311d3-188">Byref の範囲の設定</span><span class="sxs-lookup"><span data-stu-id="311d3-188">Scoping for byrefs</span></span>

<span data-ttu-id="311d3-189">A `let`-バインドされた値の参照が定義された範囲を超えることはできません。</span><span class="sxs-lookup"><span data-stu-id="311d3-189">A `let`-bound value cannot have its reference exceed the scope in which it was defined.</span></span> <span data-ttu-id="311d3-190">たとえば、次は許可されません。</span><span class="sxs-lookup"><span data-stu-id="311d3-190">For example, the following is disallowed:</span></span>

```fsharp
let test2 () =
    let x = 12
    &x // Error: 'x' exceeds its defined scope!

let test () =
    let x =
        let y = 1
        &y // Error: `y` exceeds its defined scope!
    ()
```

<span data-ttu-id="311d3-191">こうと、最適化をオンまたはオフをコンパイルする場合に応じて異なる結果を取得します。</span><span class="sxs-lookup"><span data-stu-id="311d3-191">This prevents you from getting different results depending on if you compile with optimizations on or off.</span></span>
