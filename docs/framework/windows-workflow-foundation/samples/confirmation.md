---
title: 確認
ms.date: 03/30/2017
ms.assetid: 8637aeaf-ac9e-49b8-93f4-da15dee45277
ms.openlocfilehash: caa712aa52da01ce44335a361fd6c9f5215316bf
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "43660997"
---
# <a name="confirmation"></a>確認
このサンプルでは、<xref:System.Activities.Statements.CompensableActivity> および確認を使用する 4 つの一般的なシナリオを示します。 確認を示すために、4 つのワークフローを実行します。 このサンプルには、宣言型バージョンと命令型バージョンが用意されています。  
  
## <a name="confirm-a-compensable-activity"></a>補正可能なアクティビティの確認  
 最初のワークフローでは、補正可能なアクティビティを確認する方法を示します。このワークフローは、2 つの <xref:System.Activities.Statements.CompensableActivity> インスタンスのシーケンスで構成されています。 2 つ目の <xref:System.Activities.Statements.CompensableActivity> の完了後、確認アクティビティによって 1 つ目のアクティビティが確認されます。 ワークフローが正常に完了すると、確認または補正されていないすべての <xref:System.Activities.Statements.CompensableActivity> インスタンスが既定の順序で自動的に確認されます。 確認アクティビティを使用しなかった場合、2 つ目の <xref:System.Activities.Statements.CompensableActivity> が最初に確認されていたことになります。  
  
## <a name="explicit-compensation"></a>明示的な補正  
 2 番目のシナリオでは、<xref:System.Activities.Statements.CompensableActivity> が明示的に補正される場合の既定の確認に対する影響を示します。 このワークフローは、2 つの <xref:System.Activities.Statements.CompensableActivity> アクティビティのシーケンスで構成されています。2 つ目のアクティビティが完了すると、1 つ目のアクティビティが明示的に補正されます。 したがって、ワークフローが完了すると、2 つ目の <xref:System.Activities.Statements.CompensableActivity> のみが確認されます。  
  
## <a name="controlling-the-order-of-confirmation-for-nested-compensableactivity-activities"></a>入れ子になった CompensableActivity アクティビティの確認順序の制御  
 3 番目のシナリオでは、入れ子になった <xref:System.Activities.Statements.CompensableActivity> の確認順序を制御する方法を示します。 このシナリオは、ワークフローのルートとしての <xref:System.Activities.Statements.CompensableActivity> で構成されています。 ルート <xref:System.Activities.Statements.CompensableActivity> の本体は 3 つの <xref:System.Activities.Statements.CompensableActivity> のシーケンスです。 ルート <xref:System.Activities.Statements.CompensableActivity.ConfirmationHandler%2A> の <xref:System.Activities.Statements.CompensableActivity> は、1 つ目および 2 つ目の入れ子になった <xref:System.Activities.Statements.CompensableActivity> をこの順序で確認するように指定するシーケンスです。 ワークフローが完了すると、ルート <xref:System.Activities.Statements.CompensableActivity> が確認され、その後、1 つ目、2 つ目、および 3 つ目の入れ子になった <xref:System.Activities.Statements.CompensableActivity> がこの順序で確認されます。 したがって、既定の確認順序は基本的に逆になります。 3 つ目の <xref:System.Activities.Statements.CompensableActivity> はルート <xref:System.Activities.Statements.CompensableActivity> の一部として <xref:System.Activities.Statements.CompensableActivity.ConfirmationHandler%2A> によって明示的に確認されなかったため、既定の順序に従って確認されます。 ただし、このアクティビティが唯一未確認の <xref:System.Activities.Statements.CompensableActivity> であるので、このアクティビティが確認されるだけです。  
  
## <a name="scoping-of-variables"></a>変数のスコープ  
 4 番目のシナリオでは、アクティビティが完了した場合またはワークフローが完了した場合でも、<xref:System.Activities.Statements.CompensableActivity>、<xref:System.Activities.Statements.CompensableActivity.CompensationHandler%2A>、または <xref:System.Activities.Statements.CompensableActivity.ConfirmationHandler%2A> の各ハンドラーが実行されるときに、<xref:System.Activities.Statements.CompensableActivity.CancellationHandler%2A> またはその親のいずれかに対して定義された変数が有効期間中にスコープ外にならないようにする方法を示します。 このワークフローは、2 つの <xref:System.Activities.Statements.CompensableActivity> のシーケンスで構成されています。 1 つ目のアクティビティの本体では、変数 `mySum` は、5 と 10 の合計、および印刷される結果に設定されます。 2 つ目の <xref:System.Activities.Statements.CompensableActivity> の本体では、合計は、既存の合計と 7 の合計、および印刷される結果に設定されます。 1 つ目の <xref:System.Activities.Statements.CompensableActivity> に対しては、カスタムの確認ハンドラーが定義されています。このアクティビティは、合計を印刷し、7 を差し引いて、合計を再度印刷します。 印刷された合計を調べることで、両方の <xref:System.Activities.Statements.CompensableActivity> の本体だけでなく <xref:System.Activities.Statements.CompensableActivity.ConfirmationHandler%2A> についても変数がスコープ内にあることがわかります。  
  
#### <a name="to-run-the-sample"></a>サンプルを実行するには  
  
1.  [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] でソリューションを読み込みます。  
  
2.  ConfirmationSample.exe アプリケーションを実行します。  
  
3.  次の出力を確認します。  
  
 **明示的な確認: workflowCompensableActivity1 の開始: BodyCompensableActivity2: BodyCompensableActivity1: workflowCompensableActivity2 の確認 HandlerEnd: 確認 HandlerExplicit の補正: 開始workflowCompensableActivity1: BodyCompensableActivity2: BodyCompensableActivity1: workflowCompensableActivity2 の補正 HandlerEnd: 確認 HandlerCustom 確認ハンドラー: 開始 workflowCompensableActivity1 の。BodyCompensableActivity2: BodyCompensableActivity3: workflowCompensableActivity1 の BodyEnd: 確認 HandlerCompensableActivity2: 確認 HandlerCompensableActivity3: 確認ハンドラーで確認 HandlerVariable アクセス。WorkflowCompensableActivity1 の開始: BodyCompensableActivity1: 合計: 15CompensableActivity2: BodyCompensableActivity2: 7、sumCompensableActivity2 を追加する: 合計: workflowCompensableActivity2 の 22End: 確認HandlerCompensableActivity1: 確認 HandlerCompensableActivity2: 合計: 22CompensableActivity2: 合計をここでは 12 を引いた後: を終了する 10Press」と入力します。**  
  
> [!IMPORTANT]
>  サンプルは、既にコンピューターにインストールされている場合があります。 続行する前に、次の (既定の) ディレクトリを確認してください。  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  このディレクトリが存在しない場合に移動[Windows Communication Foundation (WCF) と .NET Framework 4 向けの Windows Workflow Foundation (WF) サンプル](https://go.microsoft.com/fwlink/?LinkId=150780)すべて Windows Communication Foundation (WCF) をダウンロードして[!INCLUDE[wf1](../../../../includes/wf1-md.md)]サンプル。 このサンプルは、次のディレクトリに格納されます。  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Compensation\Confirmation`