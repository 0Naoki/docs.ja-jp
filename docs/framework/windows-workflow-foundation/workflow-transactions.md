---
title: ワークフロー トランザクション
ms.date: 03/30/2017
ms.assetid: 6081fb02-c0f2-483d-97b8-f3b7dc03011d
ms.openlocfilehash: e2a0c301abac562904e976fe09e5a68697b191e5
ms.sourcegitcommit: 586dbdcaef9767642436b1e4efbe88fb15473d6f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2018
ms.locfileid: "48838092"
---
# <a name="workflow-transactions"></a><span data-ttu-id="7c1cb-102">ワークフロー トランザクション</span><span class="sxs-lookup"><span data-stu-id="7c1cb-102">Workflow Transactions</span></span>

[!INCLUDE[wf1](../../../includes/wf1-md.md)] <span data-ttu-id="7c1cb-103">は、<xref:System.Transactions> アクティビティを使用してトランザクション済み作業単位のスコープを設定することで、<xref:System.Activities.Statements.TransactionScope> トランザクションへの参加をサポートします。</span><span class="sxs-lookup"><span data-stu-id="7c1cb-103"> provides support for participating in <xref:System.Transactions> transactions by using the <xref:System.Activities.Statements.TransactionScope> activity to scope a transacted unit of work.</span></span> <span data-ttu-id="7c1cb-104"><xref:System.Transactions.TransactionScope?displayProperty=nameWithType> は明示的に完了する必要がありますが、<xref:System.Activities.Statements.TransactionScope?displayProperty=nameWithType> アクティビティは正常完了時にトランザクション上で暗黙的に完了を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="7c1cb-104">While the <xref:System.Transactions.TransactionScope?displayProperty=nameWithType> must be explicitly completed the <xref:System.Activities.Statements.TransactionScope?displayProperty=nameWithType> activity implicitly calls complete on the transaction upon successful completion.</span></span> <span data-ttu-id="7c1cb-105"><xref:System.Activities.Statements.TransactionScope.Body%2A> アクティビティの <xref:System.Activities.Statements.TransactionScope> に含まれるすべてのアクティビティは、トランザクションに参加します。</span><span class="sxs-lookup"><span data-stu-id="7c1cb-105">Any activities that are contained in the <xref:System.Activities.Statements.TransactionScope.Body%2A> of the <xref:System.Activities.Statements.TransactionScope> activity participate in the transaction.</span></span> <span data-ttu-id="7c1cb-106">WF は、<xref:System.ServiceModel.Activities.TransactedReceiveScope> アクティビティを使用してワークフローにトランザクションをフローできます。</span><span class="sxs-lookup"><span data-stu-id="7c1cb-106">WF can to flow transactions into a workflow through the use of the <xref:System.ServiceModel.Activities.TransactedReceiveScope> activity.</span></span> <span data-ttu-id="7c1cb-107"><xref:System.Activities.Statements.TransactionScope> アクティビティと同様に、<xref:System.ServiceModel.Activities.TransactedReceiveScope.Body%2A> に含まれるすべてのアクティビティはトランザクションに参加します。</span><span class="sxs-lookup"><span data-stu-id="7c1cb-107">Like the <xref:System.Activities.Statements.TransactionScope> activity, any activity contained in the <xref:System.ServiceModel.Activities.TransactedReceiveScope.Body%2A> participates in the transaction.</span></span> <span data-ttu-id="7c1cb-108">WF は、<xref:System.Transactions.Transaction.Current%2A?displayProperty=nameWithType> に依存するアクティビティが、<xref:System.Activities.Statements.TransactionScope> と <xref:System.ServiceModel.Activities.TransactedReceiveScope> の両方で確実に動作するようにします。</span><span class="sxs-lookup"><span data-stu-id="7c1cb-108">WF ensures that activities dependent on <xref:System.Transactions.Transaction.Current%2A?displayProperty=nameWithType> works with both <xref:System.Activities.Statements.TransactionScope> and <xref:System.ServiceModel.Activities.TransactedReceiveScope>.</span></span> <span data-ttu-id="7c1cb-109">システム標準アクティビティがすべての要件を満たさない場合、高度なフロー シナリオやトランザクション制御シナリオを可能にするには、<xref:System.Activities.RuntimeTransactionHandle> を使用してカスタム アクティビティを構築します。</span><span class="sxs-lookup"><span data-stu-id="7c1cb-109">If the system-provided activities do not address all requirements, custom activities can be built using the <xref:System.Activities.RuntimeTransactionHandle> to enable advanced flow and transaction control scenarios.</span></span>  
  
<span data-ttu-id="7c1cb-110">構成でワークフローを作成、次の例では、<xref:System.Activities.Statements.Sequence>アクティビティを含む子アクティビティを含む、<xref:System.Activities.Statements.TransactionScope>アクティビティ。</span><span class="sxs-lookup"><span data-stu-id="7c1cb-110">In the following example, a workflow is constructed consisting of a <xref:System.Activities.Statements.Sequence> activity that contains child activities including a <xref:System.Activities.Statements.TransactionScope> activity.</span></span> <span data-ttu-id="7c1cb-111"><xref:System.Activities.Statements.TransactionScope.Body%2A> の <xref:System.Activities.Statements.TransactionScope> アクティビティは、<xref:System.Activities.Statements.TransactionScope> アクティビティにより初期化されるトランザクションの下で実行されます。</span><span class="sxs-lookup"><span data-stu-id="7c1cb-111">The <xref:System.Activities.Statements.TransactionScope.Body%2A> activities of the <xref:System.Activities.Statements.TransactionScope> execute under the transaction initialized by the <xref:System.Activities.Statements.TransactionScope> activity.</span></span>  
  
```csharp  
static Activity ScenarioOne()  
{  
    return new Sequence  
    {  
        Activities =  
        {  
            new WriteLine { Text = "    Begin workflow" },  
  
            new TransactionScope  
            {  
                Body = new Sequence  
                {  
                    Activities =   
                    {  
                        new WriteLine { Text = "    Begin TransactionScope" },  
  
                        new PrintTransactionId(),  
  
                        new TransactionScopeTest(),  
  
                        new WriteLine { Text = "    End TransactionScope" },  
                    },  
                },  
            },  
  
            new WriteLine { Text = "    End workflow" },  
        }  
    };  
}  
```  
  
<span data-ttu-id="7c1cb-112">詳細については、使用方法を参照してください<xref:System.ServiceModel.Activities.TransactedReceiveScope>を参照してください[ワークフロー サービスとの間にトランザクションをフロー](../../../docs/framework/wcf/feature-details/flowing-transactions-into-and-out-of-workflow-services.md)します。</span><span class="sxs-lookup"><span data-stu-id="7c1cb-112">For more information, see about using <xref:System.ServiceModel.Activities.TransactedReceiveScope>, see [Flowing Transactions into and out of Workflow Services](../../../docs/framework/wcf/feature-details/flowing-transactions-into-and-out-of-workflow-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c1cb-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="7c1cb-113">See Also</span></span>  
 <xref:System.Activities.Statements.TransactionScope>  
 <xref:System.Transactions.TransactionScope>  
 <xref:System.Transactions.Transaction.Current%2A?displayProperty=nameWithType>
