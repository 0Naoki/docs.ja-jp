---
title: カスタム補正のサンプル
ms.date: 03/30/2017
ms.assetid: 385920da-9284-44bf-9fe9-0d87c7478ec5
ms.openlocfilehash: ac141a48f87f5b14f6b528f7b3ceb7fdddeaf2d2
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "43503720"
---
# <a name="custom-compensation-sample"></a>カスタム補正のサンプル
このサンプルでは、<xref:System.Activities.Statements.CompensableActivity> とその補正ハンドラーを使用してカスタム補正ロジックを定義する方法を示します。 このサンプルでは、トラック レンタル会社のシナリオをモデル化しています。  
  
## <a name="sample-details"></a>サンプルの詳細  
 シミュレートする手順は次のとおりです。  
  
1.  ユーザーが日付を指定してトラック レンタルの見積もりを要求します。  
  
2.  トラック会社 3 社に連絡して、3 つの見積もりを入手します。  
  
3.  ユーザーがトラックの見積もりを 1 つ選択し、クレジット カードでの注文に進みます。  
  
4.  アプリケーションで、他の 2 つのトラックの見積もりが取り消されます。  
  
5.  利用予定日の 10 日前を過ぎてからの取り消しの場合にプレミアム アカウント以外には払い戻しされないサービス手数料が、アプリケーションで請求されます。  
  
6.  アプリケーションで、トラックのレンタル料金が請求されます。  
  
7.  アプリケーションは、利用予定日になるか顧客が予約を取り消すか、どちらか早い方まで待機します。  
  
8.  顧客が予約を取り消した場合、次のロジックに従って <xref:System.Activities.Statements.CompensableActivity.CompensationHandler%2A> カスタム補正ロジックが実行されます。  
  
    1.  顧客がプレミアム アカウントでなく、かつ利用予定日の 10 日前を過ぎている場合、サービス手数料が請求されます。それ以外の場合は、サービス手数料が返金されます。  
  
    2.  残りの補正可能なアクティビティ (トラックの注文 + トラックの注文料金) については、既定の補正ロジックに従って、逆の順序で補正が実行されます。  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>サンプルをセットアップ、ビルド、および実行するには  
  
1.  [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] を使用して、CustomCompensation.sln ソリューション ファイルを開きます。 このソリューションは \WF\Basic\Compensation\CustomCompensation ディレクトリにあります。  
  
2.  Ctrl キーと Shift キーを押しながら B キーを押して、ソリューションをビルドします。  
  
3.  Ctrl キーを押しながら F5 キーを押してアプリケーションを実行します。  
  
> [!IMPORTANT]
>  サンプルは、既にコンピューターにインストールされている場合があります。 続行する前に、次の (既定の) ディレクトリを確認してください。  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  このディレクトリが存在しない場合に移動[Windows Communication Foundation (WCF) と .NET Framework 4 向けの Windows Workflow Foundation (WF) サンプル](https://go.microsoft.com/fwlink/?LinkId=150780)すべて Windows Communication Foundation (WCF) をダウンロードして[!INCLUDE[wf1](../../../../includes/wf1-md.md)]サンプル。 このサンプルは、次のディレクトリに格納されます。  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Compensation\CustomCompensation`