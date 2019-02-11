---
title: ASP.NET Core Web アプリ用の Azure ホスティングの推奨事項
description: ASP.NET Core および Azure での最新の Web アプリケーションの設計 | ASP.NET Web アプリ用の Azure ホスティングの推奨事項
author: ardalis
ms.author: wiwagn
ms.date: 01/30/2019
ms.openlocfilehash: cda4c002c73e2dd0db1b2d5d1fa8bc76903c5c62
ms.sourcegitcommit: 3500c4845f96a91a438a02ef2c6b4eef45a5e2af
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/07/2019
ms.locfileid: "55828385"
---
# <a name="azure-hosting-recommendations-for-aspnet-core-web-apps"></a>ASP.NET Core Web アプリ用の Azure ホスティングの推奨事項

> "基幹業務のリーダーはどこでも、IT 部門を通さずにクラウドからアプリケーションにアクセスし (別名 SaaS)、雑誌を購読するかのように料金を支払っています。 そして、サービスが不要になったら、無駄なくサブスクリプションを取り消すことができます。"  
> _\- Daryl Plummer、Gartner アナリスト_

Windows Azure なら、アプリケーションのニーズとアーキテクチャに応じたサポートが可能です。 ホスティングのニーズは多数のサービスで構成される高度なアプリケーションの静的な Web サイトと同じくらい簡単にできます。 ASP.NET Core のモノリシックな Web アプリケーションとサポートされるサービスには、推奨されるいくつかのよく知られている構成が含まれています。 この記事の推奨事項は、完全なアプリケーション、個別のプロセス、またはデータであっても、ホスティングされるリソースの種類に基づいてグループ化されています。

## <a name="web-applications"></a>Web アプリケーション

Web アプリケーションは次を使用してホスティングできます。

- App Service Web Apps

- コンテナー

- Azure Service Fabric

- 仮想マシン (VM)

このうち、ほとんどのシナリオでお勧めできる手法が App Service Web Apps です。 マイクロサービス アーキテクチャでは、コンテナー ベースの方法、または Service Fabric を検討してください。 アプリケーションを実行しているマシンをさらに制御する必要がある場合は、Azure Virtual Machines を検討してください。

### <a name="app-service-web-apps"></a>App Service Web Apps

App Service Web Apps は、Web アプリケーションのホスティングに最適化されたフル マネージド プラットフォームを提供します。 これは、サービスとしてのプラットフォーム (PaaS) 製品です。Azure がアプリの実行とスケーリングに必要なインフラストラクチャに対処するため、ビジネス ロジックに集中することができます。 App Service Web Apps の主な機能: 

- DevOps の最適化 (継続的インテグレーションと継続的配信、複数の環境、A/B テスト、スクリプトのサポート)

- グローバルなスケーリングと高可用性

- SaaS プラットフォームとオンプレミス データへの接続

- セキュリティとコンプライアンス

- Visual Studio の統合

Azure App Service は、ほとんどの Web アプリに最適な選択肢です。 デプロイと管理はプラットフォームに統合されており、サイトは高い負荷を処理できるように素早くスケーリングでき、組み込みの負荷分散とトラフィック マネージャーが高可用性を提供します。 オンライン移行ツールを使用して既存のサイトを簡単に Azure App Service に移動したり、Web アプリケーション ギャラリーからオープンソース アプリを使用したり、選択したフレームワークとツールを使用して新しいサイトを作成したりできます。 Web ジョブ機能により、バックグラウンド ジョブ処理を App Service Web アプリに簡単に追加できます。

### <a name="azure-kubernetes-service"></a>Azure Kubernetes Service

Azure Kubernetes Service (AKS) は、ホストされている Kubernetes 環境を管理するサービスで、コンテナー オーケストレーションの専門知識がなくても、コンテナー化したアプリケーションのデプロイと管理をすばやく簡単に行うことができます。 また、アプリケーションをオフラインにせずに、オンデマンドでリソースのプロビジョニング、アップグレード、スケーリングを実行できるため、継続的に行う操作と保守の負担も解消されます。

AKS では、Azure に対する責任の多くをオフロードすることによって、Kubernetes クラスターの管理における複雑な運用のオーバーヘッドを削減します。 ホストされている Kubernetes サービスとして、Azure では、正常性の監視や保守などの重要なタスクが処理されます。 また、マスターではなく、クラスター内のエージェント ノードのみの料金を支払います。 マネージド Kubernetes サービスとして、AKS では次が提供されます。

- 自動化された Kubernetes バージョンのアップグレードと修正。
- 簡単なクラスターのスケーリング。
- 自己復旧のホストされているコントロール プレーン (マスター)。
- コストの削減 - 実行中のエージェント プール ノードの料金のみを支払う。

Azure で AKS クラスター内のノードの管理を処理することで、クラスターのアップグレードなど、多くのタスクを手動で実行する必要がなくなりました。 Azure ではこれらの重要な保守タスクが処理されるため、AKS ではクラスターへの直接アクセスを提供しません (SSH の使用など)。

### <a name="azure-service-fabric"></a>Azure Service Fabric

Service Fabric は、新しいアプリを作成している場合や、マイクロサービス アーキテクチャを使用するために既存のアプリを作成し直す場合に適しています。 マシンの共有プールで実行されるアプリは小規模から開始し、マシンの数に合わせて大幅にスケーリングすることができます。 ステートフル サービスによってアプリの状態を一貫して安全に保存でき、Service Fabric ではサービスのパーティショニング、スケーリング、可用性が自動的に管理されます。 Service Fabric は、Open Web Interface for .NET (OWIN) および ASP.NET Core による WebAPI もサポートします。 App Service と比較すると、Service Fabric の方が基になるインフラストラクチャをより制御でき、直接アクセスもできます。 サーバーのリモート制御、またはサーバーのスタートアップ タスクの構成ができます。

