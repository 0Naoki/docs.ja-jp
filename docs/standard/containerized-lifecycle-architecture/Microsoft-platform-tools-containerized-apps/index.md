---
title: コンテナー化アプリ用の Microsoft プラットフォームとツールの概要
description: Microsoft プラットフォームとツールでコンテナー化された Docker アプリケーションのライフサイクル
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/21/2017
ms.openlocfilehash: fe65e9036c1e0bdf2afe05426c01e75d48f93439
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2018
ms.locfileid: "53152340"
---
# <a name="introduction-to-the-microsoft-platform-andtools-for-containerized-apps"></a>Microsoft プラットフォームとコンテナー化アプリ用ツールの概要


図 3-1 は、複数のチーム (アプリの開発、DevOps インフラストラクチャ プロセス、および IT 管理および運用) によって提供される作業の種類で分類された Docker アプリのライフ サイクルの主要な柱を示しています。 通常、企業では、それぞれの領域を代表する "ペルソナ" のプロファイルは異なります。 そのため、スキルも異なります。

![](./media/image1.png)

図 3-1:Microsoft プラットフォームとツールでコンテナー化された Docker アプリケーションのライフ サイクルの主要な柱

コンテナー化された Docker ライフ サイクル ワークフローは、"既定の製品選択" を基にして最初に規範を作成し、開発者がより簡単に早く作業を開始できるようにすることができますが、基本的に内部にオープンなフレームワークが存在する必要があるので、各組織または企業からの異なるコンテキストに合わせて調整できる柔軟なワークフロー機能です。 ワークフロー インフラストラクチャ (コンポーネントと製品) は、各企業が将来使用する環境をカバーできるだけの十分な柔軟性が必要であり、開発製品や DevOps 製品を他と交換することさえ可能になっている必要があります。 この柔軟性とオープンさ、プラットフォームとインフラストラクチャの広い選択肢は、以下の章で説明するように、コンテナー化された Docker アプリケーションで Microsoft がまさに優先していることです。

表 3-1 は、コンテナー化された Docker アプリケーション用 Microsoft DevOps の目的が、オープンな DevOps ワークフローを提供し、各フェーズ (Microsoft またはサード パーティ) で使用する製品を選択できるようにすることであり、同時に、既に接続された "既定の製品" を提供する簡素化されたワークフローを提供することを示しています。これにより、Docker アプリ用のエンタープライズレベルの DevOps の使用をすばやく開始することができます。

表 3-1:任意のテクノロジに DevOps ワークフローを開く

| ホスト | マイクロソフト テクノロジ | サード パーティ — Azure 接続可能 |
| ---------------------------| ----------------------------------------------------| --------------------------------------------------------------------------------|
| Docker アプリのプラットフォーム   | • Microsoft Visual Studio および Visual Studio Code<br /> • .NET<br /> • Microsoft Azure Container Service<br /> • Azure Service Fabric<br /> • Azure Container Registry<br /> | • 任意のコード エディター (Sublime など)<br /> • 任意の言語 (Node.js、Java、Go など)<br /> • 任意のオーケストレーターとスケジューラ<br /> • 任意の Docker レジストリ<br /> |
| Docker アプリ用の DevOps     | • Azure DevOps サービス<br /> • Microsoft Team Foundation Server<br /> • Azure Container Service<br /> • Azure Service Fabric<br /> | • GitHub、Git、Subversion など<br /> • Jenkins、Chef、Puppet、Velocity、CircleCI、TravisCI など<br /> • On-premises Docker Datacenter、Docker Swarm、Mesos DC/OS、Kubernetes など<br /> |
| 管理と監視  | • Operations Management Suite<br /> • Applications Insights<br /> | • Marathon、Chronos など<br />

Microsoft プラットフォームとコンテナー化された Docker アプリ用ツールは表 3-1 に示すように、定義されている次のコンポーネントから成ります。

