---
title: "UDP アクティベーション"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4b0ccd10-0dfb-4603-93f9-f0857c581cb7
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 32c452042ffee0a09143042900d24b7429234bec
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/02/2017
---
# <a name="udp-activation"></a>UDP アクティベーション
このサンプルがに基づいて、[トランスポート: UDP](../../../../docs/framework/wcf/samples/transport-udp.md)サンプルです。 拡張されて、[トランスポート: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) Windows プロセス アクティブ化サービス (WAS) を使用するプロセス アクティブ化をサポートするサンプルです。  
  
 サンプルは、次の 3 つの主要素で構成されます。  
  
-   UDP プロトコル アクティベータ。アクティベーション対象のアプリケーションの代わりに UDP メッセージを受信するスタンドアロンのプロセスです。  
  
-   UDP カスタム トランスポートを使用してメッセージを送信するクライアント。  
  
-   UDP カスタム トランスポート経由でメッセージを受信するサービス。WAS によってアクティブ化されるワーカー プロセス内でホストされています。  
  
## <a name="udp-protocol-activator"></a>UDP プロトコル アクティベータ  
 UDP プロトコル アクティベータは、[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] クライアントと [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] サービス間のブリッジです。 トランスポート層で UDP プロトコルを介するデータ通信を実現します。 主な機能は、次の 2 つです。  
  
-   WAS リスナ アダプタ (LA)。WAS と連携し、受信メッセージに応答してプロセスをアクティブ化します。  
  
-   UDP プロトコル リスナ。アクティベーション対象のアプリケーションの代わりに UDP メッセージを受け入れます。  
  
 このアクティベータは、サーバー コンピュータ上でスタンドアロン プログラムとして実行される必要があります。 通常、WAS リスナ アダプタ (NetTcpActivator や NetPipeActivator など) は、長時間にわたって実行される Windows サービスに実装されます。 ただしこのサンプルでは、単純化してわかりやすくするために、このプロトコル アクティベータをスタンドアロン アプリケーションとして実装しています。  
  
### <a name="was-listener-adapter"></a>WAS リスナ アダプタ  
 UDP の WAS リスナ アダプタは `UdpListenerAdapter` クラスに実装されています。 これは WAS とやり取りするモジュールで、UDP プロトコル用アプリケーションのアクティベーションを実行します。 これは、次の Webhost API を呼び出すことによって実行されます。  
  
-   `WebhostRegisterProtocol`  
  
-   `WebhostUnregisterProtocol`  
  
-   `WebhostOpenListenerChannelInstance`  
  
-   `WebhostCloseAllListenerChannelInstances`  
  
 このリスナ アダプタは、`WebhostRegisterProtocol` を最初に呼び出した後、applicationHost.config (%windir%\system32\inetsrv 内にあります) に登録されているすべてのアプリケーションの WAS からコールバック `ApplicationCreated` を受信します。 このサンプルで処理するのは、(プロトコル ID が "net.udp" の) UDP プロトコルが有効なアプリケーションだけです。 他の実装でこのアプリケーションへの動的な構成変更 (アプリケーションを無効から有効に移行する場合など) に応答する場合、そうした実装では異なる方法でアプリケーションを処理することがあります。  
  
 コールバック `ConfigManagerInitializationCompleted` が受信される場合、WAS により、プロトコルの初期化に関するすべての通知が完了したことを示します。 その時点で、リスナ アダプタはアクティベーション要求を処理する準備ができています。  
  
 アプリケーションに初めて新しい要求が届くと、このリスナ アダプタは `WebhostOpenListenerChannelInstance` を WAS に呼び出します。ワーカー プロセスがまだ開始されていない場合は、これにより開始されます。 次に、プロトコル ハンドラが読み込まれ、リスナ アダプタと仮想アプリケーション間の通信を開始できるようになります。  
  
 %SystemRoot%\System32\inetsrv\ApplicationHost.config にリスナー アダプターが登録されている、<`listenerAdapters`> には次のセクションします。  
  
```xml  
<add name="net.udp" identity="S-1-5-21-2127521184-1604012920-1887927527-387045" />  
```  
  
### <a name="protocol-listener"></a>プロトコル リスナ  
 UDP プロトコル リスナはプロトコル アクティベータ内部のモジュールで、仮想アプリケーションの代わりに UDP エンドポイントでリッスンします。 これは `UdpSocketListener` クラスに実装されています。 エンドポイントは `IPEndpoint` として表され、このポート番号はサイトのプロトコルのバインディングから抽出されます。  
  
### <a name="control-service"></a>サービスの制御  
 このサンプルでは、[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] を使用してアクティベータと WAS ワーカー プロセス間で通信を行います。 アクティベータに存在するサービスは、コントロール サービスと呼ばれます。  
  
## <a name="protocol-handlers"></a>プロトコル ハンドラー  
 リスナ アダプタが `WebhostOpenListenerChannelInstance` を呼び出した後、ワーカー プロセスが開始されていない場合は WAS プロセス マネージャによって開始されます。 ワーカー プロセス内部のアプリケーション マネージャは、UDP プロセス プロトコル ハンドラ (PPH) を読み込み、`ListenerChannelId` を要求します。 次に呼び出して、PPH`IAdphManager`です。`StartAppDomainProtocolListenerChannel` UDP AppDomain プロトコル ハンドラ (ADPH) を開始します。  
  
## <a name="hostedudptransportconfiguration"></a>HostedUDPTransportConfiguration  
 この情報は、Web.config で次のように登録されます。  
  