### <a name="azure-virtual-machines"></a>Azure Virtual Machines

既存のアプリケーションで大幅な変更を App Service または Service Fabric で実行する必要がある場合は、クラウドへの移行を簡略化するために Virtual Machines を選択できます。 ただし、Azure App Service および Service Fabric と比較すると、VM の構成、セキュリティ保護、保守を正しく行うには、さらなる時間と IT の専門知識が必要になります。 Azure Virtual Machines を検討している場合は、現在の VM 環境のパッチ適用、更新、管理に必要な、継続的な保守作業を考慮してください。 Azure Virtual Machines はサービスとしてのインフラストラクチャ (IaaS) で、App Service と Service Fabric は PaaS です。

#### <a name="feature-comparison"></a>機能の比較

| 機能                                                                                    | App Service | コンテナー (AKS) | Service Fabric | 仮想マシン |
| ------------------------------------------------------------------------------------------ | ----------- | ---------------- | -------------- | --------------- |
| ほぼ即時のデプロイ                                                                    | x           | x                | x              |                 |
| 再デプロイせずに大型のマシンにスケールアップ                                               | x           | x                | x              |                 |
| インスタンスによるコンテンツと構成の共有。スケーリング時の再デプロイまたは再構成が不要 | x           | x                | x              |                 |
| 複数のデプロイ環境 (運用環境、ステージング)                                     | x           | x                | x              |                 |
| OS の自動更新の管理                                                             | x           | x                |                |                 |
| 32/64 ビットのプラットフォームのシームレスな切り替え                                             | x           | x                |                |                 |
| Git、FTP によるコードのデプロイ                                                                  | x           | x                |                | x               |
| WebDeploy によるコードのデプロイ                                                                 | x           | x                |                | x               |
| TFS によるコードのデプロイ                                                                       | x           | x                | x              | x               |
| 多層アーキテクチャの Web または Web サービスのホスティング                                    | x           | x                | x              | x               |
| Service Bus、Storage、SQL Database のような Azure サービスへのアクセス                              | x           | x                | x              | x               |
| 任意のカスタム MSI のインストール                                                                     |             | x                | x              | x               |

## <a name="logical-processes"></a>論理プロセス

アプリケーションから分離できる個々の論理プロセスは、Azure Functions に関係なく "サーバーレス" な方法でデプロイできます。 Azure Functions では、アプリケーションまたはインフラストラクチャの実行を気にせずに、特定の問題で必要なコードのみを記述できます。 C\#、F\#、Node.js、Python、PHP などのさまざまなプログラミング言語を選択できるため、当面のタスクに対して最も生産性の高い言語を使用できます。 ほとんどのクラウドベースのソリューションと同様、使用した時間に対してのみ料金を支払います。Azure Functions は必要に応じて確実にスケール アップされます。

## <a name="data"></a>データ

Azure はさまざまなデータ記憶域のオプションを提供しているため、アプリケーションが対象となるデータに適したデータ プロバイダーを使用できます。

トランザクションに基づくリレーショナル データの場合、Azure SQL Database が最も適しています。 高パフォーマンスの読み取りが多くのデータの場合、Azure SQL Database に基づく Redis キャッシュが適しています。

構造化されていない JSON データは、SQL Database 列から Azure Storage の Blob またはテーブル、DocumentDB まで、さまざまな方法で格納できます。 このうち、DocumentDB がクエリ機能では最も優れており、クエリのサポートを必要とする JSON ベースのドキュメントが多数ある場合は、このオプションが推奨されます。

アプリケーションの動作を調整するために使用する一時的なコマンドベースの、またはイベントベースのデータでは、Azure Service Bus または Azure Storage キューを使用できます。 Azure Storage Bus はより柔軟性に優れているため、アプリケーション内、およびアプリケーション間で重要なメッセージをやり取りする場合に推奨されるサービスです。

## <a name="architecture-recommendations"></a>アーキテクチャに関する推奨事項

アプリケーションの要件で、アーキテクチャについて指示している必要があります。 利用できるさまざまな Azure サービスが多くあります。 適切なサービスを選ぶことが重要です。 Microsoft では、一般的なシナリオに最適化された典型的なアーキテクチャを特定できるように、参照アーキテクチャのギャラリーを提供しています。 アプリケーションの要件に最も近い、または少なくとも使い始めに適している参照アーキテクチャを見つけることができます。

図 11-2 は、参照アーキテクチャの例です。 この図は、マーケティングに最適化された Sitecore コンテンツ管理システム Web サイトに推奨されるアーキテクチャの手法を示しています。

![](./media/image11-2.png)

**図 11-1** Sitecore マーケティング Web サイトの参照アーキテクチャ。

**参照 – Azure のホスティングの推奨事項**

- Azure ソリューション アーキテクチャ\
  <https://azure.microsoft.com/solutions/architecture/>

- Azure の開発者ガイド\
  <https://azure.microsoft.com/campaigns/developer-guide/>

- Web Apps の概要\
  <https://docs.microsoft.com/azure/app-service/app-service-web-overview>

- Azure App Service、Virtual Machines、Service Fabric および Cloud Services の比較\
  <https://docs.microsoft.com/azure/app-service-web/choose-web-site-cloud-service-vm>

- Azure Kubernetes Service (AKS) の概要\
  <https://docs.microsoft.com/azure/aks/intro-kubernetes>

>[!div class="step-by-step"]
>[前へ](development-process-for-azure.md)