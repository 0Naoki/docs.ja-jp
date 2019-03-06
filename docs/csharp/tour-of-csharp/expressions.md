---
title: C# の式 - C# 言語のツアー
description: 式、オペランド、および演算子は、C# 言語の構成要素です
ms.date: 11/06/2016
ms.assetid: 20d5eb10-7381-47b9-ad90-f1cc895aa27e
ms.openlocfilehash: 682f98d51bf4eb3c1641297972afb86956e06d3e
ms.sourcegitcommit: 79066169e93d9d65203028b21983574ad9dcf6b4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/01/2019
ms.locfileid: "57212093"
---
# <a name="expressions"></a><span data-ttu-id="13be7-103">式</span><span class="sxs-lookup"><span data-stu-id="13be7-103">Expressions</span></span>

<span data-ttu-id="13be7-104">*式*は、*オペランド*と*演算子*で構成されます。</span><span class="sxs-lookup"><span data-stu-id="13be7-104">*Expressions* are constructed from *operands* and *operators*.</span></span> <span data-ttu-id="13be7-105">式の演算子は、オペランドに適用する演算を表します。</span><span class="sxs-lookup"><span data-stu-id="13be7-105">The operators of an expression indicate which operations to apply to the operands.</span></span> <span data-ttu-id="13be7-106">演算子の例として、`+`、`-`、`*`、`/`、および `new` などがあります。</span><span class="sxs-lookup"><span data-stu-id="13be7-106">Examples of operators include `+`, `-`, `*`, `/`, and `new`.</span></span> <span data-ttu-id="13be7-107">オペランドの例としては、リテラル、フィールド、ローカル変数、式などがあります。</span><span class="sxs-lookup"><span data-stu-id="13be7-107">Examples of operands include literals, fields, local variables, and expressions.</span></span>

<span data-ttu-id="13be7-108">複数の演算子を含む式の場合、演算子の*優先順位*によって各々の演算子が評価される順序が決定されます。</span><span class="sxs-lookup"><span data-stu-id="13be7-108">When an expression contains multiple operators, the *precedence* of the operators controls the order in which the individual operators are evaluated.</span></span> <span data-ttu-id="13be7-109">たとえば、式 `x + y * z` の評価は `x + (y * z)` ですが、これは `*` 演算子が `+` 演算子より高い優先順位だからです。</span><span class="sxs-lookup"><span data-stu-id="13be7-109">For example, the expression `x + y * z` is evaluated as `x + (y * z)` because the `*` operator has higher precedence than the `+` operator.</span></span>

<span data-ttu-id="13be7-110">1 つのオペランドが同じ優先順位を持つ 2 つの演算子の間で発生した場合、演算子の*結合性*によって演算が実行される順序が決定されます。</span><span class="sxs-lookup"><span data-stu-id="13be7-110">When an operand occurs between two operators with the same precedence, the *associativity* of the operators controls the order in which the operations are performed:</span></span>

*   <span data-ttu-id="13be7-111">代入演算子を除くすべてのバイナリ演算子は、*左からの結合*、つまり演算は左から右に実行されます。</span><span class="sxs-lookup"><span data-stu-id="13be7-111">Except for the assignment operators, all binary operators are *left-associative*, meaning that operations are performed from left to right.</span></span> <span data-ttu-id="13be7-112">たとえば、`x + y + z` は `(x + y) + z` と評価されます。</span><span class="sxs-lookup"><span data-stu-id="13be7-112">For example, `x + y + z` is evaluated as `(x + y) + z`.</span></span>
*   <span data-ttu-id="13be7-113">代入演算子と条件演算子 (`?:`) は*右からの結合*、つまり演算は右から左に実行されます。</span><span class="sxs-lookup"><span data-stu-id="13be7-113">The assignment operators and the conditional operator (`?:`) are *right-associative*, meaning that operations are performed from right to left.</span></span> <span data-ttu-id="13be7-114">たとえば、`x = y = z` は `x = (y = z)` と評価されます。</span><span class="sxs-lookup"><span data-stu-id="13be7-114">For example, `x = y = z` is evaluated as `x = (y = z)`.</span></span>

