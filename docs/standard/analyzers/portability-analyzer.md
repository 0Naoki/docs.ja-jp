---
title: .NET Portability Analyzer - .NET
description: .NET Portability Analyzer ツールを使って、さまざまな .NET の実装 (.NET Core、.NET Standard、UWP、Xamarin など) の間でのコードの移植性を評価する方法について説明します。
author: blackdwarf
ms.author: mairaw
ms.date: 07/26/2017
ms.technology: dotnet-standard
ms.assetid: 0375250f-5704-4993-a6d5-e21c499cea1e
ms.openlocfilehash: 515dd7a393d87811377aa5d9fb02de35943b6966
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/02/2018
ms.locfileid: "43415689"
---
# <a name="the-net-portability-analyzer"></a>.NET Portability Analyzer

ライブラリをマルチプラットフォーム対応にしたい場合や、 アプリケーションで他の .NET の実装とプロファイル (.NET Core、.NET Standard、UWP、Xamarin for iOS/Android/Mac など) との互換性を確保するのに必要な作業量を知りたい場合は、 [.NET Portability Analyzer](https://marketplace.visualstudio.com/items?itemName=ConnieYau.NETPortabilityAnalyzer) が役立ちます。このツールを使用すると、アセンブリを分析して、プログラムが .NET 実装全体でどの程度柔軟な構造になっているかについて詳細なレポートを生成することができます。 Portability Analyzer は、Visual Studio 拡張機能のコンソール アプリとして提供されます。

## <a name="new-targets"></a>新しいターゲット

* [.NET Core](../../core/index.md): モジュール型の設計で、side-by-side を採用しており、クロスプラットフォームのシナリオを対象としています。 side-by-side 機能により、他のアプリに影響を与えることなく新しい .NET Core バージョンを導入することができます。
* [ASP.NET Core](/aspnet/core): .NET Core 上に構築された最新の Web フレームワークであり、開発者に .NET Core と同じメリットを提供します。
* [ユニバーサル Windows プラットフォーム](https://blogs.msdn.microsoft.com/dotnet/2014/04/24/net-native-performance): .NET Native の静的コンパイルを使用することで、x64 および ARM マシンで動作する Windows ストア アプリのパフォーマンスが向上します。 
* .NET Core + プラットフォーム拡張機能: .NET Core API と、WCF、ASP.NET Core、FSharp、Azure などの .NET エコシステム内のその他の API が含まれます。
* .NET Standard + プラットフォーム拡張機能: .NET Standard API と、WCF、ASP.NET Core、FSharp、および Azure などの .NET エコシステム内のその他の API が含まれます。

## <a name="how-to-use-portability-analyzer"></a>Portability Analyzer の使用方法

.NET Portability Analyzer を使用するには、[Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=ConnieYau.NETPortabilityAnalyzer) から拡張機能をダウンロードし、インストールする必要があります。 これは、Visual Studio 2015 と Visual Studio 2017 で機能します。 **[分析]**、 > **[Portability Analyzer Settings (Portability Analyzer の設定)]** の順に選択して構成し、ターゲット プラットフォームを選択できます。

![Portability のスクリーンショット](./media/portability-analyzer/portability-screenshot.png)

プロジェクト全体を分析するには、**ソリューション エクスプローラー**でプロジェクトを右クリックし、**[Analyze Assembly Portability]** (アセンブリの移植性を分析) を選択します。 または、**[分析]** メニューで **[Analyze Assembly Portability]** (アセンブリの移植性を分析) を選択します。 そこから、プロジェクトの実行可能ファイルまたは DLL を選択します。

![移植性ソリューション エクスプローラー](./media/portability-analyzer/portability-solution-explorer.png)

分析を実行すると、.NET 移植性レポートが表示されます。 ターゲット プラットフォームでサポートされていない型のみが一覧に表示され、**[エラー一覧]** の **[メッセージ]** タブで、推奨事項を確認できます。 また、**[メッセージ]** タブから問題のある領域に直接移動することもできます。

![移植性レポート](./media/portability-analyzer/portability-report.png)

Visual Studio を使用しない場合は、 コマンド プロンプトから Portability Analyzer を使用することもできます。 [API Portability Analyzer](https://www.microsoft.com/download/details.aspx?id=42678) をダウンロードします。

*   現在のディレクトリを分析するには、次のコマンドを入力します。`\...\ApiPort.exe analyze -f .`
*   特定の .dll ファイルの一覧を分析するには、次のコマンドを入力します。`\...\ApiPort.exe analyze -f first.dll -f second.dll -f third.dll`

.NET 移植性レポートは、Excel ファイル (*.xlsx*) として現在のディレクトリに保存されます。 Excel のブックの **[詳細]** タブに詳細情報が記載されています。

.NET Portability Analyzer の詳細については、[GitHub ドキュメント](https://github.com/Microsoft/dotnet-apiport#documentation)にアクセスし、Channel 9 動画の「[A Brief Look at the .NET Portability Analyzer](https://channel9.msdn.com/Blogs/Seth-Juarez/A-Brief-Look-at-the-NET-Portability-Analyzer)」 (.NET Portability Analyzer の概要) をご覧ください。
