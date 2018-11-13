---
title: 文字列 (F#)
description: F# の 'string' 型が Unicode 文字のシーケンスとして変更不可のテキストを表示する方法について説明します。
ms.date: 05/16/2016
ms.openlocfilehash: 21971602093bc84b0df47d4ae46a14fb936c28bb
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/02/2018
ms.locfileid: "43799344"
---
# <a name="strings"></a><span data-ttu-id="031e5-103">文字列</span><span class="sxs-lookup"><span data-stu-id="031e5-103">Strings</span></span>

> [!NOTE]
<span data-ttu-id="031e5-104">この記事の API リファレンスのリンクをクリックすると MSDN に移動します。</span><span class="sxs-lookup"><span data-stu-id="031e5-104">The API reference links in this article will take you to MSDN.</span></span>  <span data-ttu-id="031e5-105">docs.microsoft.com API リファレンスは完全ではありません。</span><span class="sxs-lookup"><span data-stu-id="031e5-105">The docs.microsoft.com API reference is not complete.</span></span>

<span data-ttu-id="031e5-106">`string`型が Unicode 文字のシーケンスとして変更不可のテキストを表します。</span><span class="sxs-lookup"><span data-stu-id="031e5-106">The `string` type represents immutable text as a sequence of Unicode characters.</span></span> <span data-ttu-id="031e5-107">`string` は、.NET Framework の `System.String` のエイリアスです。</span><span class="sxs-lookup"><span data-stu-id="031e5-107">`string` is an alias for `System.String` in the .NET Framework.</span></span>

## <a name="remarks"></a><span data-ttu-id="031e5-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="031e5-108">Remarks</span></span>

<span data-ttu-id="031e5-109">文字列リテラルは引用符 (") 文字で区切られます。</span><span class="sxs-lookup"><span data-stu-id="031e5-109">String literals are delimited by the quotation mark (") character.</span></span> <span data-ttu-id="031e5-110">円記号 ( \\ ) 特定の特殊文字をエンコードするために使用します。</span><span class="sxs-lookup"><span data-stu-id="031e5-110">The backslash character ( \\ ) is used to encode certain special characters.</span></span> <span data-ttu-id="031e5-111">円記号と、次の文字の組み合わせと呼ばれる、*エスケープ シーケンス*します。</span><span class="sxs-lookup"><span data-stu-id="031e5-111">The backslash and the next character together are known as an *escape sequence*.</span></span> <span data-ttu-id="031e5-112">エスケープ シーケンスが F# 文字列リテラルは、次の表に示すでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="031e5-112">Escape sequences supported in F# string literals are shown in the following table.</span></span>

|<span data-ttu-id="031e5-113">文字</span><span class="sxs-lookup"><span data-stu-id="031e5-113">Character</span></span>|<span data-ttu-id="031e5-114">エスケープ シーケンス</span><span class="sxs-lookup"><span data-stu-id="031e5-114">Escape sequence</span></span>|
|---------|---------------|
|<span data-ttu-id="031e5-115">バックスペース</span><span class="sxs-lookup"><span data-stu-id="031e5-115">Backspace</span></span>|`\b`|
|<span data-ttu-id="031e5-116">改行</span><span class="sxs-lookup"><span data-stu-id="031e5-116">Newline</span></span>|`\n`|
|<span data-ttu-id="031e5-117">キャリッジ リターン</span><span class="sxs-lookup"><span data-stu-id="031e5-117">Carriage return</span></span>|`\r`|
|<span data-ttu-id="031e5-118">タブ</span><span class="sxs-lookup"><span data-stu-id="031e5-118">Tab</span></span>|`\t`|
|<span data-ttu-id="031e5-119">円記号</span><span class="sxs-lookup"><span data-stu-id="031e5-119">Backslash</span></span>|`\\`|
|<span data-ttu-id="031e5-120">引用符</span><span class="sxs-lookup"><span data-stu-id="031e5-120">Quotation mark</span></span>|`\"`|
|<span data-ttu-id="031e5-121">アポストロフィ</span><span class="sxs-lookup"><span data-stu-id="031e5-121">Apostrophe</span></span>|`\'`|
|<span data-ttu-id="031e5-122">Unicode 文字</span><span class="sxs-lookup"><span data-stu-id="031e5-122">Unicode character</span></span>|<span data-ttu-id="031e5-123">`\uXXXX` または`\UXXXX`(場所`X`16 進数の数字を示します)</span><span class="sxs-lookup"><span data-stu-id="031e5-123">`\uXXXX` or `\UXXXX` (where `X` indicates a hexadecimal digit)</span></span>|

<span data-ttu-id="031e5-124">前にある場合、@ 記号、リテラルには、逐語的文字列。</span><span class="sxs-lookup"><span data-stu-id="031e5-124">If preceded by the @ symbol, the literal is a verbatim string.</span></span> <span data-ttu-id="031e5-125">つまり、2 つの引用符文字が 1 つの引用符文字として解釈される点が異なりますエスケープ シーケンスが無視します。</span><span class="sxs-lookup"><span data-stu-id="031e5-125">This means that any escape sequences are ignored, except that two quotation mark characters are interpreted as one quotation mark character.</span></span>

<span data-ttu-id="031e5-126">さらに、文字列の場合は、三重引用符で囲まれている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="031e5-126">Additionally, a string may be enclosed by triple quotes.</span></span> <span data-ttu-id="031e5-127">この場合、すべてのエスケープ シーケンスは無視されます、二重引用符文字も含まれます。</span><span class="sxs-lookup"><span data-stu-id="031e5-127">In this case, all escape sequences are ignored, including double quotation mark characters.</span></span> <span data-ttu-id="031e5-128">埋め込まれた文字列を引用符で囲まれたを含む文字列を指定するには、逐語的文字列または三重引用符で囲まれた文字列か、使用できます。</span><span class="sxs-lookup"><span data-stu-id="031e5-128">To specify a string that contains an embedded quoted string, you can either use a verbatim string or a triple-quoted string.</span></span> <span data-ttu-id="031e5-129">逐語的文字列を使用する場合は、一重引用符文字を示す 2 つの引用符文字を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="031e5-129">If you use a verbatim string, you  must specify two quotation mark characters to indicate a single quotation mark character.</span></span> <span data-ttu-id="031e5-130">三重引用符で囲まれた文字列を使用する場合は、文字列の末尾として解析することがなく、単一引用符文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="031e5-130">If you use a triple-quoted string, you can use the single quotation mark characters without them being parsed as the end of the string.</span></span> <span data-ttu-id="031e5-131">この方法は、XML または埋め込まれた引用符を含むその他の構造を操作する場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="031e5-131">This technique can be useful when you work with XML or other structures that include embedded quotation marks.</span></span>

```fsharp
// Using a verbatim string
let xmlFragment1 = @"<book author=""Milton, John"" title=""Paradise Lost"">"

// Using a triple-quoted string
let xmlFragment2 = """<book author="Milton, John" title="Paradise Lost">"""
```

<span data-ttu-id="031e5-132">コードでは、文字列は、改行が受け入れられ、改行以外として解釈されますとして改行、円記号が改行の前に最後の文字。</span><span class="sxs-lookup"><span data-stu-id="031e5-132">In code, strings that have line breaks are accepted and the line breaks are interpreted literally as newlines, unless a backslash character is the last character before the line break.</span></span> <span data-ttu-id="031e5-133">次の行の先頭の空白文字には、円記号を使用する場合は無視されます。</span><span class="sxs-lookup"><span data-stu-id="031e5-133">Leading white space on the next line is ignored when the backslash character is used.</span></span> <span data-ttu-id="031e5-134">次のコードには、文字列が生成されます。`str1`値を持つ`"abc\ndef"`と文字列`str2`値を持つ`"abcdef"`します。</span><span class="sxs-lookup"><span data-stu-id="031e5-134">The following code produces a string `str1` that has value `"abc\ndef"` and a string `str2` that has value `"abcdef"`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1001.fs)]

