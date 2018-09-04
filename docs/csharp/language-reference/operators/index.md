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
ms.openlocfilehash: 30e4942934e5d65b214d24a0948f70169d625485
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "43507250"
---
# <a name="c-operators"></a><span data-ttu-id="3ba9a-102">C# 演算子</span><span class="sxs-lookup"><span data-stu-id="3ba9a-102">C# Operators</span></span>
<span data-ttu-id="3ba9a-103">C# には、多くの演算子が用意されています。演算子とは、式で実行する演算 (数値演算、インデックス作成、関数呼び出しなど) を指定する記号のことです。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-103">C# provides many operators, which are symbols that specify which operations (math, indexing, function call, etc.) to perform in an expression.</span></span> <span data-ttu-id="3ba9a-104">多くの演算子は、ユーザー定義型に適用する際に[オーバーロード](../../../csharp/programming-guide/statements-expressions-operators/overloadable-operators.md)して、その意味を変更できます。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-104">You can [overload](../../../csharp/programming-guide/statements-expressions-operators/overloadable-operators.md) many operators to change their meaning when applied to a user-defined type.</span></span>  
  
 <span data-ttu-id="3ba9a-105">整数型に対する演算 (`==`、`!=`、`<`、`>`、`&`、`|`) は、通常、列挙型 (`enum`) で使用できます。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-105">Operations on integral types (such as `==`, `!=`, `<`, `>`, `&`, `|`) are generally allowed on enumeration (`enum`) types.</span></span>  
  
 <span data-ttu-id="3ba9a-106">ここでは、C# の演算子を優先順位の高い順に示します。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-106">The sections below list the C# operators starting with the highest precedence to the lowest.</span></span> <span data-ttu-id="3ba9a-107">各セクションの演算子の優先順位は同じです。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-107">The operators within each section share the same precedence level.</span></span>  
 
