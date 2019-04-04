---
title: WPF のグローバリゼーション
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [WPF], international user interface
- XAML [WPF], globalization
- international user interface [WPF], XAML
- globalization [WPF]
ms.assetid: 4571ccfe-8a60-4f06-9b37-7ac0b1c2d10f
ms.openlocfilehash: dee1df1e122e47ea67618da5a1e4349e28d90447
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57377366"
---
# <a name="globalization-for-wpf"></a><span data-ttu-id="6d14f-102">WPF のグローバリゼーション</span><span class="sxs-lookup"><span data-stu-id="6d14f-102">Globalization for WPF</span></span>
<span data-ttu-id="6d14f-103">このトピックで作成する際に注意する必要がある問題が発生する[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]グローバル市場向けアプリケーション。</span><span class="sxs-lookup"><span data-stu-id="6d14f-103">This topic introduces issues that you should be aware of when writing [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] applications for the global market.</span></span> <span data-ttu-id="6d14f-104">グローバリゼーション プログラミングの要素がで定義されている[!INCLUDE[TLA#tla_net](../../../../includes/tlasharptla-net-md.md)]で`System.Globalization`します。</span><span class="sxs-lookup"><span data-stu-id="6d14f-104">The globalization programming elements are defined in [!INCLUDE[TLA#tla_net](../../../../includes/tlasharptla-net-md.md)] in `System.Globalization`.</span></span>



<a name="xaml_globalization"></a>
## <a name="xaml-globalization"></a><span data-ttu-id="6d14f-105">XAML グローバリゼーション</span><span class="sxs-lookup"><span data-stu-id="6d14f-105">XAML Globalization</span></span>
 [!INCLUDE[TLA#tla_xaml#initcap](../../../../includes/tlasharptla-xamlsharpinitcap-md.md)] <span data-ttu-id="6d14f-106">に基づいて[!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)]で定義されているグローバリゼーション サポートを利用して、[!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]仕様。</span><span class="sxs-lookup"><span data-stu-id="6d14f-106">is based on [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] and takes advantage of the globalization support defined in the [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] specification.</span></span> <span data-ttu-id="6d14f-107">次のセクションでは、いくつか説明[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]を意識する必要がある機能です。</span><span class="sxs-lookup"><span data-stu-id="6d14f-107">The following sections describe some [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] features that you should be aware of.</span></span>

<a name="char_reference"></a>
### <a name="character-references"></a><span data-ttu-id="6d14f-108">文字参照</span><span class="sxs-lookup"><span data-stu-id="6d14f-108">Character References</span></span>
<span data-ttu-id="6d14f-109">文字参照では、特定の UTF16 コード単位[!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)]文字、10 進数または 16 進数のいずれかを表します。</span><span class="sxs-lookup"><span data-stu-id="6d14f-109">A character reference gives the UTF16 code unit of the particular [!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)] character it represents, in either decimal or hexadecimal.</span></span> <span data-ttu-id="6d14f-110">次の例では、コプト文字の大文字に、または 'Ϩ' の参照を 10 進数の文字を示しています。</span><span class="sxs-lookup"><span data-stu-id="6d14f-110">The following example shows a decimal character reference for the COPTIC CAPITAL LETTER HORI, or 'Ϩ':</span></span>

```
&#1000;
```

<span data-ttu-id="6d14f-111">次の例では、16 進数の文字の一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="6d14f-111">The following example shows a hexadecimal character reference.</span></span> <span data-ttu-id="6d14f-112">持つことに注意してください、 **x** 16 進数の前にします。</span><span class="sxs-lookup"><span data-stu-id="6d14f-112">Notice that it has an **x** in front of the hexadecimal number.</span></span>

```
&#x3E8;
```

<a name="encoding"></a>
### <a name="encoding"></a><span data-ttu-id="6d14f-113">エンコード</span><span class="sxs-lookup"><span data-stu-id="6d14f-113">Encoding</span></span>
 <span data-ttu-id="6d14f-114">サポートされているエンコード[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]は[!INCLUDE[TLA#tla_ascii](../../../../includes/tlasharptla-ascii-md.md)]、 [!INCLUDE[TLA2#tla_unicode](../../../../includes/tla2sharptla-unicode-md.md)] utf-16 と utf-8 です。</span><span class="sxs-lookup"><span data-stu-id="6d14f-114">The encoding supported by [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] are [!INCLUDE[TLA#tla_ascii](../../../../includes/tlasharptla-ascii-md.md)], [!INCLUDE[TLA2#tla_unicode](../../../../includes/tla2sharptla-unicode-md.md)] UTF-16, and UTF-8.</span></span> <span data-ttu-id="6d14f-115">エンコード ステートメントがの先頭に[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]ドキュメント。</span><span class="sxs-lookup"><span data-stu-id="6d14f-115">The encoding statement is at the beginning of [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] document.</span></span> <span data-ttu-id="6d14f-116">エンコーディング属性が存在せず、バイト順もない場合、パーサーでは既定として UTF-8 が使用されます。</span><span class="sxs-lookup"><span data-stu-id="6d14f-116">If no encoding attribute exists and there is no byte-order, the parser defaults to UTF-8.</span></span> <span data-ttu-id="6d14f-117">UTF-8 と UTF-16 は優先エンコードです。</span><span class="sxs-lookup"><span data-stu-id="6d14f-117">UTF-8 and UTF-16 are the preferred encodings.</span></span> <span data-ttu-id="6d14f-118">UTF-7 には対応していません。</span><span class="sxs-lookup"><span data-stu-id="6d14f-118">UTF-7 is not supported.</span></span> <span data-ttu-id="6d14f-119">次の例で utf-8 エンコードを指定する方法を示します、[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]ファイル。</span><span class="sxs-lookup"><span data-stu-id="6d14f-119">The following example demonstrates how to specify a UTF-8 encoding in a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file.</span></span>

```
?xml encoding="UTF-8"?
```

<a name="lang_attrib"></a>
### <a name="language-attribute"></a><span data-ttu-id="6d14f-120">言語属性</span><span class="sxs-lookup"><span data-stu-id="6d14f-120">Language Attribute</span></span>
 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] <span data-ttu-id="6d14f-121">使用して[xml:lang](../../xaml-services/xml-lang-handling-in-xaml.md)を要素の language 属性を表します。</span><span class="sxs-lookup"><span data-stu-id="6d14f-121">uses [xml:lang](../../xaml-services/xml-lang-handling-in-xaml.md) to represent the language attribute of an element.</span></span>  <span data-ttu-id="6d14f-122">活用するために、<xref:System.Globalization.CultureInfo>クラス、言語属性の値で定義済みカルチャ名のいずれかを指定する必要がある<xref:System.Globalization.CultureInfo>します。</span><span class="sxs-lookup"><span data-stu-id="6d14f-122">To take advantage of the <xref:System.Globalization.CultureInfo> class, the language attribute value needs to be one of the culture names predefined by <xref:System.Globalization.CultureInfo>.</span></span> <span data-ttu-id="6d14f-123">[xml:lang](../../xaml-services/xml-lang-handling-in-xaml.md) は要素ツリーで継承可能であり (XML ルールによる継承であり、必ずしも依存関係プロパティの継承によるものではありません)、その既定値は、明示的に割り当てられていない場合、空の文字列になります。</span><span class="sxs-lookup"><span data-stu-id="6d14f-123">[xml:lang](../../xaml-services/xml-lang-handling-in-xaml.md) is inheritable in the element tree (by XML rules, not necessarily because of dependency property inheritance) and its default value is an empty string if it is not assigned explicitly.</span></span>

 <span data-ttu-id="6d14f-124">言語属性は、方言を指定するときに非常に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="6d14f-124">The language attribute is very useful for specifying dialects.</span></span> <span data-ttu-id="6d14f-125">たとえば、フランス語であれば、フランス、ケベック、ベルギー、スイスでスペル、語彙、発音が異なります。</span><span class="sxs-lookup"><span data-stu-id="6d14f-125">For example, French has different spelling, vocabulary, and pronunciation in France, Quebec, Belgium, and Switzerland.</span></span> <span data-ttu-id="6d14f-126">中国語、日本語、および韓国語のコード ポイントを共有することも[!INCLUDE[TLA2#tla_unicode](../../../../includes/tla2sharptla-unicode-md.md)]が、表意文字の形が異なるため、まったく別のフォントを使用します。</span><span class="sxs-lookup"><span data-stu-id="6d14f-126">Also Chinese, Japanese, and Korean share code points in [!INCLUDE[TLA2#tla_unicode](../../../../includes/tla2sharptla-unicode-md.md)], but the ideographic shapes are different and they use totally different fonts.</span></span>

 <span data-ttu-id="6d14f-127">次[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]の例では、`fr-CA`言語属性をカナダ フランス語を指定します。</span><span class="sxs-lookup"><span data-stu-id="6d14f-127">The following [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] example uses the `fr-CA` language attribute to specify Canadian French.</span></span>

```xml
<TextBlock xml:lang="fr-CA">Découvrir la France</TextBlock>
```

<a name="unicode"></a>
### <a name="unicode"></a><span data-ttu-id="6d14f-128">Unicode</span><span class="sxs-lookup"><span data-stu-id="6d14f-128">Unicode</span></span>
 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] <span data-ttu-id="6d14f-129">サポートされているすべて[!INCLUDE[TLA2#tla_unicode](../../../../includes/tla2sharptla-unicode-md.md)]サロゲートを含む機能。</span><span class="sxs-lookup"><span data-stu-id="6d14f-129">supports all [!INCLUDE[TLA2#tla_unicode](../../../../includes/tla2sharptla-unicode-md.md)] features including surrogates.</span></span> <span data-ttu-id="6d14f-130">文字セットにマップできる限り[!INCLUDE[TLA2#tla_unicode](../../../../includes/tla2sharptla-unicode-md.md)]、サポートされています。</span><span class="sxs-lookup"><span data-stu-id="6d14f-130">As long as the character set can be mapped to [!INCLUDE[TLA2#tla_unicode](../../../../includes/tla2sharptla-unicode-md.md)], it is supported.</span></span> <span data-ttu-id="6d14f-131">たとえば、GB18030 では、一部の文字が中国語、日本語、韓国語 (CFK) の拡張 A および B とサロゲート ペアにマッピングされているため、完全に対応しています。</span><span class="sxs-lookup"><span data-stu-id="6d14f-131">For example, GB18030 introduces some characters that are mapped to the Chinese, Japanese, and Korean (CFK) extension A and B and surrogate pairs, therefore it is fully supported.</span></span> <span data-ttu-id="6d14f-132">A[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]アプリケーションが使用できる<xref:System.Globalization.StringInfo>サロゲート ペアがあるかどうかを理解することや、組み合わせ文字なし文字列を操作します。</span><span class="sxs-lookup"><span data-stu-id="6d14f-132">A [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application can use <xref:System.Globalization.StringInfo> to manipulate strings without understanding whether they have surrogate pairs or combining characters.</span></span>

<a name="design_intl_ui_with_xaml"></a>
## <a name="designing-an-international-user-interface-with-xaml"></a><span data-ttu-id="6d14f-133">XAML で各国対応ユーザー インターフェイスを設計する</span><span class="sxs-lookup"><span data-stu-id="6d14f-133">Designing an International User Interface with XAML</span></span>
 <span data-ttu-id="6d14f-134">このセクションについて説明します[!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]機能アプリケーションを作成するときに考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6d14f-134">This section describes [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] features that you should consider when writing an application.</span></span>

<a name="intl_text"></a>
### <a name="international-text"></a><span data-ttu-id="6d14f-135">国際対応テキスト</span><span class="sxs-lookup"><span data-stu-id="6d14f-135">International Text</span></span>
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <span data-ttu-id="6d14f-136">サポートされている Microsoft .NET Framework のすべての書き込みのシステムの組み込みの処理が含まれています。</span><span class="sxs-lookup"><span data-stu-id="6d14f-136">includes built-in processing for all Microsoft .NET Framework supported writing systems.</span></span>

 <span data-ttu-id="6d14f-137">現在、次の書体がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="6d14f-137">The following scripts are currently supported:</span></span>

-   <span data-ttu-id="6d14f-138">アラビア語</span><span class="sxs-lookup"><span data-stu-id="6d14f-138">Arabic</span></span>

-   <span data-ttu-id="6d14f-139">ベンガル語</span><span class="sxs-lookup"><span data-stu-id="6d14f-139">Bengali</span></span>

-   <span data-ttu-id="6d14f-140">デバナガリ</span><span class="sxs-lookup"><span data-stu-id="6d14f-140">Devanagari</span></span>

-   <span data-ttu-id="6d14f-141">キリル言語</span><span class="sxs-lookup"><span data-stu-id="6d14f-141">Cyrillic</span></span>

-   <span data-ttu-id="6d14f-142">ギリシャ語</span><span class="sxs-lookup"><span data-stu-id="6d14f-142">Greek</span></span>

-   <span data-ttu-id="6d14f-143">グジャラート語</span><span class="sxs-lookup"><span data-stu-id="6d14f-143">Gujarati</span></span>

-   <span data-ttu-id="6d14f-144">グルムキー</span><span class="sxs-lookup"><span data-stu-id="6d14f-144">Gurmukhi</span></span>

-   <span data-ttu-id="6d14f-145">ヘブライ語</span><span class="sxs-lookup"><span data-stu-id="6d14f-145">Hebrew</span></span>

-   <span data-ttu-id="6d14f-146">表意文字スクリプト</span><span class="sxs-lookup"><span data-stu-id="6d14f-146">Ideographic scripts</span></span>

-   <span data-ttu-id="6d14f-147">カナラ語</span><span class="sxs-lookup"><span data-stu-id="6d14f-147">Kannada</span></span>

-   <span data-ttu-id="6d14f-148">ラオス語</span><span class="sxs-lookup"><span data-stu-id="6d14f-148">Lao</span></span>

-   <span data-ttu-id="6d14f-149">ラテン語</span><span class="sxs-lookup"><span data-stu-id="6d14f-149">Latin</span></span>

-   <span data-ttu-id="6d14f-150">マラヤーラム語</span><span class="sxs-lookup"><span data-stu-id="6d14f-150">Malayalam</span></span>

-   <span data-ttu-id="6d14f-151">モンゴル語</span><span class="sxs-lookup"><span data-stu-id="6d14f-151">Mongolian</span></span>

-   <span data-ttu-id="6d14f-152">オディア語</span><span class="sxs-lookup"><span data-stu-id="6d14f-152">Odia</span></span>

-   <span data-ttu-id="6d14f-153">シリア語</span><span class="sxs-lookup"><span data-stu-id="6d14f-153">Syriac</span></span>

-   <span data-ttu-id="6d14f-154">タミール語</span><span class="sxs-lookup"><span data-stu-id="6d14f-154">Tamil</span></span>

-   <span data-ttu-id="6d14f-155">テルグ語</span><span class="sxs-lookup"><span data-stu-id="6d14f-155">Telugu</span></span>

-   <span data-ttu-id="6d14f-156">ターナ</span><span class="sxs-lookup"><span data-stu-id="6d14f-156">Thaana</span></span>

-   <span data-ttu-id="6d14f-157">タイ語\*</span><span class="sxs-lookup"><span data-stu-id="6d14f-157">Thai\*</span></span>

-   <span data-ttu-id="6d14f-158">チベット語</span><span class="sxs-lookup"><span data-stu-id="6d14f-158">Tibetan</span></span>

 <span data-ttu-id="6d14f-159">\* このリリースでは、タイ語テキストを表示し、編集できますが、単語を分割することはできません。</span><span class="sxs-lookup"><span data-stu-id="6d14f-159">\*In this release the display and editing of Thai text is supported; word breaking is not.</span></span>

 <span data-ttu-id="6d14f-160">現在、次のスクリプトはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="6d14f-160">The following scripts are not currently supported:</span></span>

-   <span data-ttu-id="6d14f-161">クメール語</span><span class="sxs-lookup"><span data-stu-id="6d14f-161">Khmer</span></span>

-   <span data-ttu-id="6d14f-162">韓国語の古いハングル</span><span class="sxs-lookup"><span data-stu-id="6d14f-162">Korean Old Hangul</span></span>

-   <span data-ttu-id="6d14f-163">ミャンマー</span><span class="sxs-lookup"><span data-stu-id="6d14f-163">Myanmar</span></span>

-   <span data-ttu-id="6d14f-164">シンハラ語</span><span class="sxs-lookup"><span data-stu-id="6d14f-164">Sinhala</span></span>

 <span data-ttu-id="6d14f-165">すべての書記体系エンジン サポート[!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)]フォント。</span><span class="sxs-lookup"><span data-stu-id="6d14f-165">All the writing system engines support [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] fonts.</span></span> [!INCLUDE[TLA2#tla_opentype](../../../../includes/tla2sharptla-opentype-md.md)] <span data-ttu-id="6d14f-166">フォントを含めることができます、[!INCLUDE[TLA2#tla_opentype](../../../../includes/tla2sharptla-opentype-md.md)]より国際的およびハイエンドなタイポグラフィ フォントのデザイン、フォントの作成を有効にするレイアウト テーブル。</span><span class="sxs-lookup"><span data-stu-id="6d14f-166">fonts can include the [!INCLUDE[TLA2#tla_opentype](../../../../includes/tla2sharptla-opentype-md.md)] layout tables that enable font creators to design better international and high-end typographic fonts.</span></span> <span data-ttu-id="6d14f-167">[!INCLUDE[TLA2#tla_opentype](../../../../includes/tla2sharptla-opentype-md.md)]フォント レイアウト テーブルは、テキストのレイアウトを向上させるためにテキスト処理アプリケーションを有効にするグリフ代用、グリフ配置、位置揃え、基線配置に関する情報を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="6d14f-167">The [!INCLUDE[TLA2#tla_opentype](../../../../includes/tla2sharptla-opentype-md.md)] font layout tables contain information about glyph substitutions, glyph positioning, justification, and baseline positioning, enabling text-processing applications to improve text layout.</span></span>

 [!INCLUDE[TLA2#tla_opentype](../../../../includes/tla2sharptla-opentype-md.md)] <span data-ttu-id="6d14f-168">大量のグリフの処理の設定を使用してフォントを許可する[!INCLUDE[TLA2#tla_unicode](../../../../includes/tla2sharptla-unicode-md.md)]エンコードします。</span><span class="sxs-lookup"><span data-stu-id="6d14f-168">fonts allow the handling of large glyph sets using [!INCLUDE[TLA2#tla_unicode](../../../../includes/tla2sharptla-unicode-md.md)] encoding.</span></span> <span data-ttu-id="6d14f-169">このようなエンコードにより、広範な国際対応が可能になり、さまざまなグリフを印刷できます。</span><span class="sxs-lookup"><span data-stu-id="6d14f-169">Such encoding enables broad international support as well as for typographic glyph variants.</span></span>

 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <span data-ttu-id="6d14f-170">テキストのレンダリングが提要[!INCLUDE[TLA#tla_ct](../../../../includes/tlasharptla-ct-md.md)]サブピクセル技術解決の独立性をサポートします。</span><span class="sxs-lookup"><span data-stu-id="6d14f-170">text rendering is powered by [!INCLUDE[TLA#tla_ct](../../../../includes/tlasharptla-ct-md.md)] sub-pixel technology that supports resolution independence.</span></span> <span data-ttu-id="6d14f-171">これにより読みやすさが大幅に向上し、あらゆる書体で高品質の雑誌スタイルの書面を作成できます。</span><span class="sxs-lookup"><span data-stu-id="6d14f-171">This significantly improves legibility and provides the ability to support high quality magazine style documents for all scripts.</span></span>

<a name="intl_layout"></a>
### <a name="international-layout"></a><span data-ttu-id="6d14f-172">国際対応レイアウト</span><span class="sxs-lookup"><span data-stu-id="6d14f-172">International Layout</span></span>
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <span data-ttu-id="6d14f-173">では非常に便利な方法で横書きレイアウト、双方向レイアウト、縦書きレイアウトを作成できます。</span><span class="sxs-lookup"><span data-stu-id="6d14f-173">provides a very convenient way to support horizontal, bidirectional, and vertical layouts.</span></span> <span data-ttu-id="6d14f-174">プレゼンテーション フレームワークで、<xref:System.Windows.FrameworkElement.FlowDirection%2A>レイアウトを定義するプロパティを使用できます。</span><span class="sxs-lookup"><span data-stu-id="6d14f-174">In presentation framework the <xref:System.Windows.FrameworkElement.FlowDirection%2A> property can be used to define layout.</span></span> <span data-ttu-id="6d14f-175">フローの方向パターン:</span><span class="sxs-lookup"><span data-stu-id="6d14f-175">The flow direction patterns are:</span></span>

-   <span data-ttu-id="6d14f-176">*LeftToRight* - ラテン語や東アジア言語などのための横書きレイアウト。</span><span class="sxs-lookup"><span data-stu-id="6d14f-176">*LeftToRight* - horizontal layout for Latin, East Asian and so forth.</span></span>

-   <span data-ttu-id="6d14f-177">*RightToLeft* - アラビア語やヘブライ語などのための双方向レイアウト。</span><span class="sxs-lookup"><span data-stu-id="6d14f-177">*RightToLeft* - bidirectional for Arabic, Hebrew and so forth.</span></span>

<a name="developing_localizable_apps"></a>
## <a name="developing-localizable-applications"></a><span data-ttu-id="6d14f-178">ローカライズ可能なアプリケーションの開発</span><span class="sxs-lookup"><span data-stu-id="6d14f-178">Developing Localizable Applications</span></span>
 <span data-ttu-id="6d14f-179">世界中で利用されるアプリケーションを開発するときは、アプリケーションをローカライズ可能にすることを忘れてはなりません。</span><span class="sxs-lookup"><span data-stu-id="6d14f-179">When you write an application for global consumption you should keep in mind that the application must be localizable.</span></span> <span data-ttu-id="6d14f-180">後続のトピックで、考慮事項を指摘します。</span><span class="sxs-lookup"><span data-stu-id="6d14f-180">The following topics point out things to consider.</span></span>

<a name="mui"></a>
### <a name="multilingual-user-interface"></a><span data-ttu-id="6d14f-181">多言語ユーザー インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6d14f-181">Multilingual User Interface</span></span>
 <span data-ttu-id="6d14f-182">多言語ユーザー インターフェイス (MUI) は、[!INCLUDE[TLA#tla_ms](../../../../includes/tlasharptla-ms-md.md)]の切り替えをサポートして[!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)]別の 1 つの言語から。</span><span class="sxs-lookup"><span data-stu-id="6d14f-182">Multilingual User Interfaces (MUI) is a [!INCLUDE[TLA#tla_ms](../../../../includes/tlasharptla-ms-md.md)] support for switching [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] from one language to another.</span></span> <span data-ttu-id="6d14f-183">A[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]アプリケーションはアセンブリ モデルを使用して、MUI をサポートします。</span><span class="sxs-lookup"><span data-stu-id="6d14f-183">A [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application uses the assembly model to support MUI.</span></span> <span data-ttu-id="6d14f-184">1 つのアプリケーションに言語に依存しないアセンブリと言語に依存するサテライト リソース アセンブリが含まれます。</span><span class="sxs-lookup"><span data-stu-id="6d14f-184">One application contains language-neutral assemblies as well as language-dependent satellite resource assemblies.</span></span> <span data-ttu-id="6d14f-185">エントリ ポイントはメイン アセンブリのマネージド .EXE です。</span><span class="sxs-lookup"><span data-stu-id="6d14f-185">The entry point is a managed .EXE in the main assembly.</span></span>  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <span data-ttu-id="6d14f-186">リソース ローダーは活用、[!INCLUDE[TLA2#tla_netframewk](../../../../includes/tla2sharptla-netframewk-md.md)]のリソース ルックアップとフォールバックをサポートするためにリソース マネージャー。</span><span class="sxs-lookup"><span data-stu-id="6d14f-186">resource loader takes advantage of the [!INCLUDE[TLA2#tla_netframewk](../../../../includes/tla2sharptla-netframewk-md.md)]'s resource manager to support resource lookup and fallback.</span></span> <span data-ttu-id="6d14f-187">多言語サテライト アセンブリは同じメイン アセンブリと連動します。</span><span class="sxs-lookup"><span data-stu-id="6d14f-187">Multiple language satellite assemblies work with the same main assembly.</span></span> <span data-ttu-id="6d14f-188">読み込まれるリソース アセンブリに依存、<xref:System.Globalization.CultureInfo.CurrentUICulture%2A>現在のスレッド。</span><span class="sxs-lookup"><span data-stu-id="6d14f-188">The resource assembly that is loaded depends on the <xref:System.Globalization.CultureInfo.CurrentUICulture%2A> of the current thread.</span></span>

<a name="localizable_ui"></a>
### <a name="localizable-user-interface"></a><span data-ttu-id="6d14f-189">ローカライズ可能なユーザー インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6d14f-189">Localizable User Interface</span></span>
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <span data-ttu-id="6d14f-190">アプリケーションを使用して、[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]を定義する、[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="6d14f-190">applications use [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] to define their [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].</span></span> [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] <span data-ttu-id="6d14f-191">で開発すると、オブジェクトの階層に一連のプロパティとロジックを指定できます。</span><span class="sxs-lookup"><span data-stu-id="6d14f-191">allows developers to specify a hierarchy of objects with a set of properties and logic.</span></span> <span data-ttu-id="6d14f-192">主な用途[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]を開発する[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]アプリケーションが、これを使用して、任意の階層の指定[!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)]オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="6d14f-192">The primary use of [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] is to develop [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications but it can be used to specify a hierarchy of any [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] objects.</span></span> <span data-ttu-id="6d14f-193">ほとんどの開発者が使用して[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]アプリケーションを指定する[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]c# などのプログラミング言語を使用して、ユーザーとの対話に応答するとします。</span><span class="sxs-lookup"><span data-stu-id="6d14f-193">Most developers use [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] to specify their application's [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] and use a programming language such as C# to react to user interaction.</span></span>

 <span data-ttu-id="6d14f-194">リソースの観点から、[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]ファイルの説明の言語に依存するように設計[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]リソース要素は、そのため、最終的な配布形式が外国の言語にローカライズ可能にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6d14f-194">From a resource point of view, a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file designed to describe a language-dependent [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] is a resource element and therefore its final distribution format must be localizable to support international languages.</span></span> <span data-ttu-id="6d14f-195">[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]多くようにイベントが処理できない[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]アプリケーションは、これを行うコードのブロックを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="6d14f-195">Because [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] cannot handle events many [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] applications contain blocks of code to do this.</span></span> <span data-ttu-id="6d14f-196">詳細については、[XAML の概要 (WPF)](xaml-overview-wpf.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6d14f-196">For more information, see [XAML Overview (WPF)](xaml-overview-wpf.md).</span></span> <span data-ttu-id="6d14f-197">コードが除去し、異なるバイナリにコンパイル時に、[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]ファイルが XAML の BAML 形式にトークン化します。</span><span class="sxs-lookup"><span data-stu-id="6d14f-197">Code is stripped out and compiled into different binaries when a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file is tokenized into the BAML form of XAML.</span></span> <span data-ttu-id="6d14f-198">XAML ファイル、画像、その他の種類の管理対象リソース オブジェクトの BAML 形式はサテライト リソース アセンブリに組み込まれます。サテライト リソース アセンブリに組み込むことで、他の言語にローカライズできます。ローカライズが必要なければ、メイン アセンブリに組み込まれます。</span><span class="sxs-lookup"><span data-stu-id="6d14f-198">The BAML form of XAML files, images, and other types of managed resource objects are embedded in the satellite resource assembly, which can be localized into other languages, or the main assembly when localization is not required.</span></span>

> [!NOTE]
>  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <span data-ttu-id="6d14f-199">すべてのアプリケーション サポート、 [!INCLUDE[TLA2#tla_netframewk](../../../../includes/tla2sharptla-netframewk-md.md)] [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]文字列テーブルやイメージなどのリソース。</span><span class="sxs-lookup"><span data-stu-id="6d14f-199">applications support all the [!INCLUDE[TLA2#tla_netframewk](../../../../includes/tla2sharptla-netframewk-md.md)][!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] resources including string tables, images, and so forth.</span></span>

<a name="building_localizable_apps"></a>
### <a name="building-localizable-applications"></a><span data-ttu-id="6d14f-200">ローカライズ可能なアプリケーションの構築</span><span class="sxs-lookup"><span data-stu-id="6d14f-200">Building Localizable Applications</span></span>
 <span data-ttu-id="6d14f-201">ローカライズを調整すること、[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]を異なるカルチャにします。</span><span class="sxs-lookup"><span data-stu-id="6d14f-201">Localization means to adapt a [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] to different cultures.</span></span> <span data-ttu-id="6d14f-202">させる、[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]アプリケーションをローカライズ可能で、開発者がローカライズ可能なすべてのリソースをリソース アセンブリにビルドする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6d14f-202">To make a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application localizable, developers need to build all the localizable resources into a resource assembly.</span></span> <span data-ttu-id="6d14f-203">さまざまな言語にローカライズされたリソース アセンブリと分離コードは リソース管理を使用して[!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)]を読み込めません。</span><span class="sxs-lookup"><span data-stu-id="6d14f-203">The resource assembly is localized into different languages, and the code-behind uses resource management [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)] to load.</span></span> <span data-ttu-id="6d14f-204">必要なファイルのいずれかを[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]アプリケーションは、プロジェクト ファイル (.proj) です。</span><span class="sxs-lookup"><span data-stu-id="6d14f-204">One of the files required for a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application is a project file (.proj).</span></span> <span data-ttu-id="6d14f-205">アプリケーションで使用するすべてのリソースをプロジェクト ファイルに含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="6d14f-205">All resources that you use in your application should be included in the project file.</span></span> <span data-ttu-id="6d14f-206">その方法を .csproj ファイルからの次の例で示します。</span><span class="sxs-lookup"><span data-stu-id="6d14f-206">The following example from a .csproj file shows how to do this.</span></span>

```xml
<Resource Include="data\picture1.jpg"/>
<EmbeddedResource Include="data\stringtable.en-US.restext"/>
```

 <span data-ttu-id="6d14f-207">使用する、アプリケーションでリソースをインスタンス化、<xref:System.Resources.ResourceManager>を使用するリソースを読み込むとします。</span><span class="sxs-lookup"><span data-stu-id="6d14f-207">To use a resource in your application instantiate a <xref:System.Resources.ResourceManager> and load the resource you want to use.</span></span> <span data-ttu-id="6d14f-208">この方法を次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="6d14f-208">The following example demonstrates how to do this.</span></span>

 [!code-csharp[LocalizationResources#2](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationResources/CSharp/page1.xaml.cs#2)]

<a name="using_clickonce"></a>
## <a name="using-clickonce-with-localized-applications"></a><span data-ttu-id="6d14f-209">ローカライズされたアプリケーションで ClickOnce を使用する</span><span class="sxs-lookup"><span data-stu-id="6d14f-209">Using ClickOnce with Localized Applications</span></span>
 <span data-ttu-id="6d14f-210">ClickOnce は、Visual Studio 2005 に付属するは、新しい Windows フォーム展開テクノロジです。</span><span class="sxs-lookup"><span data-stu-id="6d14f-210">ClickOnce is a new Windows Forms deployment technology that will ship with Visual Studio 2005.</span></span> <span data-ttu-id="6d14f-211">アプリケーションをインストールしたり、Web アプリケーションをアップグレードしたりできます。</span><span class="sxs-lookup"><span data-stu-id="6d14f-211">It enables application installation and upgrading of Web applications.</span></span> <span data-ttu-id="6d14f-212">ClickOnce で展開されたアプリケーションがローカライズされると、ローカライズされたカルチャでのみ表示できます。</span><span class="sxs-lookup"><span data-stu-id="6d14f-212">When an application that was deployed with ClickOnce is localized it can only be viewed on the localized culture.</span></span> <span data-ttu-id="6d14f-213">たとえば、デプロイされたアプリケーションが日本語にローカライズされている場合にのみ表示できる日本語で[!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)]英語版の Windows ではなく。</span><span class="sxs-lookup"><span data-stu-id="6d14f-213">For example, if a deployed application is localized to Japanese it can only be viewed on Japanese [!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)] not on English Windows.</span></span> <span data-ttu-id="6d14f-214">これにより、英語版の Windows を実行する日本のユーザーの一般的なシナリオのため、問題を表示します。</span><span class="sxs-lookup"><span data-stu-id="6d14f-214">This presents a problem because it is a common scenario for Japanese users to run an English version of Windows.</span></span>

 <span data-ttu-id="6d14f-215">この問題の解決策は、非依存言語フォールバック属性を設定することです。</span><span class="sxs-lookup"><span data-stu-id="6d14f-215">The solution to this problem is setting the neutral language fallback attribute.</span></span> <span data-ttu-id="6d14f-216">アプリケーション開発者はメイン アセンブリからリソースを任意で削除し、特定のカルチャに対応するサテライト アセンブリでそのリソースを見つけられるように指定できます。</span><span class="sxs-lookup"><span data-stu-id="6d14f-216">An application developer can optionally remove resources from the main assembly and specify that the resources can be found in a satellite assembly corresponding to a specific culture.</span></span> <span data-ttu-id="6d14f-217">このプロセスの使用を制御する、<xref:System.Resources.NeutralResourcesLanguageAttribute>します。</span><span class="sxs-lookup"><span data-stu-id="6d14f-217">To control this process use the <xref:System.Resources.NeutralResourcesLanguageAttribute>.</span></span> <span data-ttu-id="6d14f-218">コンス トラクター、<xref:System.Resources.NeutralResourcesLanguageAttribute>クラスには 2 つの署名を受け取る 1 つ、<xref:System.Resources.UltimateResourceFallbackLocation>場所を指定するパラメーターを<xref:System.Resources.ResourceManager>フォールバック リソースを抽出する必要があります: メイン アセンブリまたはサテライト アセンブリ。</span><span class="sxs-lookup"><span data-stu-id="6d14f-218">The constructor of the <xref:System.Resources.NeutralResourcesLanguageAttribute> class has two signatures, one that takes an <xref:System.Resources.UltimateResourceFallbackLocation> parameter to specify the location where the <xref:System.Resources.ResourceManager> should extract the fallback resources: main assembly or satellite assembly.</span></span> <span data-ttu-id="6d14f-219">この属性を使用する方法の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="6d14f-219">The following example shows how to use the attribute.</span></span> <span data-ttu-id="6d14f-220">最終的なフォールバックの場所のコードと、<xref:System.Resources.ResourceManager>現在実行中のアセンブリのディレクトリのサブディレクトリ"de"でリソースを見つけます。</span><span class="sxs-lookup"><span data-stu-id="6d14f-220">For the ultimate fallback location, the code causes the <xref:System.Resources.ResourceManager> to look for the resources in the "de" subdirectory of the directory of the currently executing assembly.</span></span>

```
[assembly: NeutralResourcesLanguageAttribute(
    "de" , UltimateResourceFallbackLocation.Satellite)]
```

## <a name="see-also"></a><span data-ttu-id="6d14f-221">関連項目</span><span class="sxs-lookup"><span data-stu-id="6d14f-221">See also</span></span>
- [<span data-ttu-id="6d14f-222">WPF のグローバリゼーションおよびローカリゼーションの概要</span><span class="sxs-lookup"><span data-stu-id="6d14f-222">WPF Globalization and Localization Overview</span></span>](wpf-globalization-and-localization-overview.md)
