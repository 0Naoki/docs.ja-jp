---
title: OpenType フォントの機能
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- fonts [WPF], OpenType
- typography [WPF], OpenType font technology
- OpenType font technology [WPF]
ms.assetid: 4061a9d1-fe8b-4921-9e17-18ec7d2e3ea2
ms.openlocfilehash: f3d1dd9f7ef8122ac5573121e4f779fade776c8c
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "43659046"
---
# <a name="opentype-font-features"></a><span data-ttu-id="d5451-102">OpenType フォントの機能</span><span class="sxs-lookup"><span data-stu-id="d5451-102">OpenType Font Features</span></span>
<span data-ttu-id="d5451-103">このトピックでは、[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] における [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] フォント技術の主要機能の概要を説明します。</span><span class="sxs-lookup"><span data-stu-id="d5451-103">This topic provides an overview of some of the key features of [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] font technology in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].</span></span>  
  

  
<a name="overview"></a>   
## <a name="opentype-font-format"></a><span data-ttu-id="d5451-104">OpenType フォントの書式</span><span class="sxs-lookup"><span data-stu-id="d5451-104">OpenType Font Format</span></span>  
 <span data-ttu-id="d5451-105">[!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] フォント書式は [!INCLUDE[TLA#tla_truetype](../../../../includes/tlasharptla-truetype-md.md)] フォント書式の拡張で、PostScript フォント データのサポートが追加されています。</span><span class="sxs-lookup"><span data-stu-id="d5451-105">The [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] font format is an extension of the [!INCLUDE[TLA#tla_truetype](../../../../includes/tlasharptla-truetype-md.md)] font format, adding support for PostScript font data.</span></span> <span data-ttu-id="d5451-106">[!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] フォント書式は、[!INCLUDE[TLA#tla_ms](../../../../includes/tlasharptla-ms-md.md)] および Adobe Corporation により共同開発されました。</span><span class="sxs-lookup"><span data-stu-id="d5451-106">The [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] font format was developed jointly by [!INCLUDE[TLA#tla_ms](../../../../includes/tlasharptla-ms-md.md)] and Adobe Corporation.</span></span> [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)]<span data-ttu-id="d5451-107"> フォントおよび [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] フォントをサポートするオペレーティング システム サービスでは、フォントに [!INCLUDE[TLA2#tla_truetype](../../../../includes/tla2sharptla-truetype-md.md)] アウトラインまたは CFF (PostScript) アウトラインのどちらが含まれていても、ユーザーは簡単な方法でフォントのインストールと使用ができます。</span><span class="sxs-lookup"><span data-stu-id="d5451-107"> fonts and the operating system services which support [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] fonts provide users with a simple way to install and use fonts, whether the fonts contain [!INCLUDE[TLA2#tla_truetype](../../../../includes/tla2sharptla-truetype-md.md)] outlines or CFF (PostScript) outlines.</span></span>  
  
 <span data-ttu-id="d5451-108">[!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] フォント書式では、次のような開発者の課題に対処します。</span><span class="sxs-lookup"><span data-stu-id="d5451-108">The [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] font format addresses the following developer challenges:</span></span>  
  
-   <span data-ttu-id="d5451-109">より広範なマルチプラットフォームのサポート。</span><span class="sxs-lookup"><span data-stu-id="d5451-109">Broader multi-platform support.</span></span>  
  
-   <span data-ttu-id="d5451-110">国際文字セットのサポート強化。</span><span class="sxs-lookup"><span data-stu-id="d5451-110">Better support for international character sets.</span></span>  
  
-   <span data-ttu-id="d5451-111">フォント データの保護強化。</span><span class="sxs-lookup"><span data-stu-id="d5451-111">Better protection for font data.</span></span>  
  
-   <span data-ttu-id="d5451-112">ファイルのサイズを小さくして、より効率的にフォントを配布。</span><span class="sxs-lookup"><span data-stu-id="d5451-112">Smaller file sizes to make font distribution more efficient.</span></span>  
  
-   <span data-ttu-id="d5451-113">高度なテキスト編集コントロールの幅広いサポート。</span><span class="sxs-lookup"><span data-stu-id="d5451-113">Broader support for advanced typographic control.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d5451-114">Windows SDK には、[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] アプリケーションで使用できるサンプルの [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] フォント セットが含まれています。</span><span class="sxs-lookup"><span data-stu-id="d5451-114">The Windows SDK contains a set of sample [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] fonts that you can use with [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] applications.</span></span> <span data-ttu-id="d5451-115">これらのフォントでは、このトピックで説明していく機能の大半が提供されています。</span><span class="sxs-lookup"><span data-stu-id="d5451-115">These fonts provide most of the features illustrated in the rest of this topic.</span></span> <span data-ttu-id="d5451-116">詳細については、「[OpenType フォント パックのサンプル](../../../../docs/framework/wpf/advanced/sample-opentype-font-pack.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d5451-116">For more information, see [Sample OpenType Font Pack](../../../../docs/framework/wpf/advanced/sample-opentype-font-pack.md).</span></span>  
  
 <span data-ttu-id="d5451-117">[!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] フォント書式の詳細については、[OpenType の仕様](https://go.microsoft.com/fwlink/?LinkId=96731)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d5451-117">See the [OpenType Specification](https://go.microsoft.com/fwlink/?LinkId=96731) for details of the [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] font format.</span></span>  
  
### <a name="advanced-typographic-extensions"></a><span data-ttu-id="d5451-118">高度なテキスト編集の拡張機能</span><span class="sxs-lookup"><span data-stu-id="d5451-118">Advanced Typographic Extensions</span></span>  
 <span data-ttu-id="d5451-119">高度なテキスト編集のテーブル ([!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] レイアウト テーブル) では、[!INCLUDE[TLA2#tla_truetype](../../../../includes/tla2sharptla-truetype-md.md)] または CFF アウトラインを使用してフォントの機能を拡張しています。</span><span class="sxs-lookup"><span data-stu-id="d5451-119">The Advanced Typographic tables ([!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] Layout tables) extend the functionality of fonts with either [!INCLUDE[TLA2#tla_truetype](../../../../includes/tla2sharptla-truetype-md.md)] or CFF outlines.</span></span> [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)]<span data-ttu-id="d5451-120"> レイアウトのフォントには、フォントの機能を拡張する追加の情報が含まれ、高品質の国際タイポグラフィをサポートします。</span><span class="sxs-lookup"><span data-stu-id="d5451-120"> Layout fonts contain additional information that extends the capabilities of the fonts to support high-quality international typography.</span></span> <span data-ttu-id="d5451-121">ほとんどの [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] フォントは、利用可能な [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] 機能全体のサブセットのみを公開するものです。</span><span class="sxs-lookup"><span data-stu-id="d5451-121">Most [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] fonts expose only a subset of the total [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] features available.</span></span> [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)]<span data-ttu-id="d5451-122"> フォントには次のような特徴があります。</span><span class="sxs-lookup"><span data-stu-id="d5451-122"> fonts provide the following features.</span></span>  
  
-   <span data-ttu-id="d5451-123">合字、位置フォーム、代替、およびその他のフォント置換をサポートする、文字とグリフの間の充実したマッピング。</span><span class="sxs-lookup"><span data-stu-id="d5451-123">Rich mapping between characters and glyphs that support ligatures, positional forms, alternates, and other font substitutions.</span></span>  
  
-   <span data-ttu-id="d5451-124">2 次元配置とグリフ結合のサポート。</span><span class="sxs-lookup"><span data-stu-id="d5451-124">Support for two-dimensional positioning and glyph attachment.</span></span>  
  
-   <span data-ttu-id="d5451-125">フォントには明示的なスクリプトと言語情報が含まれるため、テキスト処理アプリケーションはそれに従って動作を調整可能。</span><span class="sxs-lookup"><span data-stu-id="d5451-125">Explicit script and language information contained in font, so a text-processing application can adjust its behavior accordingly.</span></span>  
  
 <span data-ttu-id="d5451-126">[!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] レイアウト テーブルについては、[!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] の仕様の[「フォント ファイル テーブル」](https://www.microsoft.com/typography/otspec/otff.htm)セクションで詳しく説明されています。</span><span class="sxs-lookup"><span data-stu-id="d5451-126">The [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] Layout tables are described in more detail in the ["Font File Tables"](https://www.microsoft.com/typography/otspec/otff.htm) section of the [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] specification.</span></span>  
  
 <span data-ttu-id="d5451-127">この概要の残りの部分では、幅と、視覚的に、興味のいくつかの柔軟性が導入されています[!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)]のプロパティによって公開される機能、<xref:System.Windows.Documents.Typography>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="d5451-127">The remainder of this overview introduces the breadth and flexibility of some of the visually-interesting [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] features that are exposed by the properties of the <xref:System.Windows.Documents.Typography> object.</span></span> <span data-ttu-id="d5451-128">このオブジェクトの詳細については、「[タイポグラフィ クラス](#typography_class)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d5451-128">For more information on this object, see [Typography Class](#typography_class).</span></span>  
  
<a name="variants"></a>   
## <a name="variants"></a><span data-ttu-id="d5451-129">バリアント</span><span class="sxs-lookup"><span data-stu-id="d5451-129">Variants</span></span>  
 <span data-ttu-id="d5451-130">バリアントを使用して、上付き文字と下付きなどのさまざまなタイポグラフィ スタイルを表示します。</span><span class="sxs-lookup"><span data-stu-id="d5451-130">Variants are used to render different typographic styles, such as superscripts and subscripts.</span></span>  
  
### <a name="superscripts-and-subscripts"></a><span data-ttu-id="d5451-131">上付き/下付きの文字</span><span class="sxs-lookup"><span data-stu-id="d5451-131">Superscripts and Subscripts</span></span>  
 <span data-ttu-id="d5451-132"><xref:System.Windows.Documents.Typography.Variants%2A>プロパティでは、上付き文字と下付き文字の値を設定することができます、[!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)]フォント。</span><span class="sxs-lookup"><span data-stu-id="d5451-132">The <xref:System.Windows.Documents.Typography.Variants%2A> property allows you to set superscript and subscript values for an [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] font.</span></span>  
  
 <span data-ttu-id="d5451-133">次のテキストは、Palatino Linotype フォントの上付き文字を示したものです。</span><span class="sxs-lookup"><span data-stu-id="d5451-133">The following text displays superscripts for the Palatino Linotype font.</span></span>  
  
 <span data-ttu-id="d5451-134">![OpenType の上付き文字を使用してテキストを](../../../../docs/framework/wpf/advanced/media/opentypefont14.gif "opentypefont14")</span><span class="sxs-lookup"><span data-stu-id="d5451-134">![Text using OpenType superscripts](../../../../docs/framework/wpf/advanced/media/opentypefont14.gif "opentypefont14")</span></span>  
<span data-ttu-id="d5451-135">OpenType の上付き文字を使用するテキスト</span><span class="sxs-lookup"><span data-stu-id="d5451-135">Text using OpenType superscripts</span></span>  
  
 <span data-ttu-id="d5451-136">次のマークアップ例のプロパティを使用して Palatino Linotype フォントの上付き文字を定義する方法を示しています、<xref:System.Windows.Documents.Typography>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="d5451-136">The following markup example shows how to define superscripts for the Palatino Linotype font, using properties of the <xref:System.Windows.Documents.Typography> object.</span></span>  
  
 [!code-xaml[OpenTypeFontSamples#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#12)]  
  
 <span data-ttu-id="d5451-137">次のテキストでは、Palatino Linotype フォントの下付き文字を表示します。</span><span class="sxs-lookup"><span data-stu-id="d5451-137">The following text displays subscripts for the Palatino Linotype font.</span></span>  
  
 <span data-ttu-id="d5451-138">![OpenType の下付き文字を使用してテキストを](../../../../docs/framework/wpf/advanced/media/opentypefont15.gif "opentypefont15")</span><span class="sxs-lookup"><span data-stu-id="d5451-138">![Text using OpenType subscripts](../../../../docs/framework/wpf/advanced/media/opentypefont15.gif "opentypefont15")</span></span>  
<span data-ttu-id="d5451-139">OpenType の下付き文字を使用するテキスト</span><span class="sxs-lookup"><span data-stu-id="d5451-139">Text using OpenType subscripts</span></span>  
  
 <span data-ttu-id="d5451-140">次のマークアップ例のプロパティを使用して Palatino Linotype フォントの下付き文字を定義する方法を示しています、<xref:System.Windows.Documents.Typography>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="d5451-140">The following markup example shows how to define subscripts for the Palatino Linotype font, using properties of the <xref:System.Windows.Documents.Typography> object.</span></span>  
  
 [!code-xaml[OpenTypeFontSamples#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#13)]  
  
### <a name="decorative-uses-of-superscripts-and-subscripts"></a><span data-ttu-id="d5451-141">上付き文字と下付き文字の装飾的な用途</span><span class="sxs-lookup"><span data-stu-id="d5451-141">Decorative Uses of Superscripts and Subscripts</span></span>  
 <span data-ttu-id="d5451-142">上付き文字と下付き文字を使用して、大文字と小文字が混在したテキストに装飾的効果をつけることもできます。</span><span class="sxs-lookup"><span data-stu-id="d5451-142">You can also use superscripts and subscripts to create decorative effects of mixed case text.</span></span> <span data-ttu-id="d5451-143">次のテキストは、Palatino Linotype フォントの上付き文字と下付き文字を示したものです。</span><span class="sxs-lookup"><span data-stu-id="d5451-143">The following text displays superscript and subscript text for the Palatino Linotype font.</span></span> <span data-ttu-id="d5451-144">大文字には影響がないことに注目してください。</span><span class="sxs-lookup"><span data-stu-id="d5451-144">Note that the capitals are not affected.</span></span>  
  
 <span data-ttu-id="d5451-145">![OpenType の上付き文字と下付き文字を使用してテキストを](../../../../docs/framework/wpf/advanced/media/opentypefont16.gif "opentypefont16")</span><span class="sxs-lookup"><span data-stu-id="d5451-145">![Text using OpenType superscripts and subscripts](../../../../docs/framework/wpf/advanced/media/opentypefont16.gif "opentypefont16")</span></span>  
<span data-ttu-id="d5451-146">OpenType の上付き文字と下付き文字を使用するテキスト</span><span class="sxs-lookup"><span data-stu-id="d5451-146">Text using OpenType superscripts and subscripts</span></span>  
  
 <span data-ttu-id="d5451-147">次のマークアップ例上付き文字とのプロパティを使用して、フォントの下付き文字を定義する方法を示しています、<xref:System.Windows.Documents.Typography>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="d5451-147">The following markup example shows how to define superscripts and subscripts for a font, using properties of the <xref:System.Windows.Documents.Typography> object.</span></span>  
  
 [!code-xaml[OpenTypeFontSamples#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#14)]  
  
<a name="capitals"></a>   
## <a name="capitals"></a><span data-ttu-id="d5451-148">大文字</span><span class="sxs-lookup"><span data-stu-id="d5451-148">Capitals</span></span>  
 <span data-ttu-id="d5451-149">大文字は、大文字スタイルのグリフでテキストをレンダリングするタイポグラフィ形式のセットです。</span><span class="sxs-lookup"><span data-stu-id="d5451-149">Capitals are a set of typographical forms that render text in capital-styled glyphs.</span></span> <span data-ttu-id="d5451-150">通常、テキストをすべて大文字で表示すると、文字間隔が狭すぎるように見え、文字の印象と縦横比が重すぎるように感じられます。</span><span class="sxs-lookup"><span data-stu-id="d5451-150">Typically, when text is rendered as all capitals, the spacing between letters can appear too tight, and the weight and proportion of the letters too heavy.</span></span> [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)]<span data-ttu-id="d5451-151"> では、小型英大文字、超小型英大文字、タイトル用、大文字スペーシングを含め、大文字に関する多くのスタイル形式をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="d5451-151"> supports a number of styling formats for capitals, including small capitals, petite capitals, titling, and capital spacing.</span></span> <span data-ttu-id="d5451-152">これらのスタイル形式を使用して、英大文字の外観を変えることができます。</span><span class="sxs-lookup"><span data-stu-id="d5451-152">These styling formats allow you to control the appearance of capitals.</span></span>  
  
 <span data-ttu-id="d5451-153">次のテキストは、Pescadero フォントの標準の大文字と、その後に "SmallCaps" および "AllSmallCaps" のスタイルをあてた文字を示したものです。</span><span class="sxs-lookup"><span data-stu-id="d5451-153">The following text displays standard capital letters for the Pescadero font, followed by the letters styled as "SmallCaps" and "AllSmallCaps".</span></span> <span data-ttu-id="d5451-154">この場合、同じフォント サイズは 3 つすべての単語の使用します。</span><span class="sxs-lookup"><span data-stu-id="d5451-154">In this case, the same font size is used for all three words.</span></span>  
  
 <span data-ttu-id="d5451-155">![OpenType の大文字を使用してテキストを](../../../../docs/framework/wpf/advanced/media/opentypefont11.gif "opentypefont11")</span><span class="sxs-lookup"><span data-stu-id="d5451-155">![Text using OpenType capitals](../../../../docs/framework/wpf/advanced/media/opentypefont11.gif "opentypefont11")</span></span>  
<span data-ttu-id="d5451-156">OpenType の大文字を使用するテキスト</span><span class="sxs-lookup"><span data-stu-id="d5451-156">Text using OpenType capitals</span></span>  
  
 <span data-ttu-id="d5451-157">次のマークアップ例のプロパティを使用して Pescadero フォントの大文字を定義する方法を示しています、<xref:System.Windows.Documents.Typography>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="d5451-157">The following markup example shows how to define capitals for the Pescadero font, using properties of the <xref:System.Windows.Documents.Typography> object.</span></span> <span data-ttu-id="d5451-158">"SmallCaps" 形式を使用する場合は、先頭の大文字は無視されます。</span><span class="sxs-lookup"><span data-stu-id="d5451-158">When the "SmallCaps" format is used, any leading capital letter is ignored.</span></span>  
  
 [!code-xaml[OpenTypeFontSamples#9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#9)]  
  
### <a name="titling-capitals"></a><span data-ttu-id="d5451-159">タイトル用大文字</span><span class="sxs-lookup"><span data-stu-id="d5451-159">Titling Capitals</span></span>  
 <span data-ttu-id="d5451-160">タイトル用大文字は、重みと縦横比が軽く、標準の大文字よりも洗練された印象を与えるように設計されています。</span><span class="sxs-lookup"><span data-stu-id="d5451-160">Titling capitals are lighter in weight and proportion and designed to give a more elegant look than normal capitals.</span></span> <span data-ttu-id="d5451-161">タイトル用大文字は、見出しとして大きなフォント サイズで通常使用されます。</span><span class="sxs-lookup"><span data-stu-id="d5451-161">Titling capitals are typically used in larger font sizes as headings.</span></span> <span data-ttu-id="d5451-162">次のテキストには、Pescadero フォントの標準的なタイトル用大文字が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d5451-162">The following text displays normal and titling capitals for the Pescadero font.</span></span> <span data-ttu-id="d5451-163">2 番目の行のテキストの幅の狭い縦線の幅に注意してください。</span><span class="sxs-lookup"><span data-stu-id="d5451-163">Notice the narrower stem widths of the text on the second line.</span></span>  
  
 <span data-ttu-id="d5451-164">![OpenType のタイトル大文字を使用してテキストを](../../../../docs/framework/wpf/advanced/media/opentypefont20.gif "OpenTypeFont20")</span><span class="sxs-lookup"><span data-stu-id="d5451-164">![Text using OpenType titling capitals](../../../../docs/framework/wpf/advanced/media/opentypefont20.gif "OpenTypeFont20")</span></span>  
<span data-ttu-id="d5451-165">OpenType のタイトル大文字を使用するテキスト</span><span class="sxs-lookup"><span data-stu-id="d5451-165">Text using OpenType titling capitals</span></span>  
  
 <span data-ttu-id="d5451-166">次のマークアップ例のプロパティを使用して Pescadero フォントのタイトル用大文字を定義する方法を示しています、<xref:System.Windows.Documents.Typography>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="d5451-166">The following markup example shows how to define titling capitals for the Pescadero font, using properties of the <xref:System.Windows.Documents.Typography> object.</span></span>  
  
 [!code-xaml[OpenTypeFontSamples#OpenTypeFontSnippet17](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#opentypefontsnippet17)]  
  
### <a name="capital-spacing"></a><span data-ttu-id="d5451-167">大文字スペーシング</span><span class="sxs-lookup"><span data-stu-id="d5451-167">Capital Spacing</span></span>  
 <span data-ttu-id="d5451-168">大文字スペーシングは、テキストをすべて大文字にする場合に間隔を広くする機能です。</span><span class="sxs-lookup"><span data-stu-id="d5451-168">Capital spacing is a feature that allows you to provide more spacing when using all capitals in text.</span></span> <span data-ttu-id="d5451-169">通常、英大文字は小文字と調和させる設計されます。</span><span class="sxs-lookup"><span data-stu-id="d5451-169">Capital letters are typically designed to blend with lowercase letters.</span></span> <span data-ttu-id="d5451-170">間で魅力的な間隔を表示し、大文字と小文字をあまりにも堅く見えますすべて大文字を使用する場合。</span><span class="sxs-lookup"><span data-stu-id="d5451-170">Spacing that appears attractive between and a capital letter and a lowercase letter may look too tight when all capital letters are used.</span></span> <span data-ttu-id="d5451-171">次のテキストは、Pescadero フォントの標準的な大文字の間隔を表示します。</span><span class="sxs-lookup"><span data-stu-id="d5451-171">The following text displays normal and capital spacing for the Pescadero font.</span></span>  
  
 <span data-ttu-id="d5451-172">![OpenType の大文字スペーシングを使用してテキストを](../../../../docs/framework/wpf/advanced/media/opentypefont21.gif "OpenTypeFont21")</span><span class="sxs-lookup"><span data-stu-id="d5451-172">![Text using OpenType capital spacing](../../../../docs/framework/wpf/advanced/media/opentypefont21.gif "OpenTypeFont21")</span></span>  
<span data-ttu-id="d5451-173">OpenType の大文字スペーシングを使用するテキスト</span><span class="sxs-lookup"><span data-stu-id="d5451-173">Text using OpenType capital spacing</span></span>  
  
 <span data-ttu-id="d5451-174">次のマークアップ例のプロパティを使用して Pescadero フォントの大文字スペーシングを定義する方法を示しています、<xref:System.Windows.Documents.Typography>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="d5451-174">The following markup example shows how to define capital spacing for the Pescadero font, using properties of the <xref:System.Windows.Documents.Typography> object.</span></span>  
  
 [!code-xaml[OpenTypeFontSamples#OpenTypeFontSnippet18](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#opentypefontsnippet18)]  
  
<a name="ligatures"></a>   
## <a name="ligatures"></a><span data-ttu-id="d5451-175">合字</span><span class="sxs-lookup"><span data-stu-id="d5451-175">Ligatures</span></span>  
 <span data-ttu-id="d5451-176">合字とは、2 つ以上のグリフを、より読みやすい、あるいはより魅力的なテキストにするために、1 つのグリフに形成したものです。</span><span class="sxs-lookup"><span data-stu-id="d5451-176">Ligatures are two or more glyphs that are formed into a single glyph in order to create more readable or attractive text.</span></span> [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)]<span data-ttu-id="d5451-177"> フォントは、4 種類の合字をサポートします。</span><span class="sxs-lookup"><span data-stu-id="d5451-177"> fonts support four types of ligatures:</span></span>  
  
-   <span data-ttu-id="d5451-178">**標準合字**。</span><span class="sxs-lookup"><span data-stu-id="d5451-178">**Standard ligatures**.</span></span> <span data-ttu-id="d5451-179">読みやすさを高めるように設計されています。</span><span class="sxs-lookup"><span data-stu-id="d5451-179">Designed to enhance readability.</span></span> <span data-ttu-id="d5451-180">標準合字には、"fi"、"fl" および "ff" があります。</span><span class="sxs-lookup"><span data-stu-id="d5451-180">Standard ligatures include "fi", "fl", and "ff".</span></span>  
  
-   <span data-ttu-id="d5451-181">**コンテキスト合字**。</span><span class="sxs-lookup"><span data-stu-id="d5451-181">**Contextual ligatures**.</span></span> <span data-ttu-id="d5451-182">合字を構成する文字の間の結合を向上させることによって、読みやすさを高めるよう設計されています。</span><span class="sxs-lookup"><span data-stu-id="d5451-182">Designed to enhance readability by providing better joining behavior between the characters that make up the ligature.</span></span>  
  
-   <span data-ttu-id="d5451-183">**随意合字**。</span><span class="sxs-lookup"><span data-stu-id="d5451-183">**Discretionary ligatures**.</span></span> <span data-ttu-id="d5451-184">装飾を加える設計で、特に読みやすくなるようには設計されていません。</span><span class="sxs-lookup"><span data-stu-id="d5451-184">Designed to be ornamental, and not specifically designed for readability.</span></span>  
  
-   <span data-ttu-id="d5451-185">**歴史的合字**。</span><span class="sxs-lookup"><span data-stu-id="d5451-185">**Historical ligatures**.</span></span> <span data-ttu-id="d5451-186">歴史的な記述に相応しい設計で、特に読みやすくなるようには設計されていません。</span><span class="sxs-lookup"><span data-stu-id="d5451-186">Designed to be historical, and not specifically designed for readability.</span></span>  
  
 <span data-ttu-id="d5451-187">次のテキストは、Pericles フォントの標準合字グリフを示したものです。</span><span class="sxs-lookup"><span data-stu-id="d5451-187">The following text displays standard ligature glyphs for the Pericles font.</span></span>  
  
 <span data-ttu-id="d5451-188">![OpenType の標準合字を使用してテキストを](../../../../docs/framework/wpf/advanced/media/opentypefont04.gif "opentypefont04")</span><span class="sxs-lookup"><span data-stu-id="d5451-188">![Text using OpenType standard ligatures](../../../../docs/framework/wpf/advanced/media/opentypefont04.gif "opentypefont04")</span></span>  
<span data-ttu-id="d5451-189">OpenType の標準合字を使用するテキスト</span><span class="sxs-lookup"><span data-stu-id="d5451-189">Text using OpenType standard ligatures</span></span>  
  
 <span data-ttu-id="d5451-190">次のマークアップ例のプロパティを使用して Pericles フォントの標準合字グリフを定義する方法を示しています、<xref:System.Windows.Documents.Typography>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="d5451-190">The following markup example shows how to define standard ligature glyphs for the Pericles font, using properties of the <xref:System.Windows.Documents.Typography> object.</span></span>  
  
 [!code-xaml[OpenTypeFontSamples#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#4)]  
  
 <span data-ttu-id="d5451-191">次のテキストは、Pericles フォントの随意合字グリフを示したものです。</span><span class="sxs-lookup"><span data-stu-id="d5451-191">The following text displays discretionary ligature glyphs for the Pericles font.</span></span>  
  
 <span data-ttu-id="d5451-192">![OpenType の随意合字を使用してテキストを](../../../../docs/framework/wpf/advanced/media/opentypefont05.gif "opentypefont05")</span><span class="sxs-lookup"><span data-stu-id="d5451-192">![Text using OpenType discretionary ligatures](../../../../docs/framework/wpf/advanced/media/opentypefont05.gif "opentypefont05")</span></span>  
<span data-ttu-id="d5451-193">OpenType の随意合字を使用するテキスト</span><span class="sxs-lookup"><span data-stu-id="d5451-193">Text using OpenType discretionary ligatures</span></span>  
  
 <span data-ttu-id="d5451-194">次のマークアップ例のプロパティを使用して Pericles フォントの随意合字グリフを定義する方法を示しています、<xref:System.Windows.Documents.Typography>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="d5451-194">The following markup example shows how to define discretionary ligature glyphs for the Pericles font, using properties of the <xref:System.Windows.Documents.Typography> object.</span></span>  
  
 [!code-xaml[OpenTypeFontSamples#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#5)]  
  
 <span data-ttu-id="d5451-195">既定では、[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] の [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] フォントでは標準合字が有効です。</span><span class="sxs-lookup"><span data-stu-id="d5451-195">By default, [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] fonts in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] enable standard ligatures.</span></span> <span data-ttu-id="d5451-196">たとえば、Palatino Linotype フォントを使用する場合、標準合字 "fi"、"ff" および "fl" は組み合わせ文字グリフとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="d5451-196">For example, if you use the Palatino Linotype font, the standard ligatures "fi", "ff", and "fl" appear as a combined character glyph.</span></span> <span data-ttu-id="d5451-197">各標準合字の文字のペアが互いに接触することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="d5451-197">Notice that the pair of characters for each standard ligature touch each other.</span></span>  
  
 <span data-ttu-id="d5451-198">![OpenType の標準合字を使用してテキストを](../../../../docs/framework/wpf/advanced/media/opentypefont06.gif "opentypefont06")</span><span class="sxs-lookup"><span data-stu-id="d5451-198">![Text using OpenType standard ligatures](../../../../docs/framework/wpf/advanced/media/opentypefont06.gif "opentypefont06")</span></span>  
<span data-ttu-id="d5451-199">OpenType の標準合字を使用するテキスト</span><span class="sxs-lookup"><span data-stu-id="d5451-199">Text using OpenType standard ligatures</span></span>  
  
 <span data-ttu-id="d5451-200">ただし、標準合字機能を無効にして、"ff" などの標準合字が、組み合わせ文字グリフとしてではなく、2 つの別々のグリフとして表示されるようにできます。</span><span class="sxs-lookup"><span data-stu-id="d5451-200">However, you can disable standard ligature features so that a standard ligature such as "ff" displays as two separate glyphs, rather than as a combined character glyph.</span></span>  
  
 <span data-ttu-id="d5451-201">![OpenType の標準合字を無効になっているテキストを使用して](../../../../docs/framework/wpf/advanced/media/opentypefont07.gif "opentypefont07")</span><span class="sxs-lookup"><span data-stu-id="d5451-201">![Text using disabled OpenType standard ligatures](../../../../docs/framework/wpf/advanced/media/opentypefont07.gif "opentypefont07")</span></span>  
<span data-ttu-id="d5451-202">OpenType の無効な標準合字を使用するテキスト</span><span class="sxs-lookup"><span data-stu-id="d5451-202">Text using disabled OpenType standard ligatures</span></span>  
  
 <span data-ttu-id="d5451-203">次のマークアップ例のプロパティを使用して Palatino Linotype フォントの標準合字グリフを無効にする方法を示しています、<xref:System.Windows.Documents.Typography>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="d5451-203">The following markup example shows how to disable standard ligature glyphs for the Palatino Linotype font, using properties of the <xref:System.Windows.Documents.Typography> object.</span></span>  
  
 [!code-xaml[OpenTypeFontSamples#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#6)]  
  
<a name="swashes"></a>   
## <a name="swashes"></a><span data-ttu-id="d5451-204">飾り付き</span><span class="sxs-lookup"><span data-stu-id="d5451-204">Swashes</span></span>  
 <span data-ttu-id="d5451-205">飾り付きは装飾的なグリフで、カリグラフィを連想させる、手の込んだ装飾が使用されます。</span><span class="sxs-lookup"><span data-stu-id="d5451-205">Swashes are decorative glyphs that use elaborate ornamentation often associated with calligraphy.</span></span> <span data-ttu-id="d5451-206">次のテキストには、Pescadero フォントの標準と飾り付きグリフが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d5451-206">The following text displays standard and swash glyphs for the Pescadero font.</span></span>  
  
 <span data-ttu-id="d5451-207">![OpenType の標準と飾り付きグリフを使用してテキストを](../../../../docs/framework/wpf/advanced/media/opentypefont08.gif "opentypefont08")</span><span class="sxs-lookup"><span data-stu-id="d5451-207">![Text using OpenType standard and swash glyphs](../../../../docs/framework/wpf/advanced/media/opentypefont08.gif "opentypefont08")</span></span>  
<span data-ttu-id="d5451-208">OpenType の標準グリフと飾り付きグリフを使用するテキスト</span><span class="sxs-lookup"><span data-stu-id="d5451-208">Text using OpenType standard and swash glyphs</span></span>  
  
 <span data-ttu-id="d5451-209">飾り付きは、季節のご挨拶などの短いフレーズで装飾的な要素としてよく使用されます。</span><span class="sxs-lookup"><span data-stu-id="d5451-209">Swashes are often used as decorative elements in short phrases such as event announcements.</span></span> <span data-ttu-id="d5451-210">次のテキストは、イベントの名前の大文字を強調するために、飾り付きを使用します。</span><span class="sxs-lookup"><span data-stu-id="d5451-210">The following text uses swashes to emphasize the capital letters of the name of the event.</span></span>  
  
 <span data-ttu-id="d5451-211">![OpenType の巻き髭を使用してテキストを](../../../../docs/framework/wpf/advanced/media/opentypefont09.gif "opentypefont09")</span><span class="sxs-lookup"><span data-stu-id="d5451-211">![Text using OpenType swashes](../../../../docs/framework/wpf/advanced/media/opentypefont09.gif "opentypefont09")</span></span>  
<span data-ttu-id="d5451-212">OpenType の巻き髭を使用するテキスト</span><span class="sxs-lookup"><span data-stu-id="d5451-212">Text using OpenType swashes</span></span>  
  
 <span data-ttu-id="d5451-213">次のマークアップ例のプロパティを使用して、フォントの飾り付きを定義する方法を示しています、<xref:System.Windows.Documents.Typography>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="d5451-213">The following markup example shows how to define swashes for a font, using properties of the <xref:System.Windows.Documents.Typography> object.</span></span>  
  
 [!code-xaml[OpenTypeFontSamples#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#7)]  
  
### <a name="contextual-swashes"></a><span data-ttu-id="d5451-214">コンテキスト飾り付き</span><span class="sxs-lookup"><span data-stu-id="d5451-214">Contextual Swashes</span></span>  
 <span data-ttu-id="d5451-215">飾り付きグリフの特定の組み合わせでは、隣りあう文字の下に延びる部分が重なり合うなど、美しくない外観になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d5451-215">Certain combinations of swash glyphs can cause an unattractive appearance, such as overlapping descenders on adjacent letters.</span></span> <span data-ttu-id="d5451-216">コンテキスト飾り付きを使用してより優れた外観を生成する代替の飾り付きグリフを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="d5451-216">Using a contextual swash allows you to use a substitute swash glyph that produces a better appearance.</span></span> <span data-ttu-id="d5451-217">コンテキスト飾り付きを適用した後と前に、次のテキストは同じ単語を示します。</span><span class="sxs-lookup"><span data-stu-id="d5451-217">The following text shows the same word before and after a contextual swash is applied.</span></span>  
  
 <span data-ttu-id="d5451-218">![OpenType のコンテキスト巻き髭を使用してテキストを](../../../../docs/framework/wpf/advanced/media/opentypefont19.gif "OpenTypeFont19")</span><span class="sxs-lookup"><span data-stu-id="d5451-218">![Text using OpenType contextual swashes](../../../../docs/framework/wpf/advanced/media/opentypefont19.gif "OpenTypeFont19")</span></span>  
<span data-ttu-id="d5451-219">OpenType のコンテキスト巻き髭を使用するテキスト</span><span class="sxs-lookup"><span data-stu-id="d5451-219">Text using OpenType contextual swashes</span></span>  
  
 <span data-ttu-id="d5451-220">次のマークアップ例のプロパティを使用して Pescadero フォントのコンテキスト飾り付きを定義する方法を示しています、<xref:System.Windows.Documents.Typography>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="d5451-220">The following markup example shows how to define a contextual swash for the Pescadero font, using properties of the <xref:System.Windows.Documents.Typography> object.</span></span>  
  
 [!code-xaml[OpenTypeFontSamples#OpenTypeFontSnippet16](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#opentypefontsnippet16)]  
  
<a name="alternates"></a>   
## <a name="alternates"></a><span data-ttu-id="d5451-221">代替</span><span class="sxs-lookup"><span data-stu-id="d5451-221">Alternates</span></span>  
 <span data-ttu-id="d5451-222">代替文字は、標準的なグリフの代わりに使用できるグリフです。</span><span class="sxs-lookup"><span data-stu-id="d5451-222">Alternates are glyphs that can be substituted for a standard glyph.</span></span> <span data-ttu-id="d5451-223">次の例で使用される Pericles フォントなどの [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] フォントには、テキストの異なる外観を作るのに使用できる代替グリフを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="d5451-223">[!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] fonts, such as the Pericles font used in the following examples, can contain alternate glyphs that you can use to create different appearances for text.</span></span> <span data-ttu-id="d5451-224">次のテキストは、Pericles フォントの標準グリフを示したものです。</span><span class="sxs-lookup"><span data-stu-id="d5451-224">The following text displays standard glyphs for the Pericles font.</span></span>  
  
 <span data-ttu-id="d5451-225">![OpenType の標準グリフを使用してテキストを](../../../../docs/framework/wpf/advanced/media/opentypefont01.gif "opentypefont01")</span><span class="sxs-lookup"><span data-stu-id="d5451-225">![Text using OpenType standard glyphs](../../../../docs/framework/wpf/advanced/media/opentypefont01.gif "opentypefont01")</span></span>  
<span data-ttu-id="d5451-226">OpenType の標準グリフを使用するテキスト</span><span class="sxs-lookup"><span data-stu-id="d5451-226">Text using OpenType standard glyphs</span></span>  
  
 <span data-ttu-id="d5451-227">Pericles [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] フォントには、標準グリフ セットに代替スタイルを提供する追加グリフが含まれています。</span><span class="sxs-lookup"><span data-stu-id="d5451-227">The Pericles [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] font contains additional glyphs that provide stylistic alternates to the standard set of glyphs.</span></span> <span data-ttu-id="d5451-228">次のテキストでは、スタイル代替グリフが表示されています。</span><span class="sxs-lookup"><span data-stu-id="d5451-228">The following text displays stylistic alternate glyphs.</span></span>  
  
 <span data-ttu-id="d5451-229">![OpenType のスタイル代替グリフを使用してテキストを](../../../../docs/framework/wpf/advanced/media/opentypefont02.gif "opentypefont02")</span><span class="sxs-lookup"><span data-stu-id="d5451-229">![Text using OpenType stylistic alternate glyphs](../../../../docs/framework/wpf/advanced/media/opentypefont02.gif "opentypefont02")</span></span>  
<span data-ttu-id="d5451-230">OpenType のスタイル代替グリフを使用するテキスト</span><span class="sxs-lookup"><span data-stu-id="d5451-230">Text using OpenType stylistic alternate glyphs</span></span>  
  
 <span data-ttu-id="d5451-231">次のマークアップ例のプロパティを使用して Pericles フォントのスタイル代替グリフを定義する方法を示しています、<xref:System.Windows.Documents.Typography>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="d5451-231">The following markup example shows how to define stylistic alternate glyphs for the Pericles font, using properties of the <xref:System.Windows.Documents.Typography> object.</span></span>  
  
 [!code-xaml[OpenTypeFontSamples#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#2)]  
  
 <span data-ttu-id="d5451-232">次のテキストには、いくつかその他のスタイル代替グリフ Pericles フォントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d5451-232">The following text displays several other stylistic alternate glyphs for the Pericles font.</span></span>  
  
 <span data-ttu-id="d5451-233">![OpenType のスタイル代替グリフを使用してテキストを](../../../../docs/framework/wpf/advanced/media/opentypefont03.gif "opentypefont03")</span><span class="sxs-lookup"><span data-stu-id="d5451-233">![Text using OpenType stylistic alternate glyphs](../../../../docs/framework/wpf/advanced/media/opentypefont03.gif "opentypefont03")</span></span>  
<span data-ttu-id="d5451-234">OpenType のスタイル代替グリフを使用するテキスト</span><span class="sxs-lookup"><span data-stu-id="d5451-234">Text using OpenType stylistic alternate glyphs</span></span>  
  
 <span data-ttu-id="d5451-235">次のマークアップの例では、これらの他のスタイル代替グリフを定義する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="d5451-235">The following markup example shows how to define these other stylistic alternate glyphs.</span></span>  
  
 [!code-xaml[OpenTypeFontSamples#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#3)]  
  
### <a name="random-contextual-alternates"></a><span data-ttu-id="d5451-236">ランダムなコンテキスト代替</span><span class="sxs-lookup"><span data-stu-id="d5451-236">Random Contextual Alternates</span></span>  
 <span data-ttu-id="d5451-237">ランダムなコンテキスト代替は、単一文字に複数の代替グリフを提供します。</span><span class="sxs-lookup"><span data-stu-id="d5451-237">Random contextual alternates provide multiple substitute glyphs for a single character.</span></span> <span data-ttu-id="d5451-238">スクリプトの種類のフォントで実装された場合、この機能は、一連の外観に違いが多少ランダムに選択されたグリフを使用して手書き入力をシミュレートできます。</span><span class="sxs-lookup"><span data-stu-id="d5451-238">When implemented with script-type fonts, this feature can simulate handwriting by using of a set of randomly chosen glyphs with slight differences in appearance.</span></span> <span data-ttu-id="d5451-239">次のテキストは、Lindsey フォントのランダムなコンテキスト代替を使用します。</span><span class="sxs-lookup"><span data-stu-id="d5451-239">The following text uses random contextual alternates for the Lindsey font.</span></span> <span data-ttu-id="d5451-240">注意して、文字"a"は少し異なります外観</span><span class="sxs-lookup"><span data-stu-id="d5451-240">Notice that the letter "a" varies slightly in appearance</span></span>  
  
 <span data-ttu-id="d5451-241">![OpenType のランダムなコンテキスト代替を使用してテキストを](../../../../docs/framework/wpf/advanced/media/opentypefont23.gif "OpenTypeFont23")</span><span class="sxs-lookup"><span data-stu-id="d5451-241">![Text using OpenType random contextual alternates](../../../../docs/framework/wpf/advanced/media/opentypefont23.gif "OpenTypeFont23")</span></span>  
<span data-ttu-id="d5451-242">OpenType のランダムなコンテキスト代替を使用するテキスト</span><span class="sxs-lookup"><span data-stu-id="d5451-242">Text using OpenType random contextual alternates</span></span>  
  
 <span data-ttu-id="d5451-243">次のマークアップ例のプロパティを使用して Lindsey フォントのランダムなコンテキスト代替を定義する方法を示しています、<xref:System.Windows.Documents.Typography>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="d5451-243">The following markup example shows how to define random contextual alternates for the Lindsey font, using properties of the <xref:System.Windows.Documents.Typography> object.</span></span>  
  
 [!code-xaml[OpenTypeFontSamples#OpenTypeFontSnippet20](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/Window1.xaml#opentypefontsnippet20)]  
  
### <a name="historical-forms"></a><span data-ttu-id="d5451-244">歴史的形式</span><span class="sxs-lookup"><span data-stu-id="d5451-244">Historical Forms</span></span>  
 <span data-ttu-id="d5451-245">歴史的形式は、過去に一般的であった表示形式です。</span><span class="sxs-lookup"><span data-stu-id="d5451-245">Historical forms are typographic conventions that were common in the past.</span></span> <span data-ttu-id="d5451-246">次のテキストには、「ボストン, マサチューセッツ州」という語句が表示されます。 Palatino Linotype フォントのグリフの履歴フォームを使用します。</span><span class="sxs-lookup"><span data-stu-id="d5451-246">The following text displays the phrase, "Boston, Massachusetts", using an historical form of glyphs for the Palatino Linotype font.</span></span>  
  
 <span data-ttu-id="d5451-247">![OpenType の歴史的形式を使用してテキストを](../../../../docs/framework/wpf/advanced/media/opentypefont10.gif "opentypefont10")</span><span class="sxs-lookup"><span data-stu-id="d5451-247">![Text using OpenType historical forms](../../../../docs/framework/wpf/advanced/media/opentypefont10.gif "opentypefont10")</span></span>  
<span data-ttu-id="d5451-248">OpenType の履歴フォームを使用するテキスト</span><span class="sxs-lookup"><span data-stu-id="d5451-248">Text using OpenType historical forms</span></span>  
  
 <span data-ttu-id="d5451-249">次のマークアップ例のプロパティを使用して Palatino Linotype フォントの歴史的形式を定義する方法を示しています、<xref:System.Windows.Documents.Typography>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="d5451-249">The following markup example shows how to define historical forms for the Palatino Linotype font, using properties of the <xref:System.Windows.Documents.Typography> object.</span></span>  
  
 [!code-xaml[OpenTypeFontSamples#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#8)]  
  
<a name="numerical_styles"></a>   
## <a name="numerical-styles"></a><span data-ttu-id="d5451-250">数値スタイル</span><span class="sxs-lookup"><span data-stu-id="d5451-250">Numerical Styles</span></span>  
 <span data-ttu-id="d5451-251">OpenType フォントでは、テキスト内の数値に使用できる数多くの機能をサポートします。</span><span class="sxs-lookup"><span data-stu-id="d5451-251">OpenType fonts support a large number of features that can be used with numerical values in text.</span></span>  
  
### <a name="fractions"></a><span data-ttu-id="d5451-252">小数</span><span class="sxs-lookup"><span data-stu-id="d5451-252">Fractions</span></span>  
 [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)]<span data-ttu-id="d5451-253"> フォントは、スラッシュや横棒を使用した小数スタイルをサポートします。</span><span class="sxs-lookup"><span data-stu-id="d5451-253"> fonts support styles for fractions, including slashed and stacked.</span></span>  
  
 <span data-ttu-id="d5451-254">次のテキストは、Palatino Linotype フォントの小数スタイルを示したものです。</span><span class="sxs-lookup"><span data-stu-id="d5451-254">The following text displays fraction styles for the Palatino Linotype font.</span></span>  
  
 <span data-ttu-id="d5451-255">![スラッシュし、分数を OpenType を使用してテキスト](../../../../docs/framework/wpf/advanced/media/opentypefont12.gif "opentypefont12")</span><span class="sxs-lookup"><span data-stu-id="d5451-255">![Text using OpenType slashed and stacked fractions](../../../../docs/framework/wpf/advanced/media/opentypefont12.gif "opentypefont12")</span></span>  
<span data-ttu-id="d5451-256">OpenType の分数 (横) と分数 (縦) を使用するテキスト</span><span class="sxs-lookup"><span data-stu-id="d5451-256">Text using OpenType slashed and stacked fractions</span></span>  
  
 <span data-ttu-id="d5451-257">次のマークアップ例のプロパティを使用して Palatino Linotype フォントの小数スタイルを定義する方法を示しています、<xref:System.Windows.Documents.Typography>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="d5451-257">The following markup example shows how to define fraction styles for the Palatino Linotype font, using properties of the <xref:System.Windows.Documents.Typography> object.</span></span>  
  
 [!code-xaml[OpenTypeFontSamples#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#10)]  
  
### <a name="old-style-numerals"></a><span data-ttu-id="d5451-258">旧式スタイルの数字</span><span class="sxs-lookup"><span data-stu-id="d5451-258">Old Style Numerals</span></span>  
 [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)]<span data-ttu-id="d5451-259"> フォントは、旧式スタイルの数字形式をサポートします。</span><span class="sxs-lookup"><span data-stu-id="d5451-259"> fonts support an old style numeral format.</span></span> <span data-ttu-id="d5451-260">この形式は、もはや標準ではなくなったスタイルで数字を表示するのに便利です。</span><span class="sxs-lookup"><span data-stu-id="d5451-260">This format is useful for displaying numerals in styles that are no longer standard.</span></span> <span data-ttu-id="d5451-261">次のテキストは、Palatino Linotype フォントの標準と古いスタイルの数字形式で、18 世紀日付を表示します。</span><span class="sxs-lookup"><span data-stu-id="d5451-261">The following text displays an 18th century date in standard and old style numeral formats for the Palatino Linotype font.</span></span>  
  
 <span data-ttu-id="d5451-262">![OpenType の旧式スタイルの数字を使用してテキストを](../../../../docs/framework/wpf/advanced/media/opentypefont24.gif "OpenTypeFont24")</span><span class="sxs-lookup"><span data-stu-id="d5451-262">![Text using OpenType old style numerals](../../../../docs/framework/wpf/advanced/media/opentypefont24.gif "OpenTypeFont24")</span></span>  
<span data-ttu-id="d5451-263">OpenType の古いスタイルの数字を使用するテキスト</span><span class="sxs-lookup"><span data-stu-id="d5451-263">Text using OpenType old style numerals</span></span>  
  
 <span data-ttu-id="d5451-264">次のテキストは、Palatino Linotype フォントの標準の数字と、旧式スタイルの数字を示したものです。</span><span class="sxs-lookup"><span data-stu-id="d5451-264">The following text displays standard numerals for the Palatino Linotype font, followed by old style numerals.</span></span>  
  
 <span data-ttu-id="d5451-265">![OpenType 古いスタイルの数字セットを使用してテキストを](../../../../docs/framework/wpf/advanced/media/opentypefont13.gif "opentypefont13")</span><span class="sxs-lookup"><span data-stu-id="d5451-265">![Text using OpenType old style numeral sets](../../../../docs/framework/wpf/advanced/media/opentypefont13.gif "opentypefont13")</span></span>  
<span data-ttu-id="d5451-266">OpenType の古いスタイルの数字セットを使用するテキスト</span><span class="sxs-lookup"><span data-stu-id="d5451-266">Text using OpenType old style numeral sets</span></span>  
  
 <span data-ttu-id="d5451-267">次のマークアップ例のプロパティを使用して Palatino Linotype フォントの旧式スタイルの数字を定義する方法を示しています、<xref:System.Windows.Documents.Typography>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="d5451-267">The following markup example shows how to define old style numerals for the Palatino Linotype font, using properties of the <xref:System.Windows.Documents.Typography> object.</span></span>  
  
 [!code-xaml[OpenTypeFontSamples#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#11)]  
  
### <a name="proportional-and-tabular-figures"></a><span data-ttu-id="d5451-268">プロポーショナルと表形式の数字</span><span class="sxs-lookup"><span data-stu-id="d5451-268">Proportional and Tabular Figures</span></span>  
 [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)]<span data-ttu-id="d5451-269"> フォントはプロポーショナルと表形式の数字をサポートし、数字を扱うときに幅を調整します。</span><span class="sxs-lookup"><span data-stu-id="d5451-269"> fonts support a proportional and tabular figure feature to control the alignment of widths when using numerals.</span></span> <span data-ttu-id="d5451-270">プロポーショナルの数字では、それぞれの数字は異なる幅を持つものとして扱われます。たとえば "1" は "5" より狭い幅です。</span><span class="sxs-lookup"><span data-stu-id="d5451-270">Proportional figures treat each numeral as having a different width—"1" is narrower than "5".</span></span> <span data-ttu-id="d5451-271">表形式の図表は、財務型情報の読みやすさの向上に配置、垂直方向、等幅の数字として扱われます。</span><span class="sxs-lookup"><span data-stu-id="d5451-271">Tabular figures are treated as equal-width numerals so that they align vertically, which increases the readability of financial type information.</span></span>  
  
 <span data-ttu-id="d5451-272">次のテキストには、Miramonte フォントを使用して最初の列に 2 つのプロポーショナル数字が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d5451-272">The following text displays two proportional figures in the first column using the Miramonte font.</span></span> <span data-ttu-id="d5451-273">「5」と「1」数字の幅の違いに注意してください。</span><span class="sxs-lookup"><span data-stu-id="d5451-273">Note the difference in width between the numerals "5" and "1".</span></span> <span data-ttu-id="d5451-274">2 番目の列には、表形式の図の機能を使用して調整幅と同じ 2 つの数値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d5451-274">The second column shows the same two numeric values with the widths adjusted by using the tabular figure feature.</span></span>  
  
 <span data-ttu-id="d5451-275">![OpenType のプロポーショナルと表形式の数字を使用してテキストを](../../../../docs/framework/wpf/advanced/media/opentypefont22.gif "OpenTypeFont22")</span><span class="sxs-lookup"><span data-stu-id="d5451-275">![Text using OpenType proportional & tabular figures](../../../../docs/framework/wpf/advanced/media/opentypefont22.gif "OpenTypeFont22")</span></span>  
<span data-ttu-id="d5451-276">OpenType のプロポーショナルと表形式の数字を使用するテキスト</span><span class="sxs-lookup"><span data-stu-id="d5451-276">Text using OpenType proportional and tabular figures</span></span>  
  
 <span data-ttu-id="d5451-277">次のマークアップ例のプロパティを使用して Miramonte フォントのプロポーショナルと表形式の数字を定義する方法を示しています、<xref:System.Windows.Documents.Typography>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="d5451-277">The following markup example shows how to define proportional and tabular figures for the Miramonte font, using properties of the <xref:System.Windows.Documents.Typography> object.</span></span>  
  
 [!code-xaml[OpenTypeFontSamples#OpenTypeFontSnippet19](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/Window1.xaml#opentypefontsnippet19)]  
  
### <a name="slashed-zero"></a><span data-ttu-id="d5451-278">スラッシュ付きゼロ</span><span class="sxs-lookup"><span data-stu-id="d5451-278">Slashed Zero</span></span>  
 [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)]<span data-ttu-id="d5451-279"> フォントは、英文字 "O" と数字の "0" の違いを強調するためのスラッシュ付きゼロの数字形式をサポートします。</span><span class="sxs-lookup"><span data-stu-id="d5451-279"> fonts support a slashed zero numeral format to emphasize the difference between the letter "O" and the numeral "0".</span></span> <span data-ttu-id="d5451-280">スラッシュ付きゼロは、財務およびビジネス情報における ID によく使用されます。</span><span class="sxs-lookup"><span data-stu-id="d5451-280">The slashed zero numeral is often used for identifiers in financial and business information.</span></span>  
  
 <span data-ttu-id="d5451-281">次のテキストには、Miramonte フォントを使用して、サンプル注文識別子が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d5451-281">The following text displays a sample order identifier using the Miramonte font.</span></span> <span data-ttu-id="d5451-282">最初の行では、標準の数字を使用します。</span><span class="sxs-lookup"><span data-stu-id="d5451-282">The first line uses standard numerals.</span></span> <span data-ttu-id="d5451-283">使用する 2 番目の線はスラッシュ ゼロに大文字の"O"より優れたコントラストを提供します。</span><span class="sxs-lookup"><span data-stu-id="d5451-283">The second line used slashed zero numerals to provide better contrast with the uppercase "O" letter.</span></span>  
  
 <span data-ttu-id="d5451-284">![OpenType を使用してテキストをスラッシュ ゼロ](../../../../docs/framework/wpf/advanced/media/opentypefont17.gif "OpenTypeFont17")</span><span class="sxs-lookup"><span data-stu-id="d5451-284">![Text using OpenType slashed zero numerals](../../../../docs/framework/wpf/advanced/media/opentypefont17.gif "OpenTypeFont17")</span></span>  
<span data-ttu-id="d5451-285">OpenType のスラッシュ付きのゼロを使用するテキスト</span><span class="sxs-lookup"><span data-stu-id="d5451-285">Text using OpenType slashed zero numerals</span></span>  
  
 <span data-ttu-id="d5451-286">次のマークアップ例は、定義する方法を示しますのプロパティを使用して Miramonte フォントのスラッシュ ゼロ、<xref:System.Windows.Documents.Typography>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="d5451-286">The following markup example shows how to define slashed zero numerals for the Miramonte font, using properties of the <xref:System.Windows.Documents.Typography> object.</span></span>  
  
 [!code-xaml[OpenTypeFontSamples#OpenTypeFontSnippet15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#opentypefontsnippet15)]  
  
<a name="typography_class"></a>   
## <a name="typography-class"></a><span data-ttu-id="d5451-287">タイポグラフィ クラス</span><span class="sxs-lookup"><span data-stu-id="d5451-287">Typography Class</span></span>  
 <span data-ttu-id="d5451-288"><xref:System.Windows.Documents.Typography>オブジェクトは、一連の機能を公開する、[!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)]フォントをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="d5451-288">The <xref:System.Windows.Documents.Typography> object exposes the set of features that an [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] font supports.</span></span> <span data-ttu-id="d5451-289">プロパティを設定して<xref:System.Windows.Documents.Typography>、マークアップでは、ドキュメントの利用を簡単に作成できます[!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)]機能します。</span><span class="sxs-lookup"><span data-stu-id="d5451-289">By setting the properties of <xref:System.Windows.Documents.Typography> in markup, you can easily author documents that take advantage of [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] features.</span></span>  
  
 <span data-ttu-id="d5451-290">次のテキストは、Pescadero フォントの標準の大文字と、その後に "SmallCaps" および "AllSmallCaps" のスタイルをあてた文字を示したものです。</span><span class="sxs-lookup"><span data-stu-id="d5451-290">The following text displays standard capital letters for the Pescadero font, followed by the letters styled as "SmallCaps" and "AllSmallCaps".</span></span> <span data-ttu-id="d5451-291">この場合、同じフォント サイズは 3 つすべての単語の使用します。</span><span class="sxs-lookup"><span data-stu-id="d5451-291">In this case, the same font size is used for all three words.</span></span>  
  
 <span data-ttu-id="d5451-292">![OpenType の大文字を使用してテキストを](../../../../docs/framework/wpf/advanced/media/opentypefont11.gif "opentypefont11")</span><span class="sxs-lookup"><span data-stu-id="d5451-292">![Text using OpenType capitals](../../../../docs/framework/wpf/advanced/media/opentypefont11.gif "opentypefont11")</span></span>  
<span data-ttu-id="d5451-293">OpenType の大文字を使用するテキスト</span><span class="sxs-lookup"><span data-stu-id="d5451-293">Text using OpenType capitals</span></span>  
  
 <span data-ttu-id="d5451-294">次のマークアップ例のプロパティを使用して Pescadero フォントの大文字を定義する方法を示しています、<xref:System.Windows.Documents.Typography>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="d5451-294">The following markup example shows how to define capitals for the Pescadero font, using properties of the <xref:System.Windows.Documents.Typography> object.</span></span> <span data-ttu-id="d5451-295">"SmallCaps" 形式を使用する場合は、先頭の大文字は無視されます。</span><span class="sxs-lookup"><span data-stu-id="d5451-295">When the "SmallCaps" format is used, any leading capital letter is ignored.</span></span>  
  
 [!code-xaml[OpenTypeFontSamples#9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#9)]  
  
 <span data-ttu-id="d5451-296">次のコード例では、前のマークアップの例と同じタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="d5451-296">The following code example accomplishes the same task as the previous markup example.</span></span>  
  
 [!code-csharp[TypographyCodeSnippets#TypographyCodeSnippet1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TypographyCodeSnippets/CSharp/Page1.xaml.cs#typographycodesnippet1)]
 [!code-vb[TypographyCodeSnippets#TypographyCodeSnippet1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TypographyCodeSnippets/visualbasic/page1.xaml.vb#typographycodesnippet1)]  
  
### <a name="typography-class-properties"></a><span data-ttu-id="d5451-297">タイポグラフィ クラスのプロパティ</span><span class="sxs-lookup"><span data-stu-id="d5451-297">Typography Class Properties</span></span>  
 <span data-ttu-id="d5451-298">次の表は、プロパティ、値、および既定の設定、<xref:System.Windows.Documents.Typography>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="d5451-298">The following table lists the properties, values, and default settings of the <xref:System.Windows.Documents.Typography> object.</span></span>  
  
|<span data-ttu-id="d5451-299">プロパティ</span><span class="sxs-lookup"><span data-stu-id="d5451-299">Property</span></span>|<span data-ttu-id="d5451-300">[値]</span><span class="sxs-lookup"><span data-stu-id="d5451-300">Value(s)</span></span>|<span data-ttu-id="d5451-301">既定値</span><span class="sxs-lookup"><span data-stu-id="d5451-301">Default Value</span></span>|  
|--------------|----------------|-------------------|  
|<xref:System.Windows.Documents.Typography.AnnotationAlternates%2A>|<span data-ttu-id="d5451-302">数値 - バイト</span><span class="sxs-lookup"><span data-stu-id="d5451-302">Numeric value - byte</span></span>|<span data-ttu-id="d5451-303">0</span><span class="sxs-lookup"><span data-stu-id="d5451-303">0</span></span>|  
|<xref:System.Windows.Documents.Typography.Capitals%2A>|<span data-ttu-id="d5451-304"><xref:System.Windows.FontCapitals.AllPetiteCaps> &#124; <xref:System.Windows.FontCapitals.AllSmallCaps> &#124; <xref:System.Windows.FontCapitals.Normal> &#124; <xref:System.Windows.FontCapitals.PetiteCaps> &#124; <xref:System.Windows.FontCapitals.SmallCaps> &#124; <xref:System.Windows.FontCapitals.Titling> &#124; <xref:System.Windows.FontCapitals.Unicase></span><span class="sxs-lookup"><span data-stu-id="d5451-304"><xref:System.Windows.FontCapitals.AllPetiteCaps> &#124; <xref:System.Windows.FontCapitals.AllSmallCaps> &#124; <xref:System.Windows.FontCapitals.Normal> &#124; <xref:System.Windows.FontCapitals.PetiteCaps> &#124; <xref:System.Windows.FontCapitals.SmallCaps> &#124; <xref:System.Windows.FontCapitals.Titling> &#124; <xref:System.Windows.FontCapitals.Unicase></span></span>|<xref:System.Windows.FontCapitals.Normal?displayProperty=nameWithType>|  
|<xref:System.Windows.Documents.Typography.CapitalSpacing%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.CaseSensitiveForms%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.ContextualAlternates%2A>|<xref:System.Boolean>|`true`|  
|<xref:System.Windows.Documents.Typography.ContextualLigatures%2A>|<xref:System.Boolean>|`true`|  
|<xref:System.Windows.Documents.Typography.ContextualSwashes%2A>|<span data-ttu-id="d5451-305">数値 - バイト</span><span class="sxs-lookup"><span data-stu-id="d5451-305">Numeric value - byte</span></span>|<span data-ttu-id="d5451-306">0</span><span class="sxs-lookup"><span data-stu-id="d5451-306">0</span></span>|  
|<xref:System.Windows.Documents.Typography.DiscretionaryLigatures%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.EastAsianExpertForms%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.EastAsianLanguage%2A>|<span data-ttu-id="d5451-307"><xref:System.Windows.FontEastAsianLanguage.HojoKanji> &#124; <xref:System.Windows.FontEastAsianLanguage.Jis04> &#124; <xref:System.Windows.FontEastAsianLanguage.Jis78> &#124; <xref:System.Windows.FontEastAsianLanguage.Jis83> &#124; <xref:System.Windows.FontEastAsianLanguage.Jis90> &#124; <xref:System.Windows.FontEastAsianLanguage.NlcKanji> &#124; <xref:System.Windows.FontEastAsianLanguage.Normal> &#124; <xref:System.Windows.FontEastAsianLanguage.Simplified> &#124; <xref:System.Windows.FontEastAsianLanguage.Traditional> &#124; <xref:System.Windows.FontEastAsianLanguage.TraditionalNames></span><span class="sxs-lookup"><span data-stu-id="d5451-307"><xref:System.Windows.FontEastAsianLanguage.HojoKanji> &#124; <xref:System.Windows.FontEastAsianLanguage.Jis04> &#124; <xref:System.Windows.FontEastAsianLanguage.Jis78> &#124; <xref:System.Windows.FontEastAsianLanguage.Jis83> &#124; <xref:System.Windows.FontEastAsianLanguage.Jis90> &#124; <xref:System.Windows.FontEastAsianLanguage.NlcKanji> &#124; <xref:System.Windows.FontEastAsianLanguage.Normal> &#124; <xref:System.Windows.FontEastAsianLanguage.Simplified> &#124; <xref:System.Windows.FontEastAsianLanguage.Traditional> &#124; <xref:System.Windows.FontEastAsianLanguage.TraditionalNames></span></span>|<xref:System.Windows.FontEastAsianLanguage.Normal?displayProperty=nameWithType>|  
|<xref:System.Windows.Documents.Typography.EastAsianWidths%2A>|<span data-ttu-id="d5451-308"><xref:System.Windows.FontEastAsianWidths.Full> &#124; <xref:System.Windows.FontEastAsianWidths.Half> &#124; <xref:System.Windows.FontEastAsianWidths.Normal> &#124; <xref:System.Windows.FontEastAsianWidths.Proportional> &#124; <xref:System.Windows.FontEastAsianWidths.Quarter> &#124; <xref:System.Windows.FontEastAsianWidths.Third></span><span class="sxs-lookup"><span data-stu-id="d5451-308"><xref:System.Windows.FontEastAsianWidths.Full> &#124; <xref:System.Windows.FontEastAsianWidths.Half> &#124; <xref:System.Windows.FontEastAsianWidths.Normal> &#124; <xref:System.Windows.FontEastAsianWidths.Proportional> &#124; <xref:System.Windows.FontEastAsianWidths.Quarter> &#124; <xref:System.Windows.FontEastAsianWidths.Third></span></span>|<xref:System.Windows.FontEastAsianWidths.Normal?displayProperty=nameWithType>|  
|<xref:System.Windows.Documents.Typography.Fraction%2A>|<span data-ttu-id="d5451-309"><xref:System.Windows.FontFraction.Normal> &#124; <xref:System.Windows.FontFraction.Slashed> &#124; <xref:System.Windows.FontFraction.Stacked></span><span class="sxs-lookup"><span data-stu-id="d5451-309"><xref:System.Windows.FontFraction.Normal> &#124; <xref:System.Windows.FontFraction.Slashed> &#124; <xref:System.Windows.FontFraction.Stacked></span></span>|<xref:System.Windows.FontFraction.Normal?displayProperty=nameWithType>|  
|<xref:System.Windows.Documents.Typography.HistoricalForms%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.HistoricalLigatures%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.Kerning%2A>|<xref:System.Boolean>|`true`|  
|<xref:System.Windows.Documents.Typography.MathematicalGreek%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.NumeralAlignment%2A>|<span data-ttu-id="d5451-310"><xref:System.Windows.FontNumeralAlignment.Normal> &#124; <xref:System.Windows.FontNumeralAlignment.Proportional> &#124; <xref:System.Windows.FontNumeralAlignment.Tabular></span><span class="sxs-lookup"><span data-stu-id="d5451-310"><xref:System.Windows.FontNumeralAlignment.Normal> &#124; <xref:System.Windows.FontNumeralAlignment.Proportional> &#124; <xref:System.Windows.FontNumeralAlignment.Tabular></span></span>|<xref:System.Windows.FontNumeralAlignment.Normal?displayProperty=nameWithType>|  
|<xref:System.Windows.Documents.Typography.NumeralStyle%2A>|<xref:System.Boolean>|<xref:System.Windows.FontNumeralStyle.Normal?displayProperty=nameWithType>|  
|<xref:System.Windows.Documents.Typography.SlashedZero%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StandardLigatures%2A>|<xref:System.Boolean>|`true`|  
|<xref:System.Windows.Documents.Typography.StandardSwashes%2A>|<span data-ttu-id="d5451-311">数値 - バイト</span><span class="sxs-lookup"><span data-stu-id="d5451-311">numeric value – byte</span></span>|<span data-ttu-id="d5451-312">0</span><span class="sxs-lookup"><span data-stu-id="d5451-312">0</span></span>|  
|<xref:System.Windows.Documents.Typography.StylisticAlternates%2A>|<span data-ttu-id="d5451-313">数値 - バイト</span><span class="sxs-lookup"><span data-stu-id="d5451-313">numeric value – byte</span></span>|<span data-ttu-id="d5451-314">0</span><span class="sxs-lookup"><span data-stu-id="d5451-314">0</span></span>|  
|<xref:System.Windows.Documents.Typography.StylisticSet1%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet2%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet3%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet4%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet5%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet6%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet7%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet8%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet9%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet10%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet11%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet12%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet13%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet14%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet15%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet16%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet17%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet18%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet19%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet20%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.Variants%2A>|<span data-ttu-id="d5451-315"><xref:System.Windows.FontVariants.Inferior> &#124; <xref:System.Windows.FontVariants.Normal> &#124; <xref:System.Windows.FontVariants.Ordinal> &#124; <xref:System.Windows.FontVariants.Ruby> &#124; <xref:System.Windows.FontVariants.Subscript> &#124; <xref:System.Windows.FontVariants.Superscript></span><span class="sxs-lookup"><span data-stu-id="d5451-315"><xref:System.Windows.FontVariants.Inferior> &#124; <xref:System.Windows.FontVariants.Normal> &#124; <xref:System.Windows.FontVariants.Ordinal> &#124; <xref:System.Windows.FontVariants.Ruby> &#124; <xref:System.Windows.FontVariants.Subscript> &#124; <xref:System.Windows.FontVariants.Superscript></span></span>|<xref:System.Windows.FontVariants.Normal?displayProperty=nameWithType>|  
  
## <a name="see-also"></a><span data-ttu-id="d5451-316">関連項目</span><span class="sxs-lookup"><span data-stu-id="d5451-316">See Also</span></span>  
 <xref:System.Windows.Documents.Typography>  
 [<span data-ttu-id="d5451-317">OpenType の仕様</span><span class="sxs-lookup"><span data-stu-id="d5451-317">OpenType Specification</span></span>](https://go.microsoft.com/fwlink/?LinkId=96731)  
 [<span data-ttu-id="d5451-318">WPF のタイポグラフィ</span><span class="sxs-lookup"><span data-stu-id="d5451-318">Typography in WPF</span></span>](../../../../docs/framework/wpf/advanced/typography-in-wpf.md)  
 [<span data-ttu-id="d5451-319">OpenType フォント パックのサンプル</span><span class="sxs-lookup"><span data-stu-id="d5451-319">Sample OpenType Font Pack</span></span>](../../../../docs/framework/wpf/advanced/sample-opentype-font-pack.md)  
 [<span data-ttu-id="d5451-320">アプリケーションでのフォントのパッケージング</span><span class="sxs-lookup"><span data-stu-id="d5451-320">Packaging Fonts with Applications</span></span>](../../../../docs/framework/wpf/advanced/packaging-fonts-with-applications.md)
