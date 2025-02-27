---
title: 構成チャネル ファクトリ
ms.date: 03/30/2017
ms.assetid: 3b749493-bd8a-4ccb-893e-5948901a1486
ms.openlocfilehash: 1b74c15599ebc932a2a0ed46d646b54bec986794
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2019
ms.locfileid: "70045657"
---
# <a name="configuration-channel-factory"></a>構成チャネル ファクトリ
このサンプルでは、<xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> の使用方法を示します。 で<xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601>は、WCF クライアントの構成を一元的に管理できます。 これは、アプリケーション ドメインによる読み込みの後に構成が選択または変更される場合にも役立ちます。

## <a name="demonstrates"></a>使用例
 <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601>

## <a name="discussion"></a>説明
 このサンプルでは、既定のアプリケーション構成ファイルを使用することなく、<xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> を使用して、クライアント アプリケーションに特定の構成ファイルを追加する方法を示します。

 このサンプルは、2 つのプロジェクトで構成されます。 最初のプロジェクトは、クライアントから送信されるメッセージに応答するために実行される単純なサービスです。 2 番目のプロジェクトは、Test.config 構成ファイルの <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> を使用して、2 つの <xref:System.Configuration.ExeConfigurationFileMap> オブジェクトを作成し、サービスとの通信にそれらのオブジェクトを使用するクライアント アプリケーションです。 どちらのクライアントも Test.config で指定された構成を使用してサービスと通信します。

 次のコードでは、カスタム構成ファイルをクライアント アプリケーションに追加します。

```csharp
ExeConfigurationFileMap fileMap = new ExeConfigurationFileMap();
fileMap.ExeConfigFilename = "Test.config";
Configuration newConfiguration = ConfigurationManager.OpenMappedExeConfiguration(fileMap, ConfigurationUserLevel.None);

ConfigurationChannelFactory<ICalculatorChannel> factory1 = new ConfigurationChannelFactory<ICalculatorChannel>("endpoint1", newConfiguration, new EndpointAddress("http://localhost:8000/servicemodelsamples/service"));
ICalculatorChannel client1 = factory1.CreateChannel();
```

#### <a name="to-set-up-build-and-run-the-sample"></a>サンプルをセットアップ、ビルド、および実行するには

1. 管理者特権で Visual Studio 2012 を開きます。

2. ConfigurationChannelFactory ソリューション (2 つのプロジェクト) を右クリックし、 **[プロパティ]** を選択します。

3. **[共通プロパティ]** で、 **[スタートアッププロジェクト]** を選択し、 **[マルチスタートアッププロジェクト]** をクリックします。

4. **サービス**プロジェクトを一覧の先頭に移動し、**アクションを ' start '** に変更します。次に、**サービス**プロジェクトの後に**クライアント**プロジェクトを移動します。このとき、**アクションを ' start '** にして、**クライアント**プロジェクトを実行します。**サービス**プロジェクトの後。

5. **[OK]** をクリックし、f5 キー (または CTRL + F5 キー) を押してサンプルを実行します。

> [!IMPORTANT]
> サンプルは、既にコンピューターにインストールされている場合があります。 続行する前に、次の (既定の) ディレクトリを確認してください。  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> このディレクトリが存在しない場合は、 [Windows Communication Foundation (wcf) および Windows Workflow Foundation (WF) のサンプルの .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780)にアクセスして、すべての[!INCLUDE[wf1](../../../../includes/wf1-md.md)] Windows Communication Foundation (wcf) とサンプルをダウンロードしてください。 このサンプルは、次のディレクトリに格納されます。  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\ConfigurationChannelFactory`