<span data-ttu-id="13be7-115">優先順位と結合性は、かっこを使用して制御することができます。</span><span class="sxs-lookup"><span data-stu-id="13be7-115">Precedence and associativity can be controlled using parentheses.</span></span> <span data-ttu-id="13be7-116">たとえば、`x + y * z` は最初に `y` と `z` を掛け、そして結果を `x` に足しますが、`(x + y) * z` では最初に `x` と `y` を足してから `z` を掛けます。</span><span class="sxs-lookup"><span data-stu-id="13be7-116">For example, `x + y * z` first multiplies `y` by `z` and then adds the result to `x`, but `(x + y) * z` first adds `x` and `y` and then multiplies the result by `z`.</span></span>

<span data-ttu-id="13be7-117">ほとんどの演算子は*オーバーロード*できます。</span><span class="sxs-lookup"><span data-stu-id="13be7-117">Most operators can be *overloaded*.</span></span> <span data-ttu-id="13be7-118">演算子をオーバーロードすると、ユーザー定義演算子の実装を、1 つまたは両方のオペランドがユーザー定義のクラスまたは構造体型である演算子に指定することができます。</span><span class="sxs-lookup"><span data-stu-id="13be7-118">Operator overloading permits user-defined operator implementations to be specified for operations where one or both of the operands are of a user-defined class or struct type.</span></span>

<span data-ttu-id="13be7-119">以下は C# の演算子をまとめたもので、演算子のカテゴリを優先順位の高い順に記載してあります。</span><span class="sxs-lookup"><span data-stu-id="13be7-119">The following summarizes C#’s operators, listing the operator categories in order of precedence from highest to lowest.</span></span> <span data-ttu-id="13be7-120">同じカテゴリの演算子は、同じ優先順位を持ちます。</span><span class="sxs-lookup"><span data-stu-id="13be7-120">Operators in the same category have equal precedence.</span></span> <span data-ttu-id="13be7-121">各カテゴリには、そのカテゴリの式の一覧を、その式型の説明と共に示しています。</span><span class="sxs-lookup"><span data-stu-id="13be7-121">Under each category is a list of expressions in that category along with the description of that expression type.</span></span>

