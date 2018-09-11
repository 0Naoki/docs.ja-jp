---
title: WCF Data Services の開発と配置
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, developing
- WCF Data Services, deploying
- deploying [WCF Data Services
- developing applications [WCF Data Services]
ms.assetid: 6557c0e3-5aea-4f6e-bc14-77ad317a168b
ms.openlocfilehash: cf1782eaf54701f0cf93576325b3d46e8bc4d3f1
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2018
ms.locfileid: "44271188"
---
# <a name="develop-and-deploy-wcf-data-services"></a>開発し、WCF Data Services のデプロイ

このトピックでは、開発と、WCF Data Services の展開について情報を提供します。 WCF Data Services の基本的な詳細については、次を参照してください。 [Getting Started](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md)と[概要](../../../../docs/framework/data/wcf/wcf-data-services-overview.md)します。

## <a name="develop-wcf-data-services"></a>WCF Data Services を開発します。

サポートするデータ サービスを作成する WCF Data Services を使用する場合、[!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)]開発中に、次の基本的なタスクを実行する必要があります。

1.  **データ モデルを定義する**

     WCF Data Services には、さまざまなさまざまな遅延バインディング データ型へのリレーショナル データベースからのデータ ソースからデータに基づくデータ モデルを定義するためのデータ サービス プロバイダーがサポートしています。 詳細については、次を参照してください。[データ サービス プロバイダー](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md)します。

2.  **データ サービスを作成する**

     最も基本的なデータ サービスでは、 <xref:System.Data.Services.DataService%601> クラスを継承するクラスを `T` 型 (エンティティ コンテナーの名前空間修飾名) と一緒に公開します。 詳細については、「 [Defining WCF Data Services](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)の開発と配置について説明します。

3.  **データ サービスを構成する**

     既定では、WCF Data Services には、エンティティ コンテナーによって公開されているリソースへのアクセスが無効にします。 <xref:System.Data.Services.DataServiceConfiguration>インターフェイスでは、リソースへのアクセスを構成し、サービス操作、OData のサポートされているバージョンを指定して、バッチ動作や返されるエンティティの最大数など、他のサービス全体の動作を定義できます。1 つの応答フィード。 詳細については、次を参照してください。[データ サービスの構成](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md)します。

このトピックでは、Visual Studio を使用して、主に開発およびデータ サービスの配置をについて説明します。 OData フィードとしてデータを公開するための WCF Data Services によって提供される柔軟性については、次を参照してください。 [Defining WCF Data Services](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)します。

### <a name="choose-a-development-web-server"></a>開発 Web サーバーを選択します。

として WCF データ サービスを開発する際に、[!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]アプリケーションまたは[!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]Visual Studio 2015 を使用して Web サイト、開発中に、データ サービスを実行する Web サーバーの選択肢があります。 次の Web サーバーは、テストし、ローカル コンピューターでデータ サービスのデバッグを容易にできるように Visual Studio と統合します。

