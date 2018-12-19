---
title: true および false 演算子 - C# リファレンス
ms.custom: seodec18
ms.date: 12/10/2018
helpviewer_keywords:
- false operator [C#]
- true operator [C#]
ms.assetid: 81a888fd-011e-4589-b242-6c261fea505e
ms.openlocfilehash: 0a75566fdb6222157ecda12a50fd78e22f92fcb4
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2018
ms.locfileid: "53245733"
---
# <a name="true-and-false-operators-c-reference"></a><span data-ttu-id="ea4a7-102">true および false 演算子 (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="ea4a7-102">true and false operators (C# Reference)</span></span>

<span data-ttu-id="ea4a7-103">`true` 演算子は、オペランドが確実に true であることを示す[ブール](bool.md)値 `true` を返します。</span><span class="sxs-lookup"><span data-stu-id="ea4a7-103">The `true` operator returns the [bool](bool.md) value `true` to indicate that an operand is definitely true.</span></span> <span data-ttu-id="ea4a7-104">`false` 演算子は、オペランドが確実に false であることを示す `bool` 値 `true` を返します。</span><span class="sxs-lookup"><span data-stu-id="ea4a7-104">The `false` operator returns the `bool` value `true` to indicate that an operand is definitely false.</span></span> <span data-ttu-id="ea4a7-105">`true` および `false` 演算子が互いに補完することは保証されていません。</span><span class="sxs-lookup"><span data-stu-id="ea4a7-105">The `true` and `false` operators are not guaranteed to complement each other.</span></span> <span data-ttu-id="ea4a7-106">つまり、`true` と `false` 演算子の両方が同じオペランドに対して `bool` 値 `false` を返す場合があります。</span><span class="sxs-lookup"><span data-stu-id="ea4a7-106">That is, both the `true` and `false` operator might return the `bool` value `false` for the same operand.</span></span> <span data-ttu-id="ea4a7-107">ある型でこの 2 つの演算子の 1 つを定義する場合は、もう 1 つの演算子も定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ea4a7-107">If a type defines one of the two operators, it must also define another operator.</span></span>

<span data-ttu-id="ea4a7-108">`true` と `false` 演算子が定義された型によって、[論理 OR 演算子](../operators/or-operator.md) `|` または[論理 AND 演算子](../operators/and-operator.md) `&` が特定の方法で[オーバーロード](operator.md)される場合、[条件付き論理 OR 演算子](../operators/conditional-or-operator.md) `||` または [条件付き論理 AND 演算子](../operators/conditional-and-operator.md) `&&` を、それぞれ、その型のオペランドに対して評価することができます。</span><span class="sxs-lookup"><span data-stu-id="ea4a7-108">If a type with the defined `true` and `false` operators [overloads](operator.md) the [logical OR operator](../operators/or-operator.md) `|` or the [logical AND operator](../operators/and-operator.md) `&` in a certain way, the [conditional logical OR operator](../operators/conditional-or-operator.md) `||` or [conditional logical AND operator](../operators/conditional-and-operator.md) `&&`, respectively, can be evaluated for the operands of that type.</span></span> <span data-ttu-id="ea4a7-109">詳細については、「[C# 言語仕様](../language-specification/index.md)」の[ユーザー定義型条件論理演算子](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators)に関するセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ea4a7-109">For more information, see the [User-defined conditional logical operators](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators) section of the [C# language specification](../language-specification/index.md).</span></span>

<span data-ttu-id="ea4a7-110">`true` 演算子が定義された型は、[if](if-else.md)、[do](do.md)、[while](while.md)、および [for](for.md) ステートメントと、[条件演算子 `?:`](../operators/conditional-operator.md) の制御条件式の結果の型にすることができます。</span><span class="sxs-lookup"><span data-stu-id="ea4a7-110">A type with the defined `true` operator can be the type of a result of a controlling conditional expression in the [if](if-else.md), [do](do.md), [while](while.md), and [for](for.md) statements and in the [conditional operator `?:`](../operators/conditional-operator.md).</span></span> <span data-ttu-id="ea4a7-111">詳細については、「[C# 言語仕様](../language-specification/index.md)」の[ブール型の式](~/_csharplang/spec/expressions.md#boolean-expressions)に関するセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ea4a7-111">For more information, see the [Boolean expressions](~/_csharplang/spec/expressions.md#boolean-expressions) section of the [C# language specification](../language-specification/index.md).</span></span>

> [!TIP]
> <span data-ttu-id="ea4a7-112">3 値ロジックをサポートする必要がある場合は、`bool?` 型を使用します。たとえば、3 値ロジック型をサポートするデータベースを操作する場合などです。</span><span class="sxs-lookup"><span data-stu-id="ea4a7-112">Use the `bool?` type, if you need to support the three-valued logic, for example, when you work with databases that support a three-valued logical type.</span></span> <span data-ttu-id="ea4a7-113">詳細については、「[Null 許容型の使用](../../programming-guide/nullable-types/using-nullable-types.md)」の記事の「[bool? 型](../../programming-guide/nullable-types/using-nullable-types.md#the-bool-type)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ea4a7-113">For more information, see [The bool? type](../../programming-guide/nullable-types/using-nullable-types.md#the-bool-type) section of the [Using nullable types](../../programming-guide/nullable-types/using-nullable-types.md) article.</span></span>

<span data-ttu-id="ea4a7-114">次の例では、`true` と `false` 演算子の両方を定義する型を示します。</span><span class="sxs-lookup"><span data-stu-id="ea4a7-114">The following example presents the type that defines both `true` and `false` operators.</span></span> <span data-ttu-id="ea4a7-115">さらに、論理 AND 演算子 `&` をオーバーロードして、演算子 `&&` もその型のオペランドで評価できるようにします。</span><span class="sxs-lookup"><span data-stu-id="ea4a7-115">Moreover, it overloads the logical AND operator `&` in such a way that the operator `&&` also can be evaluated for the operands of that type.</span></span>

[!code-csharp-interactive[true and false operators example](~/samples/snippets/csharp/keywords/TrueFalseOperatorsExample.cs)]

<span data-ttu-id="ea4a7-116">`&&` 演算子のショートサーキット動作に注意してください。</span><span class="sxs-lookup"><span data-stu-id="ea4a7-116">Notice the short-circuiting behavior of the `&&` operator.</span></span> <span data-ttu-id="ea4a7-117">`GetFuelLaunchStatus` メソッドから `LaunchStatus.Red` が返されると、`&&` 演算子の 2 番目のオペランドは評価されません。</span><span class="sxs-lookup"><span data-stu-id="ea4a7-117">When the `GetFuelLaunchStatus` method returns `LaunchStatus.Red`, the second operand of the `&&` operator is not evaluated.</span></span> <span data-ttu-id="ea4a7-118">これは、`LaunchStatus.Red` が確実に false であるためです。</span><span class="sxs-lookup"><span data-stu-id="ea4a7-118">That is because `LaunchStatus.Red` is definitely false.</span></span> <span data-ttu-id="ea4a7-119">したがって、論理 AND の結果は 2 番目のオペランドの値に依存しません。</span><span class="sxs-lookup"><span data-stu-id="ea4a7-119">Then the result of the logical AND doesn't depend on the value of the second operand.</span></span> <span data-ttu-id="ea4a7-120">この例の出力は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="ea4a7-120">The output of the example is as follows:</span></span>

```console
Getting fuel launch status...
Wait!
```

## <a name="see-also"></a><span data-ttu-id="ea4a7-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="ea4a7-121">See also</span></span>

- [<span data-ttu-id="ea4a7-122">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="ea4a7-122">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="ea4a7-123">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="ea4a7-123">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="ea4a7-124">C# のキーワード</span><span class="sxs-lookup"><span data-stu-id="ea4a7-124">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="ea4a7-125">C# 演算子</span><span class="sxs-lookup"><span data-stu-id="ea4a7-125">C# Operators</span></span>](../operators/index.md)
- [<span data-ttu-id="ea4a7-126">`true` リテラル</span><span class="sxs-lookup"><span data-stu-id="ea4a7-126">`true` literal</span></span>](true-literal.md)
- [<span data-ttu-id="ea4a7-127">`false` リテラル</span><span class="sxs-lookup"><span data-stu-id="ea4a7-127">`false` literal</span></span>](false-literal.md)