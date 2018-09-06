---
title: 形式の自動選択
ms.date: 03/30/2017
ms.assetid: dab51e56-8517-4a6a-bb54-b55b15ab37bb
ms.openlocfilehash: 4fd695195f5c7c13bc088248a6b3c12388328d37
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2018
ms.locfileid: "43784759"
---
# <a name="automatic-format-selection"></a>形式の自動選択
このサンプルでは、操作コードで形式を明示的に設定する方法と、モデルをプログラミングする Windows Communication Foundation (WCF) REST を使用した (XML または JSON) 形式の自動選択を有効にする方法を示します。  
  
## <a name="sample-details"></a>サンプルの詳細  
 このサンプルは、サービスと、サービスに要求を発行するクライアント コードで構成されます。 サービスは、単一の HTTP `GET` 操作 (`EchoWithGet`) と単一の HTTP `POST` 操作 (`EchoWithPost`) をサポートします。 どちらの操作でも文字列を要求し、応答で文字列を返します。 `GET` 操作では、文字列は URI クエリ文字列パラメーターで示されます。 `POST` 操作では、文字列は XML でシリアル化された要求の本文で示されます。 サービスは、[!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)] の新機能である形式の自動選択と形式の強制選択を利用して、XML または JSON 形式のいずれかで応答を返すことができます。  
  
 このサンプルでは、App.config ファイルを使用して形式の自動選択を有効にしています。 既定の Web HTTP エンドポイントでは、`automaticFormatSelectionEnabled` 属性に `true` の値が指定されています。 形式の自動選択が有効になっている、WCF インフラストラクチャは、最も適切な応答形式 (XML または JSON)、要求の HTTP Accept または Content-type ヘッダーの指定を選択します。 開発者は、`automaticFormatSelectionEnabled` 属性を `true` に設定する以外、この新しい機能を使用するためにコードまたは構成を追加する必要はありません。 Program.cs で、クライアント コードで要求が送信されるには、両方の`GET`と`POST`"application/xml"または"application/json"のいずれかとして指定された HTTP Accept ヘッダーでサービスとサービスの操作は、その応答を返しますそれぞれの形式。  
  
 また、`GET` 操作では、形式の強制選択が使用されます。 `GET` 操作では、オプションの `format` クエリ文字列パラメーターがあるかどうかをチェックし、ある場合は、<xref:System.ServiceModel.Web.WebOperationContext.OutgoingResponse%2A> プロパティで応答形式を設定します。 この方法で応答形式を強制的に設定、WCF インフラストラクチャによって実行形式の自動選択をオーバーライドします。  
  
 このサンプルは、コンソール アプリケーション内で実行される自己ホスト型サービスとクライアントで構成されています。 コンソール アプリケーションが実行されると、クライアントはサービスに要求を発行し、応答からの適切な情報をコンソール ウィンドウに書き込みます。  
  
#### <a name="to-use-this-sample"></a>このサンプルを使用するには  
  
1.  形式の自動選択サンプルのソリューションを開きます。 サンプルを正しく実行するには、[!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] を起動するときに、管理者として実行する必要があります。 これには、右クリックし、[!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]アイコンと選択**管理者として実行**コンテキスト メニューから。  
  
2.  Ctrl キーと Shift キーを押しながら B キーを押してソリューションをビルドし、Ctrl キーを押しながら F5 キーを押してコンソール アプリケーションの AutomaticFormatSelection プロジェクトを実行します。 コンソール ウィンドウが表示されて、実行中のサービスの URI および実行中のサービスの HTML ヘルプ ページの URI が示されます。  
  
3.  サンプルが実行されると、クライアントは要求をサービスに送信し、応答をコンソール ウィンドウに書き込みます。 応答の形式は XML または JSON になります。  
  
4.  任意のキーを押して、サンプルを終了します。  
  
> [!IMPORTANT]
>  サンプルは、既にコンピューターにインストールされている場合があります。 続行する前に、次の (既定の) ディレクトリを確認してください。  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  このディレクトリが存在しない場合に移動[Windows Communication Foundation (WCF) と .NET Framework 4 向けの Windows Workflow Foundation (WF) サンプル](https://go.microsoft.com/fwlink/?LinkId=150780)すべて Windows Communication Foundation (WCF) をダウンロードして[!INCLUDE[wf1](../../../../includes/wf1-md.md)]サンプル。 このサンプルは、次のディレクトリに格納されます。  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\AutomaticFormatSelection`  
  
## <a name="see-also"></a>関連項目
