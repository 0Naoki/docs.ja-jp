---
ms.openlocfilehash: 624814e40c361c30e251a9388f1444734a276c0a
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72315873"
---
# <a name="contributing"></a>コントリビューション

.NET ドキュメントへの貢献に関心をお寄せいただきありがとうございます。

> Microsoft のガイドラインをサイト全体のガイドに移す作業が進行中です。
> 新しいガイダンスを表示するには、「[Microsoft Docs 共同作成者ガイド概要](https://docs.microsoft.com/contribute/)」を参照してください。

このドキュメントでは、[.NET ドキュメント サイト](https://docs.microsoft.com/dotnet)でホストされる記事とコード サンプルを投稿するためのプロセスについて説明します。 投稿には、誤字の修正のような簡単なものから、新しい記事のような複雑なものまであります。

- [投稿のプロセス](#process-for-contributing)
- [C# の対話型エクスペリエンス](#the-c-interactive-experience)
- [注意事項](#dos-and-donts)
- [共同作成者ライセンス条項](#contributor-license-agreement)

このリポジトリには、.NET の概念に関するドキュメントが含まれています。 .NET ドキュメント サイトは、このリポジトリに加え、次の複数のリポジトリで構築されています。

- [コード サンプルとスニペット](https://github.com/dotnet/samples)  
    このリポジトリの問題とタスクについては、[dotnet/docs/issues](https://github.com/dotnet/docs/issues) で追跡されます。
- [.NET API リファレンス](https://github.com/dotnet/dotnet-api-docs)  
    このリポジトリの問題とタスクについては、[dotnet/dotnet-api-docs/issues](https://github.com/dotnet/dotnet-api-docs/issues) で追跡されます。
- [.NET Compiler Platform SDK リファレンス](https://github.com/dotnet/roslyn-api-docs)  
    このリポジトリの問題とタスクについては、[dotnet/docs/issues](https://github.com/dotnet/docs/issues) で追跡されます。

## <a name="process-for-contributing"></a>投稿のプロセス

[Git と GitHub.com](https://guides.github.com/activities/hello-world/) の基本的な理解が必要です。

**手順 1:** 少しの変更の場合 (たとえば、入力ミスを修正する場合や、すぐに pull request を開いてドキュメント内に見つけた問題に対処する場合) は、この手順をスキップします。 新しいコンテンツを書き込んだり、既存のコンテンツを完全に改訂したりすることに興味がある場合は、自分が何をしたいかを説明する[問題](https://github.com/dotnet/docs/issues)を開きます。
*docs* フォルダーのコンテンツはセクションで構成され、それらが目次 (TOC) に反映されます。 TOC のどこにトピックを配置するかを明確にします。 提案に対するフィードバックを得ます。

または

コミュニティへの投稿が歓迎されている既存の問題から選択することもできます。 [Projects for .NET Community contributors](https://github.com/dotnet/docs/projects/35) (.NET コミュニティへの投稿者向けのプロジェクト) に、コミュニティへの投稿者が利用できる多くの作業項目が一覧で示されています。 自分の興味と責任のレベルに応じて、次のカテゴリに属する問題から選択できます。

- **メンテナンス**。 このカテゴリには、リンク切れや間違っているリンクの修正、不足しているコード例の追加、限定されたコンテンツの問題への対応などの非常に単純な投稿が含まれています。 場合によっては、これらの問題に多数のファイルが関係していることがあります。 その場合は、開始する前にご自分が何に取り組みたいかを Microsoft にお知らせください。

- **コンテンツの更新**。 このドキュメント セットは非常に大きいものであるため、コンテンツが簡単が古くなったり改訂が必要になったりします。 さらに、さまざまな理由で、一部のコンテンツでは、同じものが重複していたり、3 つも存在したりしています。 コンテンツの更新では、機能領域の中で個々のトピックが最新のものであるかコンテンツの改訂であるかを明らかにすることで重複を回避し、すべての一意のコンテンツがより小さなドキュメント セット内に保持されるようにする必要があります。

- **新しいコンテンツの作成**。 ご自分で独自のトピックを作成することに興味がある場合は、Microsoft がドキュメント セットに追加したいと思っているトピックが問題の一覧に示されています。 ただし、トピックに取り掛かる前に Microsoft にお知らせください。 ここに記載されていないトピックを記述することに関心がある場合は、問題を開いてください。

[未解決の問題](https://github.com/dotnet/docs/issues)の一覧を調べて、ご自分が興味のある問題に取り組むことを志願することもできます。 投稿できる問題には、[up-for-grabs](https://github.com/dotnet/docs/labels/up-for-grabs) ラベルがタグ付けされています。 

**手順 2:** 必要に応じて、`dotnet/docs`、`dotnet/samples`、または `dotnet/dotnet-api-docs` リポジトリをフォークして、変更を行うためのブランチを作成します。

小さな変更の場合は、GitHub の Web インターフェイスを使用できます。 変更したいファイルの **[Edit the file in your fork of this project]** (このプロジェクトの自分のフォーク内でこのファイルを編集する) をクリックするだけです。 変更を送信すると、GitHub によって、専用の新しいブランチが作成されます。

**手順 3:** この新しいブランチで変更を行います。

新しいトピックの場合は、この[テンプレート ファイル](./styleguide/template.md)を開始点として使用できます。 このファイルには、作成のガイドラインが含まれ、作成者情報など、記事ごとに必要なメタデータについても説明されています。

手順 1 で、ご自分の記事について特定した TOC の場所に対応するフォルダーに移動します。
そのフォルダーには、そのセクション内のすべての記事のマークダウン ファイルが格納されています。
必要に応じて、ご自分のコンテンツ用のファイルを格納する新しいフォルダーを作成します。 そのセクションのメインの記事は *index.md* と呼ばれます。
画像とその他の静的なリソース用に、記事を含むフォルダー内に *media* という名前のサブフォルダーを作成します (まだ存在していない場合)。 *media* フォルダーの中に、記事の名前のサブフォルダーを作成します (インデックス ファイル以外)。
リポジトリのルートの下の *samples* フォルダー内に、大きなサイズのサンプルを含めます。

適切なマークダウン構文に従ってください。 詳細については、[スタイル ガイド](./styleguide/template.md)を参照してください。

### <a name="example-structure"></a>構造の例

```
docs
  /about
  /core
    /porting
      porting-overview.md
      /media
        /porting-overview
            portability_report.png
```

**手順 4:** ご自分のブランチから `dotnet/docs/master`、`dotnet/dotnet-api-docs/master`、または `dotnet/samples/master` に Pull Request (PR) を送信します。

PR は*常に*マスター ブランチを対象にする必要があります。 ライブ ブランチを対象とする PR は*決して*開かないでください。

各 PR では、通常は一度に 1 つの問題に対応します。 PR では、1 つまたは複数のファイルを変更できます。 複数のファイルで複数の修正を行う場合は、PR を分けることが推奨されています。

PR で既存の問題に対応する場合は、コミット メッセージまたは PR の説明に `Fixes #Issue_Number` キーワードを追加してください。 これにより、PR がマージされるときに、問題が自動的に閉じられます。 詳細については、[コミット メッセージによって問題を閉じる](https://help.github.com/articles/closing-issues-via-commit-messages/)方法についての記事を参照してください。

.NET チームが PR を確認し、変更を承認するために必要な他の更新や変更があるかどうかをお知らせします。

**手順 5:** チームによって説明されたとおりに、ご自分のブランチに必要な更新を加えます。

フィードバックが適用され、変更が承認されると、保守管理者によって、PR がマスター ブランチにマージされます。

特定の周期で、マスター ブランチのすべてのコミットがライブ ブランチにプッシュされるので、 https://docs.microsoft.com/dotnet/ でライブでご自分の投稿を確認できます。

### <a name="contributing-to-samples"></a>サンプルへの投稿

Microsoft では、リポジトリ内に存在するコードを次のように区別しています。

- サンプル: 閲覧者は、サンプルをダウンロードして、実行できます。 すべてのサンプルは、完全なアプリケーションまたはライブラリである必要があります。 サンプルでライブラリが作成される場合は、単体テストまたは閲覧者がコードを実行できるアプリケーションが含まれている必要があります。

- スニペット: は、小規模な概念やタスクを示します。 コンパイルされますが、完全なアプリケーションであることを意図するものではありません。

コードはすべて [dotnet/samples](https://github.com/dotnet/samples) リポジトリ内に存在します。 Microsoft では、samples フォルダーの構造と docs フォルダーの構造が一致しているモデルを目指して努力しています。 従っている基準は次のとおりです。

- 最上位の *snippets* フォルダーには、焦点を絞った小さなサンプル用のスニペットが含まれます。
- API リファレンス サンプルは、*snippets/\<言語>/api/\<名前空間>/\<アプリ名>* というパターンのフォルダーに格納されています。
- その他の最上位フォルダーは、*docs* リポジトリ内の最上位フォルダーと一致します。 たとえば、docs リポジトリには *machine-learning/tutorials* フォルダーがあり、*samples/machine-learning/tutorials* フォルダーには機械学習のチュートリアル用のサンプルが含まれます。

さらに、*core* フォルダーと *standard* フォルダーの下のすべてのサンプルは、NET Core によってサポートされているすべてのプラットフォーム上でビルドされ、実行される必要があります。 CI ビルド システムにはそれが適用されます。 最上位の *framework* フォルダーには、Windows 上でのみビルドされ、検証されたサンプルが含まれます。

これらのディレクトリは、docs リポジトリに新しいコンテンツが追加されたときに拡張される可能性があります。 たとえば、`xamarin-ios` や `xamarin-android` などの Xamarin ディレクトリが追加されます。

ご自分で作成した完全なサンプルには、*readme.md* ファイルを含める必要があります。 このファイルには、サンプルの簡単な説明 (1 つまたは 2 つの段落) を含める必要があります。 *Readme.md* で、このサンプルを探索することで何を学習できるかを閲覧者に通知する必要があります。 *Readme.md* ファイルには、[.NET ドキュメント サイト](https://docs.microsoft.com/dotnet/welcome)上に公開されているドキュメントへのリンクも含める必要があります。
リポジトリ内の特定のファイルをそのサイトのどこにマップするかを判断するには、リポジトリ パスの `/docs` を `https://docs.microsoft.com/dotnet` に置き換えます。

ご自分のトピックには、サンプルへのリンクも含まれます。 GitHub 上のサンプルのフォルダーに直接リンクしてください。

詳細については、[サンプルの Readme](https://github.com/dotnet/samples/blob/master/README.md) を参照してください。

## <a name="the-c-interactive-experience"></a>C# の対話型エクスペリエンス

C# で記述された短いサンプル コードでは、`csharp-interactive` 言語タグを使用して、ブラウザーで実行される C# のサンプルを指定できます (インライン コード サンプルでは `csharp-interactive` タグを使用し、ソースから含まれるスニペットでは `code-csharp-interactive` タグを使用します)。これらのコード サンプルでは、記事内の コード ウィンドウと出力ウィンドウが表示されます。 ユーザーがサンプルを実行すると、対話型コードの実行による出力が出力ウィンドウに表示されます。 

C# の対話型エクスペリエンスでは、サンプルの操作方法が変わります。 訪問者は、サンプルを実行して結果を確認できます。 サンプルまたは対応するテキストに出力に関する情報を含める必要があるかどうかを判断するために役立つさまざまな要素があります。

### <a name="when-to-display-the-expected-output-without-running-the-sample"></a>期待される出力をサンプルの実行なしで表示する状況

- 初心者向けの記事では、出力を提供して、閲覧者が期待される応答と自分の作業の出力を比較できるようにする必要があります。
- サンプルの出力がトピックに不可欠である場合は、その出力を表示する必要があります。 たとえば、書式設定されたテキストに関する記事では、サンプルの実行なしでテキストの書式を示す必要があります。
- サンプルと予想される出力の両方が短い場合は、出力を表示することを検討してください。 それによって、少し時間を節約できます。
- 現在のカルチャまたはインバリアント カルチャが出力にどのように影響するかを説明する記事では、予想される出力を説明する必要があります。 Linux ベースのホスト上では、対話型 REPL (Read Evaluate Print Loop) が実行されます。 既定のカルチャとインバリアント カルチャでは、オペレーティング システムが異なるコンピューター上では生成される出力が異なります。 Windows、Linux、および Mac の各システム上での出力を、記事で説明する必要があります。

### <a name="when-to-exclude-expected-output-from-the-sample"></a>予想される出力をサンプルから除外する状況 

- サンプルを実行すると大量の出力が生成される記事では、出力をコメントに含める必要はありません。 サンプルが実行されると、コードがわかりにくくなります。
- トピックの実例をサンプルで示す記事で、記事を理解するために出力が不可欠ではない場合があります。 例として、クエリの構文を説明するために LINQ クエリを実行するコードで、実行すると出力コレクション内のすべての項目が表示されるコードがあります。

## <a name="dos-and-donts"></a>注意事項

次の一覧に、.NET ドキュメントに投稿する際に注意する必要があるいくつかのガイド ルールを示します。

- 巨大な pull request を送信**しないでください**。 代わりに、問題を提出し、ディスカッションを開始して、大量の時間を費やす前に方向について同意が得られるようにしてください。
- [スタイル ガイド](./styleguide/template.md)と[スタイルとトーン](./styleguide/voice-tone.md)のガイドラインを**お読みください**。
- [テンプレート](./styleguide/template.md) ファイルを作業の開始点として**使用してください**。
- 記事に取り掛かる前に、フォークに個別のブランチを**作成してください**。
- [GitHub フロー ワークフロー](https://guides.github.com/introduction/flow/)に**従ってください**。
- 投稿について頻繁にブログやツイート**を書いてください**。

> 注: 現在、一部のトピックでは、この記事や[スタイル ガイド](./styleguide/template.md)に指定されたすべてのガイドラインに従っていないことに気付く場合があります。 Microsoft では、サイト全体で一貫性の達成に向けて取り組んでいます。 その特定の目標に向けて現在追跡中の[未解決の問題](https://github.com/dotnet/docs/issues?q=is%3Aissue+is%3Aopen+label%3Aguidelines-adherence)の一覧をご確認ください。

## <a name="contributor-license-agreement"></a>貢献者使用許諾契約書

ご自分の PR がマージされる前に、[.NET Foundation 貢献者使用許諾契約書 (CLA)](https://cla.dotnetfoundation.org) に署名する必要があります。 これは、.NET Foundation 内のプロジェクトに対して 1 回だけ実行する必要があります。 [貢献者使用許諾契約書 (CLA)](https://en.wikipedia.org/wiki/Contributor_License_Agreement) について詳しくは、Wikipedia を参照してください。

契約書: [net-foundation-contribution-license-agreement.pdf](https://github.com/dotnet/home/blob/master/guidance/net-foundation-contribution-license-agreement.pdf)

前もって契約に署名する必要はありません。 PR は通常どおり、複製、フォーク、送信できます。 PR が作成されると、CLA ボットで分類されます。 変更が軽微である (入力ミスの修正など) 場合、PR には `cla-not-required` ラベルが付けられます。 それ以外の場合は、`cla-required` に分類されます。 ご自分が CLA に署名した後、現在以降のすべての pull request には `cla-signed` ラベルが付けられます。
