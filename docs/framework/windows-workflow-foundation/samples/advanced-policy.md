---
title: 高度なポリシー
ms.date: 03/30/2017
ms.assetid: 75a22c88-5e54-4ae8-84cb-fbb22a612f0a
ms.openlocfilehash: becdc28affd877239474d6f0f007a480297bccb8
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "44083791"
---
# <a name="advanced-policy"></a>高度なポリシー
このサンプルは、単純なポリシーのサンプルを拡張するものです。 単純なポリシーのサンプルに含まれる個人向け割引ルールとビジネス割引ルールの他に、新しいルールがいくつか追加されています。  
  
 高額な注文に対する割引額を大きく設定する、高額ルールが追加されています。 このルールの優先順位の値は前の 2 つのルールより小さいので、割引フィールドを上書きし、個人向けおよびビジネス向けの割引ルールより優先されます。  
  
 割引レベルに基づいて合計額を計算する、合計の計算ルールも追加されています。 ワークフロー アクティビティに定義されたメソッドの参照方法と、他のアクションの使用方法を示します。 また、このルールは、割引フィールドが変更されるたびに評価されるため、チェーン動作についても示します。 さらに、メソッドに対する属性の適用についても、CalculateTotal メソッドに RuleWriteAttribute 属性を適用する例で示します。 これにより、メソッドが実行されるたびに、影響を受けるルール (ErrorTotalRule) が再評価されます。  
  
 追加されている最後のルールは、エラーを検出します (ここでは、合計が 0 未満)。 エラーが検出されると、ポリシーの実行は停止されます。  
  
 最後に、`Console.Writeline` 呼び出しがアクションとして各ルールに追加されています。これは、ルール実行についての詳細を表示できるようにするためで、また、参照型の静的メソッドにアクセスできることも示します。 追跡を使用して、実行されるルールの詳細を表示することもできます。  
  
 このサンプルで使用されているルールを次に示します。  
  
 **ResidentialDiscountRule:**  
  
 IF OrderValue > 500 AND CustomerType = Residential  
  
 THEN Discount = 5%  
  
 **BusinessDiscountRule:**  
  
 IF OrderValue > 10000 AND CustomerType = Business  
  
 THEN Discount = 10%  
  
 **HighValueDiscountRule:**  
  
 IF OrderValue > 20000  
  
 THEN Discount = 15%  
  
 **TotalRule:**  
  
 IF Discount > 0  
  
 THEN CalculateTotal(OrderValue, Discount)  
  
 ELSE Total = OrderValue  
  
 **ErrorTotalRule:**  
  
 IF 合計\<0  
  
 THEN Error = "Fired ErrorTotalRule"; Halt  
  
 ルールの評価と実行は、トレースと追跡で確認することもできます。  
  
### <a name="to-build-the-sample"></a>サンプルをビルドするには  
  
1.  [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] で、ソリューションを開きます。  
  
2.  Ctrl キーと Shift キーを押しながら B キーを押して、ソリューションをビルドします。  
  
3.  Ctrl キーを押しながら F5 キーを押して、ソリューションをデバッグなしで実行します。  
  
### <a name="to-run-the-sample"></a>サンプルを実行するには  
  
-   [SDK コマンド プロンプト] ウィンドウで、AdvancedPolicy\bin\debug フォルダー (Visual Basic バージョンのサンプルの場合は AdvancedPolicy\bin フォルダー) にある .exe ファイルを実行します。このフォルダーは、サンプルのメイン フォルダーの下に作成されます。  
  
> [!IMPORTANT]
>  サンプルは、既にコンピューターにインストールされている場合があります。 続行する前に、次の (既定の) ディレクトリを確認してください。  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  このディレクトリが存在しない場合に移動[Windows Communication Foundation (WCF) と .NET Framework 4 向けの Windows Workflow Foundation (WF) サンプル](https://go.microsoft.com/fwlink/?LinkId=150780)すべて Windows Communication Foundation (WCF) をダウンロードして[!INCLUDE[wf1](../../../../includes/wf1-md.md)]サンプル。 このサンプルは、次のディレクトリに格納されます。  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Rules\Policy\AdvancedPolicy`  
  
## <a name="see-also"></a>関連項目  
 <xref:System.Workflow.Activities.Rules.RuleSet>  
 <xref:System.Workflow.Activities.PolicyActivity>  
 [簡単なポリシー](../../../../docs/framework/windows-workflow-foundation/samples/simple-policy.md)
