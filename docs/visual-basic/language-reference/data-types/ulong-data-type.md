---
title: ULong 型 (Visual Basic)
ms.date: 01/31/2018
f1_keywords:
- vb.ulong
helpviewer_keywords:
- numbers [Visual Basic], whole
- whole numbers
- integral data types [Visual Basic]
- integer numbers
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- integers [Visual Basic], types
- data types [Visual Basic], integral
- literal type characters [Visual Basic], UL
- ULong data type
- UL literal type characters [Visual Basic]
ms.assetid: 017e0702-774e-44ae-bedc-786b424ca84e
ms.openlocfilehash: 13dec9f298655a4bfe6672e2dbba7c7262379cc4
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2018
ms.locfileid: "50202882"
---
# <a name="ulong-data-type-visual-basic"></a><span data-ttu-id="115cc-102">ULong データ型 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="115cc-102">ULong data type (Visual Basic)</span></span>

<span data-ttu-id="115cc-103">0 から 18,446,744,073,709,551,615 まで 64 ビット (8 バイト) の符号なし整数 (1.84 倍以上の 10 ^19)。</span><span class="sxs-lookup"><span data-stu-id="115cc-103">Holds unsigned 64-bit (8-byte) integers ranging in value from 0 through 18,446,744,073,709,551,615 (more than 1.84 times 10 ^ 19).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="115cc-104">Remarks</span><span class="sxs-lookup"><span data-stu-id="115cc-104">Remarks</span></span>

<span data-ttu-id="115cc-105">使用して、`ULong`データ型に対して大きすぎますバイナリ データを格納する`UInteger`、または使用可能な最大符号なし整数値。</span><span class="sxs-lookup"><span data-stu-id="115cc-105">Use the `ULong` data type to contain binary data too large for `UInteger`, or the largest possible unsigned integer values.</span></span>  
  
<span data-ttu-id="115cc-106">`ULong` の既定値は 0 です。</span><span class="sxs-lookup"><span data-stu-id="115cc-106">The default value of `ULong` is 0.</span></span>

## <a name="literal-assignments"></a><span data-ttu-id="115cc-107">リテラルの割り当て</span><span class="sxs-lookup"><span data-stu-id="115cc-107">Literal assignments</span></span>

