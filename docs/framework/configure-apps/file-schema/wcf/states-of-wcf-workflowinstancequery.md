---
title: WCF の &lt;states&gt;、&lt;workflowInstanceQuery&gt;
ms.date: 03/30/2017
ms.assetid: d17f7525-8035-4e9e-85a0-4cddae59f85d
ms.openlocfilehash: a6c54f0903f30b5a7c3147cf4b874516a766c2b8
ms.sourcegitcommit: 15d99019aea4a5c3c91ddc9ba23692284a7f61f3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/12/2018
ms.locfileid: "49121945"
---
# <a name="ltstatesgt-of-wcf-ltworkflowinstancequerygt"></a>WCF の &lt;states&gt;、&lt;workflowInstanceQuery&gt;

追跡レコードが作成されたときの追跡ワークフロー インスタンスの定期受信済み状態のコレクションを表します。  
  
追跡プロファイルのクエリの詳細については、次を参照してください[追跡プロファイル。](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)  
  
\<system.serviceModel >\<追跡 >  
\<プロファイル >  
\<trackingProfile>  
\<ワークフロー >  
\<workflowInstanceQueries>  
\<workflowInstanceQuery >  
\<状態 >  
  
## <a name="syntax"></a>構文  
  
```xml
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <workflowInstanceQueries>
          <workflowInstanceQuery>
            <states>
              <state name="Name"/>
            </states>
          </workflowInstanceQuery>
        </workflowInstanceQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```
  
## <a name="attributes-and-elements"></a>属性と要素

以降のセクションでは、属性、子要素、および親要素について説明します。  
  
### <a name="attributes"></a>属性  

なし。  
  
### <a name="child-elements"></a>子要素
  
|要素|説明|  
|-------------|-----------------|  
|[\<状態 >](state-of-wcf-workflowinstancequery.md)|追跡レコードが作成されたときの追跡ワークフロー インスタンスの定期受信済み状態。|  
  
### <a name="parent-elements"></a>親要素  
  
|要素|説明|  
|-------------|-----------------|  
|[\<workflowInstanceQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowinstancequery.md)|開始したイベントや完了したイベントなど、ワークフロー インスタンスのライフサイクルの変化を追跡するクエリ。|  
  
## <a name="remarks"></a>Remarks

返されたレコードは、このコレクションの状態でフィルター処理されます。  
  
次の表に、有効な状態の値を示します。  
  
|状態|説明|  
|-----------|-----------------|  
|Aborted|ワークフロー インスタンスは中止されました。|  
|Completed|ワークフロー インスタンスは完了しました。|  
|Deleted|ワークフロー インスタンスは削除されました。|  
|Idle|ワークフロー インスタンスはアイドル状態です。|  
|Persisted|ワークフロー インスタンスは永続化されました。|  
|Resumed|ワークフロー インスタンスが再開されました。|  
|Started|ワークフロー インスタンスが開始されました。|  
|UnhandledException|ワークフロー インスタンスで未処理の例外が発生しました。|  
|アンロード|ワークフロー インスタンスはアンロードされました。|  
|Canceled|ワークフロー インスタンスは取り消されました。|  
|Suspended|ワークフロー インスタンスが中断されています。|  
|Terminated|ワークフロー インスタンスは終了しました。|  
|Unsuspended|ワークフロー インスタンスの中断が解除されました。|  
  
## <a name="example"></a>例

次の構成は、このクエリを使用して、`Started` インスタンス状態のワークフロー インスタンス レベルの追跡レコードを定期受信します。  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a>関連項目  

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>       
- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElementCollection?displayProperty=nameWithType>       
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>       
- [ワークフローの追跡とトレース](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
- [追跡プロファイル](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