* <span data-ttu-id="13be7-122">1 次式</span><span class="sxs-lookup"><span data-stu-id="13be7-122">Primary</span></span>
    - <span data-ttu-id="13be7-123">`x.m`:メンバー アクセス。</span><span class="sxs-lookup"><span data-stu-id="13be7-123">`x.m`: Member access</span></span>
    - <span data-ttu-id="13be7-124">`x(...)`:メソッドおよびデリゲートの呼び出し。</span><span class="sxs-lookup"><span data-stu-id="13be7-124">`x(...)`: Method and delegate invocation</span></span>
    - <span data-ttu-id="13be7-125">`x[...]`:配列アクセスおよびインデクサー アクセス。</span><span class="sxs-lookup"><span data-stu-id="13be7-125">`x[...]`: Array and indexer access</span></span>
    - <span data-ttu-id="13be7-126">`x++`:後置インクリメント。</span><span class="sxs-lookup"><span data-stu-id="13be7-126">`x++`: Post-increment</span></span>
    - <span data-ttu-id="13be7-127">`x--`:後置デクリメント。</span><span class="sxs-lookup"><span data-stu-id="13be7-127">`x--`: Post-decrement</span></span>
    - <span data-ttu-id="13be7-128">`new T(...)`:オブジェクトおよびデリゲートの作成。</span><span class="sxs-lookup"><span data-stu-id="13be7-128">`new T(...)`: Object and delegate creation</span></span>
    - <span data-ttu-id="13be7-129">`new T(...){...}`:初期化子を使用したオブジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="13be7-129">`new T(...){...}`: Object creation with initializer</span></span>
    - <span data-ttu-id="13be7-130">`new {...}`:匿名オブジェクト初期化子</span><span class="sxs-lookup"><span data-stu-id="13be7-130">`new {...}`:  Anonymous object initializer</span></span>
    - <span data-ttu-id="13be7-131">`new T[...]`:配列の作成</span><span class="sxs-lookup"><span data-stu-id="13be7-131">`new T[...]`: Array creation</span></span>
    - <span data-ttu-id="13be7-132">`typeof(T)`:`T` の <xref:System.Type> オブジェクトの取得</span><span class="sxs-lookup"><span data-stu-id="13be7-132">`typeof(T)`: Obtain <xref:System.Type> object for `T`</span></span>
    - <span data-ttu-id="13be7-133">`checked(x)`:checked コンテキストで式を評価します。</span><span class="sxs-lookup"><span data-stu-id="13be7-133">`checked(x)`: Evaluate expression in checked context</span></span>
    - <span data-ttu-id="13be7-134">`unchecked(x)`:unchecked コンテキストで式を評価します。</span><span class="sxs-lookup"><span data-stu-id="13be7-134">`unchecked(x)`: Evaluate expression in unchecked context</span></span>
    - <span data-ttu-id="13be7-135">`default(T)`:`T` 型の既定値の取得</span><span class="sxs-lookup"><span data-stu-id="13be7-135">`default(T)`: Obtain default value of type `T`</span></span>
    - <span data-ttu-id="13be7-136">`delegate {...}`:匿名関数 (匿名メソッド)。</span><span class="sxs-lookup"><span data-stu-id="13be7-136">`delegate {...}`: Anonymous function (anonymous method)</span></span>
* <span data-ttu-id="13be7-137">単項</span><span class="sxs-lookup"><span data-stu-id="13be7-137">Unary</span></span>
    - <span data-ttu-id="13be7-138">`+x`:Identity</span><span class="sxs-lookup"><span data-stu-id="13be7-138">`+x`: Identity</span></span>
    - <span data-ttu-id="13be7-139">`-x`:否定。</span><span class="sxs-lookup"><span data-stu-id="13be7-139">`-x`: Negation</span></span>
    - <span data-ttu-id="13be7-140">`!x`:論理否定。</span><span class="sxs-lookup"><span data-stu-id="13be7-140">`!x`: Logical negation</span></span>
    - <span data-ttu-id="13be7-141">`~x`:ビットごとの否定。</span><span class="sxs-lookup"><span data-stu-id="13be7-141">`~x`: Bitwise negation</span></span>
    - <span data-ttu-id="13be7-142">`++x`:前置インクリメント。</span><span class="sxs-lookup"><span data-stu-id="13be7-142">`++x`: Pre-increment</span></span>
    - <span data-ttu-id="13be7-143">`--x`:前置デクリメント。</span><span class="sxs-lookup"><span data-stu-id="13be7-143">`--x`: Pre-decrement</span></span>
    - <span data-ttu-id="13be7-144">`(T)x`:`x` を明示的に `T` 型に変換</span><span class="sxs-lookup"><span data-stu-id="13be7-144">`(T)x`: Explicitly convert `x` to type `T`</span></span>
    - <span data-ttu-id="13be7-145">`await x`:`x` が完了するのを非同期的に待つ</span><span class="sxs-lookup"><span data-stu-id="13be7-145">`await x`: Asynchronously wait for `x` to complete</span></span>
* <span data-ttu-id="13be7-146">乗法</span><span class="sxs-lookup"><span data-stu-id="13be7-146">Multiplicative</span></span>
    - <span data-ttu-id="13be7-147">`x * y`:乗算</span><span class="sxs-lookup"><span data-stu-id="13be7-147">`x * y`: Multiplication</span></span>
    - <span data-ttu-id="13be7-148">`x / y`:除算記号</span><span class="sxs-lookup"><span data-stu-id="13be7-148">`x / y`: Division</span></span>
    - <span data-ttu-id="13be7-149">`x % y`:剰余。</span><span class="sxs-lookup"><span data-stu-id="13be7-149">`x % y`: Remainder</span></span>