<span data-ttu-id="115cc-108">宣言し、初期化を`ULong`10 進リテラル、16 進リテラル、8 進数のリテラルを割り当てることや (Visual Basic 2017 以降) バイナリ リテラルでは、変数。</span><span class="sxs-lookup"><span data-stu-id="115cc-108">You can declare and initialize a `ULong` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span> <span data-ttu-id="115cc-109">整数リテラルが `ULong` の範囲外にある場合 (つまり、<xref:System.UInt64.MinValue?displayProperty=nameWithType> より小さいか、<xref:System.UInt64.MaxValue?displayProperty=nameWithType> より大きい場合)、コンパイル エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="115cc-109">If the integer literal is outside the range of `ULong` (that is, if it is less than <xref:System.UInt64.MinValue?displayProperty=nameWithType> or greater than <xref:System.UInt64.MaxValue?displayProperty=nameWithType>, a compilation error occurs.</span></span>

<span data-ttu-id="115cc-110">次の例では、整数 7,934,076,125 を 10 進リテラル、16 進リテラル、バイナリ リテラルで表したものが、`ULong` 値に割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="115cc-110">In the following example, integers equal to 7,934,076,125 that are represented as decimal, hexadecimal, and binary literals are assigned to `ULong` values.</span></span>
  
[!code-vb[ULong](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#ULong)]

> [!NOTE] 
> <span data-ttu-id="115cc-111">プレフィックスを使用する`&h`または`&H`を 16 進リテラル、プレフィックスを示すために`&b`または`&B`、バイナリ リテラル、およびプレフィックスを示すために`&o`または`&O`を 8 進数のリテラルを示すためにします。</span><span class="sxs-lookup"><span data-stu-id="115cc-111">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="115cc-112">10 進リテラルには、プレフィックスはありません。</span><span class="sxs-lookup"><span data-stu-id="115cc-112">Decimal literals have no prefix.</span></span>

<span data-ttu-id="115cc-113">Visual Basic 2017 から始めて、使用することできますも、アンダー スコア文字`_`、読みやすさを強化するために、桁区切り記号として次の例として示します。</span><span class="sxs-lookup"><span data-stu-id="115cc-113">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[ULong](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#LongS)]

<span data-ttu-id="115cc-114">Visual Basic 15.5 以降では、使用することできますもアンダー スコア文字 (`_`) プレフィックスと 16 進数、バイナリ、または 8 進数の桁の間の先頭の区切り記号として。</span><span class="sxs-lookup"><span data-stu-id="115cc-114">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span></span> <span data-ttu-id="115cc-115">例えば:</span><span class="sxs-lookup"><span data-stu-id="115cc-115">For example:</span></span>

```vb
Dim number As ULong = &H_F9AC_0326_1489_D68C
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

<span data-ttu-id="115cc-116">数値リテラルを含めることも、`UL`または`ul`[文字入力](../../programming-guide\language-features\data-types/type-characters.md)を示すために、`ULong`データ型は、次の例を示します。</span><span class="sxs-lookup"><span data-stu-id="115cc-116">Numeric literals can also include the `UL` or `ul` [type character](../../programming-guide\language-features\data-types/type-characters.md) to denote the `ULong` data type, as the following example shows.</span></span>

```vb
Dim number = &H_00_00_0A_96_2F_AC_14_D7ul
```

## <a name="programming-tips"></a><span data-ttu-id="115cc-117">プログラミングのヒント</span><span class="sxs-lookup"><span data-stu-id="115cc-117">Programming tips</span></span>
  
-   <span data-ttu-id="115cc-118">**負の数。**</span><span class="sxs-lookup"><span data-stu-id="115cc-118">**Negative Numbers.**</span></span> <span data-ttu-id="115cc-119">`ULong`符号なしの型は、負の数を表すことはできません。</span><span class="sxs-lookup"><span data-stu-id="115cc-119">Because `ULong` is an unsigned type, it cannot represent a negative number.</span></span> <span data-ttu-id="115cc-120">単項マイナスを使用する場合 (`-`) 型に評価される式で演算子`ULong`、Visual Basic の式を変換する`Decimal`最初。</span><span class="sxs-lookup"><span data-stu-id="115cc-120">If you use the unary minus (`-`) operator on an expression that evaluates to type `ULong`, Visual Basic converts the expression to `Decimal` first.</span></span>  
  
-   <span data-ttu-id="115cc-121">**CLS 準拠です。**</span><span class="sxs-lookup"><span data-stu-id="115cc-121">**CLS Compliance.**</span></span> <span data-ttu-id="115cc-122">`ULong`データ型がの一部、[共通言語仕様](http://www.ecma-international.org/publications/standards/Ecma-335.htm)(CLS) に CLS 準拠コードがそれを使用するコンポーネントを使用できないようにします。</span><span class="sxs-lookup"><span data-stu-id="115cc-122">The `ULong` data type is not part of the [Common Language Specification](http://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), so CLS-compliant code cannot consume a component that uses it.</span></span>  
  
-   <span data-ttu-id="115cc-123">**相互運用の考慮事項。**</span><span class="sxs-lookup"><span data-stu-id="115cc-123">**Interop Considerations.**</span></span> <span data-ttu-id="115cc-124">.NET Framework、例のオートメーションまたは COM オブジェクト用に作成されていないコンポーネントとやり取りする場合などの型を注意してください`ulong`他の環境で別のデータ幅 (32 ビット) を持つことができます。</span><span class="sxs-lookup"><span data-stu-id="115cc-124">If you are interfacing with components not written for the .NET Framework, for example Automation or COM objects, keep in mind that types such as `ulong` can have a different data width (32 bits) in other environments.</span></span> <span data-ttu-id="115cc-125">このようなコンポーネントに 32 ビットの引数を渡す場合の宣言として`UInteger`の代わりに`ULong`管理対象の Visual Basic コードです。</span><span class="sxs-lookup"><span data-stu-id="115cc-125">If you are passing a 32-bit argument to such a component, declare it as `UInteger` instead of `ULong` in your managed Visual Basic code.</span></span>  
  
     <span data-ttu-id="115cc-126">さらに、オートメーションは Windows 95、Windows 98、Windows ME、および Windows 2000 で 64 ビット整数をサポートしません。</span><span class="sxs-lookup"><span data-stu-id="115cc-126">Furthermore, Automation does not support 64-bit integers on Windows 95, Windows 98, Windows ME, or Windows 2000.</span></span> <span data-ttu-id="115cc-127">Visual Basic を渡すことはできません`ULong`これらのプラットフォームで、オートメーション コンポーネントへの引数。</span><span class="sxs-lookup"><span data-stu-id="115cc-127">You cannot pass a Visual Basic `ULong` argument to an Automation component on these platforms.</span></span>  
  
-   <span data-ttu-id="115cc-128">**拡大します。**</span><span class="sxs-lookup"><span data-stu-id="115cc-128">**Widening.**</span></span> <span data-ttu-id="115cc-129">`ULong`拡大変換後のデータ型`Decimal`、 `Single`、および`Double`します。</span><span class="sxs-lookup"><span data-stu-id="115cc-129">The `ULong` data type widens to `Decimal`, `Single`, and `Double`.</span></span> <span data-ttu-id="115cc-130">つまり、変換できる`ULong`遭遇することがなくこれらの型のいずれにも、<xref:System.OverflowException?displayProperty=nameWithType>エラー。</span><span class="sxs-lookup"><span data-stu-id="115cc-130">This means you can convert `ULong` to any of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>  
  
-   <span data-ttu-id="115cc-131">**型宣言文字。**</span><span class="sxs-lookup"><span data-stu-id="115cc-131">**Type Characters.**</span></span> <span data-ttu-id="115cc-132">リテラルの型文字を付加`UL`リテラルに強制的に、`ULong`データ型。</span><span class="sxs-lookup"><span data-stu-id="115cc-132">Appending the literal type characters `UL` to a literal forces it to the `ULong` data type.</span></span> <span data-ttu-id="115cc-133">`ULong` 識別子の型文字がありません。</span><span class="sxs-lookup"><span data-stu-id="115cc-133">`ULong` has no identifier type character.</span></span>
  
-   <span data-ttu-id="115cc-134">**フレームワークの型。**</span><span class="sxs-lookup"><span data-stu-id="115cc-134">**Framework Type.**</span></span> <span data-ttu-id="115cc-135">.NET Framework において対応する型は、<xref:System.UInt64?displayProperty=nameWithType> 構造体です。</span><span class="sxs-lookup"><span data-stu-id="115cc-135">The corresponding type in the .NET Framework is the <xref:System.UInt64?displayProperty=nameWithType> structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="115cc-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="115cc-136">See also</span></span>

 <xref:System.UInt64>  
 [<span data-ttu-id="115cc-137">データの種類</span><span class="sxs-lookup"><span data-stu-id="115cc-137">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)  
 [<span data-ttu-id="115cc-138">データ型変換関数</span><span class="sxs-lookup"><span data-stu-id="115cc-138">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [<span data-ttu-id="115cc-139">変換の概要</span><span class="sxs-lookup"><span data-stu-id="115cc-139">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [<span data-ttu-id="115cc-140">方法 : 符号なしの型を使用する Windows の機能を呼び出す</span><span class="sxs-lookup"><span data-stu-id="115cc-140">How to: Call a Windows Function that Takes Unsigned Types</span></span>](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)  
 [<span data-ttu-id="115cc-141">データ型の有効な使用方法</span><span class="sxs-lookup"><span data-stu-id="115cc-141">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