-   **Docker アプリ開発用プラットフォーム** サービス、または "アプリ" を構成するサービスのコレクションの開発。 開発プラットフォームは、コードを共有コード リポジトリにプッシュする前に開発者が実行する必要があるすべての作業を提供します。 コンテナーとして展開されている開発サービスは、Docker を使用しない同じアプリまたはサービスの開発とよく似ています。 優先する言語 (.NET、Node.js、Go など) と好みのエディターまたは Visual Studio または Visual Studio Code などの IDE を使用する続行するとします。 ただし、展開先として Docker を考慮するのではなく、Docker 環境でサービスを開発します。 コンテナーでローカルでコードを構築、実行、テスト、およびデバッグ、開発時に配置先の環境を提供します。 ローカルで配置先の環境を提供することで、Docker コンテナーは、DevOps のライフ サイクルを改善するために大きく役立ちます。 Visual Studio および Visual Studio Code には、開発プロセス内で Docker コンテナーを統合するための拡張機能があります。

-   **Docker アプリ用の DevOps** Docker アプリケーションを作成する開発者は、Azure DevOps サービスまたは Jenkins のようなその他のサード パーティ製品を使用できます、包括的なビルドをアプリケーション ライフ サイクル管理 (ALM) を自動化します。

コンテナーに重点を置いた Azure DevOps サービスを使用する開発者を作成できます (Azure DevOps サービス-Git、GitHub、リモート Git リポジトリ、または Subversion) 任意の場所から継続的インテグレーション (CI) 制御、高速で反復的なプロセスでソース コードをカバーする DevOps、内部単体テストでは、コンテナー/サービスの統合テスト、継続的デリバリー (CD)、およびリリース管理 (RM) の間。 開発者は、開発からステージング環境と実稼働環境の Azure コンテナー サービスへの Docker アプリケーションのリリースを自動化することもできます。
 
-   IT 実稼働の管理と監視

**管理** IT 部門は、いくつかの方法で実稼働アプリケーションとサービスを管理できます。

-   **Azure ポータル** オープン ソース オーケストレーターを使用している場合、Azure Container Service (ACS) と、Docker Datacenter や Mesosphere Marathon などのクラスター管理ツールが、Docker の環境の設定と管理に役立ちます。 Azure Service Fabric を使用している場合、Service Fabric Explorer ツールを利用すると、クラスターを視覚化して構成できます。

-   **Docker ツール** 使い慣れたツールを使用して、コンテナー アプリケーションを管理することができます。 コンテナーのワークロードをクラウドに移動するために、既存の Docker 管理方法を変更する必要はありません。 既に精通している任意のアプリケーション管理ツールを使用し、選択したオーケストレーター用の標準 API エンドポイント経由で接続します。 Docker Datacenter や CLI Docker ツールなどの他のサードパーティ製ツールを使用して、Docker アプリケーションを管理することもできます。

-   **オープン ソース ツール** ACS はオーケストレーション エンジンのための標準的な API エンドポイントを公開するため、最も一般的なツールは ACS と互換性があり、ほとんどの場合は既定で使用できます。これには、ビジュアライザー、監視ツール、コマンドライン ツールが含まれ、将来的に利用可能になるツールも含まれます。

**監視**実稼働環境の実行中に、次を使用してあらゆる側面を監視することができます。

-   **Operations Management Suite (OMS)** "OMS コンテナー ソリューション" は、コンテナーおよびコンテナー ホストの場所、どのコンテナーが実行中または失敗したか、および Docker デーモンとコンテナーのログに関する情報を表示することによって、Docker ホストとコンテナーを管理および監視することができます。 また、CPU、メモリ、ネットワーク、コンテナーとホストのストレージなどのパフォーマンス メトリックを表示し、トラブルシューティングやノイズの多い近隣のコンテナーの検出に役立てることもできます。

-   **Application Insights**サービスに SDK をセットアップするだけで、実稼働環境の Docker アプリケーションを監視し、アプリケーションから製品利用統計情報データを取得することができます。

このように、Microsoft は、エンド ツー エンドのコンテナー化 Docker アプリケーションのライフ サイクルの完全な基盤を提供します。 この*製品とテクノロジの集まりを使用すると、必要に応じて既存のツールやプロセスと統合することができます*。 広範囲なアプローチの柔軟性、および機能の綿密さによる強みにより、Microsoft は、コンテナー化 Docker アプリケーション開発において強力な位置を築いています。

>[!div class="step-by-step"]
>[前へ](../Docker-application-lifecycle/containers-foundation-for-devops-collaboration.md)
>[次へ](../design-develop-containerized-apps/index.md)