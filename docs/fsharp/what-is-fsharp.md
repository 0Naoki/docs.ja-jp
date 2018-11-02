---
title: F# とは
description: どのような f# プログラミング言語とはなどの f# プログラミングについて説明します。 豊富なデータ型、関数、およびそれらをまとめる方法について説明します。
ms.date: 08/03/2018
ms.openlocfilehash: 193747f380c61a387ed79ecca6abbcd90ee74376
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/02/2018
ms.locfileid: "43863297"
---
# <a name="what-is-f"></a>F# とは #

F# は関数型プログラミング言語を適切な保守しやすいコードを記述するが容易にします。

F# プログラミングでは、主に、型と型推論され、自動的に汎用化されている関数を定義する必要があります。 これにより、問題のドメインとプログラミングの詳細ではなく、そのデータの操作上に残すに専念できます。

```fsharp
open System // Gets access to functionality in System namespace.

// Defines a function that takes a name and produces a greeting.
let getGreeting name =
    sprintf "Hello, %s! Isn't F# great?" name

[<EntryPoint>]
let main args =
    // Defines a list of names
    let names = [ "Don"; "Julia"; "Xi" ]

    // Prints a greeting for each name!
    names
    |> List.map getGreeting
    |> List.iter (fun greeting -> printfn "%s" greeting)

    0
```

F# など、多数の機能があります。

* 軽量構文
* 既定では変更できません。
* 型の推論と自動ジェネリック化
* ファーストクラス関数
* 強力なデータ型
* パターン マッチング
* 非同期プログラミング

機能の完全なセットが記載されて、 [f# 言語リファレンス](language-reference/index.md)します。

## <a name="rich-data-types"></a>豊富なデータ型

などのデータ型[レコード](language-reference/records.md)と[判別共用体](language-reference/discriminated-unions.md)複雑なデータとドメインを表現することができます。

```fsharp
// Group data with Records
type SuccessfulWithdrawal = {
    Amount: decimal
    Balance: decimal
}

type FailedWithdrawal = {
    Amount: decimal
    Balance: decimal
    IsOverdraft: bool
}

// Use discriminated unions to represent data of 1 or more forms
type WithdrawalResult =
    | Success of SuccessfulWithdrawal
    | InsufficientFunds of FailedWithdrawal
    | CardExpired of System.DateTime
    | UndisclosedFailure
```

F# のレコード、判別共用体は、null 以外、変更できない、および簡単に使用できるように、既定では同等です。

## <a name="enforced-correctness-with-functions-and-pattern-matching"></a>関数およびパターン マッチングで正確性を強制

F# の関数を宣言する簡単で実際には強力です。 組み合わせると[パターン マッチング](language-reference/pattern-matching.md)コンパイラが正確性が適用される動作を定義することができます。

```fsharp
// Returns a WithdrawalResult
let withdrawMoney amount = // Implementation elided

let handleWithdrawal amount =
    let w = withdrawMoney amount

    // The F# compiler enforces accounting for each case!
    match w with
    | Success s -> printfn "Successfully withdrew %f" s.Amount
    | InsufficientFunds f -> printfn "Failed: balance is %f" f.Balance
    | CardExpired d -> printfn "Failed: card expired on %O" d
    | UndisclosedFailure -> printfn "Failed: unknown :("
```

F# の関数もファースト クラス、つまりパラメーターとして渡され、その他の関数から返されることができます。

## <a name="functions-to-define-operations-on-objects"></a>オブジェクトに対する操作を定義する関数

F# が有用なデータ型は、blend のデータと機能する必要がある場合、オブジェクトの完全なサポート。 F# の関数は、オブジェクトを操作に使用されます。

```fsharp
type Set<[<EqualityConditionOn>] ‘T when ‘T: comparison>(elements: seq<'T>) =
    member s.IsEmpty = // Implementation elided
    member s.Contains (value) =// Implementation elided
    member s.Add (value) = // Implementation elided
    // ...
    // Further Implementation elided
    // ...
    interface IEnumerable<‘T>
    interface IReadOnlyCollection<‘T>

[<RequireQualifiedAccess>]
module Set =
    let isEmpty (set: Set<'T>) = set.IsEmpty

    let contains element (set: Set<'T>) = set.Contains(element)

    let add value (set: Set<'T>) = set.Add(value)
```

F# でのオブジェクト指向コードを記述するのではなく多くの場合、コードを記述するオブジェクトを操作する関数として別のデータ型を扱います。 などの機能[ジェネリック インターフェイス](language-reference/interfaces.md)、[オブジェクト式](language-reference/object-expressions.md)とを賢く利用[メンバー](language-reference/members/index.md)は大規模な f# プログラムでは一般的です。

## <a name="next-steps"></a>次の手順

多数の F# の機能の詳細については、チェック アウト、 [f# のツアー](tour.md)します。