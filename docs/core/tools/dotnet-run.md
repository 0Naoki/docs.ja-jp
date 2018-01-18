---
title: "dotnet run コマンド - .NET Core CLI"
description: "dotnet run コマンドは、ソース コードからアプリケーションを実行する便利なオプションを提供します。"
author: mairaw
ms.author: mairaw
ms.date: 09/24/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.workload: dotnetcore
ms.openlocfilehash: 1f5a3927859f89bef6c50d3d31b73de43cd1cd31
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/23/2017
---
# <a name="dotnet-run"></a>dotnet run

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>name

`dotnet run` -- 明示的なコンパイルや起動コマンドなしで、ソース コードを実行します。

## <a name="synopsis"></a>構文

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

```
dotnet run [-c|--configuration] [-f|--framework] [--force] [--launch-profile] [--no-build] [--no-dependencies] [--no-launch-profile] [--no-restore] [-p|--project] [--runtime] [[--] [application arguments]]
dotnet run [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

```
dotnet run [-c|--configuration] [-f|--framework] [-p|--project] [[--] [application arguments]]
dotnet run [-h|--help]
```

---

## <a name="description"></a>説明

`dotnet run` コマンドは、1 つのコマンドを使用して、ソース コードからアプリケーションを実行する便利なオプションを提供します。 コマンド ラインからの短期間の反復開発に便利です。 このコマンドは [`dotnet build`](dotnet-build.md) コマンドに依存し、コードをビルドします。 そのため、プロジェクトを最初に復元する必要があるなど、ビルドに要件があれば、それが `dotnet run` にも適用されます。 

出力ファイルは既定の場所である `bin/<configuration>/<target>` に書き込まれます。 たとえば、`netcoreapp1.0` というアプリケーションがあり、`dotnet run` を実行する場合、`bin/Debug/netcoreapp1.0` に出力されます。 必要に応じて、ファイルは上書きされます。 一時ファイルは `obj` ディレクトリに置かれます。 

フレームワークを複数指定するプロジェクトの場合、`-f|--framework <FRAMEWORK>` オプションを使用してフレームワークを指定しない限り、`dotnet run` を実行するとエラーが発生します。

`dotnet run` コマンドは、ビルド済みのアセンブリではなく、プロジェクトのコンテキストで使用されます。 代わりにフレームワークに依存するアプリケーション DLL の実行を試みる場合は、コマンドなしで [dotnet](dotnet.md) を実行する必要があります。 たとえば、`myapp.dll` を実行する場合は、次のコードを使用します。

```
dotnet myapp.dll
```

`dotnet` ドライバーの詳細については、「[.NET Core Command Line Tools (CLI)](index.md)」 (.NET Core コマンド ライン ツール (CLI)) を参照してください。

アプリケーションを実行するために、`dotnet run` コマンドは、NuGet キャッシュから共有ランタイムの外にあるアプリケーションの依存関係を解決します。 このコマンドではキャッシュされた依存関係を使用するため、`dotnet run` を使用してアプリケーションを実稼働環境で実行することは推奨されません。 代わりに、[`dotnet publish`](dotnet-publish.md) コマンドを使用して[展開を作成](../deploying/index.md)し、発行された出力を展開します。

## <a name="options"></a>オプション

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

`--`

実行中のアプリケーションの引数と `dotnet run` の引数を区切ります。 この後の引数はすべて実行中のアプリケーションに渡されます。

`-c|--configuration {Debug|Release}`

ビルド構成を定義します。 既定値は `Debug` です。

`-f|--framework <FRAMEWORK>`

指定された[フレームワーク](../../standard/frameworks.md)を使用してアプリをビルドし、実行します。 フレームワークはプロジェクト ファイルに指定する必要があります。

`--force`

最後の復元が成功した場合でも、すべての依存関係が強制的に解決されます。 これは、*project.assets.json* を削除する処理に相当します。

`-h|--help`

コマンドの短いヘルプを印刷します。

`--launch-profile <NAME>`

アプリケーションを起動する場合に使用する起動プロファイル (存在する場合) の名前です。 起動プロファイルは *launchSettings.json* ファイル内に定義されており、通常は、`Development`、`Staging`、および `Production` と呼ばれています。 詳細については、[「Working with multiple environments」](/aspnet/core/fundamentals/environments) (複数の環境での使用) をご覧ください。

`--no-build`

実行前にプロジェクトをビルドしません。

`--no-dependencies`

プロジェクト間 (P2P) 参照を含むプロジェクトを復元する場合は、参照ではなく、ルート プロジェクトを復元します。

`--no-launch-profile`

アプリケーションを構成するための *launchSettings.json* の使用を試みません。

`--no-restore`

コマンドを実行するときに、暗黙的な復元を実行しません。

`-p|--project <PATH>`

実行するプロジェクト ファイルのパスを指定します (フォルダー名または完全なパス)。 指定しない場合は、既定で現在のディレクトリに設定されます。

`--runtime <RUNTIME_IDENTIFIER>`

パッケージを復元するターゲット ランタイムを指定します。 ランタイム ID (RID) の一覧については、[RID カタログ](../rid-catalog.md)に関するページをご覧ください。

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

`--`

実行中のアプリケーションの引数と `dotnet run` の引数を区切ります。 この後の引数はすべて実行中のアプリケーションに渡されます。

`-c|--configuration {Debug|Release}`

ビルド構成を定義します。 既定値は `Debug` です。

`-f|--framework <FRAMEWORK>`

指定された[フレームワーク](../../standard/frameworks.md)を使用してアプリをビルドし、実行します。 フレームワークはプロジェクト ファイルに指定する必要があります。

`-h|--help`

コマンドの短いヘルプを印刷します。

`-p|--project <PATH/PROJECT.csproj>`

プロジェクト ファイルのパスと名前を指定します  (注を参照)。指定しない場合は、既定で現在のディレクトリに設定されます。

> [!NOTE]
> `-p|--project` オプションでプロジェクト ファイルのパスと名前を使用します。 CLI の回帰により、.NET Core 1.x SDK でフォルダー パスを指定できなくなります。 この問題の詳細については、[「dotnet run -p, can not start a project (dotnet/cli #5992)」](https://github.com/dotnet/cli/issues/5992) (dotnet run -p でプロジェクトを開始できない (dotnet/cli #5992)) を参照してください。

---

## <a name="examples"></a>使用例

現在のディレクトリのプロジェクトを実行します。

`dotnet run`

指定されたプロジェクトを実行します。

`dotnet run --project /projects/proj1/proj1.csproj`

現在のディレクトリのプロジェクトを実行します (この例では、`--` 引数が使用されているため、`--help` 引数がアプリケーションに渡されます)。

`dotnet run --configuration Release -- --help`
