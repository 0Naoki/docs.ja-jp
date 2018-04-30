---
title: サービスとトランザクション
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- service contracts [WCF], designing services and transactions
ms.assetid: 864813ff-2709-4376-912d-f5c8d318c460
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: c39c9f6e56dc4c2bf2feb5340d7d1bb1b96f5ab6
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/30/2018
---
# <a name="services-and-transactions"></a>サービスとトランザクション
[!INCLUDE[indigo1](../../../includes/indigo1-md.md)] アプリケーションでは、クライアントからトランザクションを開始し、そのトランザクションをサービス操作内で調整できます。 クライアントはトランザクションを開始し、複数のサービス操作を呼び出す可能性があります。サービス操作が、1 つの単位としてコミットまたはロールバックされます。  
  
 サービス コントラクトでトランザクション動作を有効にするには、<xref:System.ServiceModel.ServiceBehaviorAttribute> を指定し、クライアント トランザクションを必要とするサービス操作について <xref:System.ServiceModel.ServiceBehaviorAttribute.TransactionIsolationLevel%2A> プロパティと <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> プロパティを設定します。 <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionAutoComplete%2A> パラメーターは、未処理の例外がスローされなかった場合に、メソッドが実行されているトランザクションが自動的に完了されるかどうかを指定します。 これらの属性の詳細については、次を参照してください。 [ServiceModel トランザクションの属性](../../../docs/framework/wcf/feature-details/servicemodel-transaction-attributes.md)です。  
  
 データベース更新の記録など、サービス操作で実行され、リソース マネージャーで管理される作業は、クライアント トランザクションの一部です。  
  
 <xref:System.ServiceModel.ServiceBehaviorAttribute> 属性と <xref:System.ServiceModel.OperationBehaviorAttribute> 属性を使用して、サービス側のトランザクション動作を制御する方法を次の例に示します。  
  
```  
[ServiceBehavior(TransactionIsolationLevel = System.Transactions.IsolationLevel.Serializable)]  
public class CalculatorService: ICalculatorLog  
{  
    [OperationBehavior(TransactionScopeRequired = true,  
                           TransactionAutoComplete = true)]  
    public double Add(double n1, double n2)  
    {  
        recordToLog(String.Format("Added {0} to {1}", n1, n2));  
        return n1 + n2;  
    }  
  
    [OperationBehavior(TransactionScopeRequired = true,   
                               TransactionAutoComplete = true)]  
    public double Subtract(double n1, double n2)  
    {  
        recordToLog(String.Format("Subtracted {0} from {1}", n1, n2));  
        return n1 - n2;  
    }  
  
    [OperationBehavior(TransactionScopeRequired = true,   
                                       TransactionAutoComplete = true)]  
    public double Multiply(double n1, double n2)  
    {  
        recordToLog(String.Format("Multiplied {0} by {1}", n1, n2));  
        return n1 * n2;  
    }  
  
    [OperationBehavior(TransactionScopeRequired = true,   
                                       TransactionAutoComplete = true)]  
    public double Divide(double n1, double n2)  
    {  
        recordToLog(String.Format("Divided {0} by {1}", n1, n2));  
        return n1 / n2;  
    }  
  
}  
```  
  
 トランザクションを有効にすることができ、トランザクションのクライアントを構成することによってフローしサービス バインド、Ws-atomictransaction プロトコルを使用して設定、 [ \<transactionFlow >](../../../docs/framework/configure-apps/file-schema/wcf/transactionflow.md)要素を`true`ように、次のサンプル構成します。  
  
```xml  
<client>  
    <endpoint address="net.tcp://localhost/ServiceModelSamples/service"   
          binding="netTcpBinding"   
          bindingConfiguration="netTcpBindingWSAT"   
          contract="Microsoft.ServiceModel.Samples.ICalculatorLog" />  
</client>  
  
<bindings>  
    <netTcpBinding>  
        <binding name="netTcpBindingWSAT"  
                transactionFlow="true"  
                transactionProtocol="WSAtomicTransactionOctober2004" />  
     </netTcpBinding>  
</bindings>  
```  
  
 クライアントは、<xref:System.Transactions.TransactionScope> を作成し、トランザクションのスコープ内でサービス操作を呼び出すことにより、トランザクションを開始できます。  
  
```  
using (TransactionScope ts = new TransactionScope(TransactionScopeOption.RequiresNew))  
{  
    //Do work here  
    ts.Complete();  
}  
```  
  
## <a name="see-also"></a>関連項目  
 [System.ServiceModel でのトランザクション サポート](../../../docs/framework/wcf/feature-details/transactional-support-in-system-servicemodel.md)  
 [トランザクション モデル](../../../docs/framework/wcf/feature-details/transaction-models.md)  
 [WS トランザクション フロー](../../../docs/framework/wcf/samples/ws-transaction-flow.md)
