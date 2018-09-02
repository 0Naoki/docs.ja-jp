---
title: トランザクションのロールバック
ms.date: 03/30/2017
ms.assetid: 7f377147-7529-4689-a588-608cee87fdf8
ms.openlocfilehash: 8134623248b072ec5a095ab9b10840e94a09243c
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/02/2018
ms.locfileid: "43464124"
---
# <a name="transaction-rollback"></a>トランザクションのロールバック
このサンプルでは、アンビエント <xref:System.Activities.NativeActivity> にアクセスしてアンビエント トランザクションを取得し、そのトランザクションを明示的にロールバックするカスタム <xref:System.Activities.RuntimeTransactionHandle> を作成する方法を示します。  
  
## <a name="sample-details"></a>サンプルの詳細  
 ワークフローでは、最も外側の <xref:System.Activities.Statements.TransactionScope> または <xref:System.ServiceModel.Activities.TransactedReceiveScope> が完了すると、トランザクションは自動的に完了します。  未処理の例外がスコープの境界を越えて伝達されると、トランザクションは暗黙的にロールバックします。 ただし、例外をスローせずにトランザクションを明示的にロールバックすることが有効な場合もあります。 この場合、このサンプルのアクティビティのようなカスタム ロールバック アクティビティを使用して、アンビエント トランザクションを明示的に中止し、必要に応じて例外の理由を提供することができます。  
  
 `RollbackActivity` は、アンビエント <xref:System.Activities.NativeActivity> を取得するために実行プロパティにアクセスする必要があるので、<xref:System.Activities.RuntimeTransactionHandle> になります。 `Execute` メソッドでは、<xref:System.Activities.RuntimeTransactionHandle> を取得し、アンビエント ランタイム トランザクションなしでアクティビティが使用されたことを示す `null` であるかどうかを確認します。 次にトランザクションを取得し、`null` が存在するかどうかを再度確認します。 ランタイム トランザクションを初期化せずにアンビエント <xref:System.Activities.RuntimeTransactionHandle> を取得することができます。 最後に、<xref:System.Transactions.Transaction.Rollback%2A> を呼び出し、ユーザー指定の例外、またはアクティビティによってトランザクションがロールバックされたことを示す汎用的な例外を指定して、トランザクションを中止します。  
  
 このサンプルのワークフローは、<xref:System.Activities.Statements.TransactionScope> の実行の前後にトランザクションの状態を印刷する本体を持つ `RollbackActivity` で構成されます。 トランザクションがロールバックされた場合でも、<xref:System.Activities.Statements.TransactionScope> は完了まで実行され、本体が完了するまでワークフローは中止されないことに注意してください。 ワークフローが中止されるのは、<xref:System.Activities.Statements.TransactionScope.AbortInstanceOnTransactionFailure%2A> プロパティが既定で `true` に設定されるためです。  
  
#### <a name="to-use-this-sample"></a>このサンプルを使用するには  
  
1.  [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] に TransactionRollback.sln ソリューションを読み込みます。  
  
2.  Ctrl キーと Shift キーを押しながら B キーを押して、ソリューションをビルドします。  
  
3.  Ctrl キーを押しながら F5 キーを押してアプリケーションを実行します。  
  
> [!IMPORTANT]
>  サンプルは、既にコンピューターにインストールされている場合があります。 続行する前に、次の (既定の) ディレクトリを確認してください。  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  このディレクトリが存在しない場合に移動[Windows Communication Foundation (WCF) と .NET Framework 4 向けの Windows Workflow Foundation (WF) サンプル](https://go.microsoft.com/fwlink/?LinkId=150780)すべて Windows Communication Foundation (WCF) をダウンロードして[!INCLUDE[wf1](../../../../includes/wf1-md.md)]サンプル。 このサンプルは、次のディレクトリに格納されます。  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Transactions\TransactionRollback`  
  
## <a name="see-also"></a>関連項目  
 [トランザクション](../../../../docs/framework/windows-workflow-foundation/workflow-transactions.md)