```xml  
<serviceHostingEnvironment>  
<add name="net.udp" transportConfigurationType="Microsoft.ServiceModel.Samples.Hosting.HostedUdpTransportConfiguration, UdpActivation, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6fa904d2da1848d6" />  
</serviceHostingEnvironment>  
```  
  
## <a name="special-setup-for-this-sample"></a>このサンプルの特殊なセットアップ  
 このサンプルは、Windows Vista、Windows Server 2008、または Windows 7 でのみビルドおよび実行可能です。 サンプルを実行するには、最初にすべてのコンポーネントを正しくセットアップする必要があります。 サンプルをインストールするには、次の手順に従います。  
  
#### <a name="to-set-up-this-sample"></a>このサンプルをセットアップするには  
  
1.  次のコマンドを使用して、[!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 4.0 をインストールします。  
  
    ```  
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable  
    ```  
  
2.  Windows Vista でプロジェクトをビルドします。 コンパイル後、ビルド後のフェーズで次の操作を実行します。  
  
    -   UDP バインディングを [既定の Web サイト] のサイトにインストールします。  
  
    -   物理パス "%SystemDrive%\inetpub\wwwroot\servicemodelsamples" をポイントする、仮想アプリケーション "ServiceModelSamples" を作成します。  
  
    -   さらに、この仮想アプリケーションの "net.udp" プロトコルを有効にします。  
  
3.  ユーザー インターフェイス アプリケーション "WasNetActivator.exe" を起動します。 クリックして、**セットアップ** タブで、次のチェック ボックスをオンにし、をクリックして**インストール**それらをインストールします。  
  
    -   UDP リスナ アダプタ  
  
    -   UDP プロトコル ハンドラ  
  
4.  をクリックして、**アクティベーション**のユーザー インターフェイス アプリケーション"WasNetActivator.exe"のタブです。 をクリックして、**開始**リスナー アダプターを開始するボタンをクリックします。 これで、プログラムを実行する準備ができました。  
  
    > [!NOTE]
    >  このサンプルの実行後は、Cleanup.bat を実行して、[既定の Web サイト] から net.udp バインディングを削除する必要があります。  
  
## <a name="sample-usage"></a>サンプルの使用方法  
 コンパイル後、次の 4 つの異なるバイナリが生成されます。  
  
-   Client.exe: クライアント コード。 App.config は、クライアント構成ファイルの Client.exe.config にコンパイルされます。  
  
-   UDPActivation.dll: 主要なすべての UDP 実装を含むライブラリ。  
  
-   Service.dll: サービス コード。 これは、ServiceModelSamples 仮想アプリケーションの \bin ディレクトリにコピーされます。 このサービス ファイルは Service.svc で、構成ファイルは Web.config です。これらをコンパイルすると、%SystemDrive%\Inetpub\wwwroot\ServiceModelSamples にコピーされます。  
  
-   WasNetActivator: UDP アクティベータ プログラム。  
  
-   必要なすべての要素が正しくインストールされていることを確認します。 サンプルを実行する方法を、次の手順に示します。  
  
1.  次の Windows サービスが開始されていることを確認します。  
  
    -   Windows プロセス アクティブ化サービス (WAS)。  
  
    -   インターネット インフォメーション サービス (IIS): W3SVC。  
  
2.  次に、アクティベータ WasNetActivator.exe を起動します。 下にある、**アクティブ化** タブ、唯一のプロトコル**UDP**、ドロップ ダウン リストで選択しました。 をクリックして、**開始**アクティベーターを起動するボタンをクリックします。  
  
3.  アクティベータが開始されると、コマンド ウィンドウで Client.exe を実行することにより、クライアント コードを実行できます。 このサンプルの出力は、次のようになります。  
  
    ```  
    Testing Udp Activation.  
    Start the status service.  
    Sending UDP datagrams.  
    Type a word that you want to say to the server: Hello, world!  
        Sending datagram: Hello, world![0]  
        Sending datagram: Hello, world![1]  
        Sending datagram: Hello, world![2]  
        Sending datagram: Hello, world![3]  
        Sending datagram: Hello, world![4]  
    Calling UDP duplex contract (ICalculatorContract).  
        0 + 0 = 0  
        1 + 2 = 3  
        2 + 4 = 6  
        3 + 6 = 9  
        4 + 8 = 12  
    Getting status and dump server traces:  
        Operation 'Hello' is called: Hello, world![0]  
        Operation 'Hello' is called: Hello, world![1]  
        Operation 'Hello' is called: Hello, world![2]  
        Operation 'Hello' is called: Hello, world![3]  
        Operation 'Hello' is called: Hello, world![4]  
        Operation 'Add' is called: 0 + 0  
        Operation 'Add' is called: 1 + 2  
        Operation 'Add' is called: 2 + 4  
        Operation 'Add' is called: 3 + 6  
        Operation 'Add' is called: 4 + 8  
    Press <ENTER> to complete test.  
    ```  
  
> [!IMPORTANT]
>  サンプルは、既にコンピューターにインストールされている場合があります。 続行する前に、次の (既定の) ディレクトリを確認してください。  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  このディレクトリが存在しない場合は、「 [.NET Framework 4 向けの Windows Communication Foundation (WCF) および Windows Workflow Foundation (WF) のサンプル](http://go.microsoft.com/fwlink/?LinkId=150780) 」にアクセスして、 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] および [!INCLUDE[wf1](../../../../includes/wf1-md.md)] のサンプルをすべてダウンロードしてください。 このサンプルは、次のディレクトリに格納されます。  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Transport\UdpActivation`  
  
## <a name="see-also"></a>関連項目