## <a name="primary-operators"></a><span data-ttu-id="3ba9a-108">主な演算子</span><span class="sxs-lookup"><span data-stu-id="3ba9a-108">Primary Operators</span></span>  
 <span data-ttu-id="3ba9a-109">優先順位が最も高い演算子です。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-109">These are the highest precedence operators.</span></span>
  
 <span data-ttu-id="3ba9a-110">[x.y](../../../csharp/language-reference/operators/member-access-operator.md) – メンバー アクセス。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-110">[x.y](../../../csharp/language-reference/operators/member-access-operator.md) – member access.</span></span>  
  
 <span data-ttu-id="3ba9a-111">[x?.y](../../../csharp/language-reference/operators/null-conditional-operators.md) – null 条件付きのメンバー アクセス。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-111">[x?.y](../../../csharp/language-reference/operators/null-conditional-operators.md) – null conditional member access.</span></span> <span data-ttu-id="3ba9a-112">左側のオペランドが `null` に評価される場合に `null` を返します。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-112">Returns `null` if the left-hand operand evaluates to `null`.</span></span>  
 
 <span data-ttu-id="3ba9a-113">[x?[y]](../../../csharp/language-reference/operators/null-conditional-operators.md) - null 条件付きのインデックス アクセス。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-113">[x?[y]](../../../csharp/language-reference/operators/null-conditional-operators.md) - null conditional index access.</span></span> <span data-ttu-id="3ba9a-114">左側のオペランドが `null` に評価される場合に `null` を返します。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-114">Returns `null` if the left-hand operand evaluates to `null`.</span></span>
 
 <span data-ttu-id="3ba9a-115">[f(x)](../../../csharp/language-reference/operators/invocation-operator.md) – 関数の呼び出し。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-115">[f(x)](../../../csharp/language-reference/operators/invocation-operator.md) – function invocation.</span></span>  
  
 <span data-ttu-id="3ba9a-116">[a&#91;x&#93;](../../../csharp/language-reference/operators/index-operator.md) – 集約オブジェクトのインデックス作成。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-116">[a&#91;x&#93;](../../../csharp/language-reference/operators/index-operator.md) – aggregate object indexing.</span></span>  
   
 <span data-ttu-id="3ba9a-117">[x++](../../../csharp/language-reference/operators/increment-operator.md) – 後置インクリメント。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-117">[x++](../../../csharp/language-reference/operators/increment-operator.md) – postfix increment.</span></span> <span data-ttu-id="3ba9a-118">x の値を返した後、1 大きくなった (通常は整数 1 が加算された) x の値で格納場所を更新します。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-118">Returns the value of x and then updates the storage location with the value of x that is one greater (typically adds the integer 1).</span></span>  
  
 <span data-ttu-id="3ba9a-119">[x--](../../../csharp/language-reference/operators/decrement-operator.md) – 後置デクリメント。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-119">[x--](../../../csharp/language-reference/operators/decrement-operator.md) –  postfix decrement.</span></span> <span data-ttu-id="3ba9a-120">x の値を返した後、1 小さくなった (通常は整数 1 が減算された) x の値で格納場所を更新します。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-120">Returns the value of x and then updates the storage location with the value of x that is one less (typically subtracts the integer 1).</span></span>  
  
 <span data-ttu-id="3ba9a-121">[new](../../../csharp/language-reference/keywords/new-operator.md) – 型のインスタンス化。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-121">[new](../../../csharp/language-reference/keywords/new-operator.md) – type instantiation.</span></span>  
  
 <span data-ttu-id="3ba9a-122">[typeof](../../../csharp/language-reference/keywords/typeof.md) – オペランドを表す <xref:System.Type> オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-122">[typeof](../../../csharp/language-reference/keywords/typeof.md) – returns the <xref:System.Type> object representing the operand.</span></span>  
  
 <span data-ttu-id="3ba9a-123">[checked](../../../csharp/language-reference/keywords/checked.md) – 整数演算のオーバーフロー チェックを有効にします。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-123">[checked](../../../csharp/language-reference/keywords/checked.md) – enables overflow checking for integer operations.</span></span>  
  
 <span data-ttu-id="3ba9a-124">[unchecked](../../../csharp/language-reference/keywords/unchecked.md) – 整数演算のオーバーフロー チェックを無効にします。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-124">[unchecked](../../../csharp/language-reference/keywords/unchecked.md) – disables overflow checking for integer operations.</span></span> <span data-ttu-id="3ba9a-125">これがコンパイラの既定の動作です。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-125">This is the default compiler behavior.</span></span>  
  
 <span data-ttu-id="3ba9a-126">[default(T)](../../../csharp/programming-guide/statements-expressions-operators/default-value-expressions.md) – 型 T の既定の値を生成します。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-126">[default(T)](../../../csharp/programming-guide/statements-expressions-operators/default-value-expressions.md) – produces the default value of type T.</span></span>  
  
 <span data-ttu-id="3ba9a-127">[Delegate](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md) – delegate インスタンスを宣言して返します。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-127">[delegate](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md) – declares and returns a delegate instance.</span></span>  
  
 <span data-ttu-id="3ba9a-128">[sizeof](../../../csharp/language-reference/keywords/sizeof.md) – 型オペランドのサイズをバイト単位で返します。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-128">[sizeof](../../../csharp/language-reference/keywords/sizeof.md) – returns the size in bytes of the type operand.</span></span>  
  
 <span data-ttu-id="3ba9a-129">[->](../../../csharp/language-reference/operators/dereference-operator.md) – メンバー アクセスと組み合わせてポインターを逆参照します。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-129">[->](../../../csharp/language-reference/operators/dereference-operator.md) – pointer dereferencing combined with member access.</span></span>  
  
## <a name="unary-operators"></a><span data-ttu-id="3ba9a-130">単項演算子</span><span class="sxs-lookup"><span data-stu-id="3ba9a-130">Unary Operators</span></span>  
 <span data-ttu-id="3ba9a-131">これらの演算子は、前のセクションより優先順位が低く、次のセクションより優先順位が高くなります。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-131">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>  
  
 <span data-ttu-id="3ba9a-132">[+x](../../../csharp/language-reference/operators/addition-operator.md) – x の値を返します。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-132">[+x](../../../csharp/language-reference/operators/addition-operator.md) – returns the value of x.</span></span>  
  
 <span data-ttu-id="3ba9a-133">[-x](../../../csharp/language-reference/operators/subtraction-operator.md) – 数値の否定。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-133">[-x](../../../csharp/language-reference/operators/subtraction-operator.md) – numeric negation.</span></span>  
  
 <span data-ttu-id="3ba9a-134">[\!x](../../../csharp/language-reference/operators/logical-negation-operator.md) – 論理否定。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-134">[\!x](../../../csharp/language-reference/operators/logical-negation-operator.md) – logical negation.</span></span>  
  
 <span data-ttu-id="3ba9a-135">[~x](../../../csharp/language-reference/operators/bitwise-complement-operator.md) – ビットごとの補数。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-135">[~x](../../../csharp/language-reference/operators/bitwise-complement-operator.md) – bitwise complement.</span></span>  
  
 <span data-ttu-id="3ba9a-136">[++x](../../../csharp/language-reference/operators/increment-operator.md) – 前置インクリメント。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-136">[++x](../../../csharp/language-reference/operators/increment-operator.md) – prefix increment.</span></span> <span data-ttu-id="3ba9a-137">1 大きくなった (通常は整数 1 が加算された) x の値で格納場所を更新した後に x の値を返します。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-137">Returns the value of x after updating the storage location with the value of x that is one greater (typically adds the integer 1).</span></span>  
  
 <span data-ttu-id="3ba9a-138">[--x](../../../csharp/language-reference/operators/decrement-operator.md) – 前置デクリメント。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-138">[--x](../../../csharp/language-reference/operators/decrement-operator.md) – prefix decrement.</span></span> <span data-ttu-id="3ba9a-139">1 小さくなった (通常は整数 1 が減算された) x の値で格納場所を更新した後に x の値を返します。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-139">Returns the value of x after updating the storage location with the value of x that is one less (typically subtracts the integer 1).</span></span>  
  
 <span data-ttu-id="3ba9a-140">[(T)x](../../../csharp/language-reference/operators/invocation-operator.md) – 型キャスト。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-140">[(T)x](../../../csharp/language-reference/operators/invocation-operator.md) – type casting.</span></span>  
  
 <span data-ttu-id="3ba9a-141">[await](../../../csharp/language-reference/keywords/await.md) – `Task` を待機します。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-141">[await](../../../csharp/language-reference/keywords/await.md) – awaits a `Task`.</span></span>  
  
 <span data-ttu-id="3ba9a-142">[&x](../../../csharp/language-reference/operators/and-operator.md) – アドレス。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-142">[&x](../../../csharp/language-reference/operators/and-operator.md) – address of.</span></span>  
  
 <span data-ttu-id="3ba9a-143">[\*x](../../../csharp/language-reference/operators/multiplication-operator.md) – 逆参照。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-143">[\*x](../../../csharp/language-reference/operators/multiplication-operator.md) – dereferencing.</span></span>  
  
## <a name="multiplicative-operators"></a><span data-ttu-id="3ba9a-144">乗算演算子</span><span class="sxs-lookup"><span data-stu-id="3ba9a-144">Multiplicative Operators</span></span>  
 <span data-ttu-id="3ba9a-145">これらの演算子は、前のセクションより優先順位が低く、次のセクションより優先順位が高くなります。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-145">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>  
  
 <span data-ttu-id="3ba9a-146">[x \* y](../../../csharp/language-reference/operators/multiplication-operator.md) – 乗算。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-146">[x \* y](../../../csharp/language-reference/operators/multiplication-operator.md) – multiplication.</span></span>  
  
 <span data-ttu-id="3ba9a-147">[x / y](../../../csharp/language-reference/operators/division-operator.md) – 除算。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-147">[x / y](../../../csharp/language-reference/operators/division-operator.md) – division.</span></span> <span data-ttu-id="3ba9a-148">オペランドが整数の場合、結果は 0 に近い整数になるように切り捨てられます (例: `-7 / 2 is -3`)。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-148">If the operands are integers, the result is an integer truncated toward zero (for example, `-7 / 2 is -3`).</span></span>  
  
 <span data-ttu-id="3ba9a-149">[x % y](../../../csharp/language-reference/operators/remainder-operator.md) – 剰余。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-149">[x % y](../../../csharp/language-reference/operators/remainder-operator.md) – remainder.</span></span> <span data-ttu-id="3ba9a-150">オペランドが整数の場合、x を y で除算した剰余を返します。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-150">If the operands are integers, this returns the remainder of dividing x by y.</span></span>  <span data-ttu-id="3ba9a-151">`q = x / y` で `r = x % y` の場合、`x = q * y + r` になります。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-151">If `q = x / y` and `r = x % y`, then `x = q * y + r`.</span></span>  
  
## <a name="additive-operators"></a><span data-ttu-id="3ba9a-152">加法演算子</span><span class="sxs-lookup"><span data-stu-id="3ba9a-152">Additive Operators</span></span>  
 <span data-ttu-id="3ba9a-153">これらの演算子は、前のセクションより優先順位が低く、次のセクションより優先順位が高くなります。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-153">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>  
  
 <span data-ttu-id="3ba9a-154">[x + y](../../../csharp/language-reference/operators/addition-operator.md) – 加算。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-154">[x + y](../../../csharp/language-reference/operators/addition-operator.md) – addition.</span></span>  
  
 <span data-ttu-id="3ba9a-155">[x – y](../../../csharp/language-reference/operators/subtraction-operator.md) – 減算。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-155">[x – y](../../../csharp/language-reference/operators/subtraction-operator.md) – subtraction.</span></span>  
  
## <a name="shift-operators"></a><span data-ttu-id="3ba9a-156">シフト演算子</span><span class="sxs-lookup"><span data-stu-id="3ba9a-156">Shift Operators</span></span>  
 <span data-ttu-id="3ba9a-157">これらの演算子は、前のセクションより優先順位が低く、次のセクションより優先順位が高くなります。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-157">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>  
  
 <span data-ttu-id="3ba9a-158">[x <\<  y](../../../csharp/language-reference/operators/left-shift-operator.md) – ビットを左へシフトし、右側には 0 を格納します。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-158">[x <\<  y](../../../csharp/language-reference/operators/left-shift-operator.md) – shift bits left and fill with zero on the right.</span></span>  
  
 <span data-ttu-id="3ba9a-159">[x >> y](../../../csharp/language-reference/operators/right-shift-operator.md) – ビットを右へシフトします。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-159">[x >> y](../../../csharp/language-reference/operators/right-shift-operator.md) – shift bits right.</span></span> <span data-ttu-id="3ba9a-160">左側のオペランドが `int` または `long` の場合、左側のビットには符号ビットが格納されます。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-160">If the left operand is `int` or `long`, then left bits are filled with the sign bit.</span></span> <span data-ttu-id="3ba9a-161">左側のオペランドが `uint` または `ulong` の場合、左側のビットには 0 が格納されます。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-161">If the left operand is `uint` or `ulong`, then left bits are filled with zero.</span></span>  
  
## <a name="relational-and-type-testing-operators"></a><span data-ttu-id="3ba9a-162">関係演算子と型検査演算子</span><span class="sxs-lookup"><span data-stu-id="3ba9a-162">Relational and Type-testing Operators</span></span>  
 <span data-ttu-id="3ba9a-163">これらの演算子は、前のセクションより優先順位が低く、次のセクションより優先順位が高くなります。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-163">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>  
  
 <span data-ttu-id="3ba9a-164">[x \< y](../../../csharp/language-reference/operators/less-than-operator.md) – より小さい (x が y より小さい場合は true)。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-164">[x \< y](../../../csharp/language-reference/operators/less-than-operator.md) – less than (true if x is less than y).</span></span>  
  
 <span data-ttu-id="3ba9a-165">[x > y](../../../csharp/language-reference/operators/greater-than-operator.md) – より大きい (x が y より大きい場合は true)。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-165">[x > y](../../../csharp/language-reference/operators/greater-than-operator.md) – greater than (true if x is greater than y).</span></span>  
  
 <span data-ttu-id="3ba9a-166">[x \<= y](../../../csharp/language-reference/operators/less-than-equal-operator.md) – 以下。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-166">[x \<= y](../../../csharp/language-reference/operators/less-than-equal-operator.md) – less than or equal to.</span></span>  
  
 <span data-ttu-id="3ba9a-167">[x >= y](../../../csharp/language-reference/operators/greater-than-equal-operator.md) – 以上。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-167">[x >= y](../../../csharp/language-reference/operators/greater-than-equal-operator.md) – greater than or equal to.</span></span>  
  
 <span data-ttu-id="3ba9a-168">[is](../../../csharp/language-reference/keywords/is.md) – 型の互換性。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-168">[is](../../../csharp/language-reference/keywords/is.md) – type compatibility.</span></span> <span data-ttu-id="3ba9a-169">評価される左側のオペランドを右側のオペランドで指定された型 (静的な型) にキャストできる場合は、true を返します。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-169">Returns true if the evaluated left operand can be cast to the type specified in the right operand (a static type).</span></span>  
  
 <span data-ttu-id="3ba9a-170">[as](../../../csharp/language-reference/keywords/as.md) – 型変換。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-170">[as](../../../csharp/language-reference/keywords/as.md) – type conversion.</span></span> <span data-ttu-id="3ba9a-171">左側のオペランドを右側のオペランドで指定された型 (静的な型) にキャストして返します。ただし、`(T)x` が例外をスローした場合、`as` は `null` を返します。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-171">Returns the left operand cast to the type specified by the right operand (a static type), but `as` returns `null` where `(T)x` would throw an exception.</span></span>  
  
## <a name="equality-operators"></a><span data-ttu-id="3ba9a-172">等値演算子</span><span class="sxs-lookup"><span data-stu-id="3ba9a-172">Equality Operators</span></span>  
 <span data-ttu-id="3ba9a-173">これらの演算子は、前のセクションより優先順位が低く、次のセクションより優先順位が高くなります。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-173">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>  
  
 <span data-ttu-id="3ba9a-174">[x == y](../../../csharp/language-reference/operators/equality-comparison-operator.md) – 等価比較。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-174">[x == y](../../../csharp/language-reference/operators/equality-comparison-operator.md) – equality.</span></span> <span data-ttu-id="3ba9a-175">既定では、`string` 以外の参照型の場合、参照の等価性を返します (等価テスト)。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-175">By default, for reference types other than `string`, this returns reference equality (identity test).</span></span> <span data-ttu-id="3ba9a-176">ただし、型は `==` をオーバーロードできるため、同一性のテストが目的の場合は `object` で `ReferenceEquals` メソッドを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-176">However, types can overload `==`, so if your intent is to test identity, it is best to use the `ReferenceEquals` method on `object`.</span></span>  
  
 <span data-ttu-id="3ba9a-177">[x != y](../../../csharp/language-reference/operators/not-equal-operator.md) – 等しくない。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-177">[x != y](../../../csharp/language-reference/operators/not-equal-operator.md) – not equal.</span></span> <span data-ttu-id="3ba9a-178">`==` のコメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-178">See comment for `==`.</span></span> <span data-ttu-id="3ba9a-179">型が `==` をオーバーロードする場合は、`!=` をオーバーロードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-179">If a type overloads `==`, then it must overload `!=`.</span></span>  
  
## <a name="logical-and-operator"></a><span data-ttu-id="3ba9a-180">論理 AND 演算子</span><span class="sxs-lookup"><span data-stu-id="3ba9a-180">Logical AND Operator</span></span>  
 <span data-ttu-id="3ba9a-181">この演算子は、前のセクションより優先順位が低く、次のセクションより優先順位が高くなります。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-181">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>  
  
 <span data-ttu-id="3ba9a-182">[x & y](../../../csharp/language-reference/operators/and-operator.md) – 論理またはビットごとの AND。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-182">[x & y](../../../csharp/language-reference/operators/and-operator.md) – logical or bitwise AND.</span></span> <span data-ttu-id="3ba9a-183">通常、整数型と `enum` 型で使用できます。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-183">You can generally use this with integer types and `enum` types.</span></span>  
  
## <a name="logical-xor-operator"></a><span data-ttu-id="3ba9a-184">論理 XOR 演算子</span><span class="sxs-lookup"><span data-stu-id="3ba9a-184">Logical XOR Operator</span></span>  
 <span data-ttu-id="3ba9a-185">この演算子は、前のセクションより優先順位が低く、次のセクションより優先順位が高くなります。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-185">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>  
  
 <span data-ttu-id="3ba9a-186">[x ^ y](../../../csharp/language-reference/operators/xor-operator.md) – 論理またはビットごとの XOR。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-186">[x ^ y](../../../csharp/language-reference/operators/xor-operator.md) – logical or bitwise XOR.</span></span> <span data-ttu-id="3ba9a-187">通常、整数型と `enum` 型で使用できます。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-187">You can generally use this with integer types and `enum` types.</span></span>  
  
## <a name="logical-or-operator"></a><span data-ttu-id="3ba9a-188">論理 OR 演算子</span><span class="sxs-lookup"><span data-stu-id="3ba9a-188">Logical OR Operator</span></span>  
 <span data-ttu-id="3ba9a-189">この演算子は、前のセクションより優先順位が低く、次のセクションより優先順位が高くなります。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-189">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>  
  
 <span data-ttu-id="3ba9a-190">[x &#124; y](../../../csharp/language-reference/operators/or-operator.md) – 論理またはビットごとの OR。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-190">[x &#124; y](../../../csharp/language-reference/operators/or-operator.md) – logical or bitwise OR.</span></span> <span data-ttu-id="3ba9a-191">通常、整数型と `enum` 型で使用できます。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-191">You can generally use this with integer types and `enum` types.</span></span>  
  
## <a name="conditional-and-operator"></a><span data-ttu-id="3ba9a-192">条件 AND 演算子</span><span class="sxs-lookup"><span data-stu-id="3ba9a-192">Conditional AND Operator</span></span>  
 <span data-ttu-id="3ba9a-193">この演算子は、前のセクションより優先順位が低く、次のセクションより優先順位が高くなります。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-193">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>  
  
 <span data-ttu-id="3ba9a-194">[x && y](../../../csharp/language-reference/operators/conditional-and-operator.md) – 論理 AND。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-194">[x && y](../../../csharp/language-reference/operators/conditional-and-operator.md) – logical AND.</span></span> <span data-ttu-id="3ba9a-195">最初のオペランドが false に評価される場合、C# では 2 番目のオペランドが評価されません。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-195">If the first operand evaluates to false, then C# does not evaluate the second operand.</span></span>  
  
## <a name="conditional-or-operator"></a><span data-ttu-id="3ba9a-196">条件 OR 演算子</span><span class="sxs-lookup"><span data-stu-id="3ba9a-196">Conditional OR Operator</span></span>  
 <span data-ttu-id="3ba9a-197">この演算子は、前のセクションより優先順位が低く、次のセクションより優先順位が高くなります。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-197">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>  
  
 <span data-ttu-id="3ba9a-198">[x &#124;&#124; y](../../../csharp/language-reference/operators/conditional-or-operator.md) – 論理 OR。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-198">[x &#124;&#124; y](../../../csharp/language-reference/operators/conditional-or-operator.md) – logical OR.</span></span> <span data-ttu-id="3ba9a-199">最初のオペランドが true に評価される場合、C# では 2 番目のオペランドが評価されません。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-199">If the first operand evaluates to true, then C# does not evaluate the second operand.</span></span>  
  
## <a name="null-coalescing-operator"></a><span data-ttu-id="3ba9a-200">Null 合体演算子</span><span class="sxs-lookup"><span data-stu-id="3ba9a-200">Null-coalescing Operator</span></span>  
 <span data-ttu-id="3ba9a-201">この演算子は、前のセクションより優先順位が低く、次のセクションより優先順位が高くなります。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-201">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>  
  
 <span data-ttu-id="3ba9a-202">[x ?? y](../../../csharp/language-reference/operators/null-coalescing-operator.md) – `x` が `null` 以外の場合は x を返します。null の場合は `y` を返します。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-202">[x ?? y](../../../csharp/language-reference/operators/null-coalescing-operator.md) – returns `x` if it is non-`null`; otherwise, returns `y`.</span></span>  
  
## <a name="conditional-operator"></a><span data-ttu-id="3ba9a-203">条件演算子</span><span class="sxs-lookup"><span data-stu-id="3ba9a-203">Conditional Operator</span></span>  
 <span data-ttu-id="3ba9a-204">この演算子は、前のセクションより優先順位が低く、次のセクションより優先順位が高くなります。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-204">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>  
  
 <span data-ttu-id="3ba9a-205">[t ? x : y](../../../csharp/language-reference/operators/conditional-operator.md) – テスト `t` が true に評価される場合は `x` を評価して返します。それ以外の場合は `y` を評価して返します。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-205">[t ? x : y](../../../csharp/language-reference/operators/conditional-operator.md) – if test `t` evaluates to true, then evaluate and return `x`; otherwise, evaluate and return `y`.</span></span>  
  
## <a name="assignment-and-lambda-operators"></a><span data-ttu-id="3ba9a-206">代入演算子とラムダ演算子</span><span class="sxs-lookup"><span data-stu-id="3ba9a-206">Assignment and Lambda Operators</span></span>  
 <span data-ttu-id="3ba9a-207">これらの演算子は、前のセクションより優先順位が低く、次のセクションより優先順位が高くなります。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-207">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>  
  
 <span data-ttu-id="3ba9a-208">[x = y](../../../csharp/language-reference/operators/assignment-operator.md) – 代入。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-208">[x = y](../../../csharp/language-reference/operators/assignment-operator.md) – assignment.</span></span>  
  
 <span data-ttu-id="3ba9a-209">[x += y](../../../csharp/language-reference/operators/addition-assignment-operator.md) – インクリメント。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-209">[x += y](../../../csharp/language-reference/operators/addition-assignment-operator.md) – increment.</span></span> <span data-ttu-id="3ba9a-210">`y` の値を `x` の値に加算した結果を `x` に格納し、新しい値を返します。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-210">Add the value of `y` to the value of `x`, store the result in `x`, and return the new value.</span></span> <span data-ttu-id="3ba9a-211">`x` が `event` を指定した場合、`y` は、C# によってイベント ハンドラーとして追加される適切な関数である必要があります。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-211">If `x` designates an `event`, then `y` must be an appropriate function that C# adds as an event handler.</span></span>  
  
 <span data-ttu-id="3ba9a-212">[x -= y](../../../csharp/language-reference/operators/subtraction-assignment-operator.md) – デクリメント。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-212">[x -= y](../../../csharp/language-reference/operators/subtraction-assignment-operator.md) – decrement.</span></span> <span data-ttu-id="3ba9a-213">`y` の値を `x` の値から減算した結果を `x` に格納し、新しい値を返します。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-213">Subtract the value of `y` from the value of `x`, store the result in `x`, and return the new value.</span></span> <span data-ttu-id="3ba9a-214">`x` が `event` を指定した場合、`y` は、C# によってイベント ハンドラーとして削除される適切な関数である必要があります。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-214">If `x` designates an `event`, then `y` must be an appropriate function that C# removes as an event handler</span></span>  
  
 <span data-ttu-id="3ba9a-215">[x \*= y](../../../csharp/language-reference/operators/multiplication-assignment-operator.md) – 乗算代入。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-215">[x \*= y](../../../csharp/language-reference/operators/multiplication-assignment-operator.md) – multiplication assignment.</span></span> <span data-ttu-id="3ba9a-216">`y` の値を `x` の値に乗算した結果を `x` に格納し、新しい値を返します。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-216">Multiply the value of `y` to the value of `x`, store the result in `x`, and return the new value.</span></span>  
  
 <span data-ttu-id="3ba9a-217">[x /= y](../../../csharp/language-reference/operators/division-assignment-operator.md) – 除算代入。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-217">[x /= y](../../../csharp/language-reference/operators/division-assignment-operator.md) – division assignment.</span></span> <span data-ttu-id="3ba9a-218">`x` の値を `y` の値で除算した結果を `x` に格納し、新しい値を返します。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-218">Divide the value of `x` by the value of `y`, store the result in `x`, and return the new value.</span></span>  
  
 <span data-ttu-id="3ba9a-219">[x %= y](../../../csharp/language-reference/operators/remainder-assignment-operator.md) – 剰余代入。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-219">[x %= y](../../../csharp/language-reference/operators/remainder-assignment-operator.md) – remainder assignment.</span></span> <span data-ttu-id="3ba9a-220">`x` の値を `y` の値で除算した剰余を `x` に格納し、新しい値を返します。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-220">Divide the value of `x` by the value of `y`, store the remainder in `x`, and return the new value.</span></span>  
  
 <span data-ttu-id="3ba9a-221">[x &= y](../../../csharp/language-reference/operators/and-assignment-operator.md) – AND 代入。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-221">[x &= y](../../../csharp/language-reference/operators/and-assignment-operator.md) – AND assignment.</span></span> <span data-ttu-id="3ba9a-222">`y` の値と `x` の値の AND 演算を行った結果を `x` に格納し、新しい値を返します。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-222">AND the value of `y` with the value of `x`, store the result in `x`, and return the new value.</span></span>  
  
 <span data-ttu-id="3ba9a-223">[x &#124;= y](../../../csharp/language-reference/operators/or-assignment-operator.md) – OR 代入。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-223">[x &#124;= y](../../../csharp/language-reference/operators/or-assignment-operator.md) – OR assignment.</span></span> <span data-ttu-id="3ba9a-224">`y` の値と `x` の値の OR 演算を行った結果を `x` に格納し、新しい値を返します。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-224">OR the value of `y` with the value of `x`, store the result in `x`, and return the new value.</span></span>  
  
 <span data-ttu-id="3ba9a-225">[x ^= y](../../../csharp/language-reference/operators/xor-assignment-operator.md) – XOR 代入。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-225">[x ^= y](../../../csharp/language-reference/operators/xor-assignment-operator.md) – XOR assignment.</span></span> <span data-ttu-id="3ba9a-226">`y` の値と `x` の値の XOR 演算を行った結果を `x` に格納し、新しい値を返します。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-226">XOR the value of `y` with the value of `x`, store the result in `x`, and return the new value.</span></span>  
  
 <span data-ttu-id="3ba9a-227">[x <<= y](../../../csharp/language-reference/operators/left-shift-assignment-operator.md) – 左シフト代入。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-227">[x <<= y](../../../csharp/language-reference/operators/left-shift-assignment-operator.md) – left-shift assignment.</span></span> <span data-ttu-id="3ba9a-228">`x` の値を `y` で指定した分だけ左へシフトした結果を `x` に格納し、新しい値を返します。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-228">Shift the value of `x` left by `y` places, store the result in `x`, and return the new value.</span></span>  
  
 <span data-ttu-id="3ba9a-229">[x >>= y](../../../csharp/language-reference/operators/right-shift-assignment-operator.md) – 右シフト代入。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-229">[x >>= y](../../../csharp/language-reference/operators/right-shift-assignment-operator.md) – right-shift assignment.</span></span> <span data-ttu-id="3ba9a-230">`x` の値を `y` で指定した分だけ右へシフトした結果を `x` に格納し、新しい値を返します。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-230">Shift the value of `x` right by `y` places, store the result in `x`, and return the new value.</span></span>  
  
 <span data-ttu-id="3ba9a-231">[=>](../../../csharp/language-reference/operators/lambda-operator.md) – ラムダ宣言。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-231">[=>](../../../csharp/language-reference/operators/lambda-operator.md) – lambda declaration.</span></span>  
  
## <a name="arithmetic-overflow"></a><span data-ttu-id="3ba9a-232">算術オーバーフロー</span><span class="sxs-lookup"><span data-stu-id="3ba9a-232">Arithmetic Overflow</span></span>  
 <span data-ttu-id="3ba9a-233">算術演算子 ([+](../../../csharp/language-reference/operators/addition-operator.md)、[-](../../../csharp/language-reference/operators/subtraction-operator.md)、[\*](../../../csharp/language-reference/operators/multiplication-operator.md)、[/](../../../csharp/language-reference/operators/division-operator.md)) を実行すると、結果が数値型の有効な値の範囲を超えることがあります。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-233">The arithmetic operators ([+](../../../csharp/language-reference/operators/addition-operator.md), [-](../../../csharp/language-reference/operators/subtraction-operator.md), [\*](../../../csharp/language-reference/operators/multiplication-operator.md), [/](../../../csharp/language-reference/operators/division-operator.md)) can produce results that are outside the range of possible values for the numeric type involved.</span></span> <span data-ttu-id="3ba9a-234">詳細については、各演算子に関するセクションを参照してください。概要は、以下のとおりです。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-234">You should refer to the section on a particular operator for details, but in general:</span></span>  
  
- <span data-ttu-id="3ba9a-235">整数の算術オーバーフローでは、<xref:System.OverflowException> がスローされるか、または結果の最上位ビットが破棄されます。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-235">Integer arithmetic overflow either throws an <xref:System.OverflowException> or discards the most significant bits of the result.</span></span> <span data-ttu-id="3ba9a-236">0 による整数除算では、常に <xref:System.DivideByZeroException> がスローされます。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-236">Integer division by zero always throws a <xref:System.DivideByZeroException>.</span></span>  

   <span data-ttu-id="3ba9a-237">整数のオーバーフローが発生したときの対処方法は、実行コンテキスト ([checked または unchecked](../../../csharp/language-reference/keywords/checked-and-unchecked.md)) によって異なります。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-237">When integer overflow occurs, what happens depends on the execution context, which can be [checked or unchecked](../../../csharp/language-reference/keywords/checked-and-unchecked.md).</span></span> <span data-ttu-id="3ba9a-238">checked コンテキストの場合は、<xref:System.OverflowException> がスローされます。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-238">In a checked context, an <xref:System.OverflowException> is thrown.</span></span> <span data-ttu-id="3ba9a-239">unchecked コンテキストの場合は、結果の最上位ビットが破棄され、実行が続行されます。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-239">In an unchecked context, the most significant bits of the result are discarded and execution continues.</span></span> <span data-ttu-id="3ba9a-240">このように、C# ではオーバーフローを処理するのか、それとも無視するのかをユーザーが選択できます。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-240">Thus, C# gives you the choice of handling or ignoring overflow.</span></span> <span data-ttu-id="3ba9a-241">既定では、算術演算は *unchecked* コンテキストで発生します。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-241">By default, arithmetic operations occur in an *unchecked* context.</span></span> 

   <span data-ttu-id="3ba9a-242">算術演算の場合だけでなく、整数型から整数型へのキャスト ([long](../../../csharp/language-reference/keywords/long.md) から [int](../../../csharp/language-reference/keywords/int.md) へのキャストなど) でもオーバーフローは発生し、その場合も実行が checked または unchecked のいずれかによって対処が異なります。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-242">In addition to the arithmetic operations, integral-type to integral-type casts can cause overflow (such as when you cast a [long](../../../csharp/language-reference/keywords/long.md) to an [int](../../../csharp/language-reference/keywords/int.md)), and are subject to checked or unchecked execution.</span></span> <span data-ttu-id="3ba9a-243">ただし、ビット処理演算子とシフト演算子ではオーバーフローは発生しません。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-243">However, bitwise operators and shift operators never cause overflow.</span></span>  
   
-   <span data-ttu-id="3ba9a-244">浮動小数点数の算術オーバーフローまたは 0 による浮動小数点除算では、例外はスローされません。これは、浮動小数点型が IEEE 754 に基づいており、無限大および NaN (Not a Number) を表現できるためです。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-244">Floating-point arithmetic overflow or division by zero never throws an exception, because floating-point types are based on IEEE 754 and so have provisions for representing infinity and NaN (Not a Number).</span></span>  
  
-   <span data-ttu-id="3ba9a-245">[小数](../../../csharp/language-reference/keywords/decimal.md)の算術オーバーフローでは、常に <xref:System.OverflowException> がスローされます。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-245">[Decimal](../../../csharp/language-reference/keywords/decimal.md) arithmetic overflow always throws an <xref:System.OverflowException>.</span></span> <span data-ttu-id="3ba9a-246">0 による小数除算では、常に <xref:System.DivideByZeroException> がスローされます。</span><span class="sxs-lookup"><span data-stu-id="3ba9a-246">Decimal division by zero always throws a <xref:System.DivideByZeroException>.</span></span>  

## <a name="see-also"></a><span data-ttu-id="3ba9a-247">参照</span><span class="sxs-lookup"><span data-stu-id="3ba9a-247">See Also</span></span>

- [<span data-ttu-id="3ba9a-248">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="3ba9a-248">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="3ba9a-249">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="3ba9a-249">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="3ba9a-250">C#</span><span class="sxs-lookup"><span data-stu-id="3ba9a-250">C#</span></span>](../../../csharp/index.md)
- [<span data-ttu-id="3ba9a-251">オーバーロードされた演算子</span><span class="sxs-lookup"><span data-stu-id="3ba9a-251">Overloadable Operators</span></span>](../../../csharp/programming-guide/statements-expressions-operators/overloadable-operators.md)  
- [<span data-ttu-id="3ba9a-252">C# のキーワード</span><span class="sxs-lookup"><span data-stu-id="3ba9a-252">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)
