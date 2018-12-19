---
title: 数値結果テーブルの書式設定 - C# リファレンス
ms.custom: seodec18
description: C# の標準の数値書式指定文字列について説明します
ms.date: 09/20/2018
helpviewer_keywords:
- formatting [C#]
- numeric formatting [C#]
- String.Format method
ms.assetid: 120ba537-4448-4c62-8676-7a8fdd98f496
ms.openlocfilehash: 12fe89e3aa63e9d3d8c3f102fe5a01a5f2225375
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2018
ms.locfileid: "53239970"
---
# <a name="formatting-numeric-results-table-c-reference"></a><span data-ttu-id="4eee5-103">数値結果テーブルの書式設定 (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="4eee5-103">Formatting numeric results table (C# Reference)</span></span>

<span data-ttu-id="4eee5-104">次の表は、数値結果の書式を設定するためにサポートされている書式指定子を示しています。</span><span class="sxs-lookup"><span data-stu-id="4eee5-104">The following table shows supported format specifiers for formatting numeric results.</span></span> <span data-ttu-id="4eee5-105">最後の列の書式設定後の結果は、"en-US"<xref:System.Globalization.CultureInfo> に対応します。</span><span class="sxs-lookup"><span data-stu-id="4eee5-105">The formatted result in the last column corresponds to the "en-US" <xref:System.Globalization.CultureInfo>.</span></span>

|<span data-ttu-id="4eee5-106">書式指定子</span><span class="sxs-lookup"><span data-stu-id="4eee5-106">Format specifier</span></span>|<span data-ttu-id="4eee5-107">説明</span><span class="sxs-lookup"><span data-stu-id="4eee5-107">Description</span></span>|<span data-ttu-id="4eee5-108">使用例</span><span class="sxs-lookup"><span data-stu-id="4eee5-108">Examples</span></span>|<span data-ttu-id="4eee5-109">結果</span><span class="sxs-lookup"><span data-stu-id="4eee5-109">Result</span></span>|  
|----------------------|-----------------|--------------|------------|  
|<span data-ttu-id="4eee5-110">C または c</span><span class="sxs-lookup"><span data-stu-id="4eee5-110">C or c</span></span>|<span data-ttu-id="4eee5-111">通貨</span><span class="sxs-lookup"><span data-stu-id="4eee5-111">Currency</span></span>|`string s = $"{2.5:C}";`<br /><br /> `string s = $"{-2.5:C}";`|<span data-ttu-id="4eee5-112">$2.50</span><span class="sxs-lookup"><span data-stu-id="4eee5-112">$2.50</span></span><br /><br /> <span data-ttu-id="4eee5-113">($2.50)</span><span class="sxs-lookup"><span data-stu-id="4eee5-113">($2.50)</span></span>|  
|<span data-ttu-id="4eee5-114">D または d</span><span class="sxs-lookup"><span data-stu-id="4eee5-114">D or d</span></span>|<span data-ttu-id="4eee5-115">Decimal (10 進数型)</span><span class="sxs-lookup"><span data-stu-id="4eee5-115">Decimal</span></span>|`string s = $"{25:D5}";`|<span data-ttu-id="4eee5-116">00025</span><span class="sxs-lookup"><span data-stu-id="4eee5-116">00025</span></span>|  
|<span data-ttu-id="4eee5-117">E または e</span><span class="sxs-lookup"><span data-stu-id="4eee5-117">E or e</span></span>|<span data-ttu-id="4eee5-118">指数</span><span class="sxs-lookup"><span data-stu-id="4eee5-118">Exponential</span></span>|`string s = $"{250000:E2}";`|<span data-ttu-id="4eee5-119">2.50E+005</span><span class="sxs-lookup"><span data-stu-id="4eee5-119">2.50E+005</span></span>|  
|<span data-ttu-id="4eee5-120">F または f</span><span class="sxs-lookup"><span data-stu-id="4eee5-120">F or f</span></span>|<span data-ttu-id="4eee5-121">固定小数点</span><span class="sxs-lookup"><span data-stu-id="4eee5-121">Fixed-point</span></span>|`string s = $"{2.5:F2}";`<br /><br /> `string s = $"{2.5:F0}";`|<span data-ttu-id="4eee5-122">2.50</span><span class="sxs-lookup"><span data-stu-id="4eee5-122">2.50</span></span><br /><br /> <span data-ttu-id="4eee5-123">3</span><span class="sxs-lookup"><span data-stu-id="4eee5-123">3</span></span>|  
|<span data-ttu-id="4eee5-124">G または g</span><span class="sxs-lookup"><span data-stu-id="4eee5-124">G or g</span></span>|<span data-ttu-id="4eee5-125">全般</span><span class="sxs-lookup"><span data-stu-id="4eee5-125">General</span></span>|`string s = $"{2.5:G}";`|<span data-ttu-id="4eee5-126">2.5</span><span class="sxs-lookup"><span data-stu-id="4eee5-126">2.5</span></span>|  
|<span data-ttu-id="4eee5-127">N または n</span><span class="sxs-lookup"><span data-stu-id="4eee5-127">N or n</span></span>|<span data-ttu-id="4eee5-128">数字</span><span class="sxs-lookup"><span data-stu-id="4eee5-128">Numeric</span></span>|`string s = $"{2500000:N}";`|<span data-ttu-id="4eee5-129">2,500,000.00</span><span class="sxs-lookup"><span data-stu-id="4eee5-129">2,500,000.00</span></span>|  
|<span data-ttu-id="4eee5-130">P または p</span><span class="sxs-lookup"><span data-stu-id="4eee5-130">P or p</span></span>|<span data-ttu-id="4eee5-131">パーセント</span><span class="sxs-lookup"><span data-stu-id="4eee5-131">Percent</span></span>|`string s = $"{0.25:P}";`|<span data-ttu-id="4eee5-132">25.00%</span><span class="sxs-lookup"><span data-stu-id="4eee5-132">25.00%</span></span>|  
|<span data-ttu-id="4eee5-133">R または r</span><span class="sxs-lookup"><span data-stu-id="4eee5-133">R or r</span></span>|<span data-ttu-id="4eee5-134">ラウンドトリップ</span><span class="sxs-lookup"><span data-stu-id="4eee5-134">Round-trip</span></span>|`string s = $"{2.5:R}";`|<span data-ttu-id="4eee5-135">2.5</span><span class="sxs-lookup"><span data-stu-id="4eee5-135">2.5</span></span>|  
|<span data-ttu-id="4eee5-136">X または x</span><span class="sxs-lookup"><span data-stu-id="4eee5-136">X or x</span></span>|<span data-ttu-id="4eee5-137">16 進数</span><span class="sxs-lookup"><span data-stu-id="4eee5-137">Hexadecimal</span></span>|`string s = $"{250:X}";`<br /><br /> `string s = $"{0xffff:X}";`|<span data-ttu-id="4eee5-138">FA</span><span class="sxs-lookup"><span data-stu-id="4eee5-138">FA</span></span><br /><br /> <span data-ttu-id="4eee5-139">FFFF</span><span class="sxs-lookup"><span data-stu-id="4eee5-139">FFFF</span></span>|  

## <a name="remarks"></a><span data-ttu-id="4eee5-140">コメント</span><span class="sxs-lookup"><span data-stu-id="4eee5-140">Remarks</span></span>

<span data-ttu-id="4eee5-141">書式指定子を使用して、書式設定文字列を作成します。</span><span class="sxs-lookup"><span data-stu-id="4eee5-141">You use a format specifier to create a format string.</span></span> <span data-ttu-id="4eee5-142">書式設定文字列は `Axx` 形式になります。</span><span class="sxs-lookup"><span data-stu-id="4eee5-142">The format string is of the following form: `Axx`, where</span></span>

- <span data-ttu-id="4eee5-143">`A` は書式指定子であり、数値に適用される書式設定の種類を制御します。</span><span class="sxs-lookup"><span data-stu-id="4eee5-143">`A` is the format specifier, which controls the type of formatting applied to the numeric value.</span></span>
- <span data-ttu-id="4eee5-144">`xx` は精度指定子であり、書式設定後の結果の桁数に影響します。</span><span class="sxs-lookup"><span data-stu-id="4eee5-144">`xx` is the precision specifier, which affects the number of digits in the formatted output.</span></span> <span data-ttu-id="4eee5-145">精度指定子の値は 0 から 99 の範囲です。</span><span class="sxs-lookup"><span data-stu-id="4eee5-145">The value of the precision specifier ranges from 0 to 99.</span></span>

<span data-ttu-id="4eee5-146">10 進数 ("D"または"d") と 16 進数 ("X"または"x") の形式指定子は、整数型でのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="4eee5-146">The decimal ("D" or "d") and hexadecimal ("X" or "x") format specifiers are supported only for integral types.</span></span> <span data-ttu-id="4eee5-147">ラウンドト リップ ("R"または"r") 書式指定子は、<xref:System.Single>、 <xref:System.Double> 型と <xref:System.Numerics.BigInteger> 型でのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="4eee5-147">The round-trip ("R" or "r") format specifier is supported only for <xref:System.Single>, <xref:System.Double>, and <xref:System.Numerics.BigInteger> types.</span></span>

<span data-ttu-id="4eee5-148">標準の数値書式指定文字列は、以下をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="4eee5-148">Standard numeric format strings are supported by:</span></span>

- <span data-ttu-id="4eee5-149">全数値型の `ToString` メソッドの一部のオーバーロード。</span><span class="sxs-lookup"><span data-stu-id="4eee5-149">Some overloads of the `ToString` method of all numeric types.</span></span> <span data-ttu-id="4eee5-150">たとえば、<xref:System.Int32.ToString%28System.String%29?displayProperty=nameWithType> メソッドおよび <xref:System.Int32.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType> メソッドに数値書式指定文字列を指定できます。</span><span class="sxs-lookup"><span data-stu-id="4eee5-150">For example, you can supply a numeric format string to the <xref:System.Int32.ToString%28System.String%29?displayProperty=nameWithType> and <xref:System.Int32.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType> methods.</span></span>

- <span data-ttu-id="4eee5-151">.NET の[複合書式設定機能](../../../standard/base-types/composite-formatting.md)。たとえば <xref:System.String.Format%2A?displayProperty=nameWithType> メソッドでサポートされます。</span><span class="sxs-lookup"><span data-stu-id="4eee5-151">The .NET [composite formatting feature](../../../standard/base-types/composite-formatting.md), which is supported by the <xref:System.String.Format%2A?displayProperty=nameWithType> method, for example.</span></span>

- <span data-ttu-id="4eee5-152">[挿入文字列](../tokens/interpolated.md)。</span><span class="sxs-lookup"><span data-stu-id="4eee5-152">[Interpolated strings](../tokens/interpolated.md).</span></span>

<span data-ttu-id="4eee5-153">詳細については、「[標準の数値書式指定文字列](../../../standard/base-types/standard-numeric-format-strings.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4eee5-153">For more information, see [Standard Numeric Format Strings](../../../standard/base-types/standard-numeric-format-strings.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="4eee5-154">関連項目</span><span class="sxs-lookup"><span data-stu-id="4eee5-154">See also</span></span>

- [<span data-ttu-id="4eee5-155">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="4eee5-155">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="4eee5-156">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="4eee5-156">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="4eee5-157">型のリファレンス表</span><span class="sxs-lookup"><span data-stu-id="4eee5-157">Reference tables for types</span></span>](reference-tables-for-types.md)
- [<span data-ttu-id="4eee5-158">型の書式設定</span><span class="sxs-lookup"><span data-stu-id="4eee5-158">Formatting types</span></span>](../../../standard/base-types/formatting-types.md)
- [<span data-ttu-id="4eee5-159">複合書式指定</span><span class="sxs-lookup"><span data-stu-id="4eee5-159">Composite formatting</span></span>](../../../standard/base-types/composite-formatting.md)
- [<span data-ttu-id="4eee5-160">文字列補間</span><span class="sxs-lookup"><span data-stu-id="4eee5-160">String interpolation</span></span>](../tokens/interpolated.md)
- [<span data-ttu-id="4eee5-161">string</span><span class="sxs-lookup"><span data-stu-id="4eee5-161">string</span></span>](string.md)