<span data-ttu-id="031e5-135">文字列の個々 の文字は、次のように配列に似た構文を使用してアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="031e5-135">You can access individual characters in a string by using array-like syntax, as follows.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1002.fs)]

<span data-ttu-id="031e5-136">出力は `b`になります。</span><span class="sxs-lookup"><span data-stu-id="031e5-136">The output is `b`.</span></span>

<span data-ttu-id="031e5-137">または、次のコードに示すように、配列スライス構文を使用して部分文字列を抽出することができます。</span><span class="sxs-lookup"><span data-stu-id="031e5-137">Or you can extract substrings by using array slice syntax, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1003.fs)]

<span data-ttu-id="031e5-138">出力は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="031e5-138">The output is as follows.</span></span>

```
abc
def
```

<span data-ttu-id="031e5-139">ASCII 文字列型の符号なしバイトの配列で表現できます`byte[]`します。</span><span class="sxs-lookup"><span data-stu-id="031e5-139">You can represent ASCII strings by arrays of unsigned bytes, type `byte[]`.</span></span> <span data-ttu-id="031e5-140">サフィックスを追加する`B`を ASCII 文字列であることを示すリテラル文字列にします。</span><span class="sxs-lookup"><span data-stu-id="031e5-140">You add the suffix `B` to a string literal to indicate that it is an ASCII string.</span></span> <span data-ttu-id="031e5-141">ASCII 文字列リテラルのバイト配列を使用では、Unicode のエスケープ シーケンスを除く、Unicode 文字列として同じエスケープ シーケンスをサポートします。</span><span class="sxs-lookup"><span data-stu-id="031e5-141">ASCII string literals used with byte arrays support the same escape sequences as Unicode strings, except for the Unicode escape sequences.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1004.fs)]