* <span data-ttu-id="13be7-150">加法</span><span class="sxs-lookup"><span data-stu-id="13be7-150">Additive</span></span>
    - <span data-ttu-id="13be7-151">`x + y`:加算、文字列の連結、デリゲートの組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="13be7-151">`x + y`: Addition, string concatenation, delegate combination</span></span>
    - <span data-ttu-id="13be7-152">`x – y`:減算、デリゲートの削除。</span><span class="sxs-lookup"><span data-stu-id="13be7-152">`x – y`: Subtraction, delegate removal</span></span>
* <span data-ttu-id="13be7-153">シフト</span><span class="sxs-lookup"><span data-stu-id="13be7-153">Shift</span></span>
    - <span data-ttu-id="13be7-154">`x << y`:左シフト。</span><span class="sxs-lookup"><span data-stu-id="13be7-154">`x << y`: Shift left</span></span>
    - <span data-ttu-id="13be7-155">`x >> y`:右シフト。</span><span class="sxs-lookup"><span data-stu-id="13be7-155">`x >> y`: Shift right</span></span>
* <span data-ttu-id="13be7-156">関係式と型検査</span><span class="sxs-lookup"><span data-stu-id="13be7-156">Relational and type testing</span></span>
    - <span data-ttu-id="13be7-157">`x < y`:より小さい</span><span class="sxs-lookup"><span data-stu-id="13be7-157">`x < y`: Less than</span></span>
    - <span data-ttu-id="13be7-158">`x > y`:次の値より大きい</span><span class="sxs-lookup"><span data-stu-id="13be7-158">`x > y`: Greater than</span></span>
    - <span data-ttu-id="13be7-159">`x <= y`:以下</span><span class="sxs-lookup"><span data-stu-id="13be7-159">`x <= y`: Less than or equal</span></span>
    - <span data-ttu-id="13be7-160">`x >= y`:以上</span><span class="sxs-lookup"><span data-stu-id="13be7-160">`x >= y`: Greater than or equal</span></span>
    - <span data-ttu-id="13be7-161">`x is T`:`x` が `T` であれば `true` を、そうでなければ `false` を返す</span><span class="sxs-lookup"><span data-stu-id="13be7-161">`x is T`: Return `true` if `x` is a `T`, `false` otherwise</span></span>
    - <span data-ttu-id="13be7-162">`x as T`:`T` として型指定された `x` か、`x` が `T` でない場合は `null` を返す</span><span class="sxs-lookup"><span data-stu-id="13be7-162">`x as T`: Return `x` typed as `T`, or `null` if `x` is not a `T`</span></span>
* <span data-ttu-id="13be7-163">等価比較</span><span class="sxs-lookup"><span data-stu-id="13be7-163">Equality</span></span>
    - <span data-ttu-id="13be7-164">`x == y`:等しい</span><span class="sxs-lookup"><span data-stu-id="13be7-164">`x == y`: Equal</span></span>
    - <span data-ttu-id="13be7-165">`x != y`:等しくない</span><span class="sxs-lookup"><span data-stu-id="13be7-165">`x != y`: Not equal</span></span>
* <span data-ttu-id="13be7-166">論理 AND</span><span class="sxs-lookup"><span data-stu-id="13be7-166">Logical AND</span></span>
    - <span data-ttu-id="13be7-167">`x & y`:整数のビットごとの AND、ブール型の論理 AND</span><span class="sxs-lookup"><span data-stu-id="13be7-167">`x & y`: Integer bitwise AND, boolean logical AND</span></span>
* <span data-ttu-id="13be7-168">論理 XOR</span><span class="sxs-lookup"><span data-stu-id="13be7-168">Logical XOR</span></span>
    - <span data-ttu-id="13be7-169">`x ^ y`:整数のビットごとの XOR、ブール型の論理 XOR。</span><span class="sxs-lookup"><span data-stu-id="13be7-169">`x ^ y`: Integer bitwise XOR, boolean logical XOR</span></span>
