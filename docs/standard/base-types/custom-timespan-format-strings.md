---
title: カスタム TimeSpan 書式指定文字列
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- format spexifiers, custom time interval
- format strings
- formatting [.NET Framework], time interval
- custom time interval format strings
- formatting [.NET Framework], time
- custom TimeSpan format strings
ms.assetid: a63ebf55-7269-416b-b4f5-286f6c03bf0e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9a22f462bc425a9c9e8f1be700474e7326193674
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2018
ms.locfileid: "44262636"
---
# <a name="custom-timespan-format-strings"></a>カスタム TimeSpan 書式指定文字列

<xref:System.TimeSpan> 書式指定文字列は、書式設定操作によって生成される <xref:System.TimeSpan> 値の文字列形式を定義します。 カスタム書式指定文字列は、1 つ以上のカスタム <xref:System.TimeSpan> 書式指定子と任意の数のリテラル文字で構成されます。 [標準の時間間隔書式指定文字列](standard-timespan-format-strings.md)以外の文字列は、すべてカスタム <xref:System.TimeSpan> 書式指定文字列として解釈されます。

> [!IMPORTANT]
> カスタム <xref:System.TimeSpan> 書式指定子には、日と時間、時間と分、または秒と秒の小数部を区切る記号などのプレースホルダー区切り記号は含まれません。 これらの記号は、カスタム書式指定文字列にリテラル文字列として含まれている必要があります。 たとえば、`"dd\.hh\:mm"` は、ピリオド (.) を日と時間の間の区切り記号として定義し、コロンを時間と分の間の区切り記号として定義します。
>
> カスタム <xref:System.TimeSpan> 書式指定子には、負と正の時間間隔の区別に使用できる符号も含まれていません。 符号を含めるには、条件ロジックを使用して書式指定文字列を構成する必要があります。 例については、「[その他の文字](#Other)」を参照してください。

<xref:System.TimeSpan> 値の文字列形式は、<xref:System.TimeSpan.ToString%2A?displayProperty=nameWithType> メソッドのオーバーロードの呼び出しと、<xref:System.String.Format%2A?displayProperty=nameWithType> などの複合書式指定をサポートするメソッドによって生成されます。 詳細については、「[型の書式設定](formatting-types.md)」と「[複合書式指定](composite-formatting.md)」をご覧ください。 次のコード例では、書式設定操作でカスタム書式指定文字列を使用する方法を示しています。

[!code-csharp[Conceptual.TimeSpan.Custom#1](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/customformatexample1.cs#1)]
[!code-vb[Conceptual.TimeSpan.Custom#1](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/customformatexample1.vb#1)]

カスタム <xref:System.TimeSpan> 書式指定文字列は、解析操作に必要な入力文字列の書式を定義するために <xref:System.TimeSpan.ParseExact%2A?displayProperty=nameWithType> メソッドと <xref:System.TimeSpan.TryParseExact%2A?displayProperty=nameWithType> メソッドでも使用されます  (解析では、特定の値の文字列形式が、その値に変換されます)。次のコード例では、解析操作で標準書式指定文字列を使用する方法を示しています。

[!code-csharp[Conceptual.TimeSpan.Custom#2](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/customparseexample1.cs#2)]
[!code-vb[Conceptual.TimeSpan.Custom#2](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/customparseexample1.vb#2)]

<a name="table"></a> カスタム日時書式指定子を次の表に示します。

| 書式指定子 | 説明 | 例 |
|----------------------|-----------------|-------------|
|"d" または "%d"|時間間隔の日数。<br /><br /> 詳細については、「["d" カスタム書式指定子](#dSpecifier)」を参照してください。|`new TimeSpan(6, 14, 32, 17, 685):`<br /><br /> `%d` --&gt; "6"<br /><br /> `d\.hh\:mm` --&gt; "6.14:32"|
|"dd" ～ "dddddddd"|必要に応じて先行ゼロで埋められた、時間間隔の日数。<br /><br /> 詳細については、「["dd" ～ "dddddddd" カスタム書式指定子](#ddSpecifier)」を参照してください。|`new TimeSpan(6, 14, 32, 17, 685):`<br /><br /> `ddd` --&gt; "006"<br /><br /> `dd\.hh\:mm` --&gt; "06.14:32"|
|"h" または "%h"|日数の一部としてカウントされない、時間間隔の時間数。 1 桁の時間に先行ゼロは付きません。<br /><br /> 詳細については、「["h" カスタム書式指定子](#hSpecifier)」を参照してください。|`new TimeSpan(6, 14, 32, 17, 685):`<br /><br /> `%h` --&gt; "14"<br /><br /> `hh\:mm` --&gt; "14:32"|
|"hh"|日数の一部としてカウントされない、時間間隔の時間数。 1 桁の時間には、先頭に 0 が付けられます。<br /><br /> 詳細については、「["hh" カスタム書式指定子](#hhSpecifier)」を参照してください。|`new TimeSpan(6, 14, 32, 17, 685):`<br /><br /> `hh` --&gt; "14"<br /><br /> `new TimeSpan(6, 8, 32, 17, 685):`<br /><br /> `hh` --&gt; 08|
|"m" または "%m"|時間数および日数のいずれの一部としても含まれない、時間間隔の分数。 1 桁の分に先行ゼロは付きません。<br /><br /> 詳細については、「["m" カスタム書式指定子](#mSpecifier)」を参照してください。|`new TimeSpan(6, 14, 8, 17, 685):`<br /><br /> `%m` --&gt; "8"<br /><br /> `h\:m` --&gt; "14:8"|
|"mm"|時間数および日数のいずれの一部としても含まれない、時間間隔の分数。 1 桁の分には、先頭に 0 が付きます。<br /><br /> 詳細については、「["mm" カスタム書式指定子](#mmSpecifier)」を参照してください。|`new TimeSpan(6, 14, 8, 17, 685):`<br /><br /> `mm` --&gt; "08"<br /><br /> `new TimeSpan(6, 8, 5, 17, 685):`<br /><br /> `d\.hh\:mm\:ss` --&gt; 6.08:05:17|
|"s" または "%s"|時間数、日数、および分数のいずれの一部としても含まれない、時間間隔の秒数。 1 桁の秒に先行ゼロは付きません。<br /><br /> 詳細については、「["s" カスタム書式指定子](#sSpecifier)」を参照してください。|`TimeSpan.FromSeconds(12.965)`:<br /><br /> `%s` --&gt; 12<br /><br /> `s\.fff` --&gt; 12.965|
|"ss"|時間数、日数、および分数のいずれの一部としても含まれない、時間間隔の秒数。  1 桁の秒には、先頭に 0 が付きます。<br /><br /> 詳細については、「["ss" カスタム書式指定子](#ssSpecifier)」を参照してください。|`TimeSpan.FromSeconds(6.965)`:<br /><br /> `ss` --&gt; 06<br /><br /> `ss\.fff` --&gt; 06.965|
|"f" または "%f"|時間間隔の秒部分の 1/10。<br /><br /> 詳細については、「["f" カスタム書式指定子](#fSpecifier)」を参照してください。|`TimeSpan.FromSeconds(6.895)`:<br /><br /> `f` --&gt; 8<br /><br /> `ss\.f` --&gt; 06.8|
|"ff"|時間間隔の秒部分の 1/100。<br /><br /> 詳細については、「["ff" カスタム書式指定子](#ffSpecifier)」を参照してください。|`TimeSpan.FromSeconds(6.895)`:<br /><br /> `ff` --&gt; 89<br /><br /> `ss\.ff` --&gt; 06.89|
|"fff"|時間間隔の秒部分の 1/1000。<br /><br /> 詳細については、「["fff" カスタム書式指定子](#f3Specifier)」を参照してください。|`TimeSpan.FromSeconds(6.895)`:<br /><br /> `fff` --&gt; 895<br /><br /> `ss\.fff` --&gt; 06.895|
|"ffff"|時間間隔の秒部分の 1/10000。<br /><br /> 詳細については、「["ffff" カスタム書式指定子](#f4Specifier)」を参照してください。|`TimeSpan.Parse("0:0:6.8954321")`:<br /><br /> `ffff` --&gt; 8954<br /><br /> `ss\.ffff` --&gt; 06.8954|
|"fffff"|時間間隔の秒部分の 1/100000。<br /><br /> 詳細については、「["fffff" カスタム書式指定子](#f5Specifier)」を参照してください。|`TimeSpan.Parse("0:0:6.8954321")`:<br /><br /> `fffff` --&gt; 89543<br /><br /> `ss\.fffff` --&gt; 06.89543|
|"ffffff"|時間間隔の秒部分の 1/1000000。<br /><br /> 詳細については、「["ffffff" カスタム書式指定子](#f6Specifier)」を参照してください。|`TimeSpan.Parse("0:0:6.8954321")`:<br /><br /> `ffffff` --&gt; 895432<br /><br /> `ss\.ffffff` --&gt; 06.895432|
|"fffffff"|時間間隔の秒部分の 1/10000000 (またはタイマー刻みの小数部)。<br /><br /> 詳細については、「["fffffff" カスタム書式指定子](#f7Specifier)」を参照してください。|`TimeSpan.Parse("0:0:6.8954321")`:<br /><br /> `fffffff` --&gt; 8954321<br /><br /> `ss\.fffffff` --&gt; 06.8954321|
|"F" または "%F"|時間間隔の秒部分の 1/10。 その桁がゼロの場合には、何も表示されません。<br /><br /> 詳細については、「["F" カスタム書式指定子](#F_Specifier)」を参照してください。|`TimeSpan.Parse("00:00:06.32")`:<br /><br /> `%F`: 3<br /><br /> `TimeSpan.Parse("0:0:3.091")`:<br /><br /> `ss\.F`: 03.|
|"FF"|時間間隔の秒部分の 1/100。 小数の後続のゼロは表示されません。また、2 桁のゼロも含まれません。<br /><br /> 詳細については、「["FF" カスタム書式指定子](#FF_Specifier)」を参照してください。|`TimeSpan.Parse("00:00:06.329")`:<br /><br /> `FF`: 32<br /><br /> `TimeSpan.Parse("0:0:3.101")`:<br /><br /> `ss\.FF`: 03.1|
|"FFF"|時間間隔の秒部分の 1/1000。 小数の後続のゼロは含まれません。<br /><br /> 詳細情報:|`TimeSpan.Parse("00:00:06.3291")`:<br /><br /> `FFF`: 329<br /><br /> `TimeSpan.Parse("0:0:3.1009")`:<br /><br /> `ss\.FFF`: 03.1|
|"FFFF"|時間間隔の秒部分の 1/10000。 小数の後続のゼロは含まれません。<br /><br /> 詳細については、「["FFFF" カスタム書式指定子](#F4_Specifier)」を参照してください。|`TimeSpan.Parse("00:00:06.32917")`:<br /><br /> `FFFFF`: 3291<br /><br /> `TimeSpan.Parse("0:0:3.10009")`:<br /><br /> `ss\.FFFF`: 03.1|
|"FFFFF"|時間間隔の秒部分の 1/100000。 小数の後続のゼロは含まれません。<br /><br /> 詳細については、「["FFFFF" カスタム書式指定子](#F5_Specifier)」を参照してください。|`TimeSpan.Parse("00:00:06.329179")`:<br /><br /> `FFFFF`: 32917<br /><br /> `TimeSpan.Parse("0:0:3.100009")`:<br /><br /> `ss\.FFFFF`: 03.1|
|"FFFFFF"|時間間隔の秒部分の 1/1000000。 小数の後続のゼロは表示されません。<br /><br /> 詳細については、「["FFFFFF" カスタム書式指定子](#F6_Specifier)」を参照してください。|`TimeSpan.Parse("00:00:06.3291791")`:<br /><br /> `FFFFFF`: 329179<br /><br /> `TimeSpan.Parse("0:0:3.1000009")`:<br /><br /> `ss\.FFFFFF`: 03.1|
|"FFFFFFF"|時間間隔の秒部分の 1/10000000。 小数の後続のゼロは表示されません。また、7 桁のゼロも表示されません。<br /><br /> 詳細については、「["FFFFFFF" カスタム書式指定子](#F7_Specifier)」を参照してください。|`TimeSpan.Parse("00:00:06.3291791")`:<br /><br /> `FFFFFF`: 3291791<br /><br /> `TimeSpan.Parse("0:0:3.1900000")`:<br /><br /> `ss\.FFFFFF`: 03.19|
|'*文字列*'|リテラル文字列の区切り記号。<br /><br /> 詳細については、「[その他の文字](#Other)」を参照してください。|`new TimeSpan(14, 32, 17):`<br /><br /> `hh':'mm':'ss` --&gt; "14:32:17"|
|\\|エスケープ文字。<br /><br /> 詳細については、「[その他の文字](#Other)」を参照してください。|`new TimeSpan(14, 32, 17):`<br /><br /> `hh\:mm\:ss` --&gt; "14:32:17"|
|その他の文字|エスケープされないその他の文字はすべて、カスタム書式指定子として解釈されます。<br /><br /> 詳細については、「[その他の文字](#Other)」を参照してください。|`new TimeSpan(14, 32, 17):`<br /><br /> `hh\:mm\:ss` --&gt; "14:32:17"|

<a name="dSpecifier"></a> 

## <a name="the-d-custom-format-specifier"></a>"d" カスタム書式指定子

"d" カスタム書式指定子は、時間間隔の日数を表す <xref:System.TimeSpan.Days%2A?displayProperty=nameWithType> プロパティの値を出力します。 値が 1 桁を超える場合でも、<xref:System.TimeSpan> 値の完全な日数が出力されます。 <xref:System.TimeSpan.Days%2A?displayProperty=nameWithType> プロパティの値が 0 の場合、指定子は "0" を出力します。

"d" カスタム書式指定子が単独で使用される場合は、間違って標準書式指定文字列として解釈されないように "%d" を指定します。 具体的な例を次に示します。

[!code-csharp[Conceptual.TimeSpan.Custom#3](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/customexamples1.cs#3)]
[!code-vb[Conceptual.TimeSpan.Custom#3](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/customexamples1.vb#3)]

"d" カスタム書式指定子の使用例を次に示します。

[!code-csharp[Conceptual.TimeSpan.Custom#4](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/customexamples1.cs#4)]
[!code-vb[Conceptual.TimeSpan.Custom#4](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/customexamples1.vb#4)]

[表のトップへ](#table)

<a name="ddSpecifier"></a> 

## <a name="the-dd-dddddddd-custom-format-specifiers"></a>"dd" ～ "dddddddd" カスタム書式指定子
"dd"、"ddd"、"dddd"、"ddddd"、"dddddd"、"ddddddd"、および "dddddddd" カスタム書式指定子は、時間間隔の日数を表す <xref:System.TimeSpan.Days%2A?displayProperty=nameWithType> プロパティの値を出力します。

出力文字列には、書式指定子の "d" 文字の数で指定される桁数以上が含まれ、必要に応じて、先行ゼロで埋められます。 日数の桁数が書式指定子の "d" 文字の数を超える場合は、結果文字列に完全な日数が出力されます。

次の例では、これらの書式指定子を使用して、2 つの <xref:System.TimeSpan> 値の文字列形式を表示します。 最初の時間間隔の日の部分の値は 0 です。2 番目の時間間隔の日の部分の値は 365 です。

[!code-csharp[Conceptual.TimeSpan.Custom#5](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/customexamples1.cs#5)]
[!code-vb[Conceptual.TimeSpan.Custom#5](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/customexamples1.vb#5)]

[表のトップへ](#table)

<a name="hSpecifier"></a> 

## <a name="the-h-custom-format-specifier"></a>"h" カスタム書式指定子
"h" カスタム書式指定子は、日の部分の一部としてカウントされない、時間間隔の時間数を表す <xref:System.TimeSpan.Hours%2A?displayProperty=nameWithType> プロパティの値を出力します。 <xref:System.TimeSpan.Hours%2A?displayProperty=nameWithType> プロパティの値が 0 ～ 9 の場合は 1 桁の文字列値を返し、<xref:System.TimeSpan.Hours%2A?displayProperty=nameWithType> プロパティの値が 10 ～ 23 の場合は 2 桁の文字列値を返します。

"h" カスタム書式指定子が単独で使用される場合は、誤って標準書式指定文字列として解釈されないように "%h" を指定します。 具体的な例を次に示します。

[!code-csharp[Conceptual.TimeSpan.Custom#6](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/customexamples1.cs#6)]
[!code-vb[Conceptual.TimeSpan.Custom#6](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/customexamples1.vb#6)]

通常、解析操作では、1 つの数値のみを含む入力文字列は日数として解釈されます。 代わりに "%h" カスタム書式指定子を使用すると、数値文字列を時間数として解釈できます。 具体的な例を次に示します。

[!code-csharp[Conceptual.TimeSpan.Custom#8](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/customexamples1.cs#8)]
[!code-vb[Conceptual.TimeSpan.Custom#8](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/customexamples1.vb#8)]

"h" カスタム書式指定子の使用例を次に示します。

[!code-csharp[Conceptual.TimeSpan.Custom#7](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/customexamples1.cs#7)]
[!code-vb[Conceptual.TimeSpan.Custom#7](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/customexamples1.vb#7)]

[表のトップへ](#table)

<a name="hhSpecifier"></a> 

## <a name="the-hh-custom-format-specifier"></a>"hh" カスタム書式指定子
"hh" カスタム書式指定子は、日の部分の一部としてカウントされない、時間間隔の時間数を表す <xref:System.TimeSpan.Hours%2A?displayProperty=nameWithType> プロパティの値を出力します。 0 ～ 9 の値の場合は、出力文字列に先行ゼロが含まれます。

通常、解析操作では、1 つの数値のみを含む入力文字列は日数として解釈されます。 代わりに "hh" カスタム書式指定子を使用すると、数値文字列を時間数として解釈できます。 具体的な例を次に示します。

[!code-csharp[Conceptual.TimeSpan.Custom#9](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/customexamples1.cs#9)]
[!code-vb[Conceptual.TimeSpan.Custom#9](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/customexamples1.vb#9)]

"hh" カスタム書式指定子の使用例を次に示します。

[!code-csharp[Conceptual.TimeSpan.Custom#10](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/customexamples1.cs#10)]
[!code-vb[Conceptual.TimeSpan.Custom#10](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/customexamples1.vb#10)]

[表のトップへ](#table)

<a name="mSpecifier"></a> 

## <a name="the-m-custom-format-specifier"></a>"m" カスタム書式指定子
"m" カスタム書式指定子は、日の部分の一部としてカウントされない、時間間隔の分数を表す <xref:System.TimeSpan.Minutes%2A?displayProperty=nameWithType> プロパティの値を出力します。 <xref:System.TimeSpan.Minutes%2A?displayProperty=nameWithType> プロパティの値が 0 ～ 9 の場合は 1 桁の文字列値を返し、<xref:System.TimeSpan.Minutes%2A?displayProperty=nameWithType> プロパティの値が 10 ～ 59 の場合は 2 桁の文字列値を返します。

"m" カスタム書式指定子が単独で使用される場合は、誤って標準書式指定文字列として解釈されないように "%m" を指定します。 具体的な例を次に示します。

[!code-csharp[Conceptual.TimeSpan.Custom#6](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/customexamples1.cs#6)]
[!code-vb[Conceptual.TimeSpan.Custom#6](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/customexamples1.vb#6)]

通常、解析操作では、1 つの数値のみを含む入力文字列は日数として解釈されます。 代わりに "%m" カスタム書式指定子を使用すると、数値文字列を分数として解釈できます。 具体的な例を次に示します。

[!code-csharp[Conceptual.TimeSpan.Custom#11](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/customexamples1.cs#11)]
[!code-vb[Conceptual.TimeSpan.Custom#11](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/customexamples1.vb#11)]

"m" カスタム書式指定子の使用例を次に示します。

[!code-csharp[Conceptual.TimeSpan.Custom#12](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/customexamples1.cs#12)]
[!code-vb[Conceptual.TimeSpan.Custom#12](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/customexamples1.vb#12)]

[表のトップへ](#table)

<a name="mmSpecifier"></a> 

## <a name="the-mm-custom-format-specifier"></a>"mm" カスタム書式指定子
"mm" カスタム書式指定子は、時間または日の部分の一部として含まれない、時間間隔の分数を表す <xref:System.TimeSpan.Minutes%2A?displayProperty=nameWithType> プロパティの値を出力します。 0 ～ 9 の値の場合は、出力文字列に先行ゼロが含まれます。

通常、解析操作では、1 つの数値のみを含む入力文字列は日数として解釈されます。 代わりに "mm" カスタム書式指定子を使用すると、数値文字列を分数として解釈できます。 具体的な例を次に示します。

[!code-csharp[Conceptual.TimeSpan.Custom#13](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/customexamples1.cs#13)]
[!code-vb[Conceptual.TimeSpan.Custom#13](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/customexamples1.vb#13)]

"mm" カスタム書式指定子の使用例を次に示します。

[!code-csharp[Conceptual.TimeSpan.Custom#14](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/customexamples1.cs#14)]
[!code-vb[Conceptual.TimeSpan.Custom#14](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/customexamples1.vb#14)]

[表のトップへ](#table)

<a name="sSpecifier"></a> 

## <a name="the-s-custom-format-specifier"></a>"s" カスタム書式指定子
"s" カスタム書式指定子は、時間、日、および分の部分のいずれの一部としても含まれない、時間間隔の秒数を表す <xref:System.TimeSpan.Seconds%2A?displayProperty=nameWithType> プロパティの値を出力します。 <xref:System.TimeSpan.Seconds%2A?displayProperty=nameWithType> プロパティの値が 0 ～ 9 の場合は 1 桁の文字列値を返し、<xref:System.TimeSpan.Seconds%2A?displayProperty=nameWithType> プロパティの値が 10 ～ 59 の場合は 2 桁の文字列値を返します。

"s" カスタム書式指定子が単独で使用される場合は、誤って標準書式指定文字列として解釈されないように "%s" を指定します。 具体的な例を次に示します。

[!code-csharp[Conceptual.TimeSpan.Custom#15](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/customexamples1.cs#15)]
[!code-vb[Conceptual.TimeSpan.Custom#15](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/customexamples1.vb#15)]

通常、解析操作では、1 つの数値のみを含む入力文字列は日数として解釈されます。 代わりに "%s" カスタム書式指定子を使用すると、数値文字列を秒数として解釈できます。 具体的な例を次に示します。

[!code-csharp[Conceptual.TimeSpan.Custom#17](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/customexamples1.cs#17)]
[!code-vb[Conceptual.TimeSpan.Custom#17](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/customexamples1.vb#17)]

"s" カスタム書式指定子の使用例を次に示します。

[!code-csharp[Conceptual.TimeSpan.Custom#16](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/customexamples1.cs#16)]
[!code-vb[Conceptual.TimeSpan.Custom#16](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/customexamples1.vb#16)]

[表のトップへ](#table)

<a name="ssSpecifier"></a> 

## <a name="the-ss-custom-format-specifier"></a>"ss" カスタム書式指定子
"ss" カスタム書式指定子は、時間、日、および分の部分のいずれの一部としても含まれない、時間間隔の秒数を表す <xref:System.TimeSpan.Seconds%2A?displayProperty=nameWithType> プロパティの値を出力します。 0 ～ 9 の値の場合は、出力文字列に先行ゼロが含まれます。

通常、解析操作では、1 つの数値のみを含む入力文字列は日数として解釈されます。 代わりに "ss" カスタム書式指定子を使用すると、数値文字列を秒数として解釈できます。 具体的な例を次に示します。

[!code-csharp[Conceptual.TimeSpan.Custom#18](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/customexamples1.cs#18)]
[!code-vb[Conceptual.TimeSpan.Custom#18](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/customexamples1.vb#18)]

"ss" カスタム書式指定子の使用例を次に示します。

[!code-csharp[Conceptual.TimeSpan.Custom#19](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/customexamples1.cs#19)]
[!code-vb[Conceptual.TimeSpan.Custom#19](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/customexamples1.vb#19)]

[表のトップへ](#table)

<a name="fSpecifier"></a> 

## <a name="thef-custom-format-specifier"></a>"f" カスタム書式指定子
"f" カスタム書式指定子は、時間間隔の秒部分の 1/10 を出力します。 書式指定操作では、これより下位の小数桁は切り捨てられます。 <xref:System.TimeSpan.ParseExact%2A?displayProperty=nameWithType> メソッドまたは <xref:System.TimeSpan.TryParseExact%2A?displayProperty=nameWithType> メソッドを呼び出す解析操作では、入力文字列に 1 桁の小数部が含まれている必要があります。

"f" カスタム書式指定子が単独で使用される場合は、誤って標準書式指定文字列として解釈されないように "%f" を指定します。

次の例では、"f" カスタム書式指定子を使用して、<xref:System.TimeSpan> 値の秒部分の 1/10 を表示します。 "f" は最初に唯一の書式指定子として使用されてから、カスタム書式指定文字列で "s" 指定子と結合されます。

[!code-csharp[Conceptual.TimeSpan.Custom#20](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/fspecifiers1.cs#20)]
[!code-vb[Conceptual.TimeSpan.Custom#20](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/fspecifiers1.vb#20)]

[表のトップへ](#table)

<a name="ffSpecifier"></a> 

## <a name="the-ff-custom-format-specifier"></a>"ff" カスタム書式指定子
"ff" カスタム書式指定子は、時間間隔の秒部分の 1/100 を出力します。 書式指定操作では、これより下位の小数桁は切り捨てられます。 <xref:System.TimeSpan.ParseExact%2A?displayProperty=nameWithType> メソッドまたは <xref:System.TimeSpan.TryParseExact%2A?displayProperty=nameWithType> メソッドを呼び出す解析操作では、入力文字列に 2 桁の小数部が含まれている必要があります。

次の例では、"ff" カスタム書式指定子を使用して、<xref:System.TimeSpan> 値の秒部分の 1/100 を表示します。 "ff" は最初に唯一の書式指定子として使用されてから、カスタム書式指定文字列で "s" 指定子と結合されます。

[!code-csharp[Conceptual.TimeSpan.Custom#20](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/fspecifiers1.cs#20)]
[!code-vb[Conceptual.TimeSpan.Custom#20](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/fspecifiers1.vb#20)]

[表のトップへ](#table)

<a name="f3Specifier"></a> 

## <a name="the-fff-custom-format-specifier"></a>"fff" カスタム書式指定子
"fff" カスタム書式指定子 ("f" 文字が 3 つ) は、時間間隔の秒部分の 1/1000 を出力します。 書式指定操作では、これより下位の小数桁は切り捨てられます。 <xref:System.TimeSpan.ParseExact%2A?displayProperty=nameWithType> メソッドまたは <xref:System.TimeSpan.TryParseExact%2A?displayProperty=nameWithType> メソッドを呼び出す解析操作では、入力文字列に 3 桁の小数部が含まれている必要があります。

次の例では、"fff" カスタム書式指定子を使用して、<xref:System.TimeSpan> 値の秒部分の 1/1000 を表示します。 "fff" は最初に唯一の書式指定子として使用されてから、カスタム書式指定文字列で "s" 指定子と結合されます。

[!code-csharp[Conceptual.TimeSpan.Custom#20](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/fspecifiers1.cs#20)]
[!code-vb[Conceptual.TimeSpan.Custom#20](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/fspecifiers1.vb#20)]

[表のトップへ](#table)

<a name="f4Specifier"></a> 

## <a name="the-ffff-custom-format-specifier"></a>"ffff" カスタム書式指定子
"ffff" カスタム書式指定子 ("f" 文字が 4 つ) は、時間間隔の秒部分の 1/10000 を出力します。 書式指定操作では、これより下位の小数桁は切り捨てられます。 <xref:System.TimeSpan.ParseExact%2A?displayProperty=nameWithType> メソッドまたは <xref:System.TimeSpan.TryParseExact%2A?displayProperty=nameWithType> メソッドを呼び出す解析操作では、入力文字列に 4 桁の小数部が含まれている必要があります。

次の例では、"ffff" カスタム書式指定子を使用して、<xref:System.TimeSpan> 値の秒部分の 1/10000 を表示します。 "ffff" は最初に唯一の書式指定子として使用されてから、カスタム書式指定文字列で "s" 指定子と結合されます。

[!code-csharp[Conceptual.TimeSpan.Custom#20](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/fspecifiers1.cs#20)]
[!code-vb[Conceptual.TimeSpan.Custom#20](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/fspecifiers1.vb#20)]

[表のトップへ](#table)

<a name="f5Specifier"></a> 

## <a name="the-fffff-custom-format-specifier"></a>"fffff" カスタム書式指定子
"fffff" カスタム書式指定子 ("f" 文字が 5 つ) は、時間間隔の秒部分の 1/100000 を出力します。 書式指定操作では、これより下位の小数桁は切り捨てられます。 <xref:System.TimeSpan.ParseExact%2A?displayProperty=nameWithType> メソッドまたは <xref:System.TimeSpan.TryParseExact%2A?displayProperty=nameWithType> メソッドを呼び出す解析操作では、入力文字列に 5 桁の小数部が含まれている必要があります。

次の例では、"fffff" カスタム書式指定子を使用して、<xref:System.TimeSpan> 値の秒部分の 1/100000 を表示します。 "fffff" は最初に、唯一の書式指定子として使用されてから、カスタム書式指定文字列で "s" 指定子と結合されます。

[!code-csharp[Conceptual.TimeSpan.Custom#20](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/fspecifiers1.cs#20)]
[!code-vb[Conceptual.TimeSpan.Custom#20](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/fspecifiers1.vb#20)]

[表のトップへ](#table)

<a name="f6Specifier"></a> 

## <a name="the-ffffff-custom-format-specifier"></a>"ffffff" カスタム書式指定子
"ffffff" カスタム書式指定子 ("f" 文字が 6 つ) は、時間間隔の秒部分の 1/1000000 を出力します。 書式指定操作では、これより下位の小数桁は切り捨てられます。 <xref:System.TimeSpan.ParseExact%2A?displayProperty=nameWithType> メソッドまたは <xref:System.TimeSpan.TryParseExact%2A?displayProperty=nameWithType> メソッドを呼び出す解析操作では、入力文字列に 6 桁の小数部が含まれている必要があります。

次の例では、"ffffff" カスタム書式指定子を使用して、<xref:System.TimeSpan> 値の秒部分の 1/1000000 を表示します。 最初に唯一の書式指定子として使用されてから、カスタム書式指定文字列で "s" 指定子と結合されます。

[!code-csharp[Conceptual.TimeSpan.Custom#20](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/fspecifiers1.cs#20)]
[!code-vb[Conceptual.TimeSpan.Custom#20](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/fspecifiers1.vb#20)]

[表のトップへ](#table)

<a name="f7Specifier"></a> 

## <a name="the-fffffff-custom-format-specifier"></a>"fffffff" カスタム書式指定子
"fffffff" カスタム書式指定子 ("f" 文字が 7 つ) は、時間間隔の秒部分の 1/10000000 (またはタイマー刻みの小数部) を出力します。 <xref:System.TimeSpan.ParseExact%2A?displayProperty=nameWithType> メソッドまたは <xref:System.TimeSpan.TryParseExact%2A?displayProperty=nameWithType> メソッドを呼び出す解析操作では、入力文字列に 7 桁の小数部が含まれている必要があります。

次の例では、"fffffff" カスタム書式指定子を使用して、<xref:System.TimeSpan> 値のタイマー刻みの小数部を表示します。 最初に唯一の書式指定子として使用されてから、カスタム書式指定文字列で "s" 指定子と結合されます。

[!code-csharp[Conceptual.TimeSpan.Custom#20](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/fspecifiers1.cs#20)]
[!code-vb[Conceptual.TimeSpan.Custom#20](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/fspecifiers1.vb#20)]

[表のトップへ](#table)

<a name="F_Specifier"></a> 

## <a name="the-f-custom-format-specifier"></a>"F" カスタム書式指定子
"F" カスタム書式指定子は、時間間隔の秒部分の 1/10 を出力します。 書式指定操作では、これより下位の小数桁は切り捨てられます。 時間間隔の秒部分の 1/10 が 0 の場合、それは結果文字列に含まれません。 <xref:System.TimeSpan.ParseExact%2A?displayProperty=nameWithType> メソッドまたは <xref:System.TimeSpan.TryParseExact%2A?displayProperty=nameWithType> メソッドを呼び出す解析操作では、秒の 1/10 の桁を使用するかどうかはオプションです。

"F" カスタム書式指定子が単独で使用される場合は、誤って標準書式指定文字列として解釈されないように "%F" を指定します。

次の例では、"F" カスタム書式指定子を使用して、<xref:System.TimeSpan> 値の秒部分の 1/10 を表示します。 このカスタム書式指定子は解析操作でも使用されます。

[!code-csharp[Conceptual.TimeSpan.Custom#21](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/f_specifiers1.cs#21)]
[!code-vb[Conceptual.TimeSpan.Custom#21](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/f_specifiers1.vb#21)]

[表のトップへ](#table)

<a name="FF_Specifier"></a> 

## <a name="the-ff-custom-format-specifier"></a>"FF" カスタム書式指定子
"FF" カスタム書式指定子は、時間間隔の秒部分の 1/100 を出力します。 書式指定操作では、これより下位の小数桁は切り捨てられます。 後続の小数のゼロがある場合、それらの数字は結果文字列に含まれません。 <xref:System.TimeSpan.ParseExact%2A?displayProperty=nameWithType> メソッドまたは <xref:System.TimeSpan.TryParseExact%2A?displayProperty=nameWithType> メソッドを呼び出す解析操作では、秒の 1/10 および 1/100 の桁を使用するかどうかはオプションです。

次の例では、"FF" カスタム書式指定子を使用して、<xref:System.TimeSpan> 値の秒部分の 1/100 を表示します。 このカスタム書式指定子は解析操作でも使用されます。

[!code-csharp[Conceptual.TimeSpan.Custom#22](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/f_specifiers1.cs#22)]
[!code-vb[Conceptual.TimeSpan.Custom#22](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/f_specifiers1.vb#22)]

[表のトップへ](#table)

<a name="F3_Specifier"></a> 

## <a name="the-fff-custom-format-specifier"></a>"FFF" カスタム書式指定子
"FFF" カスタム書式指定子 ("F" 文字が 3 つ) は、時間間隔の秒部分の 1/1000 を出力します。 書式指定操作では、これより下位の小数桁は切り捨てられます。 後続の小数のゼロがある場合、それらの数字は結果文字列に含まれません。 <xref:System.TimeSpan.ParseExact%2A?displayProperty=nameWithType> メソッドまたは <xref:System.TimeSpan.TryParseExact%2A?displayProperty=nameWithType> メソッドを呼び出す解析操作では、秒の 1/10、1/100、および 1/1000 の桁を使用するかどうかはオプションです。

次の例では、"FFF" カスタム書式指定子を使用して、<xref:System.TimeSpan> 値の秒部分の 1/1000 を表示します。 このカスタム書式指定子は解析操作でも使用されます。

[!code-csharp[Conceptual.TimeSpan.Custom#23](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/f_specifiers1.cs#23)]
[!code-vb[Conceptual.TimeSpan.Custom#23](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/f_specifiers1.vb#23)]

[表のトップへ](#table)

<a name="F4_Specifier"></a> 

## <a name="the-ffff-custom-format-specifier"></a>"FFFF" カスタム書式指定子
"FFFF" カスタム書式指定子 ("F" 文字が 4 つ) は、時間間隔の秒部分の 1/10000 を出力します。 書式指定操作では、これより下位の小数桁は切り捨てられます。 後続の小数のゼロがある場合、それらの数字は結果文字列に含まれません。 <xref:System.TimeSpan.ParseExact%2A?displayProperty=nameWithType> メソッドまたは <xref:System.TimeSpan.TryParseExact%2A?displayProperty=nameWithType> メソッドを呼び出す解析操作では、秒の 1/10、1/100、1/1000、および 1/10000 の桁を使用するかどうかはオプションです。

次の例では、"FFFF" カスタム書式指定子を使用して、<xref:System.TimeSpan> 値の秒部分の 1/10000 を表示します。 "FFFF" カスタム書式指定子は解析操作でも使用されます。

[!code-csharp[Conceptual.TimeSpan.Custom#24](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/f_specifiers1.cs#24)]
[!code-vb[Conceptual.TimeSpan.Custom#24](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/f_specifiers1.vb#24)]

[表のトップへ](#table)

<a name="F5_Specifier"></a> 

## <a name="the-fffff-custom-format-specifier"></a>"FFFFF" カスタム書式指定子
"FFFFF" カスタム書式指定子 ("F" 文字が 5 つ) は、時間間隔の秒部分の 1/100000 を出力します。 書式指定操作では、これより下位の小数桁は切り捨てられます。 後続の小数のゼロがある場合、それらの数字は結果文字列に含まれません。 <xref:System.TimeSpan.ParseExact%2A?displayProperty=nameWithType> メソッドまたは <xref:System.TimeSpan.TryParseExact%2A?displayProperty=nameWithType> メソッドを呼び出す解析操作では、秒の 1/10、1/100、1/1000、1/10000、および 1/100000 の桁を使用するかどうかはオプションです。

次の例では、"FFFFF" カスタム書式指定子を使用して、<xref:System.TimeSpan> 値の秒部分の 1/100000 を表示します。 "FFFFF" カスタム書式指定子は解析操作でも使用されます。

[!code-csharp[Conceptual.TimeSpan.Custom#25](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/f_specifiers1.cs#25)]
[!code-vb[Conceptual.TimeSpan.Custom#25](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/f_specifiers1.vb#25)]

[表のトップへ](#table)

<a name="F6_Specifier"></a> 

## <a name="the-ffffff-custom-format-specifier"></a>"FFFFFF" カスタム書式指定子
"FFFFFF" カスタム書式指定子 ("F" 文字が 6 つ) は、時間間隔の秒部分の 1/1000000 を出力します。 書式指定操作では、これより下位の小数桁は切り捨てられます。 後続の小数のゼロがある場合、それらの数字は結果文字列に含まれません。 <xref:System.TimeSpan.ParseExact%2A?displayProperty=nameWithType> メソッドまたは <xref:System.TimeSpan.TryParseExact%2A?displayProperty=nameWithType> メソッドを呼び出す解析操作では、秒の 1/10、1/100、1/1000、1/10000、1/100000 および 1/1000000 の桁を使用するかどうかはオプションです。

次の例では、"FFFFFF" カスタム書式指定子を使用して、<xref:System.TimeSpan> 値の秒部分の 1/1000000 を表示します。 このカスタム書式指定子は解析操作でも使用されます。

[!code-csharp[Conceptual.TimeSpan.Custom#26](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/f_specifiers1.cs#26)]
[!code-vb[Conceptual.TimeSpan.Custom#26](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/f_specifiers1.vb#26)]

[表のトップへ](#table)

<a name="F7_Specifier"></a> 

## <a name="the-fffffff-custom-format-specifier"></a>"FFFFFFF" カスタム書式指定子
"FFFFFFF" カスタム書式指定子 ("F" 文字が 7 つ) は、時間間隔の秒部分の 1/10000000 (またはタイマー刻みの小数部) を出力します。 後続の小数のゼロがある場合、それらの数字は結果文字列に含まれません。 <xref:System.TimeSpan.ParseExact%2A?displayProperty=nameWithType> メソッドまたは <xref:System.TimeSpan.TryParseExact%2A?displayProperty=nameWithType> メソッドを呼び出す解析操作では、入力文字列の 7 桁の小数部を使用するかどうかはオプションです。

次の例では、"FFFFFFF" カスタム書式指定子を使用して、<xref:System.TimeSpan> 値の秒部分の小数部を表示します。 このカスタム書式指定子は解析操作でも使用されます。

[!code-csharp[Conceptual.TimeSpan.Custom#27](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/f_specifiers1.cs#27)]
[!code-vb[Conceptual.TimeSpan.Custom#27](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/f_specifiers1.vb#27)]

[表のトップへ](#table)

<a name="Other"></a> 

## <a name="other-characters"></a>その他の文字

空白文字など、書式指定文字列内のエスケープされないその他の文字は、カスタム書式指定子として解釈されます。 ほとんどの場合、エスケープされないその他の文字が存在すると、<xref:System.FormatException> が発生します。

書式指定文字列にリテラル文字を含める方法は 2 つあります。

- 単一引用符 (リテラル文字列の区切り記号) で囲みます。

- エスケープ文字として解釈される円記号 ("\\") を前に付けます。 このため、C# では、書式指定文字列に @-quoted、またはリテラル文字の前に追加の円記号が指定されている必要があります。

  条件ロジックを使用してエスケープされたリテラルを書式指定文字列に含めることが必要になる場合もあります。 次の例では、条件ロジックを使用して負の時間間隔の符号を含めます。

  [!code-csharp[Conceptual.TimeSpan.Custom#29](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/negativevalues1.cs#29)]
  [!code-vb[Conceptual.TimeSpan.Custom#29](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/negativevalues1.vb#29)]

.NET では、時間間隔の区切り記号の文法が定義されていません。 そのため、日と時間、時間と分、分と秒、および秒と秒の小数部の間の区切り記号は、書式指定文字列ですべて文字リテラルとして扱う必要があります。

次の例では、エスケープ文字と単一引用符の両方を使用して、出力文字列に "minutes" という単語を含むカスタム書式指定文字列を定義しています。

[!code-csharp[Conceptual.TimeSpan.Custom#28](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/literal1.cs#28)]
[!code-vb[Conceptual.TimeSpan.Custom#28](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/literal1.vb#28)]

[表のトップへ](#table)

## <a name="see-also"></a>関連項目

- [型の書式設定](formatting-types.md)  
- [標準の時間間隔書式指定文字列](standard-timespan-format-strings.md)  
