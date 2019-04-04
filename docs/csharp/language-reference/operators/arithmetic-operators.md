---
title: 算術演算子 - C# リファレンス
description: 数値型を使用して乗算、除算、剰余、加算、減算の演算を実行する C# 演算子について学習します。
ms.date: 03/27/2019
author: pkulikov
f1_keywords:
- ++_CSharpKeyword
- --_CSharpKeyword
- '*_CSharpKeyword'
- /_CSharpKeyword
- '%_CSharpKeyword'
- +_CSharpKeyword
- -_CSharpKeyword
helpviewer_keywords:
- arithmetic operators [C#]
- increment operator [C#]
- ++ operator [C#]
- decrement operator [C#]
- -- operator [C#]
- multiplication operator [C#]
- '* operator [C#]'
- division operator [C#]
- / operator [C#]
- remainder operator [C#]
- '% operator [C#]'
- addition operator [C#]
- + operator [C#]
- subtraction operator [C#]
- '- operator [C#]'
ms.openlocfilehash: 192acf6fea0c6014aaf092077f8deaa844dfd2ec
ms.sourcegitcommit: d938c39afb9216db377d0f0ecdaa53936a851059
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/29/2019
ms.locfileid: "58633804"
---
# <a name="arithmetic-operators-c-reference"></a><span data-ttu-id="70b37-103">算術演算子 (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="70b37-103">Arithmetic operators (C# Reference)</span></span>

<span data-ttu-id="70b37-104">次の演算子は、数値型を使用して算術演算を実行します。</span><span class="sxs-lookup"><span data-stu-id="70b37-104">The following operators perform arithmetic operations with numeric types:</span></span>

- <span data-ttu-id="70b37-105">単項演算子: [`++` (インクリメント)](#increment-operator-)、[`--` (デクリメント)](#decrement-operator---)、[`+` (プラス)](#unary-plus-and-minus-operators)、[`-` (マイナス)](#unary-plus-and-minus-operators)。</span><span class="sxs-lookup"><span data-stu-id="70b37-105">Unary [`++` (increment)](#increment-operator-), [`--` (decrement)](#decrement-operator---), [`+` (plus)](#unary-plus-and-minus-operators), and [`-` (minus)](#unary-plus-and-minus-operators) operators.</span></span>
- <span data-ttu-id="70b37-106">2 項演算子: [`*` (乗算)](#multiplication-operator-)、[`/` (除算)](#division-operator-)、[`%` (剰余)](#remainder-operator-)、[`+` (加算)](#addition-operator-)、[`-` (減算)](#subtraction-operator--)。</span><span class="sxs-lookup"><span data-stu-id="70b37-106">Binary [`*` (multiplication)](#multiplication-operator-), [`/` (division)](#division-operator-), [`%` (remainder)](#remainder-operator-), [`+` (addition)](#addition-operator-), and [`-` (subtraction)](#subtraction-operator--) operators.</span></span>

<span data-ttu-id="70b37-107">これらの演算子は、[整数](../keywords/integral-types-table.md)と[浮動小数点](../keywords/floating-point-types-table.md)のすべての数値型をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="70b37-107">Those operators support all [integral](../keywords/integral-types-table.md) and [floating-point](../keywords/floating-point-types-table.md) numeric types.</span></span>

## <a name="increment-operator-"></a><span data-ttu-id="70b37-108">インクリメント演算子 ++</span><span class="sxs-lookup"><span data-stu-id="70b37-108">Increment operator ++</span></span>

<span data-ttu-id="70b37-109">単項インクリメント演算子 `++` は、オペランドを 1 ずつインクリメントします。</span><span class="sxs-lookup"><span data-stu-id="70b37-109">The unary increment operator `++` increments its operand by 1.</span></span> <span data-ttu-id="70b37-110">このオペランドは、変数、[プロパティ](../../programming-guide/classes-and-structs/properties.md)のアクセス、または[インデクサー](../../../csharp/programming-guide/indexers/index.md)のアクセスである必要があります。</span><span class="sxs-lookup"><span data-stu-id="70b37-110">The operand must be a variable, a [property](../../programming-guide/classes-and-structs/properties.md) access, or an [indexer](../../../csharp/programming-guide/indexers/index.md) access.</span></span>

<span data-ttu-id="70b37-111">インクリメント演算子は、後置インクリメント演算子である `x++` と、前置インクリメント演算子である`++x` という 2 つの形式でサポートされます。</span><span class="sxs-lookup"><span data-stu-id="70b37-111">The increment operator is supported in two forms: the postfix increment operator, `x++`, and the prefix increment operator, `++x`.</span></span>

### <a name="postfix-increment-operator"></a><span data-ttu-id="70b37-112">後置インクリメント演算子</span><span class="sxs-lookup"><span data-stu-id="70b37-112">Postfix increment operator</span></span>

<span data-ttu-id="70b37-113">次の例に示すように、`x++` の結果は、演算子の`x` "*前の*" 値です。</span><span class="sxs-lookup"><span data-stu-id="70b37-113">The result of `x++` is the value of `x` *before* the operation, as the following example shows:</span></span>

[!code-csharp-interactive[postfix increment](~/samples/snippets/csharp/language-reference/operators/ArithmeticOperators.cs#PostfixIncrement)]

### <a name="prefix-increment-operator"></a><span data-ttu-id="70b37-114">前置インクリメント演算子</span><span class="sxs-lookup"><span data-stu-id="70b37-114">Prefix increment operator</span></span>

<span data-ttu-id="70b37-115">次の例に示すように、`++x` の結果は、演算子の "*後ろの*" `x` 値です。</span><span class="sxs-lookup"><span data-stu-id="70b37-115">The result of `++x` is the value of `x` *after* the operation, as the following example shows:</span></span>

[!code-csharp-interactive[prefix increment](~/samples/snippets/csharp/language-reference/operators/ArithmeticOperators.cs#PrefixIncrement)]

## <a name="decrement-operator---"></a><span data-ttu-id="70b37-116">デクリメント演算子 --</span><span class="sxs-lookup"><span data-stu-id="70b37-116">Decrement operator --</span></span>

<span data-ttu-id="70b37-117">単項デクリメント演算子 `--` は、オペランドを 1 ずつデクリメントします。</span><span class="sxs-lookup"><span data-stu-id="70b37-117">The unary decrement operator `--` decrements its operand by 1.</span></span> <span data-ttu-id="70b37-118">このオペランドは、変数、[プロパティ](../../programming-guide/classes-and-structs/properties.md)のアクセス、または[インデクサー](../../../csharp/programming-guide/indexers/index.md)のアクセスである必要があります。</span><span class="sxs-lookup"><span data-stu-id="70b37-118">The operand must be a variable, a [property](../../programming-guide/classes-and-structs/properties.md) access, or an [indexer](../../../csharp/programming-guide/indexers/index.md) access.</span></span>

<span data-ttu-id="70b37-119">デクリメント演算子は、後置デクリメント演算子である `x--` と、前置デクリメント演算子である `--x` という 2 つの形式でサポートされます。</span><span class="sxs-lookup"><span data-stu-id="70b37-119">The decrement operator is supported in two forms: the postfix decrement operator, `x--`, and the prefix decrement operator, `--x`.</span></span>

### <a name="postfix-decrement-operator"></a><span data-ttu-id="70b37-120">後置デクリメント演算子</span><span class="sxs-lookup"><span data-stu-id="70b37-120">Postfix decrement operator</span></span>

<span data-ttu-id="70b37-121">次の例に示すように、`x--` の結果は、演算子の "*前の*" `x` 値です。</span><span class="sxs-lookup"><span data-stu-id="70b37-121">The result of `x--` is the value of `x` *before* the operation, as the following example shows:</span></span>

[!code-csharp-interactive[postfix decrement](~/samples/snippets/csharp/language-reference/operators/ArithmeticOperators.cs#PostfixDecrement)]

### <a name="prefix-decrement-operator"></a><span data-ttu-id="70b37-122">前置デクリメント演算子</span><span class="sxs-lookup"><span data-stu-id="70b37-122">Prefix decrement operator</span></span>

<span data-ttu-id="70b37-123">次の例に示すように、`--x` の結果は、演算子の "*後ろの*" `x` 値です。</span><span class="sxs-lookup"><span data-stu-id="70b37-123">The result of `--x` is the value of `x` *after* the operation, as the following example shows:</span></span>

[!code-csharp-interactive[prefix decrement](~/samples/snippets/csharp/language-reference/operators/ArithmeticOperators.cs#PrefixDecrement)]

## <a name="unary-plus-and-minus-operators"></a><span data-ttu-id="70b37-124">単項プラス演算子と単項マイナス演算子</span><span class="sxs-lookup"><span data-stu-id="70b37-124">Unary plus and minus operators</span></span>

<span data-ttu-id="70b37-125">単項 `+` 演算子によって、そのオペランドの値が返されます。</span><span class="sxs-lookup"><span data-stu-id="70b37-125">The unary `+` operator returns the value of its operand.</span></span> <span data-ttu-id="70b37-126">単項 `-` 演算子は、そのオペランドの数値の否定を計算します。</span><span class="sxs-lookup"><span data-stu-id="70b37-126">The unary `-` operator computes the numeric negation of its operand.</span></span>

[!code-csharp-interactive[unary plus and minus](~/samples/snippets/csharp/language-reference/operators/ArithmeticOperators.cs#UnaryPlusAndMinus)]

<span data-ttu-id="70b37-127">単項 `-` 演算子は、[ulong](../keywords/ulong.md) 型をサポートしません。</span><span class="sxs-lookup"><span data-stu-id="70b37-127">The unary `-` operator doesn't support the [ulong](../keywords/ulong.md) type.</span></span>

## <a name="multiplication-operator-"></a><span data-ttu-id="70b37-128">乗算演算子 \*</span><span class="sxs-lookup"><span data-stu-id="70b37-128">Multiplication operator \*</span></span>

<span data-ttu-id="70b37-129">乗算演算子 (`*`) は、そのオペランドの積を計算します。</span><span class="sxs-lookup"><span data-stu-id="70b37-129">The multiplication operator `*` computes the product of its operands:</span></span>

[!code-csharp-interactive[multiplication operator](~/samples/snippets/csharp/language-reference/operators/ArithmeticOperators.cs#Multiplication)]

<span data-ttu-id="70b37-130">単項 `*` 演算子は、[ポインター間接参照演算子](multiplication-operator.md#pointer-indirection-operator)です。</span><span class="sxs-lookup"><span data-stu-id="70b37-130">The unary `*` operator is a [pointer indirection operator](multiplication-operator.md#pointer-indirection-operator).</span></span>

## <a name="division-operator-"></a><span data-ttu-id="70b37-131">除算演算子 /</span><span class="sxs-lookup"><span data-stu-id="70b37-131">Division operator /</span></span>

<span data-ttu-id="70b37-132">除算演算子 `/` は、1 つ目のオペランドを 2 つ目のオペランドで除算します。</span><span class="sxs-lookup"><span data-stu-id="70b37-132">The division operator `/` divides its first operand by its second operand.</span></span>

### <a name="integer-division"></a><span data-ttu-id="70b37-133">整数の除算</span><span class="sxs-lookup"><span data-stu-id="70b37-133">Integer division</span></span>

<span data-ttu-id="70b37-134">整数型のオペランドに対する `/` 演算子の結果は、整数型で、2 つのオペランドの商を 0 方向に丸めたものと等しくなります。</span><span class="sxs-lookup"><span data-stu-id="70b37-134">For the operands of integer types, the result of the `/` operator is of an integer type and equals the quotient of the two operands rounded towards zero:</span></span>

[!code-csharp-interactive[integer division](~/samples/snippets/csharp/language-reference/operators/ArithmeticOperators.cs#IntegerDivision)]

<span data-ttu-id="70b37-135">2 つのオペランドの商を浮動小数点数として取得するには、`float`、`double`、または `decimal` 型を使います。</span><span class="sxs-lookup"><span data-stu-id="70b37-135">To obtain the quotient of the two operands as a floating-point number, use the `float`, `double`, or `decimal` type:</span></span>

[!code-csharp-interactive[integer as floating-point division](~/samples/snippets/csharp/language-reference/operators/ArithmeticOperators.cs#IntegerAsFloatingPointDivision)]

### <a name="floating-point-division"></a><span data-ttu-id="70b37-136">浮動小数点の除算</span><span class="sxs-lookup"><span data-stu-id="70b37-136">Floating-point division</span></span>

<span data-ttu-id="70b37-137">`float`、`double`、`decimal` 型に対する `/` 演算子の結果は、2 つのオペランドの商となります。</span><span class="sxs-lookup"><span data-stu-id="70b37-137">For the `float`, `double`, and `decimal` types, the result of the `/` operator is the quotient of the two operands:</span></span>

[!code-csharp-interactive[floating-point division](~/samples/snippets/csharp/language-reference/operators/ArithmeticOperators.cs#FloatingPointDivision)]

<span data-ttu-id="70b37-138">オペランドの 1 つが `decimal` であった場合、もう 1 つのオペランドを `float` や `double` にすることはできません。`float` と `double` は暗黙的に `decimal` に変換できないためです。</span><span class="sxs-lookup"><span data-stu-id="70b37-138">If one of the operands is `decimal`, another operand can be neither `float` nor `double`, because neither `float` nor `double` is implicitly convertible to `decimal`.</span></span> <span data-ttu-id="70b37-139">`float` または `double` オペランドは明示的に `decimal` 型に変換する必要があります。</span><span class="sxs-lookup"><span data-stu-id="70b37-139">You must explicitly convert the `float` or `double` operand to the `decimal` type.</span></span> <span data-ttu-id="70b37-140">数値型間の暗黙的な変換について詳しくは、「[暗黙的な数値変換の一覧表](../keywords/implicit-numeric-conversions-table.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="70b37-140">For more information about implicit conversions between numeric types, see [Implicit numeric conversions table](../keywords/implicit-numeric-conversions-table.md).</span></span>

## <a name="remainder-operator-"></a><span data-ttu-id="70b37-141">剰余演算子 %</span><span class="sxs-lookup"><span data-stu-id="70b37-141">Remainder operator %</span></span>

<span data-ttu-id="70b37-142">剰余演算子 `%` は、最初のオペランドを 2 番目のオペランドで除算した後の剰余を計算します。</span><span class="sxs-lookup"><span data-stu-id="70b37-142">The remainder operator `%` computes the remainder after dividing its first operand by its second operand.</span></span>

### <a name="integer-remainder"></a><span data-ttu-id="70b37-143">整数の剰余</span><span class="sxs-lookup"><span data-stu-id="70b37-143">Integer remainder</span></span>
  
<span data-ttu-id="70b37-144">整数型のオペランドの場合、`a % b` の結果は `a - (a / b) * b` で生成される値になります。</span><span class="sxs-lookup"><span data-stu-id="70b37-144">For the operands of integer types, the result of `a % b` is the value produced by `a - (a / b) * b`.</span></span> <span data-ttu-id="70b37-145">0 以外の剰余の符号は、次の例で示されるように、最初のオペランドの符号と同じになります。</span><span class="sxs-lookup"><span data-stu-id="70b37-145">The sign of the non-zero remainder is the same as that of the first operand, as the following example shows:</span></span>

[!code-csharp-interactive[integer remainder](~/samples/snippets/csharp/language-reference/operators/ArithmeticOperators.cs#IntegerRemainder)]

<span data-ttu-id="70b37-146"><xref:System.Math.DivRem%2A?displayProperty=nameWithType> メソッドを使用して、整数除算と剰余の結果の両方を計算します。</span><span class="sxs-lookup"><span data-stu-id="70b37-146">Use the <xref:System.Math.DivRem%2A?displayProperty=nameWithType> method to compute both integer division and remainder results.</span></span>

### <a name="floating-point-remainder"></a><span data-ttu-id="70b37-147">浮動小数点の剰余</span><span class="sxs-lookup"><span data-stu-id="70b37-147">Floating-point remainder</span></span>

<span data-ttu-id="70b37-148">`float` オペランドと `double` オペランドの場合、有限の `x` と `y` の `x % y` の結果は、次のような値 `z` となります。</span><span class="sxs-lookup"><span data-stu-id="70b37-148">For the `float` and `double` operands, the result of `x % y` for the finite `x` and `y` is the value `z` such that</span></span>

- <span data-ttu-id="70b37-149">`z` の符号は、0 以外の場合、`x` の符号と同じになります。</span><span class="sxs-lookup"><span data-stu-id="70b37-149">The sign of `z`, if non-zero, is the same as the sign of `x`.</span></span>
- <span data-ttu-id="70b37-150">`z` の絶対値は、`|x| - n * |y|` で生成される値となります。`n` は、`|x| / |y|` 以下で最も大きい整数であり、`|x|` と `|y|` はそれぞれ、`x` と `y` の絶対値です。</span><span class="sxs-lookup"><span data-stu-id="70b37-150">The absolute value of `z` is the value produced by `|x| - n * |y|` where `n` is the largest possible integer that is less than or equal to `|x| / |y|` and `|x|` and `|y|` are the absolute values of `x` and `y`, respectively.</span></span>

> [!NOTE]
> <span data-ttu-id="70b37-151">剰余を計算するこの手法は、整数オペランドに使用される手法に類似していますが、IEEE 754 とは異なります。</span><span class="sxs-lookup"><span data-stu-id="70b37-151">This method of computing the remainder is analogous to that used for integer operands, but differs from the IEEE 754.</span></span> <span data-ttu-id="70b37-152">IEEE 754 に準拠する剰余演算が必要な場合、<xref:System.Math.IEEERemainder%2A?displayProperty=nameWithType> メソッドを使用してください。</span><span class="sxs-lookup"><span data-stu-id="70b37-152">If you need the remainder operation that complies with the IEEE 754, use the <xref:System.Math.IEEERemainder%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="70b37-153">無限オペランドがある `%` 演算子の動作については、[C# 言語仕様](~/_csharplang/spec/introduction.md)に関するページの「[剰余演算](~/_csharplang/spec/expressions.md#remainder-operator)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="70b37-153">For information about the behavior of the `%` operator with non-finite operands, see the [Remainder operator](~/_csharplang/spec/expressions.md#remainder-operator) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

<span data-ttu-id="70b37-154">`decimal` オペランドの場合、剰余演算子 `%` は <xref:System.Decimal?displayProperty=nameWithType> 型の[剰余演算子](<xref:System.Decimal.op_Modulus(System.Decimal,System.Decimal)>)に等しくなります。</span><span class="sxs-lookup"><span data-stu-id="70b37-154">For the `decimal` operands, the remainder operator `%` is equivalent to the [remainder operator](<xref:System.Decimal.op_Modulus(System.Decimal,System.Decimal)>) of the <xref:System.Decimal?displayProperty=nameWithType> type.</span></span>

<span data-ttu-id="70b37-155">次の例では、浮動小数点オペランドを使用した剰余演算子の動作を示しています。</span><span class="sxs-lookup"><span data-stu-id="70b37-155">The following example demonstrates the behavior of the remainder operator with floating-point operands:</span></span>

[!code-csharp-interactive[floating-point remainder](~/samples/snippets/csharp/language-reference/operators/ArithmeticOperators.cs#FloatingPointRemainder)]

## <a name="addition-operator-"></a><span data-ttu-id="70b37-156">加算演算子 +</span><span class="sxs-lookup"><span data-stu-id="70b37-156">Addition operator +</span></span>

<span data-ttu-id="70b37-157">加算演算子 `+` は、そのオペランドの合計を計算します。</span><span class="sxs-lookup"><span data-stu-id="70b37-157">The addition operator `+` computes the sum of its operands:</span></span>

[!code-csharp-interactive[addition operator](~/samples/snippets/csharp/language-reference/operators/ArithmeticOperators.cs#Addition)]

<span data-ttu-id="70b37-158">文字列連結とデリゲートの組み合わせにも、`+` 演算子が使用できます。</span><span class="sxs-lookup"><span data-stu-id="70b37-158">You also can use the `+` operator for string concatenation and delegate combination.</span></span> <span data-ttu-id="70b37-159">詳細については、「[`+` 演算子](addition-operator.md)」の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="70b37-159">For more information, see the [`+` operator](addition-operator.md) article.</span></span>

## <a name="subtraction-operator--"></a><span data-ttu-id="70b37-160">減算演算子 -</span><span class="sxs-lookup"><span data-stu-id="70b37-160">Subtraction operator -</span></span>

<span data-ttu-id="70b37-161">減算演算子 `-` は、その最初のオペランドから 2 番目のオペランドを減算します。</span><span class="sxs-lookup"><span data-stu-id="70b37-161">The subtraction operator `-` subtracts its second operand from its first operand:</span></span>

[!code-csharp-interactive[subtraction operator](~/samples/snippets/csharp/language-reference/operators/ArithmeticOperators.cs#Subtraction)]

<span data-ttu-id="70b37-162">デリゲートの削除には、`-` 演算子を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="70b37-162">You also can use the `-` operator for delegate removal.</span></span> <span data-ttu-id="70b37-163">詳細については、「[`-` 演算子](subtraction-operator.md)」の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="70b37-163">For more information, see the [`-` operator](subtraction-operator.md) article.</span></span>

## <a name="operator-precedence-and-associativity"></a><span data-ttu-id="70b37-164">演算子の優先順位と結合規則</span><span class="sxs-lookup"><span data-stu-id="70b37-164">Operator precedence and associativity</span></span>

<span data-ttu-id="70b37-165">次の算術演算子の一覧は、優先度が高い順に並べられています。</span><span class="sxs-lookup"><span data-stu-id="70b37-165">The following list orders arithmetic operators starting from the highest precedence to the lowest:</span></span>

- <span data-ttu-id="70b37-166">後置インクリメント `x++` 演算子と後置デクリメント `x--` 演算子</span><span class="sxs-lookup"><span data-stu-id="70b37-166">Postfix increment `x++` and decrement `x--` operators.</span></span>
- <span data-ttu-id="70b37-167">前置インクリメント `++x` 演算子と前置デクリメント `--x` 演算子および単項演算子 `+` と `-`</span><span class="sxs-lookup"><span data-stu-id="70b37-167">Prefix increment `++x` and decrement `--x` and unary `+` and `-` operators.</span></span>
- <span data-ttu-id="70b37-168">乗算演算子 `*`、`/`、`%`</span><span class="sxs-lookup"><span data-stu-id="70b37-168">Multiplicative `*`, `/`, and `%` operators.</span></span>
- <span data-ttu-id="70b37-169">加法演算子 `+` と `-`</span><span class="sxs-lookup"><span data-stu-id="70b37-169">Additive `+` and `-` operators.</span></span>

<span data-ttu-id="70b37-170">2 項算術演算子は左結合です。</span><span class="sxs-lookup"><span data-stu-id="70b37-170">Binary arithmetic operators are left-associative.</span></span> <span data-ttu-id="70b37-171">つまり、優先度が同じ演算子は、左から右に評価されます。</span><span class="sxs-lookup"><span data-stu-id="70b37-171">That is, operators with the same precedence level are evaluated from left to right.</span></span>

<span data-ttu-id="70b37-172">演算子の優先順位と結合規則によって定められた評価の順序を変更するには、かっこ `()` を使用します。</span><span class="sxs-lookup"><span data-stu-id="70b37-172">Use parentheses, `()`, to change the order of evaluation imposed by operator precedence and associativity.</span></span>

[!code-csharp-interactive[precedence and associativity](~/samples/snippets/csharp/language-reference/operators/ArithmeticOperators.cs#PrecedenceAndAssociativity)]

<span data-ttu-id="70b37-173">優先度順に並べられた C# 演算子の完全な一覧については、「[C# 演算子](index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="70b37-173">For the complete list of C# operators ordered by precedence level, see [C# operators](index.md).</span></span>

## <a name="compound-assignment"></a><span data-ttu-id="70b37-174">複合代入。</span><span class="sxs-lookup"><span data-stu-id="70b37-174">Compound assignment</span></span>

<span data-ttu-id="70b37-175">2 項演算子 `op` の場合、フォームの複合代入式</span><span class="sxs-lookup"><span data-stu-id="70b37-175">For a binary operator `op`, a compound assignment expression of the form</span></span>

```csharp
x op= y
```

<span data-ttu-id="70b37-176">上記の式は、次の式と同じです。</span><span class="sxs-lookup"><span data-stu-id="70b37-176">is equivalent to</span></span>

```csharp
x = x op y
```

<span data-ttu-id="70b37-177">ただし、`x` が評価されるのは 1 回だけです。</span><span class="sxs-lookup"><span data-stu-id="70b37-177">except that `x` is only evaluated once.</span></span>

<span data-ttu-id="70b37-178">次の例は、算術演算子を使用した複合代入の使用方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="70b37-178">The following example demonstrates the usage of compound assignment with arithmetic operators:</span></span>

[!code-csharp-interactive[compound assignment](~/samples/snippets/csharp/language-reference/operators/ArithmeticOperators.cs#CompoundAssignment)]

<span data-ttu-id="70b37-179">[イベント](../keywords/event.md)のサブスクリプションとサブスクリプションの解除には、`+=` 演算子と `-=` 演算子も使用できます。</span><span class="sxs-lookup"><span data-stu-id="70b37-179">You also use the `+=` and `-=` operators to subscribe to and unsubscribe from [events](../keywords/event.md).</span></span> <span data-ttu-id="70b37-180">詳細については、「[方法: イベント サブスクリプションとサブスクリプションの解除](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="70b37-180">For more information, see [How to: subscribe to and unsubscribe from events](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span></span>

## <a name="arithmetic-overflow-and-division-by-zero"></a><span data-ttu-id="70b37-181">算術オーバーフローと 0 による除算</span><span class="sxs-lookup"><span data-stu-id="70b37-181">Arithmetic overflow and division by zero</span></span>

<span data-ttu-id="70b37-182">算術演算の結果が関係する数値型の有限値の範囲外にある場合は、算術演算子の動作は、そのオペランドの型に依存します。</span><span class="sxs-lookup"><span data-stu-id="70b37-182">When the result of an arithmetic operation is outside the range of possible finite values of the involved numeric type, the behavior of an arithmetic operator depends on the type of its operands.</span></span>

### <a name="integer-arithmetic-overflow"></a><span data-ttu-id="70b37-183">整数の算術オーバーフロー</span><span class="sxs-lookup"><span data-stu-id="70b37-183">Integer arithmetic overflow</span></span>

<span data-ttu-id="70b37-184">0 による整数除算では、常に <xref:System.DivideByZeroException> がスローされます。</span><span class="sxs-lookup"><span data-stu-id="70b37-184">Integer division by zero always throws a <xref:System.DivideByZeroException>.</span></span>

<span data-ttu-id="70b37-185">整数の算術オーバーフローの場合、オーバーフロー チェック コンテキスト ([checked または unchecked](../keywords/checked-and-unchecked.md)) が結果の動作を制御します。</span><span class="sxs-lookup"><span data-stu-id="70b37-185">In case of integer arithmetic overflow, an overflow checking context, which can be [checked or unchecked](../keywords/checked-and-unchecked.md), controls the resulting behavior:</span></span>

- <span data-ttu-id="70b37-186">checked コンテキストでは、定数式でオーバーフローが発生すると、コンパイル時エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="70b37-186">In a checked context, if overflow happens in a constant expression, a compile-time error occurs.</span></span> <span data-ttu-id="70b37-187">それ以外の場合は、実行時に演算が実行されると <xref:System.OverflowException> がスローされます。</span><span class="sxs-lookup"><span data-stu-id="70b37-187">Otherwise, when the operation is performed at run time, an <xref:System.OverflowException> is thrown.</span></span>
- <span data-ttu-id="70b37-188">unchecked コンテキストでは、結果の格納先の型に収まらない上位ビットが破棄されて、結果が切り詰められます。</span><span class="sxs-lookup"><span data-stu-id="70b37-188">In an unchecked context, the result is truncated by discarding any high-order bits that don't fit in the destination type.</span></span>

<span data-ttu-id="70b37-189">[checked と unchecked](../keywords/checked-and-unchecked.md) のステートメントとともに、`checked` 演算子と `unchecked` 演算子を使用して、式が評価されるオーバーフロー チェック コンテキストを制御することができます。</span><span class="sxs-lookup"><span data-stu-id="70b37-189">Along with the [checked and unchecked](../keywords/checked-and-unchecked.md) statements, you can use the `checked` and `unchecked` operators to control the overflow checking context, in which an expression is evaluated:</span></span>

[!code-csharp-interactive[checked and unchecked](~/samples/snippets/csharp/language-reference/operators/ArithmeticOperators.cs#CheckedUnchecked)]

<span data-ttu-id="70b37-190">既定では、算術演算は *unchecked* コンテキストで発生します。</span><span class="sxs-lookup"><span data-stu-id="70b37-190">By default, arithmetic operations occur in an *unchecked* context.</span></span>

### <a name="floating-point-arithmetic-overflow"></a><span data-ttu-id="70b37-191">浮動小数点演算のオーバーフロー</span><span class="sxs-lookup"><span data-stu-id="70b37-191">Floating-point arithmetic overflow</span></span>

<span data-ttu-id="70b37-192">`float` 型と`double` 型を使用した算術演算では、例外はスローされません。</span><span class="sxs-lookup"><span data-stu-id="70b37-192">Arithmetic operations with the `float` and `double` types never throw an exception.</span></span> <span data-ttu-id="70b37-193">これらの型を使用した算術演算の結果は、無限および数値ではないことを表す特殊な値のいずれかになる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="70b37-193">The result of arithmetic operations with those types can be one of special values that represent infinity and not-a-number:</span></span>

[!code-csharp-interactive[double non-finite values](~/samples/snippets/csharp/language-reference/operators/ArithmeticOperators.cs#FloatingPointOverflow)]

<span data-ttu-id="70b37-194">`decimal` 型のオペランドの場合、算術オーバーフローは常に <xref:System.OverflowException> をスローし、0 による除算は常に <xref:System.DivideByZeroException> をスローします。</span><span class="sxs-lookup"><span data-stu-id="70b37-194">For the operands of the `decimal` type, arithmetic overflow always throws an <xref:System.OverflowException> and division by zero always throws a <xref:System.DivideByZeroException>.</span></span>

## <a name="round-off-errors"></a><span data-ttu-id="70b37-195">丸め誤差</span><span class="sxs-lookup"><span data-stu-id="70b37-195">Round-off errors</span></span>

<span data-ttu-id="70b37-196">実数の浮動小数点表記と浮動小数点演算の一般的な制限事項により、浮動小数点型を使った計算で丸め誤差が生じる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="70b37-196">Because of general limitations of the floating-point representation of real numbers and floating-point arithmetic, the round-off errors might occur in calculations with floating-point types.</span></span> <span data-ttu-id="70b37-197">つまり、式の生成された結果が、予期した数学的結果と異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="70b37-197">That is, the produced result of an expression might differ from the expected mathematical result.</span></span> <span data-ttu-id="70b37-198">次の例は、こうしたいくつかのケースを示しています。</span><span class="sxs-lookup"><span data-stu-id="70b37-198">The following example demonstrates several such cases:</span></span>

[!code-csharp-interactive[round-off errors](~/samples/snippets/csharp/language-reference/operators/ArithmeticOperators.cs#RoundOffErrors)]

<span data-ttu-id="70b37-199">詳細については、[System.Double](/dotnet/api/system.double#remarks)、[System.Single](/dotnet/api/system.single#remarks)、または [System.Decimal](/dotnet/api/system.decimal#remarks) の各ページの解説を参照してください。</span><span class="sxs-lookup"><span data-stu-id="70b37-199">For more information, see remarks at [System.Double](/dotnet/api/system.double#remarks), [System.Single](/dotnet/api/system.single#remarks), or [System.Decimal](/dotnet/api/system.decimal#remarks) reference pages.</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="70b37-200">演算子のオーバーロード可/不可</span><span class="sxs-lookup"><span data-stu-id="70b37-200">Operator overloadability</span></span>

<span data-ttu-id="70b37-201">ユーザー定義型は、単項算術演算子 (`++`、`--`、`+`、`-`) と 2 項算術演算子 (`*`、`/`、`%`、`+`、`-`) を[オーバーロード](../keywords/operator.md)できます。</span><span class="sxs-lookup"><span data-stu-id="70b37-201">User-defined types can [overload](../keywords/operator.md) the unary (`++`, `--`, `+`, and `-`) and binary (`*`, `/`, `%`, `+`, and `-`) arithmetic operators.</span></span> <span data-ttu-id="70b37-202">2 項演算子をオーバーロードすると、対応する複合代入演算子も暗黙的にオーバーロードされます。</span><span class="sxs-lookup"><span data-stu-id="70b37-202">When a binary operator is overloaded, the corresponding compound assignment operator is also implicitly overloaded.</span></span> <span data-ttu-id="70b37-203">ユーザー定義型は、複合代入演算子を明示的にオーバーロードすることはできません。</span><span class="sxs-lookup"><span data-stu-id="70b37-203">A user-defined type cannot explicitly overload a compound assignment operator.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="70b37-204">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="70b37-204">C# language specification</span></span>

<span data-ttu-id="70b37-205">詳細については、「[C# 言語仕様](~/_csharplang/spec/introduction.md)」の次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="70b37-205">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="70b37-206">後置インクリメント演算子と後置デクリメント演算子</span><span class="sxs-lookup"><span data-stu-id="70b37-206">Postfix increment and decrement operators</span></span>](~/_csharplang/spec/expressions.md#postfix-increment-and-decrement-operators)
- [<span data-ttu-id="70b37-207">前置インクリメント演算子と前置デクリメント演算子</span><span class="sxs-lookup"><span data-stu-id="70b37-207">Prefix increment and decrement operators</span></span>](~/_csharplang/spec/expressions.md#prefix-increment-and-decrement-operators)
- [<span data-ttu-id="70b37-208">単項プラス演算子</span><span class="sxs-lookup"><span data-stu-id="70b37-208">Unary plus operator</span></span>](~/_csharplang/spec/expressions.md#unary-plus-operator)
- [<span data-ttu-id="70b37-209">単項マイナス演算子</span><span class="sxs-lookup"><span data-stu-id="70b37-209">Unary minus operator</span></span>](~/_csharplang/spec/expressions.md#unary-minus-operator)
- [<span data-ttu-id="70b37-210">乗算演算子</span><span class="sxs-lookup"><span data-stu-id="70b37-210">Multiplication operator</span></span>](~/_csharplang/spec/expressions.md#multiplication-operator)
- [<span data-ttu-id="70b37-211">除算演算子</span><span class="sxs-lookup"><span data-stu-id="70b37-211">Division operator</span></span>](~/_csharplang/spec/expressions.md#division-operator)
- [<span data-ttu-id="70b37-212">剰余演算子</span><span class="sxs-lookup"><span data-stu-id="70b37-212">Remainder operator</span></span>](~/_csharplang/spec/expressions.md#remainder-operator)
- [<span data-ttu-id="70b37-213">加算演算子</span><span class="sxs-lookup"><span data-stu-id="70b37-213">Addition operator</span></span>](~/_csharplang/spec/expressions.md#addition-operator)
- [<span data-ttu-id="70b37-214">減算演算子</span><span class="sxs-lookup"><span data-stu-id="70b37-214">Subtraction operator</span></span>](~/_csharplang/spec/expressions.md#subtraction-operator)
- [<span data-ttu-id="70b37-215">複合代入</span><span class="sxs-lookup"><span data-stu-id="70b37-215">Compound assignment</span></span>](~/_csharplang/spec/expressions.md#compound-assignment)
- [<span data-ttu-id="70b37-216">checked 演算子と unchecked 演算子</span><span class="sxs-lookup"><span data-stu-id="70b37-216">The checked and unchecked operators</span></span>](~/_csharplang/spec/expressions.md#the-checked-and-unchecked-operators)

## <a name="see-also"></a><span data-ttu-id="70b37-217">関連項目</span><span class="sxs-lookup"><span data-stu-id="70b37-217">See also</span></span>

- [<span data-ttu-id="70b37-218">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="70b37-218">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="70b37-219">C# プログラミングガイド</span><span class="sxs-lookup"><span data-stu-id="70b37-219">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="70b37-220">C# 演算子</span><span class="sxs-lookup"><span data-stu-id="70b37-220">C# Operators</span></span>](index.md)
- <xref:System.Math?displayProperty=nameWithType>
- <xref:System.MathF?displayProperty=nameWithType>
- [<span data-ttu-id="70b37-221">.NET における数値</span><span class="sxs-lookup"><span data-stu-id="70b37-221">Numerics in .NET</span></span>](../../../standard/numerics.md)
