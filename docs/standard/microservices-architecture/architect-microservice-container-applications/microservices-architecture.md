---
title: "マイクロサービス アーキテクチャ"
description: "コンテナー化された .NET アプリケーションの .NET マイクロサービス アーキテクチャ | マイクロサービス アーキテクチャ"
keywords: "Docker, マイクロサービス, ASP.NET, コンテナー"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 453f8a22157eee9601f2586d49d872d90634bb61
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/23/2017
---
# <a name="microservices-architecture"></a>マイクロサービス アーキテクチャ

名前が示すように、マイクロサービス アーキテクチャは、一連の小さなサービスとしてサーバー アプリケーションを構築するアプローチです。 各サービスは独自のプロセスで実行され、HTTP/HTTPS、WebSockets、[AMQP](https://en.wikipedia.org/wiki/Advanced_Message_Queuing_Protocol) などのプロトコルを使用して他のプロセスと通信します。 各マイクロサービスは、特定のコンテキスト境界内で特定のエンドツーエンドのドメインまたはビジネス機能を実装します。個々のマイクロサービスを自律的に開発し、独立して展開可能にする必要があります。 最後に、さまざまなデータ ストレージ テクノロジ (SQL、NoSQL) とさまざまなプログラミング言語に基づいて、各マイクロサービスは関連するドメイン データ モデルとドメイン ロジック (主権と分散データ管理) を所有する必要があります。

マイクロサービスはどのくらいのサイズにすべきでしょうか。 マイクロサービスを開発する場合、サイズは重要なポイントではありません。 その代わり、弱く結合されたサービスを作成して、サービスごとに開発、展開、およびスケールの自律性を持たせることが重要です。 当然ながら、マイクロサービスを特定して設計する場合は、他のマイクロサービスとの直接の依存関係が多くなりすぎない限り、できるだけマイクロサービスを小さくするようにします。 マイクロサービスのサイズよりも重要な点は、必要な内部の凝集度と、他のサービスからの独立性です。

マイクロサービス アーキテクチャを選ぶ理由は何でしょうか。 短く説明すると、長期的な機敏性を実現するためです。 マイクロサービスを使用すると、個々が細かい自律的なライフサイクルを持つ、多数の独立して展開可能なサービスに基づいてアプリケーションを作成できるので、複雑で大規模で高度にスケーラブルなシステムの保守性を向上することができます。

また、個別にスケールアウトできることもマイクロサービスのメリットです。 1 つのモノリシックなアプリケーションを 1 ユニットとしてスケールアウトするのではなく、特定のマイクロサービスをスケールアウトできます。 その結果、需要に応えるために多くの処理能力やネットワーク帯域幅を必要とする機能領域だけをスケールアウトでき、スケールアウトする必要のない機能領域までスケールアウトすることはありません。 つまり、必要なハードウェア数が少ないため、コストを削減できます。

![](./media/image6.png)

**図 4-6** モノリシック展開とマイクロサービス アプローチ

図 4-6 に示すように、マイクロサービス アプローチを使用すると、複雑で大規模でスケーラブルなアプリケーションの特定の小さな領域を変更できるため、各マイクロサービスの柔軟な変更と迅速な繰り返しが可能になります。

細かいマイクロサービスベースのアプリケーションを設計することで、継続的な統合と継続的な配信方法を実現できます。 また、短期間でアプリケーションに新しい関数を配信できるようになります。 細かいアプリケーションの構成にすることで、マイクロサービスを単独で実行してテストし、マイクロサービス間の明確なコントラクトを維持しながら自律的に進化させることもできます。 インターフェイスまたはコントラクトを変更しない限り、任意のマイクロサービスの内部実装を変更することや、他のマイクロサービスを中断することなく新機能を追加することができます。

マイクロサービスベースのシステムを含む実稼働環境への移行を成功させるには、次の点が重要です。

-   サービスとインフラストラクチャの監視と正常性検査。

-   サービス (つまり、クラウドとオーケストレーター) のスケーラブルなインフラストラクチャ。

-   複数レベルのセキュリティ設計と実装: 認証、承認、シークレット管理、セキュリティで保護された通信など。

-   高速なアプリケーション配信。通常は、チームによって異なるマイクロサービスに集中します。

-   DevOps および CI/CD のプラクティスとインフラストラクチャ。

このガイドでは最初の 3 つのみを扱い、紹介しています。 アプリケーションのライフサイクルに関連する残り 2 つの点については、「[Containerized Docker Application Lifecycle with Microsoft Platform and Tools](https://aka.ms/dockerlifecycleebook)」(Microsoft プラットフォームとツールを使用してコンテナー化された Docker アプリケーションのライフサイクル) の電子書籍を参照してください。

## <a name="additional-resources"></a>その他の技術情報

-   **Mark Russinovich。マイクロサービス: クラウド原動力にするアプリケーション革命**
    [*https://azure.microsoft.com/blog/microservices-an-application-revolution-powered-by-the-cloud/*](https://azure.microsoft.com/blog/microservices-an-application-revolution-powered-by-the-cloud/)

-   **Martin Fowler。マイクロサービス**
    [*http://www.martinfowler.com/articles/microservices.html*](http://www.martinfowler.com/articles/microservices.html)

-   **Martin Fowler。マイクロサービスの前提条件**
    [*http://martinfowler.com/bliki/MicroservicePrerequisites.html*](http://martinfowler.com/bliki/MicroservicePrerequisites.html)

-   **Jimmy Nilsson。チャンク クラウド コンピューティング**
    [*https://www.infoq.com/articles/CCC-Jimmy-Nilsson*](https://www.infoq.com/articles/CCC-Jimmy-Nilsson)

-   **Cesar de la Torre。Microsoft のプラットフォームとツールを使用したコンテナー化された Docker アプリケーションのライフサイクル** (ダウンロード可能な電子ブック) [*https://aka.ms/dockerlifecycleebook*](https://aka.ms/dockerlifecycleebook)




>[!div class="step-by-step"]
[Previous] (service-oriented-architecture.md) [Next] (data-sovereignty-per-microservice.md)
