---
title: コンテンツ ベースの相関関係
ms.date: 03/30/2017
ms.assetid: 8638b5d6-1d59-456d-8acd-179a5b39b260
ms.openlocfilehash: c0367f480701468dcd5024ea3439bdcd38acc78f
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2018
ms.locfileid: "43865772"
---
# <a name="content-based-correlation"></a>コンテンツ ベースの相関関係
このサンプルでは、メッセージング アクティビティ (<xref:System.ServiceModel.Activities.Send>、<xref:System.ServiceModel.Activities.Receive>、<xref:System.ServiceModel.Activities.SendReply>、および <xref:System.ServiceModel.Activities.ReceiveReply>) を 1 つまたは複数のコンテンツ ベースの相関関係で使用する方法を示します。 このシナリオでは、最初に発注書 ID に基づいて 1 つの相関関係を初期化し、後から顧客 ID に基づいて別の相関関係を作成します。 ここでは、<xref:System.ServiceModel.Activities.Receive> アクティビティで、既存の相関関係を追跡し、なおかつ同じ受信メッセージに基づいて新しい相関関係を初期化する方法を示します。  
  
## <a name="demonstrates"></a>使用例  
 メッセージング アクティビティとコンテンツ ベースの相関関係  
  
## <a name="discussion"></a>説明  
 このサンプルでは、複数のコンテンツ ベースの相関関係を使用する方法を示します。  このシナリオでは、最初に発注書 ID に基づいて 1 つの相関関係を初期化し、後から顧客 ID に基づいて別の相関関係を作成します。  相関関係は、<xref:System.ServiceModel.Activities.Receive> アクティビティを使用してカスケード化されます。このアクティビティは、既存の相関関係 (PurchaseOrderId) を追跡し、なおかつ同じ受信メッセージに基づいて新しい相関関係 (CustomerId) も初期化します。  これを実現するために、<xref:System.ServiceModel.Activities.Receive> アクティビティで <xref:System.ServiceModel.Activities.Receive.CorrelatesOn%2A> プロパティ、<xref:System.ServiceModel.Activities.Receive.CorrelatesWith%2A> プロパティ、および <xref:System.ServiceModel.Activities.Receive.CorrelationInitializers%2A> プロパティを使用します。  
  
## <a name="to-use-this-sample"></a>このサンプルを使用するには  
  
1.  開いている[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]を右クリックし、管理者特権でのアクセス許可を持つ、[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]アイコンを**管理者として実行**します。  
  
2.  [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] を使用して、CascadingCorrelation.sln ソリューション ファイルを開きます。  
  
3.  ソリューションをビルドするには、Ctrl キーと Shift キーを押しながら B キーを押します。  
  
4.  サーバーを実行するには、F5 キーを押します。  
  
5.  サービスの準備ができ、メッセージのリッスンを開始したら、ソリューション エクスプローラーで、Client プロジェクトを右クリックして実行します。  
  
> [!IMPORTANT]
>  サンプルは、既にコンピューターにインストールされている場合があります。 続行する前に、次の (既定の) ディレクトリを確認してください。  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  このディレクトリが存在しない場合に移動[Windows Communication Foundation (WCF) と .NET Framework 4 向けの Windows Workflow Foundation (WF) サンプル](https://go.microsoft.com/fwlink/?LinkId=150780)すべて Windows Communication Foundation (WCF) をダウンロードして[!INCLUDE[wf1](../../../../includes/wf1-md.md)]サンプル。 このサンプルは、次のディレクトリに格納されます。  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\ContentBasedCorrelation`