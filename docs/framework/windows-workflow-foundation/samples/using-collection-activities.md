---
title: コレクション アクティビティの使用
ms.date: 03/30/2017
ms.assetid: e1977cf8-1695-4071-b946-7046fe39601e
ms.openlocfilehash: a92208583ddf1c0d5d85b5af6a250a15ac8851b9
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "43506552"
---
# <a name="using-collection-activities"></a>コレクション アクティビティの使用
このサンプルでは、<xref:System.Activities.Statements.AddToCollection%601> インターフェイスを実装するクラスでコレクション アクティビティ (<xref:System.Activities.Statements.ClearCollection%601>、<xref:System.Activities.Statements.ExistsInCollection%601>、<xref:System.Activities.Statements.RemoveFromCollection%601>、および <xref:System.Collections.ICollection>) を使用する方法と、コレクションを反復処理してコレクション内の各要素の内容を出力するカスタム アクティビティを作成する方法を示します。 `PrintCollection` という名前のカスタム アクティビティは、`Numbers` という名前のコレクションの項目メンバーをコンソールに出力します。  
  
 次の表で、ワークフローにコレクション操作を提供する 4 つのアクティビティについて説明します。  
  
|アクティビティ名|説明|  
|-------------------|-----------------|  
|<xref:System.Activities.Statements.AddToCollection%601>|項目をコレクションに追加します。|  
|<xref:System.Activities.Statements.ClearCollection%601>|コレクションの項目をすべて削除します。|  
|<xref:System.Activities.Statements.ExistsInCollection%601>|指定された項目がコレクション内に存在する場合、`true` を返します。|  
|<xref:System.Activities.Statements.RemoveFromCollection%601>|コレクションから項目を削除します。|  
  
 このサンプルは 2 つのソリューションで構成されます。1 つは CodedWorkflow ディレクトリにあり、もう 1 つは DesignerWorkflow ディレクトリにあります。 これらのソリューションでは、アクティビティを使用して同じ目的を達成するための 2 つの異なる方法を示します。  
  
|ソリューション|説明|メイン ファイル|  
|-|-|-|  
|CodedWorkflow|プログラムでコレクション アクティビティを呼び出す方法を示すサンプル クライアント アプリケーション。|**PrintCollection.cs**: コレクション内のすべての項目をコンソールに出力するヘルパー アクティビティ。<br /><br /> **Program.cs**: プログラムによって、一連のコレクション アクティビティを実行するシーケンス アクティビティをビルドします。|  
|DesignerWorkflow|ワークフロー デザイナーでコレクション アクティビティを宣言的に使用する方法を示すサンプル クライアント アプリケーション。|**CollectionWorkflow.xaml**: コレクション アクティビティを使用するデザイナーで宣言によって作成されたワークフローです。<br /><br /> **PrintCollection.cs**: コレクション内のすべての項目をコンソールに出力するヘルパー アクティビティ。<br /><br /> **Program.cs**: CollectionWorkflow.xaml に記述されたワークフローを呼び出します。|  
  
 デモでは、`Numbers` という名前のカスタム定義アクティビティを使用して、コレクション `PrintCollection` の項目メンバーをコンソールに出力します。  
  
#### <a name="to-use-this-sample"></a>このサンプルを使用するには  
  
1.  [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] を使用して、Collection.sln ソリューション ファイルを開きます。  
  
2.  ソリューションをビルドするには、Ctrl キーと Shift キーを押しながら B キーを押します。  
  
3.  ソリューションを実行するには、Ctrl キーを押しながら F5 キーを押します。  
  
> [!IMPORTANT]
>  サンプルは、既にコンピューターにインストールされている場合があります。 続行する前に、次の (既定の) ディレクトリを確認してください。  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  このディレクトリが存在しない場合に移動[Windows Communication Foundation (WCF) と .NET Framework 4 向けの Windows Workflow Foundation (WF) サンプル](https://go.microsoft.com/fwlink/?LinkId=150780)すべて Windows Communication Foundation (WCF) をダウンロードして[!INCLUDE[wf1](../../../../includes/wf1-md.md)]サンプル。 このサンプルは、次のディレクトリに格納されます。  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\Collection`