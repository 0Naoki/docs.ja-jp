---
title: '方法: 数値に先行するゼロを埋め込む'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- numeric format strings [.NET Framework]
- formatting [.NET Framework], numbers
- number formatting [.NET Framework]
- numbers [.NET Framework], format strings
ms.assetid: 0b2c2cb5-c580-4891-8d81-cb632f5ec384
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b48462e79c3e8ef3fdd6e0a91f5abecffc022b5c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54673035"
---
# <a name="how-to-pad-a-number-with-leading-zeros"></a><span data-ttu-id="913c6-102">方法: 数値に先行するゼロを埋め込む</span><span class="sxs-lookup"><span data-stu-id="913c6-102">How to: Pad a Number with Leading Zeros</span></span>
<span data-ttu-id="913c6-103">整数値に先行ゼロを追加するには、精度指定子と[標準の数値書式指定文字列](../../../docs/standard/base-types/standard-numeric-format-strings.md) "D" を使用します。</span><span class="sxs-lookup"><span data-stu-id="913c6-103">You can add leading zeros to an integer by using the "D" [standard numeric format string](../../../docs/standard/base-types/standard-numeric-format-strings.md) with a precision specifier.</span></span> <span data-ttu-id="913c6-104">整数値と浮動小数点数値の両方に先行ゼロを追加するには、[カスタム数値書式指定文字列](../../../docs/standard/base-types/custom-numeric-format-strings.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="913c6-104">You can add leading zeros to both integer and floating-point numbers by using a [custom numeric format string](../../../docs/standard/base-types/custom-numeric-format-strings.md).</span></span> <span data-ttu-id="913c6-105">このトピックでは、この両方の方法で数値に先行ゼロを埋め込む方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="913c6-105">This topic shows how to use both methods to pad a number with leading zeros.</span></span>  
  
### <a name="to-pad-an-integer-with-leading-zeros-to-a-specific-length"></a><span data-ttu-id="913c6-106">特定の長さになるまで整数値に先行ゼロを埋め込むには</span><span class="sxs-lookup"><span data-stu-id="913c6-106">To pad an integer with leading zeros to a specific length</span></span>  
  
1.  <span data-ttu-id="913c6-107">整数値を表示する際の最小桁数を決定します。</span><span class="sxs-lookup"><span data-stu-id="913c6-107">Determine the minimum number of digits you want the integer value to display.</span></span> <span data-ttu-id="913c6-108">この数には先行桁数も含みます。</span><span class="sxs-lookup"><span data-stu-id="913c6-108">Include any leading digits in this number.</span></span>  
  
2.  <span data-ttu-id="913c6-109">整数値を 10 進数値と 16 進数値のどちらで表示するかを決定します。</span><span class="sxs-lookup"><span data-stu-id="913c6-109">Determine whether you want to display the integer as a decimal value or a hexadecimal value.</span></span>  
  
    -   <span data-ttu-id="913c6-110">整数値を 10 進数値として表示するには、`ToString(String)` メソッドを呼び出し、`format` パラメーターの値として文字列 "D*n*" を渡します。この *n* は、文字列の最小長を表します。</span><span class="sxs-lookup"><span data-stu-id="913c6-110">To display the integer as a decimal value, call its `ToString(String)` method, and pass the string "D*n*" as the value of the `format` parameter, where *n* represents the minimum length of the string.</span></span>  
  
    -   <span data-ttu-id="913c6-111">整数値を 16 進数値として表示するには、`ToString(String)` メソッドを呼び出し、`format` パラメーターの値として文字列 "X*n*" を渡します。この *n* は、文字列の最小長を表します。</span><span class="sxs-lookup"><span data-stu-id="913c6-111">To display the integer as a hexadecimal value, call its `ToString(String)` method and pass the string "X*n*" as the value of the `format` parameter, where *n* represents the minimum length of the string.</span></span>  
  
     <span data-ttu-id="913c6-112">また、<xref:System.String.Format%2A> や <xref:System.Console.WriteLine%2A> など、[複合書式指定](../../../docs/standard/base-types/composite-formatting.md)を使用するメソッドでもこの書式指定文字列を使用できます。</span><span class="sxs-lookup"><span data-stu-id="913c6-112">You can also use the format string in a method, such as <xref:System.String.Format%2A> or <xref:System.Console.WriteLine%2A>, that uses [composite formatting](../../../docs/standard/base-types/composite-formatting.md).</span></span>  
  
 <span data-ttu-id="913c6-113">次の例は、書式指定された数値全体の長さが 8 文字以上になるように、先行ゼロを使用してさまざまな数値を書式指定します。</span><span class="sxs-lookup"><span data-stu-id="913c6-113">The following example formats several integer values with leading zeros so that the total length of the formatted number is at least eight characters.</span></span>  
  
 [!code-csharp[Formatting.HowTo.PadNumber#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.PadNumber/cs/Pad1.cs#1)]
 [!code-vb[Formatting.HowTo.PadNumber#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.PadNumber/vb/Pad1.vb#1)]  
  
### <a name="to-pad-an-integer-with-a-specific-number-of-leading-zeros"></a><span data-ttu-id="913c6-114">特定の数の先行ゼロを整数値に埋め込むには</span><span class="sxs-lookup"><span data-stu-id="913c6-114">To pad an integer with a specific number of leading zeros</span></span>  
  
1.  <span data-ttu-id="913c6-115">整数値に表示する先行ゼロの数を決定します。</span><span class="sxs-lookup"><span data-stu-id="913c6-115">Determine how many leading zeros you want the integer value to display.</span></span>  
  
2.  <span data-ttu-id="913c6-116">整数値を 10 進数値と 16 進数値のどちらで表示するかを決定します。</span><span class="sxs-lookup"><span data-stu-id="913c6-116">Determine whether you want to display the integer as a decimal value or a hexadecimal value.</span></span> <span data-ttu-id="913c6-117">10 進数値として書式指定する場合には標準書式指定子 "D" を使用する必要があります。16 進数値として書式指定する場合には標準書式指定子 "X" を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="913c6-117">Formatting it as a decimal value requires that you use the "D" standard format specifier; formatting it as a hexadecimal value requires that you use the "X" standard format specifier.</span></span>  
  
3.  <span data-ttu-id="913c6-118">整数値の `ToString("D").Length` メソッドまたは `ToString("X").Length` メソッドを使用して、先行ゼロが埋め込まれていない数値文字列の長さを決定します。</span><span class="sxs-lookup"><span data-stu-id="913c6-118">Determine the length of the unpadded numeric string by calling the integer value's `ToString("D").Length` or `ToString("X").Length` method.</span></span>  
  
4.  <span data-ttu-id="913c6-119">書式指定した文字列に埋め込む先行ゼロの数を、埋め込まれていない数値の文字列の長さに加算します。</span><span class="sxs-lookup"><span data-stu-id="913c6-119">Add the number of leading zeros that you want to include in the formatted string to the length of the unpadded numeric string.</span></span> <span data-ttu-id="913c6-120">これにより、埋め込み文字列全体の長さが定義されます。</span><span class="sxs-lookup"><span data-stu-id="913c6-120">This defines the total length of the padded string.</span></span>  
  
5.  <span data-ttu-id="913c6-121">整数値の `ToString(String)` メソッドを呼び出し、10 進数値文字列の場合は "D*n*"、16 進数値の場合は "X*n*" を渡します。*n* は埋め込み文字列全体の長さを表します。</span><span class="sxs-lookup"><span data-stu-id="913c6-121">Call the integer value's `ToString(String)` method, and pass the string "D*n*" for decimal strings and "X*n*" for hexadecimal strings, where *n* represents the total length of the padded string.</span></span> <span data-ttu-id="913c6-122">書式指定文字列 "D*n*" または "X*n*"は、複合書式指定をサポートするメソッドでも使用できます。</span><span class="sxs-lookup"><span data-stu-id="913c6-122">You can also use the "D*n*" or "X*n*" format string in a method that supports composite formatting.</span></span>  
  
 <span data-ttu-id="913c6-123">次の例は、整数値に 5 つの先行ゼロを埋め込みます。</span><span class="sxs-lookup"><span data-stu-id="913c6-123">The following example pads an integer value with five leading zeros.</span></span>  
  
 [!code-csharp[Formatting.HowTo.PadNumber#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.PadNumber/cs/Pad1.cs#2)]
 [!code-vb[Formatting.HowTo.PadNumber#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.PadNumber/vb/Pad1.vb#2)]  
  
### <a name="to-pad-a-numeric-value-with-leading-zeros-to-a-specific-length"></a><span data-ttu-id="913c6-124">特定の長さになるまで数値に先行ゼロを埋め込むには</span><span class="sxs-lookup"><span data-stu-id="913c6-124">To pad a numeric value with leading zeros to a specific length</span></span>  
  
1.  <span data-ttu-id="913c6-125">文字列形式の数値の整数部分の桁数を決定します。</span><span class="sxs-lookup"><span data-stu-id="913c6-125">Determine how many digits to the left of the decimal you want the string representation of the number to have.</span></span> <span data-ttu-id="913c6-126">合計桁数には先行ゼロも含みます。</span><span class="sxs-lookup"><span data-stu-id="913c6-126">Include any leading zeros in this total number of digits.</span></span>  
  
2.  <span data-ttu-id="913c6-127">ゼロの最小数を表すゼロ プレースホルダー ("0") を使用するカスタム数値書式指定文字列を定義します。</span><span class="sxs-lookup"><span data-stu-id="913c6-127">Define a custom numeric format string that uses the zero placeholder ("0") to represent the minimum number of zeros.</span></span>  
  
3.  <span data-ttu-id="913c6-128">数値の `ToString(String)` メソッドを呼び出し、カスタム書式指定文字列を渡します。</span><span class="sxs-lookup"><span data-stu-id="913c6-128">Call the number's `ToString(String)` method and pass it the custom format string.</span></span> <span data-ttu-id="913c6-129">カスタム書式指定文字列は、複合書式指定をサポートしているメソッドでも使用できます。</span><span class="sxs-lookup"><span data-stu-id="913c6-129">You can also use the custom format string with a method that supports composite formatting.</span></span>  
  
 <span data-ttu-id="913c6-130">次の例は、書式指定された数値全体の長さが 8 文字以上の整数になるように、先行ゼロを使用してさまざまな数値を書式指定します。</span><span class="sxs-lookup"><span data-stu-id="913c6-130">The following example formats several numeric values with leading zeros so that the total length of the formatted number is at least eight digits to the left of the decimal.</span></span>  
  
 [!code-csharp[Formatting.HowTo.PadNumber#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.PadNumber/cs/Pad1.cs#3)]
 [!code-vb[Formatting.HowTo.PadNumber#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.PadNumber/vb/Pad1.vb#3)]  
  
### <a name="to-pad-a-numeric-value-with-a-specific-number-of-leading-zeros"></a><span data-ttu-id="913c6-131">特定の数の先行ゼロを数値に埋め込むには</span><span class="sxs-lookup"><span data-stu-id="913c6-131">To pad a numeric value with a specific number of leading zeros</span></span>  
  
1.  <span data-ttu-id="913c6-132">数値に埋め込む先行ゼロの数を決定します。</span><span class="sxs-lookup"><span data-stu-id="913c6-132">Determine how many leading zeros you want the numeric value to have.</span></span>  
  
2.  <span data-ttu-id="913c6-133">埋め込みのない数値文字列での整数部の桁数を決定します。</span><span class="sxs-lookup"><span data-stu-id="913c6-133">Determine the number of digits to the left of the decimal in the unpadded numeric string.</span></span> <span data-ttu-id="913c6-134">この操作を行うには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="913c6-134">To do this:</span></span>  
  
    1.  <span data-ttu-id="913c6-135">文字列形式の数値に小数点が含まれるかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="913c6-135">Determine whether the string representation of a number includes a decimal point symbol.</span></span>  
  
    2.  <span data-ttu-id="913c6-136">小数点記号を含める場合は、整数部分の文字数を決定します。</span><span class="sxs-lookup"><span data-stu-id="913c6-136">If it does include a decimal point symbol, determine the number of characters to the left of the decimal point.</span></span>  
  
         <span data-ttu-id="913c6-137">- または -</span><span class="sxs-lookup"><span data-stu-id="913c6-137">-or-</span></span>  
  
         <span data-ttu-id="913c6-138">小数点記号を含めない場合は、文字列の長さを決定します。</span><span class="sxs-lookup"><span data-stu-id="913c6-138">If it does not include a decimal point symbol, determine the string's length.</span></span>  
  
3.  <span data-ttu-id="913c6-139">文字列に表示する各先行ゼロの位置にゼロ プレースホルダー ("0") を使用し、既定の文字列の各桁の位置にゼロ プレースホルダーまたは桁プレースホルダー ("#") を使用するカスタム書式指定文字列を作成します。</span><span class="sxs-lookup"><span data-stu-id="913c6-139">Create a custom format string that uses the zero placeholder ("0") for each of the leading zeros to appear in the string, and that uses either the zero placeholder or the digit placeholder ("#") to represent each digit in the default string.</span></span>  
  
4.  <span data-ttu-id="913c6-140">数値の `ToString(String)` メソッド、または複合書式指定をサポートするメソッドのパラメーターとして、カスタム書式指定文字列を指定します。</span><span class="sxs-lookup"><span data-stu-id="913c6-140">Supply the custom format string as a parameter either to the number's `ToString(String)` method or to a method that supports composite formatting.</span></span>  
  
 <span data-ttu-id="913c6-141">次の例は、2 つの <xref:System.Double> 値を 5 つの先行ゼロで埋め込みます。</span><span class="sxs-lookup"><span data-stu-id="913c6-141">The following example pads two <xref:System.Double> values with five leading zeros.</span></span>  
  
 [!code-csharp[Formatting.HowTo.PadNumber#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.PadNumber/cs/Pad1.cs#4)]
 [!code-vb[Formatting.HowTo.PadNumber#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.PadNumber/vb/Pad1.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="913c6-142">関連項目</span><span class="sxs-lookup"><span data-stu-id="913c6-142">See also</span></span>

- [<span data-ttu-id="913c6-143">Custom Numeric Format Strings</span><span class="sxs-lookup"><span data-stu-id="913c6-143">Custom Numeric Format Strings</span></span>](../../../docs/standard/base-types/custom-numeric-format-strings.md)
- [<span data-ttu-id="913c6-144">Standard Numeric Format Strings</span><span class="sxs-lookup"><span data-stu-id="913c6-144">Standard Numeric Format Strings</span></span>](../../../docs/standard/base-types/standard-numeric-format-strings.md)
- [<span data-ttu-id="913c6-145">複合書式指定</span><span class="sxs-lookup"><span data-stu-id="913c6-145">Composite Formatting</span></span>](../../../docs/standard/base-types/composite-formatting.md)
