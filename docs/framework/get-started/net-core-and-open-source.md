---
title: ".NET Core とオープン ソース"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e6bd4655-ce37-4003-8462-468a6fe2c40f
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: cc41a51a9c85b84f2f5365eb1650ebec37888652
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="net-core-and-open-source"></a>.NET Core とオープン ソース
このトピックでは、.NET Core の概要のほか、詳細情報の入手方法を説明します。 .NET Core に関するトピックの完全な一覧については、[「.NET Core のガイド」](../../core/index.md) を参照してください。
  
<a name="BKMK_WhatisNETCore"></a>   
## <a name="what-is-net-core"></a>.NET Core とは何ですか?  
 .NET Core は、モジュール形式のクロスプラットフォームかつオープン ソースを実装した汎用の .NET Standard です。 .NET Framework と同じ API の多くが含まれるほか (ただし、.NET Core の方が数が少ない)、ランタイム、フレームワーク、コンパイラ、およびさまざまなオペレーティング システムやチップ ターゲットをサポートするツールのコンポーネントが含まれます。 .NET Core の実装は、主に ASP.NET Core のワークロードによるものですが、新しい実装の必要性とユーザーの要望にも後押しされました。 この実装は、デバイス、クラウド、および埋め込み/IoT のシナリオで使用できます。  
  
 .NET Core を使用する場合、[.NET Core のホームページ](https://www.microsoft.com/net/core)を参照してください。  
  
 .NET Core の主な特徴を次に示します。  
  
-   **クロス プラットフォーム:** .NET Core には、ターゲットとするプラットフォームに関係なく、必要とするアプリケーション機能を実装したり、そのコードを再使用したりするための主な機能が備わっています。 現在、Windows、Linux と macOS の 3 つの主要オペレーティング システム (OS) をサポートしています。 サポートされている複数の OS で、修正せずに動作するアプリやライブラリを作成することができます。 サポートされるオペレーティング システムの一覧については、[「.NET Core Roadmap」](https://github.com/dotnet/core/blob/master/roadmap.md) (.NET Core ロードマップ) を参照してください。
  
-   **オープン ソース:** .NET Core は [.NET Foundation ](http://www.dotnetfoundation.org/)が管理している多くのプロジェクトの 1 つで、[GitHub](https://github.com/) で入手することができます。  .NET Core をオープン ソース プロジェクトとして使用すると、開発プロセスの透明性が高まるほか、コミュニティが活発化して交流が促進されます。  
  
-   **柔軟な展開:** アプリを展開する主な方法には、フレームワークに依存する展開と自己完結型の展開の 2 つがあります。 フレームワークに依存して展開する場合、アプリとサード パーティの依存関係のみがインストールされ、アプリを使用できるようにするには、.NET Core のシステム全体のバージョンが必要です。  自己完結型で展開する場合、アプリの作成に使用される .NET Core バージョンが、アプリやサード パーティの依存関係と共に展開され、他のバージョンと並行して実行することができます。    詳しくは、「[.NET Core アプリケーション展開](../../core/deploying/index.md)」をご覧ください。

-   **モジュール形式:** .NET Core は、小規模のアセンブリ パッケージで NuGet を介してリリースされるためモジュール形式となっています。 .NET Core はコア機能のほとんどが含まれる 1 つの大きなアセンブリではなく、中心的な機能が含まれる比較的小さなパッケージとして提供されています。 これによって開発モデルがよりアジャイル化されるため、必要な NuGet パッケージだけが含まれるようにアプリを最適化することができます。 小さいアプリ領域の利点には、セキュリティの強化、サービスの削減、パフォーマンスの向上、従量課金モデルによるコスト削減などがあります。  
  
## <a name="the-net-core-platform"></a>.NET Core プラットフォーム  
 .NET Core プラットフォームは複数コンポーネントで構成され、マネージ コンパイラ、ランタイム、基本クラス ライブラリ、および ASP.NET Core などの多数のアプリケーション モデルが含まれます。 さまざまなコンポーネントの詳細や、実際の操作については、以下の [GitHub](https://github.com/) リポジトリを参照してください。  
  
-   [.NET Core](https://github.com/dotnet/core)  
  
-   [CoreFX - .NET Core foundational libraries (CoreFX - .NET Core の基本的なライブラリ)](https://github.com/dotnet/corefx)  
  
-   [CoreCLR - .NET Core runtime (CoreCLR - .NET Core ランタイム)](https://github.com/dotnet/coreclr)  
  
-   [CLI - .NET Core command-line tools (CLI - .NET Core のコマンドライン ツール)](https://github.com/dotnet/cli)  
  
-   [Roslyn - .NET Compiler Platform (.NET コンパイラ プラットフォーム)](https://github.com/dotnet/roslyn)  
  
-   [ASP.NET Core](https://github.com/aspnet/home)  
  
## <a name="see-also"></a>参照  
 [.NET Core のホーム ページ](https://www.microsoft.com/net/core)  
 [.NET Core のガイド](../../core/index.md)  
 [ASP.NET Core ドキュメント](/aspnet/core/)
