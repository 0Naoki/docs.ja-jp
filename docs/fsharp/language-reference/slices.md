---
title: Slice (F#)
description: 既存F#のデータ型にスライスを使用する方法、およびその他のデータ型用に独自のスライスを定義する方法について説明します。
ms.date: 01/22/2019
ms.openlocfilehash: cbff1b055ea99ef708f9db191be49275e630ee90
ms.sourcegitcommit: 9bd1c09128e012b6e34bdcbdf3576379f58f3137
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/23/2019
ms.locfileid: "72798909"
---
# <a name="slices"></a>スライス

でF#は、スライスはデータ型のサブセットです。 データ型からスライスを取得できるようにするには、データ型で `GetSlice` メソッドを定義するか、スコープ内にある[型拡張機能](type-extensions.md)を定義する必要があります。 この記事では、既存F#の型からスライスを取得する方法と、独自の型を定義する方法について説明します。

スライスは[インデクサー](./members/indexed-properties.md)に似ていますが、基になるデータ構造から1つの値を生成するのではなく、複数の値を生成します。

F#には、現在、文字列、リスト、配列、および2D 配列のスライスのサポートが組み込まれています。

## <a name="basic-slicing-with-f-lists-and-arrays"></a>リストと配列F#を使用した基本的なスライス

スライスされる最も一般的なデータ型はF# 、リストと配列です。 次の例では、リストを使用してこれを行う方法を示します。

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

配列のスライスは、スライスリストと同じです。

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

## <a name="slicing-multidimensional-arrays"></a>多次元配列のスライス

F#は、コアライブラリのF#多次元配列をサポートしています。 1次元配列の場合と同様に、多次元配列のスライスも役に立ちます。 ただし、追加のディメンションの導入では、特定の行と列のスライスを取得できるように、若干異なる構文が必要になります。

次の例は、2D 配列をスライスする方法を示しています。

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
printfn "%A" twoByTwo
```

コアF#ライブラリでは、3d 配列の`GetSlice`が定義されていません。 その他の次元の配列をスライスする場合は、`GetSlice` メンバーを自分で定義する必要があります。

## <a name="defining-slices-for-other-data-structures"></a>他のデータ構造のスライスの定義

コアF#ライブラリでは、型の限られたセットのスライスが定義されています。 より多くのデータ型に対してスライスを定義する場合は、型定義自体または型拡張機能のいずれかを使用できます。

たとえば、<xref:System.ArraySegment%601> クラスのスライスを定義して、便利なデータ操作を可能にする方法を次に示します。

```fsharp
open System

type ArraySegment<'TItem> with
    member segment.GetSlice(start, finish) =
        let start = defaultArg start 0
        let finish = defaultArg finish segment.Count
        ArraySegment(segment.Array, segment.Offset + start, finish - start)

let arr = ArraySegment [| 1 .. 10 |]
let slice = arr.[2..5] //[ 3; 4; 5]
```

### <a name="use-inlining-to-avoid-boxing-if-it-is-necessary"></a>インライン展開を使用して、必要に応じてボックス化を回避する

実際に構造体である型のスライスを定義する場合は、`GetSlice` メンバーを `inline` することをお勧めします。 コンパイラF#はオプションの引数を最適化し、スライスの結果としてヒープの割り当てを回避します。 これは、ヒープに割り当てることができない <xref:System.Span%601> などのスライス構成の場合に非常に重要です。

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

## <a name="see-also"></a>関連項目

- [インデックス付きプロパティ](./members/indexed-properties.md)