## <a name="string-operators"></a><span data-ttu-id="031e5-142">文字列演算子</span><span class="sxs-lookup"><span data-stu-id="031e5-142">String Operators</span></span>

<span data-ttu-id="031e5-143">文字列を連結する 2 つの方法があります: を使用して、`+`演算子またはを使用して、`^`演算子。</span><span class="sxs-lookup"><span data-stu-id="031e5-143">There are two ways to concatenate strings: by using the `+` operator or by using the `^` operator.</span></span> <span data-ttu-id="031e5-144">`+`演算子が、.NET Framework の文字列処理機能との互換性を維持します。</span><span class="sxs-lookup"><span data-stu-id="031e5-144">The `+` operator maintains compatibility with the .NET Framework string handling features.</span></span>

<span data-ttu-id="031e5-145">次の例は、文字列の連結を示しています。</span><span class="sxs-lookup"><span data-stu-id="031e5-145">The following example illustrates string concatenation.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1006.fs)]

## <a name="string-class"></a><span data-ttu-id="031e5-146">String クラス</span><span class="sxs-lookup"><span data-stu-id="031e5-146">String Class</span></span>

<span data-ttu-id="031e5-147">F# の文字列型である .NET Framework では実際に`System.String`すべての入力、`System.String`メンバーは使用できます。</span><span class="sxs-lookup"><span data-stu-id="031e5-147">Because the string type in F# is actually a .NET Framework `System.String` type, all the `System.String` members are available.</span></span> <span data-ttu-id="031e5-148">これが含まれています、`+`演算子、文字列の連結に使用される、`Length`プロパティ、および`Chars`プロパティで、文字列を Unicode 文字の配列として返します。</span><span class="sxs-lookup"><span data-stu-id="031e5-148">This includes the `+` operator, which is used to concatenate strings, the `Length` property, and the `Chars` property, which returns the string as an array of Unicode characters.</span></span> <span data-ttu-id="031e5-149">文字列の詳細については、次を参照してください。`System.String`します。</span><span class="sxs-lookup"><span data-stu-id="031e5-149">For more information about strings, see `System.String`.</span></span>

<span data-ttu-id="031e5-150">使用して、`Chars`プロパティの`System.String`文字列の個々 の文字の次のコードに示すように、インデックスを指定することでアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="031e5-150">By using the `Chars` property of `System.String`, you can access the individual characters in a string by specifying an index, as is shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1005.fs)]

## <a name="string-module"></a><span data-ttu-id="031e5-151">文字列のモジュール</span><span class="sxs-lookup"><span data-stu-id="031e5-151">String Module</span></span>

<span data-ttu-id="031e5-152">含まれている文字列の処理の追加機能、`String`でモジュール、`FSharp.Core`名前空間。</span><span class="sxs-lookup"><span data-stu-id="031e5-152">Additional functionality for string handling is included in the `String` module in the `FSharp.Core` namespace.</span></span> <span data-ttu-id="031e5-153">詳細については、次を参照してください。 [Core.String モジュール](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.string-module-%5bfsharp%5d)します。</span><span class="sxs-lookup"><span data-stu-id="031e5-153">For more information, see [Core.String Module](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.string-module-%5bfsharp%5d).</span></span>

## <a name="see-also"></a><span data-ttu-id="031e5-154">関連項目</span><span class="sxs-lookup"><span data-stu-id="031e5-154">See also</span></span>

- [<span data-ttu-id="031e5-155">F# 言語リファレンス</span><span class="sxs-lookup"><span data-stu-id="031e5-155">F# Language Reference</span></span>](index.md)
