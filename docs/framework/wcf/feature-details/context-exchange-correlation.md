---
title: コンテキスト交換の相関関係
ms.date: 03/30/2017
ms.assetid: 1e2852be-3601-45ae-b507-ccc465d45c60
ms.openlocfilehash: d9de111fa08b4a398bba52bc903ea1fec8c7f298
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/03/2018
ms.locfileid: "43483698"
---
# <a name="context-exchange-correlation"></a>コンテキスト交換の相関関係
コンテキスト相関関係がで説明されているコンテキスト交換メカニズムに基づく、 [.NET コンテキスト交換プロトコルの仕様](https://go.microsoft.com/fwlink/?LinkId=166059)します。 コンテキスト相関関係では、既知のコンテキスト ヘッダーまたはクッキーを使用して、メッセージを正しいインスタンスに関連付けます。 コンテキスト相関関係を使用するには、<xref:System.ServiceModel.BasicHttpContextBinding>、<xref:System.ServiceModel.WSHttpContextBinding>、<xref:System.ServiceModel.NetTcpContextBinding> などのコンテキスト ベースのバインディングが、<xref:System.ServiceModel.Activities.WorkflowServiceHost> に提供されるエンドポイントで使用される必要があります。 このトピックでは、メッセージング アクティビティを指定したコンテキスト相関関係をワークフロー サービス内で使用する方法について説明します。  
  
## <a name="using-context-correlation"></a>コンテキスト相関関係の使用  
 クライアントがワークフロー サービスに繰り返し呼び出しを行う必要があり、そのサービスがコンテキスト バインディングの 1 つを使用してホストされている場合に、コンテキスト相関関係が使用されます。 この種類の相関関係が初期化されて、 <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply>ワークフロー サービス内のペア。 コンテキストは、応答と共にクライアントに送り返されます。その後、クライアントによって、サービスへの以降の呼び出しにアタッチされます。  
  
### <a name="configuring-context-correlation-in-a-workflow-service"></a>ワークフロー サービス内でのコンテキスト相関関係の構成  
 コンテキスト相関関係は、最初の受信メッセージに応答する <xref:System.ServiceModel.Activities.ContextCorrelationInitializer> アクティビティと関連付けられている <xref:System.ServiceModel.Activities.SendReply> を使用して初期化されます。 次の例では、コンテキスト相関関係を初期化するように <xref:System.ServiceModel.Activities.SendReply> が構成されています。  
  
```csharp  
Variable<string> Item = new Variable<string>();  
Variable<CorrelationHandle> OrderHandle = new Variable<CorrelationHandle>();  
  
Receive StartOrder = new Receive  
{  
    CanCreateInstance = true,  
    ServiceContractName = "IOrderService",  
    OperationName = "StartOrder"  
};  
  
SendReply ReplyToStartOrder = new SendReply  
{  
    Request = StartOrder,  
    CorrelationInitializers =  
    {  
        new ContextCorrelationInitializer  
        {  
            CorrelationHandle = OrderHandle  
        }  
    }  
};  
```  
  
> [!NOTE]
>  この例では、実際にはコンテキストの関連付けおよび要求/応答の相関関係の 2 種類の相関関係が使用されています。 コンテキストの相関関係は、クライアントからの呼び出しが適切なインスタンスにルーティングされるように使用されます。 要求/応答の相関関係は、これらのアクティビティによってモデル化される双方向の操作を実装するために、<xref:System.ServiceModel.Activities.Receive> アクティビティおよび <xref:System.ServiceModel.Activities.SendReply> アクティビティで使用されます。 この例では、コンテキスト相関関係は明示的に構成されて、および<xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply>ペアは、暗黙の型によって提供される既定の要求/応答の相関関係を使用して<xref:System.ServiceModel.Activities.CorrelationHandle>管理<xref:System.ServiceModel.Activities.WorkflowServiceHost>します。 使用する場合、 **ReceiveAndSendReply**ワークフロー デザイナーは、要求/応答の相関関係での活動テンプレートを明示的に構成します。 要求-応答の相関関係および暗黙の関連付けハンドル管理の詳細については、次を参照してください。[要求/応答](../../../../docs/framework/wcf/feature-details/request-reply-correlation.md)と[相関関係の概要](../../../../docs/framework/wcf/feature-details/correlation-overview.md)します。 詳細については、 **ReceiveAndSendReply**活動のテンプレートを参照してください[ReceiveAndSendReply](/visualstudio/workflow-designer/receiveandsendreply-template-designer)します。  
  
 ワークフロー サービス内の以降の <xref:System.ServiceModel.Activities.Receive> アクティビティは、前の例の <xref:System.ServiceModel.Activities.CorrelationHandle> で初期化された <xref:System.ServiceModel.Activities.SendReply> を参照できます。  
  
```csharp  
Receive AddItem = new Receive  
{  
    ServiceContractName = "IOrderService",  
    OperationName = "AddItem",  
    CorrelatesWith = OrderHandle  
};  
```  
  
 エンドポイントは、<xref:System.ServiceModel.Activities.WorkflowServiceHost> で、<xref:System.ServiceModel.BasicHttpContextBinding> などのコンテキスト ベースのバインディングを使用するように構成されます。  
  
```xml  
<endpoint  
  contract="IOrderContract"  
  binding = "basicHttpContextBinding"  
  address="http://localhost:8080/OrderService" />  
```  
  
### <a name="configuring-context-correlation-in-a-workflow-client"></a>ワークフロー クライアント内でのコンテキスト相関関係の構成  
 クライアントが別のワークフローである場合は、コンテキスト相関関係をクライアントでも構成する必要があります。 クライアント ワークフローでの<xref:System.ServiceModel.Activities.ReceiveReply>の<xref:System.ServiceModel.Activities.Send> / <xref:System.ServiceModel.Activities.ReceiveReply>でワークフロー サービスへの初期呼び出しのペアを構成する必要があります、<xref:System.ServiceModel.Activities.ContextCorrelationInitializer>します。  
  
```csharp  
Variable<CorrelationHandle> cchandle = new Variable<CorrelationHandle>();  
Send request = new Send  
{  
    // Activity configuration omitted.  
};  
  
ReceiveReply reply = new ReceiveReply  
{  
    Request = request,  
    CorrelationInitializers =   
    {  
        new ContextCorrelationInitializer  
        {  
            CorrelationHandle = cchandle  
        }  
    }  
};  
```  
  
 相関関係が初期化されると、以降の <xref:System.ServiceModel.Activities.Send> アクティビティでは、<xref:System.ServiceModel.Activities.CorrelationHandle> を使用して、同じサービス インスタンスでメソッドを呼び出すことができます。  
  
```csharp  
Send request2 = new Send  
{  
    CorrelatesWith = cchandle,  
    // Remaining activity configuration omitted.  
};  
```  
  
 これらの例では、コンテキスト相関関係が明示的に構成されています。 クライアント ワークフローが <xref:System.ServiceModel.Activities.WorkflowServiceHost> でもホストされていない場合は、アクティビティが <xref:System.ServiceModel.Activities.CorrelationScope> アクティビティ内に含まれていない限り、相関関係を明示的に構成する必要があります。 コンテキスト相関関係の詳細については、次を参照してください。、 [NetContextExchangeCorrelation](https://msdn.microsoft.com/library/93c74a1a-b9e2-46c6-95c0-c9b0e9472caf)サンプル。  
  
 ワークフロー サービスへの呼び出しを行うクライアントがワークフローではない場合でも、ワークフロー サービスへの最初の呼び出しで返されたコンテキストを明示的に渡す限り、呼び出しを繰り返して行うことができます。 サービス参照を [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] ストアに追加することでプロキシが生成され、このコンテキストが既定で渡されます。
