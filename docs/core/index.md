---
title: .NET Core のガイド
description: .NET Core は、Windows、Linux、および Mac アプリを作成するためのモジュール型の高性能な .NET 実装です。 ここでは、.NET Core の概要について説明します。
author: richlander
ms.date: 09/23/2019
ms.custom: updateeachrelease
ms.openlocfilehash: 95f18ca09852ce139a4b99ed7aef4802d4883e13
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2019
ms.locfileid: "71216221"
---
# <a name="net-core-guide"></a>.NET Core のガイド

[.NET Core](about.md) は、Microsoft および .NET コミュニティによって [GitHub](https://github.com/dotnet/core) 上で管理されている、[オープンソース](https://github.com/dotnet/coreclr/blob/master/LICENSE.TXT)の汎用的な開発プラットフォームです。 クロスプラットフォーム (Windows、macOS、Linux をサポート) であり、デバイス、クラウド、および IoT アプリケーションを構築するために使用できます。

特徴、サポートされる言語とフレームワーク、キー API など、.NET Core について詳しくは、「[.NET Core について](about.md)」 をご覧ください。

「[.NET Core チュートリアル](tutorials/index.md)」では、単純な .NET Core アプリケーションを作成する方法を学習できます。 最初のアプリを、ほんの数分で起動および実行できます。 ブラウザーで .NET Core を使用してみる場合は、[C# における数値](../csharp/tutorials/intro-to-csharp/numbers-in-csharp.yml)に関するオンライン チュートリアルをご覧ください。

## <a name="download-net-core"></a>.NET Core のダウンロード

[.NET Core SDK](https://www.microsoft.com/net/download) をダウンロードして、お使いの Windows、macOS、または Linux コンピューター上で .NET Core をお試しください。 また、Docker コンテナーを使用する場合は、[.NET Core の Docker Hub](https://hub.docker.com/_/microsoft-dotnet-core/) にアクセスしてください。

別の .NET Core バージョンを探している場合も、すべての .NET Core バージョンを [.NET Core のダウンロード](https://dotnet.microsoft.com/download/dotnet-core)で入手できます。

## <a name="net-core-30"></a>.NET Core 3.0

最新バージョンは .NET Core 3.0 です。 新機能として、Windows Presentation Foundation (WPF) および Windows フォームを使った Windows デスクトップのサポートや、Blazor を使ったフル スタック C# Web 開発、SignalR および Azure SignalR Service の新しい機能強化、C# 8 での新しい C# 言語機能などがあります。 .NET Core 3.0 の新機能の完全な一覧については、「[.NET Core 3.0 の新機能](./whats-new/dotnet-core-3-0.md)」をご覧ください。

## <a name="create-your-first-application"></a>最初のアプリケーションの作成

.NET Core SDK をインストールしたらコマンド プロンプトを開きます。 次の `dotnet` コマンドを入力し、C# アプリケーションを作成して実行します。

```dotnetcli
dotnet new console
dotnet run
```

次の出力が表示されます。

```output
Hello World!
```

## <a name="support"></a>サポート

.NET Core は、[Microsoft によって](https://dotnet.microsoft.com/platform/support/policy)、Windows、macOS、Linux 上でサポートされています。 年に数回、通常は毎月、セキュリティと品質向上のために更新されます。

.NET Core のバイナリ形式の配布は、Azure 内のマイクロソフトが管理するサーバーで構築されてテストされ、他のすべてのマイクロソフト製品と同様にサポートされます。

Red Hat Enterprise Linux (RHEL) では [.NET Core は Red Hat によってサポート](http://redhatloves.net/)されます。 Red Hat がソースから .NET Core をビルドして、[Red Hat ソフトウェア コレクション](https://developers.redhat.com/products/softwarecollections/overview/)で使用できるようにします。 Red Hat とマイクロソフトが共同して、.NET Core が RHEL 上で適切に動作するようにします。
