---
title: "マイクロサービス API とコントラクトの作成、進化、バージョン管理"
description: ".NET マイクロサービス: コンテナー化された .NET アプリケーションのアーキテクチャ | マイクロサービス API とコントラクトの作成、進化、バージョン管理"
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
ms.openlocfilehash: 3aaa7eaa8bc535874369cf08414f2211cae1bed9
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/23/2017
---
# <a name="creating-evolving-and-versioning-microservice-apis-and-contracts"></a>マイクロサービス API とコントラクトの作成、進化、バージョン管理

マイクロサービス API は、サービスとそのクライアント間のコントラクトです。 API コントラクトに違反していない場合に限り、マイクロサービスを単独で進化させることができます。そのため、コントラクトは非常に重要です。 コントラクトを変更すると、クライアント アプリケーションや API ゲートウェイに影響します。

API 定義の性質は、使用しているプロトコルによって異なります。 たとえば、メッセージング ([AMQP](https://www.amqp.org/) など) を使用している場合、API は複数の種類のメッセージで構成されます。 HTTP サービスと RESTful サービスを使用している場合、API は、URL と、要求と応答の JSON 形式で構成されます。

ただし、たとえ最初のコントラクトについて熟慮した場合でも、サービスの API は時間の経過と共に変更する必要があります。 そのような状況になった場合、特に複数のクライアント アプリケーションによって使用されるパブリック API である場合は、通常、すべてのクライアントを強制的に新しい API コントラクトにアップグレードすることはできません。 通常、サービス コントラクトの古いバージョンと新しいバージョンの両方が同時に実行されるように、新しいバージョンのサービスを段階的に展開する必要があります。 そのため、サービスのバージョン管理戦略を用意することが重要です。

API の変更が少ない場合 (たとえば、API に属性やパラメーターを追加する場合など)、古い API を使用するクライアントが新しいバージョンのサービスに切り替えても、使用できるようにします。 必須の不足している属性がある場合は既定値を指定することができます。また、クライアントは追加された応答属性があっても無視できる可能性があります。

ただし、サービスの API に重大な互換性のない変更を加える必要が生じることがあります。 クライアント アプリケーションまたはサービスに対して、すぐに新しいバージョンにアップグレードすることを強制できないので、ある程度の期間、以前のバージョンの API をサポートする必要があります。 REST などの HTTP ベースのメカニズムを使用している場合は、API バージョン番号を URL または HTTP ヘッダーに埋め込む方法があります。 次に、同じサービス インスタンス内で両方のバージョンのサービスを同時に実装するか、それぞれに 1 つのバージョンの API を処理する異なるインスタンスを展開するかを判断します。 このようなときにお勧めのアプローチは、異なる実装バージョンを独立したハンドラーに分離する [Mediator パターン](https://en.wikipedia.org/wiki/Mediator_pattern) (たとえば、[MediatR ライブラリ](https://github.com/jbogard/MediatR)など) です。

最後に、REST アーキテクチャを使用している場合、[Hypermedia](https://www.infoq.com/articles/mark-baker-hypermedia) はサービスのバージョン管理と API を進化させるために最適なソリューションです。

## <a name="additional-resources"></a>その他の技術情報

-   **Scott Hanselman。ASP.NET Core RESTful Web API バージョン管理で簡単に**
    <http://www.hanselman.com/blog/ASPNETCoreRESTfulWebAPIVersioningMadeEasy.aspx>

-   **RESTful Web API のバージョン管理**
    [*https://docs.microsoft.com/azure/architecture/best-practices/api-design#versioning-a-restful-web-api*](https://docs.microsoft.com/azure/architecture/best-practices/api-design#versioning-a-restful-web-api)

-   **Roy Fielding。バージョン管理、ハイパーメディア、REST**
    <https://www.infoq.com/articles/roy-fielding-on-versioning>


>[!div class="step-by-step"]
[前へ] (asynchronous-message-based-communication.md) [次へ] (microservices-addressability-service-registry.md)
