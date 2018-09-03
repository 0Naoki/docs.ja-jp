---
title: TransactedReceiveScope の使用
ms.date: 03/30/2017
ms.assetid: d455f1dc-bfc5-43d6-8ae9-bc3b3a3ea08a
ms.openlocfilehash: bc1c418f3fa116f5e1c1647af3543a38122842f5
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/03/2018
ms.locfileid: "43481472"
---
# <a name="use-of-transactedreceivescope"></a>TransactedReceiveScope の使用
このサンプルでは、クライアントからサーバーにトランザクションをフローする方法を示します。このために、<xref:System.Activities.Statements.TransactionScope> を使用してクライアント上に新しいトランザクションを作成し、<xref:System.ServiceModel.Activities.TransactedReceiveScope> を使用してフローされたトランザクションを含むメッセージを受信し、サーバー上でトランザクションの有効期間のスコープを設定します。 このサンプルは、クライアントとサーバーの役割を果たす 2 つのプロジェクトで構成されます。  
  
## <a name="client-application"></a>クライアント アプリケーション  
 クライアント アプリケーションは、分散トランザクション ID の出力、サーバーへのメッセージの送信、トランザクションのフロー、応答の受信、分散トランザクション ID の再出力、および完了処理を行うワークフローを実行します。 最初に出力される分散トランザクション ID は空の GUID です。これは、その時点ではトランザクションがまだローカルのみであるためです。  
  
## <a name="server-application"></a>サーバー アプリケーション  
 サーバー プロジェクトはクライアントに似ていますが、ワークフローが <xref:System.ServiceModel.Activities.WorkflowServiceHost> でホストされます。これは、エンドポイントでクライアントからのメッセージをリッスンする必要があるためです。 ワークフローの中心は、クライアントからフローされたトランザクションの受信、送信されたメッセージの出力、分散トランザクション ID の出力、およびクライアントへの応答の送信を行う <xref:System.ServiceModel.Activities.TransactedReceiveScope> です。 分散トランザクション ID は空でない GUID になり、トランザクションに対応するアクティビティが <xref:System.ServiceModel.Activities.TransactedReceiveScope> の本体に追加された場合、そのアクティビティはフローされたランザクションで実行されます。  
  
#### <a name="to-run-the-sample"></a>サンプルを実行するには  
  
1.  [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] で TransactedReceiveScope.sln ソリューションを開きます。  
  
2.  ソリューションをビルドするには、CTRL + SHIFT + B キーを押しますまたは選択**ソリューションのビルド**から、**ビルド**メニュー。  
  
3.  ビルドが完了すると、ソリューションを右クリックしを選択**スタートアップ プロジェクトの設定**します。 ダイアログ ボックスで、次のように選択します。**マルチ スタートアップ プロジェクト**させ、両方のプロジェクトのアクションが**開始**します。  
  
4.  F5 キーを押すか、選択**デバッグの開始**から、**デバッグ**メニュー。 または、ctrl キーを押しながら f5 キーを押してまたは選択**デバッグなしで開始**から、**デバッグ**] メニューの [デバッグなしで実行します。  
  
    > [!NOTE]
    >  クライアントを起動する前に、サーバーを起動しておく必要があります。 サービスをホストするコンソール ウィンドウの出力で、起動された時間が示されます。  
  
> [!IMPORTANT]
>  サンプルは、既にコンピューターにインストールされている場合があります。 続行する前に、次の (既定の) ディレクトリを確認してください。  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  このディレクトリが存在しない場合に移動[Windows Communication Foundation (WCF) と .NET Framework 4 向けの Windows Workflow Foundation (WF) サンプル](https://go.microsoft.com/fwlink/?LinkId=150780)すべて Windows Communication Foundation (WCF) をダウンロードして[!INCLUDE[wf1](../../../../includes/wf1-md.md)]サンプル。 このサンプルは、次のディレクトリに格納されます。  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Transactions\TransactedReceiveScope`