---
title: 探索ルーター サービス
ms.date: 03/30/2017
ms.assetid: 3d30af47-b24f-40e5-833a-24d77125c9e6
ms.openlocfilehash: 9434c26fb12b73ea4f1c185658b03cb95a3a2310
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2019
ms.locfileid: "70039829"
---
# <a name="discovery-router-service"></a>探索ルーター サービス
このサンプルでは、探索メッセージを別のエンドポイントに転送する方法を示します。  
  
## <a name="demonstrates"></a>使用例  
 探索ルーティング  
  
## <a name="discussion"></a>説明  
 探索ルーティングは、プロキシがサービスを認識しないが、別のプロキシのことは認識する場合に、クライアントがプロキシを使用してそのようなサービスを検索するシナリオで役に立ちます。 このプロキシは、探索パケットをこのクライアントから 2 番目のプロキシに転送できます。 2 番目のプロキシはサービスを検索し、応答を元のクライアントに返します。  
  
 このサンプルでは、クライアントはメッセージを探索ルーティング コンポーネントに送信します。 このメッセージは、探索ルーター上の特定のエンドポイントに送信されます。 その後、このルーターはメッセージを UDP マルチキャスト エンドポイントに転送します。 プローブ メッセージはマルチキャスト エンドポイントに送信され、UDP マルチキャスト アドレスをリッスンするサービスは、その探索ルーターに応答します。 探索ルーターは応答を収集し、クライアントにその応答を返します。  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>サンプルをセットアップ、ビルド、および実行するには  
  
1. このサンプルをビルドします。  
  
2. DiscoveryRouter 実行可能ファイルを実行します。  
  
3. ビルド ディレクトリからサービス実行可能ファイルを実行します。  
  
4. クライアント実行可能ファイルを実行します。 クライアントでサービスが検索されることに注意してください。  
  
> [!IMPORTANT]
> サンプルは、既にコンピューターにインストールされている場合があります。 続行する前に、次の (既定の) ディレクトリを確認してください。  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> このディレクトリが存在しない場合は、 [Windows Communication Foundation (wcf) および Windows Workflow Foundation (WF) のサンプルの .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780)にアクセスして、すべての[!INCLUDE[wf1](../../../../includes/wf1-md.md)] Windows Communication Foundation (wcf) とサンプルをダウンロードしてください。 このサンプルは、次のディレクトリに格納されます。  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Discovery\DiscoveryRouter`
