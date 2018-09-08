---
title: 構成ベースのアクティブ化
ms.date: 03/30/2017
ms.assetid: 21bb762e-c43e-4b0c-887b-5e434d665838
ms.openlocfilehash: e016dffdaf93b222c1fd2380bfa175256b009068
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/08/2018
ms.locfileid: "44188307"
---
# <a name="configuration-based-activation"></a>構成ベースのアクティブ化
このサンプルでは、.svc ファイルを必要とせずに Windows Communication Foundation (WCF) サービスをアクティブ化する方法を示します。  
  
> [!IMPORTANT]
>  サンプルは、既にコンピューターにインストールされている場合があります。 続行する前に、次の (既定の) ディレクトリを確認してください。  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  このディレクトリが存在しない場合に移動[Windows Communication Foundation (WCF) と .NET Framework 4 向けの Windows Workflow Foundation (WF) サンプル](https://go.microsoft.com/fwlink/?LinkId=150780)すべて Windows Communication Foundation (WCF) をダウンロードして[!INCLUDE[wf1](../../../../includes/wf1-md.md)]サンプル。 このサンプルは、次のディレクトリに格納されます。  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Hosting\ConfigBasedActivation`  
  
## <a name="sample-details"></a>サンプルの詳細  
 このサンプルで、クライアントは、WCF テスト クライアントであり、サービスが IIS でホストされています。  
  
> [!NOTE]
>  このサンプルのセットアップ手順とビルド手順については、このトピックの最後を参照してください。  
  
### <a name="activation-of-services-without-requiring-a-svc-file"></a>.svc ファイルを必要としない、サービスのアクティブ化  
 [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)] では、サービスをアクティブ化するために .svc ファイルが必要でした。 アプリケーションと共に追加ファイルを配置して管理する必要があったため、このことは管理のオーバーヘッドを増やす原因となりました。 [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)] リリースでは、アプリケーション構成ファイルを使用してアクティブ化コンポーネントを構成することができます。  
  
 [!INCLUDE[netfx40_short](../../../../includes/netfx40-short-md.md)] では、アプリケーション構成ファイルの <xref:System.ServiceModel.Configuration.ServiceActivationElement> に、新しい構成要素 <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection> が導入されています。 <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection> コレクションは、次のコード例に示すように、サービスのコレクションを受け取ってアクティブ化を行います。  
  
```xml  
<serviceActivations>  
   <add relativeAddress="Calculator.svc" service="Microsoft.ServiceModel.Samples.CalculatorService" />  
  
<serviceActivations>  
```  
  
 注目すべき点は、構成が .svc ファイルの構成に非常に似ていることです。 導入された追加の属性は、サービスのアドレスを提供する `relativeAddress` です。 相対アドレスは、サービスの仮想パスでもあります。 ホストは、ファイルの Web.config ファイルが存在する場合に、そのファイルを `virtualPath` の場所から取得します。ファイルが存在しない場合、ホストはその親フォルダーを再帰的に検索します。  
  
> [!NOTE]
>  このサンプルを機能させるには、IIS でホストする必要があります。  
  
#### <a name="to-use-this-sample"></a>このサンプルを使用するには  
  
1.  [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] を使用して、Service.csproj ファイルを開きます。  
  
2.  ソリューションをビルドするには、Ctrl キーと Shift キーを押しながら B キーを押します。  
  
3.  WCFTestClient.exe を実行してサービスをテストします。  
  
4.  [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)]を使用して、%SystemDrive%\Program Files\Microsoft Visual Studio 10.0\Common7\IDE フォルダーに移動します。  
  
5.  WcfTestClient.exe を実行します。  
  
6.  サービスの MEX アドレスを設定します。  
  
7.  Ctrl と Shift キーを押しながら A キーを押して、サービス アドレスを設定します。  
  
8.  アドレスに設定 http://localhost/ServiceModelSamples/Calculator.svc です。  
  
9. `Add` 操作を実行します。 `n1` パラメーターの値を 10 に、`n2` パラメーターの値を 15 に設定します。  
  
10. キーを押して**呼び出す**します。  
  
     予期される結果は 25 です。  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>サンプルをセットアップ、ビルド、および実行するには  
  
1.  実行済みであるかどうかを必ず、 [Windows Communication Foundation サンプルの 1 回限りのセットアップ手順](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)します。  
  
2.  ソリューションの C# 版または Visual Basic .NET 版をビルドするには、「 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)」の手順に従います。  
  
3.  ソリューションがビルドされたら、Setup.bat を実行し、IIS で ServiceModelSamples アプリケーションを設定します。 ServiceModelSamples ディレクトリは、IIS アプリケーションとして表示されます。  
  
4.  1 つまたは複数コンピューター構成では、サンプルを実行する手順については、 [Windows Communication Foundation サンプルの実行](../../../../docs/framework/wcf/samples/running-the-samples.md)します。  
  
## <a name="see-also"></a>関連項目  
 [AppFabric のホストおよび永続化のサンプル](https://go.microsoft.com/fwlink/?LinkId=193961)
