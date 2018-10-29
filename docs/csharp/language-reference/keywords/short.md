---
title: short (C# リファレンス)
ms.date: 03/14/2017
f1_keywords:
- short
- short_CSharpKeyword
helpviewer_keywords:
- short keyword [C#]
ms.assetid: 04c10688-e51a-4a87-bfec-83f7fb42ff11
ms.openlocfilehash: 0d90f31da49b94eee490e95f0cdf1d582bb0b059
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2018
ms.locfileid: "50184154"
---
# <a name="short-c-reference"></a><span data-ttu-id="d6c0d-102">short (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="d6c0d-102">short (C# Reference)</span></span>

<span data-ttu-id="d6c0d-103">`short` は、次の表に示すサイズと範囲で値を格納する整数データ型を示します。</span><span class="sxs-lookup"><span data-stu-id="d6c0d-103">`short` denotes an integral data type that stores values according to the size and range shown in the following table.</span></span>

|<span data-ttu-id="d6c0d-104">型</span><span class="sxs-lookup"><span data-stu-id="d6c0d-104">Type</span></span>|<span data-ttu-id="d6c0d-105">範囲</span><span class="sxs-lookup"><span data-stu-id="d6c0d-105">Range</span></span>|<span data-ttu-id="d6c0d-106">サイズ</span><span class="sxs-lookup"><span data-stu-id="d6c0d-106">Size</span></span>|<span data-ttu-id="d6c0d-107">.NET 型</span><span class="sxs-lookup"><span data-stu-id="d6c0d-107">.NET type</span></span>|
|----------|-----------|----------|-------------------------|
|`short`|<span data-ttu-id="d6c0d-108">-32,768 ～ 32,767</span><span class="sxs-lookup"><span data-stu-id="d6c0d-108">-32,768 to 32,767</span></span>|<span data-ttu-id="d6c0d-109">符号付き 16 ビット整数</span><span class="sxs-lookup"><span data-stu-id="d6c0d-109">Signed 16-bit integer</span></span>|<xref:System.Int16?displayProperty=nameWithType>|

## <a name="literals"></a><span data-ttu-id="d6c0d-110">リテラル</span><span class="sxs-lookup"><span data-stu-id="d6c0d-110">Literals</span></span>

<span data-ttu-id="d6c0d-111">`short` 変数を宣言し、10 進リテラル、16 進リテラル、または (C# 7.0 以降) バイナリ リテラルを割り当てることによって初期化できます。</span><span class="sxs-lookup"><span data-stu-id="d6c0d-111">You can declare and initialize a `short` variable by assigning a decimal literal, a hexadecimal literal, or (starting with C# 7.0) a binary literal to it.</span></span>  <span data-ttu-id="d6c0d-112">整数リテラルが `short` の範囲外にある場合 (つまり、<xref:System.Int16.MinValue?displayProperty=nameWithType> より小さいか、<xref:System.Int16.MaxValue?displayProperty=nameWithType> より大きい場合)、コンパイル エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="d6c0d-112">If the integer literal is outside the range of `short` (that is, if it is less than <xref:System.Int16.MinValue?displayProperty=nameWithType> or greater than <xref:System.Int16.MaxValue?displayProperty=nameWithType>), a compilation error occurs.</span></span>

<span data-ttu-id="d6c0d-113">次の例では、整数 1,034 を 10 進リテラル、16 進リテラル、バイナリ リテラルで表したものが、[int](int.md) から `short` 値に暗黙的に変換されています。</span><span class="sxs-lookup"><span data-stu-id="d6c0d-113">In the following example, integers equal to 1,034 that are represented as decimal, hexadecimal, and binary literals are implicitly converted from [int](int.md) to `short` values.</span></span>

[!code-csharp[Short](~/samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#Short)]

> [!NOTE]
> <span data-ttu-id="d6c0d-114">16 進リテラルを表すにはプレフィックス `0x` または `0X` を使い、バイナリ リテラルを表すにはプレフィックス `0b` または `0B` を使います。</span><span class="sxs-lookup"><span data-stu-id="d6c0d-114">You use the prefix `0x` or `0X` to denote a hexadecimal literal and the prefix `0b` or `0B` to denote a binary literal.</span></span> <span data-ttu-id="d6c0d-115">10 進リテラルには、プレフィックスはありません。</span><span class="sxs-lookup"><span data-stu-id="d6c0d-115">Decimal literals have no prefix.</span></span>

<span data-ttu-id="d6c0d-116">C# 7.0 以降では、読みやすさを強化するためにいくつかの機能が追加されています。</span><span class="sxs-lookup"><span data-stu-id="d6c0d-116">Starting with C# 7.0, a couple of features have been added to enhance readability.</span></span>

- <span data-ttu-id="d6c0d-117">C# 7.0 では、桁区切り記号としてアンダースコア文字 (`_`) が使用できます。</span><span class="sxs-lookup"><span data-stu-id="d6c0d-117">C# 7.0 allows the usage of the underscore character, `_`, as a digit separator.</span></span>
- <span data-ttu-id="d6c0d-118">C# 7.2 では、プレフィックスの後に、`_` をバイナリまたは 16 進リテラルの桁区切り記号として使用できます。</span><span class="sxs-lookup"><span data-stu-id="d6c0d-118">C# 7.2 allows `_` to be used as a digit separator for a binary or hexadecimal literal, after the prefix.</span></span> <span data-ttu-id="d6c0d-119">10 進リテラルは先頭にアンダー スコアを持つことはできません。</span><span class="sxs-lookup"><span data-stu-id="d6c0d-119">A decimal literal isn't permitted to have a leading underscore.</span></span>

<span data-ttu-id="d6c0d-120">以下にいくつか例を示します。</span><span class="sxs-lookup"><span data-stu-id="d6c0d-120">Some examples are shown below.</span></span>

[!code-csharp[Short](~/samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#ShortS)]

## <a name="compiler-overload-resolution"></a><span data-ttu-id="d6c0d-121">コンパイラのオーバーロード解決</span><span class="sxs-lookup"><span data-stu-id="d6c0d-121">Compiler overload resolution</span></span>

<span data-ttu-id="d6c0d-122">オーバーロードされたメソッドを呼び出すときは、キャストを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d6c0d-122">A cast must be used when calling overloaded methods.</span></span> <span data-ttu-id="d6c0d-123">たとえば、`short` パラメーターと [int](int.md) パラメーターを使用したオーバーロードされたメソッドがあるとします。</span><span class="sxs-lookup"><span data-stu-id="d6c0d-123">Consider, for example, the following overloaded methods that use `short` and [int](int.md) parameters:</span></span>

```csharp
public static void SampleMethod(int i) {}
public static void SampleMethod(short s) {}
```

<span data-ttu-id="d6c0d-124">`short` キャストを使用すると、正しい型が呼び出されます。次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="d6c0d-124">Using the `short` cast guarantees that the correct type is called, for example:</span></span>

```csharp
SampleMethod(5);         // Calling the method with the int parameter
SampleMethod((short)5);  // Calling the method with the short parameter
```

## <a name="conversions"></a><span data-ttu-id="d6c0d-125">変換</span><span class="sxs-lookup"><span data-stu-id="d6c0d-125">Conversions</span></span>

<span data-ttu-id="d6c0d-126">`short` から [int](int.md)、[long](long.md)、[float](float.md)、[double](double.md)、[decimal](decimal.md) への、定義済みの暗黙的な変換が組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="d6c0d-126">There is a predefined implicit conversion from `short` to [int](int.md), [long](long.md), [float](float.md), [double](double.md), or [decimal](decimal.md).</span></span>

<span data-ttu-id="d6c0d-127">記憶領域が大きなリテラル以外の数値型を暗黙的に `short` に変換することはできません (整数型の記憶領域については、「[整数型の一覧表](integral-types-table.md)」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="d6c0d-127">You cannot implicitly convert nonliteral numeric types of larger storage size to `short` (see [Integral Types Table](integral-types-table.md) for the storage sizes of integral types).</span></span> <span data-ttu-id="d6c0d-128">たとえば、2 つの `short` 変数 `x` と `y` があるとします。</span><span class="sxs-lookup"><span data-stu-id="d6c0d-128">Consider, for example, the following two `short` variables `x` and `y`:</span></span>

```csharp
short x = 5, y = 12;
```

<span data-ttu-id="d6c0d-129">次の代入ステートメントは、代入演算子の右側にある算術式が既定で [int](int.md) に評価されるため、コンパイル エラーになります。</span><span class="sxs-lookup"><span data-stu-id="d6c0d-129">The following assignment statement produces a compilation error because the arithmetic expression on the right-hand side of the assignment operator evaluates to [int](int.md) by default.</span></span>

```csharp
short z  = x + y;        // Compiler error CS0266: no conversion from int to short
```

<span data-ttu-id="d6c0d-130">この問題を解決するには、キャストを使用します。</span><span class="sxs-lookup"><span data-stu-id="d6c0d-130">To fix this problem, use a cast:</span></span>

```csharp
short z  = (short)(x + y);   // Explicit conversion
```

<span data-ttu-id="d6c0d-131">次のステートメントを使うこともできます。このステートメントでは、変換先の変数の記憶領域サイズは元のサイズ以上になります。</span><span class="sxs-lookup"><span data-stu-id="d6c0d-131">It is also possible to use the following statements, where the destination variable has the same storage size or a larger storage size:</span></span>

```csharp
int m = x + y;
long n = x + y;
```

<span data-ttu-id="d6c0d-132">浮動小数点型から `short` への暗黙的な変換は行われません。</span><span class="sxs-lookup"><span data-stu-id="d6c0d-132">There is no implicit conversion from floating-point types to `short`.</span></span> <span data-ttu-id="d6c0d-133">たとえば、次のステートメントは、明示的なキャストを使用しない場合、コンパイラ エラーになります。</span><span class="sxs-lookup"><span data-stu-id="d6c0d-133">For example, the following statement generates a compiler error unless an explicit cast is used:</span></span>

```csharp
short x = 3.0;          // Error: no implicit conversion from double
short y = (short)3.0;   // OK: explicit conversion
```

<span data-ttu-id="d6c0d-134">浮動小数点型と整数型の混在する算術式の詳細については、「[float](float.md)」と「[double](double.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d6c0d-134">For information on arithmetic expressions with mixed floating-point types and integral types, see [float](float.md) and [double](double.md).</span></span>

<span data-ttu-id="d6c0d-135">暗黙的な数値変換規則について詳しくは、「[暗黙的な数値変換の一覧表](implicit-numeric-conversions-table.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d6c0d-135">For more information on implicit numeric conversion rules, see the [Implicit Numeric Conversions Table](implicit-numeric-conversions-table.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="d6c0d-136">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="d6c0d-136">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="d6c0d-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="d6c0d-137">See also</span></span>

- <xref:System.Int16>
- [<span data-ttu-id="d6c0d-138">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="d6c0d-138">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="d6c0d-139">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="d6c0d-139">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="d6c0d-140">C# のキーワード</span><span class="sxs-lookup"><span data-stu-id="d6c0d-140">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="d6c0d-141">整数型の一覧表</span><span class="sxs-lookup"><span data-stu-id="d6c0d-141">Integral Types Table</span></span>](integral-types-table.md)
- [<span data-ttu-id="d6c0d-142">組み込み型の一覧表</span><span class="sxs-lookup"><span data-stu-id="d6c0d-142">Built-In Types Table</span></span>](built-in-types-table.md)
- [<span data-ttu-id="d6c0d-143">暗黙的な数値変換の一覧表</span><span class="sxs-lookup"><span data-stu-id="d6c0d-143">Implicit Numeric Conversions Table</span></span>](implicit-numeric-conversions-table.md)
- [<span data-ttu-id="d6c0d-144">明示的な数値変換の一覧表</span><span class="sxs-lookup"><span data-stu-id="d6c0d-144">Explicit Numeric Conversions Table</span></span>](explicit-numeric-conversions-table.md)