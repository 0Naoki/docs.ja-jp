---
title: スライス (F#)
description: 既存のスライスを使用する方法について説明しますF#データ型と他のデータ型のスライスを定義する方法。
ms.date: 01/22/2019
ms.openlocfilehash: c204c6cbb195b33998b92dd940313a132ecc321d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54746709"
---
# <a name="slices"></a><span data-ttu-id="fe5cb-103">スライス</span><span class="sxs-lookup"><span data-stu-id="fe5cb-103">Slices</span></span>

<span data-ttu-id="fe5cb-104">F#、スライスがデータ型のサブセットです。</span><span class="sxs-lookup"><span data-stu-id="fe5cb-104">In F#, a slice is a subset of a data type.</span></span> <span data-ttu-id="fe5cb-105">データ型から、スライスを実行できるようにするには、データ型を定義する必要がありますか、`GetSlice`メソッドまたは、[拡張子を入力](type-extensions.md)にスコープされています。</span><span class="sxs-lookup"><span data-stu-id="fe5cb-105">To be able to take a slice from a data type, the data type must either define a `GetSlice` method or in a [type extension](type-extensions.md) that is in scope.</span></span> <span data-ttu-id="fe5cb-106">この記事は、既存のファイルからのスライスを実行する方法を説明しますF#型と、独自に定義する方法。</span><span class="sxs-lookup"><span data-stu-id="fe5cb-106">This article explains how to take slices from existing F# types and how to define your own.</span></span>

<span data-ttu-id="fe5cb-107">スライスはのような[インデクサー](members/indexed-properties.md)が、基になるデータ構造体から単一の値を生成するのではなく複数の。</span><span class="sxs-lookup"><span data-stu-id="fe5cb-107">Slices are similar to [indexers](members/indexed-properties.md), but instead of yielding a single value from the underlying data structure, they yield multiple ones.</span></span>

<span data-ttu-id="fe5cb-108">F#現在は、文字列、リスト、配列、および 2D 配列のスライスの組み込みサポート。</span><span class="sxs-lookup"><span data-stu-id="fe5cb-108">F# currently has intrinsic support for slicing strings, lists, arrays, and 2D arrays.</span></span>

## <a name="basic-slicing-with-f-lists-and-arrays"></a><span data-ttu-id="fe5cb-109">基本的なスライスF#リストと配列</span><span class="sxs-lookup"><span data-stu-id="fe5cb-109">Basic slicing with F# lists and arrays</span></span>

<span data-ttu-id="fe5cb-110">スライスは最も一般的なデータ型はF#リストと配列。</span><span class="sxs-lookup"><span data-stu-id="fe5cb-110">The most common data types that are sliced are F# lists and arrays.</span></span> <span data-ttu-id="fe5cb-111">次の例では、リストでそれを行う方法を示します。</span><span class="sxs-lookup"><span data-stu-id="fe5cb-111">The following example demonstrates how to do this with lists:</span></span>

```fsharp
// Generate a list of 100 integers
let fullList = [ 1 .. 100 ]

// Create a slice from indices 1-5 (inclusive)
let smallSlice = fullList.[1..5]
printfn "Small slice: %A" smallSlice

// Create a slice from the beginning to index 5 (inclusive)
let unboundedBeginning = fullList.[..5]
printfn "Unbounded beginning slice: %A" unboundedBeginning

// Create a slice from an index to the end of the list
let unboundedEnd = fullList.[94..]
printfn "Unbounded end slice: %A" unboundedEnd
```

<span data-ttu-id="fe5cb-112">リストのスライスと同じように、配列のスライスします。</span><span class="sxs-lookup"><span data-stu-id="fe5cb-112">Slicing arrays is just like slicing lists:</span></span>

```fsharp
// Generate an array of 100 integers
let fullArray = [| 1 .. 100 |]

// Create a slice from indices 1-5 (inclusive)
let smallSlice = fullArray.[1..5]
printfn "Small slice: %A" smallSlice

// Create a slice from the beginning to index 5 (inclusive)
let unboundedBeginning = fullArray.[..5]
printfn "Unbounded beginning slice: %A" unboundedBeginning

// Create a slice from an index to the end of the list
let unboundedEnd = fullArray.[94..]
printfn "Unbounded end slice: %A" unboundedEnd
```

## <a name="slicing-multidimensional-arrays"></a><span data-ttu-id="fe5cb-113">多次元配列のスライス</span><span class="sxs-lookup"><span data-stu-id="fe5cb-113">Slicing multidimensional arrays</span></span>

<span data-ttu-id="fe5cb-114">F#多次元配列をサポートしている、F#コア ライブラリです。</span><span class="sxs-lookup"><span data-stu-id="fe5cb-114">F# supports multidimensional arrays in the F# core library.</span></span> <span data-ttu-id="fe5cb-115">1 次元の配列と多次元配列のスライスにも役立ちます。</span><span class="sxs-lookup"><span data-stu-id="fe5cb-115">As with one-dimensional arrays, slices of multidimensional arrays can also be useful.</span></span> <span data-ttu-id="fe5cb-116">ただし、特定の行と列のスライスを実行できるように、追加のディメンションの概要は、構文がやや異なる定められています。</span><span class="sxs-lookup"><span data-stu-id="fe5cb-116">However, the introduction of additional dimensions mandates a slightly different syntax so that you can take slices of specific rows and columns.</span></span>

<span data-ttu-id="fe5cb-117">2D 配列のスライスには、次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="fe5cb-117">The following examples demonstrate how to slice a 2D array:</span></span>

```fsharp
// Generate a 3x3 2D matrix
let A = array2D [[1;2;3];[4;5;6];[7;8;9]]
printfn "Full matrix:\n %A" A

// Take the first row
let row0 = A.[0,*]
printfn "Row 0: %A" row0

// Take the first column
let col0 = A.[*,0]
printfn "Column 0: %A" col0

// Take all rows but only two columns
let subA = A.[*,0..1]
printfn "%A" subA

// Take two rows and all columns
let subA' = A.[0..1,*]
printfn "%A" subA'

// Slice a 2x2 matrix out of the full 3x3 matrix
let twoByTwo = A.[0..1,0..1]
printfn "%A" twobyTwo
```

<span data-ttu-id="fe5cb-118">F#コア ライブラリを一切定義しません`GetSlice`3D の配列。</span><span class="sxs-lookup"><span data-stu-id="fe5cb-118">The F# core library does not define `GetSlice`for 3D arrays.</span></span> <span data-ttu-id="fe5cb-119">定義する必要がありますまたは他の配列以上のディメンションをスライスする場合、`GetSlice`メンバー自分でします。</span><span class="sxs-lookup"><span data-stu-id="fe5cb-119">If you wish to slice those or other arrays of more dimensions, you must define the `GetSlice` member yourself.</span></span>

## <a name="defining-slices-for-other-data-structures"></a><span data-ttu-id="fe5cb-120">その他のデータ構造にスライスを定義します。</span><span class="sxs-lookup"><span data-stu-id="fe5cb-120">Defining slices for other data structures</span></span>

<span data-ttu-id="fe5cb-121">F#コア ライブラリが限定的なセットの種類のスライスを定義します。</span><span class="sxs-lookup"><span data-stu-id="fe5cb-121">The F# core library defines slices for a limited set of types.</span></span> <span data-ttu-id="fe5cb-122">多くのデータ型のスライスを定義する場合は、これを行う型定義自体または型の拡張機能。</span><span class="sxs-lookup"><span data-stu-id="fe5cb-122">If you wish to define slices for more data types, you can do so either in the type definition itself or in a type extension.</span></span>

<span data-ttu-id="fe5cb-123">たとえば、ここではのスライスを定義する方法、<xref:System.ArraySegment`1>便利なデータ操作に許可するクラス。</span><span class="sxs-lookup"><span data-stu-id="fe5cb-123">For example, here's how you might define slices for the <xref:System.ArraySegment`1> class to allow for convenient data manipulation:</span></span>

```fsharp
open System

type ArraySegment<'TItem> with
    member segment.GetSlice(?start, ?finish) =
        let start = defaultArg start 0
        let finish = defaultArg finish segment.Count
        ArraySegment(segment.Array, segment.Offset + start, finish - start)

let arr = ArraySegment [| 1 .. 10 |]
let slice = arr.[2..5] //[ 3; 4; 5]
```

### <a name="use-inlining-to-avoid-boxing-if-it-is-necessary"></a><span data-ttu-id="fe5cb-124">必要がある場合は、ボックス化を回避するためにインライン化の使用</span><span class="sxs-lookup"><span data-stu-id="fe5cb-124">Use inlining to avoid boxing if it is necessary</span></span>

<span data-ttu-id="fe5cb-125">実際には構造体である型のスライスを定義している場合ことをお勧めする`inline`、`GetSlice`メンバー。</span><span class="sxs-lookup"><span data-stu-id="fe5cb-125">If you are defining slices for a type that is actually a struct, we recommend that you `inline` the `GetSlice` member.</span></span> <span data-ttu-id="fe5cb-126">F#コンパイラによる最適化のスライスの結果としてヒープ割り当てを回避する、省略可能な引数。</span><span class="sxs-lookup"><span data-stu-id="fe5cb-126">The F# compiler optimizes away the optional arguments, avoiding any heap allocations as a result of slicing.</span></span> <span data-ttu-id="fe5cb-127">これは非常に重要ですなどの構造をスライス<xref:System.Span`1>することはできませんがヒープに割り当てられます、します。</span><span class="sxs-lookup"><span data-stu-id="fe5cb-127">This is critically important for slicing constructs such as <xref:System.Span`1> that cannot be be allocated on the heap.</span></span>

```fsharp
open System

type Span<'T> with
    // Note the 'inline' in the member definition
    member inline sp.GetSlice(startIdx, endIdx) =
        let s = defaultArg startIdx 0
        let e = defaultArg endIdx sp.Length
        sp.Slice(s, e)

let printSpan (sp: Span<int>) =
    let arr = sp.ToArray()
    printfn "%A" arr

let sp = [| 1; 2; 3; 4; 5 |].AsSpan()
printSpan sp.[0..] // [|1; 2; 3; 4; 5|]
printSpan sp.[..5] // [|1; 2; 3; 4; 5|]
printSpan sp.[0..3] // [|1; 2; 3|]
printSpan sp.[1..2] // |2; 3|]
```

## <a name="see-also"></a><span data-ttu-id="fe5cb-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="fe5cb-128">See also</span></span>

- [<span data-ttu-id="fe5cb-129">インデックス付きプロパティ</span><span class="sxs-lookup"><span data-stu-id="fe5cb-129">Indexed properties</span></span>](members/indexed-properties.md)