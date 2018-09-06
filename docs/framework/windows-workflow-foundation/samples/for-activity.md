---
title: For アクティビティ
ms.date: 03/30/2017
ms.assetid: 2ea751b4-36f0-48aa-a115-70a2ab89f6d8
ms.openlocfilehash: 7a7023abb9057ab4b25552fbf9a81cd2ae2b4e88
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2018
ms.locfileid: "43881523"
---
# <a name="for-activity"></a>For アクティビティ
For サンプルでは、<xref:System.Activities.NativeActivity> から継承するカスタム アクティビティを構築し、そのアクティビティをワークフローで使用して実際の例を実行する方法を示します。 このサンプルに含まれるカスタム アクティビティは、C# の `for` ステートメントと同じように機能します。 T  
  
 `For` カスタム アクティビティには、`InitAction`、`IterationAction`、`Condition`、および `Body` というプロパティがあります。これらのプロパティは、標準的な C# の `For` ステートメントの初期化ステートメント、反復ステートメント、継続条件、および本体ステートメントにそれぞれ対応します。  
  
 次の表で、サンプルの主要なファイルについて説明します。  
  
|ファイル|説明|  
|----------|-----------------|  
|For.cs|`For` カスタム アクティビティのクラス定義。<xref:System.Activities.NativeActivity> クラスを拡張して C# の `For` ステートメントの機能を提供します。|  
|Program.cs|カスタム `For` アクティビティを使用してコレクションに対して基本的な反復処理を実行するクライアント アプリケーション。|  
  
> [!NOTE]
>  `For` カスタム アクティビティを使用する場合は、必ず `Condition` プロパティを設定してください。そうしないと、無限ループが発生する可能性があります。  
  
## <a name="demonstrates"></a>使用例  
 <xref:System.Activities.NativeActivity> から継承するカスタム アクティビティを作成します。  
  
## <a name="discussion"></a>説明  
 次の表で、このサンプルに含まれるアクティビティのプロパティについて説明します。  
  
 InitAction  
 初期化ステートメント  
  
 IterationAction  
 反復ステートメント  
  
 状態  
 条件ステートメント  
  
 Body  
 本体ステートメント  
  
 このアクティビティは、<xref:System.Activities.NativeActivity> から継承して、ランタイム機能 (`ScheduleActivity` のいずれかの <xref:System.Activities.NativeActivityContext> メソッドを使用した追加アクティビティの実行スケジュールの設定など) へのアクセスを取得します。  
  
#### <a name="to-use-this-sample"></a>このサンプルを使用するには  
  
1.  [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] を使用して、For.sln ソリューション ファイルを開きます。  
  
2.  Ctrl キーと Shift キーを押しながら B キーを押して、ソリューションをビルドします。  
  
3.  F5 キーを押して、ソリューションを実行します。  
  
> [!IMPORTANT]
>  サンプルは、既にコンピューターにインストールされている場合があります。 続行する前に、次の (既定の) ディレクトリを確認してください。  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  このディレクトリが存在しない場合に移動[Windows Communication Foundation (WCF) と .NET Framework 4 向けの Windows Workflow Foundation (WF) サンプル](https://go.microsoft.com/fwlink/?LinkId=150780)すべて Windows Communication Foundation (WCF) をダウンロードして[!INCLUDE[wf1](../../../../includes/wf1-md.md)]サンプル。 このサンプルは、次のディレクトリに格納されます。  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\For`