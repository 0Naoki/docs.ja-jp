---
title: WS-AtomicTransaction サポートの構成
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WS-AT protocol [WCF], configuring WS-Atomic Transaction
ms.assetid: cb9f1c9c-1439-4172-b9bc-b01c3e09ac48
caps.latest.revision: 31
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b2d94c96b8cc225344300540d9fc406a4742db2a
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/30/2018
---
# <a name="configuring-ws-atomic-transaction-support"></a>WS-AtomicTransaction サポートの構成
ここでは、WS-AtomicTransaction (WS-AT) 構成ユーティリティを使用して WS-AT サポートを構成する方法について説明します。  
  
## <a name="using-the-ws-at-configuration-utility"></a>WS-AT 構成ユーティリティの使用  
 WS-AT 構成ユーティリティ (wsatConfig.exe) は、WS-AT 設定の構成に使用されます。 WS-AT プロトコル サービスを有効にするには、この構成ユーティリティを使用して、WS-AT の HTTPS ポートを構成し、X.509 証明書をその HTTPS ポートにバインドし、証明書のサブジェクト名または拇印を指定して、承認されたパートナーの証明書を構成する必要があります。 この構成ユーティリティでは、トレース モードを選択して、送信トランザクションの既定のタイムアウト値と受信トランザクションの最大タイムアウト値を設定することもできます。  
  
 このツールの機能は、コンポーネント サービス管理コンソールで Microsoft 管理コンソール (MMC) のプロパティ ページ スナップインを使用するか、またはコマンド ライン ウィンドウから操作できます。 WS-AT サポートをローカル コンピューターで構成するには、コマンド ライン ウィンドウを使用し、ローカル コンピューターとリモート コンピューターの両方で設定を構成するには、MMC スナップインを使用します。  
  
 コマンド ライン ウィンドウは、Windows SDK のインストール場所の "%WINDIR%\Microsoft.NET\Framework\v3.0\Windows Communication Foundation" で使用できます。  
  
 コマンド ライン ツールの詳細については、次を参照してください。 [Ws-atomictransaction 構成ユーティリティ (wsatConfig.exe)](../../../../docs/framework/wcf/ws-atomictransaction-configuration-utility-wsatconfig-exe.md)です。  
  
 実行している場合[!INCLUDE[wxp](../../../../includes/wxp-md.md)]または[!INCLUDE[ws2003](../../../../includes/ws2003-md.md)]に移動して、MMC スナップインにアクセスできる**コントロール パネル]、[管理ツール]、[コンポーネント サービス**を右クリック、**マイ コンピューター**、および選択すると**プロパティ**です。 この場所では、Microsoft 分散トランザクション コーディネーター (MSDTC) を構成することもできます。 構成できるオプションは、[グループ化されて、 **WS-AT**タブです。Windows Vista を実行している場合または[!INCLUDE[lserver](../../../../includes/lserver-md.md)]、MMC スナップインでにあります をクリックして、**開始** ボタン、および入力`dcomcnfg.exe`で、**検索**ボックス。 MMC が開いているときに移動、**マイ Computer\Distributed トランザクション コーディネーター DTC**ノードを右クリックし、**プロパティ**です。 構成できるオプションは、グループ化されて、 **WS-AT**タブです。  
  
 スナップインの詳細については、次を参照してください。、 [Ws-atomictransaction 構成 MMC スナップインで](../../../../docs/framework/wcf/ws-atomictransaction-configuration-mmc-snap-in.md)です。  
  
 ツールのユーザー インターフェイスを有効にするには、WsatUI.dll ファイルを登録しておく必要があります。このファイルは、次のパスにあります。  
  
 %PROGRAMFILES%\Microsoft SDKs\Windows\v6.0\Bin  
  
 製品を登録するには、[コマンド プロンプト] ウィンドウから次のコマンドを実行します。  
  
 `regasm.exe /codebase WsatUI.dll`  
  
## <a name="enabling-ws-at"></a>WS-AT の有効化  
 ポート 443 と、ローカル コンピューター ストアにインストールされている秘密キーを持つ X.509 証明書を使用して、MSDTC 内部で WS-AT プロトコル サービスを有効にするには、wsatConfig.exe ツールを使用して次のコマンドを実行します。  
  
 `WsatConfig.exe –network:enable –port:8443 –endpointCert:<machine|"Issuer\SubjectName"> -accountsCerts:<thumbprint|"Issuer\SubjectName"> -restart`  
  
 個々のパラメーターを、ユーザーの環境に適した値に置き換えます。  
  
 MSDTC 内部で WS-AT プロトコル サービスを無効にするには、wsatConfig.exe ツールを使用して次のコマンドを実行します。  
  
 `WsatConfig.exe –network:disable -restart`  
  
## <a name="configuring-trust-between-two-machines"></a>2 台のコンピューター間での信頼の確立  
 WS-AT プロトコル サービスでは、管理者が、分散トランザクションに参加する個々のアカウントを明示的に承認する必要があります。 2 台のコンピューターの管理者である場合は、両方のコンピューターを構成して、相互の信頼関係を確立することができます。それには、コンピューター間で適切な証明書を交換し、その証明書を適切な証明書ストアにインストールし、wsatConfig.exe ツールを使用して各コンピューターの証明書をお互いの承認済み参加者の証明書リストに追加します。 この手順は、WS-AT を使用する 2 台のコンピューター間で分散トランザクションを実行するために必要です。  
  
 次の例では、A と B という 2 台のコンピューター間で信頼を確立する手順を示します。  
  
### <a name="creating-and-exporting-certificates"></a>証明書の作成とエクスポート  
 この手順では、MMC 証明書スナップインを使用する必要があります。 このスナップインにアクセスするには、[スタート] ボタンをクリックして [ファイル名を指定して実行] をクリックし、入力ボックスに「mmc」と入力して [OK] をクリックします。 次に、 **Console1**  ウィンドウに移動**ファイル追加と削除**スナップインの追加 をクリックし、選択**証明書**から、**利用できるスタンドアロンスナップイン** ボックスの一覧です。 最後に、選択**コンピューター アカウント**を管理し、をクリックして**OK**です。 **証明書**ノード スナップイン コンソールに表示されます。  
  
 信頼を確立するために必要な証明書は、あらかじめ用意されている必要があります。 作成し、次の手順の前に新しい証明書をインストールする方法については、次を参照してください。[する方法: を作成し、開発時に WCF の一時的なクライアント証明書をインストール](http://go.microsoft.com/fwlink/?LinkId=158925)です。  
  
1.  コンピューター A で、MMC 証明書スナップインを使用して、既存の証明書 (certA) を LocalMachine\MY (Personal Node) ストアと LocalMachine\ROOT (信頼されたルート証明機関のノード) ストアにインポートします。 特定のノードに証明書をインポートするノードを右クリックし **すべてのタスク/インポート**です。  
  
2.  コンピューター B で、MMC 証明書スナップインを使用して、秘密キーを持つ証明書 certB を作成するか取得し、LocalMachine\MY (Personal Node) ストアと LocalMachine\ROOT (信頼されたルート証明機関のノード) ストアにインポートします。  
  
3.  certA の秘密キーをファイルにエクスポートします (エクスポートしていない場合)。  
  
4.  certB の秘密キーをファイルにエクスポートします (エクスポートしていない場合)。  
  
### <a name="establishing-mutual-trust-between-machines"></a>コンピューター間での相互の信頼関係の確立  
  
1.  コンピューター A で、certB のファイルを LocalMachine\MY ストアと LocalMachine\ROOT ストアにインポートします。 これによって、コンピューター A が certB を信頼して通信することを宣言します。  
  
2.  コンピューター B で、certA のファイルを LocalMachine\MY ストアと LocalMachine\ROOT ストアにインポートします。 これによって、コンピューター B が certA を信頼して通信することを示します。  
  
 この手順が完了すると、2 台のコンピューター間に信頼が確立されるので、WS-AT を使用して相互に通信するように構成できます。  
  
### <a name="configuring-msdtc-to-use-certificates"></a>MSDTC での証明書の使用の構成  
 WS-AT プロトコル サービスは、クライアントとサーバーの両方として機能するので、このサービスは、受信接続のリッスンと送信接続の開始を実行する必要があります。 このため、外部の通信相手と通信するときに使用する証明書と、受信接続を受け入れるときに承認する証明書を MSDTC に設定する必要があります。  
  
 これを構成するには、MMC WS-AT スナップインを使用します。 このツールの詳細については、次を参照してください。、 [Ws-atomictransaction 構成 MMC スナップインで](../../../../docs/framework/wcf/ws-atomictransaction-configuration-mmc-snap-in.md)トピックです。 次の手順では、MSDTC を実行している 2 台のコンピューター間に信頼を確立する方法を説明します。  
  
1.  コンピューター A の設定を構成します。 「エンドポイントの証明書」certA を選択します。 "承認された証明書"で、certB を選択します。  
  
2.  コンピューター B の設定を構成します。 「エンドポイントの証明書」certB を選択します。 "承認された証明書"で、certA を選択します。  
  
> [!NOTE]
>  一方のコンピューターからもう一方のコンピューターにメッセージを送信する場合、送信側は、受信側の証明書のサブジェクト名と受信側のコンピューターの名前が一致することを確認します。 これらが一致しないと、証明書の確認が失敗し、2 台のコンピューターは通信できなくなります。  
>   
>  ドメインに参加しているコンピューターの名前は完全修飾ドメイン名です。 既定では、ワークグループ上のコンピューターの名前は、コンピューターの NetBIOS 名です。 ただし、2 台のコンピューター間で使用されている接続用のドメイン ネーム システム (DNS) サフィックスが存在する場合は、名前に DNS サフィックス含めることもできます。  
>   
>  ワークグループ コンピューターがドメインに参加するときなどにコンピューターの名前を変更した場合は、証明書を再発行するか、DNS サフィックスを手動で構成する必要があります。  
  
## <a name="security"></a>セキュリティ  
 一部の MSDTC と WS-AT 関連の設定はそれぞれ、レジストリ HKLM\Software\Microsoft\MSDTC と HKLM\Software\Microsoft\WSAT に格納されるので、必ずこのレジストリ キーをセキュリティで保護し、管理者だけがそのキーに書き込めるようにします。 ツールでは、レジストリ エディターをセキュリティで保護しを選択するキーを右クリックして**権限**適切なアクセス制御を設定します。 重要なキーを特権の低いユーザーに対して読み取り専用にしておくことが、システムのセキュリティと整合性を確保するために重要です。  
  
 MSDTC を展開する場合、管理者は、すべての MSDTC データの交換がセキュリティで保護されるようにする必要があります。 ワークグループの展開では、トランザクションのインフラストラクチャを悪質なユーザーから隔離してください。クラスターの展開では、クラスター レジストリをセキュリティで保護してください。  
  
## <a name="tracing"></a>トレース  
 WS-AT プロトコル サービスがサポートする統合、トランザクション特定トレースを有効になっているおよび管理できるを使用すると、 [Ws-atomictransaction 構成 MMC スナップインで](../../../../docs/framework/wcf/ws-atomictransaction-configuration-mmc-snap-in.md)ツールです。  トレースには、特定のトランザクションに参加した時刻、トランザクションが終了状態に到達した時刻、各トランザクション参加で受け取った結果などを示すデータを含めることができます。 使用してすべてのトレースを表示することができます、[サービス トレース ビューアー ツール (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md)ツールです。  
  
 WS-AT プロトコル サービスは、ETW トレース セッションを通じて統合 ServiceModel トレースもサポートします。 これにより、既存のトランザクション トレースに加えて、より詳細な通信固有のトレースが得られます。  これらの追加トレースを有効にするには、次の手順を実行します。  
  
1.  開く、**開始/実行** メニューの 入力 ボックスに「regedit」を入力し、、選択**OK**です。  
  
2.  **レジストリ エディター**Hkey_Local_Machine\SOFTWARE\Microsoft\WSAT\3.0\、左側のウィンドウで次のフォルダーに移動  
  
3.  右クリックして、`ServiceModelDiagnosticTracing`値の右側のウィンドウで、選択**変更**です。  
  
4.  **値のデータ**入力ボックスに、有効にするトレース レベルを指定する有効な値は次のいずれかを入力します。  
  
-   0 : オフ  
  
-   1 : クリティカル  
  
-   3 : エラー ( 既定値)  
  
-   7 : 警告  
  
-   15 : 情報  
  
-   31 : 詳細  
  
## <a name="see-also"></a>関連項目  
 [WS-AtomicTransaction 構成ユーティリティ (wsatConfig.exe)](../../../../docs/framework/wcf/ws-atomictransaction-configuration-utility-wsatconfig-exe.md)  
 [WS-AtomicTransaction 構成 MMC スナップイン](../../../../docs/framework/wcf/ws-atomictransaction-configuration-mmc-snap-in.md)