1.  **ローカル IIS サーバー**

     インターネット インフォメーション サービス (IIS) で実行される [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] アプリケーションまたは [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Web サイトとしてデータ サービスを作成する場合は、ローカル コンピューターで IIS を使用してデータ サービスを開発およびテストすることをお勧めします。 IIS でデータ サービスを実行すると、デバッグ時における HTTP 要求のトレースが容易になります。 また、データ サービスに必要なファイルやデータベースなどのリソースにアクセスするために IIS で必要とされる権限を事前に確認することもできます。 データ サービスを IIS で実行する IIS と Windows Communication Foundation (WCF) の両方がインストールされ、正しく構成されていることを確認する必要がありますが、ファイル システムおよびデータベースで IIS アカウントへのアクセスを付与します。 詳細については、「 [方法: IIS 上で実行する WCF Data Service を開発する](../../../../docs/framework/data/wcf/how-to-develop-a-wcf-data-service-running-on-iis.md)」を参照してください。

    > [!NOTE]
    > ローカル IIS サーバーを構成する開発環境を有効にする管理者権限を持つ Visual Studio を実行する必要があります。

2.  **Visual Studio 開発サーバー**

     Visual Studio には、組み込みの Web サーバー、Visual Studio 開発サーバーが含まれています。 これは、既定の Web サーバーを[!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]プロジェクト。 この Web サーバーは、開発時にローカル コンピューターで [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] プロジェクトを実行するように設計されています。 [WCF Data Services クイック スタート](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)Visual Studio 開発サーバーで実行されているデータ サービスを作成する方法を示しています。

     Visual Studio 開発サーバーを使用してデータ サービスを開発するときに、次の制限の注意があります。

    -   このサーバーにはローカル コンピューター上でしかアクセスできません。

    -   このサーバーは、HTTP メッセージの既定のポートであるポート 80 ではなく、 `localhost` および特定のポートでリッスンします。 詳細については、「 [ASP.NET Web プロジェクト用の Visual Studio の Web サーバー](https://msdn.microsoft.com/library/31d4f588-df59-4b7e-b9ea-e1f2dd204328)」を参照してください。

    -   このサーバーでは、現在のユーザー アカウントのコンテキストでデータ サービスが実行されます。 たとえば、管理者レベルのユーザーとして実行している場合、Visual Studio 開発サーバーで実行されているデータ サービスは管理者レベルの特権があります。 そのため、データ サービスは、IIS サーバーに配置されたときにはアクセスする権限を持たないリソースにも、アクセスできることになります。

    -   このサーバーには、認証など、IIS の必要以上の機能は含まれていません。

    -   このサーバーは、チャンク HTTP ストリームを処理できない、データ サービスから大きなバイナリ データにアクセスするときに、WCF Data Services クライアントによって既定をする送信されます。 詳細については、次を参照してください。[ストリーミング プロバイダー](../../../../docs/framework/data/wcf/streaming-provider-wcf-data-services.md)します。

    -   このサーバーには、期間の処理に関する問題 (`.`) この文字がキーの値で WCF Data Services でサポートされている場合でも、URL 内の文字します。

    > [!TIP]
    > 場合でも、Visual Studio 開発サーバーを使用すると、開発中に、データ サービスをテストでは、IIS を実行している Web サーバーへの配置後にもう一度テストする必要があります。

3.  **Microsoft Azure 開発環境**

     Windows Azure Tools for Visual Studio には、Visual Studio での Windows Azure サービスを開発するためのツールの統合セットが含まれています。 これらのツールでは、Microsoft Azure に配置できるデータ サービスを開発し、配置前にローカル コンピューターでデータ サービスをテストすることができます。 Visual Studio を使用して Windows Azure platform で実行されるデータ サービスを開発する場合は、これらのツールを使用します。 Visual Studio からの Windows Azure Tools をダウンロードすることができます、 [Microsoft ダウンロード センター](https://go.microsoft.com/fwlink/?LinkID=201848)します。 Windows Azure 上で実行されるデータ サービスの開発の詳細については、投稿をご覧ください。 [Windows Azure での OData サービスを展開する](https://go.microsoft.com/fwlink/?LinkId=201847)します。

### <a name="development-tips"></a>開発のヒント

データ サービスを開発する際は、次の点を考慮してください。

-   ユーザーを認証する場合や、特定のユーザーのアクセスを制限する場合は、データ サービスのセキュリティ要件を決定します。 詳細については、「 [Securing WCF Data Services](../../../../docs/framework/data/wcf/securing-wcf-data-services.md)」を参照してください。

-   データ サービスをデバッグするときは、HTTP 検査プログラムを使用すると、要求メッセージおよび応答メッセージの内容を検査できるので非常に便利です。 生のパケットを表示できるネットワーク パケット アナライザーを使用すると、データ サービスの HTTP 要求および HTTP 応答を検査できます。

-   データ サービスのデバッグ時は、通常の操作時以上に、データ サービスの詳細なエラー情報が必要になることがあります。 データ サービスから詳細なエラー情報を取得するには、 <xref:System.Data.Services.DataServiceConfiguration.UseVerboseErrors%2A> の <xref:System.Data.Services.DataServiceConfiguration> プロパティを `true` に設定し、データ サービス クラスの <xref:System.ServiceModel.Description.ServiceDebugBehavior.IncludeExceptionDetailInFaults%2A> 属性の <xref:System.ServiceModel.Description.ServiceDebugBehavior> プロパティを `true`に設定します。 詳細については、投稿をご覧ください。 [WCF Data Services のデバッグ](https://go.microsoft.com/fwlink/?LinkId=201868)します。 また、HTTP メッセージング レイヤーで発生する例外を表示するのには WCF でのトレースを有効にできます。 詳細については、「 [Configuring Tracing](../../../../docs/framework/wcf/diagnostics/tracing/configuring-tracing.md)」を参照してください。

-   データ サービスとして開発は、通常、[!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]アプリケーション プロジェクトができますもサービスを作成するデータとして、 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Visual Studio で Web サイト プロジェクト。 2 つの種類のプロジェクト間の違いについては、次を参照してください。 [NIB: Web アプリケーション プロジェクトと Visual Studio での Web サイト プロジェクト](https://msdn.microsoft.com/library/2861815e-f5a2-4378-a2f8-b8a86dc012f5)します。

-   使用してデータ サービスを作成すると、**新しい項目の追加**Visual studio で、データ サービス ダイアログ ボックスがによってホストされている[!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]IIS でします。 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] と IIS がデータ サービスの既定のホストですが、その他のホスト オプションもサポートされています。 詳細については、次を参照してください。[データ サービスのホスティング](../../../../docs/framework/data/wcf/hosting-the-data-service-wcf-data-services.md)します。

## <a name="deploy-wcf-data-services"></a>WCF Data Services をデプロイします。

WCF Data Services では、データ サービスをホストするプロセスを柔軟に選択できます。 Visual Studio を使用して、次のプラットフォームにデータ サービスをデプロイすることができます。

-   **IIS でホストされる Web サーバー**

     データ サービスを [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] プロジェクトとして開発すると、 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] の標準配置プロセスを使用して IIS Web サーバーに配置することができます。  Visual Studio には、次の展開テクノロジの[!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]種類に応じての[!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]プロジェクトを配置するデータ サービスをホストします。

    -   **ASP.NET Web アプリケーション用の配置テクノロジ**

        -   [Web 配置パッケージ](https://msdn.microsoft.com/library/1f9713c8-9540-494c-b80d-9893b970ad6f)

        -   [ワンクリック発行](https://msdn.microsoft.com/library/59226246-99ad-4aec-975d-7c61e8a8911c)

    -   **ASP.NET Web サイト用の配置テクノロジ**

        -   [Web サイトのコピー ツール](https://msdn.microsoft.com/library/b819aed4-014b-427e-be80-02317b1bb003)

        -   [Web サイトの発行ツール](https://msdn.microsoft.com/library/d0a1a20f-15be-4940-9485-cb8e4aa8181b)

        -   [XCopy](https://msdn.microsoft.com/library/4312c651-2119-49be-bbeb-ee28bdbfe71e)

     配置オプションの詳細については、[!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]アプリケーションを参照してください[for Visual Studio および ASP.NET Web 配置の概要](https://msdn.microsoft.com/library/99bd1927-b59f-4e02-87b4-55c6ba2adbc3)します。

    > [!TIP]
    > データ サービスを IIS に配置する前に、IIS を実行している Web サーバーへの配置をテストしておく必要があります。 詳細については、「 [How to: Develop a WCF Data Service Running on IIS](../../../../docs/framework/data/wcf/how-to-develop-a-wcf-data-service-running-on-iis.md)」を参照してください。

-   **Windows Azure**

     Visual Studio の Windows Azure Tools を使用して、Windows Azure にデータ サービスをデプロイできます。 Visual Studio からの Windows Azure Tools をダウンロードすることができます、 [Microsoft ダウンロード センター](https://go.microsoft.com/fwlink/?LinkID=201848)します。 Windows Azure へのデータ サービスの展開に関する詳細については、投稿をご覧ください。 [Windows Azure での OData サービスを展開する](https://go.microsoft.com/fwlink/?LinkId=201847)します。

### <a name="deployment-considerations"></a>配置に関する注意事項

データ サービスを配置する際は、次の点を考慮してください。

-   [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] プロバイダーを使用して SQL Server データベースにアクセスするデータ サービスを配置する場合、データ サービスの配置でのデータ構造、データ、またはその両方の反映も必要になることがあります。 Visual Studio が先のデータベースでこれを行うスクリプト (.sql ファイル) を自動的に作成し、これらのスクリプトは、の Web 配置パッケージに含めることができます、[!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]アプリケーション。 詳細については、次を参照してください。[方法: Web アプリケーション プロジェクトでのデータベース配置](https://msdn.microsoft.com/library/683b33f1-8a3d-45cf-af6e-61ab50fc518b)します。 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Web サイトでは、これを行うを使用して、 **Database Publishing Wizard** Visual Studio でします。 詳細については、次を参照してください。[データベース公開ウィザードを使用してデータベースを展開する](https://msdn.microsoft.com/library/1e3682e7-8b57-4da6-a393-af9640ccf8b7)します。

-   WCF Data Services には、基本的な WCF 実装が含まれているために、Windows Server で実行されている IIS に配置されたデータ サービスを監視するのに Windows Server AppFabric を使用できます。 Windows Server AppFabric を使用してデータ サービスを監視する方法の詳細については、投稿をご覧ください。 [Windows Server AppFabric による WCF Data Services の追跡](https://go.microsoft.com/fwlink/?LinkID=202005)します。

## <a name="see-also"></a>関連項目

- [データ サービスのホスティング](../../../../docs/framework/data/wcf/hosting-the-data-service-wcf-data-services.md)
- [WCF Data Services のセキュリティ保護](../../../../docs/framework/data/wcf/securing-wcf-data-services.md)
- [WCF Data Services の定義](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)
