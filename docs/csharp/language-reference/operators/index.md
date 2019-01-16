---
title: C# 演算子
ms.date: 04/04/2018
f1_keywords:
- cs.operators
helpviewer_keywords:
- boolean operators [C#]
- expressions [C#], operators
- logical operators [C#]
- operators [C#]
- Visual C#, operators
- indirection operators [C#]
- assignment operators [C#]
- shift operators [C#]
- relational operators [C#]
- bitwise operators [C#]
- address operators [C#]
- keywords [C#], operators
- arithmetic operators [C#]
ms.assetid: 0301e31f-22ad-49af-ac3c-d5eae7f0ac43
ms.openlocfilehash: 6380fa4ec99f598be0d01db1061900520e94d5f1
ms.sourcegitcommit: 5c36aaa8299a2437c155700c810585aff19edbec
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/16/2019
ms.locfileid: "54333409"
---
# <a name="c-operators"></a><span data-ttu-id="0d030-102">C# 演算子</span><span class="sxs-lookup"><span data-stu-id="0d030-102">C# operators</span></span>

<span data-ttu-id="0d030-103">C# には、多くの演算子が用意されています。演算子とは、式で実行する演算 (数値演算、インデックス作成、関数呼び出しなど) を指定する記号のことです。</span><span class="sxs-lookup"><span data-stu-id="0d030-103">C# provides many operators, which are symbols that specify which operations (math, indexing, function call, etc.) to perform in an expression.</span></span> <span data-ttu-id="0d030-104">多くの演算子は、ユーザー定義型に適用する際に[オーバーロード](../../programming-guide/statements-expressions-operators/overloadable-operators.md)して、その意味を変更できます。</span><span class="sxs-lookup"><span data-stu-id="0d030-104">You can [overload](../../programming-guide/statements-expressions-operators/overloadable-operators.md) many operators to change their meaning when applied to a user-defined type.</span></span>

<span data-ttu-id="0d030-105">整数型に対する演算 (`==`、`!=`、`<`、`>`、`&`、`|`) は、通常、列挙型 (`enum`) で使用できます。</span><span class="sxs-lookup"><span data-stu-id="0d030-105">Operations on integral types (such as `==`, `!=`, `<`, `>`, `&`, `|`) are generally allowed on enumeration (`enum`) types.</span></span>

<span data-ttu-id="0d030-106">ここでは、C# の演算子を優先順位の高い順に示します。</span><span class="sxs-lookup"><span data-stu-id="0d030-106">The sections below list the C# operators starting with the highest precedence to the lowest.</span></span> <span data-ttu-id="0d030-107">各セクションの演算子の優先順位は同じです。</span><span class="sxs-lookup"><span data-stu-id="0d030-107">The operators within each section share the same precedence level.</span></span>

## <a name="primary-operators"></a><span data-ttu-id="0d030-108">主な演算子</span><span class="sxs-lookup"><span data-stu-id="0d030-108">Primary operators</span></span>

<span data-ttu-id="0d030-109">優先順位が最も高い演算子です。</span><span class="sxs-lookup"><span data-stu-id="0d030-109">These are the highest precedence operators.</span></span>

<span data-ttu-id="0d030-110">[x.y](member-access-operator.md) – メンバー アクセス。</span><span class="sxs-lookup"><span data-stu-id="0d030-110">[x.y](member-access-operator.md) – member access.</span></span>

<span data-ttu-id="0d030-111">[x?.y](null-conditional-operators.md) – null 条件付きのメンバー アクセス。</span><span class="sxs-lookup"><span data-stu-id="0d030-111">[x?.y](null-conditional-operators.md) – null conditional member access.</span></span> <span data-ttu-id="0d030-112">左側のオペランドが `null` に評価される場合に `null` を返します。</span><span class="sxs-lookup"><span data-stu-id="0d030-112">Returns `null` if the left-hand operand evaluates to `null`.</span></span>

<span data-ttu-id="0d030-113">[x?[y]](null-conditional-operators.md) - null 条件付きのインデックス アクセス。</span><span class="sxs-lookup"><span data-stu-id="0d030-113">[x?[y]](null-conditional-operators.md) - null conditional index access.</span></span> <span data-ttu-id="0d030-114">左側のオペランドが `null` に評価される場合に `null` を返します。</span><span class="sxs-lookup"><span data-stu-id="0d030-114">Returns `null` if the left-hand operand evaluates to `null`.</span></span>

<span data-ttu-id="0d030-115">[f(x)](invocation-operator.md) – 関数の呼び出し。</span><span class="sxs-lookup"><span data-stu-id="0d030-115">[f(x)](invocation-operator.md) – function invocation.</span></span>

<span data-ttu-id="0d030-116">[a&#91;x&#93;](index-operator.md) – 集約オブジェクトのインデックス作成。</span><span class="sxs-lookup"><span data-stu-id="0d030-116">[a&#91;x&#93;](index-operator.md) – aggregate object indexing.</span></span>

<span data-ttu-id="0d030-117">[x++](increment-operator.md) – 後置インクリメント。</span><span class="sxs-lookup"><span data-stu-id="0d030-117">[x++](increment-operator.md) – postfix increment.</span></span> <span data-ttu-id="0d030-118">x の値を返した後、1 大きくなった (通常は整数 1 が加算された) x の値で格納場所を更新します。</span><span class="sxs-lookup"><span data-stu-id="0d030-118">Returns the value of x and then updates the storage location with the value of x that is one greater (typically adds the integer 1).</span></span>

<span data-ttu-id="0d030-119">[x--](decrement-operator.md) – 後置デクリメント。</span><span class="sxs-lookup"><span data-stu-id="0d030-119">[x--](decrement-operator.md) –  postfix decrement.</span></span> <span data-ttu-id="0d030-120">x の値を返した後、1 小さくなった (通常は整数 1 が減算された) x の値で格納場所を更新します。</span><span class="sxs-lookup"><span data-stu-id="0d030-120">Returns the value of x and then updates the storage location with the value of x that is one less (typically subtracts the integer 1).</span></span>

<span data-ttu-id="0d030-121">[new](../keywords/new-operator.md) – 型のインスタンス化。</span><span class="sxs-lookup"><span data-stu-id="0d030-121">[new](../keywords/new-operator.md) – type instantiation.</span></span>

<span data-ttu-id="0d030-122">[typeof](../keywords/typeof.md) – オペランドを表す <xref:System.Type> オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="0d030-122">[typeof](../keywords/typeof.md) – returns the <xref:System.Type> object representing the operand.</span></span>

<span data-ttu-id="0d030-123">[checked](../keywords/checked.md) – 整数演算のオーバーフロー チェックを有効にします。</span><span class="sxs-lookup"><span data-stu-id="0d030-123">[checked](../keywords/checked.md) – enables overflow checking for integer operations.</span></span>

<span data-ttu-id="0d030-124">[unchecked](../keywords/unchecked.md) – 整数演算のオーバーフロー チェックを無効にします。</span><span class="sxs-lookup"><span data-stu-id="0d030-124">[unchecked](../keywords/unchecked.md) – disables overflow checking for integer operations.</span></span> <span data-ttu-id="0d030-125">これがコンパイラの既定の動作です。</span><span class="sxs-lookup"><span data-stu-id="0d030-125">This is the default compiler behavior.</span></span>

<span data-ttu-id="0d030-126">[default(T)](../../programming-guide/statements-expressions-operators/default-value-expressions.md) – 型 T の既定の値を生成します。</span><span class="sxs-lookup"><span data-stu-id="0d030-126">[default(T)](../../programming-guide/statements-expressions-operators/default-value-expressions.md) – produces the default value of type T.</span></span>

<span data-ttu-id="0d030-127">[Delegate](../../programming-guide/statements-expressions-operators/anonymous-methods.md) – delegate インスタンスを宣言して返します。</span><span class="sxs-lookup"><span data-stu-id="0d030-127">[delegate](../../programming-guide/statements-expressions-operators/anonymous-methods.md) – declares and returns a delegate instance.</span></span>

<span data-ttu-id="0d030-128">[sizeof](../keywords/sizeof.md) – 型オペランドのサイズをバイト単位で返します。</span><span class="sxs-lookup"><span data-stu-id="0d030-128">[sizeof](../keywords/sizeof.md) – returns the size in bytes of the type operand.</span></span>

<span data-ttu-id="0d030-129">[->](dereference-operator.md) – メンバー アクセスと組み合わせてポインターを逆参照します。</span><span class="sxs-lookup"><span data-stu-id="0d030-129">[->](dereference-operator.md) – pointer dereferencing combined with member access.</span></span>

## <a name="unary-operators"></a><span data-ttu-id="0d030-130">単項演算子</span><span class="sxs-lookup"><span data-stu-id="0d030-130">Unary operators</span></span>

<span data-ttu-id="0d030-131">これらの演算子は、前のセクションより優先順位が低く、次のセクションより優先順位が高くなります。</span><span class="sxs-lookup"><span data-stu-id="0d030-131">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="0d030-132">[+x](addition-operator.md) – x の値を返します。</span><span class="sxs-lookup"><span data-stu-id="0d030-132">[+x](addition-operator.md) – returns the value of x.</span></span>

<span data-ttu-id="0d030-133">[-x](subtraction-operator.md) – 数値の否定。</span><span class="sxs-lookup"><span data-stu-id="0d030-133">[-x](subtraction-operator.md) – numeric negation.</span></span>

<span data-ttu-id="0d030-134">[\!x](logical-negation-operator.md) – 論理否定。</span><span class="sxs-lookup"><span data-stu-id="0d030-134">[\!x](logical-negation-operator.md) – logical negation.</span></span>

<span data-ttu-id="0d030-135">[~x](bitwise-complement-operator.md) – ビットごとの補数。</span><span class="sxs-lookup"><span data-stu-id="0d030-135">[~x](bitwise-complement-operator.md) – bitwise complement.</span></span>

<span data-ttu-id="0d030-136">[++x](increment-operator.md) – 前置インクリメント。</span><span class="sxs-lookup"><span data-stu-id="0d030-136">[++x](increment-operator.md) – prefix increment.</span></span> <span data-ttu-id="0d030-137">1 大きくなった (通常は整数 1 が加算された) x の値で格納場所を更新した後に x の値を返します。</span><span class="sxs-lookup"><span data-stu-id="0d030-137">Returns the value of x after updating the storage location with the value of x that is one greater (typically adds the integer 1).</span></span>

<span data-ttu-id="0d030-138">[--x](decrement-operator.md) – 前置デクリメント。</span><span class="sxs-lookup"><span data-stu-id="0d030-138">[--x](decrement-operator.md) – prefix decrement.</span></span> <span data-ttu-id="0d030-139">1 小さくなった (通常は整数 1 が減算された) x の値で格納場所を更新した後に x の値を返します。</span><span class="sxs-lookup"><span data-stu-id="0d030-139">Returns the value of x after updating the storage location with the value of x that is one less (typically subtracts the integer 1).</span></span>

<span data-ttu-id="0d030-140">[(T)x](invocation-operator.md) – 型キャスト。</span><span class="sxs-lookup"><span data-stu-id="0d030-140">[(T)x](invocation-operator.md) – type casting.</span></span>

<span data-ttu-id="0d030-141">[await](../keywords/await.md) – `Task` を待機します。</span><span class="sxs-lookup"><span data-stu-id="0d030-141">[await](../keywords/await.md) – awaits a `Task`.</span></span>

<span data-ttu-id="0d030-142">[&x](and-operator.md) – アドレス。</span><span class="sxs-lookup"><span data-stu-id="0d030-142">[&x](and-operator.md) – address of.</span></span>

<span data-ttu-id="0d030-143">[\*x](multiplication-operator.md) – 逆参照。</span><span class="sxs-lookup"><span data-stu-id="0d030-143">[\*x](multiplication-operator.md) – dereferencing.</span></span>

## <a name="multiplicative-operators"></a><span data-ttu-id="0d030-144">乗算演算子</span><span class="sxs-lookup"><span data-stu-id="0d030-144">Multiplicative operators</span></span>

<span data-ttu-id="0d030-145">これらの演算子は、前のセクションより優先順位が低く、次のセクションより優先順位が高くなります。</span><span class="sxs-lookup"><span data-stu-id="0d030-145">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="0d030-146">[x \* y](multiplication-operator.md) – 乗算。</span><span class="sxs-lookup"><span data-stu-id="0d030-146">[x \* y](multiplication-operator.md) – multiplication.</span></span>

<span data-ttu-id="0d030-147">[x / y](division-operator.md) – 除算。</span><span class="sxs-lookup"><span data-stu-id="0d030-147">[x / y](division-operator.md) – division.</span></span> <span data-ttu-id="0d030-148">オペランドが整数の場合、結果は 0 に近い整数になるように切り捨てられます (例: `-7 / 2 is -3`)。</span><span class="sxs-lookup"><span data-stu-id="0d030-148">If the operands are integers, the result is an integer truncated toward zero (for example, `-7 / 2 is -3`).</span></span>

<span data-ttu-id="0d030-149">[x % y](remainder-operator.md) – 剰余。</span><span class="sxs-lookup"><span data-stu-id="0d030-149">[x % y](remainder-operator.md) – remainder.</span></span> <span data-ttu-id="0d030-150">オペランドが整数の場合、x を y で除算した剰余を返します。</span><span class="sxs-lookup"><span data-stu-id="0d030-150">If the operands are integers, this returns the remainder of dividing x by y.</span></span>  <span data-ttu-id="0d030-151">`q = x / y` で `r = x % y` の場合、`x = q * y + r` になります。</span><span class="sxs-lookup"><span data-stu-id="0d030-151">If `q = x / y` and `r = x % y`, then `x = q * y + r`.</span></span>

## <a name="additive-operators"></a><span data-ttu-id="0d030-152">加法演算子</span><span class="sxs-lookup"><span data-stu-id="0d030-152">Additive operators</span></span>

<span data-ttu-id="0d030-153">これらの演算子は、前のセクションより優先順位が低く、次のセクションより優先順位が高くなります。</span><span class="sxs-lookup"><span data-stu-id="0d030-153">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="0d030-154">[x + y](addition-operator.md) – 加算。</span><span class="sxs-lookup"><span data-stu-id="0d030-154">[x + y](addition-operator.md) – addition.</span></span>

<span data-ttu-id="0d030-155">[x – y](subtraction-operator.md) – 減算。</span><span class="sxs-lookup"><span data-stu-id="0d030-155">[x – y](subtraction-operator.md) – subtraction.</span></span>

## <a name="shift-operators"></a><span data-ttu-id="0d030-156">シフト演算子</span><span class="sxs-lookup"><span data-stu-id="0d030-156">Shift operators</span></span>

<span data-ttu-id="0d030-157">これらの演算子は、前のセクションより優先順位が低く、次のセクションより優先順位が高くなります。</span><span class="sxs-lookup"><span data-stu-id="0d030-157">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="0d030-158">[x <\<  y](left-shift-operator.md) – ビットを左へシフトし、右側には 0 を格納します。</span><span class="sxs-lookup"><span data-stu-id="0d030-158">[x <\<  y](left-shift-operator.md) – shift bits left and fill with zero on the right.</span></span>

<span data-ttu-id="0d030-159">[x >> y](right-shift-operator.md) – ビットを右へシフトします。</span><span class="sxs-lookup"><span data-stu-id="0d030-159">[x >> y](right-shift-operator.md) – shift bits right.</span></span> <span data-ttu-id="0d030-160">左側のオペランドが `int` または `long` の場合、左側のビットには符号ビットが格納されます。</span><span class="sxs-lookup"><span data-stu-id="0d030-160">If the left operand is `int` or `long`, then left bits are filled with the sign bit.</span></span> <span data-ttu-id="0d030-161">左側のオペランドが `uint` または `ulong` の場合、左側のビットには 0 が格納されます。</span><span class="sxs-lookup"><span data-stu-id="0d030-161">If the left operand is `uint` or `ulong`, then left bits are filled with zero.</span></span>

## <a name="relational-and-type-testing-operators"></a><span data-ttu-id="0d030-162">関係演算子と型検査演算子</span><span class="sxs-lookup"><span data-stu-id="0d030-162">Relational and type-testing operators</span></span>

<span data-ttu-id="0d030-163">これらの演算子は、前のセクションより優先順位が低く、次のセクションより優先順位が高くなります。</span><span class="sxs-lookup"><span data-stu-id="0d030-163">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="0d030-164">[x \< y](less-than-operator.md) – より小さい (x が y より小さい場合は true)。</span><span class="sxs-lookup"><span data-stu-id="0d030-164">[x \< y](less-than-operator.md) – less than (true if x is less than y).</span></span>

<span data-ttu-id="0d030-165">[x > y](greater-than-operator.md) – より大きい (x が y より大きい場合は true)。</span><span class="sxs-lookup"><span data-stu-id="0d030-165">[x > y](greater-than-operator.md) – greater than (true if x is greater than y).</span></span>

<span data-ttu-id="0d030-166">[x \<= y](less-than-equal-operator.md) – 以下。</span><span class="sxs-lookup"><span data-stu-id="0d030-166">[x \<= y](less-than-equal-operator.md) – less than or equal to.</span></span>

<span data-ttu-id="0d030-167">[x >= y](greater-than-equal-operator.md) – 以上。</span><span class="sxs-lookup"><span data-stu-id="0d030-167">[x >= y](greater-than-equal-operator.md) – greater than or equal to.</span></span>

<span data-ttu-id="0d030-168">[is](../keywords/is.md) – 型の互換性。</span><span class="sxs-lookup"><span data-stu-id="0d030-168">[is](../keywords/is.md) – type compatibility.</span></span> <span data-ttu-id="0d030-169">評価される左側のオペランドを右側のオペランドで指定された型 (静的な型) にキャストできる場合は、true を返します。</span><span class="sxs-lookup"><span data-stu-id="0d030-169">Returns true if the evaluated left operand can be cast to the type specified in the right operand (a static type).</span></span>

<span data-ttu-id="0d030-170">[as](../keywords/as.md) – 型変換。</span><span class="sxs-lookup"><span data-stu-id="0d030-170">[as](../keywords/as.md) – type conversion.</span></span> <span data-ttu-id="0d030-171">左側のオペランドを右側のオペランドで指定された型 (静的な型) にキャストして返します。ただし、`(T)x` が例外をスローした場合、`as` は `null` を返します。</span><span class="sxs-lookup"><span data-stu-id="0d030-171">Returns the left operand cast to the type specified by the right operand (a static type), but `as` returns `null` where `(T)x` would throw an exception.</span></span>

## <a name="equality-operators"></a><span data-ttu-id="0d030-172">等値演算子</span><span class="sxs-lookup"><span data-stu-id="0d030-172">Equality operators</span></span>

<span data-ttu-id="0d030-173">これらの演算子は、前のセクションより優先順位が低く、次のセクションより優先順位が高くなります。</span><span class="sxs-lookup"><span data-stu-id="0d030-173">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="0d030-174">[x == y](equality-comparison-operator.md) – 等価比較。</span><span class="sxs-lookup"><span data-stu-id="0d030-174">[x == y](equality-comparison-operator.md) – equality.</span></span> <span data-ttu-id="0d030-175">既定では、`string` 以外の参照型の場合、参照の等価性を返します (等価テスト)。</span><span class="sxs-lookup"><span data-stu-id="0d030-175">By default, for reference types other than `string`, this returns reference equality (identity test).</span></span> <span data-ttu-id="0d030-176">ただし、型は `==` をオーバーロードできるため、同一性のテストが目的の場合は `object` で `ReferenceEquals` メソッドを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0d030-176">However, types can overload `==`, so if your intent is to test identity, it is best to use the `ReferenceEquals` method on `object`.</span></span>

<span data-ttu-id="0d030-177">[x != y](not-equal-operator.md) – 等しくない。</span><span class="sxs-lookup"><span data-stu-id="0d030-177">[x != y](not-equal-operator.md) – not equal.</span></span> <span data-ttu-id="0d030-178">`==` のコメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0d030-178">See comment for `==`.</span></span> <span data-ttu-id="0d030-179">型が `==` をオーバーロードする場合は、`!=` をオーバーロードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0d030-179">If a type overloads `==`, then it must overload `!=`.</span></span>

## <a name="logical-and-operator"></a><span data-ttu-id="0d030-180">論理 AND 演算子</span><span class="sxs-lookup"><span data-stu-id="0d030-180">Logical AND operator</span></span>

<span data-ttu-id="0d030-181">この演算子は、前のセクションより優先順位が低く、次のセクションより優先順位が高くなります。</span><span class="sxs-lookup"><span data-stu-id="0d030-181">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="0d030-182">[x & y](and-operator.md) – 論理またはビットごとの AND。</span><span class="sxs-lookup"><span data-stu-id="0d030-182">[x & y](and-operator.md) – logical or bitwise AND.</span></span> <span data-ttu-id="0d030-183">通常、整数型と `enum` 型で使用できます。</span><span class="sxs-lookup"><span data-stu-id="0d030-183">You can generally use this with integer types and `enum` types.</span></span>

## <a name="logical-xor-operator"></a><span data-ttu-id="0d030-184">論理 XOR 演算子</span><span class="sxs-lookup"><span data-stu-id="0d030-184">Logical XOR operator</span></span>

<span data-ttu-id="0d030-185">この演算子は、前のセクションより優先順位が低く、次のセクションより優先順位が高くなります。</span><span class="sxs-lookup"><span data-stu-id="0d030-185">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="0d030-186">[x ^ y](xor-operator.md) – 論理またはビットごとの XOR。</span><span class="sxs-lookup"><span data-stu-id="0d030-186">[x ^ y](xor-operator.md) – logical or bitwise XOR.</span></span> <span data-ttu-id="0d030-187">通常、整数型と `enum` 型で使用できます。</span><span class="sxs-lookup"><span data-stu-id="0d030-187">You can generally use this with integer types and `enum` types.</span></span>

## <a name="logical-or-operator"></a><span data-ttu-id="0d030-188">論理演算子 OR</span><span class="sxs-lookup"><span data-stu-id="0d030-188">Logical OR operator</span></span>

<span data-ttu-id="0d030-189">この演算子は、前のセクションより優先順位が低く、次のセクションより優先順位が高くなります。</span><span class="sxs-lookup"><span data-stu-id="0d030-189">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="0d030-190">[x &#124; y](or-operator.md) – 論理またはビットごとの OR。</span><span class="sxs-lookup"><span data-stu-id="0d030-190">[x &#124; y](or-operator.md) – logical or bitwise OR.</span></span> <span data-ttu-id="0d030-191">通常、整数型と `enum` 型で使用できます。</span><span class="sxs-lookup"><span data-stu-id="0d030-191">You can generally use this with integer types and `enum` types.</span></span>

## <a name="conditional-and-operator"></a><span data-ttu-id="0d030-192">条件 AND 演算子</span><span class="sxs-lookup"><span data-stu-id="0d030-192">Conditional AND operator</span></span>

<span data-ttu-id="0d030-193">この演算子は、前のセクションより優先順位が低く、次のセクションより優先順位が高くなります。</span><span class="sxs-lookup"><span data-stu-id="0d030-193">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="0d030-194">[x && y](conditional-and-operator.md) – 論理 AND。</span><span class="sxs-lookup"><span data-stu-id="0d030-194">[x && y](conditional-and-operator.md) – logical AND.</span></span> <span data-ttu-id="0d030-195">最初のオペランドが false に評価される場合、C# では 2 番目のオペランドが評価されません。</span><span class="sxs-lookup"><span data-stu-id="0d030-195">If the first operand evaluates to false, then C# does not evaluate the second operand.</span></span>

## <a name="conditional-or-operator"></a><span data-ttu-id="0d030-196">条件 OR 演算子</span><span class="sxs-lookup"><span data-stu-id="0d030-196">Conditional OR operator</span></span>

<span data-ttu-id="0d030-197">この演算子は、前のセクションより優先順位が低く、次のセクションより優先順位が高くなります。</span><span class="sxs-lookup"><span data-stu-id="0d030-197">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="0d030-198">[x &#124;&#124; y](conditional-or-operator.md) – 論理 OR。</span><span class="sxs-lookup"><span data-stu-id="0d030-198">[x &#124;&#124; y](conditional-or-operator.md) – logical OR.</span></span> <span data-ttu-id="0d030-199">最初のオペランドが true に評価される場合、C# では 2 番目のオペランドが評価されません。</span><span class="sxs-lookup"><span data-stu-id="0d030-199">If the first operand evaluates to true, then C# does not evaluate the second operand.</span></span>

## <a name="null-coalescing-operator"></a><span data-ttu-id="0d030-200">Null 合体演算子</span><span class="sxs-lookup"><span data-stu-id="0d030-200">Null-coalescing operator</span></span>

<span data-ttu-id="0d030-201">この演算子は、前のセクションより優先順位が低く、次のセクションより優先順位が高くなります。</span><span class="sxs-lookup"><span data-stu-id="0d030-201">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="0d030-202">[x ?? y](null-coalescing-operator.md) – `x` が `null` 以外の場合は x を返します。null の場合は `y` を返します。</span><span class="sxs-lookup"><span data-stu-id="0d030-202">[x ?? y](null-coalescing-operator.md) – returns `x` if it is non-`null`; otherwise, returns `y`.</span></span>

## <a name="conditional-operator"></a><span data-ttu-id="0d030-203">条件演算子</span><span class="sxs-lookup"><span data-stu-id="0d030-203">Conditional operator</span></span>

<span data-ttu-id="0d030-204">この演算子は、前のセクションより優先順位が低く、次のセクションより優先順位が高くなります。</span><span class="sxs-lookup"><span data-stu-id="0d030-204">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="0d030-205">[t ? x : y](conditional-operator.md) – テスト `t` が true に評価される場合は `x` を評価して返します。それ以外の場合は `y` を評価して返します。</span><span class="sxs-lookup"><span data-stu-id="0d030-205">[t ? x : y](conditional-operator.md) – if test `t` evaluates to true, then evaluate and return `x`; otherwise, evaluate and return `y`.</span></span>

## <a name="assignment-and-lambda-operators"></a><span data-ttu-id="0d030-206">代入演算子とラムダ演算子</span><span class="sxs-lookup"><span data-stu-id="0d030-206">Assignment and Lambda operators</span></span>

<span data-ttu-id="0d030-207">これらの演算子は、前のセクションより優先順位が低く、次のセクションより優先順位が高くなります。</span><span class="sxs-lookup"><span data-stu-id="0d030-207">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="0d030-208">[x = y](assignment-operator.md) – 代入。</span><span class="sxs-lookup"><span data-stu-id="0d030-208">[x = y](assignment-operator.md) – assignment.</span></span>

<span data-ttu-id="0d030-209">[x += y](addition-assignment-operator.md) – インクリメント。</span><span class="sxs-lookup"><span data-stu-id="0d030-209">[x += y](addition-assignment-operator.md) – increment.</span></span> <span data-ttu-id="0d030-210">`y` の値を `x` の値に加算した結果を `x` に格納し、新しい値を返します。</span><span class="sxs-lookup"><span data-stu-id="0d030-210">Add the value of `y` to the value of `x`, store the result in `x`, and return the new value.</span></span> <span data-ttu-id="0d030-211">`x` が `event` を指定した場合、`y` は、C# によってイベント ハンドラーとして追加される適切な関数である必要があります。</span><span class="sxs-lookup"><span data-stu-id="0d030-211">If `x` designates an `event`, then `y` must be an appropriate function that C# adds as an event handler.</span></span>

<span data-ttu-id="0d030-212">[x -= y](subtraction-assignment-operator.md) – デクリメント。</span><span class="sxs-lookup"><span data-stu-id="0d030-212">[x -= y](subtraction-assignment-operator.md) – decrement.</span></span> <span data-ttu-id="0d030-213">`y` の値を `x` の値から減算した結果を `x` に格納し、新しい値を返します。</span><span class="sxs-lookup"><span data-stu-id="0d030-213">Subtract the value of `y` from the value of `x`, store the result in `x`, and return the new value.</span></span> <span data-ttu-id="0d030-214">`x` が `event` を指定した場合、`y` は、C# によってイベント ハンドラーとして削除される適切な関数である必要があります。</span><span class="sxs-lookup"><span data-stu-id="0d030-214">If `x` designates an `event`, then `y` must be an appropriate function that C# removes as an event handler</span></span>

<span data-ttu-id="0d030-215">[x \*= y](multiplication-assignment-operator.md) – 乗算代入。</span><span class="sxs-lookup"><span data-stu-id="0d030-215">[x \*= y](multiplication-assignment-operator.md) – multiplication assignment.</span></span> <span data-ttu-id="0d030-216">`y` の値を `x` の値に乗算した結果を `x` に格納し、新しい値を返します。</span><span class="sxs-lookup"><span data-stu-id="0d030-216">Multiply the value of `y` to the value of `x`, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="0d030-217">[x /= y](division-assignment-operator.md) – 除算代入。</span><span class="sxs-lookup"><span data-stu-id="0d030-217">[x /= y](division-assignment-operator.md) – division assignment.</span></span> <span data-ttu-id="0d030-218">`x` の値を `y` の値で除算した結果を `x` に格納し、新しい値を返します。</span><span class="sxs-lookup"><span data-stu-id="0d030-218">Divide the value of `x` by the value of `y`, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="0d030-219">[x %= y](remainder-assignment-operator.md) – 剰余代入。</span><span class="sxs-lookup"><span data-stu-id="0d030-219">[x %= y](remainder-assignment-operator.md) – remainder assignment.</span></span> <span data-ttu-id="0d030-220">`x` の値を `y` の値で除算した剰余を `x` に格納し、新しい値を返します。</span><span class="sxs-lookup"><span data-stu-id="0d030-220">Divide the value of `x` by the value of `y`, store the remainder in `x`, and return the new value.</span></span>

<span data-ttu-id="0d030-221">[x &= y](and-assignment-operator.md) – AND 代入。</span><span class="sxs-lookup"><span data-stu-id="0d030-221">[x &= y](and-assignment-operator.md) – AND assignment.</span></span> <span data-ttu-id="0d030-222">`y` の値と `x` の値の AND 演算を行った結果を `x` に格納し、新しい値を返します。</span><span class="sxs-lookup"><span data-stu-id="0d030-222">AND the value of `y` with the value of `x`, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="0d030-223">[x &#124;= y](or-assignment-operator.md) – OR 代入。</span><span class="sxs-lookup"><span data-stu-id="0d030-223">[x &#124;= y](or-assignment-operator.md) – OR assignment.</span></span> <span data-ttu-id="0d030-224">`y` の値と `x` の値の OR 演算を行った結果を `x` に格納し、新しい値を返します。</span><span class="sxs-lookup"><span data-stu-id="0d030-224">OR the value of `y` with the value of `x`, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="0d030-225">[x ^= y](xor-assignment-operator.md) – XOR 代入。</span><span class="sxs-lookup"><span data-stu-id="0d030-225">[x ^= y](xor-assignment-operator.md) – XOR assignment.</span></span> <span data-ttu-id="0d030-226">`y` の値と `x` の値の XOR 演算を行った結果を `x` に格納し、新しい値を返します。</span><span class="sxs-lookup"><span data-stu-id="0d030-226">XOR the value of `y` with the value of `x`, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="0d030-227">[x <<= y](left-shift-assignment-operator.md) – 左シフト代入。</span><span class="sxs-lookup"><span data-stu-id="0d030-227">[x <<= y](left-shift-assignment-operator.md) – left-shift assignment.</span></span> <span data-ttu-id="0d030-228">`x` の値を `y` で指定した分だけ左へシフトした結果を `x` に格納し、新しい値を返します。</span><span class="sxs-lookup"><span data-stu-id="0d030-228">Shift the value of `x` left by `y` places, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="0d030-229">[x >>= y](right-shift-assignment-operator.md) – 右シフト代入。</span><span class="sxs-lookup"><span data-stu-id="0d030-229">[x >>= y](right-shift-assignment-operator.md) – right-shift assignment.</span></span> <span data-ttu-id="0d030-230">`x` の値を `y` で指定した分だけ右へシフトした結果を `x` に格納し、新しい値を返します。</span><span class="sxs-lookup"><span data-stu-id="0d030-230">Shift the value of `x` right by `y` places, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="0d030-231">[=>](lambda-operator.md) – ラムダ宣言。</span><span class="sxs-lookup"><span data-stu-id="0d030-231">[=>](lambda-operator.md) – lambda declaration.</span></span>

## <a name="arithmetic-overflow"></a><span data-ttu-id="0d030-232">算術オーバーフロー</span><span class="sxs-lookup"><span data-stu-id="0d030-232">Arithmetic overflow</span></span>

<span data-ttu-id="0d030-233">算術演算子 ([+](addition-operator.md)、[-](subtraction-operator.md)、[\*](multiplication-operator.md)、[/](division-operator.md)) を実行すると、結果が数値型の有効な値の範囲を超えることがあります。</span><span class="sxs-lookup"><span data-stu-id="0d030-233">The arithmetic operators ([+](addition-operator.md), [-](subtraction-operator.md), [\*](multiplication-operator.md), [/](division-operator.md)) can produce results that are outside the range of possible values for the numeric type involved.</span></span> <span data-ttu-id="0d030-234">詳細については、各演算子に関するセクションを参照してください。概要は、以下のとおりです。</span><span class="sxs-lookup"><span data-stu-id="0d030-234">You should refer to the section on a particular operator for details, but in general:</span></span>

- <span data-ttu-id="0d030-235">整数の算術オーバーフローでは、<xref:System.OverflowException> がスローされるか、または結果の最上位ビットが破棄されます。</span><span class="sxs-lookup"><span data-stu-id="0d030-235">Integer arithmetic overflow either throws an <xref:System.OverflowException> or discards the most significant bits of the result.</span></span> <span data-ttu-id="0d030-236">0 による整数除算では、常に <xref:System.DivideByZeroException> がスローされます。</span><span class="sxs-lookup"><span data-stu-id="0d030-236">Integer division by zero always throws a <xref:System.DivideByZeroException>.</span></span>

   <span data-ttu-id="0d030-237">整数のオーバーフローが発生したときの対処方法は、実行コンテキスト ([checked または unchecked](../keywords/checked-and-unchecked.md)) によって異なります。</span><span class="sxs-lookup"><span data-stu-id="0d030-237">When integer overflow occurs, what happens depends on the execution context, which can be [checked or unchecked](../keywords/checked-and-unchecked.md).</span></span> <span data-ttu-id="0d030-238">checked コンテキストの場合は、<xref:System.OverflowException> がスローされます。</span><span class="sxs-lookup"><span data-stu-id="0d030-238">In a checked context, an <xref:System.OverflowException> is thrown.</span></span> <span data-ttu-id="0d030-239">unchecked コンテキストの場合は、結果の最上位ビットが破棄され、実行が続行されます。</span><span class="sxs-lookup"><span data-stu-id="0d030-239">In an unchecked context, the most significant bits of the result are discarded and execution continues.</span></span> <span data-ttu-id="0d030-240">このように、C# ではオーバーフローを処理するのか、それとも無視するのかをユーザーが選択できます。</span><span class="sxs-lookup"><span data-stu-id="0d030-240">Thus, C# gives you the choice of handling or ignoring overflow.</span></span> <span data-ttu-id="0d030-241">既定では、算術演算は *unchecked* コンテキストで発生します。</span><span class="sxs-lookup"><span data-stu-id="0d030-241">By default, arithmetic operations occur in an *unchecked* context.</span></span>

   <span data-ttu-id="0d030-242">算術演算の場合だけでなく、整数型から整数型へのキャスト ([long](../keywords/long.md) から [int](../keywords/int.md) へのキャストなど) でもオーバーフローは発生し、その場合も実行が checked または unchecked のいずれかによって対処が異なります。</span><span class="sxs-lookup"><span data-stu-id="0d030-242">In addition to the arithmetic operations, integral-type to integral-type casts can cause overflow (such as when you cast a [long](../keywords/long.md) to an [int](../keywords/int.md)), and are subject to checked or unchecked execution.</span></span> <span data-ttu-id="0d030-243">ただし、ビット処理演算子とシフト演算子ではオーバーフローは発生しません。</span><span class="sxs-lookup"><span data-stu-id="0d030-243">However, bitwise operators and shift operators never cause overflow.</span></span>

- <span data-ttu-id="0d030-244">浮動小数点数の算術オーバーフローまたは 0 による浮動小数点除算では、例外はスローされません。これは、浮動小数点型が IEEE 754 に基づいており、無限大および NaN (Not a Number) を表現できるためです。</span><span class="sxs-lookup"><span data-stu-id="0d030-244">Floating-point arithmetic overflow or division by zero never throws an exception, because floating-point types are based on IEEE 754 and so have provisions for representing infinity and NaN (Not a Number).</span></span>

- <span data-ttu-id="0d030-245">[小数](../keywords/decimal.md)の算術オーバーフローでは、常に <xref:System.OverflowException> がスローされます。</span><span class="sxs-lookup"><span data-stu-id="0d030-245">[Decimal](../keywords/decimal.md) arithmetic overflow always throws an <xref:System.OverflowException>.</span></span> <span data-ttu-id="0d030-246">0 による小数除算では、常に <xref:System.DivideByZeroException> がスローされます。</span><span class="sxs-lookup"><span data-stu-id="0d030-246">Decimal division by zero always throws a <xref:System.DivideByZeroException>.</span></span>

## <a name="see-also"></a><span data-ttu-id="0d030-247">関連項目</span><span class="sxs-lookup"><span data-stu-id="0d030-247">See also</span></span>

- [<span data-ttu-id="0d030-248">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="0d030-248">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="0d030-249">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="0d030-249">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="0d030-250">C#</span><span class="sxs-lookup"><span data-stu-id="0d030-250">C#</span></span>](../../index.md)
- [<span data-ttu-id="0d030-251">オーバーロードされた演算子</span><span class="sxs-lookup"><span data-stu-id="0d030-251">Overloadable Operators</span></span>](../../programming-guide/statements-expressions-operators/overloadable-operators.md)
- [<span data-ttu-id="0d030-252">C# のキーワード</span><span class="sxs-lookup"><span data-stu-id="0d030-252">C# Keywords</span></span>](../keywords/index.md)