* <span data-ttu-id="13be7-170">論理 OR</span><span class="sxs-lookup"><span data-stu-id="13be7-170">Logical OR</span></span>
    - <span data-ttu-id="13be7-171">`x | y`:整数のビットごとの OR、ブール型の論理 OR。</span><span class="sxs-lookup"><span data-stu-id="13be7-171">`x | y`: Integer bitwise OR, boolean logical OR</span></span>
* <span data-ttu-id="13be7-172">条件 AND</span><span class="sxs-lookup"><span data-stu-id="13be7-172">Conditional AND</span></span>
    - <span data-ttu-id="13be7-173">`x && y`:`x` が `false` でない場合にのみ `y` を評価する</span><span class="sxs-lookup"><span data-stu-id="13be7-173">`x && y`: Evaluates `y` only if `x` is not `false`</span></span>
* <span data-ttu-id="13be7-174">条件 OR</span><span class="sxs-lookup"><span data-stu-id="13be7-174">Conditional OR</span></span>
    - <span data-ttu-id="13be7-175">`x || y`:`x` が `true` でない場合にのみ `y` を評価する</span><span class="sxs-lookup"><span data-stu-id="13be7-175">`x || y`: Evaluates `y` only if `x` is not `true`</span></span>
* <span data-ttu-id="13be7-176">Null 合体演算子</span><span class="sxs-lookup"><span data-stu-id="13be7-176">Null coalescing</span></span>
    - <span data-ttu-id="13be7-177">`x ?? y`:`x` が null の場合は `y` に評価、そうでない場合は `x` に評価する</span><span class="sxs-lookup"><span data-stu-id="13be7-177">`x ?? y`: Evaluates to `y` if `x` is null, to `x` otherwise</span></span>
* <span data-ttu-id="13be7-178">条件</span><span class="sxs-lookup"><span data-stu-id="13be7-178">Conditional</span></span>
    - <span data-ttu-id="13be7-179">`x ? y : z`:`x` が `true` の場合は `y` を、`x` が `false` の場合は `z` を評価する</span><span class="sxs-lookup"><span data-stu-id="13be7-179">`x ? y : z`: Evaluates `y` if `x` is `true`, `z` if `x` is `false`</span></span>
* <span data-ttu-id="13be7-180">代入または匿名関数</span><span class="sxs-lookup"><span data-stu-id="13be7-180">Assignment or anonymous function</span></span>
    - <span data-ttu-id="13be7-181">`x = y`:代入</span><span class="sxs-lookup"><span data-stu-id="13be7-181">`x = y`: Assignment</span></span>
    - <span data-ttu-id="13be7-182">`x op= y`:複合代入。サポートされる演算子は次のとおりです:</span><span class="sxs-lookup"><span data-stu-id="13be7-182">`x op= y`: Compound assignment; supported operators are</span></span>
        - <span data-ttu-id="13be7-183">`*=`   `/=`   `%=`   `+=`   `-=`   `<<=`   `>>=`   `&=`  `^=`  `|=`</span><span class="sxs-lookup"><span data-stu-id="13be7-183">`*=`   `/=`   `%=`   `+=`   `-=`   `<<=`   `>>=`   `&=`  `^=`  `|=`</span></span>
    - <span data-ttu-id="13be7-184">`(T x) => y`:匿名関数 (ラムダ式)</span><span class="sxs-lookup"><span data-stu-id="13be7-184">`(T x) => y`: Anonymous function (lambda expression)</span></span>

> [!div class="step-by-step"]
> <span data-ttu-id="13be7-185">[前へ](types-and-variables.md)
> [次へ](statements.md)</span><span class="sxs-lookup"><span data-stu-id="13be7-185">[Previous](types-and-variables.md)
[Next](statements.md)</span></span>