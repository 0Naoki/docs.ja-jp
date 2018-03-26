---
title: .NET Framework の新機能
ms.custom: updateeachrelease
ms.date: 05/02/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- what's new [.NET Framework]
ms.assetid: 1d971dd7-10fc-4692-8dac-30ca308fc0fa
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 04696ff346ffab438ce8bef2974fdd1a19d940af
ms.sourcegitcommit: c883637b41ee028786edceece4fa872939d2e64c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2018
---
# <a name="whats-new-in-the-net-framework"></a>.NET Framework の新機能
<a name="introduction"></a> この記事では、.NET Framework の次のバージョンにおける主な新機能と機能強化の概要を示します。  
 
[.NET Framework 4.7.1](#v471)    
[.NET Framework 4.7](#v47)   
[.NET Framework 4.6.2](#v462)   
[.NET Framework 4.6.1](#v461)   
[.NET 2015 と .NET Framework 4.6](#v46)   
[.NET Framework 4.5.2](#v452)   
[.NET Framework 4.5.1](#v451)   
[.NET Framework 4.5](#v45)   

この記事は、各新機能の包括的な情報を説明するものではありません。また、この内容は変更される可能性があります。 .NET Framework の概要については、「[.NET Framework の概要](../../../docs/framework/get-started/index.md)」をご覧ください。 サポートされているプラットフォームについては、「[.NET Framework システム要件](~/docs/framework/get-started/system-requirements.md)」を参照してください。 ダウンロード リンクとインストール手順については、「[.NET Framework のインストール](../../../docs/framework/install/guide-for-developers.md)」を参照してください。

> [!NOTE]
> また .NET Framework チームは、NuGet により OOB 機能をリリースすることによって、プラットフォーム サポートを拡張し、新しい機能 (変更できないコレクションや SIMD 対応ベクター型など) を提供しています。 詳細については、「[その他のクラス ライブラリと API](../additional-apis/index.md)」および[.NET Framework と OOB リリース](~/docs/framework/get-started/the-net-framework-and-out-of-band-releases.md)に関するページを参照してください。 .NET Framework 用の [NuGet パッケージの完全な一覧](https://blogs.msdn.microsoft.com/dotnet/p/nugetpackages/)をご確認いただくか、[Microsoft のフィード](https://nuget.org/api/v2/curated-feeds/dotnetframework/Packages/)をサブスクライブしてください。

<a name="v471"></a> 
## <a name="introducing-the-net-framework-471"></a>.NET Framework 4.7.1 の概要

.NET Framework 4.7.1 は、.NET Framework 4.6、4.6.1、4.6.2、4.7 を基に、多数の新しい修正といくつかの新機能を追加したものであり、これまでと同様に非常に安定した製品です。

### <a name="downloading-and-installing-the-net-framework-471"></a>.NET Framework 4.7.1 のダウンロードとインストール
 
.NET Framework 4.7.1 は、次の場所からダウンロードできます。

- [.NET Framework 4.7.1 の Web インストーラー](http://go.microsoft.com/fwlink/?LinkId=852095)

- [.NET Framework 4.7.1 のオフライン インストーラー](http://go.microsoft.com/fwlink/?LinkId=852107)

.NET Framework 4.7.1 は、Windows 10、Windows 8.1、Windows 7 SP1、および Windows Server 2008 R2 SP1 以降に相当するサーバー プラットフォームにインストールできます。 .NET Framework 4.7.1 は、Web インストーラーまたはオフライン インストーラーを使用してインストールできます。 ほとんどのユーザーにお勧めする方法は、Web インストーラーの使用です。

[.NET Framework 4.7.1 Developer Pack](http://go.microsoft.com/fwlink/?LinkId=852105) をインストールすれば、Visual Studio 2012 以降で、.NET Framework 4.7.1 をインストール対象に設定できます。 

### <a name="whats-new-in-the-net-framework-471"></a>.NET Framework 4.7.1 の新機能

.NET Framework 4.7.1 には、次の領域における新機能が含まれています。
 
- [コア](#core471)
- [共通言語ランタイム (CLR)](#clr)
- [ネットワーク](#net471)
- [ASP.NET](#asp-net471) 

さらに、.NET Framework 4.7.1 ではアクセシビリティ機能が向上し、支援技術のユーザーに適切なエクスペリエンスを提供できます。 .NET Framework 4.7.1 のアクセシビリティ機能の改善の詳細については、「[What's new in accessibility in the .NET Framework](whats-new-in-accessibility.md)」 (.NET Framework のアクセシビリティの新機能) を参照してください。 

<a name="core471" />
#### <a name="core"></a>コア

**.NET Standard 2.0 のサポート**

[.NET Standard](~/docs/standard/net-standard.md) は、そのバージョンの標準をサポートする各 .NET 実装で使用する必要がある API のセットを定義します。 .NET Framework 4.7.1 は、.NET Standard 2.0 を完全にサポートし、.NET Standard 2.0 で定義され、.NET Framework 4.6.1、4.6.2、および 4.7 にはなかった[約 200 の API](https://github.com/dotnet/standard/blob/master/netstandard/src/ApiCompatBaseline.net461.txt) を追加します  (これらのバージョンの .NET Framework は、追加の .NET Standard サポート ファイルもターゲット システムにも展開されている場合にのみ .NET Standard 2.0 をサポートします)。詳細については、「[.NET Framework 4.7.1 Runtime and Compiler Features](https://blogs.msdn.microsoft.com/dotnet/2017/09/28/net-framework-4-7-1-runtime-and-compiler-features)」(.NET Framework 4.7.1 ランタイムとコンパイラの機能) ブログ投稿の「BCL - .NET Standard 2.0 Support」(BCL - .NET Standard 2.0 のサポート) を参照してください。

**構成ビルダーのサポート**

構成ビルダーを使用して、開発者が、実行時にアプリケーションの構成設定を動的に注入およびビルドすることができます。 カスタム構成ビルダーを使用して、構成セクションの既存のデータを変更したり、最初から完全に構成セクション全体をビルドしたりすることができます。 構成ビルダーを使用しない場合は、構成ファイルは静的であり、それらの設定はアプリケーションが起動されるしばらく前に定義されます。

カスタム構成ビルダーを作成するには、抽象 <xref:System.Configuration.ConfigurationBuilder> クラスからビルダーを派生させ、その <xref:System.Configuration.ConfigurationBuilder.ProcessConfigurationSection%2A?displayProperty=nameWithType> と <xref:System.Configuration.ConfigurationBuilder.ProcessRawXml%2A?displayProperty=nameWithType> をオーバーライドします。 また、.config ファイルでもビルダーを定義します。 詳細については、「[.NET Framework 4.7.1 ASP.NET and Configuration Features](https://blogs.msdn.microsoft.com/dotnet/2017/09/13/net-framework-4-7-1-asp-net-and-configuration-features) 」(.NET Framework 4.7.1 ASP.NET と構成機能) ブログ投稿の「Configuration Builders」(構成ビルダー) セクションを参照してください。 

**実行時の機能の検出**

<xref:System.Runtime.CompilerServices.RuntimeFeature?displayProperty=nameWithType> クラスは、コンパイル時または実行時に特定の .NET の実装上で事前に定義された機能がサポートされているかどうかを判断するためのメカニズムを提供します。 コンパイラは、コンパイル時に、指定されたフィールドが存在するかどうかを確認し、その機能がサポートされているかどうかを判断します。サポートされている場合は、その機能を利用するコードを生成できます。 実行時に、アプリケーションは、コードを生成する前に <xref:System.Runtime.CompilerServices.RuntimeFeature.IsSupported%2A?displayProperty=nameWithType> メソッドを呼び出すことができます。 詳細については、「[Add helper method to describe features supported by the runtime](https://github.com/dotnet/corefx/issues/17116)」(ランタイムでサポートされる機能を記述するヘルパー メソッドを追加する) を参照してください。

**値のタプル型はシリアル化できる**

.NET Framework 4.7.1 以降、<xref:System.ValueTuple?displayProperty=nameWithType> および関連するジェネリック型は、[Serializable](xref:System.SerializableAttribute) としてマークされ、バイナリのシリアル化ができるようになりました。 これにより、<xref:System.Tuple%603> や <xref:System.Tuple%604> などのタプル型を簡単に値のタプル型に移行できます。 詳細については、「[.NET Framework 4.7.1 Runtime and Compiler Features](https://blogs.msdn.microsoft.com/dotnet/2017/09/28/net-framework-4-7-1-runtime-and-compiler-features)」(.NET Framework 4.7.1 ランタイムとコンパイラの機能) ブログ投稿の「Compiler -- ValueTuple is Serializable」(コンパイラ -- 値タプルはシリアル化できる) を参照してください。

**読み取り専用の参照のサポート**

.NET Framework 4.7.1 では、<xref:System.Runtime.CompilerServices.IsReadOnlyAttribute?displayProperty=nameWithType> が追加されました。 この属性は、読み取り専用の ref 戻り値型またはパラメーターを持つメンバーをマークする言語コンパイラで使用します。 詳細については、「[.NET Framework 4.7.1 Runtime and Compiler Features](https://blogs.msdn.microsoft.com/dotnet/2017/09/28/net-framework-4-7-1-runtime-and-compiler-features)」(.NET Framework 4.7.1 ランタイムとコンパイラの機能) ブログ投稿の「Compiler - Support for ReadOnlyReferences」(コンパイラ - ReadOnlyReferences のサポート) を参照してください。 Ref 戻り値の詳細については、「[Ref return values and ref locals (C# Guide)](~/docs/csharp/programming-guide/classes-and-structs/ref-returns.md)」(Ref 戻り値と ref ローカル変数 (c# ガイド)) および「[Ref return values (Visual Basic)](../../visual-basic/programming-guide/language-features/procedures/ref-return-values.md)」(Ref 戻り値 (Visual Basic)) を参照してください。

<a name="clr" />
#### <a name="common-language-runtime-clr"></a>共通言語ランタイム (CLR)

**ガベージ コレクションのパフォーマンス改善**

.NET Framework 4.7.1 のガベージ コレクション (GC) への変更は、特に大きなオブジェクト ヒープ (LOH) の割り当ての場合の全体的なパフォーマンスを向上させます。 .NET Framework 4.7.1 では、小さなオブジェクト ヒープ (SOH) と LOH の割り当てに個別のロックを使用します。これにより、バックグラウンドの GC (BGC) が SOH をスイープするときに LOH の割り当てが許可されます。 その結果、多数の LOH の割り当てを行うアプリケーションでは、割り当てのロックの競合が減少し、パフォーマンスが向上します。 詳細については、「[.NET Framework 4.7.1 Runtime and Compiler Features](https://blogs.msdn.microsoft.com/dotnet/2017/09/28/net-framework-4-7-1-runtime-and-compiler-features/)」(.NET Framework 4.7.1 ランタイムとコンパイラの機能) ブログ投稿の「Runtime -- GC Performance Improvements」(ランタイム - GC のパフォーマンスの向上) セクションを参照してください。 

<a name="net471"/>
#### <a name="networking"></a>ネットワーキング

**Message.HashAlgorithm 用の SHA-2 のサポート**

.NET Framework 4.7 およびそれ以前のバージョンでは、<xref:System.Messaging.Message.HashAlgorithm%2A?displayProperty=nameWithType> プロパティは値 <xref:System.Messaging.HashAlgorithm.Md5?displayProperty=nameWithType> および <xref:System.Messaging.HashAlgorithm.Sha?displayProperty=nameWithType> のみをサポートしていました。 .NET Framework 4.7.1 以降では、<xref:System.Messaging.HashAlgorithm.Sha256?displayProperty=nameWithType>、<xref:System.Messaging.HashAlgorithm.Sha384?displayProperty=nameWithType>、<xref:System.Messaging.HashAlgorithm.Sha512?displayProperty=nameWithType> もサポートされます。 <xref:System.Messaging.Message> インスタンス自体は、ハッシュは行わず、MSMQ に値を渡すだけですなので、この値が実際に使用されるかどうかは MSMQ によって異なります。 詳細については、「[.NET Framework 4.7.1 ASP.NET and Configuration Features](https://blogs.msdn.microsoft.com/dotnet/2017/09/13/net-framework-4-7-1-asp-net-and-configuration-features/) 」(.NET Framework 4.7.1 ASP.NET と構成機能) ブログ投稿の「SHA-2 support for Message.HashAlgorithm」(Message.HashAlgorithm 用の SHA-2 のサポート) セクションを参照してください。

<a name="asp-net471" />
#### <a name="aspnet"></a>ASP.NET

**ASP.NET アプリケーションの実行ステップ**

ASP.NET は、23 のイベントを含む定義済みのパイプラインで要求を処理します。 ASP.NET は、実行ステップとして、各イベント ハンドラーを実行します。 バージョンの .NET Framework 4.7 までの ASP.NET のバージョンでは、ASP.NET は、ネイティブ スレッドとマネージ スレッドの切り替えのために、実行コンテキストをフローすることはできません。 代わりに、ASP.NET は、<xref:System.Web.HttpContext> のみを選択的にフローします。 .NET Framework 4.7.1 以降、<xref:System.Web.HttpApplication.OnExecuteRequestStep(System.Action{System.Web.HttpContextBase,System.Action})?displayProperty=nameWithType> メソッドでは、モジュールがアンビエント データを復元することもできます。 この機能は、アプリケーションの実行フローを考慮する、トレース、プロファイリング、診断、トランザクションなどに関連するライブラリを対象とします。 詳細については、「[.NET Framework 4.7.1 ASP.NET and Configuration Features](https://blogs.msdn.microsoft.com/dotnet/2017/09/13/net-framework-4-7-1-asp-net-and-configuration-features) 」(.NET Framework 4.7.1 ASP.NET と構成機能) ブログ投稿の「ASP.NET Execution Step Feature」(ASP.NET 実行ステップの機能) を参照してください。 

**ASP.NET HttpCookie 解析**

.NET Framework 4.7.1 には、新しいメソッド <xref:System.Web.HttpCookie.TryParse%2A?displayProperty=nameWithType> が含まれています。これは、文字列から <xref:System.Web.HttpCookie> オブジェクトを作成し、有効期限日やパスなどの cookie の値を正確に割り当てるための標準化された方法を提供します。 詳細については、「[.NET Framework 4.7.1 ASP.NET and Configuration Features](https://blogs.msdn.microsoft.com/dotnet/2017/09/13/net-framework-4-7-1-asp-net-and-configuration-features) 」(.NET Framework 4.7.1 ASP.NET と構成機能) ブログ投稿の「ASP.NET HttpCookie parsing」(ASP.NET HttpCookie の解析) を参照してください。 

**ASP.NET フォーム認証資格情報の SHA-2 ハッシュ オプション**

.NET Framework 4.7 およびそれ以前のバージョンでは、ASP.NET を使用して開発者が、MD5 または SHA1 を使用し、構成ファイルにハッシュされたパスワードを含むユーザーの資格情報を格納することができました。 .NET Framework 4.7.1 以降では、ASP.NET はまた、SHA256、SHA384、SHA512 などの新しい安全な SHA-2 ハッシュ オプションもサポートします。 SHA1 は既定のまま残り、Web 構成ファイルで既定以外のハッシュ アルゴリズムを定義することができます。 例:

```xml
<system.web>
    <authentication mode="Forms">
        <forms loginUrl="~/login.aspx">
          <credentials passwordFormat="SHA512">
            <user name="jdoe" password="6D003E98EA1C7F04ABF8FCB375388907B7F3EE06F278DB966BE960E7CBBD103DF30CA6D61F7E7FD981B2E4E3A64D43C836A4BEDCA165C33B163E6BCDC538A664" />
          </credentials>
        </forms>
    </authentication>
</system.web>
```

<a name="v47"></a> 
### <a name="whats-new-in-the-net-framework-47"></a>.NET Framework 4.7 の新機能

.NET Framework 4.7 には、次の領域における新機能が含まれています。

- [コア](#Core47)
- [ネットワーク](#net47)
- [ASP.NET](#ASP-NET47)
- [Windows Communication Foundation (WCF)](#wcf47)
- [Windows フォーム](#wf47)
- [Windows Presentation Foundation (WPF)](#WPF47)

.NET Framework 4.7 に追加された新しい API の一覧については、GitHub で [.NET Framework 4.7 API の変更点](https://github.com/Microsoft/dotnet/blob/master/releases/net47/dotnet47-api-changes.md)に関するページをご覧ください。 .NET Framework 4.7 における機能の改善とバグ修正の一覧については、GitHub で [.NET Framework 4.7 の変更点](http://github.com/Microsoft/dotnet/blob/master/releases/net47/dotnet47-changes.md)に関するページをご覧ください。  詳細については、.NET Blog の「[Announcing the .NET Framework 4.7 (.NET Framework 4.7 の発表)](https://blogs.msdn.microsoft.com/dotnet/2017/04/05/announcing-the-net-framework-4-7/)」をご覧ください。

<a name="Core47" />
#### <a name="core"></a>コア

.NET Framework 4.7 で、<xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> によるシリアル化が改善されます。

**楕円曲線暗号 (ECC) による機能強化***

.NET Framework 4.7 では、`ImportParameters(ECParameters)` メソッドが <xref:System.Security.Cryptography.ECDsa> クラスと <xref:System.Security.Cryptography.ECDiffieHellman> クラスに追加され、既に確立されたキーをオブジェクトで表すことができるようになりました。 明示的な曲線パラメーターを使ってキーをエクスポートするための `ExportParameters(Boolean)` メソッドも追加されました。

また、.NET Framework 4.7 は、その他の曲線 (Brainpool 曲線スイートなど) のサポートと、新しい <xref:System.Security.Cryptography.ECDsa.Create%2A> および <xref:System.Security.Cryptography.ECDiffieHellman.Create%2A> ファクトリ メソッドによる作成しやすい事前定義も追加されました。

GitHub で [.NET Framework 4.7 の暗号化の向上の例](https://gist.github.com/richlander/5a182899895a87a296c21ada97f7a54e)を見ることができます。

**DataContractJsonSerializer による制御文字のサポートの向上**

.NET Framework 4.7 の <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> では、ECMAScript 6 標準に準拠して制御文字をシリアル化します。 この動作は、.NET Framework 4.7 を対象とするアプリケーションでは既定で有効になり、.NET Framework 4.7 で実行していても対象は以前のバージョンの .NET Framework であるアプリケーションの場合はオプトイン機能です。 詳細については、「[.NET Framework 4.7 における再ターゲットの変更点](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-7.md)」をご覧ください。

<a name="net47" />
#### <a name="networking"></a>ネットワーキング

.NET Framework 4.7 では、次のネットワーク関連機能が追加されています。

**TLS プロトコルの既定のオペレーティング システム サポート***

<xref:System.Net.Security.SslStream?displayProperty=nameWithType> および HTTP、FTP、SMTP などの上位スタック コンポーネントによって使われる TLS スタックにより、開発者はオペレーティング システムによってサポートされる既定の TLS プロトコルを使うことができます。 TLS バージョンをハード コーディングする必要はなくなりました。

<a name="ASP-NET47" />
#### <a name="aspnet"></a>ASP.NET

.NET Framework 4.7 の ASP.NET には、次の新機能が含まれます。

**オブジェクト キャッシュの拡張性**

.NET Framework 4.7 以降では、ASP.NET で追加された新しい API セットを使うことで、開発者は、メモリ内オブジェクト キャッシュとメモリ監視に関する既定の ASP.NET の実装を置き換えることができます。 ASP.NET の実装が適切ではない場合、次の 3 つのコンポーネントを置き換えることができるようになりました。

- **オブジェクト キャッシュ ストア**。 新しいキャッシュ プロバイダー構成セクションを使うことで、開発者は、新しい **ICacheStoreProvider** インターフェイスを使って、ASP.NET アプリケーション用のオブジェクト キャッシュの新しい実装をプラグインできます。
 
- **メモリ監視**。 ASP.NET の既定のメモリ モニターは、アプリケーションがプロセスに構成されているプライベート バイト制限に近づくと、またはコンピューターの使用可能な合計物理 RAM が低下すると、アプリケーションに通知します。 これらの制限に近づくと、通知が発生します。 一部のアプリケーションでは、通知の発生が構成されている制限に近すぎるため、有効な対応を取れません。 開発者は、<xref:System.Web.Hosting.ApplicationMonitors.MemoryMonitor%2A?displayProperty=nameWithType> プロパティを使用して既定値を置き換える独自のメモリ モニターを作成できるようになりました。

- **メモリ制限への対応**。 既定では、プライベート バイト プロセス制限が近づくと、ASP.NET はオブジェクト キャッシュの削減を試み、<xref:System.GC.Collect%2A?displayProperty=nameWithType> を定期的に呼び出します。 アプリケーションによっては、<xref:System.GC.Collect%2A?displayProperty=nameWithType> の呼び出し頻度またはトリミングされるキャッシュ量が非効率になります。 開発者は、アプリケーションのメモリ モニターに **IObserver** の実装をサブスクライブすることにより、既定の動作を置換または補完できます。

<a name="wcf47" />
#### <a name="windows-communication-foundation-wcf"></a>Windows Communication Foundation (WCF)

Windows Communication Foundation (WCF) では以下の機能が追加または変更されました。

**既定のメッセージ セキュリティ設定を TLS1.1 または TLS1.2 に構成する機能。**

.NET Framework 4.7 以降の WCF では、既定のメッセージ セキュリティ プロトコルとして、SSL 3.0 と TSL 1.0 に加えて、TSL 1.1 または TLS 1.2 を構成できます。 これはオプトイン設定です。有効にするには、アプリケーション構成ファイルに次のエントリを追加する必要があります。

```xml
<runtime>
   <AppContextSwitchOverrides value="Switch.System.ServiceModel.DisableUsingServicePointManagerSecurityProtocols=false;Switch.System.Net.DontEnableSchUseStrongCrypto=false" /> 
</runtime>
```

**WCF アプリケーションと WCF シリアル化の信頼性の向上**

WCF に競合状態を除去する複数のコード変更が追加され、シリアル化オプションの信頼性とパフォーマンスが向上しています。 次の設定があります。

- **SocketConnection.BeginRead** および **SocketConnection.Read** の呼び出しでの非同期コードと同期コードの併用のサポートの向上。
- **SharedConnectionListener** および **DuplexChannelBinder** で接続を中止するときの信頼性の向上。
- <xref:System.Runtime.Serialization.FormatterServices.GetSerializableMembers%28System.Type%29?displayProperty=nameWithType> メソッドの呼び出し時のシリアル化操作の信頼性を向上しました。
- **ChannelSynchronizer.RemoveWaiter** メソッドを呼び出して待機を削除するときの信頼性の向上。

<a name="wf47" />
#### <a name="windows-forms"></a>Windows フォーム

.NET Framework 4.7 では、Windows フォームによる高 DPI モニターのサポートが向上しました。

**高 DPI のサポート**

.NET Framework 4.7 を対象とするアプリケーションでは、Windows フォーム アプリケーションに対して高 DPI および動的 DPI がサポートされるようになっています。 高 DPI のサポートにより、フォームのレイアウトと外観および高 DPI モニターでのコントロールが向上します。 動的 DPI は、ユーザーが実行中のアプリケーションの DPI または表示倍率を変更すると、フォームのレイアウトと外観およびコントロールを変更します。

高 DPI のサポートはオプトイン機能であり、アプリケーション構成ファイルの [\<System.Windows.Forms.ConfigurationSection>](../configure-apps/file-schema/winforms/index.md) セクションを定義することで構成します。 Windows フォーム アプリケーションへの高 DPI サポートおよび動的 DPI サポート追加の詳細については、「[Windows フォームの高 DPI サポート](../winforms/high-dpi-support-in-windows-forms.md)」をご覧ください。

<a name="WPF47"></a> 
#### <a name="windows-presentation-foundation-wpf"></a>Windows Presentation Foundation (WPF)

.NET Framework 4.7 では、WPF の機能が次のように強化されています。

**Windows WM_POINTER メッセージに基づくタッチ/スタイラス スタックのサポート**

Windows Ink Services Platform (WISP) の代わりに [WM_POINTER メッセージ](https://msdn.microsoft.com/library/windows/desktop/hh454903.aspx)に基づいてタッチ/スタイラス スタックを使うオプションが追加されました。 これは、.NET Framework のオプトイン機能です。 詳細については、「[.NET Framework 4.7 における再ターゲットの変更点](../migration-guide/retargeting-changes-in-the-net-framework-4-7.md)」をご覧ください。

**WPF 印刷 API の新しい実装**

<xref:System.Printing.PrintQueue?displayProperty=nameWithType> クラスの WPF 印刷 API は、非推奨になった [XPS 印刷 API](https://msdn.microsoft.com/library/windows/desktop/ff686814(v=vs.85).aspx) ではなく Windows [ドキュメント印刷パッケージ API](https://msdn.microsoft.com/library/windows/desktop/hh448418(v=vs.85).aspx) を呼び出します。 アプリケーションの互換性に対するこの変更の影響については、「[.NET Framework 4.7 における再ターゲットの変更点](../migration-guide/retargeting-changes-in-the-net-framework-4-7.md)」をご覧ください。 

<a name="v462"></a> 
## <a name="whats-new-in-the-net-framework-462"></a>.NET Framework 4.6.2 の新機能

[!INCLUDE[net_v462](../../../includes/net-v462-md.md)] には、次の領域における新機能が含まれています。

- [ASP.NET](#ASPNET462)

- [文字カテゴリ](#Strings)

- [暗号](#Crypto462)

- [SQLClient](#SQLClient)

- [Windows Communication Foundation](#WCF)

- [Windows Presentation Foundation (WPF)](#WPF462)

- [Windows Workflow Foundation (WF)](#WF462)

- [ClickOnce](#ClickOnce)

- [Windows フォームおよび WPF アプリの UWP アプリへの変換](#UWPConvert)

- [デバッグの機能強化](#Debug462)

.NET Framework 4.6.2 に追加された新しい API の一覧については、GitHub で [.NET Framework 4.6.2 API の変更点](https://github.com/Microsoft/dotnet/blob/master/releases/net462/dotnet462-api-changes.md)に関するページを参照してください。 .NET Framework 4.6.2 における機能の改善とバグ修正の一覧については、GitHub で「[.NET Framework 4.6.2 List of Changes (.NET Framework 4.6.2 API の変更点の一覧)](http://go.microsoft.com/fwlink/?LinkId=708778)」を参照してください。  詳細については、.NET Blog の「[Announcing .NET Framework 4.6.2](https://blogs.msdn.microsoft.com/dotnet/2016/08/02/announcing-net-framework-4-6-2/)」(.NET Framework 4.6.2 の発表) を参照してください。

<a name="ASPNET462"></a> 
### <a name="aspnet"></a>ASP.NET
 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] では、ASP.NET の機能が次のように強化されています。

 **データ注釈検証コントロールのローカライズされたエラー メッセージのサポート強化** データ注釈検証コントロールを使用して、1 つ以上の属性をクラス プロパティに追加して検証を行うことができます。 属性の <xref:System.ComponentModel.DataAnnotations.ValidationAttribute.ErrorMessage%2A?displayProperty=nameWithType> 要素は、検証が失敗した場合にエラー メッセージのテキストを定義します。 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] 以降では、ASP.NET でエラー メッセージを簡単にローカライズできます。 エラー メッセージは次のような場合にローカライズされます。

1.  <xref:System.ComponentModel.DataAnnotations.ValidationAttribute.ErrorMessage%2A?displayProperty=nameWithType> が検証属性で指定されている。

2.  リソース ファイルが App_LocalResources フォルダーに格納されている。

3.  ローカライズされたリソース ファイル名の形式が `DataAnnotation.Localization.{`*名前*`}.resx` (この*名前*は、*languageCode*`-`*country/regionCode* または *languageCode* 形式のカルチャ名) である。

4.  リソースのキー名が <xref:System.ComponentModel.DataAnnotations.ValidationAttribute.ErrorMessage%2A?displayProperty=nameWithType> 属性に割り当てられている文字列で、その値がローカライズされたエラー メッセージである。

 たとえば、次のデータ注釈属性では、無効な評価の場合に表示する、既定のカルチャのエラー メッセージを定義します。

```csharp
public class RatingInfo
{
   [Required(ErrorMessage = "The rating must be between 1 and 10.")]
   [Display(Name = "Your Rating")]
   public int Rating { get; set; }
}
```

```vb
Public Class RatingInfo
   <Required(ErrorMessage = "The rating must be between 1 and 10.")>
   <Display(Name = "Your Rating")>
   Public Property Rating As Integer = 1
End Class
```

 キーがエラー メッセージ文字列であり、その値がローカライズされたエラー メッセージであるようにリソース ファイル DataAnnotation.Localization.fr.resx を作成します。 ファイルは `App.LocalResources` フォルダーになければいけません。 たとえば下記は、キーとその値で、値はローカライズされたフランス語 (fr) のエラー メッセージです。

| name                                 | [値]                                     |
| ------------------------------------ | ----------------------------------------- |
| 評価は、1 から 10 の範囲である必要があります。 | La note doit être comprise entre 1 et 10. |

 This file can then

 また、データ注釈ローカリゼーションを拡張することができます。 開発者は、<xref:System.Web.Globalization.IStringLocalizerProvider> インターフェイスを実装してリソース ファイル以外の場所にローカリゼーション文字列を格納することで、独自の文字列ローカライザー プロバイダーにプラグインできます。

 **セッション状態ストア プロバイダーでの非同期サポート** ASP.NET では、セッション状態ストア プロバイダーでタスクを返すメソッドを使用できるようになりました。これにより、ASP.NET アプリで非同期のスケーラビリティのメリットが得られます。 セッション状態ストア プロバイダーでの非同期操作をサポートするために、ASP.NET には新しいインターフェイスである <xref:System.Web.SessionState.ISessionStateModule?displayProperty=nameWithType> が含まれています。これは <xref:System.Web.IHttpModule> から継承され、開発者はこれを使用して独自のセッション状態モジュールと非同期セッション ストア プロバイダーを実装することができます。 このインターフェイスは次のように定義されます。

```csharp
public interface ISessionStateModule : IHttpModule {
    void ReleaseSessionState(HttpContext context);
    Task ReleaseSessionStateAsync(HttpContext context);
}
```

 また、<xref:System.Web.SessionState.SessionStateUtility> クラスには <xref:System.Web.SessionState.SessionStateUtility.IsSessionStateReadOnly%2A> および <xref:System.Web.SessionState.SessionStateUtility.IsSessionStateRequired%2A> という 2 つの新しいメソッドが含まれています。これらを使用して、非同期操作をサポートできます。

 **出力キャッシュ プロバイダーの非同期サポート** [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] 以降では、タスクを返すメソッドを出力キャッシュ プロバイダーで使用して、非同期のスケーラビリティのメリットを得ることができます。  これらのメソッドを実装するプロバイダーは、Web サーバー上のスレッド ブロックを減らし、ASP.NET サービスのスケーラビリティを向上させます。

 非同期出力キャッシュ プロバイダーをサポートするために、次の API が追加されました。

- <xref:System.Web.Caching.OutputCacheProvider?displayProperty=nameWithType> から継承される <xref:System.Web.Caching.OutputCacheProviderAsync?displayProperty=nameWithType> クラス。これにより、開発者は非同期出力キャッシュ プロバイダーを実装できます。

- <xref:System.Web.Caching.OutputCacheUtility> クラス。出力キャッシュを構成するためのヘルパー メソッドを提供します。

- <xref:System.Web.HttpCachePolicy?displayProperty=nameWithType> クラスの新しい 18 個のメソッド。 これらのメソッドには、<xref:System.Web.HttpCachePolicy.GetCacheability%2A>、<xref:System.Web.HttpCachePolicy.GetCacheExtensions%2A>、<xref:System.Web.HttpCachePolicy.GetETag%2A>、<xref:System.Web.HttpCachePolicy.GetETagFromFileDependencies%2A>、<xref:System.Web.HttpCachePolicy.GetMaxAge%2A>、<xref:System.Web.HttpCachePolicy.GetMaxAge%2A>、<xref:System.Web.HttpCachePolicy.GetNoStore%2A>、<xref:System.Web.HttpCachePolicy.GetNoTransforms%2A>、<xref:System.Web.HttpCachePolicy.GetOmitVaryStar%2A>、<xref:System.Web.HttpCachePolicy.GetProxyMaxAge%2A>、<xref:System.Web.HttpCachePolicy.GetRevalidation%2A>、<xref:System.Web.HttpCachePolicy.GetUtcLastModified%2A>、<xref:System.Web.HttpCachePolicy.GetVaryByCustom%2A>、<xref:System.Web.HttpCachePolicy.HasSlidingExpiration%2A>、および <xref:System.Web.HttpCachePolicy.IsValidUntilExpires%2A> が含まれます。

- <xref:System.Web.HttpCacheVaryByContentEncodings?displayProperty=nameWithType> クラスの新しい 2 つのメソッド (<xref:System.Web.HttpCacheVaryByContentEncodings.GetContentEncodings%2A> と <xref:System.Web.HttpCacheVaryByContentEncodings.SetContentEncodings%2A>)。

- <xref:System.Web.HttpCacheVaryByHeaders?displayProperty=nameWithType> クラスの新しい 2 つのメソッド (<xref:System.Web.HttpCacheVaryByHeaders.GetHeaders%2A> と <xref:System.Web.HttpCacheVaryByHeaders.SetHeaders%2A>)。

- <xref:System.Web.HttpCacheVaryByParams?displayProperty=nameWithType> クラスの新しい 2 つのメソッド (<xref:System.Web.HttpCacheVaryByParams.GetParams%2A> と <xref:System.Web.HttpCacheVaryByParams.SetParams%2A>)。

- <xref:System.Web.Caching.AggregateCacheDependency?displayProperty=nameWithType> クラスの <xref:System.Web.Caching.AggregateCacheDependency.GetFileDependencies%2A> メソッド。

- <xref:System.Web.Caching.CacheDependency> の <xref:System.Web.Caching.CacheDependency.GetFileDependencies%2A> メソッド。

<a name="Strings"></a> 
### <a name="character-categories"></a>文字カテゴリ
 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] の文字は [Unicode Standard バージョン 8.0.0](http://www.unicode.org/versions/Unicode8.0.0/) に基づいて分類されます。 [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] と [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] では、文字は Unicode 6.3 文字のカテゴリに基づいて分類されました。

 Unicode 8.0 のサポートは、<xref:System.Globalization.CharUnicodeInfo> クラスによる文字列の分類およびそれに依存する型とメソッドに限定されます。 これらには、<xref:System.Globalization.StringInfo> クラス、オーバーロードされた <xref:System.Char.GetUnicodeCategory%2A?displayProperty=nameWithType> メソッド、および .NET Framework の正規表現エンジンによって認識される[文字クラス](../../../docs/standard/base-types/character-classes-in-regular-expressions.md)が含まれます。  文字や文字列の比較と並べ替えは、この変更の影響を受けることなく、引き続き基となるオペレーティング システムに依存します (Windows 7 システムの場合は、.NET Framework で提供される文字データに依存)。

 Unicode 6.0 から Unicode 7.0 への文字カテゴリの変更については、Unicode Consortium Web サイトの [Unicode Standard バージョン 7.0.0](http://www.unicode.org/versions/Unicode7.0.0/) に関する記述を参照してください。 Unicode 7.0 から Unicode 8.0 への変更については、Unicode Consortium の Web サイトの [Unicode Standard バージョン 8.0.0](http://www.unicode.org/versions/Unicode8.0.0/) に関する記述を参照してください。

<a name="Crypto462"></a> 
### <a name="cryptography"></a>暗号
 **FIPS 186-3 DSA を含む X509 証明書のサポート** [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] には、FIPS 186-2 の 1024 ビットという制限を超えるキーを持つ、DSA (Digital Signature Algorithm) X509 証明書のサポートが追加されています。

 より大きな FIPS 186-3 のキー サイズのサポートに加えて、[!INCLUDE[net_v462](../../../includes/net-v462-md.md)] では、SHA-2 ファミリのハッシュ アルゴリズム (SHA256、SHA384、SHA512) によるシグネチャ計算も可能です。 FIPS 186-3 のサポートは新しい <xref:System.Security.Cryptography.DSACng?displayProperty=nameWithType> クラスで提供されます。

 .NET Framework 4.6 の <xref:System.Security.Cryptography.RSA> クラスと .NET Framework 4.6.1 の <xref:System.Security.Cryptography.ECDsa> クラスの最近の変更に合わせて、[!INCLUDE[net_v462](../../../includes/net-v462-md.md)] の <xref:System.Security.Cryptography.DSA> 抽象基本クラスにメソッドが追加されました。呼び出し元はこの機能をキャストせずに使用することができます。 データに署名する場合は、以下の例のように、<xref:System.Security.Cryptography.X509Certificates.DSACertificateExtensions.GetDSAPrivateKey%2A?displayProperty=nameWithType> 拡張メソッドを呼び出すことができます。

```csharp
public static byte[] SignDataDsaSha384(byte[] data, X509Certificate2 cert)
{
    using (DSA dsa = cert.GetDSAPrivateKey())
    {
        return dsa.SignData(data, HashAlgorithmName.SHA384);
    }
}
```

```vb 
Public Shared Function SignDataDsaSha384(data As Byte(), cert As X509Certificate2) As Byte()
    Using DSA As DSA = cert.GetDSAPrivateKey()
        Return DSA.SignData(data, HashAlgorithmName.SHA384)
    End Using
End Function
```

 署名データを検証する場合は、以下の例のように、<xref:System.Security.Cryptography.X509Certificates.DSACertificateExtensions.GetDSAPublicKey%2A?displayProperty=nameWithType> 拡張メソッドを呼び出すことができます。

```csharp
public static bool VerifyDataDsaSha384(byte[] data, byte[] signature, X509Certificate2 cert)
{
    using (DSA dsa = cert.GetDSAPublicKey())
    {
        return dsa.VerifyData(data, signature, HashAlgorithmName.SHA384);
    }
}
```

```vb
 Public Shared Function VerifyDataDsaSha384(data As Byte(), signature As Byte(), cert As X509Certificate2) As Boolean
    Using dsa As DSA = cert.GetDSAPublicKey()
        Return dsa.VerifyData(data, signature, HashAlgorithmName.SHA384)
    End Using
End Function
```

 **ECDiffieHellman キー派生ルーチンへの入力をよりわかりやすく** .NET Framework 3.5 では、3 種類の KDF (キー派生関数) ルーチンによる Elliptic Curve Diffie-Hellman キーの承諾のサポートが追加されました。 ルーチンへの入力、およびルーチン自体は <xref:System.Security.Cryptography.ECDiffieHellmanCng> オブジェクトのプロパティで構成されました。 しかし、すべてのルーチンですべての入力プロパティが読み取られるわけではないため、これまで開発者がよく混乱することがありました。

 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] ではこれに対処するために、次の 3 つのメソッドが <xref:System.Security.Cryptography.ECDiffieHellman> 基本クラスに追加され、これらの KDF ルーチンとその入力がよりわかりやくなりました。

|ECDiffieHellman メソッド|説明|
|----------------------------|-----------------|
|<xref:System.Security.Cryptography.ECDiffieHellman.DeriveKeyFromHash%28System.Security.Cryptography.ECDiffieHellmanPublicKey%2CSystem.Security.Cryptography.HashAlgorithmName%2CSystem.Byte%5B%5D%2CSystem.Byte%5B%5D%29>|次の式を使用してキー マテリアルを派生させます。<br /><br /> HASH(secretPrepend &#124;&#124; *x* &#124;&#124; secretAppend)<br /><br /> HASH(secretPrepend OrElse *x* OrElse secretAppend)<br /><br /> ここで *x* は、EC Diffie-Hellman アルゴリズムの計算結果を表します。|
|<xref:System.Security.Cryptography.ECDiffieHellman.DeriveKeyFromHmac%28System.Security.Cryptography.ECDiffieHellmanPublicKey%2CSystem.Security.Cryptography.HashAlgorithmName%2CSystem.Byte%5B%5D%2CSystem.Byte%5B%5D%2CSystem.Byte%5B%5D%29>|次の式を使用してキー マテリアルを派生させます。<br /><br /> HMAC(hmacKey, secretPrepend &#124;&#124; *x* &#124;&#124; secretAppend)<br /><br /> HMAC(hmacKey, secretPrepend OrElse *x* OrElse secretAppend)<br /><br /> ここで *x* は、EC Diffie-Hellman アルゴリズムの計算結果を表します。|
|<xref:System.Security.Cryptography.ECDiffieHellman.DeriveKeyTls%28System.Security.Cryptography.ECDiffieHellmanPublicKey%2CSystem.Byte%5B%5D%2CSystem.Byte%5B%5D%29>|TLS 擬似乱数関数 (PRF) 派生アルゴリズムを使用して、キー マテリアルを派生させます。|

 **永続化されたキーによる対称暗号化のサポート** Windows の暗号化ライブラリ (CNG) では、永続化された対称キーの格納とハードウェアに格納された対称キーの使用のサポートが追加され、[!INCLUDE[net_v462](../../../includes/net-v462-md.md)] で開発者はこの機能を利用できるようになりました。  キー名とキー プロバイダーの概念が実装に固有であるため、この機能を使用するには、推奨されるファクトリ手法 (`Aes.Create` の呼び出しなど) ではなく、具象実装型のコンストラクターを利用する必要があります。

 永続化されたキーによる対称暗号化は、AES (<xref:System.Security.Cryptography.AesCng>) と 3DES (<xref:System.Security.Cryptography.TripleDESCng>) アルゴリズムでサポートされます。 例:

```csharp
public static byte[] EncryptDataWithPersistedKey(byte[] data, byte[] iv)
{
    using (Aes aes = new AesCng("AesDemoKey", CngProvider.MicrosoftSoftwareKeyStorageProvider))
    {
        aes.IV = iv;

        // Using the zero-argument overload is required to make use of the persisted key
        using (ICryptoTransform encryptor = aes.CreateEncryptor())
        {
            if (!encryptor.CanTransformMultipleBlocks)
            {
                throw new InvalidOperationException("This is a sample, this case wasn’t handled...");
            }

            return encryptor.TransformFinalBlock(data, 0, data.Length);
        }
    }
}
```

```vb 
Public Shared Function EncryptDataWithPersistedKey(data As Byte(), iv As Byte()) As Byte()
    Using Aes As Aes = New AesCng("AesDemoKey", CngProvider.MicrosoftSoftwareKeyStorageProvider)
        Aes.IV = iv

        ' Using the zero-argument overload Is required to make use of the persisted key
        Using encryptor As ICryptoTransform = Aes.CreateEncryptor()
            If Not encryptor.CanTransformMultipleBlocks Then
                Throw New InvalidOperationException("This is a sample, this case wasn’t handled...")
            End If
            Return encryptor.TransformFinalBlock(data, 0, data.Length)
        End Using
    End Using
End Function
```

 **SHA-2 ハッシュの SignedXml サポート** [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] では <xref:System.Security.Cryptography.Xml.SignedXml> クラスに対するサポートが追加され、RSA-SHA256、RSA-SHA384、RSA-SHA512 の各 PKCS#1 署名メソッド、および SHA256、SHA384、SHA512 の各参照ダイジェスト アルゴリズムが使用できるようになりました。

 以下のように、URI 定数はすべて <xref:System.Security.Cryptography.Xml.SignedXml> で示されます。

|SignedXml フィールド|定数|
|---------------------|--------------|
|<xref:System.Security.Cryptography.Xml.SignedXml.XmlDsigSHA256Url>|"http://www.w3.org/2001/04/xmlenc#sha256"|
|<xref:System.Security.Cryptography.Xml.SignedXml.XmlDsigRSASHA256Url>|"http://www.w3.org/2001/04/xmldsig-more#rsa-sha256"|
|<xref:System.Security.Cryptography.Xml.SignedXml.XmlDsigSHA384Url>|"http://www.w3.org/2001/04/xmldsig-more#sha384"|
|<xref:System.Security.Cryptography.Xml.SignedXml.XmlDsigRSASHA384Url>|"http://www.w3.org/2001/04/xmldsig-more#rsa-sha384"|
|<xref:System.Security.Cryptography.Xml.SignedXml.XmlDsigSHA512Url>|"http://www.w3.org/2001/04/xmlenc#sha512"|
|<xref:System.Security.Cryptography.Xml.SignedXml.XmlDsigRSASHA512Url>|"http://www.w3.org/2001/04/xmldsig-more#rsa-sha512"|

 これらのアルゴリズムのサポートを追加するためにカスタムの <xref:System.Security.Cryptography.SignatureDescription> ハンドラーを <xref:System.Security.Cryptography.CryptoConfig> に登録していたプログラムはすべて従来どおり引き続き機能しますが、既定でプラットフォームでサポートされるようになったため、<xref:System.Security.Cryptography.CryptoConfig> への登録は不要になりました。

<a name="SQLClient"></a> 
### <a name="sqlclient"></a>SqlClient
 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] では、.NET Framework SQL Server 用データ プロバイダー (<xref:System.Data.SqlClient?displayProperty=nameWithType>) に次の新機能が含まれています。

 **Azure SQL Database への接続プールとタイムアウト** 接続プールが有効な状態で、タイムアウトまたは他のログイン エラーが発生した場合は、例外がキャッシュされ、キャッシュされた例外は次の 5 秒から 1 分の間の後続の接続試行時にすべてスローされます。  詳細については、「[SQL Server の接続プール (ADO.NET)](../../../docs/framework/data/adonet/sql-server-connection-pooling.md)」を参照してください。

 通常は迅速に復旧される一時的なエラーで接続試行が失敗する可能性があるため、Azure SQL Database への接続時のこの動作は望ましくありません。 接続試行操作をより最適化するため、Azure SQL Database への接続が失敗した場合は、接続プールのブロック期間の動作は削除されます。

 新しい `PoolBlockingPeriod` キーワードを追加することで、使用しているアプリに最適なブロック期間を選択できます。 次の値が含まれます。

 `Auto` Azure SQL Database に接続しているアプリケーションの接続プールのブロック期間は無効になり、他のすべての SQL Server インスタンスに接続しているアプリケーションの接続プールのブロック期間が有効になります。 これが既定値です。 サーバー エンドポイント名の末尾が以下のいずれかである場合は、Azure SQL Database と見なされます。

- .database.windows.net

- .database.chinacloudapi.cn

- .database.usgovcloudapi.net

- .database.cloudapi.de

 `AlwaysBlock` 接続プールのブロック期間は常に有効になります。

 `NeverBlock` 接続プールのブロック期間は常に無効になります。

 **Always Encrypted の強化** SQLClient では、Always Encrypted の以下の 2 つの機能が強化されました。

- 暗号化されたデータベースの列に対するパラメーター クエリのパフォーマンスを向上させるために、クエリ パラメーターの暗号化メタデータがキャッシュされるようになりました。 <xref:System.Data.SqlClient.SqlConnection.ColumnEncryptionQueryMetadataCacheEnabled%2A?displayProperty=nameWithType> プロパティが `true` (既定値) に設定されている状態で、同じクエリが複数回呼び出された場合、クライアントはサーバーからパラメーターのメタデータを 1 回だけ取得します。

- キー キャッシュ内の列暗号化キー エントリは、<xref:System.Data.SqlClient.SqlConnection.ColumnEncryptionKeyCacheTtl%2A?displayProperty=nameWithType> プロパティを使用して設定された構成可能な時間間隔後に削除されるようになりました。

<a name="WCF"></a> 
### <a name="windows-communication-foundation"></a>Windows Communication Foundation
 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] では、Windows Communication Foundation の次の領域の機能が強化されています。

 **CNG を使用して格納される証明書の WCF トランスポート セキュリティ サポート** WCF トランスポート セキュリティでは、Windows 暗号化ライブラリ (CNG) を使用して格納される証明書がサポートされます。 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] では、このサポートは、指数の長さが 32 ビット以下の公開キーを持つ証明書を使用する場合に限定されます。 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] を対象とするアプリケーションでは、この機能は既定で有効になります。

 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] 以前を対象とするアプリケーションが [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] で実行されている場合、app.config または web.config ファイルの [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) セクションに次の行を追加することで、この機能を有効にできます。

```xml
<AppContextSwitchOverrides
    value="Switch.System.ServiceModel.DisableCngCertificates=false"
/>
```

以下のようなコードを使用してプログラムで行うこともできます。

```csharp
private const string DisableCngCertificates = @"Switch.System.ServiceModel.DisableCngCertificates";
AppContext.SetSwitch(disableCngCertificates, false);
```

```vb
Const DisableCngCertificates As String = "Switch.System.ServiceModel.DisableCngCertificates"
AppContext.SetSwitch(disableCngCertificates, False)
```

 **DataContractJsonSerializer クラスによる複数の夏時間調整規則のサポート強化** お客様はアプリケーションの構成設定を使用して、<xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> クラスで 1 つのタイム ゾーンに対して複数の調整規則がサポートされているかどうかを判別することができます。 これはオプトイン機能です。 これを有効にするには、app.config ファイルに次の設定を追加します。

```xml
<runtime>
     <AppContextSwitchOverrides value="Switch.System.Runtime.Serialization.DoNotUseTimeZoneInfo=false" />
</runtime>
```

この機能が有効な場合、<xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> オブジェクトは <xref:System.TimeZone> 型ではなく <xref:System.TimeZoneInfo> 型を使用して、日時データを逆シリアル化します。 <xref:System.TimeZoneInfo> では、<xref:System.TimeZone> でサポートされない複数の調整規則がサポートされるため、過去のタイム ゾーン データを操作できます。

<xref:System.TimeZoneInfo> 構造体とタイム ゾーン調整の詳細については、「[タイム ゾーンの概要](../../../docs/standard/datetime/time-zone-overview.md)」を参照してください。

**XMLSerializer クラスでのシリアル化と逆シリアル化の際に UTC 時刻を保持するサポート** 通常、<xref:System.Xml.Serialization.XmlSerializer> クラスを使用して UTC の <xref:System.DateTime> 値をシリアル化する場合、日時は保持するものの、現地時刻と見なすシリアル化された時刻文字列が作成されます。  たとえば、次のコードを呼び出して UTC 日時をインスタンス化するとします。

```csharp
DateTime utc = new DateTime(2016, 11, 07, 3, 0, 0, DateTimeKind.Utc);
```

```vb
Dim utc As New Date(2016, 11, 07, 3, 0, 0, DateTimeKind.Utc)
```

この場合、システムのシリアル化された時刻文字列は、UTC より 8 時間遅れの "03:00:00.0000000-08:00" となります。  シリアル化された値は常に、現地日時の値として逆シリアル化されます。

 アプリケーションの構成設定を使用すれば、<xref:System.DateTime> 値のシリアル化と逆シリアル化の際に <xref:System.Xml.Serialization.XmlSerializer> で UTC タイム ゾーンの情報が保持されるかどうかを判別できます。

```xml 
<runtime>
     <AppContextSwitchOverrides 
          value="Switch.System.Runtime.Serialization.DisableSerializeUTCDateTimeToTimeAndDeserializeUTCTimeToUTCDateTime=false" />
</runtime>
```

この機能が有効な場合、<xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> オブジェクトは <xref:System.TimeZone> 型ではなく <xref:System.TimeZoneInfo> 型を使用して、日時データを逆シリアル化します。 <xref:System.TimeZoneInfo> では、<xref:System.TimeZone> でサポートされない複数の調整規則がサポートされるため、過去のタイム ゾーン データを操作できます。

<xref:System.TimeZoneInfo> 構造体とタイム ゾーン調整の詳細については、「[タイム ゾーンの概要](../../../docs/standard/datetime/time-zone-overview.md)」を参照してください。

 **NetNamedPipeBinding の一致順** WCF には、クライアント アプリケーションで設定できる新しいアプリ設定があります。これにより、クライアント アプリケーションは常に、要求したものと最も一致する URI でリッスンしているサービスに接続できます。 このアプリ設定が `false` (既定値) に設定されている場合、クライアントは <xref:System.ServiceModel.NetNamedPipeBinding> を使用して、要求した URI の部分文字列である URI でリッスンしているサービスへの接続を試行できます。

 たとえば、クライアントが `net.pipe://localhost/Service1` でリッスンしているサービスに接続しようとしているときに、管理者特権で実行しているコンピューター上の別のサービスが `net.pipe://localhost` でリッスンしているとします。 このアプリ設定が `false` に設定されている場合、クライアントは間違ったサービスに接続しようとします。 アプリ設定を `true` に設定すれば、クライアントは常に最も一致するサービスに接続するようになります。

> [!NOTE]
>  <xref:System.ServiceModel.NetNamedPipeBinding> を使用するクライアントは、完全なエンドポイント アドレスではなく、サービスのベース アドレス (存在する場合) に基づいてサービスを検索します。 この設定が常に機能するようにするには、サービスは一意のベース アドレスを使用する必要があります。

 この変更を有効にするには、以下のアプリ設定をクライアント アプリケーションの App.config ファイルまたは Web.config ファイルに追加します。

```xml
<configuration>
    <appSettings>
        <add key="wcf:useBestMatchNamedPipeUri" value="true" />
    </appSettings>
</configuration>
```

 **SSL 3.0 が既定のプロトコルではなくなった** トランスポート セキュリティで NetTcp を使用し、証明書の資格情報の種類を使用する場合、SSL 3.0 は、安全な接続のネゴシエーションに使用される既定のプロトコルではなくなりました。 TLS 1.0 が NetTcp のプロトコル一覧に含まれているため、ほとんどの場合、既存のアプリには影響はないと考えられます。 既存のすべてのクライアントは TLS 1.0 以降を使用して接続をネゴシエートできるようになりました。 Ssl3 が必要な場合は、以下の構成メカニズムのいずれかを使用して、ネゴシエートされたプロトコルの一覧に追加します。

- <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement.SslProtocols%2A?displayProperty=nameWithType> プロパティ

- <xref:System.ServiceModel.TcpTransportSecurity.SslProtocols%2A?displayProperty=nameWithType> プロパティ

- [\<netTcpBinding>](../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md) セクションの [\<transport>](../../../docs/framework/configure-apps/file-schema/wcf/transport-of-nettcpbinding.md) セクション

- [\<customBinding>](../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) セクションの [\<sslStreamSecurity>](../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md) セクション

<a name="WPF462"></a> 
### <a name="windows-presentation-foundation-wpf"></a>Windows Presentation Foundation (WPF)
 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] では、Windows Presentation Foundation の次の領域の機能が強化されています。

 **グループの並べ替え** <xref:System.Windows.Data.CollectionView> オブジェクトを使用してデータをグループ化するアプリケーションは、グループを並べ替える方法を明示的に宣言できるようになりました。 明示的な並べ替えにより、アプリがグループを動的に追加または削除する場合や、グループ化に関連する項目のプロパティの値を変更する場合に発生する非直感的な順序付けの問題が解決されます。 また、グループ化プロパティの比較がコレクション全体の並べ替えからグループの並べ替えに変更されるため、グループ作成プロセスのパフォーマンスを向上させることができます。

 グループの並べ替えをサポートするために、新しい <xref:System.ComponentModel.GroupDescription.SortDescriptions%2A?displayProperty=nameWithType> および <xref:System.ComponentModel.GroupDescription.CustomSort%2A?displayProperty=nameWithType> プロパティで、<xref:System.ComponentModel.GroupDescription> オブジェクトによって生成されるグループのコレクションを並べ替える方法が示されます。 これは、同じ名前の <xref:System.Windows.Data.ListCollectionView> プロパティでデータ項目を並べ替える方法を示すのと同様です。

 <xref:System.Windows.Data.PropertyGroupDescription> クラスの新しい 2 つの静的プロパティである <xref:System.Windows.Data.PropertyGroupDescription.CompareNameAscending%2A> と <xref:System.Windows.Data.PropertyGroupDescription.CompareNameDescending%2A> は、最も一般的なケースで使用できます。

 たとえば、次の XAML ではデータを年齢でグループ化し、年齢グループを昇順に並べ替え、各年齢グループ内の項目を姓でグループ化します。

```xaml
<GroupDescriptions>
     <PropertyGroupDescription 
         PropertyName="Age" 
         CustomSort= 
              "{x:Static PropertyGroupDescription.CompareNamesAscending}"/>
     </PropertyGroupDescription>
</GroupDescriptions>

<SortDescriptions>
     <SortDescription PropertyName="LastName"/>
</SortDescriptions>
```

 **ソフト キーボードのサポート** ソフト キーボードのサポートにより、WPF アプリケーションでのフォーカス追跡が可能になります。テキスト入力が可能なコントロールによりタッチ入力を受信すると、Windows 10 の新しいソフト キーボードが自動的に起動および終了します。

 .NET Framework の以前のバージョンでは、WPF アプリケーションは、WPF のペン/タッチ ジェスチャ サポートを無効にしないとフォーカス追跡を選択できません。  そのため、WPF アプリケーションは完全な WPF タッチのフル サポートを選ぶか、Windows のマウス プロモーションに依存する必要があります。

 **モニターごとの DPI** WPF アプリ用の高 DPI とハイブリッド DPI 環境の最近の急激な増加に対応するために、[!INCLUDE[net_v462](../../../includes/net-v462-md.md)] の WPF でモニターごとに対応できるようになりました。 ご使用の WPF アプリでモニターごとの DPI 対応を有効にする方法の詳細については、GitHub の[サンプルと開発者向けガイド](https://github.com/Microsoft/WPF-Samples/tree/master/PerMonitorDPI)に関するページを参照してください。

 .NET Framework の以前のバージョンでは、WPF アプリはシステム DPI 対応です。 つまり、アプリケーションの UI は、アプリがレンダリングされるモニターの DPI に基づき、必要に応じて OS でスケーリングされます。 ,

 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] で実行されるアプリの場合、次のように、アプリケーションの構成ファイルの [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) セクションに構成ステートメントを追加して、WPF アプリでモニターごとの DPI 変更を無効にすることができます。

```xml
<runtime>
   <AppContextSwitchOverrides value="Switch.System.Windows.DoNotScaleForDpiChanges=false"/>
</runtime>
```

<a name="WF462"></a> 
### <a name="windows-workflow-foundation-wf"></a>Windows Workflow Foundation (WF)
 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] では、Windows Workflow Foundation の次領域の機能が強化されています。

 **再ホストされた WF デザイナーにおける C# 式と IntelliSense のサポート** [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] より、WF では Visual Studio デザイナーとコード内ワークフローの両方で C# 式に対応するようになりました。 再ホストされたワークフロー デザイナーは WF の主な機能です。これにより、ワークフロー デザイナーを Visual Studio の外部のアプリケーション (WPF など) で使用できるようになります。  Windows Workflow Foundation は、再ホストされたワークフロー デザイナーで C# 式と IntelliSense をサポートできるようにします。 詳細については、[Windows Workflow Foundation のブログ](http://go.microsoft.com/fwlink/?LinkID=809042&clcid=0x409)を参照してください。

 `Availability of IntelliSense when a customer rebuilds a workflow project from Visual Studio` [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] より前のバージョンの .NET Framework で、お客様が Visual Studio からワークフロー プロジェクトを再ビルドした場合、WF Designer IntelliSense は破損してしまいます。 プロジェクトのビルドに成功しても、デザイナーでワークフローの種類が見つからず、**[エラー一覧]** ウィンドウにワークフローの種類が欠落していることを示す IntelliSense からの警告が表示されます。 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] はこの問題に対処し、IntelliSense を使用できるようにします。

 **ワークフロー追跡を有効にしたワークフロー V1 アプリケーションを FIPS モードで実行** FIPS コンプライアンス モードが有効なコンピューターで、ワークフロー追跡が有効なワークフロー バージョン 1 スタイルのアプリケーションを正常に実行できるようになりました。 このシナリオを有効にするには、app.config ファイルを以下のように変更する必要があります。

```xml
<add key="microsoft:WorkflowRuntime:FIPSRequired" value="true" />
```

 このシナリオが有効でない場合、アプリケーションを実行すると、引き続き例外が生成され、"この実装は Windows プラットフォーム FIPS 検証暗号化アルゴリズムの一部ではありません" というメッセージが表示されます。

 **Visual Studio ワークフロー デザイナーで動的更新を使用する場合のワークフローの改善** ワークフロー デザイナー、フローチャート アクティビティ デザイナー、およびその他のワークフロー アクティビティ デザイナーで、<xref:System.Activities.DynamicUpdate.DynamicUpdateServices.PrepareForUpdate%2A?displayProperty=nameWithType> メソッドを呼び出した後に保存されたワークフローが正常に読み込まれ、表示されるようになりました。 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] より前のバージョンの .NET Framework では、<xref:System.Activities.DynamicUpdate.DynamicUpdateServices.PrepareForUpdate%2A?displayProperty=nameWithType> を呼び出した後に保存されたワークフローの XAML ファイルを Visual Studio で読み込むと、以下の問題が発生する場合がありました。

- ワークフロー デザイナーで XAML ファイルが正しく読み込めない (行の末尾に <xref:System.Activities.Presentation.ViewState.ViewStateData.Id%2A?displayProperty=nameWithType> がある場合)。

- フローチャート アクティビティ デザイナーまたは他のワークフロー アクティビティ デザイナーで、アタッチされるプロパティの値ではなく既定の場所にすべてのオブジェクトが表示される場合がある。

<a name="ClickOnce"></a> 
### <a name="clickonce"></a>ClickOnce
 ClickOnce が更新され、既にサポートされている 1.0 プロトコルに加え、TLS 1.1 と TLS 1.2 がサポートがサポートされるようになりました。 ClickOnce が必要なプロトコルを自動的に検出するため、TLS 1.1 と 1.2 のサポートを有効にするために、ClickOnce アプリケーション内での追加の手順は不要です。

<a name="UWPConvert"></a> 
### <a name="converting-windows-forms-and-wpf-apps-to--uwp-apps"></a>Windows フォームおよび WPF アプリの UWP アプリへの変換
 Windows では、WPF および Windows フォーム アプリを含む、既存の Windows デスクトップ アプリを UWP (ユニバーサル Windows プラットフォーム) で使用できるようになりました。 このテクノロジはブリッジとして機能し、既存のコード ベースを段階的に UWP に移行し、アプリをすべての Windows 10 デバイスで使用できるようにします。

 変換後のデスクトップ アプリは UWP アプリのアプリ ID のようなアプリ ID を取得し、UWP API をアクセス可能にして、ライブ タイルや通知などの機能を有効にすることができます。 アプリは引き続き従来どおり動作し、完全信頼アプリとして実行されます。 アプリが変換されたら、アプリ コンテナー プロセスを既存の完全信頼プロセスに追加し、適応ユーザー インターフェイスを追加できます。 すべての機能がアプリ コンテナー プロセスに移行されたら、完全信頼プロセスを削除し、新しい UWP アプリをすべての Windows 10 デバイスで有効にすることができます。

<a name="Debug462"></a> 
### <a name="debugging-improvements"></a>デバッグの機能強化
 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] で *アンマネージ デバッグ API* が強化され、<xref:System.NullReferenceException> がスローされたときに、ソース コードの単一行でどの変数が `null` になっているかを判別できるように、さらに分析されるようになりました。   このシナリオをサポートするために、次の API がアンマネージ デバッグ API に追加されました。

- [ICorDebugCode4](../../../docs/framework/unmanaged-api/debugging/icordebugcode4-interface.md)、[ICorDebugVariableHome](../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)、および [ICorDebugVariableHomeEnum](../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md) インターフェイス。これらは管理対象変数の元のホームを公開します。 これにより、デバッガーは、<xref:System.NullReferenceException> の発生時になんらかのコード フロー分析を行い、さかのぼって、`null` だった元の場所に対応する管理対象変数を判別できます。

- [ICorDebugType2::GetTypeID](../../../docs/framework/unmanaged-api/debugging/icordebugtype2-gettypeid-method.md) メソッドでは ICorDebugType を [COR_TYPEID](../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) にマッピングできます。これにより、デバッガーは、ICorDebugType のインスタンスがなくても [COR_TYPEID](../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) を取得できます。 その後、[COR_TYPEID](../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) で既存の API を使用して、型のクラス レイアウトを判別できます。

<a name="v461"></a> 
## <a name="whats-new-in-the-net-framework-461"></a>.NET Framework 4.6.1 の新機能
 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] には、次の領域における新機能が含まれています。

- [暗号](#Crypto)

- [ADO.NET](#ADO.NET461)

- [Windows Presentation Foundation (WPF)](#WPF461)

- [Windows Workflow Foundation](#WWF461)

- [プロファイル](#Profile461)

- [NGen](#NGEN461)

 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] の詳細については、次のトピックを参照してください。

- [.NET Framework 4.6.1 の変更の一覧](http://go.microsoft.com/fwlink/?LinkId=622964)

- [4.6.1 でのアプリケーションの互換性](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-6-1.md)

- [.NET Framework API の diff (差分)](http://go.microsoft.com/fwlink/?LinkId=622989) (GitHub 上)

<a name="Crypto"></a> 
### <a name="cryptography-support-for-x509-certificates-containing-ecdsa"></a>暗号化: ECDSA を含む X509 証明書のサポート
 .NET Framework 4.6 では、X509 証明書の RSACng サポートが追加されました。 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] では、ECDSA (Elliptic Curve Digital Signature Algorithm: 楕円曲線デジタル署名アルゴリズム) X509 証明書のサポートが追加されました。

 ECDSA は、RSA よりも安全な暗号化アルゴリズムで、パフォーマンスも向上するため、トランスポート層セキュリティ (TLS) のパフォーマンスとスケーラビリティが問題になる場合に最適な選択肢です。 .NET Framework の実装では、既存の Windows 機能の呼び出しがラップされます。

 次のサンプル コードでは、[!INCLUDE[net_v461](../../../includes/net-v461-md.md)] での新しい ECDSA X509 証明書のサポートを使用してバイト ストリームの署名が簡単に生成できることを示しています。

 [!code-csharp[whatsnew.461.crypto#1](../../../samples/snippets/csharp/VS_Snippets_CLR/whatsnew.461.crypto/cs/Code46.cs#1)]
 [!code-vb[whatsnew.461.crypto#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/whatsnew.461.crypto/vb/Code461.vb#1)]

 このコードは、.NET Framework 4.6 での署名の生成に必要な次のコードとは大きく異なっています。

 [!code-csharp[whatsnew.461.crypto#2](../../../samples/snippets/csharp/VS_Snippets_CLR/whatsnew.461.crypto/cs/Code46.cs#2)]
 [!code-vb[whatsnew.461.crypto#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/whatsnew.461.crypto/vb/Code46.vb#2)]

<a name="ADO.NET461"></a> 
### <a name="adonet"></a>ADO.NET
 次のものが ADO.NET に追加されました。

 ハードウェア保護キーに対する Always Encrypted のサポート ADO.NET では、Always Encrypted 列 (常に暗号化される列) のマスター キーをハードウェア セキュリティ モジュール (HSM) に格納することが、ネイティブでサポートされるようになりました。 このサポートによって、ユーザーは、HSM に格納された非対称キーを利用できます。カスタムの列マスター キー ストア プロバイダーを作成してからアプリケーションに登録する必要はありません。

 HSM に格納された列マスター キーで保護された Always Encrypted データにアクセスするには、HSM ベンダー提供の CSP プロバイダーまたは CNG キー ストア プロバイダーをアプリ サーバーまたはクライアント コンピューターにインストールする必要があります。

 AlwaysOn に対する <xref:System.Data.SqlClient.SqlConnectionStringBuilder.MultiSubnetFailover%2A> の接続動作の向上 SqlClient で、AlwaysOn 可用性グループ (AG) へのより高速な接続が自動的に提供されるようになりました。 SqlClient では、アプリケーションが別のサブネット上の AlwaysOn 可用性グループ (AG) に接続しているかどうかを自動的に検出し、現在のアクティブなサーバーを迅速に探索し、そのサーバーへの接続を提供します。 このリリースよりも前は、アプリケーションで接続文字列を設定し、`"MultisubnetFailover=true"` を含め、AlwaysOn 可用性グループに接続されていることを示す必要がありました。 `true` への接続キーワードを設定しないと、アプリケーションで AlwaysOn 可用性グループに接続中にタイムアウトが発生する可能性がありました。 このリリースを使用すれば、アプリケーションで <xref:System.Data.SqlClient.SqlConnectionStringBuilder.MultiSubnetFailover%2A> を `true` に設定する必要が*なくなり*ます。 Always On 可用性グループの SqlClient サポートの詳細については、「[高可用性障害復旧のための SqlClient サポート](../../../docs/framework/data/adonet/sql/sqlclient-support-for-high-availability-disaster-recovery.md)」をご覧ください。

<a name="WPF461"></a> 
### <a name="windows-presentation-foundation-wpf"></a>Windows Presentation Foundation (WPF)
 Windows Presentation Foundation には、さまざまな改善と変更が含まれています。

 パフォーマンスの向上 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] で、タッチ イベントの開始の遅延が修正されました。 また、<xref:System.Windows.Controls.RichTextBox> コントロールの入力が高速入力時のレンダーのスレッドを停止させなくなりました。

 スペル チェック機能の改善 WPF のスペル チェック機能が、追加の言語のスペル チェックのためにオペレーティング システムのサポートを利用するように、Windows 8.1 以降のバージョンで更新されました。  Windows 8.1 よりも前の Windows バージョンの機能の変更はありません。

 以前のバージョンの .NET Framework と同様に、<xref:System.Windows.Controls.TextBox> コントロールまたは <xref:System.Windows.Controls.RichTextBox> ブロック用の言語が、次の順序で情報を探すことによって検出されます。

- `xml:lang` (存在する場合)。

- 現在の入力言語。

- 現在のスレッド カルチャ。

 WPF での言語サポートの詳細については、[.NET Framework 4.6.1 機能に関する WPF ブログの記事](http://go.microsoft.com/fwlink/?LinkID=691819)を参照してください。

 ユーザーごとのユーザー辞書の追加サポート [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] では、グローバルに登録されているユーザー辞書が認識されます。 この機能は、ユーザー辞書をコントロールごとに登録する機能に加えて使用できます。

 以前のバージョンの WPF では、ユーザー辞書で除外された単語とオートコレクト リストが認識されませんでした。 `%AppData%\Microsoft\Spelling\<language tag>` ディレクトリに配置できるファイルの使用によって、これらが Windows 8.1 と Windows 10 でサポートされます。  これらのファイルには、次の規則が適用されます。

- これらのファイルには、拡張子の .dic (追加された単語の場合)、.exc (除外された単語の場合)、または .acl (オートコレクトの場合) が付いている必要があります。

- これらのファイルは、バイト オーダー マーク (BOM) で始まる UTF-16 LE プレーン テキストである必要があります。

- それぞれの行は、1 つの単語 (追加および除外された単語の一覧内)、または単語が縦棒 ("&#124;") で区切られたオートコレクトのペア (オートコレクトの単語の一覧内) で構成される必要があります。

- これらのファイルは読み取り専用と見なされ、システムによって変更されることはありません。

> [!NOTE]
>  これらの新しいファイル形式は、WPF スペル チェック API で直接サポートされるわけではありません。また、アプリケーションで WPF に提供されるユーザー辞書では以前と同様に .lex ファイルを使用する必要があります。

 サンプル MSDN に多数の [WPF サンプル](https://msdn.microsoft.com/library/ms771633.aspx)があります。 サンプルの利用状況に基づき、よく使用される 200 を超えるサンプルが、[オープン ソースの GitHub リポジトリ](https://github.com/Microsoft/WPF-Samples)に移動される予定です。 プル要求を送信するか、または[GitHub issue (GitHub の問題)](https://github.com/Microsoft/WPF-Samples/issues) を開いて、これらのサンプルの改善にご協力ください。

 DirectX 拡張機能の WPF には、DX10 および Dx11 のコンテンツとの相互運用を容易にする、<xref:System.Windows.Interop.D3DImage> の新しい実装を提供する [NuGet パッケージ](http://go.microsoft.com/fwlink/?LinkID=691342)が含まれています。 このパッケージのコードはオープン ソース化されており、[GitHub で](https://github.com/Microsoft/WPFDXInterop)入手できます。

<a name="WWF461"></a> 
### <a name="windows-workflow-foundation-transactions"></a>Windows Workflow Foundation: トランザクション
 <xref:System.Transactions.Transaction.EnlistPromotableSinglePhase%2A?displayProperty=nameWithType> メソッドで、MSDTC 以外の分散トランザクション マネージャーを使用して、トランザクションをプロモート (昇格) できるようになりました。 このプロモートは、新しい <xref:System.Transactions.Transaction.EnlistPromotableSinglePhase%28System.Transactions.IPromotableSinglePhaseNotification%2CSystem.Guid%29?displayProperty=nameWithType> オーバーロードに GUID のトランザクション プロモーター識別子を指定することによって行います。 この操作が成功すると、そのトランザクションの機能に制限が加えられます。 MSDTC 以外のトランザクション プロモーターが登録される (参加する) と、次の各メソッドで MSDTC へのプロモートが必要になるため、これらのメソッドで <xref:System.Transactions.TransactionPromotionException> がスローされます。

- <xref:System.Transactions.Transaction.EnlistDurable%2A?displayProperty=nameWithType>

- <xref:System.Transactions.TransactionInterop.GetDtcTransaction%2A?displayProperty=nameWithType>

- <xref:System.Transactions.TransactionInterop.GetExportCookie%2A?displayProperty=nameWithType>

- <xref:System.Transactions.TransactionInterop.GetTransmitterPropagationToken%2A?displayProperty=nameWithType>

 MSDTC 以外のトランザクション プロモーターが登録されると、そのプロモーターで定義するプロトコルを使用することで、そのプロモーターをその後の永続参加リストに使用する必要があります。 トランザクション プロモーターの <xref:System.Guid> は、<xref:System.Transactions.Transaction.PromoterType%2A> プロパティを使用して取得できます。 トランザクションがプロモートする際、トランザクション プロモーターによって、プロモート済みトークンを表す <xref:System.Byte> 配列が提供されます。 アプリケーションで、MSDTC 以外のプロモート済みトランザクションのプロモート済みトークンを <xref:System.Transactions.Transaction.GetPromotedToken%2A> メソッドを使用して取得できます。

 新しい <xref:System.Transactions.Transaction.EnlistPromotableSinglePhase%28System.Transactions.IPromotableSinglePhaseNotification%2CSystem.Guid%29?displayProperty=nameWithType> オーバーロードのユーザーは、プロモーション操作が正常に完了するように、特定の呼び出しシーケンスに従う必要があります。 これらの規則は、メソッドのドキュメントに記載されています。

<a name="Profile461"></a> 
### <a name="profiling"></a>プロファイル
 アンマネージ プロファイル API が、次のように拡張されました。

 [ICorProfilerInfo7](../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md) インターフェイス内の PDB へのアクセスのサポートが向上 ASP.NET 5 では、アセンブリがメモリ内で Roslyn によってコンパイルされることがよりいっそう一般的になっています。 プロファイル ツールを作成する開発者にとって、これは従来ディスクにシリアル化されていた PDB が存在しなくなる可能性があることを意味しています。 プロファイル ツールでは、多くの場合 PDB を使用して、コード カバレッジや 1 行単位のパフォーマンス分析などのタスクのソース行に、コードをマップし戻します。 [ICorProfilerInfo7](../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md) インターフェイスは、メモリ内の PDB データにアクセスして、これらのプロファイル ツールを提供する 2 つの新しいメソッド、[ICorProfilerInfo7::GetInMemorySymbolsLength](../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-getinmemorysymbolslength-method.md) と [ICorProfilerInfo7::ReadInMemorySymbols](../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-readinmemorysymbols.md) を含むようになりました。これらの新しい API を使用すれば、プロファイラーでメモリ内の PDB の内容をバイト配列として取得してから、それを処理したり、ディスクにシリアル化したりできます。

 ICorProfiler インターフェイスを使用したインストルメンテーションの改良 動的インストルメンテーションに `ICorProfiler` API の ReJit 機能を使用しているプロファイラーで、いくつかのメタデータを変更できるようになりました。 従来、このようなツールでは、いつでも IL をインストルメント化できましたが、メタデータを変更できるのはモジュールを読み込む時だけでした。 IL はメタデータを参照するため、実行できるインストルメンテーションの種類が限られています。 モジュールの読み込み後のメタデータの編集のサブセットをサポートするために、[ICorProfilerInfo7::ApplyMetaData](../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-applymetadata-method.md) メソッドを追加することで (特に新しい `AssemblyRef`、`TypeRef`、`TypeSpec`、`MemberRef`、`MemberSpec`、および `UserString` の各レコードを追加することで)、これらの制限の一部を解消しました。 この変更により、はるかに広範な実行時インストルメンテーションが可能になります。

<a name="NGEN461"></a> 
### <a name="native-image-generator-ngen-pdbs"></a>ネイティブ イメージ ジェネレーター (NGEN) PDB
 マシン間のイベント トレースを使用すれば、ユーザーはマシン A 上でプログラムのプロファイリングを行い、マシン B 上でソース行のマッピングを使用して、プロファイリング データを確認できます。以前のバージョンの.NET Framework を使用する場合、ソースからネイティブへのマッピングを作成するには、ユーザーは、プロファイルされたコンピューターにあるすべてのモジュールとネイティブ イメージを、IL PDB が含まれた分析用コンピューターにコピーする必要がありました。 この処理は、Phone アプリケーションなどファイル サイズが比較的小さい場合には高速に実行されますが、これらのファイルのサイズがデスクトップ システム上で非常に大きくなる可能性があり、その場合コピーにかなりの時間を要する可能性があります。

 NGen PDB を使用すれば、IL PDB に依存することなく、NGen で IL からネイティブへのマッピングが含まれた PDB を作成できます。 このマシン間のイベント トレース シナリオで必要なことは、コンピューター A で生成されたネイティブ イメージの PDB をコンピューター B にコピーすることと、[Debug Interface Access API](/visualstudio/debugger/debug-interface-access/debug-interface-access-sdk-reference) を使用して IL PDB のソースから IL へのマッピングとネイティブ イメージの PDB の IL からネイティブへのマッピングを読み取ることだけです。 両方のマッピングを組み合わせることで、ソースからネイティブへのマッピングが実現します。 ネイティブ イメージの PDB は、どのモジュールとネイティブ イメージよりもはるかにサイズが小さいため、コンピューター A からコンピューター B へのコピーの処理は非常に高速になります。

<a name="v46"></a> 
## <a name="whats-new-in-net-2015"></a>.NET 2015 の新機能
 .NET 2015 では、[!INCLUDE[net_v46](../../../includes/net-v46-md.md)] と .NET Core が導入されています。 一部の新機能はその両方に適用され、その他の機能は [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] または [!INCLUDE[net_core](../../../includes/net-core-md.md)] に固有です。

- **ASP.NET 5**

     .NET 2015 には、ASP.NET 5 が含まれています。これは、最新のクラウド ベースのアプリを構築するのに非常に効率の良い .NET 実装です。 ASP.NET 5 はモジュール形式であるため、アプリケーションで必要な機能のみを含めることができます。 IIS でホストすることも、カスタムのプロセスでセルフホストすることもできます。さらに同じサーバー上のさまざまなバージョンの .NET Framework でアプリを実行することも可能です。 クラウド展開用に設計されている新たな環境構成システムが含まれています。

     MVC、Web API、および Web ページは、MVC 6 と呼ばれる 1 つのフレームワークに統合されています。 Visual Studio 2015 の新しいツールで ASP.NET 5 アプリをビルドします。 既存のアプリケーションは、この新しい .NET Framework で動作しますが、MVC 6 または SignalR 3 を使用するアプリケーションをビルドするには Visual Studio 2015 のプロジェクト システムを使用する必要があります。

     詳細については、[ASP.NET 5](http://go.microsoft.com/fwlink/?LinkId=518238) に関するページを参照してください。

- **ASP.NET の更新プログラム**

    - **非同期応答フラッシュ用のタスク ベース API**

         ASP.NET で、非同期応答フラッシュ用の単純なタスク ベース API である <xref:System.Web.HttpResponse.FlushAsync%2A?displayProperty=nameWithType> が提供されるようになりました。これにより、言語の `async/await` サポートを使用して非同期的に応答をフラッシュできます。

    - `Model binding supports task-returning methods`

         [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] では、Web フォーム ページやユーザー コントロールでの CRUD ベースのデータ操作に対して拡張可能なコード中心のアプローチを可能にするモデル バインド機能が ASP.NET に追加されました。 このモデル バインド システムで、<xref:System.Threading.Tasks.Task> を返すモデル バインド メソッドがサポートされるようになりました。 この機能により、Web フォーム開発者は Entity Framework などの ORM の新しいバージョンを使用するときに、データ バインド システムのように簡単に非同期のスケーラビリティ上のメリットを得ることができます。

         非同期モデル バインドは、`aspnet:EnableAsyncModelBinding` 構成設定によって制御されます。

        ```xml
        <appSettings>
           <add key=" aspnet:EnableAsyncModelBinding" value="true|false" />
        </appSettings>
        ```

         [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] を対象とするアプリでは、既定で `true` になります。 [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] で実行され、.NET Framework の以前のバージョンを対象とするアプリでは、既定で `false` になります。 有効にするには、この構成設定を `true` に設定します。

    - **HTTP/2 のサポート (Windows 10)**

         [HTTP/2](http://www.wikipedia.org/wiki/HTTP/2) は HTTP プロトコルの新しいバージョンで、接続の使用状況が (クライアントとサーバー間のラウンド トリップ数の減少により) 大幅に改善されて、ユーザーが Web ページを読み込むときの遅延が軽減されています。  このプロトコルは単一のエクスペリエンスの一部として要求さる複数の成果物のために最適化されているので、HTTP/2 が最も役立つのは (サービスではなく) web ページです。 .NET Framework 4.6 では、HTTP/2 のサポートが ASP.NET に追加されました。 ネットワーク機能は複数のレイヤーで存在するので、HTTP/2 を有効にするために、Windows、IIS、および ASP.NET で新機能が必要とされていました。 ASP.NET で HTTP/2 を使用するには、Windows 10 を実行している必要があります。

         HTTP/2 は、<xref:System.Net.Http.HttpClient?displayProperty=nameWithType> API を使用する Windows 10 ユニバーサル Windows プラットフォーム (UWP) アプリでもサポートされ、既定で有効になります。

         ASP.NET アプリケーションで [PUSH_PROMISE](http://http2.github.io/http2-spec/#PUSH_PROMISE) 機能を使用する手段を提供するために、<xref:System.Web.HttpResponse.PushPromise%28System.String%29> と <xref:System.Web.HttpResponse.PushPromise%28System.String%2CSystem.String%2CSystem.Collections.Specialized.NameValueCollection%29> の 2 つのオーバーロードを持つ新しいメソッドが <xref:System.Web.HttpResponse> クラスに追加されました。

        > [!NOTE]
        >  ASP.NET 5 では HTTP/2 がサポートされましたが、PUSH PROMISE 機能のサポートはまだ追加されていません。

         ブラウザーと web サーバー (Windows 上の IIS) がすべての処理を実行します。 ユーザーの側で複雑な操作を実行する必要はありません。

         [主要なブラウザーのほとんどは HTTP/2 をサポートしている](http://www.wikipedia.org/wiki/HTTP/2)ため、多くの場合、サーバーが HTTP/2 をサポートしていれば、ユーザーもそのメリットを得ることができます。

    - **トークン バインディング プロトコルのサポート**

         Microsoft と Google は、[トークン バインディング プロトコル](https://github.com/TokenBinding/Internet-Drafts)と呼ばれる、認証のための新しいアプローチに共同で取り組んできました。 この前提となっているのは、犯罪者が (ブラウザー キャッシュ内の) 認証トークンを盗用することで、本来ならパスワードや他の特別な情報でセキュリティ保護されているリソース (銀行口座など) にアクセスできる可能性がある、ということです。 新しいプロトコルは、この問題を軽減することを目指しています。

         トークン バインディング プロトコルは、Windows 10 でブラウザーの機能として実装されます。 ASP.NET アプリは、認証トークンの正当性が検証されるように、このプロトコルに参加します。 クライアントとサーバーの実装は、プロトコルによって指定されるエンド ツー エンドの保護を確立します。

    - **ランダムな文字列のハッシュ アルゴリズム**

         .NET Framework 4.5 で、[ランダム化された文字列のハッシュ アルゴリズム](../configure-apps/file-schema/runtime/userandomizedstringhashalgorithm-element.md)が導入されました。 しかし、ASP.NET の一部の機能は安定したハッシュ コードに依存していたため、この機能は ASP.NET ではサポートされませんでした。 [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] では、ランダムな文字列のハッシュ アルゴリズムがサポートされるようになりました。 この機能を有効にするには、`aspnet:UseRandomizedStringHashAlgorithm` 構成設定を使用します。

        ```xml
        <appSettings>
           <add key="aspnet:UseRandomizedStringHashAlgorithm" value="true|false" />
        </appSettings>
        ```

- **ADO.NET**

     ADO .NET では、SQL Server 2016 Community Technology Preview 2 (CTP2) で使用できる Always Encrypted 機能がサポートされました。 SQL Server は、Always Encrypted 機能を使用して、暗号化されたデータに対して操作を実行できます。特に、サーバー上ではなく、ユーザーが信頼している環境内にアプリケーションと共に暗号化キーを保存できるようになりました。 Always Encrypted でユーザー データが保護されるので、DBA はプレーン テキスト データにアクセスできません。 データの暗号化と復号化は、ドライバー レベルで透過的に行われるので、既存のアプリケーションに対する変更が最小限に抑えられます。 詳細については、「[Always Encrypted (データベース エンジン)](/sql/relational-databases/security/encryption/always-encrypted-database-engine)」および「[Always Encrypted (クライアント開発)](/sql/relational-databases/security/encryption/always-encrypted-client-development)」を参照してください。

- **マネージ コードの JIT コンパイラ (64 ビット)**

     .NET Framework 4.6 の特徴の 1 つとして、新しいバージョンの 64 ビット JIT コンパイラ (RyuJIT というコードネームで呼ばれていたもの) があります。 この新しい 64 ビット コンパイラは、これまでの 64 ビット JIT コンパイラよりもパフォーマンスが大幅に向上しています。 新しい 64 ビット コンパイラは、.NET Framework 4.6 上で実行される 64 ビット プロセスで有効になります。 64 ビットまたは AnyCPU としてコンパイルされ、64 ビット オペレーティング システム上で実行されるアプリは、64 ビットで動作します。 新しいコンパイラへの移行をできる限り透過的に行うように注意を払いましたが、動作の変更が発生する可能性があります。 新しい JIT コンパイラの使用中に発生した問題については、直接お聞かせいただければと思います。 新しい 64 ビット JIT コンパイラに関連する可能性のある問題が発生した場合は、[Microsoft Connect](http://connect.microsoft.com/) にご連絡ください。

     新しい 64 ビット JIT コンパイラには、ハードウェア SIMD アクセラレータ機能も含まれています。これを <xref:System.Numerics> 名前空間の SIMD 対応の型と組み合わせると、パフォーマンスが大幅に向上する可能性があります。

- **アセンブリ ローダーの改善**

     アセンブリ ローダーで、対応する NGEN イメージの読み込み後に IL アセンブリをアンロードすることにより、メモリがより効率的に使用されるようになりました。 この変更は、仮想メモリが減少するため、特に大規模な 32 ビット アプリ (Visual Studio など) で有益であり、物理メモリの節約にもなります。

- **基本クラス ライブラリの変更点**

     主なシナリオを利用できるようにするため、多くの新しい API が [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] に関連して追加されました。 変更点と追加点を以下に示します。

    - **IReadOnlyCollection\<T> implementations**

         追加のコレクション <xref:System.Collections.Generic.IReadOnlyCollection%601> (<xref:System.Collections.Generic.Queue%601>、<xref:System.Collections.Generic.Stack%601> など) が実装されています。

    - **CultureInfo.CurrentCulture と CultureInfo.CurrentUICulture**

         <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=nameWithType> プロパティと <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=nameWithType> プロパティが読み取り専用ではなく、読み取り/書き込み可能になりました。 新しい <xref:System.Globalization.CultureInfo> オブジェクトをこれらのプロパティに割り当てると、`Thread.CurrentThread.CurrentCulture` プロパティで現在定義されているスレッド カルチャと、`Thread.CurrentThread.CurrentUICulture` プロパティで現在定義されている UI スレッド カルチャも変更されます。

    - **ガベージ コレクション (GC) の機能強化**

         <xref:System.GC> クラスに <xref:System.GC.TryStartNoGCRegion%2A> メソッドと <xref:System.GC.EndNoGCRegion%2A> メソッドが含まれるようになりました。これらのメソッドを使用するとクリティカル パスの実行中にガベージ コレクションを不許可にできます。

         <xref:System.GC.Collect%28System.Int32%2CSystem.GCCollectionMode%2CSystem.Boolean%2CSystem.Boolean%29?displayProperty=nameWithType> メソッドの新しいオーバーロードを使用して、小さなオブジェクト ヒープと大きなオブジェクト ヒープの両方に関して、スイープして圧縮するのか、スイープのみを行うのかを制御できます。

    - **SIMD が有効な型**

         <xref:System.Numerics> 名前空間には、<xref:System.Numerics.Matrix3x2>、<xref:System.Numerics.Matrix4x4>、<xref:System.Numerics.Plane>、<xref:System.Numerics.Quaternion>、<xref:System.Numerics.Vector2>、<xref:System.Numerics.Vector3>、<xref:System.Numerics.Vector4> など、いくつかの SIMD 対応の型が含まれるようになりました。

         新しい 64 ビット JIT コンパイラにはハードウェア SIMD アクセラレータ機能も含まれているため、新しい 64 ビット JIT コンパイラで SIMD 対応の型を使用すると、パフォーマンスが大幅に向上します。

    - **暗号の更新**

         <xref:System.Security.Cryptography?displayProperty=nameWithType> API は、[Windows CNG 暗号化 API](https://msdn.microsoft.com/library/windows/desktop/aa376214.aspx) をサポートするために更新中です。 以前のバージョンの .NET Framework は、<xref:System.Security.Cryptography?displayProperty=nameWithType> の実装の基礎として、[それより前のバージョンの Windows 暗号化 API](https://msdn.microsoft.com/library/windows/desktop/aa380255.aspx) に完全に依存していました。 CNG API は特定のカテゴリのアプリにとって重要な[最新の暗号アルゴリズム](https://msdn.microsoft.com/library/windows/desktop/bb204775.aspx#suite_b_support)をサポートするものであるため、CNG API をサポートしてほしいというリクエストが寄せられていました。

         .NET Framework 4.6 には、Windows CNG 暗号化 API をサポートするために、次の新しい機能強化が含まれています。

        - 可能な場合に CAPI ベースの実装ではなく CNG ベースの実装を返す X509 証明書用の一連の拡張メソッド `System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPublicKey(System.Security.Cryptography.X509Certificates.X509Certificate2)` および `System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPrivateKey(System.Security.Cryptography.X509Certificates.X509Certificate2)`  (一部のスマート カードなどでは現在も CAPI が必要であり、API がフォールバックを処理します)。

        - RSA アルゴリズムの CNG 実装を提供する <xref:System.Security.Cryptography.RSACng?displayProperty=nameWithType> クラス。

        - 一般的な操作でキャストを不要にする RSA API の機能強化。 たとえば、以前のバージョンの .NET Framework で <xref:System.Security.Cryptography.X509Certificates.X509Certificate2> オブジェクトを使用してデータを暗号化するには、次のようなコードが必要です。

             [!code-csharp[WhatsNew.Casting#1](../../../samples/snippets/csharp/VS_Snippets_CLR/whatsnew.casting/cs/program.cs#1)]
             [!code-vb[WhatsNew.Casting#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/whatsnew.casting/vb/module1.vb#1)]

             .NET Framework 4.6 で新しい暗号化を使用するコードは、次のように書き換えてキャストを回避することができます。

             [!code-csharp[WhatsNew.Casting#2](../../../samples/snippets/csharp/VS_Snippets_CLR/whatsnew.casting/cs/program.cs#2)]
             [!code-vb[WhatsNew.Casting#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/whatsnew.casting/vb/module1.vb#2)]

    - **日付および時間と UNIX 時間の変換のサポート**

         日付値および時間値と UNIX 時間の変換をサポートするため、次の新しいメソッドが <xref:System.DateTimeOffset> 構造体に追加されました。

        - <xref:System.DateTimeOffset.FromUnixTimeSeconds%2A?displayProperty=nameWithType>

        - <xref:System.DateTimeOffset.FromUnixTimeMilliseconds%2A?displayProperty=nameWithType>

        - <xref:System.DateTimeOffset.ToUnixTimeSeconds%2A?displayProperty=nameWithType>

        - <xref:System.DateTimeOffset.ToUnixTimeMilliseconds%2A?displayProperty=nameWithType>

    - **互換性スイッチ**

         新しい <xref:System.AppContext> クラスは、ライブラリの作成者が統一された新機能のオプトアウト メカニズムをユーザーに提供できるようにする、新しい互換性機能を追加します。 これは、オプトアウト要求を伝達するために、コンポーネント間に疎結合のコントラクトを確立します。 通常、この機能は既存の機能が変更されるときに重要となります。 それに対して、新しい機能には暗黙のオプトインが既に存在しています。

         <xref:System.AppContext> によって、ライブラリは互換性スイッチを定義して公開します。また、それらに依存するコードは、それらのスイッチを設定してライブラリの動作に影響を与えることができます。 ライブラリは、既定では新しい機能を提供し、スイッチが設定されている場合のみそれを変更する (つまり以前の機能を提供する) ことができます。

         アプリケーション (またはライブラリ) は、依存するライブラリが定義したスイッチの値 (常に <xref:System.Boolean> 値) を宣言できます。 スイッチは常に暗黙的に `false` です。 スイッチを `true` に設定すると、それが有効になります。 スイッチを明示的に `false` に設定すると、新しい動作が提供されます。

        ```csharp
        AppContext.SetSwitch("Switch.AmazingLib.ThrowOnException", true);
        ```

         ライブラリは、コンシューマーがスイッチの値を宣言したことを確認してから、それを適切に実行する必要があります。

        ```csharp
        if (!AppContext.TryGetSwitch("Switch.AmazingLib.ThrowOnException", out shouldThrow)) 
        {
           // This is the case where the switch value was not set by the application. 
           // The library can choose to get the value of shouldThrow by other means. 
           // If no overrides nor default values are specified, the value should be 'false'. 
           // A false value implies the latest behavior.
        }

           // The library can use the value of shouldThrow to throw exceptions or not.
           if (shouldThrow) 
           {
              // old code
           }
           else {
              // new code
           }
        }
        ```

         スイッチは、ライブラリによって公開される正式なコントラクトであるため、一貫性のある形式を使用することをお勧めします。 2 つの明確な形式を次に示します。

        - *Switch*.*namespace*.*switchname*

        - *Switch*.*library*.*switchname*

    - **タスク ベースの非同期パターン (TAP) の変更点**

         [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] をターゲットとするアプリの場合、<xref:System.Threading.Tasks.Task> オブジェクトと <xref:System.Threading.Tasks.Task%601> オブジェクトは、呼び出し元のスレッドのカルチャと UI カルチャを継承します。 以前のバージョンの .NET Framework をターゲットするとアプリまたは特定のバージョンの .NET Framework をターゲットとしないアプリの動作には影響を及ぼしません。 詳細については、<xref:System.Globalization.CultureInfo> クラスのトピックの「カルチャとタスク ベースの非同期の操作」セクションをご覧ください。

         <xref:System.Threading.AsyncLocal%601?displayProperty=nameWithType> クラスを使用すると、`async` メソッドなど、特定の非同期制御フローに対してローカルなアンビエント データを表すことができます。 これは、スレッド間でデータを保持するために使用できます。 <xref:System.Threading.AsyncLocal%601.Value%2A?displayProperty=nameWithType> プロパティの明示的な変更やスレッドでのコンテキスト変換の発生などによってアンビエント データが変更されるたびに通知されるコールバック メソッドを定義することもできます。

         タスク ベースの非同期パターン (TAP) に、特定の状態で完了したタスクを返す 3 つの便利なメソッド <xref:System.Threading.Tasks.Task.CompletedTask%2A?displayProperty=nameWithType>、<xref:System.Threading.Tasks.Task.FromCanceled%2A?displayProperty=nameWithType>、および <xref:System.Threading.Tasks.Task.FromException%2A?displayProperty=nameWithType> が追加されました。

         <xref:System.IO.Pipes.NamedPipeClientStream> クラスで、新しい <xref:System.IO.Pipes.NamedPipeClientStream.ConnectAsync%2A> メソッドによる非同期通信がサポートされるようになりました。 メソッドをオーバーライドします。

    - **EventSource がイベント ログへの書き込みをサポート**

         コンピューター上で作成された既存の ETW セッションに加えて、<xref:System.Diagnostics.Tracing.EventSource> クラスを使用して管理または操作メッセージをイベント ログに記録できるようになりました。 以前は、この機能のために Microsoft.Diagnostics.Tracing.EventSource NuGet パッケージを使用する必要がありました。 この機能は .NET Framework 4.6 に組み込まれました。

         NuGet パッケージと .NET Framework 4.6 は、どちらも次の機能によって更新されています。

        - **ダイナミック イベント**

             イベント メソッドを作成せずに、実行時にイベントを定義できます。

        - **リッチ ペイロード**

             特別な属性が指定されたクラスや配列に加えて、プリミティブ型もペイロードとして渡すことができます。

        - **アクティビティの追跡**

             Start イベントと Stop イベントの間のイベントに、現在アクティブなすべてのアクティビティを表す ID が付けられます。

         これらの機能をサポートするため、<xref:System.Diagnostics.Tracing.EventSource> クラスにオーバーロードされた <xref:System.Diagnostics.Tracing.EventSource.Write%2A> メソッドが追加されました。

- **Windows Presentation Foundation (WPF)**

    - **HDPI の強化**

         [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] では、WPF での HDPI サポートが強化されました。 境界があるコントロールでのクリッピングの発生を減らすため、レイアウトの丸め処理が変更されました。 既定では、<xref:System.Runtime.Versioning.TargetFrameworkAttribute> が .NET 4.6 に設定されている場合にのみ、この機能が有効になります。  以前のバージョンの Framework を対象とするアプリケーションが [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] で実行される場合は、app.config ファイルの [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) セクションに次の行を追加することで、新しい動作を選択できます。

        ```xml
        <AppContextSwitchOverrides
        value="Switch.MS.Internal.DoNotApplyLayoutRoundingToMarginsAndBorderThickness=false"
        />
        ```

         異なる DPI 設定を持つ (マルチ DPI セットアップの) 複数のモニターにまたがる WPF ウィンドウは、ブラック アウト領域なしで完全にレンダリングされるようになりました。 この動作の選択を解除するには、app.config ファイルの `<appSettings>` セクションに次の行を追加して、この新しい動作を無効にします。

        ```xml
        <add key="EnableMultiMonitorDisplayClipping" value="true"/>
        ```

         DPI 設定に基づいて自動的に正しいカーソルを読み込む機能のサポートが <xref:System.Windows.Input.Cursor?displayProperty=nameWithType> に追加されました。

    - **タッチの改善**

         タッチで予期しない動作が発生するという、お客様から報告された [Connect](https://connect.microsoft.com/VisualStudio/feedback/details/903760/) の問題が [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] で対処されました。 Windows 8.1 以降では、Windows ストア アプリケーションと WPF アプリケーションのダブルタップのしきい値が同じになりました。

    - **透過的な子ウィンドウのサポート**

         [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] の WPF では、Windows 8.1 以降の透過的な子ウィンドウがサポートされます。 これにより、最上位レベルのウィンドウ内に四角形でない透過的な子ウィンドウを作成できます。 この機能を有効にするには、<xref:System.Windows.Interop.HwndSourceParameters.UsesPerPixelTransparency%2A?displayProperty=nameWithType> プロパティを `true` に設定します。

- **Windows Communication Foundation (WCF)**

    - **SSL のサポート**

         WCF で、NetTcp をトランスポート セキュリティおよびクライアント認証と共に使用する場合に、SSL のバージョンとして SSL 3.0 および TLS 1.0 に加えて TLS 1.1 および TLS 1.2 がサポートされるようになりました。 使用するプロトコルを選択することも、安全性の低い古いプロトコルを無効化することもできるようになりました。 これを行うには、<xref:System.ServiceModel.TcpTransportSecurity.SslProtocols%2A> プロパティを設定するか、または構成ファイルに以下を追加します。

        ```xml
        <netTcpBinding>
           <binding>
              <security mode= "None|Transport|Message|TransportWithMessageCredential" >
                 <transport clientCredentialType="None|Windows|Certificate"
                            protectionLevel="None|Sign|EncryptAndSign"
                            sslProtocols="Ssl3|Tls1|Tls11|Tls12">
                    </transport>
              </security>
           </binding>
        </netTcpBinding>
        ```

    - **異なる HTTP 接続によるメッセージの送信**

         WCF で、ユーザーが別の基になる HTTP 接続を使用して特定のメッセージを送信できるようになりました。 これには、2 つの方法があります。

        - **接続グループ名プレフィックスの使用**

             ユーザーは、WCF で接続グループ名のプレフィックスとして使用される文字列を指定できます。 異なるプレフィックスを持つ 2 つのメッセージは、別の基になる HTTP 接続を使用して送信されます。 プレフィックスを設定するには、メッセージの <xref:System.ServiceModel.Channels.Message.Properties%2A?displayProperty=nameWithType> プロパティにキー/値のペアを追加します。 キーは "HttpTransportConnectionGroupNamePrefix" で、値は使用するプレフィックスです。

        - **異なるチャネル ファクトリの使用**

             ユーザーは、異なるチャネル ファクトリによって作成されたチャネルを使用して送信されるメッセージで別の基になる HTTP 接続を使用する機能を有効にすることもできます。 この機能を有効にするには、ユーザーが次の `appSetting` を `true` に設定する必要があります。

            ```xml
            <appSettings>
               <add key="wcf:httpTransportBinding:useUniqueConnectionPoolPerFactory" value="true" />
            </appSettings>
            ```

- **Windows Workflow Foundation (WWF)**

     順序不定の操作要求がタイムアウトする前に未処理の "非プロトコル" ブックマークが存在する場合に、ワークフロー サービスが要求を保持する秒数を指定できるようになりました。 "非プロトコル" ブックマークとは、未処理の Receive アクティビティに関連付けられていないブックマークです。 一部のアクティビティはその実装内で非プロトコル ブックマークを作成するため、必ずしも非プロトコル ブックマークの存在が明らかにわかるとは限りません。 例として State や Pick などがあります。 ステート マシンを使用して実装されたワークフロー サービスや、Pick アクティビティを含むワークフロー サービスがある場合は、非プロトコル ブックマークが存在する可能性が高くなります。 この間隔を指定するには、app.config ファイルの `appSettings` セクションに次のような行を追加します。

    ```xml
    <add key="microsoft:WorkflowServices:FilterResumeTimeoutInSeconds" value="60"/>
    ```

     既定値は 60 秒です。 `value` を 0 に設定すると、順序不定の要求はただちに拒否され、次のようなテキストを含むエラーが返されます。

    ```
    Operation 'Request3|{http://tempuri.org/}IService' on service instance with identifier '2b0667b6-09c8-4093-9d02-f6c67d534292' cannot be performed at this time. Please ensure that the operations are performed in the correct order and that the binding in use provides ordered delivery guarantees. 
    ```

     これは、順序不定の操作メッセージを受信し、非プロトコル ブックマークが存在しない場合に受信するメッセージと同じです。

     `FilterResumeTimeoutInSeconds` 要素の値がゼロ以外で、非プロトコル ブックマークが存在し、タイムアウト間隔が終了した場合、その操作は失敗し、タイムアウト メッセージが発生します。

- **トランザクション**

     <xref:System.Transactions.TransactionException> から派生した例外がスローされる原因となったトランザクションに、分散トランザクション識別子を含めることができるようになりました。 これを行うには、次のキーを app.config ファイルの `appSettings` セクションに追加します。

    ```xml
    <add key="Transactions:IncludeDistributedTransactionIdInExceptionMessage" value="true"/> 
    ```

     既定値は `false` です。

- **ネットワーク**

    - **ソケットの再利用**

         Windows 10 には、送信 TCP 接続のローカル ポートを再利用してコンピューターのリソースを効率的に使用する新しいスケーラビリティの高いネットワーク アルゴリズムが含まれています。 .NET Framework 4.6 では、この新しいアルゴリズムがサポートされ、.NET アプリで新しい動作を利用できます。 以前のバージョンの Windows では、人工的な同時接続の制限 (通常は動的なポート範囲の既定のサイズである 16,384) があったため、負荷がかかったときにポートが使い尽くされ、サービスのスケーラビリティが制限されることがありました。

         [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] では、ポートの再利用を有効にする次の 2 つの新しい API が追加され、同時接続に対する 64K の制限が実質的になくなりました。

        - <xref:System.Net.Sockets.SocketOptionName?displayProperty=nameWithType> 列挙型値。

        - <xref:System.Net.ServicePointManager.ReusePort%2A?displayProperty=nameWithType> プロパティ。

         既定では、`HKLM\SOFTWARE\Microsoft\.NETFramework\v4.0.30319` レジストリ キーの `HWRPortReuseOnSocketBind` の値が 0x1 に設定されないかぎり、<xref:System.Net.ServicePointManager.ReusePort%2A?displayProperty=nameWithType> プロパティは `false` になります。 HTTP 接続でのローカル ポートの再利用を有効にするには、<xref:System.Net.ServicePointManager.ReusePort%2A?displayProperty=nameWithType> プロパティを `true` に設定します。 これにより、<xref:System.Net.Http.HttpClient> および <xref:System.Net.HttpWebRequest> からの外向きのすべての TCP ソケット接続で Windows 10 の新しいソケット オプション [SO_REUSE_UNICASTPORT](https://msdn.microsoft.com/library/windows/desktop/ms740532.aspx) が使用されるようになるため、ローカル ポートの再利用が可能になります。

         ソケット専用のアプリケーションを作成する開発者は、<xref:System.Net.Sockets.Socket.SetSocketOption%2A?displayProperty=nameWithType> などのメソッドを呼び出すときに <xref:System.Net.Sockets.SocketOptionName?displayProperty=nameWithType> オプションを指定することにより、送信ソケットでバインド中にローカル ポートを再利用できるようになります。

    - **国際ドメイン名と PunyCode のサポート**

         <xref:System.Uri> クラスに新しいプロパティ <xref:System.Uri.IdnHost%2A> が追加され、国際ドメイン名と PunyCode のサポートが強化されました。

- **Windows フォーム コントロールでのサイズ変更**

     この機能が [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] にも拡張されました。<xref:System.Windows.Forms.DomainUpDown>、<xref:System.Windows.Forms.NumericUpDown>、<xref:System.Windows.Forms.DataGridViewComboBoxColumn>、<xref:System.Windows.Forms.DataGridViewColumn>、<xref:System.Windows.Forms.ToolStripSplitButton> 型、および <xref:System.Drawing.Design.UITypeEditor> を描画するときに使用する <xref:System.Drawing.Design.PaintValueEventArgs.Bounds%2A> プロパティで指定される四角形も含まれるようになりました。

     これはオプトイン機能です。 この機能を有効にするには、アプリケーション構成 (app.config) ファイルで `EnableWindowsFormsHighDpiAutoResizing` 要素を `true` に設定します。

    ```xml
    <appSettings>
       <add key="EnableWindowsFormsHighDpiAutoResizing" value="true" />
    </appSettings>
    ```

- **コード ページのエンコーディングのサポート**

      [!INCLUDE[net_core](../../../includes/net-core-md.md)] primarily supports the Unicode encodings and by default provides limited support for code page encodings. You can add support for code page encodings available in the .NET Framework but unsupported in [!INCLUDE[net_core](../../../includes/net-core-md.md)] by registering code page encodings with the <xref:System.Text.Encoding.RegisterProvider%2A?displayProperty=nameWithType> method. For more information, see <xref:System.Text.CodePagesEncodingProvider?displayProperty=nameWithType>.

- **.NET ネイティブ**

     [!INCLUDE[net_core](../../../includes/net-core-md.md)] をターゲットとし、c# または Visual Basic で作成されている Windows 10 用の Windows アプリは、IL ではなくネイティブ コードにアプリをコンパイルする新しい技術を活用できます。 これで、起動時間と実行時間がより速いアプリを生成できます。 詳しくは、「[.NET ネイティブによるアプリのコンパイル](../../../docs/framework/net-native/index.md)」をご覧ください。 JIT コンパイルと NGEN による結果の違い、およびコードにおけるその影響の概要については、「[.NET ネイティブとコンパイル](../../../docs/framework/net-native/net-native-and-compilation.md)」をご覧ください。

     アプリは、Visual Studio 2015 でコンパイルするときに、既定でネイティブ コードにコンパイルされます。 詳しくは、「[.NET ネイティブの概要](../../../docs/framework/net-native/getting-started-with-net-native.md)」をご覧ください。

     .NET ネイティブ アプリのデバッグをサポートするため、アンマネージ デバッグ APIに対して数多くの新しいインターフェイスと列挙型が追加されました。 詳しくは、「[デバッグ (アンマネージ API リファレンス)](../../../docs/framework/unmanaged-api/debugging/index.md)」をご覧ください。

- **オープン ソースの .NET Framework パッケージ**

      [!INCLUDE[net_core](../../../includes/net-core-md.md)] packages such as the immutable collections, [SIMD APIs](http://go.microsoft.com/fwlink/?LinkID=518639), and networking APIs such as those found in the <xref:System.Net.Http> namespace are now available as open source packages on [GitHub](https://github.com/). To access the code, see [NetFx on GitHub](http://go.microsoft.com/fwlink/?LinkID=518634). For more information and how to contribute to these packages, see [.NET Core and Open-Source](../../../docs/framework/get-started/net-core-and-open-source.md), [.NET Home Page on GitHub](http://go.microsoft.com/fwlink/?LinkID=518635).

 [ページのトップへ](#introduction)

<a name="v452"></a> 
## <a name="whats-new-in-the-net-framework-452"></a>.NET Framework 4.5.2 の新機能

- **ASP.NET アプリ用の新しい API。** 新しい <xref:System.Web.HttpResponse.AddOnSendingHeaders%2A?displayProperty=nameWithType> メソッドと <xref:System.Web.HttpResponseBase.AddOnSendingHeaders%2A?displayProperty=nameWithType> メソッドにより、応答がクライアント アプリにフラッシュされる際の、応答ヘッダーと状態コードを確認および変更できます。 <xref:System.Web.HttpApplication.PreSendRequestHeaders> イベントや <xref:System.Web.HttpApplication.PreSendRequestContent> イベントの代わりに、より効率的で信頼性の高いこれらのメソッドの使用を検討してください。

     <xref:System.Web.Hosting.HostingEnvironment.QueueBackgroundWorkItem%2A?displayProperty=nameWithType> メソッドにより、小さなバックグラウンド作業項目をスケジュールできます。 ASP.NET はこれらの項目を追跡し、すべてのバックグラウンド作業項目が完了するまで IIS が突然ワーカー プロセスを終了しないようにします。 このメソッドは、ASP.NET マネージ アプリ ドメインの外部で呼び出すことはできません。

     新しい <xref:System.Web.HttpResponse.HeadersWritten?displayProperty=nameWithType> プロパティと <xref:System.Web.HttpResponseBase.HeadersWritten?displayProperty=nameWithType> プロパティは、応答ヘッダーが書き込まれたかどうかを示すブール値を返します。 これらのプロパティを使用して、<xref:System.Web.HttpResponse.StatusCode%2A?displayProperty=nameWithType> (ヘッダーが書き込まれた場合に例外をスローする) などの API への呼び出しが成功することを確認できます。

- **Windows フォーム コントロールでのサイズ変更** この機能が拡張されました。 これにより、システム DPI 設定を使用して、次の追加コントロールのコンポーネント (例: コンボ ボックスのドロップダウン矢印) をサイズ変更できます。

     <xref:System.Windows.Forms.ComboBox> <xref:System.Windows.Forms.ToolStripComboBox> <xref:System.Windows.Forms.ToolStripMenuItem> <xref:System.Windows.Forms.Cursor> <xref:System.Windows.Forms.DataGridView> <xref:System.Windows.Forms.DataGridViewComboBoxColumn>

     これはオプトイン機能です。 この機能を有効にするには、アプリケーション構成 (app.config) ファイルで `EnableWindowsFormsHighDpiAutoResizing` 要素を `true` に設定します。

    ```xml
    <appSettings>
       <add key="EnableWindowsFormsHighDpiAutoResizing" value="true" />
    </appSettings>
    ```

- **新しいワークフロー機能。** <xref:System.Transactions.Transaction.EnlistPromotableSinglePhase%2A> メソッドを使用している (および、結果として <xref:System.Transactions.IPromotableSinglePhaseNotification> インターフェイスを実装している) リソース マネージャーは、新しい <xref:System.Transactions.Transaction.PromoteAndEnlistDurable%2A?displayProperty=nameWithType> メソッドを使用して、次の事柄を要求できます。

    - トランザクションを Microsoft 分散トランザクション コーディネーター (MSDTC) トランザクションに昇格する。

    - <xref:System.Transactions.IPromotableSinglePhaseNotification> を <xref:System.Transactions.ISinglePhaseNotification> (単一フェーズのコミットをサポートする永続的登録リスト) に置き換えます。

     これは同じアプリ ドメイン内で実行でき、MSDTC とやり取りして昇格を実行するためにアンマネージ コードを追加する必要はありません。 <xref:System.Transactions?displayProperty=nameWithType> から昇格可能な登録リストにより実装された <xref:System.Transactions.IPromotableSinglePhaseNotification>`Promote` メソッドへの未処理の呼び出しがある場合のみ、この新しいメソッドを呼び出すことができます。

- **プロファイリングの機能強化。** 次の新しいアンマネージ プロファイリング API により、さらに信頼性の高いプロファイリングを提供します。

     [COR_PRF_ASSEMBLY_REFERENCE_INFO 構造体](../../../docs/framework/unmanaged-api/profiling/cor-prf-assembly-reference-info-structure.md) [COR_PRF_HIGH_MONITOR 列挙型](../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md) [GetAssemblyReferences メソッド](../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) [GetEventMask2 メソッド](../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-geteventmask2-method.md) [SetEventMask2 メソッド](../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) [AddAssemblyReference メソッド](../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-addassemblyreference-method.md)

     以前の `ICorProfiler` の実装は、依存アセンブリの遅延読み込みをサポートしていました。 新しいプロファイリング API では、プロファイラーにより挿入される依存アセンブリを、アプリの完全な初期化後に読み込むのではなく、すぐに読み込む必要があります。 この変更は、既存の `ICorProfiler` API のユーザーには影響しません。

- **デバッグの機能強化。** 次の新しいアンマネージド デバッグ API により、プロファイラーとの統合性が向上しました。 これにより、ダンプのデバッグ時にコンパイラ ReJIT 要求により作成されたローカル変数やコードだけでなく、プロファイラーにより挿入されたメタデータにアクセスできます。

     [SetWriteableMetadataUpdateMode メソッド](../../../docs/framework/unmanaged-api/debugging/icordebugprocess7-setwriteablemetadataupdatemode-method.md) [EnumerateLocalVariablesEx メソッド](../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-enumeratelocalvariablesex-method.md) [GetLocalVariableEx メソッド](../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-getlocalvariableex-method.md) [GetCodeEx メソッド](../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-getcodeex-method.md) [GetActiveReJitRequestILCode メソッド](../../../docs/framework/unmanaged-api/debugging/icordebugfunction3-getactiverejitrequestilcode-method.md) [GetInstrumentedILMap メソッド](../../../docs/framework/unmanaged-api/debugging/icordebugilcode2-getinstrumentedilmap-method.md)

- **イベント トレーシングの変更。** .NET Framework 4.5.2 では、より大きなサーフェイス領域において、アウトプロセスの Windows イベント トレーシング (ETW) に基づくアクティビティ トレーシングができるようになりました。 これにより、アドバンスト パワー マネージメント (APM) ベンダーは、スレッドを越えた個々の要求とアクティビティのコストを正確に追跡する軽量ツールを提供できます。  これらのイベントは、ETW コントローラーで有効にされた場合にのみ発生します。したがって、変更は以前に記述された ETW コードや ETW が無効な状態で実行されるコードには影響しません。

- **トランザクションの昇格と永続参加リストへの変換**

     <xref:System.Transactions.Transaction.PromoteAndEnlistDurable%2A?displayProperty=nameWithType> は、.NET Framework 4.5.2 および 4.6 に追加された新しい API です。

    ```csharp
    [System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name = "FullTrust")]
    public Enlistment PromoteAndEnlistDurable(Guid resourceManagerIdentifier,
                                              IPromotableSinglePhaseNotification promotableNotification,
                                              ISinglePhaseNotification enlistmentNotification,
                                              EnlistmentOptions enlistmentOptions)
    ```

     このメソッドは、以前に <xref:System.Transactions.ITransactionPromoter.Promote%2A?displayProperty=nameWithType> メソッドへの応答として <xref:System.Transactions.Transaction.EnlistPromotableSinglePhase%2A?displayProperty=nameWithType> によって作成された参加リストで使用できます。 これは、`System.Transactions` に対して、トランザクションを MSDTC トランザクションに昇格させ、昇格可能参加リストを永続参加リストに "変換" するように要求します。 このメソッドが正常に完了すると、<xref:System.Transactions.IPromotableSinglePhaseNotification> インターフェイスが `System.Transactions` から参照されなくなり、その後の通知は指定された <xref:System.Transactions.ISinglePhaseNotification> インターフェイスに到着します。 問題の参加リストは、永続参加リストとして機能し、トランザクションのログ記録と復旧をサポートする必要があります。 詳細については、<xref:System.Transactions.Transaction.EnlistDurable%2A?displayProperty=nameWithType> を参照してください。 さらに、この参加リストは <xref:System.Transactions.ISinglePhaseNotification> もサポートする必要があります。  このメソッドは、<xref:System.Transactions.ITransactionPromoter.Promote%2A?displayProperty=nameWithType> の呼び出しの処理中に*のみ*呼び出すことができます。 そうでない場合は、<xref:System.Transactions.TransactionException> 例外がスローされます。

 [ページのトップへ](#introduction)

<a name="v451"></a> 
## <a name="whats-new-in-the-net-framework-451"></a>.NET Framework 4.5.1 の新機能
 **2014 年 4 月の更新**:

- [Visual Studio 2013 更新プログラム 2](http://go.microsoft.com/fwlink/p/?LinkId=393658) には、次のシナリオをサポートするポータブル クラス ライブラリ テンプレートの更新が含まれています。

    - Windows 8.1、Windows Phone 8.1、および Windows Phone Silverlight 8.1 を対象とするポータブル ライブラリで Windows ランタイム API を使用できます。

    - Windows 8.1 または Windows Phone 8.1 を対象とする場合、ポータブル ライブラリに XAML (Windows.UI.XAML 型) を含めることができます。 次の XAML テンプレートがサポートされています。空白のページ、リソース ディクショナリ、テンプレート コントロール、およびユーザー コントロール。

    - Windows 8.1 および Windows Phone 8.1 を対象とするストア アプリで使用するためにポータブル Windows ラインタイム コンポーネント (.winmd ファイル) を作成できます。

    - ポータブル クラス ライブラリのような Windows ストアまたは Windows Phone ストア クラス ライブラリを再ターゲットできます。

     これらの変更の詳細については、[ポータブル クラス ライブラリ](../../../docs/standard/cross-platform/cross-platform-development-with-the-portable-class-library.md)に関するページを参照してください。

- .NET Framework のコンテンツ セットには、Windows アプリをビルドして配置するためのプリコンパイル テクノロジである [!INCLUDE[net_native](../../../includes/net-native-md.md)] のドキュメントが含まれます。 [!INCLUDE[net_native](../../../includes/net-native-md.md)] は、中間言語 (IL) ではなくネイティブ コードへアプリを直接コンパイルすることにより、パフォーマンスを向上させます。 詳しくは、「[.NET ネイティブによるアプリのコンパイル](../../../docs/framework/net-native/index.md)」をご覧ください。

- [.NET Framework Reference Source](http://referencesource.microsoft.com/) で、新しい参照エクスペリエンスと強化された機能が提供されます。 これにより、.NET Frameworkのソース コードをオンラインで参照したり、[リファレンスをダウンロード](http://referencesource.microsoft.com/download.html)してオフラインで表示したりできます。さらに、デバッグ中にソース (パッチや更新を含む) をステップ実行できます。 詳細については、ブログ記事「[A new look for .NET Reference Source (.NET Reference Source の新しい外観)](https://blogs.msdn.microsoft.com/dotnet/2014/02/24/a-new-look-for-net-reference-source/)」を参照してください。

 .NET Framework 4.5.1 のコア機能の新機能と機能強化には次が含まれます。

- アセンブリの自動バインディング リダイレクト。 [!INCLUDE[vs_dev12](../../../includes/vs-dev12-md.md)] 以降では、アプリまたはそのコンポーネントが同じアセンブリの複数バージョンを参照している場合、[!INCLUDE[net_v451](../../../includes/net-v451-md.md)] を対象とするアプリのコンパイル時に、バインディング リダイレクトをアプリ構成ファイルに追加できます。 また、.NET Framework の以前のバージョンを対象とするプロジェクトで、この機能を有効にすることもできます。 詳しくは、「[方法: 自動バインディング リダイレクトを有効/無効にする](../../../docs/framework/configure-apps/how-to-enable-and-disable-automatic-binding-redirection.md)」をご覧ください。

- 開発者がサーバーおよびクラウド アプリケーションのパフォーマンスを向上するために役立つ診断情報を収集する機能。 詳細については、<xref:System.Diagnostics.Tracing.EventSource.WriteEventWithRelatedActivityId%2A> クラスの <xref:System.Diagnostics.Tracing.EventSource.WriteEventWithRelatedActivityIdCore%2A> メソッドと <xref:System.Diagnostics.Tracing.EventSource> メソッドを参照してください。

- ガベージ コレクション中に大きなオブジェクト ヒープ (LOH) を圧縮する機能。 詳細については、<xref:System.Runtime.GCSettings.LargeObjectHeapCompactionMode%2A?displayProperty=nameWithType> プロパティを参照してください。

- その他のパフォーマンス向上 (ASP.NET アプリの中断、マルチコア JIT の改良、.NET Framework 更新後のアプリ起動時間の短縮など)。 詳細については、ブログ記事「[.NET Framework 4.5.1 announcement](https://blogs.msdn.microsoft.com/dotnet/2013/06/26/announcing-the-net-framework-4-5-1-preview/)」(.NET Framework 4.5.1 についてのお知らせ) および「[ASP.NET app suspend](https://blogs.msdn.microsoft.com/dotnet/2013/10/09/asp-net-app-suspend-responsive-shared-net-web-hosting/)」 (ASP.NET アプリケーションの中断) を参照してください。

 Windows フォームの機能強化には次が含まれます。

- Windows フォーム コントロールでのサイズ変更。 アプリのアプリケーション構成ファイル (app.config) 内のエントリで有効にすることにより、システム DIP 設定を使用してコントロールのコンポーネント (例: プロパティ グリッドに表示されるアイコン) をサイズ変更できます。 現在、この機能は次の Windows フォーム コントロールでサポートされています。

     <xref:System.Windows.Forms.PropertyGrid> <xref:System.Windows.Forms.TreeView> <xref:System.Windows.Forms.DataGridView> の一部 (サポートされている追加コントロールについては、「[4.5.2 の新機能](#v452)」を参照してください)

     この機能を有効にするには、構成ファイル (app.config) に新しい \<appSettings> 要素を追加し、`EnableWindowsFormsHighDpiAutoResizing` 要素を `true` に設定します。

    ```xml
    <appSettings>
       <add key="EnableWindowsFormsHighDpiAutoResizing" value="true" />
    </appSettings>
    ```

 [!INCLUDE[vs_dev12](../../../includes/vs-dev12-md.md)] で .NET Framework アプリをデバッグするときの改善点は次のとおりです。

- Visual Studio デバッガーの戻り値。 [!INCLUDE[vs_dev12](../../../includes/vs-dev12-md.md)] でマネージ アプリをデバッグする場合、メソッドの戻り値の型と値が [自動変数] ウィンドウに表示されます。 デスクトップ アプリ、Windows ストア アプリ、Windows Phone アプリについて、この情報を使用できます。 詳細については、MSDN ライブラリの「[メソッド呼び出しの戻り値の調査](http://msdn.microsoft.com/library/e3245b37-8e2e-4200-ba84-133726e95f1f\(v=vs.120\).aspx)」を参照してください。

- 64 ビット アプリのエディット コンティニュ。 [!INCLUDE[vs_dev12](../../../includes/vs-dev12-md.md)] では、デスクトップ、Windows ストア、Windows Phone 用の 64 ビット マネージ アプリについて、エディット コンティニュ機能がサポートされています。 既存の制限は、32 ビット アプリと 64 ビット アプリの両方でまだ有効です (「[Supported Code Changes (C#)](/visualstudio/debugger/supported-code-changes-csharp)」(サポートされているコードの変更 (C#)) の記事の最後のセクションを参照してください)。

- 非同期対応のデバッグ。 [!INCLUDE[vs_dev12](../../../includes/vs-dev12-md.md)] で非同期アプリを簡単にデバッグするために、呼び出し履歴には、非同期プログラミングをサポートするためにコンパイラに用意されているインフラストラクチャ コード、および論理上の親フレーム内のチェーンが表示されません。これにより、論理的なプログラムの実行をよりわかりやすく行うことができます。 [タスク] ウィンドウが [並列タスク] ウィンドウに代わって使用され、特定のブレークポイントに関連するタスクが表示されます。また、現在アクティブなタスクやアプリでスケジュールされているタスクなども表示されます。 この機能については、「[.NET Framework 4.5.1 announcement](https://blogs.msdn.microsoft.com/dotnet/2013/06/26/announcing-the-net-framework-4-5-1-preview/)」(.NET Framework 4.5.1 についてのお知らせ) の「Async-aware debugging」(非同期対応のデバッグ) セクションを参照してください。

- Windows ランタイム コンポーネント向けのより適切な例外処理のサポート。 [!INCLUDE[win81](../../../includes/win81-md.md)] では、言語の種類に関係なく、Windows ストア アプリから発生する例外には、例外を発生させたエラーに関する情報が保持されます。 この機能については、「[.NET Framework 4.5.1 announcement](https://blogs.msdn.microsoft.com/dotnet/2013/06/26/announcing-the-net-framework-4-5-1-preview/)」(.NET Framework 4.5.1 についてのお知らせ) の「Windows Store app development」(Windows ストア アプリ開発) のセクションを参照してください。 

 [!INCLUDE[vs_dev12](../../../includes/vs-dev12-md.md)] 以降では、[Mpgo.exe (マネージ プロファイル ガイド付き最適化ツール)](../../../docs/framework/tools/mpgo-exe-managed-profile-guided-optimization-tool.md) を使用して、[!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] アプリとデスクトップ アプリを最適化することができます。

 ASP.NET 4.5.1 の新機能については、ASP.NET サイトの「[ASP.NET 4.5.1 and Visual Studio 2013](http://go.microsoft.com/fwlink/?LinkID=309094)」(ASP.NET 4.5.1 および Visual Studio 2013) を参照してください。

 [ページのトップへ](#introduction)

<a name="v45"></a> 
## <a name="whats-new-in-the-net-framework-45"></a>.NET Framework 4.5 の新機能

### <a name="core-new-features-and-improvements"></a>コア機能の新機能と機能強化

- 配置時に .NET Framework 4 アプリケーションを検出して終了することにより、システムの再起動を減らす機能。 「[.NET Framework 4.5 のインストール中のシステム再起動の削減](../../../docs/framework/deployment/reducing-system-restarts.md)」をご覧ください。

- 64 ビット プラットフォームでの 2 ギガバイト (GB) を超える配列のサポート。 この機能は、アプリケーション構成ファイルで有効にすることができます。 「[\<gcAllowVeryLargeObjects> 要素](../../../docs/framework/configure-apps/file-schema/runtime/gcallowverylargeobjects-element.md)」も参照してください。オブジェクト サイズと配列サイズに関する他の制限も記載されています。

- サーバーのガベージ コレクションをバックグラウンドで行うことにより、パフォーマンスを改善します。 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] でサーバーのガベージ コレクションを使用すると、バックグラウンド ガベージ コレクションが自動的に有効になります。 「[Fundamentals of Garbage Collection](../../../docs/standard/garbage-collection/fundamentals.md)」(ガベージ コレクションの基礎) トピックの「バックグラウンド サーバー ガベージ コレクション」というセクションをご覧ください。

- マルチコア プロセッサでオプションで使用できるバックグラウンドの Just-in-time (JIT) コンパイルを使用すると、アプリケーションのパフォーマンスが向上します。 「<xref:System.Runtime.ProfileOptimization>」を参照してください。

- 正規表現エンジンがタイムアウトする前に、正規表現の解決を試みる時間に制限を設ける機能。<xref:System.Text.RegularExpressions.Regex.MatchTimeout%2A?displayProperty=nameWithType> プロパティを参照してください。

- アプリケーション ドメインの既定のカルチャを定義する機能。 詳細については、<xref:System.Globalization.CultureInfo> クラスのトピックを参照してください。

- Unicode UTF-16 エンコードのコンソール サポート。 詳細については、<xref:System.Console> クラスのトピックを参照してください。

- カルチャに従った文字列の順序のバージョン指定と比較データのサポート。 詳細については、<xref:System.Globalization.SortVersion> クラスのトピックを参照してください。

- リソースを取得するときのパフォーマンスを改善します。 「[リソースのパッケージ化と配置](../../../docs/framework/resources/packaging-and-deploying-resources-in-desktop-apps.md)」を参照してください。

- Zip 圧縮の機能強化により、圧縮ファイルのサイズが小さくなりました。 <xref:System.IO.Compression?displayProperty=nameWithType> 名前空間を参照してください。

- <xref:System.Reflection.Context.CustomReflectionContext> クラスを使用して、既定のリフレクションの動作をオーバーライドするリフレクション コンテキストをカスタマイズできる機能。

- <xref:System.Globalization.IdnMapping?displayProperty=nameWithType> クラスを [!INCLUDE[win8](../../../includes/win8-md.md)] で使用した場合の IDNA (Internationalized Domain Names in Applications) 規格の 2008 バージョンのサポート。

- オペレーティング システムへの文字列比較の処理代行。.NET Framework を [!INCLUDE[win8](../../../includes/win8-md.md)] で使用したときに、Unicode 6.0 が実装されます。 他のプラットフォームで実行されている場合、.NET Framework には、Unicode 5.x. を実装する独自の文字列比較データが含まれています。 <xref:System.String> クラスおよび <xref:System.Globalization.SortVersion> クラスの「コメント」セクションを参照してください。

- アプリケーション ドメインごとに文字列のハッシュ コードを計算する機能。 「[\<UseRandomizedStringHashAlgorithm> 要素](../../../docs/framework/configure-apps/file-schema/runtime/userandomizedstringhashalgorithm-element.md)」をご覧ください。

- <xref:System.Type> クラスと <xref:System.Reflection.TypeInfo> クラスで、タイプ リフレクションのサポートが分割されました。 「[Reflection in the .NET Framework for Windows Store Apps](../../../docs/framework/reflection-and-codedom/reflection-for-windows-store-apps.md)」(Windows ストア アプリのための .NET Framework のリフレクション) をご覧ください。

### <a name="managed-extensibility-framework-mef"></a>MEF (Managed Extensibility Framework)
 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] では、MEF (Managed Extensibility Framework) に次の新機能が用意されています。

- ジェネリック型のサポート。

- 属性ではなく命名規則に基づいてパーツを作成できるようにする、規則ベースのプログラミング モデル。

- 複数のスコープ。

- [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] アプリを作成するときに使用できる MEF のサブセット。 このサブセットは、[ダウンロード可能パッケージ](http://go.microsoft.com/fwlink/?LinkId=256238)として NuGet ギャラリーから入手できます。 パッケージをインストールするには、Visual Studio でプロジェクトを開き、**[プロジェクト]** メニューの **[NuGet パッケージの管理]** をクリックし、`Microsoft.Composition` パッケージをオンラインで検索します。

 詳しくは、「[Managed Extensibility Framework (MEF)](../../../docs/framework/mef/index.md)」を参照してください。

### <a name="asynchronous-file-operations"></a>非同期のファイル操作
 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]では、新しい非同期機能が C# および Visual Basic 言語に追加されました。 これらの機能は、非同期操作を実行するためのタスク ベースのモデルを追加します。 この新しいモデルを使用するには、I/O クラスで非同期メソッドを使用します。 「[非同期ファイル I/O](../../../docs/standard/io/asynchronous-file-i-o.md)」を参照してください。

<a name="tools"></a> 
### <a name="tools"></a>ツール
 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] では、リソース ファイル ジェネレーター (Resgen.exe) を使用すると、.NET Framework アセンブリに埋め込まれた .resources ファイルから [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] アプリ用の .resw ファイルを作成することができます。 詳しくは、「[Resgen.exe (リソース ファイル ジェネレーター)](../../../docs/framework/tools/resgen-exe-resource-file-generator.md)」をご覧ください。

 マネージ プロファイル ガイド付き最適化ツール (Mpgo.exe) を使用すると、ネイティブ イメージ アセンブリを最適化することによって、アプリケーションの起動時間、メモリの使用率 (ワーキング セットのサイズ)、およびスループットを向上させることができます。 このコマンド ライン ツールは、ネイティブ イメージ アプリケーション アセンブリ用のプロファイル データを生成します。 「[Mpgo.exe (マネージ プロファイル ガイド付き最適化ツール)](../../../docs/framework/tools/mpgo-exe-managed-profile-guided-optimization-tool.md)」をご覧ください。 [!INCLUDE[vs_dev12](../../../includes/vs-dev12-md.md)] 以降では、[!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] アプリおよびデスクトップ アプリを最適化するために、Mpgo.exe を使用できます。

<a name="parallel"></a> 
### <a name="parallel-computing"></a>並列コンピューティング
 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] では、並列計算用にいくつかの新機能と機能強化が提供されています。 パフォーマンスの向上、コントロールの強化、非同期プログラミングのサポートの改善、新しいデータフロー ライブラリ、並列デバッグとパフォーマンス分析のためのサポートの強化などが挙げられます。 ブログ「Parallel Programming with .NET」(.NET での並列プログラミング) の記事「[What’s New for Parallelism in .NET 4.5](http://go.microsoft.com/fwlink/?LinkId=235061)」(.NET 4.5 での並列処理の新機能) を参照してください。

<a name="web"></a> 
### <a name="web"></a>Web
 ASP.NET 4.5 および 4.5.1 では、Web フォーム モデルのバインディング、WebSocket のサポート、非同期ハンドラー、パフォーマンスの向上などの多くの機能が追加されています。 詳細については、次のリソースを参照してください。

- MSDN ライブラリの「[ASP.NET 4.5 および Visual Studio 2012](http://msdn.microsoft.com/library/ac9bb7f6-f094-4af7-bad0-acf49a5dbc55)」。

- ASP.NET のサイトの [ASP.NET 4.5.1 および Visual Studio 2013](http://go.microsoft.com/fwlink/?LinkID=309094)に関するページ。

<a name="networking"></a> 
### <a name="networking"></a>ネットワーキング
 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] は、HTTP アプリケーションに新しいプログラミング インターフェイスを提供します。 詳細については、新しい <xref:System.Net.Http?displayProperty=nameWithType> 名前空間と <xref:System.Net.Http.Headers?displayProperty=nameWithType> 名前空間を参照してください。

 既存の <xref:System.Net.HttpListener> と関連クラスを使用して WebSocket 接続を受け入れ、やり取りするための新しいプログラミング インターフェイスのサポートも含まれています。 詳細については、新しい <xref:System.Net.WebSockets> 名前空間と <xref:System.Net.HttpListener> クラスを参照してください。

 また [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] には、次のネットワークの機能強化が含まれています。

- RFC 準拠の URI サポート。 詳細については、<xref:System.Uri> および関連クラスを参照してください。

- 国際化ドメイン名 (IDN: Internationalized Domain Name) による解析のサポート。 詳細については、<xref:System.Uri> および関連クラスを参照してください。

- 電子メール アドレスの国際化 (EAI) のサポート。 詳細については、「<xref:System.Net.Mail>」を参照してください。

- 強化された IPv6 サポート。 詳細については、「<xref:System.Net.NetworkInformation>」を参照してください。

- デュアル モードのソケットのサポート。 詳細については、<xref:System.Net.Sockets.Socket> クラスおよび <xref:System.Net.Sockets.TcpListener> クラスを参照してください。

<a name="client"></a> 
### <a name="windows-presentation-foundation-wpf"></a>Windows Presentation Foundation (WPF)
 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] では、WPF (Windows Presentation Foundation) の次の領域の機能が変更および強化されています。

- クイック アクセス ツール バー、アプリケーション メニューおよびタブをホストするリボン ユーザー インターフェイスを実装できる新しい <xref:System.Windows.Controls.Ribbon.Ribbon> コントロール。

- 同期および非同期のデータ検証をサポートする新しい <xref:System.ComponentModel.INotifyDataErrorInfo> インターフェイス。

- <xref:System.Windows.Controls.VirtualizingPanel> および <xref:System.Windows.Threading.Dispatcher> クラスの新しい機能。

- グループ化された大量のデータを表示するときに、非 UI スレッドのコレクションにアクセスすることによってパフォーマンスを向上。

- 静的プロパティへのデータ バインディング、<xref:System.Reflection.ICustomTypeProvider> インターフェイスを実装するカスタム型へのデータ バインディング、およびバインディング式からのデータ バインディング情報の取得。

- 値の変更に伴うデータの再配置 (ライブ形成)。

- 項目コンテナーのデータ コンテキストを切断するかどうかをチェックする機能。

- プロパティの変更とデータ ソースの更新までの経過時間を設定する機能。

- 弱いイベント パターン実装時のサポートの強化。 また、イベントでマークアップ拡張機能を使用することもできるようになりました。

<a name="windows_communication_foundation"></a> 
### <a name="windows-communication-foundation-wcf"></a>Windows Communication Foundation (WCF)
 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]では、Windows Communication Foundation (WCF) アプリケーションの記述と保守を簡単にするため、次の機能が追加されました。

- 生成された構成ファイルの簡略化。

- コントラクト優先開発のサポート。

- ASP.NET 互換モードをより簡単に構成できる機能。

- 既定のトランスポート プロパティ値に変更を加え、設定しなければならない可能性を低減しました。

- <xref:System.Xml.XmlDictionaryReaderQuotas> クラスを更新して、XML ディクショナリ リーダーのクォータを手動で構成する手間を省けるようにしました。

- ビルド処理の一部として Visual Studio による WCF 構成ファイルを検証することで、アプリケーションを実行する前に構成エラーを検出できます。

- 新しい非同期ストリーミングのサポート。

- Internet Information Services (IIS) での HTTPS 上のエンドポイントを公開しやすくする新しい HTTPS プロトコル マッピング。

- `?singleWSDL` をサービス URL に追加して 1 つの WSDL ドキュメントのメタデータを生成する機能。

- TCP トランスポートと同様のパフォーマンス特性を持つポート 80 と 443 で真の双方向通信を可能にする Websockets のサポート。

- コード内の構成サービスのサポート。

- XML エディターのツール ヒント。

- <xref:System.ServiceModel.ChannelFactory> キャッシュのサポート。

- バイナリ エンコーダーの圧縮サポート。

- 開発者が「ファイア アンド フォーゲット (撃ち放し)」メッセージングを使用するサービスを作成できるようにする UDP トランスポートのサポート。 クライアントは、サービスにメッセージを送信しますが、サービスからの応答を期待しません。

- HTTP トランスポートとトランスポート セキュリティを使用したときに、単一の WCF エンドポイントで複数の認証モードをサポートする機能。

- 国際化ドメイン名 (IDN: Internationalized Domain Name) を使用する WCF サービスのサポート。

 詳細については、「[Windows Communication Foundation 4.5 の新機能](http://go.microsoft.com/fwlink/?LinkId=228173)」を参照してください。

<a name="windows_workflow_foundation"></a> 
### <a name="windows-workflow-foundation-wf"></a>Windows Workflow Foundation (WF)
 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] では、次に示すようないくつかの新しい機能が Windows Workflow Foundation (WF) に追加されました。

- 最初に .NET Framework 4.0.1 ([.NET Framework 4 Platform Update 1](http://go.microsoft.com/fwlink/?LinkID=215092)) の一部として導入された、ステート マシンのワークフロー。 この更新プログラムには、開発者がステート マシン ワークフローを作成できるようにする新しいクラスとアクティビティが複数含まれていました。 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] では、これらのクラスとアクティビティが、次を含むように更新されました。

    - 状態でブレークポイントを設定する機能。

    - ワークフロー デザイナーで遷移をコピーして貼り付ける機能。

    - 共有されるトリガーの遷移作成のデザイナー サポート。

    - <xref:System.Activities.Statements.StateMachine>、 <xref:System.Activities.Statements.State>、および <xref:System.Activities.Statements.Transition> などのようにステート マシン ワークフローを作成する機能。

- 次のようなワークフロー デザイナーの機能が強化されました。

    - **[クイック検索]** や **[フォルダーを指定して検索]** など、Visual Studio で強化されたワークフロー検索機能。

    - 2 番目の子アクティビティがコンテナー アクティビティに追加されたときに、自動的にシーケンス アクティビティを作成し、両方のアクティビティをシーケンス アクティビティに含める機能。

    - スクロール バーを使用せずに変更されるワークフローの表示部分を変更できるようにするパン サポート。

    - ツリー スタイルのアウトライン ビューでワークフローのコンポーネントを表示し、**[ドキュメント アウトライン]** ビューでコンポーネントを選択できるようにする新しい **[ドキュメント アウトライン]** ビュー。

    - アクティビティに注釈を追加できる機能。

    - ワークフロー デザイナーでアクティビティ デリゲートを定義および使用する機能。

    - ステート マシンのアクティビティと遷移、およびフローチャート ワークフローの自動接続と自動挿入。

- ワークフローのビュー状態情報を XAML ファイルの 1 つの要素に保管して、ビュー状態情報を簡単に見つけ、編集できるようにします。

- 子アクティビティの永続化を防ぐ NoPersistScope コンテナー アクティビティ。

- C# 式のサポート: 

    - Visual Basic を使用するワークフロー プロジェクトは、Visual Basic 式を使用し、C# ワークフロー プロジェクトは C# 式を使用します。

    - Visual Studio 2010 で作成され、Visual Basic 式が使用されている C# ワークフロー プロジェクトは、C# 式を使用する C# ワークフロー プロジェクトと互換性があります。

- バージョン管理機能の強化

    - 永続化されたワークフロー インスタンスとワークフロー定義間のマッピングを提供する新しい <xref:System.Activities.WorkflowIdentity> クラス。

    - <xref:System.ServiceModel.Activities.WorkflowServiceHost> を含む同じホスト内の複数のワークフローのバージョンの並列実行。

    - 動的更新プログラムで、永続化されたワークフロー インスタンスの定義を変更する機能。

- 既存のサービス コントラクトに合わせて自動的にアクティビティを生成するサポートが提供されるコントラクト優先のワークフロー サービス開発。

 詳細については、「[.NET 4.5 での Windows Workflow Foundation の新機能](http://go.microsoft.com/fwlink/?LinkId=228176)」を参照してください。

<a name="tailored"></a> 
### [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)]
 [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] のアプリは、特定のフォーム ファクターに合わせて設計されており、Windows オペレーティング システムの機能を利用します。 C# または Visual Basic を使用して Windows 用の [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] アプリをビルドするために、[!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] または 4.5.1 のサブセットを使用できます。 このサブセットは [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)] と呼ばれ、Windows デベロッパー センターの[概要](http://go.microsoft.com/fwlink/?LinkId=228491)のページで説明されています。

<a name="portable"></a> 
### <a name="portable-class-libraries"></a>ポータブル クラス ライブラリ
 [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)] (および以降のバージョン) のポータブル クラス ライブラリ プロジェクトを使用すると、複数の .NET Framework プラットフォームで動作するマネージ アセンブリを作成してビルドできます。 ポータブル クラス ライブラリ プロジェクトを使用して、対象とするプラットフォーム (Windows Phone や [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)]など) を選択します。 プロジェクトで使用できる型およびメンバーは、自動的にこれらのプラットフォーム間で共通の型とメンバーに制限されます。 詳細については、[ポータブル クラス ライブラリ](../../../docs/standard/cross-platform/cross-platform-development-with-the-portable-class-library.md)に関するページを参照してください。

## <a name="see-also"></a>参照
 [.NET Framework および OOB リリース](../../../docs/framework/get-started/the-net-framework-and-out-of-band-releases.md)   
 [.NET Framework のアクセシビリティの新機能](whats-new-in-accessibility.md)   
 [Visual Studio 2017 の新機能 ](/visualstudio/ide/whats-new-in-visual-studio)   
 [ASP.NET](/aspnet)   
 [Visual C++ の新機能](/cpp/what-s-new-for-visual-cpp-in-visual-studio) 
